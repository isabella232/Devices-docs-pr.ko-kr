---
title: Surface Dock 2를 통해 LAN 절전 모드 해제
description: Surface Dock 2는 관리자가 원격으로 디바이스를 절전 모드로 해제하고 관리 작업을 자동으로 수행할 수 있도록 WOL(Wake on LAN)을 가장 잘 지원합니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 6/03/2021
ms.openlocfilehash: 74b36b60cb58ecb9042b73b8cdba7271d0af8c80
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614121"
---
# <a name="wake-on-lan-with-surface-dock-2"></a><span data-ttu-id="336ac-104">Surface Dock 2를 통해 LAN 절전 모드 해제</span><span class="sxs-lookup"><span data-stu-id="336ac-104">Wake On LAN with Surface Dock 2</span></span>

<span data-ttu-id="336ac-105">장치를 최신으로 유지하려면 IT 관리자가 사용하지 않을 때(일반적으로 야간 유지 관리 기간 동안) 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="336ac-106">Surface Dock 2는 WOL(Wake on LAN)을 가장 잘 지원하여 관리자가 원격으로 디바이스를 절전 모드로 해제하고 장치 또는 기타 타사 솔루션을 사용하여 Microsoft Endpoint Manager 작업을 자동으로 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-106">Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or other third party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="336ac-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="336ac-107">Requirements</span></span>

<span data-ttu-id="336ac-108">디바이스는 Surface Dock 2와 유선으로 연결되어 있어야 합니다. AC Power에 계속 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-108">Devices must have a wired connection with Surface Dock 2 and stay connected to AC Power.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a><span data-ttu-id="336ac-110">지원되는 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="336ac-110">Supported Surface devices</span></span>

- <span data-ttu-id="336ac-111">Surface Laptop 4(Intel 프로세서)</span><span class="sxs-lookup"><span data-stu-id="336ac-111">Surface Laptop 4 (Intel processors)</span></span>
- <span data-ttu-id="336ac-112">Surface Laptop 4(AMD 프로세서)</span><span class="sxs-lookup"><span data-stu-id="336ac-112">Surface Laptop 4 (AMD processors)</span></span>
- <span data-ttu-id="336ac-113">Surface Laptop 3(Intel 프로세서)</span><span class="sxs-lookup"><span data-stu-id="336ac-113">Surface Laptop 3 (Intel processors)</span></span>
- <span data-ttu-id="336ac-114">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="336ac-114">Surface Pro 7+</span></span>
- <span data-ttu-id="336ac-115">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="336ac-115">Surface Pro 7</span></span>
- <span data-ttu-id="336ac-116">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="336ac-116">Surface Pro X</span></span>
- <span data-ttu-id="336ac-117">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="336ac-117">Surface Go 2</span></span>
- <span data-ttu-id="336ac-118">Surface Laptop 이동</span><span class="sxs-lookup"><span data-stu-id="336ac-118">Surface Laptop Go</span></span>
- <span data-ttu-id="336ac-119">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="336ac-119">Surface Book 3</span></span>

<span data-ttu-id="336ac-120">Surface Dock 2는 다음과 같은 전원 상태의 장치에 대해 WOL 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-120">Surface Dock 2 provides WOL support for devices in the following power states:</span></span>

- <span data-ttu-id="336ac-121">연결된 대기 상태</span><span class="sxs-lookup"><span data-stu-id="336ac-121">Connected standby</span></span>
- <span data-ttu-id="336ac-122">최대전력(S4 전원 상태)</span><span class="sxs-lookup"><span data-stu-id="336ac-122">Hibernation (S4 power state)</span></span>
- <span data-ttu-id="336ac-123">최대전력(S5 "꺼진" 전원 상태)</span><span class="sxs-lookup"><span data-stu-id="336ac-123">Hibernation (S5 “soft off” power state)</span></span>

<span data-ttu-id="336ac-124">전원 상태에 대한 자세한 내용은 [시스템 전원 상태 를 참조합니다.](/windows/win32/power/system-power-states)</span><span class="sxs-lookup"><span data-stu-id="336ac-124">To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="336ac-125">작동 방식</span><span class="sxs-lookup"><span data-stu-id="336ac-125">How it works</span></span>

<span data-ttu-id="336ac-126">사용하지 않는 경우 Surface 장치는 최신 대기 상태 또는 연결된 대기 상태라고 하는 유휴 상태로 들어갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-126">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="336ac-127">IT 관리자는 대상 Surface 디바이스의 MAC(미디어 액세스 제어) 주소가 포함된 절전 모드 해제 요청(매직 패킷)을 사용하여 디바이스를 원격으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-127">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="336ac-128">앱 및 타사 Microsoft Endpoint Configuration Manager 같은 많은 관리 Microsoft Store WOL에 대한 기본 제공 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="336ac-128">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span>

<span data-ttu-id="336ac-129">Surface Dock 2가 없는 장치에서 WOL을 사용하도록 설정하려면 Surface 디바이스용 [LAN에서 절전 모드 해제를 참조합니다.](wake-on-lan-for-surface-devices.md)</span><span class="sxs-lookup"><span data-stu-id="336ac-129">To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="336ac-130">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="336ac-130">Learn more</span></span>

- [<span data-ttu-id="336ac-131">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="336ac-131">Surface Dock 2</span></span>](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [<span data-ttu-id="336ac-132">Surface Configuration Manager에 대한 Wake On LAN</span><span class="sxs-lookup"><span data-stu-id="336ac-132">Wake On LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)
- [<span data-ttu-id="336ac-133">시스템 전원 상태</span><span class="sxs-lookup"><span data-stu-id="336ac-133">System Power States</span></span>](/windows/win32/power/system-power-states)
- [<span data-ttu-id="336ac-134">LAN에서 절전 모드 해제 구성 - Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="336ac-134">Configure Wake on LAN - Configuration Manager</span></span>](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
