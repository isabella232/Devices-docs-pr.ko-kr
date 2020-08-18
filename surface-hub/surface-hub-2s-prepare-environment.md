---
title: Surface Hub 2S에 대한 환경 준비
description: Surface Hub 2S 환경을 준비 하기 위해 수행 해야 하는 작업에 대해 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: dddab2adce1bec9ff722a3324b9c4b1be609ae89
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934848"
---
# <span data-ttu-id="a4cd1-104">Surface Hub 2S에 대한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="a4cd1-104">Prepare your environment for Surface Hub 2S</span></span>

## <span data-ttu-id="a4cd1-105">Office 365 준비</span><span class="sxs-lookup"><span data-stu-id="a4cd1-105">Office 365 readiness</span></span>

<span data-ttu-id="a4cd1-106">Exchange Online, 비즈니스용 Skype Online, Microsoft 팀 또는 Microsoft 화이트 보드를 사용 하 고 Intune을 사용 하 여 Surface Hub 2S를 관리 하려는 경우 먼저 [끝점에 대 한 Office 365 요구 사항을](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="a4cd1-107">Office 365 끝점은 모든 추가 패킷 수준 검사 또는 처리를 우회 하 여 모든 신뢰할 수 있는 Office 365 네트워크 요청을 방화벽을 통해 직접 보내는 방법으로 네트워크를 최적화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="a4cd1-108">이 기능은 대기 시간과 해당 경계 용량 요구 사항을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="a4cd1-109">Microsoft는 필요한 포트, Url, IP 주소를 변경할 수 있는 새로운 기능과 기능을 사용 하 여 Office 365 서비스를 정기적으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="a4cd1-110">변경 사항을 평가, 구성, 최신 상태로 유지 하려면 [Office 365 IP 주소 및 URL 웹 서비스](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)에 가입 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

## <span data-ttu-id="a4cd1-111">디바이스 소속</span><span class="sxs-lookup"><span data-stu-id="a4cd1-111">Device affiliation</span></span>

<span data-ttu-id="a4cd1-112">디바이스 소속을 사용 하 여 Surface Hub 2S의 설정 앱에 대 한 사용자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-112">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="a4cd1-113">Surface Hub 2S에서 실행 되는 Windows 10 Team 운영 체제를 사용 하 여 권한 있는 사용자만 설정 앱을 사용 하 여 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-113">With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="a4cd1-114">소속을 선택 하면 기능 가용성에 영향을 줄 수 있으므로, 사용자가 의도 한 대로 기능에 액세스할 수 있도록 적절 하 게 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-114">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="a4cd1-115">초기 OOBE (첫 실행 경험) 설정 중에만 디바이스 소속을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-115">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="a4cd1-116">디바이스 소속을 다시 설정 해야 하는 경우 OOBE 설치 프로그램을 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-116">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <span data-ttu-id="a4cd1-117">소속 없음</span><span class="sxs-lookup"><span data-stu-id="a4cd1-117">No affiliation</span></span>

<span data-ttu-id="a4cd1-118">각 Surface Hub 2S에서 다른 로컬 관리자 계정을 사용 하 여 작업 그룹에서 Surface Hub 2S 하는 것과는 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-118">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="a4cd1-119">회원 가입을 선택 하지 않은 경우에는 [BitLocker 키를 USB 엄지 드라이브에](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)로컬로 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-119">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="a4cd1-120">Intune을 사용 하 여 디바이스를 등록할 수 있습니다. 그러나 로컬 관리자만 OOBE 중에 구성 된 계정 자격 증명을 사용 하 여 설정 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-120">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="a4cd1-121">설정 앱에서 관리자 계정 암호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-121">You can change the Administrator account password from the Settings app.</span></span>

## <span data-ttu-id="a4cd1-122">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="a4cd1-122">Active Directory Domain Services</span></span>

<span data-ttu-id="a4cd1-123">온-프레미스 Active Directory 도메인 서비스를 사용 하 여 Surface Hub 2S을 구입한 경우에는 도메인의 보안 그룹을 사용 하 여 설정 앱에 대 한 액세스 권한을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-123">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="a4cd1-124">이렇게 하면 모든 보안 그룹 구성원에 게 Surface Hub 2S 설정을 변경할 수 있는 권한이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-124">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="a4cd1-125">또한 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-125">Also note the following:</span></span>

- <span data-ttu-id="a4cd1-126">온-프레미스 Active Directory 도메인 서비스를 사용 하는 Surface Hub 2S의 경우 BitLocker 키를 Active Directory 스키마에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-126">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="a4cd1-127">자세한 내용은 [BitLocker에 맞게 조직 준비: 계획 및 정책을](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-127">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span> 
- <span data-ttu-id="a4cd1-128">조직의 신뢰할 수 있는 루트 Ca가 Surface Hub 2S의 동일한 컨테이너에 푸시되는 데,이는 프로비저닝 패키지를 사용 하 여 가져올 필요가 없다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-128">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>
- <span data-ttu-id="a4cd1-129">계속 해 서 Intune을 사용 하 여 디바이스를 등록 하 여 Surface Hub 2S의 설정을 중앙에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-129">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <span data-ttu-id="a4cd1-130">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a4cd1-130">Azure Active Directory</span></span>

<span data-ttu-id="a4cd1-131">Azure Active Directory (Azure AD)를 사용 하 여 Surface Hub 2S을 계열사로 선택한 경우 전역 관리자 보안 그룹의 모든 사용자가 Surface Hub 2S에서 설정 앱에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-131">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="a4cd1-132">현재는 Surface Hub 2S의 설정 앱에 로그인 하기 위해 다른 그룹을 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-132">Currently, no other group can be delegated to sign in to the Settings app on Surface Hub 2S.</span></span>

<span data-ttu-id="a4cd1-133">조직에 Intune 자동 등록을 사용 하도록 설정한 경우 Surface Hub 2S는 Intune을 사용 하 여 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-133">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="a4cd1-134">디바이스의 BitLocker 키는 Azure AD에 자동으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-134">The device’s BitLocker key is automatically saved in Azure AD.</span></span> <span data-ttu-id="a4cd1-135">Affiliating Surface Hub를 Azure AD와 함께 사용 하는 경우 single sign-on 및 간단한 인증이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4cd1-135">When affiliating Surface Hub 2S with Azure AD, single sign-on and Easy Authentication will not work.</span></span>
