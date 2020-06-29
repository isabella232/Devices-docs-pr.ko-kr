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
# <span data-ttu-id="0b008-104">Office 365를 사용한 온라인 배포(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="0b008-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="0b008-105">이 항목에서는 순수 온라인 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="0b008-106">순수 온라인(O365) 배포가 있는 경우 [제공된 PowerShell 스크립트를 사용](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts)하여 장치 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="0b008-107">PC에서 원격 PowerShell 세션을 시작하고 Exchange에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="0b008-108">관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="0b008-109">세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 회의실 사서함의 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="0b008-110">이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="0b008-111">기존 리소스 사서함을 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="0b008-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="0b008-112">새 리소스 사서함을 만드는 경우</span><span class="sxs-lookup"><span data-stu-id="0b008-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="0b008-113">사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="0b008-114">Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="0b008-115">제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="0b008-116">호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="0b008-117">정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="0b008-118">호환되는 정책이 만들어지면 장치 계정에 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="0b008-119">장치 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="0b008-120">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="0b008-121">Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="0b008-122">먼저 PowerShell 버전 2용 Azure AD 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="0b008-123">관리자 권한 powershell 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="0b008-124">일부 계정 설정을 적용하려면 Azure AD에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="0b008-125">이 cmdlet을 실행하여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="0b008-126">암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="0b008-127">자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b008-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="0b008-128">Surface Hub에는 비즈니스용 Skype 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="0b008-129">비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 [비즈니스용 Skype Online의 필수 조건](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online)을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="0b008-130">다음으로 `Get-AzureADSubscribedSku`를 사용하여 O365 테넌트에 사용 가능한 SKU 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="0b008-131">SKU 목록을 표시한 후에는 `$License.SkuId` 변수에 원하는 SkuId를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

8. <span data-ttu-id="0b008-132">비즈니스용 Skype와 함께 장치 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="0b008-133">비즈니스용 Skype PowerShell 모듈이 설치되어 있지 않으면 [비즈니스용 Skype Online Windows PowerShell 모듈을 다운로드](https://www.microsoft.com/download/details.aspx?id=39366)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="0b008-134">먼저 PC에서 원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="0b008-135">그 다음, 사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 이 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자의 값을 가져올 수 있습니다(예: <em>alice@contoso.com</em>).</span><span class="sxs-lookup"><span data-stu-id="0b008-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="0b008-136">또는 변수를 설정하여 가져 올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="0b008-137">다음 cmdlet을 통해 Surface Hub 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="0b008-138">또는 위의 $strRegistarPool 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="0b008-139">유효성 검사를 위해 비즈니스용 Skype 클라이언트(PC, Android 등)를 사용하여 이 계정에 로그인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b008-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>





