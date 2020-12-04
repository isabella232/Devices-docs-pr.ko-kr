---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: 이 문서에서는 Surface Hub 2의 Windows 10 Team에서 Windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 방법을 설명합니다.
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 01c5c8a5c6b9f7ed657829fe792fc9eecd1facb5
ms.sourcegitcommit: 5d02cca9ca8c0a252798c2fc0a89dbda81911c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195403"
---
# <span data-ttu-id="42592-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="42592-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="42592-105">Surface Hub 2S는 Windows 10 Team과 함께 사전 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-105">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="42592-106">이 사용자 지정된 Windows 10 버전은 회의실 환경에서 공동 작업을 용이하게 하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-106">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="42592-107">이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용하기 위해 Windows 10 Pro 또는 Enterprise를 실행하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="42592-108">일반적인 업그레이드 또는 마이그레이션과 달리 이 프로세스에서는 이 문서에 설명된 징계 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="42592-109">계속하기 [전에 솔루션](#solution-components) 구성 요소 및 마이그레이션 및 [설치](#migration-and-installation-workflow-summary) 워크플로를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="42592-110">Windows 10 Pro 또는 Enterprise를 설치할 때 기존 Windows 10 Team 라이선스와는 별개인 새 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-110">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="42592-111">별도의 PC 및 다운로드 가능한 도구 Surface UEFI 구성 도구를 사용하여 Windows 10 Team에서 *마이그레이션을 시작하세요.*</span><span class="sxs-lookup"><span data-stu-id="42592-111">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="42592-112">이 도구를 사용하여 Surface Hub 2S에 적용하는 새 UEFI 설정이 포함된 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-112">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="42592-113">Surface UEFI 구성기는 Surface SEMM(엔터프라이즈 관리 모드)에 대한 인터페이스로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-113">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="42592-114">회사 환경의 Surface 디바이스에서 펌웨어 설정을 중앙에서 쉽게 관리하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-114">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="42592-115">자세한 내용은 Microsoft <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-115">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft SEMM documentation</span></span></a>
 

## <span data-ttu-id="42592-116">솔루션 구성 요소</span><span class="sxs-lookup"><span data-stu-id="42592-116">Solution components</span></span>

