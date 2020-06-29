---
title: Surface 장치에 대 한 Wake On LAN (Surface)
description: Wake on LAN을 사용 하 여 관리 또는 유지 관리 작업을 수행 하기 위해 원격으로 장치를 종료 하거나, 디바이스의 전원이 꺼져 있는 경우에도 관리 솔루션을 자동으로 사용 하도록 설정할 수 있는 방법에 대해 알아봅니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
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
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835511"
---
# <span data-ttu-id="9575c-104">Surface Configuration Manager에 대한 Wake On LAN</span><span class="sxs-lookup"><span data-stu-id="9575c-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="9575c-105">Windows 10, 버전 1607 (Windows 10 기념 업데이트 라고도 함) 이상을 실행 하는 surface 디바이스는 연결 된 대기 상태에서 Wake On LAN (WOL)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="9575c-106">WOL을 사용 하면 관리 또는 유지 관리 작업을 수행 하도록 디바이스를 원격으로 종료 하거나 관리 솔루션 (예: Microsoft Endpoint Configuration Manager)을 자동으로 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="9575c-107">예를 들어, 사무실이 비어 있는 경우 야간 모드의 창 중에 Microsoft 끝점 구성 관리자를 사용 하 여 surface Dock 또는 Surface Pro 3 도킹 스테이션과 도킹 된 Surface 장치에 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="9575c-108">Surface 장치는 WOL을 지원 하기 위해 AC 전원 및 연결 된 대기 (절전)에 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="9575c-109">최대 절전 모드 또는 전원을 끄고 켠 장치에서는 WOL을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="9575c-110">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="9575c-110">Supported devices</span></span>

<span data-ttu-id="9575c-111">WOL에 대해 지원 되는 장치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="9575c-112">Surface Ethernet 어댑터</span><span class="sxs-lookup"><span data-stu-id="9575c-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="9575c-113">Surface USB-C ~ 이더넷 및 USB 어댑터</span><span class="sxs-lookup"><span data-stu-id="9575c-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="9575c-114">Surface 도크</span><span class="sxs-lookup"><span data-stu-id="9575c-114">Surface Dock</span></span>
* <span data-ttu-id="9575c-115">Surface Pro 3의 surface 도킹 스테이션</span><span class="sxs-lookup"><span data-stu-id="9575c-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="9575c-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="9575c-116">Surface 3</span></span>
* <span data-ttu-id="9575c-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="9575c-117">Surface Pro 3</span></span>
* <span data-ttu-id="9575c-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="9575c-118">Surface Pro 4</span></span>
* <span data-ttu-id="9575c-119">Surface Pro (다섯째 Gen)</span><span class="sxs-lookup"><span data-stu-id="9575c-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="9575c-120">LTE Advanced를 사용 하는 Surface Pro (다섯 번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="9575c-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="9575c-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="9575c-121">Surface Book</span></span>
* <span data-ttu-id="9575c-122">Surface 노트북 (첫번째 Gen)</span><span class="sxs-lookup"><span data-stu-id="9575c-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="9575c-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="9575c-123">Surface Pro 6</span></span>
* <span data-ttu-id="9575c-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="9575c-124">Surface Book 2</span></span>
* <span data-ttu-id="9575c-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="9575c-125">Surface Laptop 2</span></span>
* <span data-ttu-id="9575c-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="9575c-126">Surface Go</span></span>
* <span data-ttu-id="9575c-127">Surface Go LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="9575c-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="9575c-128">Surface Studio 2 (아래 Surface Studio 2 지침 참조)</span><span class="sxs-lookup"><span data-stu-id="9575c-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="9575c-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="9575c-129">Surface Pro 7</span></span>
* <span data-ttu-id="9575c-130">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="9575c-130">Surface Laptop 3</span></span>

## <span data-ttu-id="9575c-131">WOL 드라이버</span><span class="sxs-lookup"><span data-stu-id="9575c-131">WOL driver</span></span>

