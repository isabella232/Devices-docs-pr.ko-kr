---
title: 하이브리드 배포(Surface Hub)
description: 하이브리드 배포에서 Microsoft Surface Hub에 대한 디바이스 계정을 설정하려면 특별한 처리가 필요합니다.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: 하이브리드 배포, Surface Hub용 디바이스 계정, Exchange에서 호스트하는 온-프레미스, Exchange에서 호스트하는 온라인
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836204"
---
# <span data-ttu-id="067c2-104">하이브리드 배포(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="067c2-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="067c2-105">하이브리드 배포에서 Microsoft Surface Hub에 대한 디바이스 계정을 설정하려면 특별한 처리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="067c2-106">온-프레미스에 호스트된 서비스와 온라인에 호스트된 서비스가 혼합되어 있는 하이브리드 배포를 사용하는 경우 각 서버가 호스트된 위치에 따라 구성이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="067c2-107">이 항목에서는 [온-프레미스에 호스트된 Exchange](#exchange-on-premises), [온라인에 호스트된 Exchange](#exchange-online), 비즈니스용 Skype 온-프레미스, 비즈니스용 Skype Online 및 비즈니스용 Skype 하이브리드 Skype에 대한 하이브리드 배포를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="067c2-108">이 배포 유형에는 너무 많은 변형이 있으므로 모든 변형에 대한 자세한 지침을 제공할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="067c2-109">다음 프로세스는 대부분의 구성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-109">The following process will work for many configurations.</span></span> <span data-ttu-id="067c2-110">프로세스가 설치에 부적합한 경우 다른 배포 옵션에 대해 이 문서에 설명된 것과 동일한 최종 결과를 얻기 위해 PowerShell([부록: PowerShell ](appendix-a-powershell-scripts-for-surface-hub.md)참조)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="067c2-111">그런 다음 제공된 PowerShell 스크립트를 사용하여 Surface Hub 설치를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="067c2-112">[계정 확인 스크립트](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="067c2-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="067c2-113">Exchange 하이브리드 환경에서 [exchange 온-프레미스](#exchange-on-premises)에 대 한 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="067c2-114">Exchange 개체를 Office 365으로 이동 하려면 [MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="067c2-115">온-프레미스 Exchange</span><span class="sxs-lookup"><span data-stu-id="067c2-115">Exchange on-premises</span></span>

<span data-ttu-id="067c2-116">온-프레미스 Exchange를 사용하는 경우 이 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="067c2-117">이 절차에서는 AD 관리 도구를 사용하여 온-프레미스 도메인 계정의 메일 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="067c2-118">이 계정은 Office 365와 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="067c2-119">**Active Directory 사용자 및 컴퓨터** AD 도구에서 Surface Hub 계정을 만들 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**, **사용자**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="067c2-120">**전체 이름** 상자에 이전 cmdlet의 표시 이름을 입력하고 **사용자 로그온 이름** 상자에 별칭을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="067c2-121">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-121">Click **Next**.</span></span><p>

![Active Directory에서 새 사용자를 만들기 위한 새 개체 상자.](images/hybriddeployment-01a.png)

- <span data-ttu-id="067c2-123">이 계정의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-123">Type the password for this account.</span></span> <span data-ttu-id="067c2-124">확인을 위해 다시 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="067c2-125">**암호 사용 기간 제한 없음** 확인란만 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="067c2-126">**중요** Surface Hub의 비즈니스용 Skype를 사용하려면 **암호 사용 기간 제한 없음**을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="067c2-127">도메인 규칙에서 사용 기간 제한이 없는 암호를 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="067c2-128">이 경우 각 Surface Hub 디바이스 계정에 대한 예외를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![암호 대화 상자를 표시하는 이미지](images/hybriddeployment-02a.png)

-   <span data-ttu-id="067c2-130">**마침** 을 클릭하여 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-130">Click **Finish** to create the account.</span></span>

![새 사용자에 대한 계정 이름, 로그온 이름 및 암호 옵션을 보여 주는 이미지](images/hybriddeployment-03a.png)

