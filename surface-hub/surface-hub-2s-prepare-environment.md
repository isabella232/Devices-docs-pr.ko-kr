---
title: Surface Hub 2S에 대한 환경 준비
description: Surface Hub 2S에 대한 환경을 준비하기 위해 필요한 작업을 알아보십시오.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385146"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a><span data-ttu-id="42225-104">Surface Hub 2S에 대한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="42225-104">Prepare your environment for Surface Hub 2S</span></span>

## <a name="office-365-readiness"></a><span data-ttu-id="42225-105">Office 365 준비</span><span class="sxs-lookup"><span data-stu-id="42225-105">Office 365 readiness</span></span>

<span data-ttu-id="42225-106">Exchange Online, 비즈니스용 Skype Online, Microsoft Teams 또는 Microsoft Whiteboard를 사용하고 Intune에서 Surface Hub 2S를 관리하려는 경우 먼저 끝점에 대한 [Office 365](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)요구 사항을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="42225-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="42225-107">Office 365 끝점은 방화벽을 통해 모든 신뢰할 수 있는 Office 365 네트워크 요청을 직접 전송하고 모든 추가 패킷 수준 검사 또는 처리를 무시하여 네트워크를 최적화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42225-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="42225-108">이 기능은 대기 시간 및 경계 용량 요구 사항을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="42225-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="42225-109">Microsoft는 필요한 포트, URL 및 IP 주소를 변경할 수 있는 새로운 기능으로 Office 365 서비스를 정기적으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="42225-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="42225-110">변경 내용을 평가, 구성 및 최신으로 유지 관리하기 위해 [Office 365 IP](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)주소 및 URL 웹 서비스를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="42225-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

> [!NOTE]
> <span data-ttu-id="42225-111">Surface Hub는 Microsoft Teams, 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype Online에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="42225-111">Surface Hub works with Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015, or Skype for Business Online.</span></span>
<span data-ttu-id="42225-112">Lync Server 2013과 같은 이전 플랫폼은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-112">Earlier platforms, such as Lync Server 2013, are not supported.</span></span> <span data-ttu-id="42225-113">Surface Hub는 GCC-High DoD 환경에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-113">Surface Hub is not supported in GCC-High or DoD environments.</span></span>


## <a name="device-affiliation"></a><span data-ttu-id="42225-114">장치 소속</span><span class="sxs-lookup"><span data-stu-id="42225-114">Device affiliation</span></span>

<span data-ttu-id="42225-115">장치 정보를 사용하여 Surface Hub 2S의 설정 앱에 대한 사용자 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="42225-115">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="42225-116">Windows 10 Team 운영 체제(Surface Hub 2S에서 실행)를 사용하는 경우 권한이 부여된 사용자만 설정 앱을 사용하여 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-116">With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="42225-117">소속을 선택하면 기능 가용성에 영향을 줄 수 있는 것이기 때문에 사용자가 의도한 경우 기능에 액세스할 수 있도록 적절하게 계획하십시오.</span><span class="sxs-lookup"><span data-stu-id="42225-117">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="42225-118">초기 OOBE(첫 실행 경험) 설정 중에만 장치 소속을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-118">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="42225-119">장치 정보 설정을 다시 설정해야 하는 경우 OOBE 설정을 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42225-119">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <a name="no-affiliation"></a><span data-ttu-id="42225-120">소속 없음</span><span class="sxs-lookup"><span data-stu-id="42225-120">No affiliation</span></span>

<span data-ttu-id="42225-121">Surface Hub 2S가 각 Surface Hub 2S에서 다른 로컬 관리자 계정으로 작업 계정에 있는 경우와 같은 소속이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-121">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="42225-122">아니요를 선택하면 BitLocker 키를 USB 썸 드라이브에 로컬로 [저장해야 합니다.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)</span><span class="sxs-lookup"><span data-stu-id="42225-122">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="42225-123">Intune을 사용하여 디바이스를 등록할 수 있습니다. 그러나 로컬 관리자만 OOBE 중에 구성된 계정 자격 증명을 사용하여 설정 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-123">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="42225-124">설정 앱에서 관리자 계정 암호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-124">You can change the Administrator account password from the Settings app.</span></span>

## <a name="active-directory-domain-services"></a><span data-ttu-id="42225-125">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="42225-125">Active Directory Domain Services</span></span>

<span data-ttu-id="42225-126">Surface Hub 2S와 사내 Active Directory 도메인 서비스를 함께 사용하는 경우 도메인의 보안 그룹을 사용하여 설정 앱에 대한 액세스를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42225-126">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="42225-127">이렇게 하면 모든 보안 그룹 구성원이 Surface Hub 2S에서 설정을 변경할 수 있는 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="42225-127">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="42225-128">또한 다음 사항도 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="42225-128">Also note the following:</span></span>

- <span data-ttu-id="42225-129">Surface Hub 2S 계열사와 프레미스 Active Directory 도메인 서비스를 함께 사용할 경우 BitLocker 키를 Active Directory Schema에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-129">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="42225-130">자세한 내용은 [조직에서 BitLocker 준비: 계획 및 정책 을 참조하세요.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)</span><span class="sxs-lookup"><span data-stu-id="42225-130">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span>

- <span data-ttu-id="42225-131">조직의 신뢰할 수 있는 루트 CAS가 Surface Hub 2S의 동일한 컨테이너로 푸시됩니다. 즉, 프로비저닝 패키지를 사용하여 가져올 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-131">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>

- <span data-ttu-id="42225-132">Surface Hub 2S에서 설정을 중앙에서 관리하기 위해 Intune으로 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-132">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <a name="azure-active-directory"></a><span data-ttu-id="42225-133">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="42225-133">Azure Active Directory</span></span>

<span data-ttu-id="42225-134">Surface Hub 2S를 Azure AD(Azure Active Directory)와 연결하도록 선택하면 전역 관리자 보안 그룹의 모든 사용자가 Surface Hub 2S의 설정 앱에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-134">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="42225-135">Surface Hub 2S에서 설정 앱 관리 권한을 제한하는 전역이 아닌 관리자 계정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-135">You can also configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="42225-136">이렇게 하면 Surface Hub 2S에 대한 관리자 권한의 범위만 지정하고 전체 Azure AD 도메인에서 잠재적으로 원치 않는 관리자 액세스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42225-136">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> 

<span data-ttu-id="42225-137">조직에서 Intune 자동 등록을 사용하도록 설정하면 Surface Hub 2S가 자동으로 Intune에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="42225-137">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="42225-138">장치의 BitLocker 키는 Azure AD에 자동으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="42225-138">The device’s BitLocker key is automatically saved in Azure AD.</span></span> 

<span data-ttu-id="42225-139">Azure AD를 사용하여 Surface Hub를 관리하는 데 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42225-139">To learn more about managing Surface Hub with Azure AD, see:</span></span> 

 - [<span data-ttu-id="42225-140">관리자 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="42225-140">Admin group management</span></span>](admin-group-management-for-surface-hub.md)
 - [<span data-ttu-id="42225-141">Surface Hub 2S에서 비전역 관리자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="42225-141">Configure non Global admin accounts on Surface Hub 2S</span></span>](surface-hub-2s-nonglobal-admin.md)

