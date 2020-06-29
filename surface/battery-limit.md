---
title: 배터리 제한 설정 (Surface)
description: 배터리 제한은 Surface 디바이스 배터리가 충전 되는 방법을 변경 하는 UEFI 설정 이며 해당 수명 기간 연장 될 수 있습니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835988"
---
# <span data-ttu-id="37124-103">배터리 제한 설정</span><span class="sxs-lookup"><span data-stu-id="37124-103">Battery Limit setting</span></span>

<span data-ttu-id="37124-104">배터리 제한 옵션은 Surface 디바이스 배터리가 충전 되는 방법을 변경 하는 UEFI 설정으로, 해당 수명 기간을 연장 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37124-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="37124-105">장치를 키오스크 솔루션에 통합 하는 등의 경우와 같이 장치가 전원이 계속 연결 되어 있는 경우이 설정이 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37124-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="37124-106">배터리 제한 작동 방식</span><span class="sxs-lookup"><span data-stu-id="37124-106">How Battery Limit works</span></span>

<span data-ttu-id="37124-107">배터리 용량으로 장치를 설정 하면 디바이스 배터리 충전에 대 한 프로토콜이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37124-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="37124-108">배터리 한계를 사용 하는 경우 배터리 충전량이 최대 용량을 50%로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="37124-109">Windows에 보고 된 충전 수준에 따라이 한도가 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37124-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="37124-110">따라서 배터리가 최대 50%까지 충전 되어 있으며,이 한도를 초과 하 여 충전 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37124-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="37124-111">장치가 50% 충전을 초과 하는 동안 배터리 용량 한도를 사용 하는 경우 배터리 아이콘에 장치가 연결 되어 있지만 장치가 최대 충전 용량의 50%에 도달할 때까지 방전 됨을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="37124-112">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="37124-112">Supported devices</span></span>
<span data-ttu-id="37124-113">배터리 한도 UEFI 설정은 Surface Pro 7 및 Surface 노트북 3을 비롯 한 최신 Surface 장치에 기본으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37124-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="37124-114">이전 장치에는 Windows Update를 통해 또는 [Surface Support 사이트](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)의 MSI 드라이버와 펌웨어 패키지를 통해 사용할 수 있는 [surface UEFI 펌웨어 업데이트가](manage-surface-driver-and-firmware-updates.md)필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="37124-115">지원 되는 각 장치에 필요한 특정 Surface UEFI 버전에 대해 [오랜 시간 동안 연결 되어야 하는 Surface 디바이스에 대해 "배터리 한도" 사용을](https://support.microsoft.com/help/4464941) 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="37124-116">Surface UEFI (Surface Pro 4 이상)에서 배터리 한도 사용</span><span class="sxs-lookup"><span data-stu-id="37124-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="37124-117">Surface uefi 배터리 제한 설정은 Surface UEFI로 부팅 하 여 구성할 수 있습니다 (장치를 켤 때**Power + 볼륨 위로** 전환).</span><span class="sxs-lookup"><span data-stu-id="37124-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="37124-118">**부팅 구성을**선택한 다음 **고급 옵션**에서 **배터리 잔량 사용 모드** **를 켜기로 전환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="37124-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![고급 옵션 스크린샷](images/enable-bl.png) 

## <span data-ttu-id="37124-120">Surface Go 및 Surface Go에서 배터리 한도 사용 설정 2</span><span class="sxs-lookup"><span data-stu-id="37124-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="37124-121">Surface 전지 제한 설정은 Surface UEFI로 부팅 하 여 구성할 수 있습니다 (장치를 켤 때**Power + 볼륨 위로** 전환).</span><span class="sxs-lookup"><span data-stu-id="37124-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="37124-122">**부팅 구성을**선택한 다음 **키오스크 모드**아래에서 슬라이더를 오른쪽으로 이동 하 여 배터리 용량 제한을 **사용**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![화면 이동의 키오스크 모드 배터리 제한 스크린샷](images/go-batterylimit.png) 

## <span data-ttu-id="37124-124">Surface UEFI (Surface Pro 3)에서 배터리 한도 사용</span><span class="sxs-lookup"><span data-stu-id="37124-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="37124-125">Surface uefi 배터리 제한 설정은 Surface UEFI로 부팅 하 여 구성할 수 있습니다 (장치를 켤 때**Power + 볼륨 위로** 전환).</span><span class="sxs-lookup"><span data-stu-id="37124-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="37124-126">**키오스크 모드**를 선택 하 고 **배터리 제한을**선택한 다음 **사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![고급 옵션 스크린샷](images/enable-bl-sp3.png) 

![고급 옵션 스크린샷](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="37124-129">Surface Enterprise 관리 모드 (SEMM) 또는 Surface Pro 3 펌웨어 PowerShell 스크립트를 사용 하 여 배터리 한도 사용</span><span class="sxs-lookup"><span data-stu-id="37124-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="37124-130">Surface UEFI 배터리 제한은 다음 방법을 통해 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37124-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="37124-131">Surface Pro 4 이상</span><span class="sxs-lookup"><span data-stu-id="37124-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="37124-132">Microsoft Surface UEFI 구성자</span><span class="sxs-lookup"><span data-stu-id="37124-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="37124-133">[IT 다운로드 Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 의 Surface UEFI Manager Powershell 스크립트 (SEMM_Powershell.zip)</span><span class="sxs-lookup"><span data-stu-id="37124-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="37124-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="37124-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="37124-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="37124-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="37124-136">Microsoft Surface UEFI 구성자 사용</span><span class="sxs-lookup"><span data-stu-id="37124-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="37124-137">배터리 제한 모드를 구성 하려면 **고급 설정** 구성 페이지의 **키오스크 무시** 설정을 Semm (Surface Pro 4 이상)으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![고급 설정 스크린샷](images/semm-bl.png)

### <span data-ttu-id="37124-139">Surface UEFI 관리자 PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="37124-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="37124-140">배터리 제한 기능은 다음 설정을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37124-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="37124-141">**설명**: 배터리 사용 패턴에 대 한 활성 관리 체계</span><span class="sxs-lookup"><span data-stu-id="37124-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="37124-142">**기본값**:</span><span class="sxs-lookup"><span data-stu-id="37124-142">**Default**:</span></span>  `0` 

<span data-ttu-id="37124-143">`1`배터리 용량을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="37124-144">Surface Pro 3 펌웨어 도구 사용</span><span class="sxs-lookup"><span data-stu-id="37124-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="37124-145">배터리 제한 기능은 다음 설정을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37124-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="37124-146">**이름**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="37124-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="37124-147">**설명**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="37124-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="37124-148">**현재 값**:</span><span class="sxs-lookup"><span data-stu-id="37124-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="37124-149">**기본 값**:</span><span class="sxs-lookup"><span data-stu-id="37124-149">**Default Value**:</span></span> `0`

<span data-ttu-id="37124-150">**제안 된 값**:</span><span class="sxs-lookup"><span data-stu-id="37124-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="37124-151">`1`배터리 용량을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="37124-152">이 설정을 구성 하려면 [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37124-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