2. <span data-ttu-id="067c2-132">원격 사서함을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="067c2-133">관리자 권한으로 온-프레미스 Exchange 관리 셸을 열고 이 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="067c2-134">이 cmdlet을 실행하기 위한 온-프레미스 Exchange 환경이 없는 경우 계정의 Active Directory 개체에 직접 동일한 변경을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="067c2-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="067c2-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="067c2-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="067c2-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="067c2-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="067c2-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="067c2-138">계정을 만든 후 디렉터리 동기화를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="067c2-139">완료 되 면 Microsoft 365 관리 센터의 사용자 페이지로 이동 하 여 이전 단계에서 만든 계정이 온라인에 병합 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="067c2-140">Microsoft Exchange Online에 연결하고 Office 365에서 계정의 몇 가지 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="067c2-141">PC에서 원격 PowerShell 세션을 시작하고 Microsoft Exchange에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="067c2-142">관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="067c2-143">다음 단계는 Office 365 테넌트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="067c2-144">새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="067c2-145">사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="067c2-146">Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="067c2-147">제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="067c2-148">호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="067c2-149">정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="067c2-150">호환 되는 정책을 사용 하는 경우에는 해당 정책을 디바이스 계정에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="067c2-151">Exchange 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-151">Set Exchange properties.</span></span>

<span data-ttu-id="067c2-152">디바이스 계정에서 Exchange 속성을 설정하여 모임 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="067c2-153">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="067c2-154">Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-154">Connect to Azure AD.</span></span>

