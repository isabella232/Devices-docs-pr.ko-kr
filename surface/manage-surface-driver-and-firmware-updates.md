---
title: Surface 드라이버 및 펌웨어 업데이트 관리 및 배포
description: 이 문서에서는 Surface 장치에 대 한 펌웨어 및 드라이버 업데이트를 관리 하 고 배포 하는 데 사용할 수 있는 옵션을 설명 합니다.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, 펌웨어, 업데이트, 디바이스, 관리, 배포, 드라이버, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 91cde5fdf4a7745d491bd2eb928baca75955b90d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835084"
---
# <span data-ttu-id="4e884-104">Surface 드라이버 및 펌웨어 업데이트 관리 및 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-104">Manage and deploy Surface driver and firmware updates</span></span>

<span data-ttu-id="4e884-105">화면 드라이버와 펌웨어 업데이트를 관리 하는 방법은 환경과 조직의 요구 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-105">How you manage Surface driver and firmware updates varies depending on your environment and organizational requirements.</span></span> <span data-ttu-id="4e884-106">Surface 디바이스에서 펌웨어는 운영 체제에 드라이버로 표시 되며 장치 관리자에서 장치 펌웨어와 드라이버를 Windows Update 또는 비즈니스용 Windows 업데이트를 사용 하 여 자동으로 업데이트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-106">On Surface devices, firmware is exposed to the operating system as a driver and is visible in Device Manager, enabling device firmware and drivers to be automatically updated using Windows Update or Windows Update for Business.</span></span> <span data-ttu-id="4e884-107">이 간편한 접근 방법은 시작과 중소기업 또는 중간 규모의 기업에 게 적합 하지만 일반적으로 대규모 조직에서는 업데이트를 내부적으로 배포 하기 위해 IT 관리자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-107">Although this simplified approach may be feasible for startups and small or medium-sized businesses, larger organizations typically need IT admins to distribute updates internally.</span></span> <span data-ttu-id="4e884-108">여기에는 종합적인 계획, 응용 프로그램 호환성 테스트, 파일럿 및 검증 업데이트가 포함 되어 최종 승인 및 네트워크를 통해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-108">This may involve comprehensive planning, application compatibility testing, piloting and validating updates, before final approval and distribution across the network.</span></span>

> [!NOTE]
> <span data-ttu-id="4e884-109">이 문서는 기술 지원 에이전트 및 IT 전문가를 대상으로 하며 Surface 디바이스에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-109">This article is intended for technical support agents and IT professionals and applies to Surface devices only.</span></span> <span data-ttu-id="4e884-110">홈 장치에 Surface update 또는 펌웨어를 설치 하는 데 도움이 필요한 경우 [surface 펌웨어 및 Windows 10 업데이트](https://support.microsoft.com/help/4023505)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-110">If you're looking for help to install Surface updates or firmware on a home device, see [Update Surface firmware and Windows 10](https://support.microsoft.com/help/4023505).</span></span>

<span data-ttu-id="4e884-111">엔터프라이즈 등급 소프트웨어 배포 솔루션이 계속 발전 하는 동안 중앙 집중적으로 관리 하는 비즈니스의 보안을 유지 하는 것은 그대로 유지 되며, 최신 운영 체제 및 기능 향상으로 업데이트 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-111">While enterprise-grade software distribution solutions continue to evolve, the business rationale for centrally managing  updates remains the same: Maintain the security of Surface devices and keep them updated with the latest operating system and feature improvements.</span></span> <span data-ttu-id="4e884-112">이는 안정적인 프로덕션 환경을 유지 하 고 사용자가 생산성을 유지 하는 것이 차단 되지 않도록 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-112">This is essential for sustaining a stable production environment and ensuring users aren't blocked from being productive.</span></span> <span data-ttu-id="4e884-113">이 문서에서는 대규모 조직에서 이러한 목표를 달성 하는 데 권장 되는 도구 및 프로세스에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-113">This article provides an overview of recommended tools and processes for larger organizations to accomplish these goals.</span></span>

## <span data-ttu-id="4e884-114">상업용 환경의 중앙 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="4e884-114">Central update management in commercial environments</span></span>

