---
title: 디바이스 계정 만들기 및 테스트(Surface Hub)
description: 이 항목에서는 Microsoft Surface Hub가 Microsoft Exchange 및 Skype와 통신하는 데 사용하는 디바이스 계정을 만들고 테스트하는 방법을 소개합니다.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 디바이스 계정 만들기 및 테스트, 디바이스 계정, Surface Hub 및 Microsoft Exchange, Surface Hub 및 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836340"
---
# <span data-ttu-id="8b015-104">디바이스 계정 만들기 및 테스트(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="8b015-104">Create and test a device account (Surface Hub)</span></span>


<span data-ttu-id="8b015-105">이 항목에서는 Microsoft Surface Hub가 Microsoft Exchange 및 Skype와 통신하는 데 사용하는 디바이스 계정을 만들고 테스트하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-105">This topic introduces how to create and test the device account that Microsoft Surface Hub uses to communicate with Microsoft Exchange and Skype.</span></span>

<span data-ttu-id="8b015-106">**디바이스 계정**은 Surface Hub가 다음 작업에 사용하는 Exchange 리소스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-106">A **device account** is an Exchange resource account that Surface Hub uses to:</span></span>

-   <span data-ttu-id="8b015-107">모임 일정 표시</span><span class="sxs-lookup"><span data-stu-id="8b015-107">Display its meeting calendar</span></span>
-   <span data-ttu-id="8b015-108">팀 참가 또는 비즈니스용 Skype 통화</span><span class="sxs-lookup"><span data-stu-id="8b015-108">Join Teams or Skype for Business calls</span></span>
-   <span data-ttu-id="8b015-109">메일 보내기(예: 모임의 화이트보드 콘텐츠에 대한 메일 보내기)</span><span class="sxs-lookup"><span data-stu-id="8b015-109">Send email (for example, email whiteboard content from a meeting)</span></span>

<span data-ttu-id="8b015-110">디바이스 계정이 Surface Hub로 프로비전되면 사용자는 회의실에 초대하는 것과 같은 방식으로 이 계정을 모임 초대에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-110">Once the device account is provisioned to a Surface Hub, people can add this account to a meeting invitation the same way that they would invite a meeting room.</span></span> 

## <span data-ttu-id="8b015-111">구성 개요</span><span class="sxs-lookup"><span data-stu-id="8b015-111">Configuration overview</span></span>

<span data-ttu-id="8b015-112">이 표에서는 디바이스 계정을 만들 때 필요한 주요 단계와 구성 결정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-112">This table explains the main steps and configuration decisions when you create a device account.</span></span> 
 
