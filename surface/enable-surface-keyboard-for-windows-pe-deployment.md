---
title: MDT 배포 중에 Surface 노트북 키보드를 사용하도록 설정하는 방법
description: MDT를 사용하여 Surface 노트북에 Windows 10을 배포하는 경우 Windows PE 환경에서 사용할 키보드 드라이버를 가져와야 합니다.
keywords: windows 10 surface, 자동화, 사용자 지정, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312064"
---
# <span data-ttu-id="2c6d0-104">MDT 배포 중에 Surface 노트북 키보드를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="2c6d0-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="2c6d0-105">이 문서에서는 MDT(Microsoft Deployment Toolkit)를 사용하는 배포 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="2c6d0-106">이 정보를 다른 배포 방법에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="2c6d0-107">대부분의 Surface 디바이스 유형에서는 LTI(라이트 터치 설치) 중에 키보드가 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="2c6d0-108">그러나 Surface 노트북을 사용하려면 몇 가지 추가 드라이버가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="2c6d0-109">Surface Laptop(1세대) 및 Surface Laptop 2 장치의 경우 LTI의 Windows PE(Windows 사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="2c6d0-110">이 폴더 구조에 대한 자세한 내용은 [MDT를 사용하여 Windows 10 이미지 배포: 5단계:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)드라이버 리포지토리 준비를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="2c6d0-111">동일한 Windows PE 부팅 인스턴스에서 Surface Laptop 2 및 Surface Laptop 3용 키보드 드라이버를 사용하는 경우 키보드 또는 터치 패드가 Windows PE에서 작동하지 않는 경우 펌웨어를 수동으로 다시 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="2c6d0-112">전원 단추를 30초 동안 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="2c6d0-113">PSU(전원 공급 장치)에 연결되어 있는 경우 전원 단추를 누르고 PSU 코드 끝에 불이 잠시 꺼질 때까지 전원 단추를 누르고 다시 니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c6d0-114">Windows 10 S 모드가 사전 설치된 Surface 노트북에 Windows 10 이미지를 배포하는 경우 사전 설치한 Windows 10 S 모드로 Surface 디바이스에 Windows를 배포할 때의 문제인 KB [4032347을](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="2c6d0-115">선택 프로필에 키보드 드라이버를 추가하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="2c6d0-116">적절한 위치에서 최신 Surface Laptop MSI 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="2c6d0-117">Surface 노트북(1세대) 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="2c6d0-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="2c6d0-118">Surface 노트북 2 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="2c6d0-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="2c6d0-119">Intel 프로세서 드라이버 및 펌웨어가 있는 Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="2c6d0-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="2c6d0-120">Surface Laptop MSI 파일의 내용을 쉽게 찾을 수 있는 폴더(예: c:\surface_laptop_drivers)에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="2c6d0-121">내용을 추출하기 위해 상승된 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="2c6d0-122">Deployment Workbench를 열고 **배포 공유** 노드 및 배포 공유를 확장한 다음 **WindowsPEX64 폴더로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Deployment Workbench에서 WindowsPEX64 폴더의 위치를 표시하는 이미지](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="2c6d0-124">**WindowsPEX64** 폴더를 마우스 오른쪽 단추로 클릭하고 드라이버 **가져오기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c6d0-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="2c6d0-125">드라이버 가져오기 마법사의 지침에 따라 드라이버 폴더를 WindowsPEX64 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2c6d0-126">다운로드한 MSI 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="2c6d0-127">디렉터리 구조는 MSI가 릴리스된 때에 따라 SurfacePlatformInstaller(이전 MSI 파일) 또는 SurfaceUpdate(새 MSI 파일)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="2c6d0-128">Surface 노트북(1세대)을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="2c6d0-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="2c6d0-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="2c6d0-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="2c6d0-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2c6d0-133">또는 "SurfaceUpdate"로 시작되는 새 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2c6d0-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="2c6d0-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2c6d0-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2c6d0-138">Surface Laptop 2를 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="2c6d0-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="2c6d0-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="2c6d0-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="2c6d0-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="2c6d0-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="2c6d0-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="2c6d0-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="2c6d0-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2c6d0-146">또는 "SurfaceUpdate"로 시작되는 새 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2c6d0-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="2c6d0-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="2c6d0-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2c6d0-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2c6d0-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2c6d0-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2c6d0-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2c6d0-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2c6d0-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="2c6d0-154">Intel 프로세서를 통해 Surface Laptop 3을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="2c6d0-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2c6d0-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="2c6d0-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2c6d0-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2c6d0-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2c6d0-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2c6d0-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2c6d0-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2c6d0-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="2c6d0-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="2c6d0-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2c6d0-163">다음 폴더를 가져오면 Surface Laptop 3의 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="2c6d0-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2c6d0-165">SerialIOI2C</span></span>
    - <span data-ttu-id="2c6d0-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-166">SerialIOSPI</span></span>
    - <span data-ttu-id="2c6d0-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-167">SerialIOUART</span></span>
    - <span data-ttu-id="2c6d0-168">itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-168">itouch</span></span>
    - <span data-ttu-id="2c6d0-169">칩셋</span><span class="sxs-lookup"><span data-stu-id="2c6d0-169">Chipset</span></span>
    - <span data-ttu-id="2c6d0-170">ChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="2c6d0-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="2c6d0-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="2c6d0-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="2c6d0-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="2c6d0-172">ManagementEngine</span></span>
    - <span data-ttu-id="2c6d0-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="2c6d0-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="2c6d0-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="2c6d0-174">SurfaceBattery</span></span>
    - <span data-ttu-id="2c6d0-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="2c6d0-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="2c6d0-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2c6d0-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="2c6d0-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="2c6d0-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="2c6d0-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="2c6d0-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="2c6d0-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2c6d0-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="2c6d0-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="2c6d0-180">SurfaceService</span></span>
    - <span data-ttu-id="2c6d0-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="2c6d0-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="2c6d0-182">다운로드한 MSI 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="2c6d0-183">디렉터리 구조는 MSI가 릴리스된 때에 따라 SurfacePlatformInstaller(이전 MSI 파일) 또는 SurfaceUpdate(새 MSI 파일)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="2c6d0-184">Surface 노트북(1세대)을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="2c6d0-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="2c6d0-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="2c6d0-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2c6d0-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2c6d0-189">또는 "SurfaceUpdate"로 시작되는 새 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2c6d0-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="2c6d0-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2c6d0-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2c6d0-194">Surface Laptop 2를 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="2c6d0-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="2c6d0-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="2c6d0-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="2c6d0-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="2c6d0-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="2c6d0-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="2c6d0-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="2c6d0-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="2c6d0-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="2c6d0-202">또는 "SurfaceUpdate"로 시작되는 새 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="2c6d0-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2c6d0-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="2c6d0-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2c6d0-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2c6d0-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2c6d0-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2c6d0-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2c6d0-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2c6d0-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="2c6d0-210">Intel 프로세서가 있는 Surface Laptop 3을 지원하기 위해 다음 폴더를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="2c6d0-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="2c6d0-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="2c6d0-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="2c6d0-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="2c6d0-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="2c6d0-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="2c6d0-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="2c6d0-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="2c6d0-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="2c6d0-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="2c6d0-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="2c6d0-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="2c6d0-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="2c6d0-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="2c6d0-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="2c6d0-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="2c6d0-219">Intel 프로세서가 탑재된 Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="2c6d0-220">나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="2c6d0-221">WindowsPEX64 폴더에 가져온 드라이버가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="2c6d0-222">폴더는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-222">The folder should resemble the following:</span></span>  

   ![Deployment Workbench의 WindowsPEX64 폴더에 새로 가져온 드라이버를 표시하는 이미지](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="2c6d0-224">WindowsPEX64 폴더를 사용하는 선택 프로필을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="2c6d0-225">선택 프로필은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-225">The selection profile should resemble the following:</span></span>  

   ![선택 프로필의 일부로 선택된 WindowsPEX64 폴더를 표시하는 이미지](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="2c6d0-227">다음과 같이 새 선택 프로필을 사용하도록 MDT 배포 공유의 Windows PE 속성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="2c6d0-228">플랫폼의 **경우** **x64를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c6d0-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="2c6d0-229">선택 **프로필의 경우**새 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="2c6d0-230">선택 **프로필의 모든 드라이버 포함을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2c6d0-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![MDT 배포 공유의 Windows PE 속성을 표시하는 이미지](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="2c6d0-232">선택 프로필 또는 **DriverGroup001** 변수를 사용하여 나머지 Surface 노트북 드라이버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="2c6d0-233">Surface 노트북(1세대)의 경우 모델이 **Surface 노트북입니다.**</span><span class="sxs-lookup"><span data-stu-id="2c6d0-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="2c6d0-234">나머지 Surface 노트북 드라이버는 이 목록 다음 그림과 같이 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 폴더에 상주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="2c6d0-235">Surface 노트북 2의 경우 모델이 **Surface Laptop 2입니다.**</span><span class="sxs-lookup"><span data-stu-id="2c6d0-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="2c6d0-236">나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 2 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="2c6d0-237">Intel 프로세서가 탑재된 Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="2c6d0-238">나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Deployment Workbench의 Surface Laptop 폴더에 있는 일반 Surface 노트북(1세대) 드라이버를 보여 주는 이미지](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="2c6d0-240">새 선택 프로필 및 관련 설정을 사용하기 위해 MDT 배포 공유를 구성한 후 [MDT를 사용하여 Windows 10 이미지 배포: 6단계:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)배포 작업 순서 만들기에 설명된대로 배포 프로세스를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6d0-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
