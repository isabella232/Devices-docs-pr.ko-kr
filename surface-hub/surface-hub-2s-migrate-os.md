---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: Surface Hub 2의 Windows 10 Team에서 Windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 방법
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
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297641"
---
# <span data-ttu-id="2cf5d-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2cf5d-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="2cf5d-105">문서 버전 기록</span><span class="sxs-lookup"><span data-stu-id="2cf5d-105">Article version history</span></span>](#version-history)

<span data-ttu-id="2cf5d-106">Surface Hub 2S는 Windows 10 Team이 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-106">Surface Hub 2S comes with Windows 10 Team installed.</span></span> <span data-ttu-id="2cf5d-107">이 사용자 지정된 Windows 10 버전은 회의실 환경에서 공동 작업을 용이하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-107">This customized edition of Windows 10 facilitates collaboration in meeting-room environments.</span></span> <span data-ttu-id="2cf5d-108">이제 Windows 10 Pro 또는 Enterprise를 실행하여 다른 PC와 매우 마찬가지로 Surface Hub 2S를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-108">You can now instead run Windows 10 Pro or Enterprise to use your Surface Hub 2S much like any other PC.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cf5d-109">이 마이그레이션 프로세스를 수행하려면 이 문서에 설명된 특정 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-109">This migration process requires you to follow the specific procedure that's described in this article.</span></span> <span data-ttu-id="2cf5d-110">계속하기 전에 [솔루션](#solution-components) 구성 요소 및 마이그레이션 [및 설치 워크플로를 읽어 보십시오.](#migration-and-installation-workflow-summary)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-110">Before you continue, read [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary).</span></span>

> [!NOTE]
> <span data-ttu-id="2cf5d-111">Windows 10 Pro 또는 Enterprise를 설치할 때 기존 Windows 10 Team 라이선스와는 별개인 새 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span>

<span data-ttu-id="2cf5d-112">별도의 PC와 다운로드 가능한 Surface UEFI 구성기 도구를 사용하여 Windows *10 Team에서 마이그레이션을* 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable *Surface UEFI Configurator* tool.</span></span> <span data-ttu-id="2cf5d-113">이 도구는 Surface Hub 2S에 적용하는 새 UEFI 설정이 포함된 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-113">The tool creates a package that contains a new UEFI setting that you apply to the Surface Hub 2S.</span></span>  

<span data-ttu-id="2cf5d-114">Surface UEFI 구성기는 Surface SEMM(엔터프라이즈 관리 모드)의 인터페이스로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="2cf5d-115">회사 환경의 Surface 디바이스에서 펌웨어 설정을 중앙에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-115">It enables centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="2cf5d-116">자세한 내용은 Microsoft Surface 엔터프라이즈 관리 [모드를 참조하세요.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-116">For more information, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 
## <span data-ttu-id="2cf5d-117">솔루션 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2cf5d-117">Solution components</span></span>

