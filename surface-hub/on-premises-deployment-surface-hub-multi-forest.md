---
title: 온-프레미스 배포 다중 포리스트(Surface Hub)
description: 이 항목에서는 다중 포리스트 온-프레미스 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.
keywords: 다중 포리스트 배포, 온 프레미스 배포, 장치 계정, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836135"
---
# 다중 포리스트 환경에서 Surface Hub에 대한 온-프레미스 배포


이 항목에서는 다중 포리스트 온-프레미스 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.

Microsoft Exchange 2013 이상과 비즈니스용 Skype 2013 이상이 포함된 다중 포리스트 온-프레미스 배포가 있는 경우 [제공된 PowerShell 스크립트를 사용](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)하여 장치 계정을 만들 수 있습니다. 단일 포리스트 배포를 사용하는 경우 [단일 포리스트 환경에서 Surface Hub에 대한 온-프레미스 배포](on-premises-deployment-surface-hub-device-accounts.md)를 참조하세요.

1.  PC에서 원격 PowerShell 세션을 시작하고 Exchange에 연결합니다.

    관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.

    여기서 `$strExchangeServer`는 Exchange 서버의 FQDN(정규화된 도메인 이름)이고 `$strLyncFQDN`은 비즈니스용 Skype 서버의 FQDN입니다.

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  세션을 설정한 후 리소스 포리스트에서 새 사서함을 만듭니다. 이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.

    기존 리소스 사서함을 변경하는 경우:

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.

    Surface Hub는 **PasswordEnabled** 속성이 **False**로 설정된 ActiveSync 정책이 있는 장치 계정하고만 호환됩니다. 제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.

    호환되는 정책을 아직 만들지 않은 경우 "Surface Hubs"라는 정책을 만드는 다음 cmdlet을 사용합니다. 정책을 만든 후 다른 장치 계정에 동일한 정책을 적용할 수 있습니다.

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    호환되는 정책이 만들어지면 장치 계정에 정책을 적용해야 합니다. 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  장치 계정에서 다양한 Exchange 속성을 설정하여 사용자의 모임 환경을 개선할 수 있습니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다. 자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요. 사용자 포리스트에서 설정해야 합니다.

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  Active Directory에서 계정을 사용하도록 설정하여 Surface Hub에 인증할 수 있게 합니다. 사용자 포리스트에서 설정해야 합니다.

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. 이제 회의실 사서함을 연결된 사서함으로 변경해야 합니다.

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  비즈니스용 Skype 서버 풀에서 Surface Hub AD 계정을 사용하도록 설정하여 비즈니스용 Skype와 함께 장치 계정을 사용하도록 설정합니다.

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    고유한 비즈니스용 Skype 서버 풀 식별자 및 사용자 ID와 함께 Surface Hub에 대한 SIP(Session Initiation Protocol) 주소 및 도메인 컨트롤러를 사용해야 합니다.


## 익명 전자 메일 및 메신저 사용 안 함



Surface Hub는 장치 계정을 사용 하 여 전자 메일 및 공동 작업 서비스 (IM, 비디오, 음성)를 제공 합니다. 이 디바이스 계정은 전자 메일, 메신저 대화, 통화를 보낼 때의 원래 id ("보낸 사람")로 사용 됩니다. 이 계정은 개인 식별이 가능 사용자에 게는 제공 되지 않으므로 Surface Hub의 디바이스 계정에서 시작 되었기 때문에 "anonymous"로 간주 됩니다.  

**SurfaceHubPolicy**의 id를 사용 하 여 각 회의실 디바이스에 사용자 단위 클라이언트 정책이 할당 되어 있다고 가정 합니다. 익명 전자 메일 및 메시지를 사용 하지 않도록 설정 하려면 다음 명령을 사용 하 여이 클라이언트 정책에 clientPolicyEntry를 추가 합니다.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

정책이 설정 되었는지 확인 하려면 다음을 수행 합니다.

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

출력은 다음과 같아야 합니다.

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
정책 항목을 변경 하려면 다음을 실행 합니다.

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
정책 항목을 제거 하려면 다음을 실행 합니다.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