| <span data-ttu-id="8b015-113">단계</span><span class="sxs-lookup"><span data-stu-id="8b015-113">Step</span></span> | <span data-ttu-id="8b015-114">설명</span><span class="sxs-lookup"><span data-stu-id="8b015-114">Description</span></span>                     |  <span data-ttu-id="8b015-115">목적</span><span class="sxs-lookup"><span data-stu-id="8b015-115">Purpose</span></span>                             |
|------|---------------------------------|--------------------------------------|
| <span data-ttu-id="8b015-116">raid-1</span><span class="sxs-lookup"><span data-stu-id="8b015-116">1</span></span>    | <span data-ttu-id="8b015-117">로그온 가능 Exchange 리소스 사서함을 만들었음(Exchange 2013 이상 또는 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="8b015-117">Created a logon-enabled Exchange resource mailbox (Exchange 2013 or later, or Exchange Online)</span></span> | <span data-ttu-id="8b015-118">이 리소스 사서함을 통해 디바이스에서는 모임 일정을 유지 관리하고 모임 요청을 받고 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-118">This resource mailbox allows the device to maintain a meeting calendar, receive meeting requests, and send mail.</span></span> <span data-ttu-id="8b015-119">Surface Hub로 프로비전되려면 로그온 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-119">It must be logon-enabled to be provisioned to a Surface Hub.</span></span> |
| <span data-ttu-id="8b015-120">2</span><span class="sxs-lookup"><span data-stu-id="8b015-120">2</span></span>    | <span data-ttu-id="8b015-121">사서함 속성 구성</span><span class="sxs-lookup"><span data-stu-id="8b015-121">Configure mailbox properties</span></span> | <span data-ttu-id="8b015-122">Surface Hub에서 최상의 모임 환경을 실현하려면 정확한 속성을 사용하여 사서함을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-122">The mailbox must be configured with the correct properties to enable the best meeting experience on Surface Hub.</span></span> <span data-ttu-id="8b015-123">사서함 속성에 대한 자세한 내용은 [Microsoft Exchange 속성(Surface Hub)](exchange-properties-for-surface-hub-device-accounts.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b015-123">For more information on mailbox properties, see [Mailbox properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> |
| <span data-ttu-id="8b015-124">3-4</span><span class="sxs-lookup"><span data-stu-id="8b015-124">3</span></span>    | <span data-ttu-id="8b015-125">사서함에 호환 가능한 모바일 디바이스 사서함 정책 적용</span><span class="sxs-lookup"><span data-stu-id="8b015-125">Apply a compatible mobile device mailbox policy to the mailbox</span></span> | <span data-ttu-id="8b015-126">Surface Hub는 모바일 디바이스 사서함 정책이 아닌 MDM(모바일 디바이스 관리)을 사용하여 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-126">Surface Hub is managed using mobile device management (MDM) rather than through mobile device mailbox policies.</span></span> <span data-ttu-id="8b015-127">호환성을 위해 디바이스 계정에는 **PasswordEnabled** 설정이 False로 설정된 모바일 디바이스 사서함 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-127">For compatibility, the device account must have a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="8b015-128">그렇지 않으면 Surface Hub가 메일과 일정을 동기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-128">Otherwise, Surface Hub can't sync mail and calendar info.</span></span> |
| <span data-ttu-id="8b015-129">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="8b015-129">4</span></span>    | <span data-ttu-id="8b015-130">비즈니스용 Skype(Lync Server 2013 이상 또는 비즈니스용 Skype Online)에서 사서함 사용</span><span class="sxs-lookup"><span data-stu-id="8b015-130">Enable mailbox with Skype for Business (Lync Server 2013 or later, or Skype for Business Online)</span></span> | <span data-ttu-id="8b015-131">영상 통화, IM, 화면 공유 등의 회의 기능을 사용하려면 비즈니스용 Skype를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-131">Skype for Business must be enabled to use conferencing features like video calls, IM, and screen sharing.</span></span>  |
| <span data-ttu-id="8b015-132">5mb</span><span class="sxs-lookup"><span data-stu-id="8b015-132">5</span></span>    | <span data-ttu-id="8b015-133">(선택 사항) 허용 목록 ActiveSync 디바이스 ID</span><span class="sxs-lookup"><span data-stu-id="8b015-133">(Optional) Whitelist ActiveSync Device ID</span></span> | <span data-ttu-id="8b015-134">디바이스 계정이 메일과 일정 정보를 동기화하지 못하게 하는 전역 정책이 조직에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-134">Your organization may have a global policy that prevents device accounts from syncing mail and calendar info.</span></span> <span data-ttu-id="8b015-135">그렇다면 Surface Hub의 ActiveSync 장치 ID를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-135">If so, you need to allow the ActiveSync Device ID of your Surface Hub.</span></span> |
| <span data-ttu-id="8b015-136">26</span><span class="sxs-lookup"><span data-stu-id="8b015-136">6</span></span>    | <span data-ttu-id="8b015-137">(선택 사항) 암호 만료 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8b015-137">(Optional) Disable password expiration</span></span> | <span data-ttu-id="8b015-138">관리를 간소화하기 위해 디바이스 계정에 대한 암호 만료를 끄고 Surface Hub가 디바이스 계정의 암호를 자동으로 순환하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-138">To simplify management, you can turn off password expiration for the device account and allow Surface Hub to automatically rotate the device account password.</span></span> <span data-ttu-id="8b015-139">암호 관리에 대한 자세한 내용은 [암호 관리(Surface Hub)](password-management-for-surface-hub-device-accounts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b015-139">For more information about password management, see [Password management](password-management-for-surface-hub-device-accounts.md).</span></span>  |

## <span data-ttu-id="8b015-140">세부 구성 단계</span><span class="sxs-lookup"><span data-stu-id="8b015-140">Detailed configuration steps</span></span> 

<span data-ttu-id="8b015-141">원격 PowerShell을 사용하여 디바이스 계정을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-141">We recommend setting up your device accounts using remote PowerShell.</span></span> <span data-ttu-id="8b015-142">디바이스 계정을 만들고 유효성을 검사하는 데 도움이 될 수 있는 PowerShell 스크립트가 있습니다. PowerShell 스크립트 및 지침에 대한 자세한 내용은 [부록 A: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b015-142">There are PowerShell scripts available to help create and validate device accounts For more information on PowerShell scripts and instructions, see [Appendix A: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md).</span></span> 

<span data-ttu-id="8b015-143">PowerShell을 사용하여 디바이스 계정을 프로비전하는 자세한 단계의 경우 조직 배포에 따라 표에서 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-143">For detailed steps using PowerShell to provision a device account, choose an option from the table, based on your organization deployment.</span></span> 

| <span data-ttu-id="8b015-144">조직 배포</span><span class="sxs-lookup"><span data-stu-id="8b015-144">Organization deployment</span></span>             |  <span data-ttu-id="8b015-145">설명</span><span class="sxs-lookup"><span data-stu-id="8b015-145">Description</span></span>                  |
|---------------------------------|--------------------------------------|
| [<span data-ttu-id="8b015-146">온라인 배포(Office 365)</span><span class="sxs-lookup"><span data-stu-id="8b015-146">Online deployment (Office 365)</span></span>](online-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="8b015-147">조직의 환경 전체가 Office 365에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-147">Your organization's environment is deployed entirely on Office 365.</span></span> |
| [<span data-ttu-id="8b015-148">온-프레미스 배포(단일 포리스트)</span><span class="sxs-lookup"><span data-stu-id="8b015-148">On-premises deployment (single-forest)</span></span>](on-premises-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="8b015-149">조직이 제어하고 단일 포리스트 환경에서 Active Directory, Exchange 및 비즈니스용 Skype(또는 Lync)를 호스트하는 데 사용하는 서버가 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-149">Your organization has servers that it controls and uses to host Active Directory, Exchange, and Skype for Business (or Lync) in a single-forest environment.</span></span> |
| [<span data-ttu-id="8b015-150">온-프레미스 배포(다중 포리스트)</span><span class="sxs-lookup"><span data-stu-id="8b015-150">On-premises deployment (multiple forests)</span></span>](on-premises-deployment-surface-hub-multi-forest.md) | <span data-ttu-id="8b015-151">조직이 제어하고 다중 포리스트 환경에서 Active Directory, Exchange 및 비즈니스용 Skype(또는 Lync)를 호스트하는 데 사용하는 서버가 조직에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-151">Your organization has servers that it controls and uses to host Active Directory, Exchange, and Skype for Business (or Lync) in a multi-forest environment.</span></span> |
| [<span data-ttu-id="8b015-152">하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="8b015-152">Hybrid deployment</span></span>](hybrid-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="8b015-153">온-프레미스에 호스트된 서비스와 Office 365를 통해 온라인에 호스트된 서비스가 혼합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-153">Your organization has a mix of services, with some hosted on-premises and some hosted online through Office 365.</span></span> |
| [<span data-ttu-id="8b015-154">Skype 하이브리드 음성 환경으로 온라인 또는 하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="8b015-154">Online or hybrid deployment using Skype Hybrid Voice environment</span></span>](skype-hybrid-voice.md) | <span data-ttu-id="8b015-155">조직에는 클라우드의 비즈니스용 Skype 홈 풀과 Exchange 서버가 있고, 비즈니스용 Skype 2015 또는 PSTN(공중 전화망)을 통해 연결된 클라우드 커넥터 버전의 온-프레미스 풀을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-155">Your organization has Skype for Business home pools and Exchange servers in the cloud, and uses an on-premises pool of Skype for Business 2015 or Cloud Connector edition connected via Public Switched Telephone Network (PSTN).</span></span> |


<span data-ttu-id="8b015-156">그래픽 UI(사용자 인터페이스)를 사용하려면 PowerShell 대신 UI를 사용하여 일부 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-156">If you prefer to use a graphical user interface (UI), some steps can be done using UI instead of PowerShell.</span></span> <span data-ttu-id="8b015-157">자세한 내용은 [UI(Surface Hub)를 사용하여 디바이스 계정 만들기](create-a-device-account-using-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b015-157">For more information, see [Creating a device account using UI](create-a-device-account-using-office-365.md).</span></span>

## <span data-ttu-id="8b015-158">계정 확인 및 테스트</span><span class="sxs-lookup"><span data-stu-id="8b015-158">Account verification and testing</span></span>

<span data-ttu-id="8b015-159">Surface Hub 장치 계정을 확인 및 테스트하기 위해 사용할 수 있는 방법은 [계정 확인 스크립트](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)와 [Surface Hub 하드웨어 진단 앱](https://www.microsoft.com/store/apps/9nblggh51f2g) 등 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-159">There are two methods available that you can use to validate and test a Surface Hub device account: [account verifications scripts](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) and the [Surface Hub Hardware Diagnostic app](https://www.microsoft.com/store/apps/9nblggh51f2g).</span></span> <span data-ttu-id="8b015-160">계정을 확인 스크립트는 바탕 화면에서 PowerShell를 사용하여 이전에 생성된 장치 계정의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-160">The account verification script will validate a previously-created device account using PowerShell from your desktop.</span></span> <span data-ttu-id="8b015-161">Surface Hub 하드웨어 진단 앱은 Surface Hub에 설치되어 로그인 및 통신 오류에 대한 자세한 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-161">The Surface Hub Hardware Diagnostic app is installed on your Surface Hub and provides detailed feedback about signin and communication failures.</span></span> <span data-ttu-id="8b015-162">두 방법 모두 새로 생성된 장치 계정을 테스트할 수 있는 유용한 도구이며 최적의 계정 가용성을 보장하는 데 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b015-162">Both are valuable tools to test newly created device accounts and should be used to ensure optimal account availability.</span></span>

 

 

 





