---
title: Surface Configuration Manager에 대한 Wake On LAN
description: Wake On LAN을 사용하여 원격으로 디바이스 절전 모드 해제를 통해 관리 작업을 자동으로 수행하는 방법을 참조합니다.
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613805"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="1d950-104">Surface Configuration Manager에 대한 Wake On LAN</span><span class="sxs-lookup"><span data-stu-id="1d950-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="1d950-105">장치를 최신으로 유지하려면 IT 관리자가 사용하지 않을 때(일반적으로 야간 유지 관리 기간 동안) 장치를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="1d950-106">WOL(Wake on LAN)을 사용하면 관리자가 원격으로 디바이스를 절전 모드로 해제하고 자동 Microsoft Endpoint Manager 또는 타사 솔루션을 사용하여 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-106">Wake on LAN (WOL) enables admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third-party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d950-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d950-107">Requirements</span></span>

<span data-ttu-id="1d950-108">디바이스는 AC 전원에 연결되어 있어야하며 다음 호환 이더넷 어댑터 중 하나와 유선으로 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-108">Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:</span></span>

- <span data-ttu-id="1d950-109">Surface USB 3.0 기가비트 이더넷 어댑터</span><span class="sxs-lookup"><span data-stu-id="1d950-109">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>
- <span data-ttu-id="1d950-110">Surface Ethernet Adapter</span><span class="sxs-lookup"><span data-stu-id="1d950-110">Surface Ethernet Adapter</span></span>
- <span data-ttu-id="1d950-111">Surface USB-C에서 이더넷 및 USB 어댑터로</span><span class="sxs-lookup"><span data-stu-id="1d950-111">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="1d950-112">Microsoft USB-C Travel Adapter Hub</span><span class="sxs-lookup"><span data-stu-id="1d950-112">Microsoft USB-C Travel Adapter Hub</span></span>
- <span data-ttu-id="1d950-113">Surface 도크</span><span class="sxs-lookup"><span data-stu-id="1d950-113">Surface Dock</span></span>
- <span data-ttu-id="1d950-114">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="1d950-114">Surface Dock 2</span></span>

> [!NOTE]
> <span data-ttu-id="1d950-115">Surface Dock 2는 추가 IT 구성 없이도 LAN에서 Wake on LAN을 가장 잘 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-115">Surface Dock 2 provides the best support for Wake on LAN without the need for any additional IT configuration.</span></span> <span data-ttu-id="1d950-116">자세한 내용은 [Surface Dock 2용 LAN 절전 모드 해제를 참조합니다.](wake-on-lan-surface-dock2.md)</span><span class="sxs-lookup"><span data-stu-id="1d950-116">To learn more, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="1d950-117">작동 방식</span><span class="sxs-lookup"><span data-stu-id="1d950-117">How it works</span></span>

<span data-ttu-id="1d950-118">사용하지 않는 경우 Surface 장치는 최신 대기 상태 또는 연결된 대기 상태라고 하는 유휴 상태로 들어갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-118">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="1d950-119">IT 관리자는 대상 Surface 디바이스의 MAC(미디어 액세스 제어) 주소가 포함된 절전 모드 해제 요청(매직 패킷)을 사용하여 디바이스를 원격으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-119">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="1d950-120">앱 및 타사 Microsoft Endpoint Configuration Manager 같은 많은 관리 Microsoft Store WOL에 대한 기본 제공 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="1d950-121">Endpoint Configuration Manager를 통해 디바이스를 깨우는 방법을 알아보는 자세한 내용은 [Configure Wake on LAN - Configuration Manager을 참조합니다.](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)</span><span class="sxs-lookup"><span data-stu-id="1d950-121">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>

<span data-ttu-id="1d950-122">LAN에서 절전 모드 해제 지원은 절전 상태, 연결된 대기 상태 또는 최대 절전 모드(S4 전원 상태)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-122">Support for Wake on LAN varies depending on sleep state:  Connected Standby or Hibernation (S4 power state).</span></span>

## <a name="connected-standby"></a><span data-ttu-id="1d950-123">연결된 대기</span><span class="sxs-lookup"><span data-stu-id="1d950-123">Connected Standby</span></span>

<span data-ttu-id="1d950-124">기본적으로 연결된 Windows 10 Surface 디바이스에 대해 LAN 절전 모드 해제를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-124">By default, Windows 10 supports Wake on LAN for Surface devices in Connected Standby.</span></span>

### <a name="supported-surface-devices---connected-standby"></a><span data-ttu-id="1d950-125">지원되는 Surface 장치 - 연결된 대기</span><span class="sxs-lookup"><span data-stu-id="1d950-125">Supported Surface devices - Connected Standby</span></span>

