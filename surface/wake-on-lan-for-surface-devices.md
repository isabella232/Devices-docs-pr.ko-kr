---
title: Surface 디바이스용 절전 모드 해제(Surface)
description: 절전 모드 해제 LAN을 사용하여 원격으로 절전 모드 해제를 통해 관리 또는 유지 관리 작업을 수행하거나 디바이스의 전원이 전원이 다운된 경우에도 관리 솔루션을 자동으로 사용하도록 설정하는 방법을 참조하세요.
keywords: 업데이트, 배포, 드라이버, wol, 절전 모드 해제
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271125"
---
# <span data-ttu-id="0a458-104">Surface Configuration Manager에 대한 Wake On LAN</span><span class="sxs-lookup"><span data-stu-id="0a458-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="0a458-105">Windows 10 버전 1607(Windows 10 1주년 업데이트라고도 알려) 이상을 실행하고 Surface Ethernet 어댑터를 사용하여 유선 네트워크에 연결하는 Surface 디바이스는 연결된 대기 대기에서 WOL(Wake On LAN)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="0a458-106">WOL을 사용하면 원격으로 디바이스를 절전 모드 해제하여 관리 또는 유지 관리 작업을 수행하거나 관리 솔루션(예: Microsoft Endpoint Configuration Manager)을 자동으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="0a458-107">예를 들어 사무실이 비어 있는 밤의 창에서 Microsoft Endpoint Configuration Manager를 사용하여 Surface Dock 또는 Surface Pro 3 도킹 스테이션에 고정된 Surface 디바이스에 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="0a458-108">WOL을 지원하려면 Surface 디바이스가 AC 전원 및 절전(절전)에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="0a458-109">최대전면 또는 전원이 꺼진 장치에서는 WOL을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="0a458-110">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="0a458-110">Supported devices</span></span>

<span data-ttu-id="0a458-111">WOL에 대해 지원되는 장치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="0a458-112">Surface Ethernet 어댑터</span><span class="sxs-lookup"><span data-stu-id="0a458-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="0a458-113">Surface USB-C에서 이더넷 및 USB 어댑터로</span><span class="sxs-lookup"><span data-stu-id="0a458-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="0a458-114">Surface 도크</span><span class="sxs-lookup"><span data-stu-id="0a458-114">Surface Dock</span></span>
* <span data-ttu-id="0a458-115">Surface Pro 3용 Surface Docking 스테이션</span><span class="sxs-lookup"><span data-stu-id="0a458-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="0a458-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="0a458-116">Surface 3</span></span>
* <span data-ttu-id="0a458-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="0a458-117">Surface Pro 3</span></span>
* <span data-ttu-id="0a458-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="0a458-118">Surface Pro 4</span></span>
* <span data-ttu-id="0a458-119">Surface Pro(5세대)</span><span class="sxs-lookup"><span data-stu-id="0a458-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="0a458-120">Surface Pro(5세대) LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="0a458-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="0a458-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="0a458-121">Surface Book</span></span>
* <span data-ttu-id="0a458-122">Surface 노트북(1세대)</span><span class="sxs-lookup"><span data-stu-id="0a458-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="0a458-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="0a458-123">Surface Pro 6</span></span>
* <span data-ttu-id="0a458-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="0a458-124">Surface Book 2</span></span>
* <span data-ttu-id="0a458-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="0a458-125">Surface Laptop 2</span></span>
* <span data-ttu-id="0a458-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="0a458-126">Surface Go</span></span>
* <span data-ttu-id="0a458-127">Surface Go LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="0a458-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="0a458-128">Surface Studio 2(아래 Surface Studio 2 지침 참조)</span><span class="sxs-lookup"><span data-stu-id="0a458-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="0a458-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="0a458-129">Surface Pro 7</span></span>
* <span data-ttu-id="0a458-130">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="0a458-130">Surface Laptop 3</span></span>
* <span data-ttu-id="0a458-131">Surface 노트북 이동</span><span class="sxs-lookup"><span data-stu-id="0a458-131">Surface Laptop Go</span></span>
* <span data-ttu-id="0a458-132">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="0a458-132">Surface Pro 7+</span></span>

## <span data-ttu-id="0a458-133">WOL 드라이버</span><span class="sxs-lookup"><span data-stu-id="0a458-133">WOL driver</span></span>

