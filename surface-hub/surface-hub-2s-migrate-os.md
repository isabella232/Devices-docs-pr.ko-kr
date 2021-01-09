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
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9878e64e414f4fe9ec3abfbd49adf233edc1da1d
ms.sourcegitcommit: 53d1eac8840fafbcd155798fce0d8c843f48dca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2021
ms.locfileid: "11255490"
---
# <span data-ttu-id="70255-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="70255-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="70255-105">문서 버전 기록</span><span class="sxs-lookup"><span data-stu-id="70255-105">Article version history</span></span>](#version-history)

<span data-ttu-id="70255-106">Surface Hub 2S는 Windows 10 Team과 함께 사전 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-106">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="70255-107">이 사용자 지정된 Windows 10 버전은 회의실 환경에서 공동 작업을 용이하게 하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-107">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="70255-108">이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용하기 위해 Windows 10 Pro 또는 Enterprise를 실행하는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-108">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="70255-109">일반적인 업그레이드 또는 마이그레이션과 달리 이 프로세스에서는 이 문서에 설명된 징계 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-109">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="70255-110">계속하기 [전에 솔루션](#solution-components) 구성 요소 및 마이그레이션 및 [설치](#migration-and-installation-workflow-summary) 워크플로를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-110">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="70255-111">Windows 10 Pro 또는 Enterprise를 설치할 때 기존 Windows 10 Team 라이선스와는 별개인 새 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="70255-112">별도의 PC 및 다운로드 가능한 도구 Surface UEFI 구성 도구를 사용하여 Windows 10 Team에서 *마이그레이션을 시작하세요.*</span><span class="sxs-lookup"><span data-stu-id="70255-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="70255-113">이 도구를 사용하여 Surface Hub 2S에 적용하는 새 UEFI 설정이 포함된 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-113">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="70255-114">Surface UEFI 구성기는 Surface SEMM(엔터프라이즈 관리 모드)에 대한 인터페이스로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="70255-115">회사 환경의 Surface 디바이스에서 펌웨어 설정을 중앙에서 쉽게 관리하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-115">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="70255-116">자세한 내용은 Microsoft <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 설명서를 </a> 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-116">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft SEMM documentation</a>.</span></span>
 

## <span data-ttu-id="70255-117">솔루션 구성 요소</span><span class="sxs-lookup"><span data-stu-id="70255-117">Solution components</span></span>

- <span data-ttu-id="70255-118">Windows 10 Team 운영 체제를 실행하는 Surface Hub 2S 장치</span><span class="sxs-lookup"><span data-stu-id="70255-118">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="70255-119">Windows 10을 실행하는 장치 분리</span><span class="sxs-lookup"><span data-stu-id="70255-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="70255-120">SEMM 패키지를 만들기 위한 Surface UEFI 구성기 도구</span><span class="sxs-lookup"><span data-stu-id="70255-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="70255-121">Windows 10 Pro 또는 Enterprise OS 이미지, 버전 1903 이상</span><span class="sxs-lookup"><span data-stu-id="70255-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="70255-122">16GB의 저장소가 있는 USB 드라이브 2개, FAT32 형식</span><span class="sxs-lookup"><span data-stu-id="70255-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="70255-123">Surface Hub 2(MSI) 파일의 Windows 10 Pro 및 엔터프라이즈 OS용 Microsoft Windows Installer 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="70255-123">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="70255-124">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="70255-124">Internet connection</span></span>
- <span data-ttu-id="70255-125">이미징 솔루션(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="70255-125">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="70255-126">마이그레이션 및 설치 워크플로 요약</span><span class="sxs-lookup"><span data-stu-id="70255-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="70255-127">단계</span><span class="sxs-lookup"><span data-stu-id="70255-127">Step</span></span>  | <span data-ttu-id="70255-128">작업</span><span class="sxs-lookup"><span data-stu-id="70255-128">Action</span></span>                                                                                                 | <span data-ttu-id="70255-129">요약</span><span class="sxs-lookup"><span data-stu-id="70255-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="70255-130">1</span><span class="sxs-lookup"><span data-stu-id="70255-130">1</span></span> | [<span data-ttu-id="70255-131">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-131">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="70255-132">UEFI 버전이 694.2938.768.0 이상인지 확인</span><span class="sxs-lookup"><span data-stu-id="70255-132">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="70255-133">2</span><span class="sxs-lookup"><span data-stu-id="70255-133">2</span></span> | [<span data-ttu-id="70255-134">Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-134">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="70255-135"><a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **IT용 Surface 도구 페이지에서** </a> 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-135">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">**Surface Tools for IT** page</a>, select **Download**.</span></span> <span data-ttu-id="70255-136">그런 다음 **Surface UEFI 구성 프로그램을 선택하고 다운로드합니다. MSI 파일을** 설치하고 별도 PC에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-136">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="70255-137">Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-137">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a> <span data-ttu-id="70255-138">5단계에서 사용하기 위해 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-138">Save it for use in step 5.</span></span> |
| <span data-ttu-id="70255-139">3</span><span class="sxs-lookup"><span data-stu-id="70255-139">3</span></span> | [<span data-ttu-id="70255-140">SEMM 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-140">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="70255-141">Surface UEFI 구성기 실행에 필요한 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-141">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="70255-142">또는 현재 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-142">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="70255-143">4</span><span class="sxs-lookup"><span data-stu-id="70255-143">4</span></span> | [<span data-ttu-id="70255-144">SEMM 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-144">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="70255-145">Surface Hub 2S에서 적용해야 하는 구성 파일이 포함된 USB 드라이브에 SEMM 패키지를 만들 수 있는 Surface UEFI 구성을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-145">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="70255-146">이러한 SEMM 패키지 파일을 PC의 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="70255-147">5</span><span class="sxs-lookup"><span data-stu-id="70255-147">5</span></span> | [<span data-ttu-id="70255-148">Surface Hub 2에서 Windows 10 Pro 및 Enterprise OS용 Windows 10 이미지, SEMM 패키지 및 드라이버 및 펌웨어가 포함된 USB 플래시 드라이브를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-148">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="70255-149">Windows 10 이미지가 포함된 단일 USB 드라이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70255-149">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="70255-150">이 예제에서 드라이브의 이름은 *BOOTME입니다.*</span><span class="sxs-lookup"><span data-stu-id="70255-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="70255-151">Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어(2단계) 및 SEMM 패키지 파일(4단계)을 *BOOTME* 드라이브에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-151">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="70255-152">6</span><span class="sxs-lookup"><span data-stu-id="70255-152">6</span></span> | [<span data-ttu-id="70255-153">SURFACE Hub 2S에서 UEFI를 업데이트하여 OS 마이그레이션을 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-153">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="70255-154">*BOOTME* 드라이브를 사용하여 Surface Hub 2S를 UEFI 메뉴로 부팅하고 SEMM 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-154">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="70255-155">7</span><span class="sxs-lookup"><span data-stu-id="70255-155">7</span></span> | [<span data-ttu-id="70255-156">Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-156">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="70255-157">*BOOTME* 드라이브를 사용하여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="70255-158">8</span><span class="sxs-lookup"><span data-stu-id="70255-158">8</span></span> | [<span data-ttu-id="70255-159">Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-159">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="70255-160">장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-160">To ensure your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="70255-161">9</span><span class="sxs-lookup"><span data-stu-id="70255-161">9</span></span> | [<span data-ttu-id="70255-162">Surface Hub 2S를 개인 생산성 장치로 완전히 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-162">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="70255-163">Surface Hub 2S를 개인 생산성 장치로 최적화하려면 권장 설정 및 응용 프로그램을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-163">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="70255-164">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="70255-164">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="70255-165">Surface Hub를 Windows 10 Team에서 Windows 10 Desktop으로 마이그레이션하기 전에 *694.2938.768.0*이상인 UEFI 버전이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
**<span data-ttu-id="70255-166">시스템에서 UEFI 버전을 확인:</span><span class="sxs-lookup"><span data-stu-id="70255-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="70255-167">Surface Hub 2S 홈 페이지에서 \*\*\*\* 시작을 선택한 다음 Surface 앱(모든 앱 Surface)을**니다.**  >  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="70255-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="70255-168">Surface를 **선택하여** 디바이스의 현재 UEFI 버전을 포함하여 Surface Hub에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="70255-169">UEFI 버전이 *694.2938.768.0* 이상인 경우 다음 이미지와 같이 SEMM 패키지를 만들어 OS 마이그레이션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![Screenshot showing the Your Surface page in the Surface app.](images/shm-fig1.png)
 
   - <span data-ttu-id="70255-171">UEFI 버전이 버전 694.2938.768.0 이전인 경우 Window 10 Team 2020 Update BMR(Update Bare Metal Recovery) 이미지를 설치하거나 Windows 업데이트를 사용하여 현재 버전을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-171">If the UEFI version is earlier than version 694.2938.768.0, you will need to obtain a current version by either installing the Window 10 Team 2020 Update Bare Metal Recovery (BMR) image, or by using Windows Update.</span></span>
   
**<span data-ttu-id="70255-172">Windows 업데이트를 통해 UEFI를 업데이트하는 방법:</span><span class="sxs-lookup"><span data-stu-id="70255-172">To update UEFI via Windows Update:</span></span>**

1. <span data-ttu-id="70255-173">Surface Hub 2S에서 관리자로 **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-173">On your Surface Hub 2S, sign in as **Admin**.</span></span> 

    >[!Note]
    > <span data-ttu-id="70255-174">사용자 이름 또는 관리자 암호를 모르는 경우 장치를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-174">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="70255-175">자세한 내용은 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Surface Hub 2S의 초기화 및 복구를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-175">For more information, see <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank">Reset and recovery for Surface Hub 2S.</span></span></a>

1. <span data-ttu-id="70255-176">모든 앱 **설정**업데이트 및 보안 Windows 업데이트로 이동한 다음 모든  >  \*\*\*\*  >  \*\*\*\*  >  \*\*\*\* 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 

1. <span data-ttu-id="70255-177">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-177">Restart the device.</span></span> 

1. <span data-ttu-id="70255-178">Surface 앱을 사용하여 UEFI 버전을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-178">Verify the UEFI version by using the Surface app.</span></span>

1. <span data-ttu-id="70255-179">이제 UEFI 버전이 아직 버전 694.2938.768.0 이상이 아닌 경우 위의 단계를 반복하거나 Windows 10 Team 2020 BMR(Update Bare Metal Recovery) 이미지를 설치하여 최신 UEFI를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-179">At this point, if the UEFI version is not yet version  694.2938.768.0 or later, you can either repeat the above steps, or you can get the latest UEFI by installing the Windows 10 Team 2020 Update Bare Metal Recovery (BMR) image.</span></span>

**<span data-ttu-id="70255-180">BMR(Bare Metal Recovery) 이미지를 통해 UEFI를 업데이트하는 경우:</span><span class="sxs-lookup"><span data-stu-id="70255-180">To update UEFI via Bare Metal Recovery (BMR) image:</span></span>**

1.  <span data-ttu-id="70255-181">Surface 복구 [사이트로 이동하여](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.</span></span>

3.  <span data-ttu-id="70255-182">허브 일련 번호를 입력합니다(전원 연결 옆의 허브 뒷면에 위치).</span><span class="sxs-lookup"><span data-stu-id="70255-182">Enter your Hub Serial Number (located on the rear side of the Hub next to the power connection).</span></span>

4.  <span data-ttu-id="70255-183">지시에 따라 Windows 10 Team 2020 업데이트를 설치하여 포맷된 USB 드라이브에 이미지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-183">Follow the directions to download the image onto a formatted USB drive through installing the Windows 10 Team 2020 Update.</span></span>

5.  <span data-ttu-id="70255-184">업데이트가 완료된 후 장치가 OOBE를 처음 설치하면 OOBE를 완료할 필요가 없습니다. UEFI 버전이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-184">After the update has completed and the device enters the OOBE first time setup, you do not need to complete OOBE, the UEFI version will be updated.</span></span> <span data-ttu-id="70255-185">대신 화면이 꺼질 때까지 전원 단추를 눌러 장치를 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="70255-185">Instead power down the device by holding the power button until the screen turns off.</span></span> 

### <span data-ttu-id="70255-186">Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="70255-186">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="70255-187">별도의 PC에서:</span><span class="sxs-lookup"><span data-stu-id="70255-187">On a separate PC:</span></span>

1. <span data-ttu-id="70255-188"><a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">IT용 Surface 도구 페이지에서 </a> 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-188">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>

1. <span data-ttu-id="70255-189">Surface UEFI 구성기 MSI 파일을 선택하고 다운로드하여 별도의 PC에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-189">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="70255-190">Windows 10 Team 버전이 설치된 동안에는 Surface Hub 2S에서 Surface UEFI 구성기 도구를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-190">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="70255-191">Surface <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Hub 2 드라이버 및 펌웨어 Windows Installer MSI 파일을 </a> 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-191">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Surface Hub 2 Drivers and Firmware Windows Installer MSI file</a>.</span></span> <span data-ttu-id="70255-192">새 운영 체제를 설치할 때 이 파일을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-192">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="70255-193">SEMM 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="70255-193">Prepare the SEMM certificate</span></span>

<span data-ttu-id="70255-194">Surface UEFI 구성기 사용 전에 사용되지 않은 경우 인증서를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-194">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="70255-195">이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지를 사용하여만 UEFI 설정을 수정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-195">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="70255-196">인증서를 사용하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-196">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="70255-197">엔터프라이즈 조직은 일반적으로 표준 보안 관행에 따라 인증서를 생성하기 위해 자체 인프라를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-197">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="70255-198">중소기업 및 다른 기업은 파트너 공급자로부터 인증서를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-198">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="70255-199">이 옵션은 충분한 IT 전문 지식이나 전담 IT 보안 팀이 없는 조직에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-199">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="70255-200">또는 PowerShell 스크립트를 사용하여 자체 서명된 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-200">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="70255-201">자세한 내용은 Surface 엔터프라이즈 관리 모드 인증서 요구 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> 사항을 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-201">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank">Surface Enterprise Management Mode certificate requirements </a>.</span></span> <span data-ttu-id="70255-202">또는 PowerShell을 사용하여 자체 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-202">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="70255-203">자세한 내용은 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate 설명서를 </a> 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-203">For more information, see the <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate</a> documentation.</span></span>

<span data-ttu-id="70255-204">Surface UEFI 구성기에서 만드는 SEMM 패키지는 인증서로 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-204">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="70255-205">인증서는 UEFI 설정을 적용하기 전에 구성 파일의 서명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-205">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="70255-206">자세한 내용은 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 설명서를 </a> 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-206">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM documentation</a>.</span></span>
 
 
### <span data-ttu-id="70255-207">SEMM 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="70255-207">Create a SEMM package</span></span>

1. <span data-ttu-id="70255-208">별도의 PC에서 앞서 다운로드한 Surface UEFI 구성기 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-208">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="70255-209">Surface UEFI 구성기에서 시작을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-209">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI 구성기 열기](images/shm-fig2.png)
   
3. <span data-ttu-id="70255-211">**Surface 디바이스를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-211">Select **Surface Devices**, and then select **Next**.</span></span>

   ![Surface 디바이스를 선택합니다.](images/shm-fig3.png)
  
4. <span data-ttu-id="70255-213">구성 **패키지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-213">Select **Configuration Package**.</span></span>

   ![구성 패키지를 선택합니다.](images/shm-fig4.png)
  
5. <span data-ttu-id="70255-215">인증서 **보호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-215">Select **Certificate Protection**.</span></span>

   ![인증서 보호를 선택합니다.](images/shm-fig5.png)

   <span data-ttu-id="70255-217">인증서 .pfx 파일을 추가하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-217">You're prompted to add your certificate .pfx file.</span></span>

   ![인증서를 추가합니다.](images/shm-fig6.png)
   
7. <span data-ttu-id="70255-219">인증서 암호를 입력하고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-219">Enter your certificate password, and then select **OK**.</span></span>

   ![인증서 암호를 입력하고 확인을 선택합니다.](images/shm-fig7.png)

8. <span data-ttu-id="70255-221">Surface \*\*\*\* UEFI에 암호를 추가하려면 암호 보호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-221">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="70255-222">UEFI로 부팅할 때마다 이 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-222">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="70255-223">Surface \*\* Hub 2S에서 사용할 UEFI 암호를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-223">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![암호 보호를 선택합니다.](images/shm-fig8.png)
   
9. <span data-ttu-id="70255-225">UEFI 암호를 설정한 다음 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-225">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="70255-226">Surface Hub를 관리하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-226">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="70255-227">암호가 손실된 경우 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-227">If the password is lost, it can't be recovered.</span></span> 

   ![UEFI 암호를 입력합니다.](images/shm-fig9.png)

10. <span data-ttu-id="70255-229">**Surface Hub 2S를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-229">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![Surface Hub 2S를 선택합니다.](images/shm-fig10.png)
   
11. <span data-ttu-id="70255-231">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-231">Select **Next**.</span></span>

    ![다음을 선택합니다.](images/shm-fig10a.png)

12. <span data-ttu-id="70255-233">Windows 10 Pro 또는 Enterprise 설치를 허용하려면 **EnableOsMigration을**켜고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-233">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![O S 마이그레이션 사용을 선택합니다.](images/shm-fig11.png)
    
    ![OS 마이그레이션 사용 설정](images/shm-fig12.png)

### <span data-ttu-id="70255-236">SEMM 등록 관리</span><span class="sxs-lookup"><span data-stu-id="70255-236">Managing SEMM enrollment</span></span>

<span data-ttu-id="70255-237">SEMM에 장치를 등록하면 디바이스를 관리하는 방법에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-237">Enrolling devices into SEMM affects how you can manage the device going forward.</span></span> <span data-ttu-id="70255-238">예를 들어 SEMM 패키지를 적용한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다(잠겨).</span><span class="sxs-lookup"><span data-stu-id="70255-238">For example, after you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="70255-239">PXE 부팅용 **IPv6과** 같은 다른 설정의 기본값도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-239">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 

<span data-ttu-id="70255-240">마이그레이션을 완료한 후 UEFI 설정을 변경하려면 다른 SEMM 패키지를 적용하거나 SEMM에서 디바이스의 인센토를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-240">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="70255-241">UEFI 설정을 변경하기 위해 다른 SEMM 패키지를 적용하는 경우 새 SEMM 패키지를 빌드할 때 원본 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-241">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="70255-242">UEFI 구성기 도구를 사용하여 **EnableOSMigration을** 해제합니다(원래 마이그레이션 단계에 표시된 것 아님).</span><span class="sxs-lookup"><span data-stu-id="70255-242">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="70255-243">파트너와 작업</span><span class="sxs-lookup"><span data-stu-id="70255-243">Working with partners</span></span>

<span data-ttu-id="70255-244">회사에서 Surface Hub 2의 Windows 10 Pro 또는 Enterprise로의 마이그레이션을 아웃소싱하는 경우 파트너가 SEMM 인증서, SEMM 패키지 및 UEFI 암호를 전송하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-244">If your company is outsourcing the migration to Windows 10 Pro or Enterprise on Surface Hub 2, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span>  <span data-ttu-id="70255-245">또는 허브를 마이그레이션한 후 SEMM에서 즉시 등록을 등록을 해지하면 UEFI의 로컬 관리 및 디바이스를 다른 사용자로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-245">Alternatively, after migrating the Hub, you can immediately un-enroll it from SEMM, which will allow local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="70255-246">하지만 마이그레이션 후 구성할 수 있는 UEFI 암호를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-246">Nevertheless, it's still strongly recommended to use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="70255-247">자세한 내용은 [Surface UEFI 설정 관리를 참조하세요.](https://docs.microsoft.com/surface/manage-surface-uefi-settings)</span><span class="sxs-lookup"><span data-stu-id="70255-247">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="70255-248">Windows 10 Team으로 롤백</span><span class="sxs-lookup"><span data-stu-id="70255-248">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="70255-249">마이그레이션 후 아래 설명에 따라 디바이스를 Windows 10 Team으로 복원하도록 선택한 경우 먼저 SEMM에서 허브의 사용을 철회하는 것이 좋습니다. [](#roll-back-to-windows-10-team)</span><span class="sxs-lookup"><span data-stu-id="70255-249">If after migrating you choose to restore your device to Windows 10 Team, [as described below](#roll-back-to-windows-10-team), it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="70255-250">자세한 내용은 [SEMM에서 Surface 디바이스의 사용 안을 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="70255-250">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>


#### <span data-ttu-id="70255-251">USB 드라이브에 SEMM 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="70255-251">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="70255-252">USB 드라이브를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-252">Connect a USB drive to your PC.</span></span> 

1. <span data-ttu-id="70255-253">허브 **2S를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-253">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![USB 선택](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="70255-255">SEMM 패키지를 구축하면 USB 드라이브의 모든 기존 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-255">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="70255-256">SEMM 패키지를 구축하기 전에 저장할 USB 드라이브에서 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-256">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="70255-257">빌드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-257">Select **Build**.</span></span>

   ![빌드를 선택합니다.](images/shm-fig14.png)

3. <span data-ttu-id="70255-259">이 페이지의 스크린샷을 캡처한 다음 종료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-259">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="70255-260">이제 SEMM 패키지가 준비되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-260">Your SEMM package is now ready.</span></span> <span data-ttu-id="70255-261">여기에는 SEMM 패키지 *DfciUpdate.dfi* 및 SEMM 지문(인증서 지문의 마지막 두 문자)이 포함된 텍스트 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-261">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![끝을 선택합니다.](images/shm-fig15.png)
   
4. <span data-ttu-id="70255-263">인증서 지문의 마지막 두 문자를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-263">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="70255-264">Surface Hub 2S에서 패키지를 적용할 때 SEMM을 활성화하려면 다음 문자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-264">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="70255-265">Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어가 포함된 USB 플래시 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="70255-265">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="70255-266">다음 옵션 중 하나를 사용하여 Windows 10 Pro 또는 Enterprise 이미지(버전 1903 이상)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-266">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="70255-267">현재 이미징 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="70255-267">Your current imaging solution.</span></span>

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> <span data-ttu-id="70255-268">Surface 배포 </a> 가속기.</span><span class="sxs-lookup"><span data-stu-id="70255-268">Surface Deployment Accelerator</a>.</span></span> <span data-ttu-id="70255-269">이 도구를 사용하여 부팅 가능한 Windows 10 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-269">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="70255-270">이미지에는 모든 현재 Windows 10 업데이트, Office, 선택한 기타 앱 및 필요한 드라이버 및 펌웨어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-270">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="70255-271">Windows 10 Pro 또는 Enterprise 이미지가 포함된 USB 플래시 드라이브입니다.</span><span class="sxs-lookup"><span data-stu-id="70255-271">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="70255-272">그런 다음 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-272">Then install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
<span data-ttu-id="70255-273">다음 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-273">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="70255-274">다른 배포 방법을 사용하는 경우 Surface [Hub 2S의 업데이트 UEFI로](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 이동하여 이 문서의 OS 마이그레이션 섹션을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-274">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="70255-275">설치를 완료한 후 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대한 유효한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-275">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="70255-276">Windows 10 Pro 설치를 만들 경우 Windows 10 다운로드 페이지에서 지침에 따라 미디어 만들기 도구를 <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> </a> 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-276">To create a Windows 10 Pro installation, on the<a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Download Windows 10</a> page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="70255-277">Windows 10 Enterprise를 다운로드하려면 Microsoft 볼륨 라이선스 서비스 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> 센터로 이동해야 </a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-277">To download Windows 10 Enterprise, go to the <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service Center</a>.</span></span>

1. <span data-ttu-id="70255-278">새 USB 저장소 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-278">Insert a new USB storage drive.</span></span> 

1. <span data-ttu-id="70255-279">미디어 만들기 도구를 열고 설치 **미디어 만들기를**선택한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-279">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![설치 미디어를 만드시다.](images/shm-fig16.png)
   
1. <span data-ttu-id="70255-281">언어를 선택한 다음 **Windows 10** 및 **64비트(x64)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-281">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="70255-282">그런 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-282">Then select **Next**.</span></span>

   ![언어를 선택하고 Windows 10 및 64비트를 선택합니다.](images/shm-fig17.png)
   
1. <span data-ttu-id="70255-285">USB **플래시 드라이브를**선택하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-285">Select **USB flash drive**, and then select **Next**.</span></span>

   ![U S B 플래시 드라이브를 선택하고 다음을 선택합니다.](images/shm-fig18.png)
   
1. <span data-ttu-id="70255-287">다운로드가 완료되면 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-287">When the download finishes, select **Finish**.</span></span>

   ![완료를 선택합니다.](images/shm-fig19.png)
   
1. <span data-ttu-id="70255-289">Surface Hub 2의 Windows 10 Pro 및 Enterprise OS(MSI 파일)에 대한 SEMM 패키지 파일 및 드라이버 및 펌웨어를 Windows 10 이미지가 포함된 USB 플래시*드라이브(BOOTME)의*루트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-289">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="70255-290">BOOTME USB 드라이브에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-290">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="70255-291">Windows 10 부팅 가능 이미지.</span><span class="sxs-lookup"><span data-stu-id="70255-291">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="70255-292">SEMM 패키지 파일(USB 드라이브의 루트에 복사)</span><span class="sxs-lookup"><span data-stu-id="70255-292">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="70255-293">*DfciUpdate.dfi*.</span><span class="sxs-lookup"><span data-stu-id="70255-293">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="70255-294">SEMM 지문을 포함하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="70255-294">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="70255-295">이 예제에서는 파일이SurfaceUEFI_2020Aug25_1058.txt\* .) \* 자동으로 생성된 날짜 타임스탬프는 Surface UEFI 구성기에서 파일을 만든 날짜에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-295">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="70255-296">Surface Hub 2(Windows 10 Pro 및 Enterprise OS)의 드라이버 및 펌웨어(SurfaceHub2S_Win10_18362_20.082.25682.0.msi.</span><span class="sxs-lookup"><span data-stu-id="70255-296">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="70255-297">이 파일을 USB 드라이브의 루트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-297">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="70255-298">OS 마이그레이션을 사용하도록 Surface Hub 2S에서 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="70255-298">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="70255-299">Surface Hub 2S의 USB-A 포트에 BOOTME 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-299">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="70255-300">필수 파일 목록은 이전 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-300">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="70255-301">UEFI로 부팅하는 경우:</span><span class="sxs-lookup"><span data-stu-id="70255-301">To boot into UEFI:</span></span>

   1. <span data-ttu-id="70255-302">Surface Hub 2S를 끄고(종료).</span><span class="sxs-lookup"><span data-stu-id="70255-302">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="70255-303">Volume **+ 를 누르고**전원 단추를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-303">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="70255-304">UEFI **메뉴가 나타날** 때까지 볼륨 + 유지</span><span class="sxs-lookup"><span data-stu-id="70255-304">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![UEFI 메뉴가 나타날 때까지 볼륨 업 단추를 누르고 있습니다.](images/shm-fig20.png)
      
3. <span data-ttu-id="70255-306">장치를 다시 시작하면 앞에서 만든 UEFI 암호를 입력합니다(해당하는 경우 권장).</span><span class="sxs-lookup"><span data-stu-id="70255-306">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![UEFI 암호를 입력합니다.](images/shm-fig22.png)
   
4. <span data-ttu-id="70255-308">UEFI 메뉴에서 **USB에서 관리**  >  **설치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-308">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![관리 및 US B에서 설치를 선택합니다.](images/shm-fig21.png)
   
5. <span data-ttu-id="70255-310">다음 **이미지와 같이**지금 다시 시작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-310">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="70255-311">장치가 다시부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-311">The device reboots.</span></span> <span data-ttu-id="70255-312">창 중간에 흰색 Microsoft 로고를 표시한 다음 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-312">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![지금 다시 시작을 선택합니다.](images/shm-fig25.png)
   
6. <span data-ttu-id="70255-314">전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-314">Press and release the power button.</span></span> <span data-ttu-id="70255-315">빨간색 창이 나타나면 Surface 엔터프라이즈 관리 모드를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-315">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="70255-316">2문자 인증서 지문과 UEFI 설정 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-316">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="70255-317">그런 다음 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70255-317">Then select **OK**.</span></span>

   ![2문자 인증서 지문과 UEFI 설정 암호를 입력합니다.](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="70255-319">장치에서 SEMM을 활성화하면 새 UEFI 설정 **EnableOSMigration이** 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-319">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="70255-320">더 이상 Windows 10 Team에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-320">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="70255-321">대신 다음 단계를 계속하고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-321">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="70255-322">장치가 다시부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-322">The device reboots.</span></span> <span data-ttu-id="70255-323">화면 중간에 흰색 로고를 표시한 다음 다시 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-323">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="70255-324">Windows 10 Pro 또는 Enterprise 설치</span><span class="sxs-lookup"><span data-stu-id="70255-324">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="70255-325">부팅 가능한 Windows 10 Pro 또는 Enterprise 드라이브가 Surface Hub 2 USB-A 포트에 아직 없는 경우 지금 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-325">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="70255-326">그런 다음 전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-326">Then press and release the power button.</span></span> 

    <span data-ttu-id="70255-327">디바이스가 시작되면 화면 중간에 흰색 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-327">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="70255-328">그런 다음 흰색 로고 아래에 회전하는 원이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-328">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="70255-329">장치가 자동으로 USB 드라이브로 부팅되지 않는 경우 디바이스를 끄세요(전원 코드를 끄고 다시 연결).</span><span class="sxs-lookup"><span data-stu-id="70255-329">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="70255-330">전원 코드를 다시 연결한 후 디바이스가 몇 초 후에 부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-330">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="70255-331">그런 다음 화면 중간에 흰색 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70255-331">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="70255-332">디바이스가 켜지 않은 경우 전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-332">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="70255-333">화면 중간에 로고가 표시되고 나면 볼륨 단추를 누르고 흰색 로고 아래에 회전하는 원이 표시될 때까지 단추를 누릅니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="70255-333">Immediately after you see the logo in the middle of the screen, press and hold the **Volume -** button until you see the spinning circle below the white logo.</span></span>
 
   ![U.S B 드라이브에서 Windows 10으로 부팅합니다.](images/shm-fig26.png)
   
4. <span data-ttu-id="70255-335">OOBE(첫 실행 경험) 설치가 시작되면 지침에 따라 Windows 10 Pro 또는 Enterprise(버전 1903 이상)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-335">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="70255-336">Surface Hub 2 드라이버 및 펌웨어 설치</span><span class="sxs-lookup"><span data-stu-id="70255-336">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="70255-337">장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-337">To ensure your device has all the latest updates and drivers, install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span> <span data-ttu-id="70255-338">드라이버 및 펌웨어 MSI를 설치한 후 장치를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-338">After installation of the drivers and firmware MSI, reboot the device.</span></span> <span data-ttu-id="70255-339">그런 다음 허브 전원을 다시 니다. PC 전원을 1시간 동안 유지한 후 장치를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="70255-339">Then, after powering the Hub back on, keep the PC power on for an hour and reboot the device again.</span></span> <span data-ttu-id="70255-340">두 번째 다시 시작하라는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-340">You will not be prompted for the second reboot.</span></span> <span data-ttu-id="70255-341">Windows 10 Pro 또는 Enterprise로 마이그레이션하기 전에 컴퓨터의 상태에 따라 모든 펌웨어가 업데이트되도록 이 두 번째 단계가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-341">Depending on the state of your machine prior to migrating to Windows 10 Pro or Enterprise, this second step may be needed to ensure all of the firmware has been updated.</span></span>
 
## <span data-ttu-id="70255-342">권장 설정 구성</span><span class="sxs-lookup"><span data-stu-id="70255-342">Configure recommended settings</span></span>

<span data-ttu-id="70255-343">Surface Hub 2S를 개인 생산성 장치로 완전히 구성하려면 <a href="surface-hub-2-post-install.md" target="_blank"> Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성을 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-343">To fully configure Surface Hub 2S as a personal productivity device, see <a href="surface-hub-2-post-install.md" target="_blank">Configure Windows 10 Pro or Enterprise on Surface Hub 2</a>.</span></span>

> [!NOTE]
><span data-ttu-id="70255-344">이 문서에 설명된 단계가 Surface Hub 2용 Windows 10 Pro 또는 Enterprise로 성공적으로 마이그레이션되지 않는 경우 Surface Hub 지원에 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> </a> 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-344">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub Support</a>.</span></span>

## <span data-ttu-id="70255-345">Windows 10 Team으로 롤백</span><span class="sxs-lookup"><span data-stu-id="70255-345">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="70255-346">디바이스를 Windows 10 Team으로 복원하려면 Surface Hub 2S에 대한 초기화 및 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 복구를 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70255-346">If you want to restore your device to Windows 10 Team, see <a href="surface-hub-2s-recover-reset.md" target="_blank"> Reset and recovery for Surface Hub 2S</a>.</span></span>

> [!NOTE]
> <span data-ttu-id="70255-347">Windows 10 Team으로 롤백하기 전에 SEMM에서 허브를 먼저 사용인증을 해지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-347">Before rolling back to Windows 10 Team, it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="70255-348">자세한 내용은 [SEMM에서 Surface 디바이스의 사용 안을 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="70255-348">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="70255-349">버전 기록</span><span class="sxs-lookup"><span data-stu-id="70255-349">Version history</span></span>

<span data-ttu-id="70255-350">다음 표에서는 이 문서의 변경 내용을 요약하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70255-350">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="70255-351">버전</span><span class="sxs-lookup"><span data-stu-id="70255-351">Version</span></span> | <span data-ttu-id="70255-352">Date</span><span class="sxs-lookup"><span data-stu-id="70255-352">Date</span></span>               | <span data-ttu-id="70255-353">설명</span><span class="sxs-lookup"><span data-stu-id="70255-353">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="70255-354">v.</span><span class="sxs-lookup"><span data-stu-id="70255-354">v.</span></span> <span data-ttu-id="70255-355">1.4</span><span class="sxs-lookup"><span data-stu-id="70255-355">1.4</span></span>  | <span data-ttu-id="70255-356">2020년 12월 14일</span><span class="sxs-lookup"><span data-stu-id="70255-356">December 14, 2020</span></span> | <span data-ttu-id="70255-357">"Surface Hub 2에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어"에 대한 MSI 파일을 설치하는 방법과 관련한 추가 정보를 제공합니다. 시스템의 상태에 따라 두 번째 재부팅이 필요할 수 있습니다. [](#install-surface-hub-2-drivers-and-firmware)</span><span class="sxs-lookup"><span data-stu-id="70255-357">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="70255-358">v.</span><span class="sxs-lookup"><span data-stu-id="70255-358">v.</span></span> <span data-ttu-id="70255-359">1.3</span><span class="sxs-lookup"><span data-stu-id="70255-359">1.3</span></span>  | <span data-ttu-id="70255-360">2020년 12월 3일</span><span class="sxs-lookup"><span data-stu-id="70255-360">December 3, 2020</span></span> | <span data-ttu-id="70255-361">SEMM 등록 관리에 대한 [지침으로 업데이트되었습니다.](#managing-semm-enrollment)</span><span class="sxs-lookup"><span data-stu-id="70255-361">Updated with guidance about [managing SEMM enrollment](#managing-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="70255-362">v.</span><span class="sxs-lookup"><span data-stu-id="70255-362">v.</span></span> <span data-ttu-id="70255-363">1.2</span><span class="sxs-lookup"><span data-stu-id="70255-363">1.2</span></span>  | <span data-ttu-id="70255-364">2020년 9월 29일</span><span class="sxs-lookup"><span data-stu-id="70255-364">September 29, 2020</span></span> | <span data-ttu-id="70255-365">사용 가능성 피드백을 해결 하는 기타 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="70255-365">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="70255-366">v.</span><span class="sxs-lookup"><span data-stu-id="70255-366">v.</span></span> <span data-ttu-id="70255-367">1.1</span><span class="sxs-lookup"><span data-stu-id="70255-367">1.1</span></span>  | <span data-ttu-id="70255-368">2020년 9월 15일</span><span class="sxs-lookup"><span data-stu-id="70255-368">September 15, 2020</span></span> | <span data-ttu-id="70255-369">새 OS를 설치하기 위한 라이선스 요구 사항을 명확히 설명하는 추가 참고 사항이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70255-369">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="70255-370">v.</span><span class="sxs-lookup"><span data-stu-id="70255-370">v.</span></span> <span data-ttu-id="70255-371">1.0</span><span class="sxs-lookup"><span data-stu-id="70255-371">1.0</span></span>  | <span data-ttu-id="70255-372">2020년 9월 1일</span><span class="sxs-lookup"><span data-stu-id="70255-372">September 1, 2020</span></span>  | <span data-ttu-id="70255-373">새 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="70255-373">New article.</span></span>                                                                                           |