- <span data-ttu-id="1d950-126">Surface Laptop 4(Intel 프로세서만 해당)</span><span class="sxs-lookup"><span data-stu-id="1d950-126">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="1d950-127">Surface Laptop 3(Intel 프로세서만 해당)</span><span class="sxs-lookup"><span data-stu-id="1d950-127">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="1d950-128">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="1d950-128">Surface Pro 7+</span></span>
- <span data-ttu-id="1d950-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="1d950-129">Surface Pro 7</span></span>
- <span data-ttu-id="1d950-130">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="1d950-130">Surface Pro X</span></span>
- <span data-ttu-id="1d950-131">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="1d950-131">Surface Go 2</span></span>
- <span data-ttu-id="1d950-132">Surface Laptop 이동</span><span class="sxs-lookup"><span data-stu-id="1d950-132">Surface Laptop Go</span></span>
- <span data-ttu-id="1d950-133">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="1d950-133">Surface Book 3</span></span>

## <a name="hibernation"></a><span data-ttu-id="1d950-134">최대 최대화</span><span class="sxs-lookup"><span data-stu-id="1d950-134">Hibernation</span></span>

<span data-ttu-id="1d950-135">최대 절전 모드를 해제하려면 Surface Enterprise Management [Mode(SEMM)를 통해](surface-enterprise-management-mode.md) UEFI 정책 설정을 사용하도록 설정해야 합니다(Surface Dock 2에 연결된 디바이스에는 필요하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="1d950-135">To wake devices out of Hibernation requires enabling a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (not required for devices connected to Surface Dock 2).</span></span>

### <a name="supported-surface-devices---hibernation"></a><span data-ttu-id="1d950-136">지원되는 Surface 장치 - 최대 사용</span><span class="sxs-lookup"><span data-stu-id="1d950-136">Supported Surface devices - Hibernation</span></span>

- <span data-ttu-id="1d950-137">Surface Laptop 4(Intel 프로세서만 해당)</span><span class="sxs-lookup"><span data-stu-id="1d950-137">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="1d950-138">Surface Laptop 3(Intel 프로세서만 해당)</span><span class="sxs-lookup"><span data-stu-id="1d950-138">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="1d950-139">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="1d950-139">Surface Pro 7+</span></span>
- <span data-ttu-id="1d950-140">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="1d950-140">Surface Pro 7</span></span>
- <span data-ttu-id="1d950-141">Surface Laptop 이동</span><span class="sxs-lookup"><span data-stu-id="1d950-141">Surface Laptop Go</span></span>
- <span data-ttu-id="1d950-142">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="1d950-142">Surface Book 3</span></span>

### <a name="to-enable-wake-on-lan-uefi-setting"></a><span data-ttu-id="1d950-143">LAN UEFI에서 절전 모드 해제 설정을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1d950-143">To enable Wake on LAN UEFI setting</span></span>

<span data-ttu-id="1d950-144">LAN UEFI 절전 모드 해제 설정을 사용하도록 설정하려면 대상 장치를 SEMM에 등록하고 구성 패키지를 만든 다음 장치에 패키지를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-144">To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices.</span></span> <span data-ttu-id="1d950-145">자세한 내용은 다음을 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d950-145">For more information, refer to:</span></span>

- [<span data-ttu-id="1d950-146">Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="1d950-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="1d950-147">SEMM을 사용하여 Surface 장치 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="1d950-147">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)

1. <span data-ttu-id="1d950-148">[**Surface UEFI 구성기 를 다운로드하여 설치합니다.**](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="1d950-148">Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
2. <span data-ttu-id="1d950-149">구성 **패키지**  >  **만들기**+  >  **인증서**보호  > **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d950-149">Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.</span></span>
3. <span data-ttu-id="1d950-150">고급 **설정으로 이동하고** **LAN의 절전 모드 해제를 으로** **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d950-150">Go to **Advanced settings** and switch **Wake on LAN** to **On**.</span></span>
4. <span data-ttu-id="1d950-151">대상 장치에 패키지를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d950-151">Apply the package to target devices.</span></span>

    > [!div class="mx-imgBorder"]
    > ![LAN UEFI에서 절전 모드 해제 정책 설정 사용](images/wol-uefi.png)

## <a name="learn-more"></a><span data-ttu-id="1d950-153">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="1d950-153">Learn more</span></span>

- [<span data-ttu-id="1d950-154">Surface Dock 2용 LAN 절전 모드 해제</span><span class="sxs-lookup"><span data-stu-id="1d950-154">Wake on LAN for Surface Dock 2</span></span>](wake-on-lan-surface-dock2.md)
- [<span data-ttu-id="1d950-155">Microsoft Surface USB-C에서 이더넷 및 USB 어댑터로</span><span class="sxs-lookup"><span data-stu-id="1d950-155">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [<span data-ttu-id="1d950-156">Surface USB 3.0 기가비트 이더넷 어댑터</span><span class="sxs-lookup"><span data-stu-id="1d950-156">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