- <span data-ttu-id="2cf5d-118">Windows 10 Team을 실행하는 Surface Hub 2S 장치</span><span class="sxs-lookup"><span data-stu-id="2cf5d-118">Surface Hub 2S device running Windows 10 Team</span></span>
- <span data-ttu-id="2cf5d-119">Windows 10을 실행하는 장치 분리</span><span class="sxs-lookup"><span data-stu-id="2cf5d-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="2cf5d-120">SEMM 패키지를 만들기 위한 Surface UEFI 구성기 도구</span><span class="sxs-lookup"><span data-stu-id="2cf5d-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="2cf5d-121">Windows 10 Pro 또는 Enterprise OS 이미지, 버전 1903 이상</span><span class="sxs-lookup"><span data-stu-id="2cf5d-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="2cf5d-122">저장소 용량이 16GB인 USB 드라이브 2개, FAT32 형식</span><span class="sxs-lookup"><span data-stu-id="2cf5d-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="2cf5d-123">Surface Hub 2 MSI(Windows 10 Pro 및 Enterprise) Microsoft Windows Installer 드라이버 및 펌웨어</span><span class="sxs-lookup"><span data-stu-id="2cf5d-123">The drivers and firmware for Windows 10 Pro and Enterprise in a Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="2cf5d-124">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="2cf5d-124">Internet connection</span></span>
- <span data-ttu-id="2cf5d-125">이미징 솔루션(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-125">Imaging solution (optional)</span></span>
 
## <span data-ttu-id="2cf5d-126">마이그레이션 및 설치 워크플로 요약</span><span class="sxs-lookup"><span data-stu-id="2cf5d-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="2cf5d-127">단계</span><span class="sxs-lookup"><span data-stu-id="2cf5d-127">Step</span></span>  | <span data-ttu-id="2cf5d-128">작업</span><span class="sxs-lookup"><span data-stu-id="2cf5d-128">Action</span></span>                                                                                                 | <span data-ttu-id="2cf5d-129">요약</span><span class="sxs-lookup"><span data-stu-id="2cf5d-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="2cf5d-130">1</span><span class="sxs-lookup"><span data-stu-id="2cf5d-130">1</span></span> | <span data-ttu-id="2cf5d-131">[Surface Hub 2S에서 UEFI 버전을 검증합니다.](#verify-the-uefi-version-on-surface-hub-2s)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-131">[Verify the UEFI version on the Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).</span></span>                                  | <span data-ttu-id="2cf5d-132">UEFI 버전은 *버전 694.2938.768.0 이상이* 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-132">The UEFI version must be version *694.2938.768.0* or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="2cf5d-133">2</span><span class="sxs-lookup"><span data-stu-id="2cf5d-133">2</span></span> | [<span data-ttu-id="2cf5d-134">Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-134">Download Surface UEFI Configurator and the Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="2cf5d-135">**[IT용 Surface 도구 페이지에서](https://www.microsoft.com/download/details.aspx?id=46703)** </a> 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-135">On the **[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** page</a>, select **Download**.</span></span> <span data-ttu-id="2cf5d-136">그런 다음 **Surface UEFI 구성기 MSI**파일을 선택하고 다운로드하여 별도의 PC에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-136">Then select and download the **Surface UEFI Configurator MSI file**, and install it on a separate PC.</span></span> <span data-ttu-id="2cf5d-137">또한 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 [펌웨어를 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-137">Also download the [Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span></a> <span data-ttu-id="2cf5d-138">5단계에서 사용하기 위해 이 패키지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-138">Save this package for use in step 5.</span></span> |
| <span data-ttu-id="2cf5d-139">3</span><span class="sxs-lookup"><span data-stu-id="2cf5d-139">3</span></span> | [<span data-ttu-id="2cf5d-140">SEMM 인증서를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-140">Prepare the SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="2cf5d-141">Surface UEFI 구성기 실행에 필요한 인증서를 준비하거나 현재 인증서를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-141">Prepare the certificate that's required to run Surface UEFI Configurator, or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="2cf5d-142">4</span><span class="sxs-lookup"><span data-stu-id="2cf5d-142">4</span></span> | [<span data-ttu-id="2cf5d-143">SEMM 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-143">Create a SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="2cf5d-144">Surface UEFI 구성을 시작하여 USB 드라이브에 SEMM 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive.</span></span> <span data-ttu-id="2cf5d-145">이 패키지에는 Surface Hub 2S에 적용해야 하는 구성 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-145">This package will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="2cf5d-146">이러한 SEMM 패키지 파일을 PC의 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="2cf5d-147">5</span><span class="sxs-lookup"><span data-stu-id="2cf5d-147">5</span></span> | [<span data-ttu-id="2cf5d-148">Windows 10 이미지, SEMM 패키지 및 드라이버와 펌웨어를 사용하여 USB 플래시 드라이브를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-148">Load a USB flash drive with Windows 10 image, the SEMM package, and drivers and firmware.</span></span>](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="2cf5d-149">Windows 10 이미지가 포함된 USB 드라이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-149">Create a USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="2cf5d-150">이 예제에서 드라이브의 이름은 *BOOTME입니다.*</span><span class="sxs-lookup"><span data-stu-id="2cf5d-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="2cf5d-151">Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어(2단계) 및 SEMM 패키지 파일(4단계)을 *BOOTME* 드라이브에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-151">Add the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (from step 2) and the SEMM package files (from step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="2cf5d-152">6</span><span class="sxs-lookup"><span data-stu-id="2cf5d-152">6</span></span> | [<span data-ttu-id="2cf5d-153">OS 마이그레이션을 사용하도록 Surface Hub 2S의 UEFI를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-153">Update the UEFI on the Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="2cf5d-154">*BOOTME* 드라이브를 사용하여 Surface Hub 2S를 UEFI 메뉴로 부팅하고 SEMM 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-154">Use the *BOOTME* drive to boot the Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="2cf5d-155">7</span><span class="sxs-lookup"><span data-stu-id="2cf5d-155">7</span></span> | [<span data-ttu-id="2cf5d-156">Windows 10 Pro 또는 Enterprise를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-156">Install Windows 10 Pro or Enterprise.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="2cf5d-157">*BOOTME* 드라이브를 사용하여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="2cf5d-158">8</span><span class="sxs-lookup"><span data-stu-id="2cf5d-158">8</span></span> | [<span data-ttu-id="2cf5d-159">Windows 10 Pro 및 Enterprise용 드라이버 및 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-159">Install drivers and firmware for Windows 10 Pro and Enterprise.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="2cf5d-160">장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-160">To ensure that your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="2cf5d-161">9</span><span class="sxs-lookup"><span data-stu-id="2cf5d-161">9</span></span> | [<span data-ttu-id="2cf5d-162">Surface Hub 2S를 개인 생산성 장치로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-162">Configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="2cf5d-163">권장 설정 및 응용 프로그램을 사용하여 Surface Hub 2S를 개인 생산성 장치로 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-163">Enable the recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="2cf5d-164">Surface Hub 2S에서 UEFI 버전 확인</span><span class="sxs-lookup"><span data-stu-id="2cf5d-164">Verify the UEFI version on Surface Hub 2S</span></span>

<span data-ttu-id="2cf5d-165">Surface Hub를 Windows 10 Team에서 Windows 10 Desktop으로 마이그레이션하기 전에 UEFI 버전 *694.2938.768.0* 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need UEFI version *694.2938.768.0* or later.</span></span>
 
**<span data-ttu-id="2cf5d-166">시스템에서 UEFI 버전을 확인:</span><span class="sxs-lookup"><span data-stu-id="2cf5d-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="2cf5d-167">Surface Hub 2S 홈 페이지에서 \*\*\*\* 시작을 선택한 다음 Surface 앱(모든 앱 Surface)을**니다.**  >  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2cf5d-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="2cf5d-168">Surface를 **선택하여** 디바이스의 현재 UEFI 버전을 포함하여 Surface Hub에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="2cf5d-169">UEFI 버전이 *694.2938.768.0* 이상인 경우 다음 이미지와 같이 SEMM 패키지를 만들어 OS 마이그레이션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)
 
   - <span data-ttu-id="2cf5d-171">UEFI 버전이 *버전 694.2938.768.0*이전인 경우 다음 방법 중 하나를 사용하여 최신 버전을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-171">If the UEFI version is earlier than version *694.2938.768.0*, use one of the following methods to get a newer version</span></span>
   
#### <span data-ttu-id="2cf5d-172">Windows 업데이트를 통해 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="2cf5d-172">Update UEFI via Windows Update</span></span>

1. <span data-ttu-id="2cf5d-173">Surface Hub 2S에서 관리자로 **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-173">On your Surface Hub 2S, sign in as **Admin**.</span></span>

    >[!Note]
    > <span data-ttu-id="2cf5d-174">사용자 이름 또는 관리자 암호를 모르는 경우 장치를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-174">If you don't know your user name or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="2cf5d-175">자세한 내용은 [Surface Hub 2S의 초기화 및 복구를 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-175">For more information, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

1. <span data-ttu-id="2cf5d-176">모든 앱 **설정**업데이트 및 보안 Windows 업데이트로 이동하여 모든  >  \*\*\*\*  >  \*\*\*\*  >  \*\*\*\* 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and install all updates.</span></span>
1. <span data-ttu-id="2cf5d-177">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-177">Restart the device.</span></span>
1. <span data-ttu-id="2cf5d-178">Surface 앱을 사용하여 UEFI 버전을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-178">Verify the UEFI version by using the Surface app.</span></span> <span data-ttu-id="2cf5d-179">UEFI 버전이 *694.2938.768.0* 이상이 아닌 경우 이러한 단계를 반복하거나 다음 절차에 따라 최신 UEFI 버전을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-179">If the UEFI version isn't version *694.2938.768.0* or later, repeat these steps, or use the following procedure to get the latest UEFI version.</span></span>

#### <span data-ttu-id="2cf5d-180">BMR(메탈 복구) 이미지를 통해 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="2cf5d-180">Update the UEFI via bare metal recovery (BMR) image</span></span>

1.  <span data-ttu-id="2cf5d-181">Surface 복구 [사이트로 이동하여](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.</span></span>
3.  <span data-ttu-id="2cf5d-182">허브 일련 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-182">Enter your Hub serial number.</span></span> <span data-ttu-id="2cf5d-183">이 위치는 전원 연결 옆에 있는 허브의 뒷면에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-183">It's located on the back of the Hub next to the power connection.</span></span>
4.  <span data-ttu-id="2cf5d-184">지시에 따라 Windows 10 Team 2020 업데이트를 설치하여 포맷된 USB 드라이브에 이미지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-184">Follow the directions to download the image onto a formatted USB drive by installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="2cf5d-185">업데이트 후 장치는 OOBE(첫 실행 경험) 설정으로 들어갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-185">After the update, the device enters out-of-box-experience (OOBE) setup.</span></span> <span data-ttu-id="2cf5d-186">설치를 완료할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-186">You don't need to complete setup.</span></span> <span data-ttu-id="2cf5d-187">UEFI 버전이 이미 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-187">The UEFI version is already updated.</span></span> <span data-ttu-id="2cf5d-188">대신 화면이 꺼질 때까지 전원 단추를 눌러 장치를 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-188">Instead power down the device by holding the power button until the screen turns off.</span></span>

### <span data-ttu-id="2cf5d-189">Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="2cf5d-189">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="2cf5d-190">별도의 PC에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-190">On a separate PC, follow these steps:</span></span>

1. <span data-ttu-id="2cf5d-191"><a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">IT용 Surface 도구 페이지에서 </a> 다운로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-191">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="2cf5d-192">Surface UEFI 구성기 MSI 파일을 선택하고 다운로드하여 별도의 PC에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-192">Select and download the Surface UEFI Configurator MSI file, and install it on a separate PC.</span></span> <span data-ttu-id="2cf5d-193">Windows 10 Team 버전이 설치된 동안 Surface Hub 2S에서는 Surface UEFI 구성기 도구를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-193">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="2cf5d-194">Surface [Hub 2 드라이버 및 펌웨어 Windows Installer MSI 파일을 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-194">Download the [Surface Hub 2 drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="2cf5d-195">새 운영 체제를 설치할 때 이 파일을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-195">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="2cf5d-196">SEMM 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="2cf5d-196">Prepare the SEMM certificate</span></span>

<span data-ttu-id="2cf5d-197">Surface UEFI 구성기 사용 전에 사용되지 않은 경우 인증서를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-197">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="2cf5d-198">이 인증서를 사용하면 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지만 사용하여 UEFI 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-198">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span>

<span data-ttu-id="2cf5d-199">인증서를 사용하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-199">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="2cf5d-200">엔터프라이즈 조직은 일반적으로 표준 보안 관행에 따라 인증서를 생성하기 위해 자체 인프라를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-200">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="2cf5d-201">중소기업 및 다른 기업은 파트너 공급자로부터 인증서를 받을 수 있는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-201">Medium-sized businesses and others often choose to get certificates from partner providers.</span></span> <span data-ttu-id="2cf5d-202">이 옵션은 IT 전문 지식이 부족하거나 전담 IT 보안 팀이 없는 조직에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-202">This option is recommended for organizations that don't have as much IT expertise or lack a dedicated IT security team.</span></span>

- <span data-ttu-id="2cf5d-203">또는 PowerShell 스크립트를 사용하여 자체 서명된 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-203">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="2cf5d-204">자세한 내용은 Surface 엔터프라이즈 관리 모드 인증서 요구 [사항을 참조하세요.](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-204">For more information, see the [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="2cf5d-205">또는 PowerShell을 사용하여 자체 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-205">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="2cf5d-206">자세한 내용은 [New-SelfSignedCertificate 설명서를](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-206">For more information, see the [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) documentation.</span></span>

<span data-ttu-id="2cf5d-207">Surface UEFI 구성기에서 만드는 SEMM 패키지는 인증서로 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-207">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="2cf5d-208">인증서는 UEFI 설정을 적용하기 전에 구성 파일의 서명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-208">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="2cf5d-209">자세한 내용은 [SEMM 설명서를 참조하십시오.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-209">For more information, see the [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
### <span data-ttu-id="2cf5d-210">SEMM 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="2cf5d-210">Create a SEMM package</span></span>

1. <span data-ttu-id="2cf5d-211">별도의 PC에서 앞서 다운로드한 Surface UEFI 구성기 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-211">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span>

1. <span data-ttu-id="2cf5d-212">Surface UEFI 구성기에서 시작을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-212">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI 구성기 시작 화면입니다.](images/shm-fig2.png)
   
1. <span data-ttu-id="2cf5d-214">**Surface 디바이스를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-214">Select **Surface Devices**, and then select **Next**.</span></span>

   ![Screenshot shows the Surface Devices option selected.](images/shm-fig3.png)
  
1. <span data-ttu-id="2cf5d-216">구성 **패키지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-216">Select **Configuration Package**.</span></span>

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. <span data-ttu-id="2cf5d-218">인증서 **보호를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-218">Select **Certificate Protection**.</span></span>

   ![스크린샷은 "인증서 보호 선택"을 선택하는 것입니다.](images/shm-fig5.png)

   <span data-ttu-id="2cf5d-220">인증서 .pfx 파일을 추가하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-220">You'll be prompted to add your certificate .pfx file.</span></span>

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)
   
1. <span data-ttu-id="2cf5d-222">인증서 암호를 입력하고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-222">Enter your certificate password, and then select **OK**.</span></span>

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. <span data-ttu-id="2cf5d-224">암호 **보호를 선택하여** Surface UEFI에 암호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-224">Select **Password Protection** to add a password to the Surface UEFI.</span></span> <span data-ttu-id="2cf5d-225">UEFI로 부팅할 때마다 이 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-225">You'll need this password whenever you boot to the UEFI.</span></span> *<span data-ttu-id="2cf5d-226">Surface Hub 2S에서 사용할 UEFI 암호를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-226">We strongly recommend that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)
   
1. <span data-ttu-id="2cf5d-228">UEFI 암호를 설정한 다음 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-228">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2cf5d-229">Surface Hub를 관리하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-229">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> *<span data-ttu-id="2cf5d-230">이 암호가 손실된 경우 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-230">If this password is lost, it can't be recovered.</span></span>*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. <span data-ttu-id="2cf5d-232">**Surface Hub 2S를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-232">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![Screenshot shows where to select Surface Hub 2S.](images/shm-fig10.png)
   
1. <span data-ttu-id="2cf5d-234">다음을 **다시** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-234">Select **Next** again.</span></span>

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. <span data-ttu-id="2cf5d-236">Windows 10 Pro 또는 Enterprise 설치를 허용하려면 **EnableOsMigration을**켜고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-236">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![SCREENSHOT shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### <span data-ttu-id="2cf5d-239">SEMM 등록 관리</span><span class="sxs-lookup"><span data-stu-id="2cf5d-239">Manage SEMM enrollment</span></span>

<span data-ttu-id="2cf5d-240">SEMM에 장치를 등록하면 디바이스를 관리하는 방법에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-240">Enrolling a device into SEMM affects how you can manage it.</span></span> <span data-ttu-id="2cf5d-241">예를 들어 SEMM 패키지를 적용한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다(잠겨).</span><span class="sxs-lookup"><span data-stu-id="2cf5d-241">For example, after you apply a SEMM package, all UEFI settings are unavailable (locked) in the device's UEFI menu.</span></span> <span data-ttu-id="2cf5d-242">PXE 부팅용 **IPv6과** 같은 다른 설정의 기본값도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-242">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span>

<span data-ttu-id="2cf5d-243">마이그레이션을 완료한 후 UEFI 설정을 변경하려면 다른 SEMM 패키지를 적용하거나 SEMM에서 디바이스의 인센토를 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-243">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="2cf5d-244">UEFI 설정을 변경하기 위해 다른 SEMM 패키지를 적용하는 경우 새 SEMM 패키지를 빌드할 때 원본 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-244">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="2cf5d-245">UEFI 구성기 도구를 사용하여 **EnableOSMigration을** \*\* \*\* 해제합니다(원래 마이그레이션 단계와는 다름).</span><span class="sxs-lookup"><span data-stu-id="2cf5d-245">Use the UEFI Configurator tool and leave **EnableOSMigration** *off* (not *on* as in the original migration steps).</span></span>

#### <span data-ttu-id="2cf5d-246">파트너와 작업하는 경우</span><span class="sxs-lookup"><span data-stu-id="2cf5d-246">If you work with partners</span></span>

<span data-ttu-id="2cf5d-247">회사에서 Surface Hub 2 마이그레이션을 Windows 10 Pro 또는 Enterprise로 아웃소싱하는 경우 파트너가 SEMM 인증서, SEMM 패키지 및 UEFI 암호를 전송하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-247">If your company outsources the Surface Hub 2 migration to Windows 10 Pro or Enterprise, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span> <span data-ttu-id="2cf5d-248">또는 허브를 마이그레이션한 후 SEMM에서 즉시 이 허브의 인스루를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-248">Or, after you migrate the Hub, you can immediately unenroll it from SEMM.</span></span> <span data-ttu-id="2cf5d-249">이 단계를 통해 UEFI의 로컬 관리와 디바이스를 다른 사용자로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-249">This step enables local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="2cf5d-250">하지만 마이그레이션 후 구성할 수 있는 UEFI 암호를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-250">But we still strongly recommend that you use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="2cf5d-251">자세한 내용은 [Surface UEFI 설정 관리를 참조하세요.](https://docs.microsoft.com/surface/manage-surface-uefi-settings)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-251">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="2cf5d-252">Windows 10 Team으로 롤백</span><span class="sxs-lookup"><span data-stu-id="2cf5d-252">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="2cf5d-253">이 문서 나중에 설명하는 마이그레이션 후 장치를 [](#to-roll-back-to-windows-10-team)Windows 10 Team으로 복원하도록 선택하는 경우 먼저 SEMM에서 허브의 선택을 해지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-253">If you choose to restore your device to Windows 10 Team after the migration [as described later in this article](#to-roll-back-to-windows-10-team), we recommend that you first unenroll Hub from SEMM.</span></span> <span data-ttu-id="2cf5d-254">자세한 내용은 SEMM에서 Surface 장치 사용 안 [끄기를 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-254">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

#### <span data-ttu-id="2cf5d-255">USB 드라이브에 SEMM 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="2cf5d-255">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="2cf5d-256">USB 드라이브를 PC에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-256">Connect a USB drive to your PC.</span></span>
1. <span data-ttu-id="2cf5d-257">허브 **2S를 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-257">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![Screenshot shows where to select Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="2cf5d-259">SEMM 패키지를 구축하면 USB 드라이브의 모든 기존 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-259">All existing data on the USB drive will be erased when the SEMM package is built.</span></span> <span data-ttu-id="2cf5d-260">SEMM 패키지를 빌드하기 전에 USB 드라이브에서 필요한 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-260">Before you build the SEMM package, remove any files that you need from the USB drive.</span></span>
   
1. <span data-ttu-id="2cf5d-261">빌드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-261">Select **Build**.</span></span>

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. <span data-ttu-id="2cf5d-263">이 페이지의 스크린샷을 캡처한 다음 종료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-263">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="2cf5d-264">이제 SEMM 패키지가 준비되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-264">Your SEMM package is now ready.</span></span> <span data-ttu-id="2cf5d-265">여기에는 SEMM 패키지 *DfciUpdate.dfi와* 인증서 지문의 마지막 두 문자인 *SEMM*지문이 포함된 텍스트 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-265">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM *thumbprint*, which is the last two characters of the certificate's thumbprint.</span></span>

   ![Screenshot shows where to select End.](images/shm-fig15.png)
   
4. <span data-ttu-id="2cf5d-267">인증서 지문의 마지막 두 문자를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-267">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="2cf5d-268">Surface Hub 2S에서 패키지를 적용할 때 SEMM을 활성화하려면 다음 문자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-268">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="2cf5d-269">Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어를 사용하여 USB 플래시 드라이브 로드</span><span class="sxs-lookup"><span data-stu-id="2cf5d-269">Load a USB flash drive with a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="2cf5d-270">다음 옵션 중 하나를 사용하여 Windows 10 Pro 또는 Enterprise 이미지(버전 *1903 이상)를* 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-270">You can install a Windows 10 Pro or Enterprise image (version *1903* or later) by using one of the following options:</span></span>

- <span data-ttu-id="2cf5d-271">현재 이미징 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-271">Your current imaging solution.</span></span>

- <span data-ttu-id="2cf5d-272">[Surface 배포 가속기.](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-272">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span></span> <span data-ttu-id="2cf5d-273">이 도구를 사용하여 부팅 가능한 Windows 10 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-273">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="2cf5d-274">이미지에는 모든 현재 Windows 10 업데이트, 업데이트, Microsoft Office 앱 및 필요한 드라이버 및 펌웨어가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-274">The image can include all current Windows 10 updates, Microsoft Office, other apps, and the required drivers and firmware.</span></span>

- <span data-ttu-id="2cf5d-275">Windows 10 Pro 또는 Enterprise 이미지가 포함된 USB 플래시 드라이브입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-275">A USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="2cf5d-276">그런 다음 Surface Hub [2에 Windows 10 Pro 및 Enterprise용 드라이버](https://www.microsoft.com/download/details.aspx?id=101974) 및 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-276">Then install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) on Surface Hub 2.</span></span>
 
<span data-ttu-id="2cf5d-277">다음 단계에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-277">The following steps show how to create a USB flash drive from installation media and then add the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="2cf5d-278">다른 배포 방법을 사용하는 경우 [Surface Hub 2S의 업데이트 UEFI로](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 이동하여 이 문서의 OS 마이그레이션 섹션을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-278">If you use another deployment method, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="2cf5d-279">설치를 완료한 후 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대한 유효한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-279">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="2cf5d-280">Windows 10 Pro 설치를 만들하려면 지침에 따라 Windows 10 다운로드에서 미디어 만들기 [도구를 다운로드합니다.](https://www.microsoft.com/software-download/windows10)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-280">To create a Windows 10 Pro installation, follow the instructions to download the media creation tool at [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span> <span data-ttu-id="2cf5d-281">Windows 10 Enterprise를 다운로드하려면 Microsoft 볼륨 라이선스 서비스 [센터로 이동해야 합니다.](https://www.microsoft.com/licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-281">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

1. <span data-ttu-id="2cf5d-282">새 USB 저장소 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-282">Insert a new USB storage drive.</span></span>
1. <span data-ttu-id="2cf5d-283">미디어 만들기 도구를 열고 설치 **미디어 만들기를**선택한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-283">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)
   
3. <span data-ttu-id="2cf5d-285">언어를 선택한 다음 **Windows 10** 및 **64비트(x64)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-285">Select a language, and then select **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="2cf5d-286">그런 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-286">Then select **Next**.</span></span>

   ![Screenshot shows where you select the language, O S edition, and architecture type.](images/shm-fig17.png)
   
4. <span data-ttu-id="2cf5d-288">**USB 플래시 드라이브를**선택하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-288">Select **USB flash drive**, and then select **Next**.</span></span>

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)
   
5. <span data-ttu-id="2cf5d-290">다운로드가 완료되면 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-290">When the download finishes, select **Finish**.</span></span>

   ![화면에서는 U S B 드라이브가 준비되어 완료 단추가 포함되어 있는 것으로 보고합니다.](images/shm-fig19.png)
   
6. <span data-ttu-id="2cf5d-292">Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어와 SEMM 패키지 파일을 Windows 10 이미지가 포함된 USB 플래시*드라이브(BOOTME)의*루트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-292">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="2cf5d-293">BOOTME USB 드라이브에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-293">The BOOTME USB drive will contain:</span></span>

    - <span data-ttu-id="2cf5d-294">Windows 10 부팅 가능 이미지.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-294">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="2cf5d-295">USB 드라이브의 루트에 복사된 SEMM 패키지 파일:</span><span class="sxs-lookup"><span data-stu-id="2cf5d-295">The SEMM package files, copied to the root of the USB drive:</span></span>
    
      - <span data-ttu-id="2cf5d-296">*DfciUpdate.dfi*.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-296">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="2cf5d-297">SEMM 지문을 포함하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-297">A text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="2cf5d-298">이 예제에서는 파일이SurfaceUEFI_2020Aug25_1058.txt\* .) \* 자동으로 생성된 날짜-시간 스탬프는 Surface UEFI 구성기에서 파일을 만든 날짜에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-298">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date-time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="2cf5d-299">Surface Hub 2(Windows 10 Pro 및 Enterprise OS)의 드라이버 및 펌웨어(SurfaceHub2S_Win10_18362_20.082.25682.0.msi.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-299">The drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="2cf5d-300">이 파일을 USB 드라이브의 루트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-300">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="2cf5d-301">OS 마이그레이션을 사용하도록 Surface Hub 2S에서 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="2cf5d-301">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="2cf5d-302">SURFACE Hub 2S의 USB-A 포트에 BOOTME 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-302">Insert your BOOTME drive into the USB-A port on the Surface Hub 2S.</span></span> <span data-ttu-id="2cf5d-303">필요한 콘텐츠 목록은 이전 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-303">For a list of its required contents, see the previous section.</span></span>

1. <span data-ttu-id="2cf5d-304">UEFI로 부팅하는 경우:</span><span class="sxs-lookup"><span data-stu-id="2cf5d-304">To boot into UEFI:</span></span>

   1. <span data-ttu-id="2cf5d-305">Surface Hub 2S를 끄고(종료).</span><span class="sxs-lookup"><span data-stu-id="2cf5d-305">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="2cf5d-306">Volume **+ 를 누르고**전원 단추를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-306">Press and hold **Volume +**, and then press and release the power button.</span></span> <span data-ttu-id="2cf5d-307">UEFI **메뉴가 나타날** 때까지 볼륨 + 유지</span><span class="sxs-lookup"><span data-stu-id="2cf5d-307">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![그리기에는 볼륨 및 전원 단추가 표시됩니다.](images/shm-fig20.png)
      
3. <span data-ttu-id="2cf5d-309">장치가 다시 시작되면 앞에서 만든 UEFI 암호를 입력합니다(해당되는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cf5d-309">When the device restarts, enter the UEFI password that you created earlier, if applicable (recommended).</span></span>

   ![시스템 암호 화면](images/shm-fig22.png)
   
4. <span data-ttu-id="2cf5d-311">UEFI 메뉴에서 관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-311">From the UEFI menu, select **Management**.</span></span> <span data-ttu-id="2cf5d-312">그런 다음 **USB에서 설치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-312">Then select  **Install from USB**.</span></span>

   ![Screenshot shows where to select Management and then Install from U S B".](images/shm-fig21.png)
   
5. <span data-ttu-id="2cf5d-314">다음 **이미지와 같이**지금 다시 시작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-314">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="2cf5d-315">장치가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-315">The device will restart.</span></span> <span data-ttu-id="2cf5d-316">창 중간에 흰색 Microsoft 로고가 표시된 다음 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-316">It will display a white Microsoft logo in the middle of the window and then shut down.</span></span>

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. <span data-ttu-id="2cf5d-318">전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-318">Press and release the power button.</span></span> <span data-ttu-id="2cf5d-319">빨간색 대화 상자가 나타나면 Surface 엔터프라이즈 관리 모드를 활성화할지 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-319">In the red dialog box that appears, choose to activate Surface Enterprise Management Mode.</span></span>

7. <span data-ttu-id="2cf5d-320">2문자 인증서 지문과 UEFI 설정 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-320">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="2cf5d-321">그런 다음 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2cf5d-321">Then select **OK**.</span></span>

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="2cf5d-323">장치에서 SEMM을 활성화하면 새 UEFI 설정 **EnableOSMigration이** 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-323">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="2cf5d-324">더 이상 Windows 10 Team에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-324">You can no longer access Windows 10 Team.</span></span> <span data-ttu-id="2cf5d-325">대신 다음 단계를 계속하고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-325">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span>

   <span data-ttu-id="2cf5d-326">장치가 다시부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-326">The device reboots.</span></span> <span data-ttu-id="2cf5d-327">화면 중간에 흰색 로고를 표시한 다음 다시 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-327">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="2cf5d-328">Windows 10 Pro 또는 Enterprise 설치</span><span class="sxs-lookup"><span data-stu-id="2cf5d-328">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="2cf5d-329">부팅 가능한 Windows 10 Pro 또는 Enterprise 드라이브가 Surface Hub 2 USB-A 포트에 아직 없는 경우 지금 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-329">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="2cf5d-330">그런 다음 전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-330">Then press and release the power button.</span></span>

    <span data-ttu-id="2cf5d-331">디바이스가 시작되면 화면 중간에 흰색 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-331">When the device starts, you'll see the white logo in the middle of the screen.</span></span> <span data-ttu-id="2cf5d-332">그런 다음 회전하는 원이 흰색 로고 아래에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-332">Then a spinning circle appears below the white logo.</span></span>

3. <span data-ttu-id="2cf5d-333">Surface 디바이스가 USB 드라이브로 자동으로 부팅되지 않는 경우 디바이스를 끄십시오(전원 코드를 끄고 다시 연결).</span><span class="sxs-lookup"><span data-stu-id="2cf5d-333">If the Surface device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="2cf5d-334">전원 코드를 다시 연결한 후 디바이스가 몇 초 후에 부팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-334">After you plug in the power cord again, the device should boot after a few seconds.</span></span> <span data-ttu-id="2cf5d-335">그런 다음 화면 중간에 흰색 로고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-335">Then you'll see the white logo in the middle of screen.</span></span>

    <span data-ttu-id="2cf5d-336">디바이스가 켜지 않은 경우 전원 단추를 누르고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-336">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="2cf5d-337">화면 중간에 로고가 표시될 때 흰색 로고 아래에 회전하는 원이 표시될 때까지 볼륨 단추를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-337">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![볼륨 및 전원 단추의 그림입니다.](images/shm-fig26.png)
   
4. <span data-ttu-id="2cf5d-339">OOBE(첫 실행 경험) 설치가 시작되면 지침에 따라 Windows 10 Pro 또는 Enterprise(버전 1903 이상)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-339">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="2cf5d-340">Surface Hub 2 드라이버 및 펌웨어 설치</span><span class="sxs-lookup"><span data-stu-id="2cf5d-340">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="2cf5d-341">Surface Hub 2가 최신 버전이 되도록 [Windows 10 Pro](https://www.microsoft.com/download/details.aspx?id=101974)및 Enterprise용 드라이버 및 펌웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-341">To ensure that your Surface Hub 2 is up to date, install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="2cf5d-342">그런 다음 장치를 다시 부트합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-342">Then reboot the device.</span></span> <span data-ttu-id="2cf5d-343">Surface를 한 시간 동안 켜진 후 다시 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-343">Keep the Surface turned on for an hour, and then reboot it again.</span></span> <span data-ttu-id="2cf5d-344">두 번째 다시 시작하라는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-344">You won't be prompted for the second reboot.</span></span> <span data-ttu-id="2cf5d-345">이 일시 중지 및 추가 재부팅을 통해 펌웨어가 완전히 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-345">This pause and extra reboot ensures that the firmware has been fully updated.</span></span>
 
## <span data-ttu-id="2cf5d-346">권장 설정 구성</span><span class="sxs-lookup"><span data-stu-id="2cf5d-346">Configure recommended settings</span></span>

<span data-ttu-id="2cf5d-347">Surface Hub 2S를 개인 생산성 장치로 구성하려면 [Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성을 참조하세요.](surface-hub-2-post-install.md)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-347">To configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="2cf5d-348">이 문서에 설명된 단계에 따라 디바이스를 Windows 10 Pro 또는 Enterprise for Surface Hub 2로 성공적으로 마이그레이션할 수 없는 경우 Surface Hub 지원에 [문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-348">If you can't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2 by following the steps outlined in this article, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="2cf5d-349">Windows 10 Team으로 롤백</span><span class="sxs-lookup"><span data-stu-id="2cf5d-349">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="2cf5d-350">디바이스를 Windows 10 Team으로 복원하려면 [Surface Hub 2S에](surface-hub-2s-recover-reset.md)대한 초기화 및 복구를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-350">If you want to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2cf5d-351">Windows 10 Team으로 롤백하기 전에 먼저 SEMM에서 Surface Hub를 열지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-351">Before you roll back to Windows 10 Team, we recommended that you first unenroll the Surface Hub from SEMM.</span></span> <span data-ttu-id="2cf5d-352">자세한 내용은 SEMM에서 Surface 장치 사용 안 [끄기를 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-352">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="2cf5d-353">버전 기록</span><span class="sxs-lookup"><span data-stu-id="2cf5d-353">Version history</span></span>

<span data-ttu-id="2cf5d-354">다음 표에서는 이 문서의 변경 내용을 요약하여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-354">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="2cf5d-355">버전</span><span class="sxs-lookup"><span data-stu-id="2cf5d-355">Version</span></span> | <span data-ttu-id="2cf5d-356">Date</span><span class="sxs-lookup"><span data-stu-id="2cf5d-356">Date</span></span>               | <span data-ttu-id="2cf5d-357">설명</span><span class="sxs-lookup"><span data-stu-id="2cf5d-357">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="2cf5d-358">v.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-358">v.</span></span> <span data-ttu-id="2cf5d-359">1.4</span><span class="sxs-lookup"><span data-stu-id="2cf5d-359">1.4</span></span>  | <span data-ttu-id="2cf5d-360">2020년 12월 14일</span><span class="sxs-lookup"><span data-stu-id="2cf5d-360">December 14, 2020</span></span> | <span data-ttu-id="2cf5d-361">"Surface Hub 2에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어"에 대한 MSI 파일을 설치하는 방법과 관련한 추가 정보를 제공합니다. 시스템의 상태에 따라 두 번째 재부팅이 필요할 수 있습니다. [](#install-surface-hub-2-drivers-and-firmware)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-361">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="2cf5d-362">v.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-362">v.</span></span> <span data-ttu-id="2cf5d-363">1.3</span><span class="sxs-lookup"><span data-stu-id="2cf5d-363">1.3</span></span>  | <span data-ttu-id="2cf5d-364">2020년 12월 3일</span><span class="sxs-lookup"><span data-stu-id="2cf5d-364">December 3, 2020</span></span> | <span data-ttu-id="2cf5d-365">SEMM 등록 관리에 대한 [지침으로 업데이트되었습니다.](#manage-semm-enrollment)</span><span class="sxs-lookup"><span data-stu-id="2cf5d-365">Updated with guidance about [managing SEMM enrollment](#manage-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="2cf5d-366">v.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-366">v.</span></span> <span data-ttu-id="2cf5d-367">1.2</span><span class="sxs-lookup"><span data-stu-id="2cf5d-367">1.2</span></span>  | <span data-ttu-id="2cf5d-368">2020년 9월 29일</span><span class="sxs-lookup"><span data-stu-id="2cf5d-368">September 29, 2020</span></span> | <span data-ttu-id="2cf5d-369">사용 가능성 피드백을 해결 하는 기타 업데이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-369">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="2cf5d-370">v.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-370">v.</span></span> <span data-ttu-id="2cf5d-371">1.1</span><span class="sxs-lookup"><span data-stu-id="2cf5d-371">1.1</span></span>  | <span data-ttu-id="2cf5d-372">2020년 9월 15일</span><span class="sxs-lookup"><span data-stu-id="2cf5d-372">September 15, 2020</span></span> | <span data-ttu-id="2cf5d-373">새 OS를 설치하기 위한 라이선스 요구 사항을 명확히 설명하는 추가 참고 사항을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-373">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="2cf5d-374">v.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-374">v.</span></span> <span data-ttu-id="2cf5d-375">1.0</span><span class="sxs-lookup"><span data-stu-id="2cf5d-375">1.0</span></span>  | <span data-ttu-id="2cf5d-376">2020년 9월 1일</span><span class="sxs-lookup"><span data-stu-id="2cf5d-376">September 1, 2020</span></span>  | <span data-ttu-id="2cf5d-377">새 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf5d-377">New article.</span></span>                                                                                           |
