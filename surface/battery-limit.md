---
title: 배터리 제한 설정(Surface)
description: 배터리 제한은 Surface 디바이스 배터리가 충전되는 방법을 변경하고 수명을 연장하는 UEFI 설정입니다.
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
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271145"
---
# <span data-ttu-id="2f2f1-103">배터리 제한 설정</span><span class="sxs-lookup"><span data-stu-id="2f2f1-103">Battery Limit setting</span></span>

<span data-ttu-id="2f2f1-104">배터리 제한 옵션은 Surface 디바이스 배터리가 충전되는 방법을 변경하고 수명을 연장하는 UEFI 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="2f2f1-105">이 설정은 디바이스가 계속해서 전원에 연결된 경우(예: 디바이스가 키오스크 솔루션에 통합된 경우)에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="2f2f1-106">배터리 제한 작동 방식</span><span class="sxs-lookup"><span data-stu-id="2f2f1-106">How Battery Limit works</span></span>

<span data-ttu-id="2f2f1-107">디바이스를 배터리 제한으로 설정하면 디바이스 배터리를 충전하기 위한 프로토콜이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="2f2f1-108">배터리 한도를 사용하도록 설정하면 배터리 충전이 최대 용량의 50%로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="2f2f1-109">Windows에서 보고되는 요금 수준에는 이 제한이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="2f2f1-110">따라서 배터리가 최대 50%까지 충전되어 이 제한을 초과하여 충전되지 않는 것으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="2f2f1-111">장치가 50% 충전을 초과하는 동안 배터리 제한을 사용하도록 설정하면 배터리 아이콘에 장치가 연결되어 있지만 장치가 최대 충전 용량의 50%에 도달할 때까지 전원이 방전된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="2f2f1-112">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="2f2f1-112">Supported devices</span></span>

<span data-ttu-id="2f2f1-113">배터리 제한 UEFI 설정은 Surface Pro 7+, Surface Pro 7 및 Surface Laptop 3을 비롯한 최신 Surface 디바이스에 기본으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="2f2f1-114">이전 디바이스에는 Windows 업데이트 또는 Surface 지원 사이트의 MSI 드라이버 및 펌웨어 패키지를 통해 사용할 수 있는 [Surface UEFI](manage-surface-driver-and-firmware-updates.md)펌웨어 [업데이트가 필요합니다.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)</span><span class="sxs-lookup"><span data-stu-id="2f2f1-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="2f2f1-115">지원되는 각 장치에 필요한 특정 Surface UEFI 버전에 대해 장시간 연결해야 하는 Surface 디바이스에 대해 ["배터리 제한"을](https://support.microsoft.com/help/4464941) 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="2f2f1-116">Surface UEFI에서 배터리 제한 사용(Surface Pro 4 이상)</span><span class="sxs-lookup"><span data-stu-id="2f2f1-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="2f2f1-117">Surface UEFI 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면**전원 + Vol Up).**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="2f2f1-118">부팅 **구성을 선택한**다음 \*\*\*\* 고급 옵션에서 배터리 **제한** 모드를 으로 **전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![배터리 제한 고급 옵션](images/enable-bl.png) 

## <span data-ttu-id="2f2f1-120">Surface Go 및 Surface Go 2에서 배터리 제한 사용</span><span class="sxs-lookup"><span data-stu-id="2f2f1-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="2f2f1-121">Surface UEFI로 부팅하여 Surface 배터리 제한 설정을 구성할 수 있습니다(디바이스를 끄면**전원 + Vol Up).**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="2f2f1-122">부팅 **구성을 선택한**다음 **키오스크**모드에서 슬라이더를 오른쪽으로 이동하여 배터리 제한을 사용으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Surface Go의 키오스크 모드 배터리 제한](images/go-batterylimit.png) 

## <span data-ttu-id="2f2f1-124">Surface UEFI에서 배터리 제한 사용(Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="2f2f1-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="2f2f1-125">Surface UEFI 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면**전원 + Vol Up).**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="2f2f1-126">**키오스크**모드를 선택하고 배터리 **제한을**선택한 다음 사용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![고급 옵션 스크린샷](images/enable-bl-sp3.png) 

![고급 옵션](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="2f2f1-129">Surface Enterprise Management Mode(SEMM) 또는 Surface Pro 3 펌웨어 PowerShell 스크립트를 사용하여 배터리 제한 사용</span><span class="sxs-lookup"><span data-stu-id="2f2f1-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="2f2f1-130">Surface UEFI 배터리 제한은 다음 방법을 통해 구성에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="2f2f1-131">Surface Pro 4 이상</span><span class="sxs-lookup"><span data-stu-id="2f2f1-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="2f2f1-132">Microsoft Surface UEFI 구성기</span><span class="sxs-lookup"><span data-stu-id="2f2f1-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="2f2f1-133">IT용 Surface 도구의 [Surface](https://www.microsoft.com/download/details.aspx?id=46703) UEFI 관리자 Powershell 스크립트(SEMM_Powershell.zip)</span><span class="sxs-lookup"><span data-stu-id="2f2f1-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="2f2f1-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="2f2f1-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="2f2f1-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="2f2f1-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="2f2f1-136">Microsoft Surface UEFI 구성기 사용</span><span class="sxs-lookup"><span data-stu-id="2f2f1-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="2f2f1-137">배터리 제한 모드를 구성하려면 SEMM(Surface Pro **4 이상)의** 고급 설정 구성 페이지에서 키오스크 오버라이드 설정을 설정하십시오. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2f2f1-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![고급 설정 스크린샷](images/semm-bl.png)

### <span data-ttu-id="2f2f1-139">Surface UEFI 관리자 PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="2f2f1-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="2f2f1-140">배터리 제한 기능은 다음 설정을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="2f2f1-141">**설명:** 배터리 사용 패턴에 대한 활성 관리 스키마</span><span class="sxs-lookup"><span data-stu-id="2f2f1-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="2f2f1-142">**기본값:**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-142">**Default**:</span></span>  `0` 

<span data-ttu-id="2f2f1-143">배터리 `1` 제한을 사용하도록 설정하려면 이 설정을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="2f2f1-144">Surface Pro 3 펌웨어 도구 사용</span><span class="sxs-lookup"><span data-stu-id="2f2f1-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="2f2f1-145">배터리 제한 기능은 다음 설정을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="2f2f1-146">**이름:** BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="2f2f1-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="2f2f1-147">**설명:** BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="2f2f1-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="2f2f1-148">**현재 값:**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="2f2f1-149">**기본값:**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-149">**Default Value**:</span></span> `0`

<span data-ttu-id="2f2f1-150">**제안된 값:**</span><span class="sxs-lookup"><span data-stu-id="2f2f1-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="2f2f1-151">배터리 `1` 제한을 사용하도록 설정하려면 이 설정을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="2f2f1-152">이 설정을 구성하려면 [ 다음을 ](https://www.microsoft.com/download/details.aspx?id=46703)SP3_Firmware_Powershell_Scripts.zip.</span><span class="sxs-lookup"><span data-stu-id="2f2f1-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

