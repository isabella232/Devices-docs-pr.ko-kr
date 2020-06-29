---
title: Windows Autopilot 및 Surface 디바이스
ms.reviewer: ''
manager: laurawi
description: Surface 장치에 대 한 Windows Autopilot 배포 옵션에 대해 알아보세요.
keywords: autopilot, windows 10, surface, 배포
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834620"
---
# <span data-ttu-id="e5733-104">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="e5733-104">Windows Autopilot and Surface devices</span></span>

<span data-ttu-id="e5733-105">Windows Autopilot는 Windows 10의 클라우드 기반 배포 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-105">Windows Autopilot is a cloud-based deployment technology in Windows 10.</span></span> <span data-ttu-id="e5733-106">Windows Autopilot를 사용 하 여 상자를 바로 사용할 수 있는 0-터치식 프로세스에서 장치를 원격으로 배포 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-106">You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.</span></span>

<span data-ttu-id="e5733-107">Windows Autopilot에서 등록 된 디바이스는 *하드웨어 해시*라고 하는 고유한 장치 서명을 통해 처음 시작 될 때 인터넷을 통해 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-107">Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*.</span></span> <span data-ttu-id="e5733-108">Azure AD (azure Active Directory) 및 모바일 장치 관리와 같은 최신 관리 솔루션을 사용 하 여 자동으로 등록 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-108">They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.</span></span>

<span data-ttu-id="e5733-109">Windows Autopilot에 대해 사용 하도록 설정 된 Surface 파트너에서 구매할 때 Surface 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-109">You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot.</span></span> <span data-ttu-id="e5733-110">이러한 파트너는 사용자에 게 직접 새 장치를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-110">These partners can ship new devices directly to your users.</span></span> <span data-ttu-id="e5733-111">디바이스는 처음 켤 때 자동으로 등록 되 고 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-111">The devices will be automatically enrolled and configured when they are first turned on.</span></span> <span data-ttu-id="e5733-112">이 프로세스는 배포 중에 reimaging를 제거 하 여 장치 관리 및 배포의 새로운 agile 메서드를 구현할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-112">This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.</span></span>

## <span data-ttu-id="e5733-113">최신 관리</span><span class="sxs-lookup"><span data-stu-id="e5733-113">Modern management</span></span>

<span data-ttu-id="e5733-114">Autopilot는 Autopilot를 통해 배포용으로 설계 된 surface Pro 7, Surface 랩톱 3 및 surface Pro X를 포함 하 여 Surface 디바이스에 권장 되는 배포 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-114">Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7, Surface Laptop 3, and Surface Pro X, which is specifically designed for deployment through Autopilot.</span></span>

 <span data-ttu-id="e5733-115">Microsoft 클라우드 솔루션 공급자의 도움말을 사용 하 여 Surface 디바이스를 등록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-115">It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider.</span></span> <span data-ttu-id="e5733-116">이 단계에서는 Intune에서 직접 UEFI 펌웨어 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-116">This step allows you to manage UEFI firmware settings on Surface directly from Intune.</span></span> <span data-ttu-id="e5733-117">이를 통해 인증서 관리를 위해 디바이스를 물리적으로 터치 해야 할 필요가 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-117">It eliminates the need to physically touch devices for certificate management.</span></span> <span data-ttu-id="e5733-118">자세한 내용은 [SURFACE UEFI 설정의 Intune management을](surface-manage-dfci-guide.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5733-118">See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.</span></span>

## <span data-ttu-id="e5733-119">Windows 버전 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e5733-119">Windows version considerations</span></span>

<span data-ttu-id="e5733-120">구매할 때 Surface 파트너의 등록을 포함 하 여 Windows Autopilot를 통해 Surface 디바이스를 광범위 하 게 배포 하는 경우 Windows 10 버전 1709 (낙하 생성기 업데이트) 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-120">Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.</span></span>

<span data-ttu-id="e5733-121">이러한 Windows 버전에서는 확장 시 배포에 필요한 Windows Autopilot 장치를 고유 하 게 식별 하는 4000 바이트 (4k) 해시 값을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-121">These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale.</span></span> <span data-ttu-id="e5733-122">Surface Pro 7, Surface Pro X, Surface 노트북 3을 비롯 한 모든 새 Surface 장치는 Windows 10 버전 1903 이상에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-122">All new Surface devices, including Surface Pro 7, Surface Pro X, and Surface Laptop 3, ship with Windows 10 Version 1903 or later.</span></span>

## <span data-ttu-id="e5733-123">복구 또는 교체 필요에 따라 Surface 디바이스의 Exchange 환경</span><span class="sxs-lookup"><span data-stu-id="e5733-123">Exchange experience on Surface devices in need of repair or replacement</span></span>

<span data-ttu-id="e5733-124">Microsoft는 Autopilot 등록을 위해 모든 화면을 자동으로 확인 하 고 고객의 테 넌 트에서 장치를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-124">Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.</span></span>  <span data-ttu-id="e5733-125">Microsoft는 대체 장치가 고객에 게 다시 배송 되 면 대체 장치를 Windows Autopilot에 등록할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-125">Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer.</span></span> <span data-ttu-id="e5733-126">이 서비스는 모든 장치 교환 서비스에서 Microsoft와 직접 주문할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-126">This service is available on all device exchange service orders directly with Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e5733-127">고객이 파트너를 사용 하 여 디바이스를 반환 하는 경우 파트너는 deregistering 및 Windows Autopilot에 등록 하는 장치를 포함 하 여 exchange 프로세스를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-127">When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.</span></span>

