---
title: MDT 배포 중 Surface 랩톱 키보드를 사용 하도록 설정 하는 방법
description: MDT를 사용 하 여 Windows 10을 Surface 노트북에 배포 하는 경우 Windows PE 환경에서 사용할 수 있도록 키보드 드라이버를 가져와야 합니다.
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
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834716"
---
# <span data-ttu-id="85b24-104">MDT 배포 중 Surface 랩톱 키보드를 사용 하도록 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="85b24-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="85b24-105">이 문서에서는 MDT (Microsoft 배포 도구 키트)를 사용 하는 배포 접근 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="85b24-106">다른 배포 방법론에도이 정보를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="85b24-107">대부분의 Surface 장치 유형에 서,이 키보드는 LTI (Lite Touch 설치) 중에 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="85b24-108">그러나 Surface 노트북에서는 일부 추가 드라이버를 사용 하 여 키보드를 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="85b24-109">Surface 노트북 (1 Gen) 및 Surface 노트북 2 장치의 경우 LTI의 windows PE (Windows 사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="85b24-110">이 폴더 구조에 대 한 자세한 내용은 [MDT를 사용 하 여 Windows 10 이미지 배포: 5 단계: 드라이버 리포지토리 준비](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85b24-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="85b24-111">현재 드라이버 충돌로 인해 동일한 Windows PE 부팅 인스턴스에서 Surface 랩톱 2 및 Surface 랩톱 3 키보드 드라이버를 추가 하는 것은 지원 되지 않습니다. 대신 별도의 인스턴스를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="85b24-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85b24-112">Windows 10을 S 모드에 설치 되어 있는 Surface 노트북에 Windows 10 이미지를 배포 하는 경우 KB [4032347, windows를 사전 설치 된 windows 10 s 모드의 surface 장치에 배포할 때 발생](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)하는 문제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85b24-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="85b24-113">선택 프로필에 키보드 드라이버를 추가 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="85b24-114">적절 한 위치에서 최신 Surface 랩톱 MSI 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="85b24-115">Surface 노트북 (1 Gen) 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="85b24-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="85b24-116">Surface 노트북 2 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="85b24-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="85b24-117">Intel 프로세서 드라이버 및 펌웨어가 있는 Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="85b24-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="85b24-118">Surface 랩톱 MSI 파일의 내용을 쉽게 찾을 수 있는 폴더에 추출 합니다 (예: c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="85b24-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="85b24-119">콘텐츠를 추출 하려면 관리자 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="85b24-120">배포 워크 벤치를 열고 **배포 공유** 노드 및 배포 공유를 확장 한 다음 **WindowsPEX64** 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![배포 워크 벤치에서 WindowsPEX64 폴더의 위치를 표시 하는 이미지](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="85b24-122">**WindowsPEX64** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **드라이버 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="85b24-123">드라이버 가져오기 마법사의 지침에 따라 드라이버 폴더를 WindowsPEX64 폴더로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="85b24-124">다운로드 한 MSI 패키지를 확인 하 여 형식 및 디렉터리 구조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="85b24-125">디렉터리 구조는 MSI가 해제 된 시점에 따라 SurfacePlatformInstaller (오래 된 MSI 파일) 또는 SurfaceUpdate (최신 MSI 파일)로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="85b24-126">Surface 노트북 (1 Gen)을 지원 하려면 다음 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="85b24-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="85b24-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="85b24-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="85b24-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="85b24-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="85b24-131">또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="85b24-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="85b24-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="85b24-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="85b24-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="85b24-136">Surface 노트북 2를 지원 하려면 다음 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="85b24-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="85b24-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="85b24-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="85b24-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="85b24-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="85b24-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="85b24-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="85b24-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="85b24-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="85b24-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="85b24-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="85b24-144">또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="85b24-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="85b24-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="85b24-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="85b24-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="85b24-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="85b24-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="85b24-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="85b24-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="85b24-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="85b24-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="85b24-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="85b24-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="85b24-152">Intel 프로세서를 사용 하는 Surface 노트북 3을 지원 하려면 다음 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="85b24-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="85b24-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="85b24-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="85b24-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="85b24-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="85b24-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="85b24-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="85b24-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="85b24-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="85b24-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="85b24-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="85b24-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="85b24-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="85b24-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="85b24-161">다음 폴더를 가져오면 Surface 노트북 3 용 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="85b24-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="85b24-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="85b24-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="85b24-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="85b24-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="85b24-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="85b24-165">IclSerialIOUART</span></span>
- <span data-ttu-id="85b24-166">itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-166">itouch</span></span>
- <span data-ttu-id="85b24-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="85b24-167">IclChipset</span></span>
- <span data-ttu-id="85b24-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="85b24-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="85b24-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="85b24-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="85b24-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="85b24-170">ManagementEngine</span></span>
- <span data-ttu-id="85b24-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="85b24-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="85b24-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="85b24-172">SurfaceBattery</span></span>
- <span data-ttu-id="85b24-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="85b24-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="85b24-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="85b24-174">SurfaceHidMini</span></span>
- <span data-ttu-id="85b24-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="85b24-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="85b24-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="85b24-176">SurfaceIntegration</span></span>
- <span data-ttu-id="85b24-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="85b24-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="85b24-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="85b24-178">SurfaceService</span></span>
- <span data-ttu-id="85b24-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="85b24-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="85b24-180">다운로드 한 MSI 패키지를 확인 하 여 형식 및 디렉터리 구조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="85b24-181">디렉터리 구조는 MSI가 해제 된 시점에 따라 SurfacePlatformInstaller (오래 된 MSI 파일) 또는 SurfaceUpdate (최신 MSI 파일)로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="85b24-182">Surface 노트북 (1 Gen)을 지원 하려면 다음 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="85b24-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="85b24-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="85b24-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="85b24-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="85b24-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="85b24-187">또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="85b24-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="85b24-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="85b24-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="85b24-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="85b24-192">Surface 노트북 2를 지원 하려면 다음 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="85b24-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="85b24-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="85b24-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="85b24-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="85b24-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="85b24-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="85b24-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="85b24-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="85b24-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="85b24-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="85b24-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="85b24-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="85b24-200">또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="85b24-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="85b24-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="85b24-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="85b24-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="85b24-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="85b24-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="85b24-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="85b24-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="85b24-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="85b24-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="85b24-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="85b24-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="85b24-208">Intel 프로세서를 사용 하는 Surface 노트북 3을 지원 하려면 다음 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="85b24-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="85b24-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="85b24-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="85b24-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="85b24-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="85b24-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="85b24-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="85b24-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="85b24-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="85b24-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="85b24-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="85b24-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="85b24-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="85b24-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="85b24-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="85b24-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="85b24-217">Intel 프로세서를 사용 하는 Surface 노트북 3의 모델은 Surface 노트북 3입니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="85b24-218">남아 있는 Surface 노트북 드라이버는 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 노트북 3 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="85b24-219">이제 WindowsPEX64 폴더에 가져온 드라이버가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="85b24-220">폴더는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-220">The folder should resemble the following:</span></span>  

   ![배포 워크 벤치의 WindowsPEX64 폴더에 새로 가져온 드라이버를 표시 하는 이미지](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="85b24-222">WindowsPEX64 폴더를 사용 하는 선택 프로필을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="85b24-223">선택 프로필은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-223">The selection profile should resemble the following:</span></span>  

   ![선택 프로필의 일부로 선택 된 WindowsPEX64 폴더를 표시 하는 이미지](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="85b24-225">다음과 같이 새 선택 프로필을 사용 하도록 MDT 배포 공유의 Windows PE 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="85b24-226">**플랫폼용**으로 **x64**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="85b24-227">**선택 프로필**의 경우 새 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="85b24-228">**선택 프로필에서 모든 드라이버 포함을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![MDT 배포 공유의 Windows PE 속성을 보여 주는 이미지](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="85b24-230">선택 프로필 또는 **DriverGroup001** 변수를 사용 하 여 남아 있는 Surface 노트북 드라이버를 구성 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="85b24-231">Surface 노트북 (1 Gen)의 모델은 **Surface 노트북**입니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="85b24-232">남아 있는 Surface 노트북 드라이버는이 목록 뒤에 나오는 그림과 같이 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 랩톱 폴더에 상주해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="85b24-233">Surface 노트북 2의 경우 모델은 **Surface 노트북 2**입니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="85b24-234">남아 있는 Surface 노트북 드라이버는 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 노트북 2 폴더에 상주해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="85b24-235">Intel 프로세서를 사용 하는 Surface 노트북 3의 모델은 Surface 노트북 3입니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="85b24-236">남아 있는 Surface 노트북 드라이버는 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 노트북 3 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![배포 워크 벤치의 Surface 랩톱 폴더에 있는 일반 Surface 노트북 (첫번째 Gen) 드라이버를 표시 하는 이미지](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="85b24-238">새 선택 프로필 및 관련 설정을 사용 하도록 MDT 배포 공유를 구성한 후에는 [mdt를 사용 하 여 Windows 10 이미지 배포: 6 단계: 배포 작업 순서 만들기](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)에 설명 된 대로 배포 프로세스를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b24-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