- <span data-ttu-id="42592-117">Windows 10 Team 운영 체제를 실행하는 Surface Hub 2S 장치</span><span class="sxs-lookup"><span data-stu-id="42592-117">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="42592-118">Windows 10을 실행하는 장치 분리</span><span class="sxs-lookup"><span data-stu-id="42592-118">Separate device running Windows 10</span></span>
- <span data-ttu-id="42592-119">SEMM 패키지를 만들기 위한 Surface UEFI 구성기 도구</span><span class="sxs-lookup"><span data-stu-id="42592-119">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="42592-120">Windows 10 Pro 또는 Enterprise OS 이미지, 버전 1903 이상</span><span class="sxs-lookup"><span data-stu-id="42592-120">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="42592-121">16GB의 저장소가 있는 USB 드라이브 2개, FAT32 형식</span><span class="sxs-lookup"><span data-stu-id="42592-121">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="42592-122">Surface Hub 2(MSI) 파일의 Windows 10 Pro 및 엔터프라이즈 OS용 Microsoft Windows Installer 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="42592-122">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="42592-123">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="42592-123">Internet connection</span></span>
- <span data-ttu-id="42592-124">이미징 솔루션(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="42592-124">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="42592-125">마이그레이션 및 설치 워크플로 요약</span><span class="sxs-lookup"><span data-stu-id="42592-125">Migration and installation workflow summary</span></span>

| <span data-ttu-id="42592-126">단계</span><span class="sxs-lookup"><span data-stu-id="42592-126">Step</span></span>  | <span data-ttu-id="42592-127">작업</span><span class="sxs-lookup"><span data-stu-id="42592-127">Action</span></span>                                                                                                 | <span data-ttu-id="42592-128">요약</span><span class="sxs-lookup"><span data-stu-id="42592-128">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="42592-129">1</span><span class="sxs-lookup"><span data-stu-id="42592-129">1</span></span> | [<span data-ttu-id="42592-130">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-130">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="42592-131">UEFI 버전이 694.2938.768.0 이상인지 확인</span><span class="sxs-lookup"><span data-stu-id="42592-131">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="42592-132">2</span><span class="sxs-lookup"><span data-stu-id="42592-132">2</span></span> | [<span data-ttu-id="42592-133">Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-133">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="42592-134"><a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **IT용 Surface 도구 페이지에서** </a> 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-134">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">**Surface Tools for IT** page</a>, select **Download**.</span></span> <span data-ttu-id="42592-135">그런 다음 **Surface UEFI 구성 프로그램을 선택하고 다운로드합니다. MSI 파일을** 설치하고 별도 PC에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-135">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="42592-136">Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-136">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a> <span data-ttu-id="42592-137">5단계에서 사용하기 위해 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-137">Save it for use in step 5.</span></span> |
| <span data-ttu-id="42592-138">3</span><span class="sxs-lookup"><span data-stu-id="42592-138">3</span></span> | [<span data-ttu-id="42592-139">SEMM 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-139">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="42592-140">Surface UEFI 구성기 실행에 필요한 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-140">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="42592-141">또는 현재 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-141">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="42592-142">4</span><span class="sxs-lookup"><span data-stu-id="42592-142">4</span></span> | [<span data-ttu-id="42592-143">SEMM 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-143">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="42592-144">Surface Hub 2S에서 적용해야 하는 구성 파일이 포함된 USB 드라이브에 SEMM 패키지를 만들 수 있는 Surface UEFI 구성을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="42592-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="42592-145">이러한 SEMM 패키지 파일을 PC의 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-145">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="42592-146">5</span><span class="sxs-lookup"><span data-stu-id="42592-146">5</span></span> | [<span data-ttu-id="42592-147">Surface Hub 2에서 Windows 10 Pro 및 Enterprise OS용 Windows 10 이미지, SEMM 패키지 및 드라이버 및 펌웨어가 포함된 USB 플래시 드라이브를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-147">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="42592-148">Windows 10 이미지가 포함된 단일 USB 드라이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="42592-148">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="42592-149">이 예제에서 드라이브의 이름은 *BOOTME입니다.*</span><span class="sxs-lookup"><span data-stu-id="42592-149">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="42592-150">Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어(2단계) 및 SEMM 패키지 파일(4단계)을 *BOOTME* 드라이브에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-150">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="42592-151">6</span><span class="sxs-lookup"><span data-stu-id="42592-151">6</span></span> | [<span data-ttu-id="42592-152">SURFACE Hub 2S에서 UEFI를 업데이트하여 OS 마이그레이션을 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-152">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="42592-153">*BOOTME* 드라이브를 사용하여 Surface Hub 2S를 UEFI 메뉴로 부팅하고 SEMM 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-153">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="42592-154">7</span><span class="sxs-lookup"><span data-stu-id="42592-154">7</span></span> | [<span data-ttu-id="42592-155">Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-155">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="42592-156">*BOOTME* 드라이브를 사용하여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-156">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="42592-157">8</span><span class="sxs-lookup"><span data-stu-id="42592-157">8</span></span> | [<span data-ttu-id="42592-158">Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-158">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="42592-159">장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-159">To ensure your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="42592-160">9</span><span class="sxs-lookup"><span data-stu-id="42592-160">9</span></span> | [<span data-ttu-id="42592-161">Surface Hub 2S를 개인 생산성 장치로 완전히 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-161">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="42592-162">Surface Hub 2S를 개인 생산성 장치로 최적화하려면 권장 설정 및 응용 프로그램을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-162">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="42592-163">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="42592-163">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="42592-164">Surface Hub를 Windows 10 Team에서 Windows 10 Desktop으로 마이그레이션하기 전에 *694.2938.768.0*이상인 UEFI 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-164">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
**<span data-ttu-id="42592-165">시스템에서 UEFI 버전을 확인:</span><span class="sxs-lookup"><span data-stu-id="42592-165">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="42592-166">Surface Hub 2S 홈 페이지에서 **Start**시작을 선택한 다음 Surface 앱(모든 앱 Surface)을**니다.**  >  **Surface**</span><span class="sxs-lookup"><span data-stu-id="42592-166">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="42592-167">Surface를 **선택하여** 디바이스의 현재 UEFI 버전을 포함하여 Surface Hub에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-167">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="42592-168">UEFI 버전이 *694.2938.768.0* 이상인 경우 다음 이미지와 같이 SEMM 패키지를 만들어 OS 마이그레이션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-168">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![Screenshot showing the Your Surface page in the Surface app.](images/shm-fig1.png)
 
   - <span data-ttu-id="42592-170">UEFI 버전이 버전 694.2938.768.0 이전인 경우 Window 10 Team 2020 Update BMR(Update Bare Metal Recovery) 이미지를 설치하거나 Windows 업데이트를 사용하여 현재 버전을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-170">If the UEFI version is earlier than version 694.2938.768.0, you will need to obtain a current version by either installing the Window 10 Team 2020 Update Bare Metal Recovery (BMR) image, or by using Windows Update.</span></span>
   
**<span data-ttu-id="42592-171">Windows 업데이트를 통해 UEFI를 업데이트하는 방법:</span><span class="sxs-lookup"><span data-stu-id="42592-171">To update UEFI via Windows Update:</span></span>**

1. <span data-ttu-id="42592-172">Surface Hub 2S에서 관리자로 **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-172">On your Surface Hub 2S, sign in as **Admin**.</span></span> 
    >[!Note]
    > <span data-ttu-id="42592-173">사용자 이름 또는 관리자 암호를 모르는 경우 장치를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-173">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="42592-174">자세한 내용은 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Surface Hub 2S의 초기화 및 복구를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-174">For more information, see <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank">Reset and recovery for Surface Hub 2S.</span></span></a>

1. <span data-ttu-id="42592-175">모든 앱 **설정**업데이트 및 보안 Windows 업데이트로 이동한 다음 모든  >  **Settings**  >  **Update and Security**  >  **Windows Update**업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-175">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 
1. <span data-ttu-id="42592-176">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-176">Restart the device.</span></span> 
1. <span data-ttu-id="42592-177">Surface 앱을 사용하여 UEFI 버전을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-177">Verify the UEFI version by using the Surface app.</span></span> 
1. <span data-ttu-id="42592-178">이제 UEFI 버전이 아직 버전 694.2938.768.0 이상이 아닌 경우 위의 단계를 반복하거나 Windows 10 Team 2020 BMR(Update Bare Metal Recovery) 이미지를 설치하여 최신 UEFI를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-178">At this point, if the UEFI version is not yet version  694.2938.768.0 or later, you can either repeat the above steps, or you can get the latest UEFI by installing the Windows 10 Team 2020 Update Bare Metal Recovery (BMR) image.</span></span>

**<span data-ttu-id="42592-179">BMR(Bare Metal Recovery) 이미지를 통해 UEFI를 업데이트하는 경우:</span><span class="sxs-lookup"><span data-stu-id="42592-179">To update UEFI via Bare Metal Recovery (BMR) image:</span></span>**

1.  <span data-ttu-id="42592-180">Surface 복구 [사이트로 이동하여](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S 선택**</span><span class="sxs-lookup"><span data-stu-id="42592-180">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**</span></span>
3.  <span data-ttu-id="42592-181">허브 일련 번호를 입력합니다(전원 연결 옆의 허브 뒷면에 위치).</span><span class="sxs-lookup"><span data-stu-id="42592-181">Enter your Hub Serial Number (located on the rear side of the Hub next to the power connection.)</span></span>
4.  <span data-ttu-id="42592-182">지시에 따라 Windows 10 Team 2020 업데이트를 설치하여 포맷된 USB 드라이브에 이미지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-182">Follow the directions to download the image onto a formatted USB drive through installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="42592-183">업데이트가 완료된 후 장치가 OOBE를 처음 설치하면 OOBE를 완료할 필요가 없습니다. UEFI 버전이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-183">After the update has completed and the device enters the OOBE first time setup, you do not need to complete OOBE, the UEFI version will be updated.</span></span> <span data-ttu-id="42592-184">대신 화면이 꺼질 때까지 전원 단추를 눌러 장치를 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="42592-184">Instead power down the device by holding the power button until the screen turns off.</span></span> 

### <span data-ttu-id="42592-185">Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="42592-185">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="42592-186">별도의 PC에서:</span><span class="sxs-lookup"><span data-stu-id="42592-186">On a separate PC:</span></span>

1. <span data-ttu-id="42592-187"><a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">IT용 Surface 도구 페이지에서 </a> 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-187">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="42592-188">Surface UEFI 구성기 MSI 파일을 선택하고 다운로드하여 별도의 PC에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-188">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="42592-189">Windows 10 Team 버전이 설치된 동안에는 Surface Hub 2S에서 Surface UEFI 구성기 도구를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-189">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="42592-190">Surface <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Hub 2 드라이버 및 펌웨어 Windows Installer MSI 파일을 </a> 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-190">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Surface Hub 2 Drivers and Firmware Windows Installer MSI file</a>.</span></span> <span data-ttu-id="42592-191">새 운영 체제를 설치할 때 이 파일을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-191">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="42592-192">SEMM 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="42592-192">Prepare the SEMM certificate</span></span>

<span data-ttu-id="42592-193">Surface UEFI 구성기 사용 전에 사용되지 않은 경우 인증서를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-193">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="42592-194">이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지를 사용하여만 UEFI 설정을 수정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-194">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="42592-195">인증서를 사용하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-195">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="42592-196">엔터프라이즈 조직은 일반적으로 표준 보안 관행에 따라 인증서를 생성하기 위해 자체 인프라를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-196">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="42592-197">중소기업 및 다른 기업은 파트너 공급자로부터 인증서를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-197">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="42592-198">이 옵션은 충분한 IT 전문 지식이나 전담 IT 보안 팀이 없는 조직에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-198">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="42592-199">또는 PowerShell 스크립트를 사용하여 자체 서명된 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-199">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="42592-200">자세한 내용은 Surface 엔터프라이즈 관리 모드 인증서 요구 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> 사항을 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-200">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank">Surface Enterprise Management Mode certificate requirements </a>.</span></span> <span data-ttu-id="42592-201">또는 PowerShell을 사용하여 자체 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-201">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="42592-202">자세한 내용은 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate 설명서를 </a> 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42592-202">For more information, see the <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate</a> documentation.</span></span>

<span data-ttu-id="42592-203">Surface UEFI 구성기에서 만드는 SEMM 패키지는 인증서로 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-203">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="42592-204">인증서는 UEFI 설정을 적용하기 전에 구성 파일의 서명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-204">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="42592-205">자세한 내용은 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 설명서를 </a> 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="42592-205">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM documentation</a>.</span></span>
 
 
### <span data-ttu-id="42592-206">SEMM 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="42592-206">Create a SEMM package</span></span>

1. <span data-ttu-id="42592-207">별도의 PC에서 앞서 다운로드한 Surface UEFI 구성기 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-207">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="42592-208">Surface UEFI 구성기에서 시작을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-208">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI 구성기 열기](images/shm-fig2.png)
   
3. <span data-ttu-id="42592-210">**Surface 디바이스를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-210">Select **Surface Devices**, and then select **Next**.</span></span>

   ![Surface 디바이스를 선택합니다.](images/shm-fig3.png)
  
4. <span data-ttu-id="42592-212">구성 **패키지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-212">Select **Configuration Package**.</span></span>

   ![구성 패키지를 선택합니다.](images/shm-fig4.png)
  
5. <span data-ttu-id="42592-214">인증서 **보호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-214">Select **Certificate Protection**.</span></span>

   ![인증서 보호를 선택합니다.](images/shm-fig5.png)

   <span data-ttu-id="42592-216">인증서 .pfx 파일을 추가하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-216">You're prompted to add your certificate .pfx file.</span></span>

   ![인증서를 추가합니다.](images/shm-fig6.png)
   
7. <span data-ttu-id="42592-218">인증서 암호를 입력하고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-218">Enter your certificate password, and then select **OK**.</span></span>

   ![인증서 암호를 입력하고 확인을 선택합니다.](images/shm-fig7.png)

8. <span data-ttu-id="42592-220">Surface **Password Protection** UEFI에 암호를 추가하려면 암호 보호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-220">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="42592-221">UEFI로 부팅할 때마다 이 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-221">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="42592-222">Surface *strongly recommend* Hub 2S에서 사용할 UEFI 암호를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-222">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![암호 보호를 선택합니다.](images/shm-fig8.png)
   
9. <span data-ttu-id="42592-224">UEFI 암호를 설정한 다음 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-224">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="42592-225">Surface Hub를 관리하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-225">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="42592-226">암호가 손실된 경우 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-226">If the password is lost, it can't be recovered.</span></span> 

   ![UEFI 암호를 입력합니다.](images/shm-fig9.png)

10. <span data-ttu-id="42592-228">**Surface Hub 2S를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-228">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![Surface Hub 2S를 선택합니다.](images/shm-fig10.png)
   
11. <span data-ttu-id="42592-230">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-230">Select **Next**.</span></span>

    ![다음을 선택합니다.](images/shm-fig10a.png)

12. <span data-ttu-id="42592-232">Windows 10 Pro 또는 Enterprise 설치를 허용하려면 **EnableOsMigration을**켜고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-232">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![O S 마이그레이션 사용을 선택합니다.](images/shm-fig11.png)
    
    ![OS 마이그레이션 사용 설정](images/shm-fig12.png)

### <span data-ttu-id="42592-235">SEMM 등록 관리</span><span class="sxs-lookup"><span data-stu-id="42592-235">Managing SEMM enrollment</span></span>

<span data-ttu-id="42592-236">SEMM에 장치를 등록하면 디바이스를 관리하는 방법에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-236">Enrolling devices into SEMM affects how you can manage the device going forward.</span></span> <span data-ttu-id="42592-237">예를 들어 SEMM 패키지를 적용한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다(잠겨).</span><span class="sxs-lookup"><span data-stu-id="42592-237">For example, after you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="42592-238">PXE 부팅용 **IPv6과** 같은 다른 설정의 기본값도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-238">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 

<span data-ttu-id="42592-239">마이그레이션을 완료한 후 UEFI 설정을 변경하려면 다른 SEMM 패키지를 적용하거나 SEMM에서 디바이스의 인센토를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-239">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="42592-240">UEFI 설정을 변경하기 위해 다른 SEMM 패키지를 적용하는 경우 새 SEMM 패키지를 빌드할 때 원본 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-240">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="42592-241">UEFI 구성기 도구를 사용하여 **EnableOSMigration을** 해제합니다(원래 마이그레이션 단계에 표시된 것 아님).</span><span class="sxs-lookup"><span data-stu-id="42592-241">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="42592-242">파트너와 작업</span><span class="sxs-lookup"><span data-stu-id="42592-242">Working with partners</span></span>

<span data-ttu-id="42592-243">회사에서 Surface Hub 2의 Windows 10 Pro 또는 Enterprise로의 마이그레이션을 아웃소싱하는 경우 파트너가 SEMM 인증서, SEMM 패키지 및 UEFI 암호를 전송하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-243">If your company is outsourcing the migration to Windows 10 Pro or Enterprise on Surface Hub 2, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span>  <span data-ttu-id="42592-244">또는 허브를 마이그레이션한 후 SEMM에서 즉시 등록을 등록을 해지하면 UEFI의 로컬 관리 및 디바이스를 다른 사용자로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-244">Alternatively, after migrating the Hub, you can immediately un-enroll it from SEMM, which will allow local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="42592-245">하지만 마이그레이션 후 구성할 수 있는 UEFI 암호를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-245">Nevertheless, it's still strongly recommended to use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="42592-246">자세한 내용은 [Surface UEFI 설정 관리를 참조하세요.](https://docs.microsoft.com/surface/manage-surface-uefi-settings)</span><span class="sxs-lookup"><span data-stu-id="42592-246">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="42592-247">Windows 10 Team으로 롤백</span><span class="sxs-lookup"><span data-stu-id="42592-247">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="42592-248">마이그레이션 후 아래 설명에 따라 디바이스를 Windows 10 Team으로 복원하도록 선택한 경우 먼저 SEMM에서 허브의 사용을 철회하는 것이 좋습니다. [as described below](#roll-back-to-windows-10-team)</span><span class="sxs-lookup"><span data-stu-id="42592-248">If after migrating you choose to restore your device to Windows 10 Team, [as described below](#roll-back-to-windows-10-team), it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="42592-249">자세한 내용은 [SEMM에서 Surface 디바이스의 사용 안을 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="42592-249">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>


#### <span data-ttu-id="42592-250">USB 드라이브에 SEMM 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="42592-250">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="42592-251">USB 드라이브를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-251">Connect a USB drive to your PC.</span></span> 
1. <span data-ttu-id="42592-252">허브 **2S를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-252">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![USB 선택](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="42592-254">SEMM 패키지를 구축하면 USB 드라이브의 모든 기존 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-254">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="42592-255">SEMM 패키지를 구축하기 전에 저장할 USB 드라이브에서 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-255">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="42592-256">빌드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-256">Select **Build**.</span></span>

   ![빌드를 선택합니다.](images/shm-fig14.png)

3. <span data-ttu-id="42592-258">이 페이지의 스크린샷을 캡처한 다음 종료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-258">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="42592-259">이제 SEMM 패키지가 준비되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-259">Your SEMM package is now ready.</span></span> <span data-ttu-id="42592-260">여기에는 SEMM 패키지 *DfciUpdate.dfi* 및 SEMM 지문(인증서 지문의 마지막 두 문자)이 포함된 텍스트 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-260">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![끝을 선택합니다.](images/shm-fig15.png)
   
4. <span data-ttu-id="42592-262">인증서 지문의 마지막 두 문자를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-262">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="42592-263">Surface Hub 2S에서 패키지를 적용할 때 SEMM을 활성화하려면 다음 문자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-263">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="42592-264">Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어가 포함된 USB 플래시 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="42592-264">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="42592-265">다음 옵션 중 하나를 사용하여 Windows 10 Pro 또는 Enterprise 이미지(버전 1903 이상)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-265">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="42592-266">현재 이미징 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="42592-266">Your current imaging solution.</span></span>

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> <span data-ttu-id="42592-267">Surface 배포 </a> 가속기.</span><span class="sxs-lookup"><span data-stu-id="42592-267">Surface Deployment Accelerator</a>.</span></span> <span data-ttu-id="42592-268">이 도구를 사용하여 부팅 가능한 Windows 10 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-268">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="42592-269">이미지에는 모든 현재 Windows 10 업데이트, Office, 선택한 기타 앱 및 필요한 드라이버 및 펌웨어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-269">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="42592-270">Windows 10 Pro 또는 Enterprise 이미지가 포함된 USB 플래시 드라이브입니다.</span><span class="sxs-lookup"><span data-stu-id="42592-270">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="42592-271">그런 다음 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-271">Then install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
<span data-ttu-id="42592-272">다음 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-272">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="42592-273">다른 배포 방법을 사용하는 경우 Surface [Hub 2S의 업데이트 UEFI로](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 이동하여 이 문서의 OS 마이그레이션 섹션을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="42592-273">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="42592-274">설치를 완료한 후 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대한 유효한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-274">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="42592-275">Windows 10 Pro 설치를 만들 경우 Windows 10 다운로드 페이지에서 지침에 따라 미디어 만들기 도구를 <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> </a> 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-275">To create a Windows 10 Pro installation, on the<a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Download Windows 10</a> page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="42592-276">Windows 10 Enterprise를 다운로드하려면 Microsoft 볼륨 라이선스 서비스 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> 센터로 이동해야 </a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-276">To download Windows 10 Enterprise, go to the <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service Center</a>.</span></span>

2. <span data-ttu-id="42592-277">새 USB 저장소 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-277">Insert a new USB storage drive.</span></span> 
1. <span data-ttu-id="42592-278">미디어 만들기 도구를 열고 설치 **미디어 만들기를**선택한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-278">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![설치 미디어를 만드시다.](images/shm-fig16.png)
   
3. <span data-ttu-id="42592-280">언어를 선택한 다음 **Windows 10** 및 **64비트(x64)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-280">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="42592-281">그런 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-281">Then select **Next**.</span></span>

   ![언어를 선택하고 Windows 10 및 64비트를 선택합니다.](images/shm-fig17.png)
   
4. <span data-ttu-id="42592-284">USB **플래시 드라이브를**선택하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-284">Select **USB flash drive**, and then select **Next**.</span></span>

   ![U S B 플래시 드라이브를 선택하고 다음을 선택합니다.](images/shm-fig18.png)
   
5. <span data-ttu-id="42592-286">다운로드가 완료되면 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-286">When the download finishes, select **Finish**.</span></span>

   ![완료를 선택합니다.](images/shm-fig19.png)
   
6. <span data-ttu-id="42592-288">Surface Hub 2의 Windows 10 Pro 및 Enterprise OS(MSI 파일)에 대한 SEMM 패키지 파일 및 드라이버 및 펌웨어를 Windows 10 이미지가 포함된 USB 플래시*드라이브(BOOTME)의*루트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-288">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="42592-289">BOOTME USB 드라이브에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-289">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="42592-290">Windows 10 부팅 가능 이미지.</span><span class="sxs-lookup"><span data-stu-id="42592-290">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="42592-291">SEMM 패키지 파일(USB 드라이브의 루트에 복사)</span><span class="sxs-lookup"><span data-stu-id="42592-291">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="42592-292">*DfciUpdate.dfi*.</span><span class="sxs-lookup"><span data-stu-id="42592-292">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="42592-293">SEMM 지문을 포함하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="42592-293">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="42592-294">이 예제에서는 파일이SurfaceUEFI_2020Aug25_1058.txt\* .) \* 자동으로 생성된 날짜 타임스탬프는 Surface UEFI 구성기에서 파일을 만든 날짜에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-294">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="42592-295">Surface Hub 2(Windows 10 Pro 및 Enterprise OS)의 드라이버 및 펌웨어(SurfaceHub2S_Win10_18362_20.082.25682.0.msi.</span><span class="sxs-lookup"><span data-stu-id="42592-295">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="42592-296">이 파일을 USB 드라이브의 루트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-296">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="42592-297">OS 마이그레이션을 사용하도록 Surface Hub 2S에서 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="42592-297">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="42592-298">Surface Hub 2S의 USB-A 포트에 BOOTME 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-298">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="42592-299">필수 파일 목록은 이전 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-299">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="42592-300">UEFI로 부팅하는 경우:</span><span class="sxs-lookup"><span data-stu-id="42592-300">To boot into UEFI:</span></span>

   1. <span data-ttu-id="42592-301">Surface Hub 2S를 끄고(종료).</span><span class="sxs-lookup"><span data-stu-id="42592-301">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="42592-302">Volume **+ 를 누르고**전원 단추를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-302">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="42592-303">UEFI **메뉴가 나타날** 때까지 볼륨 + 유지</span><span class="sxs-lookup"><span data-stu-id="42592-303">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![UEFI 메뉴가 나타날 때까지 볼륨 업 단추를 누르고 있습니다.](images/shm-fig20.png)
      
3. <span data-ttu-id="42592-305">장치를 다시 시작하면 앞에서 만든 UEFI 암호를 입력합니다(해당하는 경우 권장).</span><span class="sxs-lookup"><span data-stu-id="42592-305">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![UEFI 암호를 입력합니다.](images/shm-fig22.png)
   
4. <span data-ttu-id="42592-307">UEFI 메뉴에서 **USB에서 관리**  >  **설치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-307">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![관리 및 US B에서 설치를 선택합니다.](images/shm-fig21.png)
   
5. <span data-ttu-id="42592-309">다음 **이미지와 같이**지금 다시 시작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-309">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="42592-310">장치가 다시부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-310">The device reboots.</span></span> <span data-ttu-id="42592-311">창 중간에 흰색 Microsoft 로고를 표시한 다음 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-311">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![지금 다시 시작을 선택합니다.](images/shm-fig25.png)
   
6. <span data-ttu-id="42592-313">전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-313">Press and release the power button.</span></span> <span data-ttu-id="42592-314">빨간색 창이 나타나면 Surface 엔터프라이즈 관리 모드를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-314">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="42592-315">2문자 인증서 지문과 UEFI 설정 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-315">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="42592-316">그런 다음 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="42592-316">Then select **OK**.</span></span>

   ![2문자 인증서 지문과 UEFI 설정 암호를 입력합니다.](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="42592-318">장치에서 SEMM을 활성화하면 새 UEFI 설정 **EnableOSMigration이** 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-318">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="42592-319">더 이상 Windows 10 Team에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-319">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="42592-320">대신 다음 단계를 계속하고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-320">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="42592-321">장치가 다시부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-321">The device reboots.</span></span> <span data-ttu-id="42592-322">화면 중간에 흰색 로고를 표시한 다음 다시 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-322">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="42592-323">Windows 10 Pro 또는 Enterprise 설치</span><span class="sxs-lookup"><span data-stu-id="42592-323">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="42592-324">부팅 가능한 Windows 10 Pro 또는 Enterprise 드라이브가 Surface Hub 2 USB-A 포트에 아직 없는 경우 지금 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-324">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="42592-325">그런 다음 전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-325">Then press and release the power button.</span></span> 

    <span data-ttu-id="42592-326">디바이스가 시작되면 화면 중간에 흰색 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-326">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="42592-327">그런 다음 흰색 로고 아래에 회전하는 원이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-327">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="42592-328">장치가 자동으로 USB 드라이브로 부팅되지 않는 경우 디바이스를 끄세요(전원 코드를 끄고 다시 연결).</span><span class="sxs-lookup"><span data-stu-id="42592-328">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="42592-329">전원 코드를 다시 연결한 후 디바이스가 몇 초 후에 부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-329">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="42592-330">그런 다음 화면 중간에 흰색 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42592-330">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="42592-331">디바이스가 켜지 않은 경우 전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-331">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="42592-332">화면 중간에 로고가 표시되고 나면 흰색 로고 아래에 회전하는 원이 표시될 때까지 볼륨 단추를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-332">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![U.S B 드라이브에서 Windows 10으로 부팅합니다.](images/shm-fig26.png)
   
4. <span data-ttu-id="42592-334">OOBE(첫 실행 경험) 설치가 시작되면 지침에 따라 Windows 10 Pro 또는 Enterprise(버전 1903 이상)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-334">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="42592-335">Surface Hub 2 드라이버 및 펌웨어 설치</span><span class="sxs-lookup"><span data-stu-id="42592-335">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="42592-336">장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-336">To ensure your device has all the latest updates and drivers, install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
## <span data-ttu-id="42592-337">권장 설정 구성</span><span class="sxs-lookup"><span data-stu-id="42592-337">Configure recommended settings</span></span>

<span data-ttu-id="42592-338">Surface Hub 2S를 개인 생산성 장치로 완전히 구성하려면 <a href="surface-hub-2-post-install.md" target="_blank"> Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성을 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-338">To fully configure Surface Hub 2S as a personal productivity device, see <a href="surface-hub-2-post-install.md" target="_blank">Configure Windows 10 Pro or Enterprise on Surface Hub 2</a>.</span></span>

> [!NOTE]
><span data-ttu-id="42592-339">이 문서에 설명된 단계가 Surface Hub 2용 Windows 10 Pro 또는 Enterprise로 성공적으로 마이그레이션되지 않는 경우 Surface Hub 지원에 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> </a> 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-339">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub Support</a>.</span></span>

## <span data-ttu-id="42592-340">Windows 10 Team으로 롤백</span><span class="sxs-lookup"><span data-stu-id="42592-340">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="42592-341">디바이스를 Windows 10 Team으로 복원하려면 Surface Hub 2S에 대한 초기화 및 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 복구를 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42592-341">If you want to restore your device to Windows 10 Team, see <a href="surface-hub-2s-recover-reset.md" target="_blank"> Reset and recovery for Surface Hub 2S</a>.</span></span>

> [!NOTE]
> <span data-ttu-id="42592-342">Windows 10 Team으로 롤백하기 전에 SEMM에서 허브를 먼저 사용인증을 해지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-342">Before rolling back to Windows 10 Team, it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="42592-343">자세한 내용은 [SEMM에서 Surface 디바이스의 사용 안을 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="42592-343">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="42592-344">버전 기록</span><span class="sxs-lookup"><span data-stu-id="42592-344">Version history</span></span>

<span data-ttu-id="42592-345">다음 표에서는 이 문서의 변경 내용을 요약하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42592-345">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="42592-346">버전</span><span class="sxs-lookup"><span data-stu-id="42592-346">Version</span></span> | <span data-ttu-id="42592-347">Date</span><span class="sxs-lookup"><span data-stu-id="42592-347">Date</span></span>               | <span data-ttu-id="42592-348">설명</span><span class="sxs-lookup"><span data-stu-id="42592-348">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="42592-349">v.</span><span class="sxs-lookup"><span data-stu-id="42592-349">v.</span></span> <span data-ttu-id="42592-350">1.3</span><span class="sxs-lookup"><span data-stu-id="42592-350">1.3</span></span>  | <span data-ttu-id="42592-351">2020년 12월 3일</span><span class="sxs-lookup"><span data-stu-id="42592-351">December 3, 2020</span></span> | <span data-ttu-id="42592-352">SEMM 등록 관리에 대한 지침으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-352">Updated with guidance about managing SEMM enrollment</span></span>                                                        |
| <span data-ttu-id="42592-353">v.</span><span class="sxs-lookup"><span data-stu-id="42592-353">v.</span></span> <span data-ttu-id="42592-354">1.2</span><span class="sxs-lookup"><span data-stu-id="42592-354">1.2</span></span>  | <span data-ttu-id="42592-355">2020년 9월 29일</span><span class="sxs-lookup"><span data-stu-id="42592-355">September 29, 2020</span></span> | <span data-ttu-id="42592-356">사용 가능성 피드백을 해결 하는 기타 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="42592-356">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="42592-357">v.</span><span class="sxs-lookup"><span data-stu-id="42592-357">v.</span></span> <span data-ttu-id="42592-358">1.1</span><span class="sxs-lookup"><span data-stu-id="42592-358">1.1</span></span>  | <span data-ttu-id="42592-359">2020년 9월 15일</span><span class="sxs-lookup"><span data-stu-id="42592-359">September 15, 2020</span></span> | <span data-ttu-id="42592-360">새 OS를 설치하기 위한 라이선스 요구 사항을 명확히 설명하는 추가 참고 사항이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42592-360">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="42592-361">v.</span><span class="sxs-lookup"><span data-stu-id="42592-361">v.</span></span> <span data-ttu-id="42592-362">1.0</span><span class="sxs-lookup"><span data-stu-id="42592-362">1.0</span></span>  | <span data-ttu-id="42592-363">2020년 9월 1일</span><span class="sxs-lookup"><span data-stu-id="42592-363">September 1, 2020</span></span>  | <span data-ttu-id="42592-364">새 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="42592-364">New article.</span></span>                                                                                           |
