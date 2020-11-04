---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: 이 문서에서는 Surface Hub 2의 Windows 10 팀에서 windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 방법에 대해 설명 합니다.
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 713bd2e76f144b4dca7c0fad5c584b06ea12b0b5
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154141"
---
# <span data-ttu-id="9929c-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9929c-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="9929c-105">Surface Hub 2S는 Windows 10 팀에 사전 설치 되어 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-105">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="9929c-106">이 사용자 지정 버전의 Windows 10은 회의실 환경에서 공동 작업을 용이 하 게 하기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-106">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="9929c-107">이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용 하기 위해 Windows 10 Pro 또는 Enterprise를 실행 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="9929c-108">일반 업그레이드 또는 마이그레이션과 달리이 프로세스는이 문서에 설명 된 대로 규범적 절차를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="9929c-109">계속 하기 전에 [솔루션 구성 요소](#solution-components) 및 [마이그레이션 및 설치 워크플로](#migration-and-installation-workflow-summary) 를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="9929c-110">Windows 10 Pro 또는 Enterprise를 설치 하는 경우 기존 Windows 10 팀 라이선스와 별개인 새로운 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-110">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="9929c-111">별도의 PC 및 다운로드 가능한 도구 *SURFACE UEFI 구성자*를 사용 하 여 Windows 10 팀에서 마이그레이션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-111">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="9929c-112">이 도구를 사용 하 여 Surface Hub 2S에 적용 하는 새 UEFI 설정을 포함 하는 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-112">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="9929c-113">Surface UEFI 구성자는 Surface 엔터프라이즈 관리 모드 (SEMM)의 인터페이스로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-113">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="9929c-114">기업 환경에서 Surface 장치에 대 한 펌웨어 설정을 중앙에서 관리할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-114">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="9929c-115">자세한 내용은 [Microsoft SEMM 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-115">For more information, see the [Microsoft SEMM documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="9929c-116">솔루션 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9929c-116">Solution components</span></span>

- <span data-ttu-id="9929c-117">Windows 10 Team 운영 체제를 실행 하는 Surface Hub 2S 장치</span><span class="sxs-lookup"><span data-stu-id="9929c-117">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="9929c-118">Windows 10을 실행 하는 별도의 장치</span><span class="sxs-lookup"><span data-stu-id="9929c-118">Separate device running Windows 10</span></span>
- <span data-ttu-id="9929c-119">SEMM 패키지를 만들기 위한 Surface UEFI 구성자 도구</span><span class="sxs-lookup"><span data-stu-id="9929c-119">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="9929c-120">Windows 10 Pro 또는 엔터프라이즈 OS 이미지, 버전 1903 이상</span><span class="sxs-lookup"><span data-stu-id="9929c-120">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="9929c-121">16gb의 저장소, FAT32 형식으로 된 2 개의 USB 드라이브</span><span class="sxs-lookup"><span data-stu-id="9929c-121">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="9929c-122">Surface Hub 2 용 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어는 MSI (Microsoft Windows Installer) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-122">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="9929c-123">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="9929c-123">Internet connection</span></span>
- <span data-ttu-id="9929c-124">이미징 솔루션 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9929c-124">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="9929c-125">마이그레이션 및 설치 워크플로 요약</span><span class="sxs-lookup"><span data-stu-id="9929c-125">Migration and installation workflow summary</span></span>