## <span data-ttu-id="e5733-128">Windows Autopilot에 대해 사용 하도록 설정 된 Surface 파트너</span><span class="sxs-lookup"><span data-stu-id="e5733-128">Surface partners enabled for Windows Autopilot</span></span>

<span data-ttu-id="e5733-129">Surface 파트너 선택은 Windows Autopilot에서 구매할 때 사용자에 게 Surface 디바이스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-129">Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase.</span></span> <span data-ttu-id="e5733-130">또한 등록 된 디바이스를 사용자에 게 직접 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-130">They can also ship enrolled devices directly to your users.</span></span> <span data-ttu-id="e5733-131">장치는 Windows Autopilot, Azure AD 및 모바일 장치 관리를 사용 하 여 0 터치 프로세스를 통해 완전히 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-131">The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.</span></span>

<span data-ttu-id="e5733-132">Windows Autopilot으로 설정 되는 Surface 파트너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5733-132">Surface partners that are enabled for Windows Autopilot include:</span></span>

| <span data-ttu-id="e5733-133">미국 파트너</span><span class="sxs-lookup"><span data-stu-id="e5733-133">US partners</span></span> | <span data-ttu-id="e5733-134">글로벌 파트너</span><span class="sxs-lookup"><span data-stu-id="e5733-134">Global partners</span></span> | <span data-ttu-id="e5733-135">미국 대리점</span><span class="sxs-lookup"><span data-stu-id="e5733-135">US distributors</span></span> |
|--------------|---------------|-------------------|
| <span data-ttu-id="e5733-136">\* [CDW](https://www.cdw.com/)</span><span class="sxs-lookup"><span data-stu-id="e5733-136">\* [CDW](https://www.cdw.com/)</span></span> | <span data-ttu-id="e5733-137">\* [수도](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="e5733-137">\* [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span></span> | <span data-ttu-id="e5733-138">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span><span class="sxs-lookup"><span data-stu-id="e5733-138">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span></span>  |
| <span data-ttu-id="e5733-139">\* [연결](https://www.connection.com/brand/microsoft/microsoft-surface)</span><span class="sxs-lookup"><span data-stu-id="e5733-139">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span></span>   | <span data-ttu-id="e5733-140">\* [ATEA](https://www.atea.com/)</span><span class="sxs-lookup"><span data-stu-id="e5733-140">\* [ATEA](https://www.atea.com/)</span></span> | <span data-ttu-id="e5733-141">\* [Techdata](https://www.techdata.com/)</span><span class="sxs-lookup"><span data-stu-id="e5733-141">\* [Techdata](https://www.techdata.com/)</span></span>  |
| <span data-ttu-id="e5733-142">\* [정보](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span><span class="sxs-lookup"><span data-stu-id="e5733-142">\* [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span></span>  | <span data-ttu-id="e5733-143">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="e5733-143">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span></span> | <span data-ttu-id="e5733-144">\* [이 진 영문법](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span><span class="sxs-lookup"><span data-stu-id="e5733-144">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span></span>   |
| <span data-ttu-id="e5733-145">\* [SHI](https://www.shi.com/Surface)</span><span class="sxs-lookup"><span data-stu-id="e5733-145">\* [SHI](https://www.shi.com/Surface)</span></span> | <span data-ttu-id="e5733-146">\* [Cancom](https://www.cancom.de/)</span><span class="sxs-lookup"><span data-stu-id="e5733-146">\* [Cancom](https://www.cancom.de/)</span></span> |    |
| <span data-ttu-id="e5733-147">\* [LDI Connect](https://www.myldi.com/managed-it/)</span><span class="sxs-lookup"><span data-stu-id="e5733-147">\* [LDI Connect](https://www.myldi.com/managed-it/)</span></span>  | <span data-ttu-id="e5733-148">\* [고 대 인 acenter](https://www.computacenter.com/uk)</span><span class="sxs-lookup"><span data-stu-id="e5733-148">\* [Computacenter](https://www.computacenter.com/uk)</span></span> |    |
| <span data-ttu-id="e5733-149">\* [보려면](https://www.functiononeit.com/#empower)</span><span class="sxs-lookup"><span data-stu-id="e5733-149">\* [F1](https://www.functiononeit.com/#empower)</span></span>  |   |  |
| <span data-ttu-id="e5733-150">\* [보호 된 신뢰](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span><span class="sxs-lookup"><span data-stu-id="e5733-150">\* [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span></span> | | | 

## <span data-ttu-id="e5733-151">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="e5733-151">Learn more</span></span>

<span data-ttu-id="e5733-152">Windows Autopilot에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5733-152">For more information about Windows Autopilot, see:</span></span>
- [<span data-ttu-id="e5733-153">Windows Autopilot 개요</span><span class="sxs-lookup"><span data-stu-id="e5733-153">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [<span data-ttu-id="e5733-154">Windows Autopilot 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5733-154">Windows Autopilot requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)