<span data-ttu-id="4e884-115">Microsoft는 드라이버 및 펌웨어 업데이트를 포함 하 여 장치를 관리 하는 효율적인 도구를 제공 하며, devicemanagement.microsoft.com에서 액세스 하는 [Microsoft Endpoint Manager 관리 센터](https://devicemanagement.microsoft.com/) 라는 단일 통합 환경으로,</span><span class="sxs-lookup"><span data-stu-id="4e884-115">Microsoft has streamlined tools for managing devices – including driver and firmware updates -- into a single unified experience called [Microsoft Endpoint Manager admin center](https://devicemanagement.microsoft.com/) accessed from devicemanagement.microsoft.com.</span></span>

### <span data-ttu-id="4e884-116">Configuration Manager 및 Intune을 사용 하 여 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="4e884-116">Manage updates with Configuration Manager and Intune</span></span>

<span data-ttu-id="4e884-117">Microsoft Endpoint Configuration Manager를 사용 하 여 Surface 펌웨어와 드라이버 업데이트를 Configuration Manager 클라이언트와 동기화 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-117">Microsoft Endpoint Configuration Manager allows you to synchronize and deploy Surface firmware and driver updates with the Configuration Manager client.</span></span> <span data-ttu-id="4e884-118">Microsoft Intune과 통합 하면 관리 되는 공동 관리 및 파트너 관리 장치를 한 곳에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-118">Integration with Microsoft Intune lets you see all your managed, co-managed, and partner-managed devices in one place.</span></span> <span data-ttu-id="4e884-119">이는 대규모 조직에서 Surface update를 관리 하는 데 권장 되는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-119">This is the recommended solution for large organizations to manage Surface updates.</span></span>

<span data-ttu-id="4e884-120">자세한 단계는 다음 리소스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-120">For detailed steps, see the following resources:</span></span>

- [<span data-ttu-id="4e884-121">Configuration Manager에서 화면 드라이버 업데이트를 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4e884-121">How to manage Surface driver updates in Configuration Manager</span></span>](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [<span data-ttu-id="4e884-122">Configuration Manager를 사용 하 여 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-122">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [<span data-ttu-id="4e884-123">끝점 구성 관리자 설명서</span><span class="sxs-lookup"><span data-stu-id="4e884-123">Endpoint Configuration Manager documentation</span></span>](https://docs.microsoft.com/configmgr/)

### <span data-ttu-id="4e884-124">Microsoft 배포 도구 키트를 사용 하 여 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="4e884-124">Manage updates with Microsoft Deployment Toolkit</span></span>

<span data-ttu-id="4e884-125">끝점 구성 관리자에 포함 된 MDT (Microsoft 배포 도구 키트)에는 환경에 따라 사용할 수 있는 선택적 배포 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-125">Included in Endpoint Configuration Manager, the Microsoft Deployment Toolkit (MDT) contains optional deployment tools that you may wish to use depending on your environment.</span></span> <span data-ttu-id="4e884-126">여기에는 windows ADK (평가 및 배포 키트), windows SIM (배포 이미지 서비스 및 관리) 및 USMT (사용자 상태 마이그레이션 도구)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-126">These include the Windows Assessment and Deployment Kit (Windows ADK), Windows System Image Manager (Windows SIM), Deployment Image Servicing and Management (DISM), and User State Migration Tool (USMT).</span></span> <span data-ttu-id="4e884-127">[Microsoft 배포 툴킷 다운로드 페이지](https://www.microsoft.com/download/details.aspx?id=54259)에서 최신 버전의 MDT를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-127">You can download the latest version of MDT from the [Microsoft Deployment Toolkit download page](https://www.microsoft.com/download/details.aspx?id=54259).</span></span>

<span data-ttu-id="4e884-128">자세한 단계는 다음 리소스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-128">For detailed steps, see the following resources:</span></span>

- [<span data-ttu-id="4e884-129">Microsoft 배포 도구 키트 문서</span><span class="sxs-lookup"><span data-stu-id="4e884-129">Microsoft Deployment Toolkit documentation</span></span>](https://docs.microsoft.com/configmgr/mdt/)
- [<span data-ttu-id="4e884-130">Microsoft Deployment Toolkit을 사용하여 Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-130">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [<span data-ttu-id="4e884-131">Microsoft 배포 도구 키트를 사용 하 여 Windows 10을 Surface 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-131">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

<span data-ttu-id="4e884-132">Surface driver 및 펌웨어 업데이트는 Windows Installer (\* .msi) 파일로 패키지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-132">Surface driver and firmware updates are packaged as Windows Installer (\*.msi) files.</span></span> <span data-ttu-id="4e884-133">이러한 Windows Installer 패키지를 배포 하려면 끝점 구성 관리자 또는 MDT를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-133">To deploy these Windows Installer packages, you can use Endpoint Configuration Manager or MDT.</span></span> <span data-ttu-id="4e884-134">장치 및 운영 체제에 맞는 올바른 .msi 파일을 선택 하는 방법에 대 한 자세한 내용은 .msi 파일 다운로드에 대 한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-134">For information about selecting the correct .msi file for a device and operating system, refer to the guidance below about downloading .msi files.</span></span>

<span data-ttu-id="4e884-135">끝점 구성 관리자를 사용 하 여 업데이트를 배포 하는 방법에 대 한 지침은 [Configuration manager를 사용 하 여 응용 프로그램 배포](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-135">For instructions on how to deploy updates by using Endpoint Configuration Manager refer to [Deploy applications with Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications).</span></span> <span data-ttu-id="4e884-136">MDT를 사용 하 여 업데이트를 배포 하는 방법에 대 한 지침은 [mdt를 사용 하 여 Windows 10 이미지 배포](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-136">For instructions on how to deploy updates by using MDT, see [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>

**<span data-ttu-id="4e884-137">WindowsPE 및 Surface 펌웨어와 드라이버</span><span class="sxs-lookup"><span data-stu-id="4e884-137">WindowsPE and Surface firmware and drivers</span></span>**

<span data-ttu-id="4e884-138">끝점 구성 관리자와 MDT는 배포 프로세스 중에 WindowsPE (Windows 사전 설치 환경)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-138">Endpoint Configuration Manager and MDT both use the Windows Preinstallation Environment (WindowsPE) during the deployment process.</span></span> <span data-ttu-id="4e884-139">WindowsPE은 네트워크 어댑터와 저장소 컨트롤러용 으로만 제한 된 기본 드라이버 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-139">WindowsPE only supports a limited set of basic drivers such as those for network adapters and storage controllers.</span></span> <span data-ttu-id="4e884-140">WindowsPE의 일부가 아닌 Windows 구성 요소의 드라이버는 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-140">Drivers for Windows components that are not part of WindowsPE might produce errors.</span></span> <span data-ttu-id="4e884-141">가장 좋은 방법은 WindowsPE 단계 동안 필요한 드라이버만 사용 하도록 배포 프로세스를 구성 하 여 이러한 오류를 방지할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-141">As a best practice, you can prevent such errors by configuring the deployment process to use only the required drivers during the WindowsPE phase.</span></span>

### <span data-ttu-id="4e884-142">Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4e884-142">Endpoint Configuration Manager</span></span>

<span data-ttu-id="4e884-143">끝점 구성 관리자에서 시작 하 여 Configuration Manager 클라이언트를 사용 하 여 Microsoft Surface 펌웨어와 드라이버 업데이트를 동기화 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-143">Starting in Endpoint Configuration Manager, you can synchronize and deploy Microsoft Surface firmware and driver updates by using the Configuration Manager client.</span></span> <span data-ttu-id="4e884-144">자세한 내용은 KB 4098906, [Configuration Manager에서 화면 드라이버 업데이트를 관리 하는 방법을](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-144">For additional information, see KB 4098906, [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).</span></span>

## <span data-ttu-id="4e884-145">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="4e884-145">Supported devices</span></span>

<span data-ttu-id="4e884-146">다운로드 가능한 .msi 파일은 Surface Pro 2 이상에서 Surface 장치에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-146">Downloadable .msi files are available for Surface devices from Surface Pro 2 and later.</span></span> <span data-ttu-id="4e884-147">Surface Pro 7, Surface Pro X 및 Surface 노트북 3과 같은 최신 Surface 장치에 대 한 .msi 파일에 대 한 정보는 릴리스할 때이 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-147">Information about .msi files for the newest Surface devices such as Surface Pro 7, Surface Pro X, and Surface Laptop 3 will be available from this page upon release.</span></span>

## <span data-ttu-id="4e884-148">DFCI를 사용 하 여 펌웨어 관리</span><span class="sxs-lookup"><span data-stu-id="4e884-148">Managing firmware with DFCI</span></span>

<span data-ttu-id="4e884-149">Intune ( [공개 미리 보기](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)에서 사용 가능) 장치 펌웨어 구성 인터페이스 (dfci) 프로필을 사용 하면 Surface uefi 관리에서 최신 관리 스택을 UEFI 하드웨어 수준으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-149">With Device Firmware Configuration Interface (DFCI) profiles built into Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="4e884-150">DFCI는 0 터치 프로비저닝을 지원 하 고, BIOS 암호를 제거 하 고, 부팅 옵션 및 기본 제공 주변 장치를 비롯 한 보안 설정 제어를 제공 하며, 앞으로 고급 보안 시나리오의 토대를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-150">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="4e884-151">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-151">For more information, see:</span></span>

- [<span data-ttu-id="4e884-152">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="4e884-152">Intune management of Surface UEFI settings</span></span>](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- <span data-ttu-id="4e884-153">[Ignite 2019: Intune에서 SURFACE UEFI 설정의 원격 관리를 발표](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-153">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

## <span data-ttu-id="4e884-154">배포 프로세스 업데이트 모범 사례</span><span class="sxs-lookup"><span data-stu-id="4e884-154">Best practices for update deployment processes</span></span>

<span data-ttu-id="4e884-155">안정적인 환경을 유지 하기 위해서는 최신 버전의 Windows 10과 함께 패리티를 유지 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-155">To maintain a stable environment, it's strongly recommended to maintain parity with the most recent version of Windows 10.</span></span>  <span data-ttu-id="4e884-156">모범 사례 권장 사항은 [Windows 10 용 빌드 배포 링 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e884-156">For best practice recommendations, see [Build deployment rings for Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).</span></span>

## <span data-ttu-id="4e884-157">다운로드 가능한 화면 업데이트 패키지</span><span class="sxs-lookup"><span data-stu-id="4e884-157">Downloadable Surface update packages</span></span>

<span data-ttu-id="4e884-158">특정 버전의 Windows 10에는 각각 필요한 모든 누적 드라이버 및 Surface 장치에 대 한 펌웨어 업데이트가 포함 된 별도의 .msi 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-158">Specific versions of Windows 10 have separate .msi files, each containing all required cumulative driver and firmware updates for Surface devices.</span></span> <span data-ttu-id="4e884-159">업데이트 패키지에는 다음 구성 요소 중 일부 또는 모두가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-159">Update packages may include some or all of the following components:</span></span>

- <span data-ttu-id="4e884-160">Wi-fi 및 LTE</span><span class="sxs-lookup"><span data-stu-id="4e884-160">Wi-Fi and LTE</span></span>
- <span data-ttu-id="4e884-161">비디오</span><span class="sxs-lookup"><span data-stu-id="4e884-161">Video</span></span>
- <span data-ttu-id="4e884-162">고체 드라이브</span><span class="sxs-lookup"><span data-stu-id="4e884-162">Solid state drive</span></span>
- <span data-ttu-id="4e884-163">시스템 집계 모듈 (SAM)</span><span class="sxs-lookup"><span data-stu-id="4e884-163">System aggregator module (SAM)</span></span>
- <span data-ttu-id="4e884-164">배터리</span><span class="sxs-lookup"><span data-stu-id="4e884-164">Battery</span></span>
- <span data-ttu-id="4e884-165">키보드 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="4e884-165">Keyboard controller</span></span>
- <span data-ttu-id="4e884-166">포함 된 컨트롤러 (EC)</span><span class="sxs-lookup"><span data-stu-id="4e884-166">Embedded controller (EC)</span></span>
- <span data-ttu-id="4e884-167">관리 엔진 (나)</span><span class="sxs-lookup"><span data-stu-id="4e884-167">Management engine (ME)</span></span>
- <span data-ttu-id="4e884-168">UEFI (통합 확장 가능 펌웨어 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="4e884-168">Unified extensible firmware interface (UEFI)</span></span>

### <span data-ttu-id="4e884-169">.Msi 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e884-169">Downloading .msi files</span></span>

1. <span data-ttu-id="4e884-170">Microsoft 다운로드 센터에서 [화면에 대 한 드라이버 및 펌웨어 다운로드](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) 를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-170">Browse to [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) on the Microsoft Download Center.</span></span>
2. <span data-ttu-id="4e884-171">Surface model 및 Windows 버전과 일치 하는 .msi 파일 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-171">Select the .msi file name that matches the Surface model and version of Windows.</span></span> <span data-ttu-id="4e884-172">.Msi 파일 이름에는 드라이버와 펌웨어를 설치 하는 데 필요한 최소 지원 Windows 빌드 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-172">The .msi file name includes the minimum supported Windows build number required to install the drivers and firmware.</span></span> <span data-ttu-id="4e884-173">예를 들어 다음 그림과 같이 Surface Book 2를 Windows 10의 빌드 18362으로 업데이트 하려면SurfaceBook2_Win10_18362_19.101.13994.msi를 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e884-173">For example, as shown in the following figure, to update a Surface Book 2 with build 18362 of Windows 10, choose **SurfaceBook2_Win10_18362_19.101.13994.msi.**</span></span> <span data-ttu-id="4e884-174">Windows 10 빌드 16299를 사용 하는 Surface Book 2의 경우 **SurfaceBook2_Win10_16299_1803509_3.msi**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-174">For a Surface Book 2 with build 16299 of Windows 10, choose **SurfaceBook2_Win10_16299_1803509_3.msi**.</span></span>

    ![그림 1.](images/fig1-downloads-msi.png)

    *<span data-ttu-id="4e884-177">그림 1.</span><span class="sxs-lookup"><span data-stu-id="4e884-177">Figure 1.</span></span> <span data-ttu-id="4e884-178">화면 업데이트 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e884-178">Downloading Surface updates</span></span>*

### <span data-ttu-id="4e884-179">Surface. msi 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="4e884-179">Surface .msi naming convention</span></span>

<span data-ttu-id="4e884-180">2019 년 8 월부터 .msi 파일이 다음 명명 규칙을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-180">Since August 2019, .msi files have used the following naming convention:</span></span>

- <span data-ttu-id="4e884-181">버전 번호의 *제품*_*windows 릴리스*_*Windows 빌드 번호*_*버전 번호*_*(일반적으로 0)* 입니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-181">*Product*_*Windows release*_*Windows build number*_*Version number*_*Revision of version number (typically zero)*.</span></span>

**<span data-ttu-id="4e884-182">예</span><span class="sxs-lookup"><span data-stu-id="4e884-182">Example</span></span>**

- <span data-ttu-id="4e884-183">SurfacePro6_Win10_18362_19.073.44195_0.msi</span><span class="sxs-lookup"><span data-stu-id="4e884-183">SurfacePro6_Win10_18362_19.073.44195_0.msi</span></span>

<span data-ttu-id="4e884-184">이 파일 이름에는 다음 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-184">This file name provides the following information:</span></span>

- <span data-ttu-id="4e884-185">**제품:** SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="4e884-185">**Product:** SurfacePro6</span></span>
- <span data-ttu-id="4e884-186">**Windows 릴리스:** Win10</span><span class="sxs-lookup"><span data-stu-id="4e884-186">**Windows release:** Win10</span></span>
- <span data-ttu-id="4e884-187">**빌드:** 18362</span><span class="sxs-lookup"><span data-stu-id="4e884-187">**Build:** 18362</span></span>
- <span data-ttu-id="4e884-188">**버전:** 19.073.44195 – 파일이 생성 된 날짜와 시간이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-188">**Version:** 19.073.44195 – This shows the date and time that the file was created, as follows:</span></span>
  - <span data-ttu-id="4e884-189">**연도:** 19 (2019)</span><span class="sxs-lookup"><span data-stu-id="4e884-189">**Year:** 19 (2019)</span></span>
  - <span data-ttu-id="4e884-190">**월 및 주:** 073 (3 월 셋째 주)</span><span class="sxs-lookup"><span data-stu-id="4e884-190">**Month and week:** 073 (third week of July)</span></span>
  - <span data-ttu-id="4e884-191">**개월의 분:** 44195</span><span class="sxs-lookup"><span data-stu-id="4e884-191">**Minute of the month:** 44195</span></span>
- <span data-ttu-id="4e884-192">**버전 개정판:** 0 (이 버전의 첫 번째 릴리스)</span><span class="sxs-lookup"><span data-stu-id="4e884-192">**Revision of version:** 0 (first release of this version)</span></span>

### <span data-ttu-id="4e884-193">레거시 Surface. msi 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="4e884-193">Legacy Surface .msi naming convention</span></span>

<span data-ttu-id="4e884-194">레거시 .msi 파일 (2019 년 8 월 이전 파일)은 동일한 전체 명명 수식을 팔 로우 하 고 다른 메서드를 사용 하 여 버전 번호를 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-194">Legacy .msi files (files built before August 2019) followed the same overall naming formula but used a different method to derive the version number.</span></span>

**<span data-ttu-id="4e884-195">예</span><span class="sxs-lookup"><span data-stu-id="4e884-195">Example</span></span>**

- <span data-ttu-id="4e884-196">SurfacePro6_Win10_16299_1900307_0.msi</span><span class="sxs-lookup"><span data-stu-id="4e884-196">SurfacePro6_Win10_16299_1900307_0.msi</span></span>

<span data-ttu-id="4e884-197">이 파일 이름에는 다음 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-197">This file name provides the following information:</span></span>

- <span data-ttu-id="4e884-198">**제품:** SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="4e884-198">**Product:** SurfacePro6</span></span>
- <span data-ttu-id="4e884-199">**Windows 릴리스:** Win10</span><span class="sxs-lookup"><span data-stu-id="4e884-199">**Windows release:** Win10</span></span>
- <span data-ttu-id="4e884-200">**빌드:** 16299</span><span class="sxs-lookup"><span data-stu-id="4e884-200">**Build:** 16299</span></span>
- <span data-ttu-id="4e884-201">**버전:** 1900307 – 파일을 만든 날짜와 릴리스 시퀀스에서의 위치가 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-201">**Version:** 1900307 – This shows the date that the file was created and its position in the release sequence, as follows:</span></span>
  - <span data-ttu-id="4e884-202">**연도:** 19 (2019)</span><span class="sxs-lookup"><span data-stu-id="4e884-202">**Year:** 19 (2019)</span></span>
  - <span data-ttu-id="4e884-203">**릴리스 수:** 003 (연도의 세 번째 릴리스)</span><span class="sxs-lookup"><span data-stu-id="4e884-203">**Number of release:** 003 (third release of the year)</span></span>
  - <span data-ttu-id="4e884-204">**제품 버전 번호:** 07 (surface pro 6은 정식 화면 pro의 일곱 번째 버전입니다.)</span><span class="sxs-lookup"><span data-stu-id="4e884-204">**Product version number:** 07 (Surface Pro 6 is officially the seventh version of Surface Pro)</span></span>
- <span data-ttu-id="4e884-205">**버전 개정판:** 0 (이 버전의 첫 번째 릴리스)</span><span class="sxs-lookup"><span data-stu-id="4e884-205">**Revision of version:** 0 (first release of this version)</span></span>

## <span data-ttu-id="4e884-206">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4e884-206">Learn more</span></span>

- [<span data-ttu-id="4e884-207">Surface 용 드라이버 및 펌웨어 다운로드</span><span class="sxs-lookup"><span data-stu-id="4e884-207">Download drivers and firmware for Surface</span></span>](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [<span data-ttu-id="4e884-208">Configuration Manager에서 화면 드라이버 업데이트를 관리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4e884-208">How to manage Surface driver updates in Configuration Manager</span></span>](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [<span data-ttu-id="4e884-209">Configuration Manager를 사용 하 여 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-209">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [<span data-ttu-id="4e884-210">끝점 구성 관리자 설명서</span><span class="sxs-lookup"><span data-stu-id="4e884-210">Endpoint Configuration Manager documentation</span></span>](https://docs.microsoft.com/configmgr/)
- [<span data-ttu-id="4e884-211">Microsoft 배포 도구 키트 문서</span><span class="sxs-lookup"><span data-stu-id="4e884-211">Microsoft Deployment Toolkit documentation</span></span>](https://docs.microsoft.com/configmgr/mdt/)
- [<span data-ttu-id="4e884-212">Microsoft Deployment Toolkit을 사용하여 Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-212">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [<span data-ttu-id="4e884-213">Microsoft 배포 도구 키트를 사용 하 여 Windows 10을 Surface 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="4e884-213">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [<span data-ttu-id="4e884-214">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="4e884-214">Intune management of Surface UEFI settings</span></span>](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- <span data-ttu-id="4e884-215">[Ignite 2019: Intune에서 SURFACE UEFI 설정의 원격 관리를 발표](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e884-215">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>
- [<span data-ttu-id="4e884-216">Windows10 업데이트 배포 링 빌드</span><span class="sxs-lookup"><span data-stu-id="4e884-216">Build deployment rings for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