<span data-ttu-id="9575c-132">Surface 장치에서 WOL 지원을 사용 하도록 설정 하려면 Surface Ethernet 어댑터에 대 한 특정 드라이버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-132">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="9575c-133">이 드라이버는 Surface 장치에 대 한 표준 드라이버 및 펌웨어 팩에 포함 되어 있지 않습니다.-별도로 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-133">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="9575c-134">Microsoft 다운로드 센터의 [IT 페이지 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 surface WOL 드라이버 (SurfaceWOL.msi)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-134">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="9575c-135">Surface 장치에서이 Microsoft Windows Installer (.msi) 파일을 실행 하 여 Surface WOL 드라이버를 설치 하거나, Microsoft 끝점 구성 관리자와 같은 응용 프로그램 배포 솔루션을 사용 하 여 Surface 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-135">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="9575c-136">배포 중에 Surface WOL 드라이버를 포함 하려면 배포 프로세스 중에 .msi 파일을 응용 프로그램으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-136">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="9575c-137">배포 프로세스에 포함할 Surface WOL 드라이버 파일을 추출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-137">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="9575c-138">예를 들어, MDT (Microsoft Deployment Toolkit) 배포 공유에 포함 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-138">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="9575c-139">Windows 10 배포의 MDT를 사용 하 여 Surface 배포에 대 한 자세한 내용은 [Microsoft 배포 툴킷를 사용 하 여 surface 디바이스에](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9575c-139">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="9575c-140">SurfaceWOL.msi를 설치 하는 동안 다음 레지스트리 키 값이 1로 설정 되어 있는 경우 WOL 드라이버가 설치 된 시스템을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-140">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="9575c-141">배포 중에 별도로 드라이버를 추출 하 고 설치 하도록 선택한 경우이 레지스트리 키가 구성 되지 않으며 수동으로 또는 스크립트를 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-141">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="9575c-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="9575c-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="9575c-143">SurfaceWOL.msi의 내용을 추출 하려면 다음 예제와 같이 MSIExec 관리 설치 옵션 (**/a**)을 사용 하 여 C:\WOL\ 폴더에 콘텐츠를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-143">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="9575c-144">Surface Studio 2 지침</span><span class="sxs-lookup"><span data-stu-id="9575c-144">Surface Studio 2 instructions</span></span>

<span data-ttu-id="9575c-145">Surface Studio 2에서 WOL을 사용 하도록 설정 하려면 다음 절차를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-145">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="9575c-146">다음 레지스트리 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-146">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="9575c-147">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-147">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="9575c-148">Surface WOL 사용</span><span class="sxs-lookup"><span data-stu-id="9575c-148">Using Surface WOL</span></span>

<span data-ttu-id="9575c-149">Surface WOL 드라이버는 장치가 매직 패킷으로 알려진 특별 한 네트워크 통신을 통해 woken 하는 WOL 표준을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-149">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="9575c-150">매직 패킷은 6 바이트의 255 (또는 16 진수로 FF)로 구성 되 고 대상 컴퓨터의 MAC 주소에 대 한 16 회 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-150">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="9575c-151">마법의 패킷과, [위키백과](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)의 WOL 표준에 대해 자세히 읽어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-151">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="9575c-152">자동 패킷을 보내고 WOL을 사용 하 여 디바이스를 깨우기 하려면 대상 디바이스 및 이더넷 어댑터의 MAC 주소를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-152">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="9575c-153">매직 패킷에서는 IP 네트워크 프로토콜을 사용 하지 않기 때문에 장치의 IP 주소 또는 DNS 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-153">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="9575c-154">구성 관리자와 같은 대부분의 관리 솔루션은 WOL에 대 한 기본 제공 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-154">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="9575c-155">또한 Microsoft Store 앱, PowerShell 모듈, 타사 응용 프로그램, 그리고 장치를 종료 하는 데 매직 패킷을 보낼 수 있는 타사 관리 솔루션 등 다양 한 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-155">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="9575c-156">예를 들어 TechNet 스크립트 센터에서 [Wake ON LAN PowerShell 모듈](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-156">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="9575c-157">장치가 매직 패킷으로 woken 된 후에는 응용 프로그램이 시스템에서 절전 모드를 방해 하지 않는 경우 또는 AllowSystemRequiredPowerRequests 레지스트리 키가 1로 구성 되지 않은 경우 응용 프로그램이 절전 모드를 막을 수 있도록 장치가 절전 모드로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9575c-157">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="9575c-158">이 레지스트리 키에 대 한 자세한 내용은이 문서의 [WOL 드라이버](#wol-driver) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9575c-158">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
