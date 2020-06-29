---
title: 이더넷 어댑터 및 Surface 배포(Surface)
description: 이 문서에서는 Surface 디바이스에 네트워크 배포를 수행하는 데 도움이 되는 지침과 답변을 제공합니다.
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: 이더넷, 배포, 이동식, 네트워크, 연결, 부팅, 펌웨어, 디바이스, 어댑터, PXE 부팅, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834708"
---
# <span data-ttu-id="d3f67-104">이더넷 어댑터 및 Surface 배포</span><span class="sxs-lookup"><span data-stu-id="d3f67-104">Ethernet adapters and Surface deployment</span></span>


<span data-ttu-id="d3f67-105">이 문서에서는 Surface Pro 3 이상을 비롯 한 Surface 장치에 대 한 네트워크 배포를 수행 하는 데 도움이 되는 지침과 답변을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-105">This article provides guidance and answers to help you perform a network deployment to Surface devices including Surface Pro 3 and later.</span></span>

<span data-ttu-id="d3f67-106">Surface 디바이스에 대한 네트워크 배포 작업의 경우 시스템 관리자에게 몇 가지 고유한 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-106">Network deployment to Surface devices can pose some unique challenges for system administrators.</span></span> <span data-ttu-id="d3f67-107">네이티브 유선 이더넷 어댑터가 부족하여 관리자는 이동식 이더넷 어댑터를 통해 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-107">Due to the lack of a native wired Ethernet adapter, administrators must provide connectivity through a removable Ethernet adapter.</span></span>

## <span data-ttu-id="d3f67-108">Surface 디바이스용 이더넷 어댑터 선택</span><span class="sxs-lookup"><span data-stu-id="d3f67-108">Select an Ethernet adapter for Surface devices</span></span>


<span data-ttu-id="d3f67-109">배포 환경으로 부팅하는 방법 또는 배포 솔루션에서 디바이스를 인식하는 방법에 대한 문제를 해결하려면 먼저 유선 네트워크 어댑터를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-109">Before you can address the concerns of how you will boot to your deployment environment or how devices will be recognized by your deployment solution, you have to use a wired network adapter.</span></span>