<span data-ttu-id="067c2-155">먼저 PowerShell 버전 2용 Azure AD 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="067c2-156">관리자 권한 PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="067c2-157">일부 계정 설정을 적용하려면 Azure AD에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="067c2-158">이 cmdlet을 실행하여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="067c2-159">Office 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="067c2-160">디바이스 계정에 유효한 Office 365(O365) 라이선스가 있어야 합니다. 그렇지 않으면 Exchange와 비즈니스용 Skype가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="067c2-161">라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 이에 따라 계정에 사용할 수 있는 라이선스 SKU가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="067c2-162">`Get-AzureADSubscribedSku`를 사용하여 O365 테넌트에 사용 가능한 SKU 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="067c2-163">SKU 목록을 표시한 후에는 `$License.SkuId` 변수에 원하는 SkuId를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="067c2-164">다음으로 [비즈니스용 Skype Online](#skype-for-business-online), [비즈니스용 Skype 온-프레미스](#skype-for-business-on-premises) 또는 [비즈니스용 Skype 하이브리드](#skype-for-business-hybrid)에서 디바이스 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="067c2-165">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="067c2-165">Skype for Business Online</span></span>

<span data-ttu-id="067c2-166">비즈니스용 Skype Online을 사용하려면 테넌트 사용자에게 Exchange 사서함이 있어야 합니다(테넌트에 Exchange 사서함이 하나 이상 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="067c2-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="067c2-167">다음 표에서 필요한 계획 또는 추가 서비스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="067c2-168">Skype 공간 시스템 시나리오</span><span class="sxs-lookup"><span data-stu-id="067c2-168">Skype room system scenario</span></span> | <span data-ttu-id="067c2-169">Office 365 Premium, 엔터프라이즈 용 Microsoft 365 앱 또는 비즈니스용 Skype 독립 실행형 요금제 2를 사용 하는 경우 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="067c2-170">엔터프라이즈 기반 요금제를 사용하는 경우 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="067c2-171">비즈니스용 Skype 서버 2015 (온-프레미스 또는 하이브리드)이 있는 경우 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="067c2-172">예약된 모임에 참가</span><span class="sxs-lookup"><span data-stu-id="067c2-172">Join a scheduled meeting</span></span> | <span data-ttu-id="067c2-173">비즈니스용 Skype 독립 실행형 요금제 1</span><span class="sxs-lookup"><span data-stu-id="067c2-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="067c2-174">E1, 3, 4, 또는 5</span><span class="sxs-lookup"><span data-stu-id="067c2-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="067c2-175">비즈니스용 Skype 서버 Standard CAL</span><span class="sxs-lookup"><span data-stu-id="067c2-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="067c2-176">임시 회의 시작</span><span class="sxs-lookup"><span data-stu-id="067c2-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="067c2-177">비즈니스용 Skype 독립 실행형 요금제 2</span><span class="sxs-lookup"><span data-stu-id="067c2-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="067c2-178">E1, 3, 4, 또는 5</span><span class="sxs-lookup"><span data-stu-id="067c2-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="067c2-179">비즈니스용 Skype 서버 Standard CAL 또는 Enterprise CAL</span><span class="sxs-lookup"><span data-stu-id="067c2-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="067c2-180">임시 회의를 시작하고 회의에서 해당 번호에 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="067c2-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="067c2-181">비즈니스용 Skype 독립 실행형 요금제 2, 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="067c2-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="067c2-182">**참고** PSTN 소비 청구는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="067c2-183">E1 또는 E3 (오디오 회의) 또는 E5</span><span class="sxs-lookup"><span data-stu-id="067c2-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="067c2-184">비즈니스용 Skype 서버 Standard CAL 또는 Enterprise CAL</span><span class="sxs-lookup"><span data-stu-id="067c2-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="067c2-185">회의실에 전화 번호를 제공하고 회의실에서 전화를 걸거나 받고 또는 전화 번호를 사용하여 전화 접속 회의 참석</span><span class="sxs-lookup"><span data-stu-id="067c2-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="067c2-186">전화 시스템 및 PSTN 음성 통화 요금제를 사용 하는 비즈니스용 Skype 독립 실행형 요금제 2</span><span class="sxs-lookup"><span data-stu-id="067c2-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="067c2-187">전화 시스템 및 PSTN 음성 통화 요금제 또는 E5와 E1 또는 E3</span><span class="sxs-lookup"><span data-stu-id="067c2-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="067c2-188">비즈니스용 Skype 서버 Standard CAL 또는 Plus CAL</span><span class="sxs-lookup"><span data-stu-id="067c2-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="067c2-189">다음 표에서 Office 365 요금제 및 비즈니스용 Skype 옵션을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="067c2-190">O365 요금제</span><span class="sxs-lookup"><span data-stu-id="067c2-190">O365 Plan</span></span> | <span data-ttu-id="067c2-191">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="067c2-191">Skype for Business</span></span> | <span data-ttu-id="067c2-192">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="067c2-192">Phone System</span></span> | <span data-ttu-id="067c2-193">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="067c2-193">Audio Conferencing</span></span> | <span data-ttu-id="067c2-194">통화 요금제</span><span class="sxs-lookup"><span data-stu-id="067c2-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="067c2-195">O365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="067c2-195">O365 Business Essentials</span></span> | <span data-ttu-id="067c2-196">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-196">Included</span></span> |  |  |  |
| <span data-ttu-id="067c2-197">O365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="067c2-197">O365 Business Premium</span></span> | <span data-ttu-id="067c2-198">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-198">Included</span></span> |  |  |  |
| <span data-ttu-id="067c2-199">E1</span><span class="sxs-lookup"><span data-stu-id="067c2-199">E1</span></span> | <span data-ttu-id="067c2-200">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-200">Included</span></span> | <span data-ttu-id="067c2-201">추가 기능</span><span class="sxs-lookup"><span data-stu-id="067c2-201">Add-on</span></span> | <span data-ttu-id="067c2-202">추가 기능</span><span class="sxs-lookup"><span data-stu-id="067c2-202">Add-on</span></span> | <span data-ttu-id="067c2-203">추가 기능 (전화 시스템 추가 기능 필요)</span><span class="sxs-lookup"><span data-stu-id="067c2-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="067c2-204">E3</span><span class="sxs-lookup"><span data-stu-id="067c2-204">E3</span></span> | <span data-ttu-id="067c2-205">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-205">Included</span></span> | <span data-ttu-id="067c2-206">추가 기능</span><span class="sxs-lookup"><span data-stu-id="067c2-206">Add-on</span></span> | <span data-ttu-id="067c2-207">추가 기능</span><span class="sxs-lookup"><span data-stu-id="067c2-207">Add-on</span></span> | <span data-ttu-id="067c2-208">추가 기능 (전화 시스템 추가 기능 필요)</span><span class="sxs-lookup"><span data-stu-id="067c2-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="067c2-209">E5</span><span class="sxs-lookup"><span data-stu-id="067c2-209">E5</span></span> | <span data-ttu-id="067c2-210">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-210">Included</span></span> | <span data-ttu-id="067c2-211">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-211">Included</span></span> | <span data-ttu-id="067c2-212">포함</span><span class="sxs-lookup"><span data-stu-id="067c2-212">Included</span></span> | <span data-ttu-id="067c2-213">추가 기능</span><span class="sxs-lookup"><span data-stu-id="067c2-213">Add-on</span></span>  |

1. <span data-ttu-id="067c2-214">먼저 PC와 비즈니스용 Skype Online 환경 간의 원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="067c2-215">비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="067c2-216">사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="067c2-217">Surface Hub 계정에 비즈니스용 Skype 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="067c2-218">비즈니스용 Skype Online에서 Surface Hub 계정을 사용하도록 설정하는 이전 단계를 완료했으면 Surface Hub에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="067c2-219">O365 관리 포털을 사용 하 여 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스를 장치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="067c2-220">테넌트 관리자로 로그인하고 O365 관리 포털을 연 다음 관리자 앱을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="067c2-221">**사용자 및 그룹** 을 클릭한 다음 **사용자 추가, 암호 재설정 등**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="067c2-222">Surface Hub 계정을 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="067c2-223">**라이선스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-223">Click **Licenses**.</span></span>

- <span data-ttu-id="067c2-224">라이선스 **할당**에서 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 비즈니스용 Skype (계획 1) 또는 비즈니스용 Skype (요금제 2)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="067c2-225">Surface Hub에서 엔터프라이즈 음성을 사용 하려면 요금제 2 라이선스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="067c2-226">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="067c2-227">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하여 이러한 라이선스 중 하나를 할당하는 데 필요한 cmdlet을 실행할 수도 있지만 여기서는 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="067c2-228">유효성 검사를 위해 비즈니스용 Skype 클라이언트(PC, Android 등)를 사용하여 이 계정에 로그인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="067c2-229">비즈니스용 Skype 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="067c2-229">Skype for Business on-premises</span></span>

<span data-ttu-id="067c2-230">이 cmdlet을 실행하려면 Skype 프런트 엔드 중 하나에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="067c2-231">Skype PowerShell을 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="067c2-232">비즈니스용 Skype 하이브리드</span><span class="sxs-lookup"><span data-stu-id="067c2-232">Skype for Business hybrid</span></span>

<span data-ttu-id="067c2-233">조직에서 [비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결](https://technet.microsoft.com/library/jj205403.aspx)을 설정한 경우에는 계정을 만들기 위한 지침이 표준 Surface Hub 배포와 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="067c2-234">Surface Hub에는 `meetingroom` 유형의 Skype 계정이 필요하지만 일반 사용자는 Skype에서 사용자 유형 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="067c2-235">사용자가 로컬 Skype 서버에 있을 수도 있고 Office 365에서 호스트될 수도 있는 하이브리드에 대해 Skype 서버를 설정한 경우 Surface Hub 계정을 만들려고 하면 몇 가지 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="067c2-236">비즈니스용 Skype Server 2015 하이브리드 환경에서는 Active Directory 도메인 서비스에서 사용자 계정을 만들 수 있도록 온-프레미스 배포에서 비즈니스용 Skype Online에서 원하는 사용자를 먼저 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="067c2-237">그런 다음 사용자를 비즈니스용 Skype Online으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="067c2-238">온-프레미스에서 온라인으로 사용자 계정을 이동 하는 작업은 [csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="067c2-239">Csmeetingroom 개체를 이동 하려면 [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="067c2-240">CsMeetingRoom cmdlet을 사용 하려면 [비즈니스용 Skype server 2015에는 5 월 2017 누적 업데이트 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) 또는 [Lync Server 2013의 7 2017 월 누적 업데이트 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="067c2-241">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="067c2-241">Exchange online</span></span>

<span data-ttu-id="067c2-242">Exchange Online을 사용하는 경우 이 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="067c2-243">Office 365에서 메일 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="067c2-244">PC에서 원격 PowerShell 세션을 시작하고 Exchange에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="067c2-245">관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="067c2-246">사서함을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-246">Set up a mailbox.</span></span>

<span data-ttu-id="067c2-247">세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 회의실 사서함의 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="067c2-248">이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="067c2-249">기존 리소스 사서함을 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="067c2-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="067c2-250">새 리소스 사서함을 만드는 경우</span><span class="sxs-lookup"><span data-stu-id="067c2-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="067c2-251">Exchange ActiveSync 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="067c2-252">사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="067c2-253">Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="067c2-254">이 기능이 제대로 설정 되어 있지 않으면 Surface Hub의 Exchange 서비스 (메일, 일정, 모임 참가)가 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="067c2-255">호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="067c2-256">정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="067c2-257">호환 되는 정책을 사용 하는 경우에는 해당 정책을 디바이스 계정에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="067c2-258">그러나 정책은 사용자 계정에만 적용할 수 있고 리소스 사서함에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="067c2-259">사서함을 사용자 유형으로 변환하고 정책을 적용한 다음 사서함으로 다시 변환합니다. 다시 사용하도록 설정하고 암호도 다시 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="067c2-260">Exchange 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-260">Set Exchange properties.</span></span>

<span data-ttu-id="067c2-261">디바이스 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="067c2-262">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="067c2-263">온-프레미스 도메인 계정에 대 한 전자 메일 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="067c2-264">이 절차에서는 AD 관리 도구를 사용하여 온-프레미스 도메인 계정의 메일 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="067c2-265">**Active Directory 사용자 및 컴퓨터** AD 도구에서 Surface Hub 계정을 만들 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**, **사용자**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="067c2-266">**전체 이름** 상자에 이전 cmdlet의 표시 이름을 입력하고 **사용자 로그온 이름** 상자에 별칭을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="067c2-267">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-267">Click **Next**.</span></span>

![Active Directory에서 새 사용자를 만들기 위한 새 개체 상자](images/hybriddeployment-01a.png)

- <span data-ttu-id="067c2-269">이 계정의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-269">Type the password for this account.</span></span> <span data-ttu-id="067c2-270">확인을 위해 다시 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="067c2-271">**암호 사용 기간 제한 없음** 확인란만 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="067c2-272">**암호 사용 기간 제한 없음** 선택은 Surface Hub의 비즈니스용 Skype에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="067c2-273">도메인 규칙에서 사용 기간 제한이 없는 암호를 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="067c2-274">이 경우 각 Surface Hub 디바이스 계정에 대한 예외를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![암호 대화 상자를 표시하는 이미지](images/hybriddeployment-02a.png)

- <span data-ttu-id="067c2-276">**마침** 을 클릭하여 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-276">Click **Finish** to create the account.</span></span>

![새 사용자에 대한 계정 이름, 로그온 이름 및 암호 옵션을 보여 주는 이미지](images/hybriddeployment-03a.png)

6. <span data-ttu-id="067c2-278">디렉터리 동기화를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-278">Run directory synchronization.</span></span>

<span data-ttu-id="067c2-279">계정을 만든 후 디렉터리 동기화를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="067c2-280">완료되면 사용자 페이지로 이동한 다음 이전 단계에서 만든 두 계정이 병합되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="067c2-281">Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-281">Connect to Azure AD.</span></span>

<span data-ttu-id="067c2-282">먼저 PowerShell 버전 2용 Azure AD 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="067c2-283">관리자 권한 PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="067c2-284">일부 계정 설정을 적용하려면 Azure AD에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="067c2-285">이 cmdlet을 실행 하 여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="067c2-286">Office 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="067c2-287">디바이스 계정에 유효한 Office 365(O365) 라이선스가 있어야 합니다. 그렇지 않으면 Exchange와 비즈니스용 Skype가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="067c2-288">라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 이에 따라 계정에 사용할 수 있는 라이선스 SKU가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="067c2-289">다음으로 `Get-AzureADSubscribedSku`를 사용하여 O365 테넌트에 사용 가능한 SKU 목록을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="067c2-290">SKU 목록을 표시한 후에는 `$License.SkuId` 변수에 원하는 SkuId를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="067c2-291">다음으로 [비즈니스용 Skype Online](#skype-for-business-online), [비즈니스용 Skype 온-프레미스](#skype-for-business-on-premises) 또는 [비즈니스용 Skype 하이브리드](#skype-for-business-hybrid)에서 디바이스 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="067c2-292">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="067c2-292">Skype for Business Online</span></span>

<span data-ttu-id="067c2-293">비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 [비즈니스용 Skype Online의 필수 조건](#skype-for-business-online)을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="067c2-294">먼저 PC와 비즈니스용 Skype Online 환경 간의 원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="067c2-295">비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="067c2-296">사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="067c2-297">Surface Hub 계정에 비즈니스용 Skype 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="067c2-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="067c2-298">비즈니스용 Skype Online에서 Surface Hub 계정을 사용하도록 설정하는 이전 단계를 완료했으면 Surface Hub에 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="067c2-299">O365 관리 포털을 사용 하 여 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스를 장치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="067c2-300">테넌트 관리자로 로그인하고 O365 관리 포털을 연 다음 관리자 앱을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="067c2-301">**사용자 및 그룹** 을 클릭한 다음 **사용자 추가, 암호 다시 설정 등**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="067c2-302">Surface Hub 계정을 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="067c2-303">**라이선스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-303">Click **Licenses**.</span></span>

- <span data-ttu-id="067c2-304">라이선스 및 엔터프라이즈 음성 요구 사항에 따라 **라이선스 할당**에서 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="067c2-305">Surface Hub에서 엔터프라이즈 음성을 사용하려는 경우 계획 3 라이선스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="067c2-306">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="067c2-307">Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하여 이러한 라이선스 중 하나를 할당하는 데 필요한 cmdlet을 실행할 수도 있지만 여기서는 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="067c2-308">유효성 검사를 위해 비즈니스용 Skype 클라이언트(PC, Android 등)를 사용하여 이 계정에 로그인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="067c2-309">비즈니스용 Skype 온-프레미스</span><span class="sxs-lookup"><span data-stu-id="067c2-309">Skype for Business on-premises</span></span>

<span data-ttu-id="067c2-310">이 cmdlet을 실행하려면 Skype 프런트 엔드 중 하나에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="067c2-311">Skype PowerShell을 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="067c2-312">비즈니스용 Skype 하이브리드</span><span class="sxs-lookup"><span data-stu-id="067c2-312">Skype for Business hybrid</span></span>

<span data-ttu-id="067c2-313">조직에서 [비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결](https://technet.microsoft.com/library/jj205403.aspx)을 설정한 경우에는 계정을 만들기 위한 지침이 표준 Surface Hub 배포와 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="067c2-314">Surface Hub에는 *meetingroom* 유형의 Skype 계정이 필요하지만 일반 사용자는 Skype에서 *사용자* 유형 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="067c2-315">사용자가 로컬 Skype 서버에 있을 수도 있고 Office 365에서 호스트될 수도 있는 하이브리드에 대해 Skype 서버를 설정한 경우 Surface Hub 계정을 만들려고 하면 몇 가지 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="067c2-316">비즈니스용 Skype Server 2015 하이브리드 환경에서는 Active Directory 도메인 서비스에서 사용자 계정을 만들 수 있도록 온-프레미스 배포에서 비즈니스용 Skype Online에서 원하는 사용자를 먼저 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="067c2-317">그런 다음 사용자를 비즈니스용 Skype Online으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="067c2-318">온-프레미스에서 온라인으로 사용자 계정을 이동 하는 작업은 [csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="067c2-319">Csmeetingroom 개체를 이동 하려면 [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="067c2-320">CsMeetingRoom cmdlet을 사용 하려면 [비즈니스용 Skype server 2015에는 5 월 2017 누적 업데이트 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) 또는 [Lync Server 2013의 7 2017 월 누적 업데이트 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="067c2-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>
