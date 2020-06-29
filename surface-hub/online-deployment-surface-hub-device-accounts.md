---
title: Office 365를 사용한 온라인 배포(Surface Hub)
description: 이 항목에서는 순수 온라인 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub에 대한 장치 계정, 온라인 배포
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836132"
---
# Office 365를 사용한 온라인 배포(Surface Hub)


이 항목에서는 순수 온라인 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.

순수 온라인(O365) 배포가 있는 경우 [제공된 PowerShell 스크립트를 사용](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts)하여 장치 계정을 만들 수 있습니다. 

1. PC에서 원격 PowerShell 세션을 시작하고 Exchange에 연결합니다.

   관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. 세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 회의실 사서함의 설정을 변경합니다. 이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.

   기존 리소스 사서함을 변경하는 경우

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   새 리소스 사서함을 만드는 경우

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.

   Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다. 제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.

   호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다. 정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   호환되는 정책이 만들어지면 장치 계정에 정책을 적용해야 합니다.

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. 장치 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선해야 합니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Azure AD에 연결합니다.
    
   먼저 PowerShell 버전 2용 Azure AD 모듈을 설치해야 합니다. 관리자 권한 powershell 프롬프트에서 다음 명령을 실행합니다.
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   일부 계정 설정을 적용하려면 Azure AD에 연결해야 합니다. 이 cmdlet을 실행하여 연결할 수 있습니다.

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. 암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다. 자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub에는 비즈니스용 Skype 라이선스가 필요합니다. 비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 [비즈니스용 Skype Online의 필수 조건](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online)을 충족해야 합니다.
   
   다음으로 `Get-AzureADSubscribedSku`를 사용하여 O365 테넌트에 사용 가능한 SKU 목록을 검색할 수 있습니다.

   SKU 목록을 표시한 후에는 `$License.SkuId` 변수에 원하는 SkuId를 할당해야 합니다.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. 비즈니스용 Skype와 함께 장치 계정을 사용하도록 설정합니다.
   비즈니스용 Skype PowerShell 모듈이 설치되어 있지 않으면 [비즈니스용 Skype Online Windows PowerShell 모듈을 다운로드](https://www.microsoft.com/download/details.aspx?id=39366)합니다. 

   - 먼저 PC에서 원격 PowerShell 세션을 만듭니다.

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - 그 다음, 사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 이 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자의 값을 가져올 수 있습니다(예: <em>alice@contoso.com</em>).

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       또는 변수를 설정하여 가져 올 수도 있습니다.
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - 다음 cmdlet을 통해 Surface Hub 계정을 사용합니다.
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       또는 위의 $strRegistarPool 변수를 사용합니다.
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

유효성 검사를 위해 비즈니스용 Skype 클라이언트(PC, Android 등)를 사용하여 이 계정에 로그인할 수 있어야 합니다.