<span data-ttu-id="d3f67-110">이더넷 어댑터를 선택할 때 주요 고려 사항은 해당 어댑터가 네트워크에서 Surface 디바이스를 부팅하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-110">The primary concern when selecting an Ethernet adapter is how that adapter will boot your Surface device from the network.</span></span> <span data-ttu-id="d3f67-111">WDS (Windows 배포 서비스)를 사용 하는 미리 준비 된 클라이언트 또는 Microsoft 끝점 구성 관리자를 사용 하는 경우 이동식 이더넷 어댑터가 특정 Surface 디바이스에 대해 전용 이거나 여러 장치 중에서 공유 되는지 여부도 고려해 야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-111">If you are pre-staging clients with Windows Deployment Services (WDS) or if you are using Microsoft Endpoint Configuration Manager, you may also want to consider whether the removable Ethernet adapters will be dedicated to a specific Surface device or shared among multiple devices.</span></span> <span data-ttu-id="d3f67-112">공유 어댑터의 잠재적 충돌에 대 한 자세한 내용은이 문서의 뒷부분에 나오는 [이동식 이더넷 어댑터를 사용 하 여 MAC 주소 관리](#manage-mac-addresses) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f67-112">For more information on potential conflicts with shared adapters, see [Manage MAC addresses with removable Ethernet adapters](#manage-mac-addresses) later in this article.</span></span>

<span data-ttu-id="d3f67-113">네트워크(PXE 부팅)를 통한 부팅은 이더넷 어댑터 또는 Microsoft의 도킹 스테이션을 사용할 경우에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-113">Booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="d3f67-114">네트워크에서 부팅하려면 이더넷 어댑터 또는 도크의 칩셋을 검색하여 Surface 디바이스의 펌웨어에서 부팅 디바이스로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-114">To boot from the network, the chipset in the Ethernet adapter or dock must be detected and configured as a boot device in the firmware of the Surface device.</span></span> <span data-ttu-id="d3f67-115">Surface Ethernet Adapter와 같은 Microsoft 이더넷 어댑터와 [Surface 도크](https://www.microsoft.com/surface/accessories/surface-dock)에서는 Surface 펌웨어와 호환되는 칩셋이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-115">Microsoft Ethernet adapters, such as the Surface Ethernet Adapter and the [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock) use a chipset that is compatible with the Surface firmware.</span></span>

<span data-ttu-id="d3f67-116">Surface 디바이스를 사용하는 네트워크 부팅에 지원되는 이더넷 디바이스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-116">The following Ethernet devices are supported for network boot with Surface devices:</span></span>

-   <span data-ttu-id="d3f67-117">Surface USB-C ~ 이더넷 및 USB 3.0 어댑터</span><span class="sxs-lookup"><span data-stu-id="d3f67-117">Surface USB-C to Ethernet and USB 3.0 Adapter</span></span>

-   <span data-ttu-id="d3f67-118">Surface USB 3.0-기가 비트 이더넷 어댑터</span><span class="sxs-lookup"><span data-stu-id="d3f67-118">Surface USB 3.0 to Gigabit Ethernet Adapter</span></span>

-   <span data-ttu-id="d3f67-119">Surface 도크</span><span class="sxs-lookup"><span data-stu-id="d3f67-119">Surface Dock</span></span>

-   <span data-ttu-id="d3f67-120">Surface 3 도킹 스테이션</span><span class="sxs-lookup"><span data-stu-id="d3f67-120">Surface 3 Docking Station</span></span>

-   <span data-ttu-id="d3f67-121">Surface Pro 3 도킹 스테이션</span><span class="sxs-lookup"><span data-stu-id="d3f67-121">Surface Pro 3 Docking Station</span></span>

-   <span data-ttu-id="d3f67-122">Surface Pro와 Surface Pro 2용 도킹 스테이션</span><span class="sxs-lookup"><span data-stu-id="d3f67-122">Docking Station for Surface Pro and Surface Pro 2</span></span>

<span data-ttu-id="d3f67-123">타사 이더넷 어댑터의 경우 PXE 부팅이 지원되지는 않지만 네트워크 배포에는 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-123">Third-party Ethernet adapters are also supported for network deployment, although they do not support PXE boot.</span></span> <span data-ttu-id="d3f67-124">타사 이더넷 어댑터를 사용하려면 배포 부팅 이미지에 드라이버를 로드하고 USB 스틱과 같은 별도의 저장 디바이스에서 해당 부팅 이미지를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-124">To use a third-party Ethernet adapter, you must load the drivers into the deployment boot image and you must launch that boot image from a separate storage device, such as a USB stick.</span></span>

## <span data-ttu-id="d3f67-125">네트워크에서 Surface 디바이스 부팅</span><span class="sxs-lookup"><span data-stu-id="d3f67-125">Boot Surface devices from the network</span></span>

<span data-ttu-id="d3f67-126">네트워크 또는 연결된 USB 스틱에서 부팅하려면 Surface 디바이스가 대체 부팅 디바이스에서 부팅하도록 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-126">To boot from the network or a connected USB stick, you must instruct the Surface device to boot from an alternate boot device.</span></span> <span data-ttu-id="d3f67-127">USB 부팅 디바이스에 우선 순위를 지정하도록 시스템 펌웨어에서 부팅 순서를 변경하거나, 부팅 프로세스 중 대체 부팅 디바이스에서 부팅하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-127">You can alter the boot order in the system firmware to prioritize USB boot devices, or you can instruct it to boot from an alternate boot device during the boot up process.</span></span>

<span data-ttu-id="d3f67-128">대체 부팅 디바이스에서 Surface 디바이스를 부팅하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d3f67-128">To boot a Surface device from an alternative boot device, follow these steps:</span></span>

1.  <span data-ttu-id="d3f67-129">Surface 디바이스가 꺼졌는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-129">Ensure the Surface device is powered off.</span></span>
2.  <span data-ttu-id="d3f67-130">**볼륨 작게** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-130">Press and hold the **Volume Down** button.</span></span>
3.  <span data-ttu-id="d3f67-131">**전원** 단추를 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-131">Press and release the **Power** button.</span></span>
4.  <span data-ttu-id="d3f67-132">USB 스틱 또는 이더넷 어댑터에서 시스템 부팅이 시작되고 나면 **볼륨 작게** 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-132">After the system begins to boot from the USB stick or Ethernet adapter, release the **Volume Down** button.</span></span>

>[!NOTE]
><span data-ttu-id="d3f67-133">이더넷 어댑터 외에도 키보드를 Surface 디바이스에 연결하여 사전 설치 환경에서 배포 마법사를 탐색해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-133">In addition to an Ethernet adapter, a keyboard must also be connected to the Surface device to enter the preinstallation environment and navigate the deployment wizard.</span></span>

 
<span data-ttu-id="d3f67-134">Windows 10 버전 1511 이상(Windows 10 버전 1511용 Windows ADK(Windows Assessment and Deployment Kit) 포함)의 경우 기본적으로 Microsoft Surface Ethernet Adapter용 드라이버가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-134">For Windows 10, version 1511 and later – including the Windows Assessment and Deployment Kit (Windows ADK) for Windows 10, version 1511 – the drivers for Microsoft Surface Ethernet Adapters are present by default.</span></span> <span data-ttu-id="d3f67-135">Microsoft Deployment Toolkit과 같은 WinPE(Windows 사전 설치 환경)를 사용하는 배포 솔루션을 사용하고 PXE로 네트워크에서 부팅하는 경우에는 배포 솔루션이 Windows ADK의 최신 버전을 사용하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-135">If you are using a deployment solution that uses Windows Preinstallation Environment (WinPE), like the Microsoft Deployment Toolkit, and booting from the network with PXE, ensure that your deployment solution is using the latest version of the Windows ADK.</span></span>

## <a href="" id="manage-mac-addresses"></a><span data-ttu-id="d3f67-136">이동식 이더넷 어댑터를 사용하여 MAC 주소 관리</span><span class="sxs-lookup"><span data-stu-id="d3f67-136">Manage MAC addresses with removable Ethernet adapters</span></span>

<span data-ttu-id="d3f67-137">네트워크에서 Windows 배포를 수행하는 관리자의 또 다른 고려 사항은 동일한 이더넷 어댑터를 사용하여 두 대 이상의 컴퓨터에 배포할 때 컴퓨터를 식별하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-137">Another consideration for administrators performing Windows deployment over the network is how you will identify computers when you use the same Ethernet adapter to deploy to more than one computer.</span></span> <span data-ttu-id="d3f67-138">배포 기술에서 사용되는 공통 식별자는 각 이더넷 어댑터와 연결된 MAC(미디어 액세스 제어) 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-138">A common identifier used by deployment technologies is the Media Access Control (MAC) address that is associated with each Ethernet adapter.</span></span> <span data-ttu-id="d3f67-139">그러나 동일한 이더넷 어댑터를 사용하여 여러 컴퓨터에 배포하는 경우 서로 다른 컴퓨터에서 사용했을 때 이동식 어댑터의 MAC 주소를 구분할 방법이 없으므로 MAC 주소를 검사하는 배포 기술을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-139">However, when you use the same Ethernet adapter to deploy to multiple computers, you cannot use a deployment technology that inspects MAC addresses because there is no way to differentiate the MAC address of the removable adapter when used on the different computers.</span></span>

<span data-ttu-id="d3f67-140">MAC 주소 충돌을 피하는 가장 간단한 방법은 각 Surface 디바이스에 대해 전용 이동식 이더넷 어댑터를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-140">The simplest solution to avoid MAC address conflicts is to provide a dedicated removable Ethernet adapter for each Surface device.</span></span> <span data-ttu-id="d3f67-141">이렇게 하면 여러 시나리오에서 이더넷 어댑터 또는 도킹 스테이션의 추가 기능을 정기적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-141">This can make sense in many scenarios where the Ethernet adapter or the additional functionality of the docking station will be used regularly.</span></span> <span data-ttu-id="d3f67-142">그러나 도킹 스테이션의 추가 연결 또는 무선 네트워크 지원이 모든 시나리오에 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-142">However, not all scenarios call for the additional connectivity of a docking station or support for wired networks.</span></span>

<span data-ttu-id="d3f67-143">어댑터가 공유될 때 충돌을 방지하는 또 다른 잠재적 해결 방법으로는 [MDT(Microsoft Deployment Toolkit)](https://technet.microsoft.com/windows/dn475741)를 사용하여 Surface 디바이스에 배포를 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-143">Another potential solution to avoid conflict when adapters are shared is to use the [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) to perform deployment to Surface devices.</span></span> <span data-ttu-id="d3f67-144">MDT에서는 개별 컴퓨터 식별에 MAC 주소를 사용하지 않으므로 이 제한 사항이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-144">MDT does not use the MAC address to identify individual computers and thus is not subject to this limitation.</span></span> <span data-ttu-id="d3f67-145">그러나 MDT는 Windows 배포 서비스를 사용하여 PXE 부팅 기능을 제공하며, 이 섹션의 뒷부분에서 설명하는 미리 구성된 클라이언트 관련 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-145">However, MDT does use Windows Deployment Services to provide PXE boot functionality, and is subject to the limitations regarding pre-staged clients which is covered later in this section.</span></span>

<span data-ttu-id="d3f67-146">배포를 위해 공유 어댑터를 사용하는 경우 영향을 받는 배포 기술에 대한 해결 방법은 다른 방법을 사용하여 고유한 시스템을 식별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-146">When you use a shared adapter for deployment, the solution for affected deployment technologies is to use another means to identify unique systems.</span></span> <span data-ttu-id="d3f67-147">Configuration Manager 및 WDS의 경우 이 문제로 인해 영향을 받을 수 있으므로 컴퓨터 제조업체에서 컴퓨터 펌웨어에 포함한 시스템 UUID(Universal Unique Identifier)를 사용하여 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-147">For Configuration Manager and WDS, both of which can be affected by this issue, the solution is to use the System Universal Unique Identifier (System UUID) that is embedded in the computer firmware by the computer manufacturer.</span></span> <span data-ttu-id="d3f67-148">Surface 디바이스의 경우 **디바이스 정보** 아래에 있는 컴퓨터 펌웨어에서 이 항목을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-148">For Surface devices, you can see this entry in the computer firmware under **Device Information**.</span></span>

<span data-ttu-id="d3f67-149">Surface 디바이스 펌웨어에 액세스하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d3f67-149">To access the firmware of a Surface device, follow these steps:</span></span>

1.  <span data-ttu-id="d3f67-150">Surface 디바이스가 꺼졌는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-150">Ensure the Surface device is powered off.</span></span>
2.  <span data-ttu-id="d3f67-151">**볼륨 크게** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-151">Press and hold the **Volume Up** button.</span></span>
3.  <span data-ttu-id="d3f67-152">**전원** 단추를 눌렀다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-152">Press and release the **Power** button.</span></span>
4.  <span data-ttu-id="d3f67-153">디바이스 부팅이 시작되고 나면 **볼륨 크게** 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-153">After the device begins to boot, release the **Volume Up** button.</span></span>

<span data-ttu-id="d3f67-154">WDS를 사용하여 배포할 때 배포 서버가 미리 구성되어 알려진 클라이언트에만 응답하도록 구성되는 경우 MAC 주소는 컴퓨터를 식별하는 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-154">When deploying with WDS, the MAC address is only used to identify a computer when the deployment server is configured to respond only to known, pre-staged clients.</span></span> <span data-ttu-id="d3f67-155">클라이언트를 미리 구성하는 경우 관리자는 Active Directory에서 컴퓨터 계정을 만들고 MAC 주소 또는 시스템 UUID로 해당 컴퓨터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-155">When pre-staging a client, an administrator creates a computer account in Active Directory and defines that computer by the MAC address or the System UUID.</span></span> <span data-ttu-id="d3f67-156">공유 이더넷 어댑터로 인해 발생하는 ID 충돌을 방지하려면 [시스템 UUID를 사용하여 미리 구성된 클라이언트를 정의](https://technet.microsoft.com/library/cc742034)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-156">To avoid the identity conflicts caused by shared Ethernet adapters, you should use [System UUID to define pre-staged clients](https://technet.microsoft.com/library/cc742034).</span></span> <span data-ttu-id="d3f67-157">또는 **Windows 배포 서버 속성**의 [**PXE 응답** 탭](https://technet.microsoft.com/library/cc732360)에서 **알려지거나 알 수 없는 모든 클라이언트 컴퓨터에 응답**을 선택하여 MAC 주소 또는 시스템 UUID에서 정의하지 않아도 되는 알 수 없는 클라이언트에 응답하도록 WDS를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-157">Alternatively, you can configure WDS to respond to unknown clients that do not require definition by either MAC address or System UUID by selecting the **Respond to all client computers (known and unknown)** option on the [**PXE Response** tab](https://technet.microsoft.com/library/cc732360) in **Windows Deployment Server Properties**.</span></span>

<span data-ttu-id="d3f67-158">공유 이더넷 어댑터와의 충돌은 Configuration Manager가 훨씬 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-158">The potential for conflicts with shared Ethernet adapters is much higher with Configuration Manager.</span></span> <span data-ttu-id="d3f67-159">WDS에서는 MAC 주소를 사용하여 개별 시스템을 정의하도록 구성한 경우에만 작업을 수행하지만 Configuration Manager는 새 컴퓨터 또는 알 수 없는 컴퓨터에 배포를 수행할 때마다 MAC 주소를 사용하여 개별 시스템을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-159">Where WDS only uses MAC addresses to define individual systems when configured to do so, Configuration Manager uses the MAC address to define individual systems whenever performing a deployment to new or unknown computers.</span></span> <span data-ttu-id="d3f67-160">이렇게 하면 디바이스가 잘못 구성되거나, 공유 이더넷 어댑터로 두 개 이상의 시스템을 배포할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-160">This can result in improperly configured devices or even the inability to deploy more than one system with a shared Ethernet adapter.</span></span> <span data-ttu-id="d3f67-161">이 상황에는 핵심 인프라 및 보안 블로그의 블로그 게시물 인 [여러 SCCM OSD에 동일한 외부 이더넷 어댑터를 사용 하는 방법](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)에 대해 자세히 설명 하는 몇 가지 잠재적인 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f67-161">There are several potential solutions for this situation that are described in detail in [How to Use The Same External Ethernet Adapter For Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374), a blog post on the Core Infrastructure and Security Blog.</span></span>

 

 





