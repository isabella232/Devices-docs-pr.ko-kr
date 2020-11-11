---
title: Surface Pro 3의 고급 UEFI 보안 기능(Surface)
description: 이 문서에서는 v3.11.760.0 UEFI 업데이트를 설치하고 구성하여 Surface Pro 3 디바이스에 대한 추가 보안 옵션을 사용하도록 설정하는 방법에 대해 설명합니다.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: 보안, 기능, 구성, 하드웨어, 디바이스, 사용자 지정, 스크립트, 업데이트
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163183"
---
# <span data-ttu-id="766e4-104">Surface Pro 3의 고급 UEFI 보안 기능</span><span class="sxs-lookup"><span data-stu-id="766e4-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="766e4-105">이 문서에서는 v3.11.760.0 UEFI 업데이트를 설치하고 구성하여 Surface Pro 3 디바이스에 대한 추가 보안 옵션을 사용하도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="766e4-106">Surface 디바이스 보안에 대해 좀 더 세부적으로 제어할 수 있도록 v3.11.760.0 UEFI 업데이트에서는 사용자가 특정 하드웨어 디바이스를 사용하지 않도록 설정하거나 이 디바이스에서 시작하지 않게 할 수 있는 추가 보안 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="766e4-107">디바이스에 UEFI 업데이트를 설치하고 나면 스크립트를 실행하여 수동 또는 자동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="766e4-108">수동으로 UEFI 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="766e4-108">Manually install the UEFI update</span></span>