<span data-ttu-id="0a458-134">Surface 디바이스에서 WOL 지원을 사용하도록 설정하려면 Surface Ethernet 어댑터에 대한 특정 드라이버가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="0a458-135">이 드라이버는 Surface 디바이스용 표준 드라이버 및 펌웨어 팩에 포함되어 있지 않습니다. 별도로 다운로드하여 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="0a458-136">Surface WOL 드라이버(SurfaceWOL.msi)는 Microsoft 다운로드 센터의 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="0a458-137">Surface 디바이스에서 이 Microsoft Windows Installer(.msi) 파일을 실행하여 Surface WOL 드라이버를 설치하거나 Microsoft Endpoint Configuration Manager와 같은 응용 프로그램 배포 솔루션을 사용하여 Surface 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="0a458-138">배포 중에 Surface WOL 드라이버를 포함하려면 배포 프로세스 중에 .msi 파일을 응용 프로그램으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="0a458-139">Surface WOL 드라이버 파일을 추출하여 배포 프로세스에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="0a458-140">예를 들어 MDT(Microsoft Deployment Toolkit) 배포 공유에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="0a458-141">Microsoft Deployment 10을 사용하여 Surface 디바이스에 [Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)배포에서 MDT를 사용하여 Surface 배포에 대한 자세한 Toolkit.</span><span class="sxs-lookup"><span data-stu-id="0a458-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="0a458-142">이 SurfaceWOL.msi 설치하는 동안 다음 레지스트리 키가 1로 설정되어 WOL 드라이버가 설치된 시스템을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="0a458-143">배포 중에 이러한 드라이버를 별도로 추출하여 설치하도록 선택한 경우 이 레지스트리 키는 구성되지 않습니다. 수동으로 또는 스크립트를 사용하여 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="0a458-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="0a458-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="0a458-145">콘텐츠의 추출을 SurfaceWOL.msi 다음 예와 같이 MSIExec 관리 설치**옵션(/a)을**사용하여 C:\WOL\ 폴더에 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="0a458-146">Surface Studio 2 지침</span><span class="sxs-lookup"><span data-stu-id="0a458-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="0a458-147">Surface Studio 2에서 WOL을 사용하도록 설정하려면 다음 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="0a458-148">다음 레지스트리 키를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="0a458-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="0a458-149">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="0a458-150">Surface WOL 사용</span><span class="sxs-lookup"><span data-stu-id="0a458-150">Using Surface WOL</span></span>

<span data-ttu-id="0a458-151">Surface WOL 드라이버는 WOL 표준을 준수합니다. 이 경우 매직 패킷으로 알려진 특수 네트워크 통신에 의해 장치가 깨어나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="0a458-152">매직 패킷은 255(또는 16진수의 FF)와 대상 컴퓨터의 MAC 주소가 16개로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="0a458-153">[Wikipedia의](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)매직 패킷 및 WOL 표준에 대해 자세히 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="0a458-154">WOL을 사용하여 매직 패킷을 보내고 디바이스를 절전 모드로 해제하려면 대상 장치와 이더넷 어댑터의 MAC 주소를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="0a458-155">매직 패킷은 IP 네트워크 프로토콜을 사용하지 않는 것이기 때문에 장치의 IP 주소 또는 DNS 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="0a458-156">Configuration Manager와 같은 많은 관리 솔루션은 WOL에 대한 기본 제공 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="0a458-157">또한 매직 패킷을 보내 디바이스를 깨우는 데 사용할 수 있는 Microsoft Store 앱, PowerShell 모듈, 타사 응용 프로그램 및 타사 관리 솔루션을 비롯한 많은 솔루션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="0a458-158">예를 들어 TechNet 스크립트 센터에서 절전 모드 해제 [LAN PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) 모듈을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="0a458-159">장치가 매직 패킷으로 깨어난 후 응용 프로그램이 시스템의 절전 모드가 적극적으로 차단되지 않는 경우 또는 AllowSystemRequiredPowerRequests 레지스트리 키가 1로 구성되어 있지 않은 경우 장치가 절전 모드로 돌아와 응용 프로그램에서 절전 모드가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a458-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="0a458-160">이 레지스트리 키에 대한 자세한 내용은 이 문서의 [WOL](#wol-driver) 드라이버 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a458-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
