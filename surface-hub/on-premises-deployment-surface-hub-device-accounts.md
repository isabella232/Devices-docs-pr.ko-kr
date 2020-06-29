---
title: 온-프레미스 배포 단일 포리스트(Surface Hub)
description: 이 항목에서는 단일 포리스트 온-프레미스 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: 단일 포리스트 배포, 온 프레미스 배포, 장치 계정, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836167"
---
# <span data-ttu-id="49116-104">단일 포리스트 환경에서 Surface Hub에 대한 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="49116-104">On-premises deployment for Surface Hub in a single-forest environment</span></span>


<span data-ttu-id="49116-105">이 항목에서는 단일 포리스트 온-프레미스 배포가 있는 경우 Microsoft Surface Hub에 대한 장치 계정을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a single-forest, on-premises deployment.</span></span>

<span data-ttu-id="49116-106">Microsoft Exchange 2013 이상과 비즈니스용 Skype 2013 이상이 포함된 단일 포리스트 온-프레미스 배포가 있는 경우 [제공된 PowerShell 스크립트를 사용](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)하여 장치 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-106">If you have a single-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="49116-107">다중 포리스트 배포를 사용하는 경우 [다중 포리스트 환경에서 Surface Hub에 대한 온-프레미스 배포](on-premises-deployment-surface-hub-multi-forest.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49116-107">If you’re using a multi-forest deployment, see [On-premises deployment for Surface Hub in a multi-forest environment](on-premises-deployment-surface-hub-multi-forest.md).</span></span>

1. <span data-ttu-id="49116-108">PC에서 원격 PowerShell 세션을 시작하고 Exchange에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

   <span data-ttu-id="49116-109">관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   <span data-ttu-id="49116-110">여기서 `$strExchangeServer`는 Exchange 서버의 FQDN(정규화된 도메인 이름)이고 `$strLyncFQDN`은 비즈니스용 Skype 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="49116-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. <span data-ttu-id="49116-111">세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 회의실 사서함의 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-111">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="49116-112">이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-112">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="49116-113">기존 리소스 사서함을 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="49116-113">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="49116-114">새 리소스 사서함을 만드는 경우</span><span class="sxs-lookup"><span data-stu-id="49116-114">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> <span data-ttu-id="49116-115">Surface Hub에서 다른 인증 방법을 사용 하 여 인증할 수 없기 때문에 ActiveSync 가상 디렉터리 기본 인증이 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-115">ActiveSync Virtual Directory Basic Authentication is required to be enabled as the Surface Hub is unable to authenticate using other authentication methods.</span></span>

3. <span data-ttu-id="49116-116">사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-116">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="49116-117">Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="49116-117">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="49116-118">제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-118">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="49116-119">호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-119">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="49116-120">정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-120">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   <span data-ttu-id="49116-121">호환되는 정책이 만들어지면 장치 계정에 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-121">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="49116-122">그러나 정책은 사용자 계정에만 적용할 수 있고 리소스 사서함에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-122">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="49116-123">사서함을 사용자 유형으로 변환하고 정책을 적용한 다음 사서함으로 다시 변환합니다. 다시 사용하도록 설정하고 암호도 다시 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-123">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. <span data-ttu-id="49116-124">장치 계정에서 다양한 Exchange 속성을 설정하여 사용자의 모임 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-124">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="49116-125">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-125">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="49116-126">암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="49116-127">자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49116-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. <span data-ttu-id="49116-128">Active Directory에서 계정을 사용하도록 설정하여 Surface Hub에 인증할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-128">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. <span data-ttu-id="49116-129">비즈니스용 Skype 서버 풀에서 Surface Hub AD 계정을 사용하도록 설정하여 비즈니스용 Skype와 함께 장치 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-129">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   <span data-ttu-id="49116-130">고유한 비즈니스용 Skype 서버 풀 식별자 및 사용자 ID와 함께 Surface Hub에 대한 SIP(Session Initiation Protocol) 주소 및 도메인 컨트롤러를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-130">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>

8. <span data-ttu-id="49116-131">옵션: 엔터프라이즈 음성을 계정에 사용하도록 설정하여 Surface Hub가 PSTN(공중 전화망) 전화 통화를 걸고 받을 수 있게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-131">OPTIONAL: You can also allow your Surface Hub to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="49116-132">엔터프라이즈 음성은 Surface Hub의 요구 사항이 아니지만 Surface Hub 클라이언트에 PSTN 전화 걸기 기능을 사용하려는 경우 사용하도록 설정하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="49116-132">Enterprise Voice isn't a requirement for Surface Hub, but if you want PSTN dialing functionality for the Surface Hub client, here's how to enable it:</span></span>

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   <span data-ttu-id="49116-133">이 경우에도 제공 된 도메인 컨트롤러 및 전화 번호 예제를 자신의 정보로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-133">Again, you need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="49116-134">매개 변수 값 `$true`는 동일하게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-134">The parameter value `$true` stays the same.</span></span>
    

 ## <span data-ttu-id="49116-135">익명 전자 메일 및 메신저 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="49116-135">Disable anonymous email and IM</span></span>




<span data-ttu-id="49116-136">Surface Hub는 장치 계정을 사용 하 여 전자 메일 및 공동 작업 서비스 (IM, 비디오, 음성)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-136">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="49116-137">이 디바이스 계정은 전자 메일, 메신저 대화, 통화를 보낼 때의 원래 id ("보낸 사람")로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49116-137">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="49116-138">이 계정은 개인 식별이 가능 사용자에 게는 제공 되지 않으므로 Surface Hub의 디바이스 계정에서 시작 되었기 때문에 "anonymous"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49116-138">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="49116-139">**SurfaceHubPolicy**의 id를 사용 하 여 각 회의실 디바이스에 사용자 단위 클라이언트 정책이 할당 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-139">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="49116-140">익명 전자 메일 및 메시지를 사용 하지 않도록 설정 하려면 다음 명령을 사용 하 여이 클라이언트 정책에 clientPolicyEntry를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-140">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="49116-141">정책이 설정 되었는지 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-141">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="49116-142">출력은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-142">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="49116-143">정책 항목을 변경 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-143">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="49116-144">정책 항목을 제거 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49116-144">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





