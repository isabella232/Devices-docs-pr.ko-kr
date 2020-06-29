---
title: Skype 하이브리드 음성 환경으로 온라인 또는 하이브리드 배포(Surface Hub)
description: 이 항목에서는 클라우드 커넥터 버전 또는 비즈니스용 Skype 2015 풀을 통한 온-프레미스 PSTN 연결을 사용하여 비즈니스용 Skype 클라우드 PBX를 활성화하는 방법에 대해 설명합니다.
keywords: 하이브리드 배포, Skype 하이브리드 음성
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836431"
---
# <span data-ttu-id="dd152-104">Skype 하이브리드 음성 환경으로 온라인 또는 하이브리드 배포(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="dd152-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="dd152-105">이 항목에서는 클라우드 커넥터 버전 또는 비즈니스용 Skype 2015 풀을 통한 온-프레미스 PSTN(공중 전화망) 연결을 사용하여 비즈니스용 Skype 클라우드 PBX를 활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="dd152-106">이 옵션에서는</span><span class="sxs-lookup"><span data-stu-id="dd152-106">In this option.</span></span> <span data-ttu-id="dd152-107">클라우드에 있는 비즈니스용 Skype 홈 풀과 Exchange 서버는 비즈니스용 Skype 2015 또는 클라우드 커넥터 버전을 실행하는 온-프레미스 풀을 통해 PSTN으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="dd152-108">[다른 클라우드 PBX 옵션](https://technet.microsoft.com/library/mt612869.aspx)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dd152-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="dd152-109">하이브리드 음성 옵션 중 하나를 사용하여 비즈니스용 Skype 클라우드 PBX를 배포한 경우 Surface Hub용 회의실 계정을 사용하도록 설정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="dd152-110">먼저 일반 사용자 계정을 만들고 모든 하이브리드 음성 옵션 및 전화 번호를 할당한 다음, 회의실 계정으로 계정 변환을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="dd152-111">이 순서대로 수행하지 않으면 하이브리드 전화 번호를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="dd152-112">하이브리드 음성을 구성하기 전에 계정을 만드는 경우 (Enable-CSMeetingRoom 명령을 실행하면) 필요한 하이브리드 음성 매개 변수를 구성할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="dd152-113">이전에 구성된 계정에 대한 하이브리드 음성 매개 변수를 구성하거나 전화 번호를 다시 구성하려면 E5 또는 E3 + 클라우드 PBX 추가 기능 라이선스를 삭제한 후 3단계부터 시작하여 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="dd152-114">Surface Hub용 새 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="dd152-115">이 예제에서는 <strong> surfacehub2@adatum.com </strong> 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="dd152-116">계정은 로컬 Active Directory에서 만들고 클라우드와 동기화 하거나 클라우드에서 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![새 개체 사용자](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="dd152-118">**암호 사용 기간 제한 없음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="dd152-119">Surface Hub 디바이스에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-119">This is important for a Surface Hub device.</span></span>

   ![암호 사용 기간 제한 없음](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="dd152-121">Office 365에서 **E5** 라이선스 또는 **E3 및 클라우드 PBX** 추가 기능을 회의실 사용자 계정에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="dd152-122">하이브리드 음성을 작동하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-122">This is required for Hybrid Voice to work.</span></span>

   ![제품 라이선스 추가](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="dd152-124">회의실 사용자 계정이 비즈니스용 Skype Online에 표시될 때까지 15분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="dd152-125">비즈니스용 Skype Online에서 회의실 사용자 계정을 만든 후 비즈니스용 Skype 원격 PowerShell에서 하이브리드 음성을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="dd152-126">Surface Hub에서 테스트 전화를 걸어 하이브리드 음성 통화 흐름을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="dd152-127">PC에서 원격 PowerShell 세션을 시작하고 다음 cmdlet을 실행하여 Exchange에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="dd152-128">세션을 설정한 후 회의실 사용자 계정을 **RoomMailboxAccount**로 사용하려면 다음 cmdlet을 실행하여 회의실 사용자 계정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="dd152-129">이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="dd152-130">사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="dd152-131">Surface Hub는 **PasswordEnabled** 속성이 **False**로 설정된 ActiveSync 정책이 있는 장치 계정하고만 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="dd152-132">제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="dd152-133">호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="dd152-134">정책을 만든 후 다른 장치 계정에 동일한 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="dd152-135">호환되는 정책이 만들어지면 장치 계정에 정책을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="dd152-136">그러나 정책은 사용자 계정에만 적용할 수 있고 리소스 사서함에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="dd152-137">다음 cmdlet을 실행하여 사서함을 사용자 유형으로 변환하고 정책을 적용한 다음 사서함으로 다시 변환해야 합니다. 계정을 다시 사용하도록 설정하고 암호도 다시 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="dd152-138">장치 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="dd152-139">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md)에서 설정할 수 있는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="dd152-140">다음 cmdlet은 Exchange 속성을 설정하는 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="dd152-141">비즈니스용 Skype Online에서 사서함을 모임 장치로 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="dd152-142">계정을 모임 장치로 사용할 수 있도록 하는 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="dd152-143">이 cmdlet을 실행하면 다음 이미지와 같이 사용자에게 회의실에 있는지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="dd152-144">**예**를 선택하는 경우 마이크와 스피커가 음소거됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="dd152-145">현재 하이브리드 음성을 포함한 회의실 계정이 완전히 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="dd152-146">Skype 온-프레미스를 사용하면 설명, 위치 등과 같은 온-프레미스에 대한 추가 특성 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="dd152-147">Skype 온라인에 회의실을 만드는 경우 이러한 매개 변수를 온라인 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="dd152-148">다음 이미지에서 디바이스에 표시되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd152-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)
