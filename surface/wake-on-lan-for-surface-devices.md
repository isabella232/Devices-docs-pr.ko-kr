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
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442170"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="b4c45-104">Surface Configuration Manager에 대한 Wake On LAN</span><span class="sxs-lookup"><span data-stu-id="b4c45-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="b4c45-105">Surface 이더넷 어댑터를 사용하여 유선 네트워크에 연결하는 Surface 디바이스는 연결된 대기 대기에서 WOL(Wake On LAN)을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="b4c45-106">WOL을 사용하면 원격으로 디바이스를 절전 모드로 해제하고 Microsoft Endpoint Manager/Microsoft Intune과 같은 관리 솔루션을 사용하여 관리 작업을 자동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="b4c45-107">WOL 지원 장치</span><span class="sxs-lookup"><span data-stu-id="b4c45-107">WOL-supported devices</span></span>

- <span data-ttu-id="b4c45-108">Surface Ethernet 어댑터</span><span class="sxs-lookup"><span data-stu-id="b4c45-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="b4c45-109">Surface USB-C에서 이더넷 및 USB 어댑터로</span><span class="sxs-lookup"><span data-stu-id="b4c45-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="b4c45-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="b4c45-110">Surface Dock 2</span></span>
- <span data-ttu-id="b4c45-111">Surface Pro 6 이상</span><span class="sxs-lookup"><span data-stu-id="b4c45-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="b4c45-112">Surface Book(모든 세대)</span><span class="sxs-lookup"><span data-stu-id="b4c45-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="b4c45-113">Surface 노트북(모든 세대)</span><span class="sxs-lookup"><span data-stu-id="b4c45-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="b4c45-114">Surface Go(모든 세대)</span><span class="sxs-lookup"><span data-stu-id="b4c45-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="b4c45-115">Surface Studio 2(부록 참조)</span><span class="sxs-lookup"><span data-stu-id="b4c45-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="b4c45-116">Surface WOL 사용</span><span class="sxs-lookup"><span data-stu-id="b4c45-116">Using Surface WOL</span></span>

<span data-ttu-id="b4c45-117">IT 관리자는 대상 컴퓨터의 MAC 주소가 포함된 LAN 요청(매직 패킷)에 대한 절전 모드 해제를 사용하여 장치를 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="b4c45-118">WOL을 사용하여 마법 패킷을 보내고 디바이스를 절전 모드로 해제하려면 대상 장치와 이더넷 어댑터의 MAC 주소를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="b4c45-119">매직 패킷은 IP 네트워크 프로토콜을 사용하지 않는 것이기 때문에 장치의 IP 주소 또는 DNS 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="b4c45-120">Microsoft Endpoint Configuration Manager 및 타사 Microsoft Store 앱과 같은 많은 관리 솔루션은 WOL에 대한 기본 제공 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="b4c45-121">디바이스는 연결된 대기 모드(절전) 모드에 있으며 AC 전원에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="b4c45-122">Endpoint Configuration Manager를 통해 디바이스를 깨우는 방법을 알아보는 자세한 내용은 [Configure Wake on LAN - Configuration Manager을 참조합니다.](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)</span><span class="sxs-lookup"><span data-stu-id="b4c45-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


## <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="b4c45-123">장치에서 WOL이 사용하도록 설정되어 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="b4c45-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="b4c45-124">이더넷 연결 장치에서 네트워크 어댑터를 선택한 다음 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4c45-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Surface Ethernet Adapter](images/surface-ethernet.png)

2. <span data-ttu-id="b4c45-126">고급 **구성을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4c45-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="b4c45-127">최신 대기 **WoL 매직 패킷으로** 스크롤하여 **사용이** 선택되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![장치에서 WOL이 사용하도록 설정되어 있는지 확인](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="b4c45-129">부록: Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="b4c45-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="b4c45-130">Surface Studio 2에서 WOL을 사용하도록 설정하려면 다음 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="b4c45-131">다음 레지스트리 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="b4c45-132">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4c45-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="b4c45-133">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="b4c45-133">Learn more</span></span>

- [<span data-ttu-id="b4c45-134">Microsoft Surface USB-C에서 이더넷 및 USB 어댑터로</span><span class="sxs-lookup"><span data-stu-id="b4c45-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="b4c45-135">Surface USB 3.0 기가비트 이더넷 어댑터</span><span class="sxs-lookup"><span data-stu-id="b4c45-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