| <span data-ttu-id="9929c-126">단계</span><span class="sxs-lookup"><span data-stu-id="9929c-126">Step</span></span>  | <span data-ttu-id="9929c-127">작업</span><span class="sxs-lookup"><span data-stu-id="9929c-127">Action</span></span>                                                                                                 | <span data-ttu-id="9929c-128">요약</span><span class="sxs-lookup"><span data-stu-id="9929c-128">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9929c-129">raid-1</span><span class="sxs-lookup"><span data-stu-id="9929c-129">1</span></span> | [<span data-ttu-id="9929c-130">Surface Hub의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인 2S.</span><span class="sxs-lookup"><span data-stu-id="9929c-130">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="9929c-131">UEFI 버전이 694.2938.768.0 이상 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-131">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="9929c-132">2</span><span class="sxs-lookup"><span data-stu-id="9929c-132">2</span></span> | [<span data-ttu-id="9929c-133">Surface UEFI 구성자 및 Surface Hub 2 드라이버와 펌웨어를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-133">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="9929c-134">[**IT에 대 한 Surface Tools**](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 **다운로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-134">On the [**Surface Tools for IT**](https://www.microsoft.com/download/details.aspx?id=46703) page, select **Download**.</span></span> <span data-ttu-id="9929c-135">그런 다음 Surface UEFI 구성자를 선택 하 여 다운로드 **합니다. MSI 파일** 을 만들고 별도의 PC에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-135">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="9929c-136">[Surface Hub 2 MSI 파일에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-136">Download the [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="9929c-137">5 단계에서 사용할 수 있도록 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-137">Save it for use in step 5.</span></span> |
| <span data-ttu-id="9929c-138">3-4</span><span class="sxs-lookup"><span data-stu-id="9929c-138">3</span></span> | [<span data-ttu-id="9929c-139">SEMM 인증서를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-139">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="9929c-140">Surface UEFI 구성자을 실행 하는 데 필요한 인증서를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-140">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="9929c-141">또는 현재 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-141">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="9929c-142">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="9929c-142">4</span></span> | [<span data-ttu-id="9929c-143">SEMM 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-143">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="9929c-144">Surface Hub 2S에 적용 해야 하는 구성 파일을 포함 하는 USB 드라이브에 SEMM 패키지를 만들기 위해 서피스 UEFI 구성자 시작</span><span class="sxs-lookup"><span data-stu-id="9929c-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="9929c-145">PC의 폴더에이 SEMM 패키지 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-145">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="9929c-146">5mb</span><span class="sxs-lookup"><span data-stu-id="9929c-146">5</span></span> | [<span data-ttu-id="9929c-147">Windows 10 용 이미지, SEMM 패키지, Surface Hub 2의 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어가 포함 된 USB 플래시 드라이브를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-147">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="9929c-148">Windows 10 이미지를 포함 하는 단일 USB 드라이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-148">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="9929c-149">이 예제에서 드라이브는 *Bootme*로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-149">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="9929c-150">Surface Hub 2 (단계 2) 및 SEMM 패키지 파일 (4 단계)에 Windows 10 Pro 및 Enterprise OS 용 드라이버와 펌웨어를 *추가 합니다.*</span><span class="sxs-lookup"><span data-stu-id="9929c-150">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="9929c-151">26</span><span class="sxs-lookup"><span data-stu-id="9929c-151">6</span></span> | [<span data-ttu-id="9929c-152">Surface Hub 2S에서 UEFI를 업데이트 하 여 OS 마이그레이션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-152">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="9929c-153">*Bootme* 드라이브를 사용 하 여 UEFI 메뉴로 부팅 Surface Hub 2S를 사용해 서 semm 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-153">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="9929c-154">7</span><span class="sxs-lookup"><span data-stu-id="9929c-154">7</span></span> | [<span data-ttu-id="9929c-155">Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-155">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="9929c-156">*Bootme* 드라이브를 사용 하 여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-156">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="9929c-157">20cm(8</span><span class="sxs-lookup"><span data-stu-id="9929c-157">8</span></span> | [<span data-ttu-id="9929c-158">Surface Hub 2에 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-158">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="9929c-159">장치에 최신 업데이트와 드라이버가 모두 포함 되도록 하려면 [Surface Hub 2 MSI 파일에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-159">To ensure your device has all the latest updates and drivers, install the [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="9929c-160">되었는지</span><span class="sxs-lookup"><span data-stu-id="9929c-160">9</span></span> | [<span data-ttu-id="9929c-161">Surface Hub 2S을 개인 생산성 장치로 완전히 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-161">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="9929c-162">Surface Hub 2S을 개인 생산성 장치로 최적화 하는 데 권장 설정 및 응용 프로그램을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-162">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="9929c-163">Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="9929c-163">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="9929c-164">Windows 10 Team에서 Windows 10 Desktop으로 Surface Hub를 마이그레이션하기 전에 적어도 *694.2938.768.0*인 UEFI 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-164">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
<span data-ttu-id="9929c-165">시스템에서 UEFI 버전을 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-165">To verify the UEFI version on your system:</span></span>

1. <span data-ttu-id="9929c-166">Surface Hub 2S 홈 페이지에서 **시작**을 선택 하 고 Surface app (**모든 앱**  >  **화면**)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-166">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="9929c-167">디바이스의 현재 UEFI 버전을 포함 하 여 Surface Hub에 대 한 정보를 표시 하려면 **화면** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-167">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="9929c-168">UEFI 버전이 *694.2938.768.0* 이상 이면 다음 이미지와 같이 OS 마이그레이션을 사용 하도록 설정 하는 semm 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-168">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![Surface 앱의 Surface 페이지를 보여 주는 스크린샷](images/shm-fig1.png)
 
   - <span data-ttu-id="9929c-170">UEFI 버전이 *694.2938.768.0*보다 이전인 경우 Windows Update를 사용 하 여 현재 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-170">If the UEFI version is earlier than *694.2938.768.0*, get a current version by using Windows Update.</span></span>

<span data-ttu-id="9929c-171">Windows Update를 사용 하 여 UEFI를 업데이트 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-171">To update the UEFI by using Windows Update:</span></span>

1. <span data-ttu-id="9929c-172">Surface Hub 2S에 **관리자로**로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-172">On your Surface Hub 2S, sign in as **Admin**.</span></span> 
    >[!Note]
    > <span data-ttu-id="9929c-173">사용자 이름 또는 관리자 암호를 모르는 경우에는 장치를 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-173">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="9929c-174">자세한 내용은 [Surface Hub 2S 다시 설정 및 복구](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-174">For more information, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

1. <span data-ttu-id="9929c-175">**모든 앱**  >  **설정**  >  **업데이트 및 보안**  >  **Windows 업데이트로**이동한 다음 모든 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-175">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 
1. <span data-ttu-id="9929c-176">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-176">Restart the device.</span></span> 
1. <span data-ttu-id="9929c-177">Surface 앱을 사용 하 여 UEFI 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-177">Verify the UEFI version by using the Surface app.</span></span> 
2. <span data-ttu-id="9929c-178">UEFI 버전이 *694.2938.768.0* 이상에 도달할 때까지이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-178">Repeat these steps until the UEFI version is *694.2938.768.0* or later.</span></span>
3. <span data-ttu-id="9929c-179">여러 번 시도한 후에 업데이트 된 UEFI가 표시 되지 않으면 **업데이트 기록을** 확인 하 고 실패 한 펌웨어 설치의 모든 인스턴스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-179">If you don't see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="9929c-180">장치를 다시 설정 해야 할 수 있습니다 (**설정**  >  **업데이트 & 보안**  >  **재설정 장치**).</span><span class="sxs-lookup"><span data-stu-id="9929c-180">You might need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="9929c-181">Surface UEFI 구성자 및 Surface Hub 2 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="9929c-181">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="9929c-182">별도의 PC에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-182">On a separate PC:</span></span>

1. <span data-ttu-id="9929c-183">[IT에 대 한 Surface Tools 페이지](https://www.microsoft.com/download/details.aspx?id=46703)에서 **다운로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-183">On the [Surface Tools for IT page](https://www.microsoft.com/download/details.aspx?id=46703), select **Download**.</span></span>  
1. <span data-ttu-id="9929c-184">Surface UEFI 구성자 MSI 파일을 선택 하 여 다운로드 하 고 별도의 PC에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-184">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="9929c-185">Windows 10 Team edition이 설치 되어 있는 동안 surface Hub 2S에서 Surface UEFI 구성자 도구를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-185">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="9929c-186">[Surface Hub 2 드라이버 및 펌웨어 Windows INSTALLER MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974)을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-186">Download the [Surface Hub 2 Drivers and Firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="9929c-187">새 운영 체제를 설치할 때이 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-187">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="9929c-188">SEMM 인증서 준비</span><span class="sxs-lookup"><span data-stu-id="9929c-188">Prepare the SEMM certificate</span></span>

<span data-ttu-id="9929c-189">이전에 Surface UEFI 구성자을 사용 하지 않은 경우에는 인증서를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-189">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="9929c-190">이 인증서는 디바이스를 SEMM에 등록 한 후에는 승인 된 인증서로 만든 패키지를 사용 하는 경우에만 UEFI 설정을 수정할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-190">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="9929c-191">인증서를 얻는 방법은 조직의 규모 또는 복잡도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-191">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="9929c-192">일반적으로 엔터프라이즈 조직은 표준 보안 관례에 따라 인증서를 생성 하는 고유한 인프라를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-192">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="9929c-193">중간 규모 기업과 다른 사용자가 파트너 공급자 로부터 인증서를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-193">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="9929c-194">이 옵션은 IT 전문 지식이 부족 하거나 전담 IT 보안 팀을 보유 하 고 있지 않은 조직에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-194">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="9929c-195">또는 PowerShell 스크립트를 사용 하 여 자체 서명 된 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-195">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="9929c-196">자세한 내용은 [Surface Enterprise 관리 모드 인증서 요구 사항을](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-196">For more information, see the [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="9929c-197">또는 PowerShell을 사용 하 여 고유한 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-197">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="9929c-198">자세한 내용은 [새로운 new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-198">For more information, see the [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) documentation.</span></span>

<span data-ttu-id="9929c-199">Surface UEFI 구성자가 생성 하는 SEMM 패키지는 인증서를 사용 하 여 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-199">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="9929c-200">이 인증서는 UEFI 설정을 적용할 수 있기 전에 구성 파일의 서명을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-200">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="9929c-201">자세한 내용은 [Semm 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-201">For more information, see the [SEMM documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 
 
### <span data-ttu-id="9929c-202">SEMM 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="9929c-202">Create a SEMM package</span></span>

1. <span data-ttu-id="9929c-203">별도의 PC에서 이전에 다운로드 한 Surface UEFI 구성자 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-203">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="9929c-204">Surface UEFI 구성자를 연 다음 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-204">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI 구성자를 엽니다.](images/shm-fig2.png)
   
3. <span data-ttu-id="9929c-206">**Surface 장치**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-206">Select **Surface Devices**, and then select **Next**.</span></span>

   ![Surface 장치를 선택 합니다.](images/shm-fig3.png)
  
4. <span data-ttu-id="9929c-208">**구성 패키지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-208">Select **Configuration Package**.</span></span>

   ![구성 패키지를 선택 합니다.](images/shm-fig4.png)
  
5. <span data-ttu-id="9929c-210">**인증서 보호**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-210">Select **Certificate Protection**.</span></span>

   ![인증서 보호를 선택 합니다.](images/shm-fig5.png)

   <span data-ttu-id="9929c-212">인증서 .pfx 파일을 추가 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-212">You're prompted to add your certificate .pfx file.</span></span>

   ![인증서를 추가 합니다.](images/shm-fig6.png)
   
7. <span data-ttu-id="9929c-214">인증서 암호를 입력 한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-214">Enter your certificate password, and then select **OK**.</span></span>

   ![인증서 암호를 입력 하 고 확인을 선택 합니다.](images/shm-fig7.png)

8. <span data-ttu-id="9929c-216">**암호 보호** 를 선택 하 여 Surface UEFI에 암호를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-216">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="9929c-217">UEFI로 부팅할 때마다이 암호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-217">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="9929c-218">Surface Hub 2S에서 사용할 UEFI 암호를 설정 하는 *것이 좋습니다* .</span><span class="sxs-lookup"><span data-stu-id="9929c-218">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![비밀 번호 보호를 선택 합니다.](images/shm-fig8.png)
   
9. <span data-ttu-id="9929c-220">UEFI 암호를 설정한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-220">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="9929c-221">Surface Hub를 관리 하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-221">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="9929c-222">암호가 손실 된 경우에는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-222">If the password is lost, it can't be recovered.</span></span> 

   ![UEFI 암호를 입력 합니다.](images/shm-fig9.png)

10. <span data-ttu-id="9929c-224">**Surface Hub 2S**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-224">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![Surface Hub 2S를 선택 합니다.](images/shm-fig10.png)
   
11. <span data-ttu-id="9929c-226">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-226">Select **Next**.</span></span>

    ![다음을 선택합니다.](images/shm-fig10a.png)

12. <span data-ttu-id="9929c-228">Windows 10 Pro 또는 Enterprise 설치를 허용 하려면 **Enableosmigration**을 설정 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-228">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![O S 마이그레이션 사용을 선택 합니다.](images/shm-fig11.png)
    
    ![OS 마이그레이션 사용을 On으로 설정 합니다.](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="9929c-231">SEMM 패키지를 적용 한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다 (잠금).</span><span class="sxs-lookup"><span data-stu-id="9929c-231">After you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="9929c-232">**PXE 부팅에 대 한 IPv6 등의** 다른 설정에 대 한 기본값도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-232">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 
>
><span data-ttu-id="9929c-233">마이그레이션을 완료 한 후 UEFI 설정을 변경 하려면 다른 SEMM 패키지를 적용 하거나 h m m m m m m m m m m m m m m m a m에서</span><span class="sxs-lookup"><span data-stu-id="9929c-233">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="9929c-234">다른 SEMM 패키지를 적용 하 여 UEFI 설정을 변경 하는 경우 새 SEMM 패키지를 빌드할 때 원래 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-234">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="9929c-235">UEFI 구성자 도구를 사용 하 고 기본 마이그레이션 단계와 같이 **Enableosmigration** 을 해제 (켜져 있지 않음) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-235">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="9929c-236">USB 드라이브에 SEMM 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="9929c-236">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="9929c-237">PC에 USB 드라이브를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-237">Connect a USB drive to your PC.</span></span> 
1. <span data-ttu-id="9929c-238">**Hub 2S**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-238">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![USB 선택](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="9929c-240">USB 드라이브의 모든 기존 데이터는 SEMM 패키지가 빌드될 때 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-240">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="9929c-241">SEMM 패키지를 작성 하기 전에 저장 하려는 USB 드라이브에서 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-241">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="9929c-242">**빌드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-242">Select **Build**.</span></span>

   ![빌드를 선택 합니다.](images/shm-fig14.png)

3. <span data-ttu-id="9929c-244">이 페이지의 스크린샷을 캡처한 다음 **End (종료**)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-244">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="9929c-245">이제 SEMM 패키지가 준비 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-245">Your SEMM package is now ready.</span></span> <span data-ttu-id="9929c-246">여기에는 semm 패키지 *Dfciupdate. dfi* 와 인증서의 손도장 (thumbprint)의 마지막 두 문자를 포함 하는 텍스트 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-246">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![종료를 선택 합니다.](images/shm-fig15.png)
   
4. <span data-ttu-id="9929c-248">인증서 지문의 마지막 두 문자를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-248">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="9929c-249">Surface Hub 2S에 패키지를 적용 하는 경우 SEMM을 활성화 하려면 이러한 문자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-249">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="9929c-250">Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어가 포함 된 USB 플래시 드라이브 준비</span><span class="sxs-lookup"><span data-stu-id="9929c-250">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="9929c-251">다음 옵션 중 하나를 사용 하 여 Windows 10 Pro 또는 엔터프라이즈 이미지 (버전 1903 이상)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-251">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="9929c-252">현재 이미징 솔루션.</span><span class="sxs-lookup"><span data-stu-id="9929c-252">Your current imaging solution.</span></span>

- <span data-ttu-id="9929c-253">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span><span class="sxs-lookup"><span data-stu-id="9929c-253">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span></span> <span data-ttu-id="9929c-254">이 도구를 사용 하 여 부팅 가능한 Windows 10 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-254">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="9929c-255">이미지에는 현재 Windows 10 업데이트, Office, 선택한 다른 앱, 필요한 드라이버 및 펌웨어가 모두 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-255">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="9929c-256">Windows 10 Pro 또는 엔터프라이즈 이미지를 포함 하는 USB 플래시 드라이브</span><span class="sxs-lookup"><span data-stu-id="9929c-256">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="9929c-257">그런 다음 [Surface Hub 2에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-257">Then install [drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
<span data-ttu-id="9929c-258">다음 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS 용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-258">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="9929c-259">다른 배포 방법을 사용 하는 경우이 문서의 [OS 마이그레이션 기능을 사용 하도록 설정 하는 Surface Hub 2S의 UEFI 업데이트](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 섹션으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-259">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="9929c-260">설치를 완료 한 후에는 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대 한 유효한 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-260">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="9929c-261">Windows 10 Pro 설치를 만들려면 [**windows 10 다운로드**](https://www.microsoft.com/software-download/windows10) 페이지에서 지침에 따라 미디어 만들기 도구를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-261">To create a Windows 10 Pro installation, on the [**Download Windows 10**](https://www.microsoft.com/software-download/windows10) page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="9929c-262">Windows 10 Enterprise를 다운로드 하려면 [Microsoft 볼륨 라이선스 서비스 센터로](https://www.microsoft.com/licensing/servicecenter/default.aspx)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-262">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="9929c-263">새 USB 저장소 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-263">Insert a new USB storage drive.</span></span> 
1. <span data-ttu-id="9929c-264">미디어 만들기 도구를 열고 **설치 미디어 만들기**를 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-264">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![설치 미디어를 만듭니다.](images/shm-fig16.png)
   
3. <span data-ttu-id="9929c-266">언어를 선택한 다음 **Windows 10** 및 **64 비트 (x64)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-266">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="9929c-267">그런 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-267">Then select **Next**.</span></span>

   ![언어를 선택 하 고 Windows 10 및 64 비트를 선택 합니다.](images/shm-fig17.png)
   
4. <span data-ttu-id="9929c-270">**USB 플래시 드라이브**를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-270">Select **USB flash drive**, and then select **Next**.</span></span>

   ![U B 플래시 드라이브를 선택 하 고 다음을 선택 합니다.](images/shm-fig18.png)
   
5. <span data-ttu-id="9929c-272">다운로드가 완료 되 면 **마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-272">When the download finishes, select **Finish**.</span></span>

   ![마침을 선택 합니다.](images/shm-fig19.png)
   
6. <span data-ttu-id="9929c-274">Windows 10 이미지를 포함 하는 USB 플래시 드라이브 (*부트*)의 루트에 Surface Hub 2 (MSI 파일)의 semm 패키지 파일과 드라이버 및 펌웨어를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-274">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="9929c-275">BOOTME USB 드라이브에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-275">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="9929c-276">Windows 10 부팅 가능 이미지</span><span class="sxs-lookup"><span data-stu-id="9929c-276">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="9929c-277">SEMM 패키지 파일 (USB 드라이브의 루트에 복사 됨).</span><span class="sxs-lookup"><span data-stu-id="9929c-277">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="9929c-278">*Dfciupdate. dfi*.</span><span class="sxs-lookup"><span data-stu-id="9929c-278">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="9929c-279">SEMM 지문을 포함 하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-279">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="9929c-280">(이 예제에서는 파일을 *SurfaceUEFI_2020Aug25_1058.txt*.) 자동으로 생성 된 날짜 시간 스탬프는 Surface UEFI Configurator를 사용 하 여 파일을 만든 날짜에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-280">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="9929c-281">Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)의 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어.</span><span class="sxs-lookup"><span data-stu-id="9929c-281">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="9929c-282">이 파일을 USB 드라이브의 루트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-282">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="9929c-283">OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI 업데이트</span><span class="sxs-lookup"><span data-stu-id="9929c-283">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="9929c-284">BOOTME 드라이브를 USB-A Surface Hub 2S의 포트에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-284">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="9929c-285">필수 파일 목록은 이전 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-285">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="9929c-286">UEFI로 부팅 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-286">To boot into UEFI:</span></span>

   1. <span data-ttu-id="9929c-287">Surface Hub 2S를 끄거나 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-287">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="9929c-288">**볼륨 +** 를 길게 누른 다음 전원 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-288">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="9929c-289">UEFI 메뉴가 나타날 때까지 지주 **볼륨 +** 를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-289">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![UEFI 메뉴가 나타날 때까지 볼륨 단추를 길게 누릅니다.](images/shm-fig20.png)
      
3. <span data-ttu-id="9929c-291">장치가 다시 시작 되 면 앞에서 만든 UEFI 암호 (해당 하는 경우)를 입력 합니다 (권장).</span><span class="sxs-lookup"><span data-stu-id="9929c-291">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![UEFI 암호를 입력 합니다.](images/shm-fig22.png)
   
4. <span data-ttu-id="9929c-293">UEFI 메뉴에서 **Management**  >  **USB에서 관리 설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-293">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![관리 및 U S B에서 설치를 선택 합니다.](images/shm-fig21.png)
   
5. <span data-ttu-id="9929c-295">다음 이미지가 표시 된 대로 **지금 다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-295">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="9929c-296">장치가 재부팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-296">The device reboots.</span></span> <span data-ttu-id="9929c-297">창 가운데에 흰색 Microsoft 로고가 표시 되 고 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-297">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![지금 다시 시작을 선택 합니다.](images/shm-fig25.png)
   
6. <span data-ttu-id="9929c-299">전원 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-299">Press and release the power button.</span></span> <span data-ttu-id="9929c-300">표시 되는 빨간색 창에서 Surface Enterprise 관리 모드를 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-300">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="9929c-301">2 자로 된 인증서 손도장과 UEFI 설정 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-301">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="9929c-302">그런 다음 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-302">Then select **OK**.</span></span>

   ![2 자로 된 인증서 손도장과 UEFI 설정 암호를 입력 합니다.](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="9929c-304">장치에서 SEMM을 활성화 하면 새 UEFI 설정 **Enableosmigration** 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-304">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="9929c-305">더 이상 Windows 10 팀에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-305">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="9929c-306">대신 다음 단계를 계속 하 고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-306">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="9929c-307">장치가 재부팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-307">The device reboots.</span></span> <span data-ttu-id="9929c-308">화면 중간에 흰색 로고를 표시 한 다음 다시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-308">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="9929c-309">Windows 10 Pro 또는 Enterprise 설치</span><span class="sxs-lookup"><span data-stu-id="9929c-309">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="9929c-310">부팅 가능 Windows 10 Pro 또는 엔터프라이즈 드라이브가 Surface Hub 2 USB-A 포트에 없는 경우 지금 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-310">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="9929c-311">그런 다음 전원 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-311">Then press and release the power button.</span></span> 

    <span data-ttu-id="9929c-312">장치가 시작 되 면 화면 가운데에 흰색 로고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-312">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="9929c-313">그런 다음 흰색 로고 아래에 회전 하는 원이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-313">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="9929c-314">장치가 자동으로 USB 드라이브로 부팅 되지 않으면 장치 전원을 끈 다음 (전원 코드를 뽑은 다음 다시 연결).</span><span class="sxs-lookup"><span data-stu-id="9929c-314">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="9929c-315">전원 코드를 다시 연결 하면 몇 초 후에 장치가 부팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-315">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="9929c-316">그러면 화면 가운데에 흰색 로고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-316">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="9929c-317">장치가 켜지 지 않으면 전원 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-317">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="9929c-318">화면 가운데에 로고가 표시 되 면 즉시 흰색 로고 아래에 회전 하는 원이 나타날 때까지 볼륨 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-318">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![U S B 드라이브에서 Windows 10으로 부팅 합니다.](images/shm-fig26.png)
   
4. <span data-ttu-id="9929c-320">OOBE (처음 실행 경험) 설정이 시작 되 면 지침에 따라 Windows 10 Pro 또는 Enterprise (버전 1903 이상)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-320">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="9929c-321">Surface Hub 2 드라이버 및 펌웨어 설치</span><span class="sxs-lookup"><span data-stu-id="9929c-321">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="9929c-322">장치에 최신 업데이트와 드라이버가 모두 있는지 확인 하려면 [Surface Hub 2에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-322">To ensure your device has all the latest updates and drivers, install [drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
## <span data-ttu-id="9929c-323">권장 설정 구성</span><span class="sxs-lookup"><span data-stu-id="9929c-323">Configure recommended settings</span></span>

<span data-ttu-id="9929c-324">Surface Hub 2S을 개인 생산성 장치로 완전히 구성 하려면 [Surface hub 2에서 Windows 10 Pro 또는 Enterprise 구성을](surface-hub-2-post-install.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-324">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="9929c-325">이 문서에서 설명 하는 단계가 Surface Hub 2 용 Windows 10 Pro 또는 Enterprise로 장치를 성공적으로 마이그레이션하지 못하는 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-325">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="9929c-326">Windows 10 팀으로 롤백</span><span class="sxs-lookup"><span data-stu-id="9929c-326">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="9929c-327">장치를 Windows 10 팀으로 복원 하려는 경우 [Surface Hub 2S 다시 설정 및 복구](surface-hub-2s-recover-reset.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9929c-327">If you want to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

## <span data-ttu-id="9929c-328">버전 기록</span><span class="sxs-lookup"><span data-stu-id="9929c-328">Version history</span></span>

<span data-ttu-id="9929c-329">다음 표에는이 문서의 변경 내용이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-329">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="9929c-330">버전</span><span class="sxs-lookup"><span data-stu-id="9929c-330">Version</span></span> | <span data-ttu-id="9929c-331">Date</span><span class="sxs-lookup"><span data-stu-id="9929c-331">Date</span></span>               | <span data-ttu-id="9929c-332">설명</span><span class="sxs-lookup"><span data-stu-id="9929c-332">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="9929c-333">variant.</span><span class="sxs-lookup"><span data-stu-id="9929c-333">v.</span></span> <span data-ttu-id="9929c-334">1.2</span><span class="sxs-lookup"><span data-stu-id="9929c-334">1.2</span></span>  | <span data-ttu-id="9929c-335">2020 년 9 월 29 일</span><span class="sxs-lookup"><span data-stu-id="9929c-335">September 29, 2020</span></span> | <span data-ttu-id="9929c-336">사용성 피드백을 처리 하는 기타 업데이트.</span><span class="sxs-lookup"><span data-stu-id="9929c-336">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="9929c-337">variant.</span><span class="sxs-lookup"><span data-stu-id="9929c-337">v.</span></span> <span data-ttu-id="9929c-338">1.1</span><span class="sxs-lookup"><span data-stu-id="9929c-338">1.1</span></span>  | <span data-ttu-id="9929c-339">2020 년 9 월 15 일</span><span class="sxs-lookup"><span data-stu-id="9929c-339">September 15, 2020</span></span> | <span data-ttu-id="9929c-340">새 OS 설치에 대 한 라이선스 요구 사항을 명확 하 게 설명 하는 추가 메모를 배치 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9929c-340">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="9929c-341">variant.</span><span class="sxs-lookup"><span data-stu-id="9929c-341">v.</span></span> <span data-ttu-id="9929c-342">1.0</span><span class="sxs-lookup"><span data-stu-id="9929c-342">1.0</span></span>  | <span data-ttu-id="9929c-343">2020 년 9 월 1 일</span><span class="sxs-lookup"><span data-stu-id="9929c-343">September 1, 2020</span></span>  | <span data-ttu-id="9929c-344">새 문서.</span><span class="sxs-lookup"><span data-stu-id="9929c-344">New article.</span></span>                                                                                           |
