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
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247310"
---
# <span data-ttu-id="b08f7-104">MDT 배포 중에 Surface 노트북 키보드를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="b08f7-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="b08f7-105">이 문서에서는 MDT(Microsoft Deployment Toolkit 사용하는 배포 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="b08f7-106">이 정보를 다른 배포 방법에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="b08f7-107">대부분의 Surface 디바이스 유형에서는 LTI(라이트 터치 설치) 중에 키보드가 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="b08f7-108">그러나 Surface 노트북을 사용하려면 몇 가지 추가 드라이버가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="b08f7-109">Surface Laptop(1세대) 및 Surface Laptop 2 장치의 경우 LTI의 Windows PE(Windows 사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="b08f7-110">이 폴더 구조에 대한 자세한 내용은 [MDT를 사용하여 Windows 10 이미지 배포: 5단계:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)드라이버 리포지토리 준비를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b08f7-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="b08f7-111">Windows 10 S 모드가 사전 설치된 Surface 노트북에 Windows 10 이미지를 배포하는 경우, 사전 설치한 Windows 10 S 모드로 Surface 디바이스에 Windows를 배포할 때의 문제인 KB [4032347을](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="b08f7-112">선택 프로필에 키보드 드라이버를 추가하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="b08f7-113">적절한 위치에서 최신 Surface Laptop MSI 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="b08f7-114">Surface 노트북(1세대) 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="b08f7-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="b08f7-115">Surface 노트북 2 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="b08f7-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="b08f7-116">Intel 프로세서 드라이버 및 펌웨어가 있는 Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="b08f7-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="b08f7-117">Surface Laptop MSI 파일의 내용을 쉽게 찾을 수 있는 폴더(예: c:\surface_laptop_drivers)에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="b08f7-118">내용을 추출하기 위해 상승된 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="b08f7-119">Deployment Workbench를 열고 **배포 공유** 노드 및 배포 공유를 확장한 다음 **WindowsPEX64 폴더로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Deployment Workbench에서 WindowsPEX64 폴더의 위치를 표시하는 이미지](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="b08f7-121">**WindowsPEX64** 폴더를 마우스 오른쪽 단추로 클릭하고 드라이버 **가져오기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b08f7-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="b08f7-122">드라이버 가져오기 마법사의 지침에 따라 드라이버 폴더를 WindowsPEX64 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="b08f7-123">다운로드한 MSI 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="b08f7-124">디렉터리 구조는 MSI가 릴리스된 때에 따라 SurfacePlatformInstaller(이전 MSI 파일) 또는 SurfaceUpdate(새 MSI 파일)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="b08f7-125">Surface 노트북(1세대)을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="b08f7-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="b08f7-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="b08f7-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="b08f7-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="b08f7-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="b08f7-130">또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="b08f7-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="b08f7-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="b08f7-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="b08f7-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="b08f7-135">Surface Laptop 2를 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="b08f7-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="b08f7-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="b08f7-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="b08f7-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="b08f7-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="b08f7-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="b08f7-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="b08f7-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="b08f7-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="b08f7-143">또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="b08f7-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="b08f7-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="b08f7-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="b08f7-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b08f7-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="b08f7-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b08f7-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="b08f7-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b08f7-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="b08f7-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="b08f7-151">Intel 프로세서를 통해 Surface Laptop 3을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="b08f7-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="b08f7-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="b08f7-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="b08f7-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="b08f7-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b08f7-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="b08f7-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b08f7-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="b08f7-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b08f7-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="b08f7-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="b08f7-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="b08f7-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="b08f7-160">다음 폴더를 가져오면 Surface Laptop 3의 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="b08f7-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="b08f7-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="b08f7-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="b08f7-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b08f7-164">IclSerialIOUART</span></span>
- <span data-ttu-id="b08f7-165">itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-165">itouch</span></span>
- <span data-ttu-id="b08f7-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="b08f7-166">IclChipset</span></span>
- <span data-ttu-id="b08f7-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="b08f7-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="b08f7-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="b08f7-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="b08f7-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="b08f7-169">ManagementEngine</span></span>
- <span data-ttu-id="b08f7-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="b08f7-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="b08f7-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="b08f7-171">SurfaceBattery</span></span>
- <span data-ttu-id="b08f7-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="b08f7-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="b08f7-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b08f7-173">SurfaceHidMini</span></span>
- <span data-ttu-id="b08f7-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="b08f7-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="b08f7-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="b08f7-175">SurfaceIntegration</span></span>
- <span data-ttu-id="b08f7-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b08f7-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="b08f7-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="b08f7-177">SurfaceService</span></span>
- <span data-ttu-id="b08f7-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="b08f7-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="b08f7-179">다운로드한 MSI 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="b08f7-180">디렉터리 구조는 MSI가 릴리스된 때에 따라 SurfacePlatformInstaller(이전 MSI 파일) 또는 SurfaceUpdate(새 MSI 파일)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="b08f7-181">Surface 노트북(1세대)을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="b08f7-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="b08f7-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="b08f7-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="b08f7-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="b08f7-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="b08f7-186">또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="b08f7-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b08f7-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="b08f7-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="b08f7-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="b08f7-191">Surface Laptop 2를 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="b08f7-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="b08f7-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="b08f7-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="b08f7-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b08f7-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="b08f7-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="b08f7-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="b08f7-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="b08f7-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="b08f7-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="b08f7-199">또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="b08f7-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b08f7-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="b08f7-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="b08f7-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b08f7-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="b08f7-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b08f7-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="b08f7-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b08f7-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="b08f7-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="b08f7-207">Intel 프로세서를 통해 Surface Laptop 3을 지원하기 위해 다음 폴더를 가져오십시오.</span><span class="sxs-lookup"><span data-stu-id="b08f7-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="b08f7-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b08f7-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="b08f7-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b08f7-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="b08f7-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b08f7-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="b08f7-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b08f7-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="b08f7-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b08f7-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="b08f7-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b08f7-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="b08f7-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="b08f7-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="b08f7-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="b08f7-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="b08f7-216">Intel 프로세서가 탑재된 Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="b08f7-217">나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="b08f7-218">WindowsPEX64 폴더에 가져온 드라이버가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="b08f7-219">폴더는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-219">The folder should resemble the following:</span></span>  

   ![Deployment Workbench의 WindowsPEX64 폴더에 새로 가져온 드라이버를 표시하는 이미지](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="b08f7-221">WindowsPEX64 폴더를 사용하는 선택 프로필을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="b08f7-222">선택 프로필은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-222">The selection profile should resemble the following:</span></span>  

   ![선택 프로필의 일부로 선택된 WindowsPEX64 폴더를 표시하는 이미지](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="b08f7-224">다음과 같이 새 선택 프로필을 사용하도록 MDT 배포 공유의 Windows PE 속성을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="b08f7-225">플랫폼의 **경우** **x64를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b08f7-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="b08f7-226">선택 **프로필의 경우**새 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="b08f7-227">선택 **프로필의 모든 드라이버 포함을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b08f7-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![MDT 배포 공유의 Windows PE 속성을 표시하는 이미지](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="b08f7-229">선택 프로필 또는 **DriverGroup001** 변수를 사용하여 나머지 Surface 노트북 드라이버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="b08f7-230">Surface 노트북(1세대)의 경우 모델이 **Surface 노트북입니다.**</span><span class="sxs-lookup"><span data-stu-id="b08f7-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="b08f7-231">나머지 Surface 노트북 드라이버는 이 목록 다음 그림과 같이 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 폴더에 상주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="b08f7-232">Surface 노트북 2의 경우 모델이 **Surface Laptop 2입니다.**</span><span class="sxs-lookup"><span data-stu-id="b08f7-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="b08f7-233">나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 2 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="b08f7-234">Intel 프로세서가 탑재된 Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="b08f7-235">나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Deployment Workbench의 Surface Laptop 폴더에 있는 일반 Surface 노트북(1세대) 드라이버를 보여 주는 이미지](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="b08f7-237">새 선택 프로필 및 관련 설정을 사용하기 위해 MDT 배포 공유를 구성한 후 [MDT를 사용하여 Windows 10 이미지 배포: 6단계:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)배포 작업 순서 만들기에 설명된대로 배포 프로세스를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="b08f7-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