<span data-ttu-id="766e4-109">Surface 디바이스의 고급 보안 기능을 구성하려면 먼저 v3.11.760.0 UEFI 업데이트를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="766e4-110">이 업데이트는 Windows 업데이트에서 업데이트를 받을 경우 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="766e4-111">Windows 업데이트를 사용하여 자동으로 업데이트하도록 Windows를 구성하는 방법에 대한 자세한 내용은 [Windows의 자동 업데이트 구성 및 사용 방법](https://support.microsoft.com/kb/306525)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="766e4-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="766e4-112">Surface Pro 3에서 UEFI를 업데이트하기 위해 Surface Pro 3 펌웨어 및 드라이버 팩의 일부로 Surface UEFI 업데이트를 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="766e4-113">이러한 펌웨어 및 드라이버 팩은 Microsoft 다운로드 센터의 [Surface Pro 3 페이지](https://www.microsoft.com/download/details.aspx?id=38826)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="766e4-114">펌웨어 및 드라이버 팩에 대한 자세한 내용은 [Surface 디바이스의 최신 펌웨어 및 드라이버 다운로드](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="766e4-115">이러한 펌웨어 및 드라이버 팩은 자체 포함된 Windows Installer(.msi) 및 보관(.zip) 형식으로 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="766e4-116">이러한 두 가지 형식과, 이 형식을 사용하여 드라이버를 업데이트하는 방법에 대한 자세한 내용은 [Surface 드라이버 및 펌웨어 업데이트 관리](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="766e4-117">수동으로 추가 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="766e4-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="766e4-118">Surface 디바이스에서 펌웨어 설정을 시작하려면 먼저 디바이스 전원이 꺼진 상태에서 **볼륨 크게** 단추를 길게 누르고, **전원** 단추를 눌렀다가 놓은 다음 디바이스가 부팅하기 시작하면 **볼륨 크게** 단추를 놓으세요.</span><span class="sxs-lookup"><span data-stu-id="766e4-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="766e4-119">Surface 디바이스에 v3.11.760.0 UEFI 업데이트를 설치하고 나면 이름이 **고급 디바이스 보안**으로 지정된 추가 UEFI 메뉴를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="766e4-120">이 메뉴를 클릭하면 다음 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="766e4-121">옵션</span><span class="sxs-lookup"><span data-stu-id="766e4-121">Option</span></span>         | <span data-ttu-id="766e4-122">설명</span><span class="sxs-lookup"><span data-stu-id="766e4-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="766e4-123">사용 가능한 설정(기본값은 굵게 표시)</span><span class="sxs-lookup"><span data-stu-id="766e4-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="766e4-124">네트워크 부팅</span><span class="sxs-lookup"><span data-stu-id="766e4-124">Network Boot</span></span>   | <span data-ttu-id="766e4-125">네트워크에서 부팅할 수 있는 Surface 디바이스 기능을 사용하거나 사용하지 않도록 설정합니다(PXE 부팅이라고도 함).</span><span class="sxs-lookup"><span data-stu-id="766e4-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="766e4-126">**사용**,부팅 불가능</span><span class="sxs-lookup"><span data-stu-id="766e4-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="766e4-127">측면 USB</span><span class="sxs-lookup"><span data-stu-id="766e4-127">Side USB</span></span>       | <span data-ttu-id="766e4-128">Surface 디바이스 측면에 있는 USB 포트를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="766e4-129">또한 부팅은 허용되지 않은 상태로 USB 포트를 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="766e4-130">**사용**, 부팅 불가능, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="766e4-131">도킹 포트</span><span class="sxs-lookup"><span data-stu-id="766e4-131">Docking Port</span></span>   | <span data-ttu-id="766e4-132">Surface 도킹 스테이션에서 포트를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="766e4-133">또한 도킹 스테이션의 USB 또는 이더넷 포트에서 부팅은 차단한 상태로 도킹 포트를 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="766e4-134">**사용**, 부팅 불가능, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="766e4-135">전면 카메라</span><span class="sxs-lookup"><span data-stu-id="766e4-135">Front Camera</span></span>   | <span data-ttu-id="766e4-136">Surface 디바이스의 앞면 카메라를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="766e4-137">**사용**, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="766e4-138">후면 카메라</span><span class="sxs-lookup"><span data-stu-id="766e4-138">Rear Camera</span></span>    | <span data-ttu-id="766e4-139">Surface 디바이스의 후면 카메라를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="766e4-140">**사용**, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="766e4-141">온보드 오디오</span><span class="sxs-lookup"><span data-stu-id="766e4-141">On Board Audio</span></span> | <span data-ttu-id="766e4-142">Surface 디바이스에서 오디오를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="766e4-143">**사용**, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="766e4-144">microSD</span><span class="sxs-lookup"><span data-stu-id="766e4-144">microSD</span></span>        | <span data-ttu-id="766e4-145">Surface 디바이스에서 microSD 슬롯을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="766e4-146">**사용**, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="766e4-147">WiFi</span><span class="sxs-lookup"><span data-stu-id="766e4-147">WiFi</span></span>           | <span data-ttu-id="766e4-148">Surface 디바이스에서 기본 제공 Wi-Fi 송수신 디바이스를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="766e4-149">이 옵션을 통해 Bluetooth도 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="766e4-150">**사용**, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="766e4-151">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="766e4-151">Bluetooth</span></span>      | <span data-ttu-id="766e4-152">Surface 디바이스에서 기본 제공 Bluetooth 송수신 디바이스를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="766e4-153">**사용**, 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="766e4-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="766e4-154">추가 보안 설정 자동화</span><span class="sxs-lookup"><span data-stu-id="766e4-154">Automate additional security settings</span></span>


<span data-ttu-id="766e4-155">관리자 권한이 있는 IT 전문가로서 Microsoft 다운로드 센터에서 사용할 수 있는 [Surface Pro 3 펌웨어 도구(476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038)를 활용하여 UEFI 설정 구성을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="766e4-156">이 도구로 사용자 지정 응용 프로그램 또는 스크립트에서 호출할 수 있는 .NET 어셈블리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="766e4-157">필수 조건</span><span class="sxs-lookup"><span data-stu-id="766e4-157">Prerequisites</span></span>**

-   <span data-ttu-id="766e4-158">아래 샘플 스크립트는 앞에서 언급한 확장을 활용하며, 관리 중인 디바이스에 도구를 설치했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="766e4-159">스크립트는 관리자 권한으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="766e4-160">디지털 서명되지 않은 샘플 스크립트를 실행하기 전에 Windows PowerShell 명령 [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx)를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="766e4-161">샘플 스크립트</span><span class="sxs-lookup"><span data-stu-id="766e4-161">Sample scripts</span></span>**

> [!NOTE]
> <span data-ttu-id="766e4-162">아래 샘플 스크립트에서 사용되는 UEFI 암호는 일반 텍스트로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-162">The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="766e4-163">보호되는 위치에 스크립트를 저장하고 제어된 환경에서 스크립트를 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="766e4-164">구성 가능한 옵션을 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-164">Show all configurable options:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

<span data-ttu-id="766e4-165">UEFI 암호를 설정 또는 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-165">Set or change UEFI password:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="766e4-166">제안된 변경의 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-166">Check status of proposed changes:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

<span data-ttu-id="766e4-167">UEFI를 기본값으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="766e4-167">Revert UEFI to default values:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

<span data-ttu-id="766e4-168">상태 코드 해석</span><span class="sxs-lookup"><span data-stu-id="766e4-168">Status code interpretation</span></span>

-   <span data-ttu-id="766e4-169">00 - 제안된 업데이트 성공</span><span class="sxs-lookup"><span data-stu-id="766e4-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="766e4-170">02 - 제안된 값 중 하나에 잘못된 문자 포함</span><span class="sxs-lookup"><span data-stu-id="766e4-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="766e4-171">03 - 제안되었으나 인식되지 않게 설정된 값 있음</span><span class="sxs-lookup"><span data-stu-id="766e4-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="766e4-172">0F - 잠금 해제 암호가 현재 설정된 암호화 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="766e4-172">0F - The unlock password did not match currently set password</span></span>

 
