---
title: Surface Enterprise 관리 모드(Surface)
description: Surface UEFI를 사용하여 Surface 디바이스의 이 기능을 통해 조직 내에서 펌웨어 설정을 보호하고 관리하는 방법을 확인합니다.
keywords: uefi, 구성, 펌웨어, 보안, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 04/16/2021
ms.openlocfilehash: 3c7eea524daa3210a329c41536f4c47a2c012bcf
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576588"
---
# <a name="microsoft-surface-enterprise-management-mode"></a><span data-ttu-id="e8394-104">Microsoft Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="e8394-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="e8394-105">Microsoft Surface Enterprise 관리 모드(SEMM)는 Surface UEFI(Unified Extensible Firmware Interface)가 있는 Surface 디바이스의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface Unified Extensible Firmware Interface (UEFI).</span></span> <span data-ttu-id="e8394-106">SEMM을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-106">You can use SEMM to:</span></span>

- <span data-ttu-id="e8394-107">조직의 펌웨어 설정을 보호하고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-107">Secure and manage firmware settings in your organization.</span></span>
- <span data-ttu-id="e8394-108">UEFI 설정 구성을 준비하고 Surface 디바이스에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-108">Prepare UEFI settings configurations and install them on a Surface device.</span></span> 

<span data-ttu-id="e8394-109">또한 SEMM은 인증서를 사용하여 무단 변조 또는 제거로부터 구성을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-109">SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="e8394-110">2S를 Surface Hub 2S를 Windows 10 Pro Windows Enterprise SEMM이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-110">To migrate a Surface Hub 2S to Windows 10 Pro or Windows Enterprise, SEMM is required.</span></span>

>[!NOTE]
><span data-ttu-id="e8394-111">SEMM은 Surface UEFI 펌웨어가 있는 디바이스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-111">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="e8394-112">여기에는 Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 상업용 SKUS(Intel 프로세서 포함Surface Laptop 4개 상업용 SKUS, Surface Laptop Intel 프로세서가 포함된 상업용 SK 3개, Surface Laptop Go 등 대부분의 Surface 장치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-112">This includes most other Surface devices including Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 commercial SKUs with an Intel processor, Surface Laptop 4 commercial SKUs with AMD processor, Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="e8394-113">SEMM은 AMD 프로세서가 있는 15인치 Surface Laptop 3 SKU에서 지원되지 않습니다(일반 정품 SKU로만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="e8394-113">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (available only as a retail SKU).</span></span> 

<span data-ttu-id="e8394-114">Surface 디바이스는 SEMM에서 구성하고 SEMM 인증서로 보호되는 경우 \*\* SEMM에 등록된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-114">When Surface devices are configured by SEMM and secured with the SEMM certificate, they're considered *enrolled* in SEMM.</span></span> <span data-ttu-id="e8394-115">SEMM 인증서가 제거되고 UEFI 설정 제어가 디바이스 사용자에게 반환되면 Surface 디바이스는 SEMM에서 등록되지 않은 것으로 간주됩니다. \*\*</span><span class="sxs-lookup"><span data-stu-id="e8394-115">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="e8394-116">SEMM을 관리하고 Surface 디바이스를 등록하는 데 사용할 수 있는 두 가지 관리 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-116">There are two administrative options that you can use to manage SEMM and enroll Surface devices:</span></span>

- <span data-ttu-id="e8394-117">SEMM 독립 실행형 도구인 Microsoft Surface UEFI 구성기는 이 문서에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-117">SEMM standalone tool, Microsoft Surface UEFI Configurator, is described in this article.</span></span> 

- <span data-ttu-id="e8394-118">통합 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e8394-118">Integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e8394-119">자세한 내용은 [USE Microsoft Endpoint Configuration Manager to manage devices with SEMM을 참조하세요.](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)</span><span class="sxs-lookup"><span data-stu-id="e8394-119">For information, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>

> [!NOTE]
> <span data-ttu-id="e8394-120">SEMM은 UEFI Surface Pro X에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-120">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="e8394-121">IT용 Surface 도구에서 UEFI [관리자를 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="e8394-121">You can download UEFI Manager from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="e8394-122">자세한 내용은 [X에서 배포, 관리 및 Surface Pro 참조하세요.](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="e8394-122">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>


## <a name="microsoft-surface-uefi-configurator"></a><span data-ttu-id="e8394-123">Microsoft Surface UEFI 구성기</span><span class="sxs-lookup"><span data-stu-id="e8394-123">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="e8394-124">SEMM의 기본 작업 영역은 그림 1에 표시된 Microsoft Surface UEFI Configurator입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-124">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> 

<span data-ttu-id="e8394-125">Microsoft Surface UEFI 구성기에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-125">You can use Microsoft Surface UEFI Configurator to:</span></span>

- <span data-ttu-id="e8394-126">설치 Windows 설치 관리자(.msi) 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-126">Create Windows Installer (.msi) packages.</span></span>
- <span data-ttu-id="e8394-127">WinPE 이미지를 사용하여 Surface 디바이스에서 SEMM을 등록, 구성 및 등록을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-127">Use WinPE images to enroll, configure, and unenroll SEMM on a Surface device.</span></span> 

<span data-ttu-id="e8394-128">이러한 패키지에는 UEFI 설정을 지정하는 구성 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-128">These packages contain a configuration file that specifies the UEFI settings.</span></span> <span data-ttu-id="e8394-129">SEMM 패키지에는 펌웨어에 설치 및 저장되는 인증서도 포함되어 있으며 UEFI 설정이 적용되기 전에 구성 파일의 서명을 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-129">SEMM packages also contain a certificate that's installed and stored in firmware and is used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!TIP]
><span data-ttu-id="e8394-130">이제 Surface UEFI 구성기 및 SEMM을 사용하여 Surface Dock 2에서 포트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-130">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="e8394-131">자세한 내용은 [SEMM을 통해 Surface Dock 2 포트 보호를 참조합니다.](secure-surface-dock-ports-semm.md)</span><span class="sxs-lookup"><span data-stu-id="e8394-131">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI 구성기](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="e8394-133">그림 1.</span><span class="sxs-lookup"><span data-stu-id="e8394-133">Figure 1.</span></span> <span data-ttu-id="e8394-134">Microsoft Surface UEFI 구성기</span><span class="sxs-lookup"><span data-stu-id="e8394-134">Microsoft Surface UEFI Configurator</span></span>*

<span data-ttu-id="e8394-135">Microsoft Surface UEFI 구성기 도구를 세 가지 모드로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-135">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

- <span data-ttu-id="e8394-136">[Surface UEFI 구성 패키지](#configuration-package).</span><span class="sxs-lookup"><span data-stu-id="e8394-136">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="e8394-137">이 모드를 사용하여 Surface UEFI 구성 패키지를 만들어 SEMM에 Surface 디바이스를 등록하고 등록된 디바이스에서 UEFI 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-137">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
- <span data-ttu-id="e8394-138">[Surface UEFI 재설정 패키지](#reset-package).</span><span class="sxs-lookup"><span data-stu-id="e8394-138">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="e8394-139">이 모드를 사용하여 SEMM에서 Surface 디바이스의 선택을 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="e8394-139">Use this mode to unenroll a Surface device from SEMM.</span></span>
- <span data-ttu-id="e8394-140">[Surface UEFI 복구 요청](#recovery-request).</span><span class="sxs-lookup"><span data-stu-id="e8394-140">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="e8394-141">이 모드를 사용하여 복구 요청에 응답하여 패키지 초기화 작업이 성공하지 않은 경우 SEMM에서 Surface 디바이스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-141">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>

#### <a name="download-microsoft-surface-uefi-configurator"></a><span data-ttu-id="e8394-142">Microsoft Surface UEFI 구성기 다운로드</span><span class="sxs-lookup"><span data-stu-id="e8394-142">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="e8394-143">Microsoft Surface UEFI 구성기는 Microsoft 다운로드 센터의 [Surface Tools for IT(IT용 Surface 도구)](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-143">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <a name="configuration-package"></a><span data-ttu-id="e8394-144">구성 패키지</span><span class="sxs-lookup"><span data-stu-id="e8394-144">Configuration package</span></span>

<span data-ttu-id="e8394-145">Surface UEFI 구성 패키지는 Surface 디바이스에서 SEMM을 구현하고 관리하는 기본 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-145">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="e8394-146">이러한 패키지에는 그림 2에 표시된 구성 파일과 인증서 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-146">These packages contain a configuration file and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="e8394-147">구성 파일에는 Microsoft Surface UEFI 구성기에서 패키지를 만들 때 지정된 UEFI 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-147">The configuration file contains UEFI settings that are specified when the package is created in Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="e8394-148">구성 패키지가 SEMM에 아직 등록되지 않은 Surface 디바이스에서 처음으로 실행되는 경우 디바이스의 펌웨어에서 인증서 파일을 프로비전하고 SEMM에 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-148">When a configuration package runs for the first time on a Surface device that's not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="e8394-149">SEMM에 장치를 등록할 때 및 인증서가 저장되고 등록이 완료되기 전에 SEMM 인증서 지문의 마지막 두 자리 숫자를 제공하여 작업을 확인하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-149">When enrolling a device in SEMM, and before the certificate is stored and the enrollment finishes, you're prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint.</span></span> <span data-ttu-id="e8394-150">이 확인을 수행하려면 등록하는 동안 사용자가 실제로 디바이스에 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-150">This confirmation requires a user to be physically present at the device during enrollment to perform the confirmation.</span></span>

![인증서를 통해 SEMM 구성 패키지 보안](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="e8394-152">그림 2.</span><span class="sxs-lookup"><span data-stu-id="e8394-152">Figure 2.</span></span> <span data-ttu-id="e8394-153">인증서를 통해 SEMM 구성 패키지 보안</span><span class="sxs-lookup"><span data-stu-id="e8394-153">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="e8394-154">SEMM 인증서의 요구 사항에 대한 자세한 내용은 이 문서 [부분의 Surface Enterprise 관리](#surface-enterprise-management-mode-certificate-requirements) 모드 인증서 요구 사항 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8394-154">For more information about the requirements for the SEMM certificate, see the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section later in this article.</span></span>

>[!TIP]
><span data-ttu-id="e8394-155">SEMM을 사용하여 UEFI 암호를 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-155">You have the option to require a UEFI password with SEMM.</span></span> <span data-ttu-id="e8394-156">이 경우 Surface UEFI의 **보안,** **장치,** 부팅 구성 및 보안 관리 Enterprise 암호가 필요합니다. \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e8394-156">If you do, the password is required to view the **Security**, **Devices**, **Boot Configuration**, and **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="e8394-157">장치가 SEMM에 등록된 후 구성 파일을 읽고 파일에 지정된 설정이 UEFI에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-157">After a device is enrolled in SEMM, the configuration file is read, and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="e8394-158">이미 SEMM에 등록된 장치에서 구성 패키지를 실행하면 구성 파일의 서명이 장치 펌웨어에 저장된 인증서에 대해 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-158">When you run a configuration package on a device that's already enrolled in SEMM, the signature of the configuration file is checked against the certificate that's stored in the device firmware.</span></span> <span data-ttu-id="e8394-159">서명이 일치하지 않는 경우 장치에 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-159">If the signature doesn't match, no changes are applied to the device.</span></span>

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a><span data-ttu-id="e8394-160">SEMM을 사용하여 Surface UEFI에서 장치 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e8394-160">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="e8394-161">다음 목록에는 SEMM에서 관리할 수 있는 모든 사용 가능한 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-161">The following list shows all the available devices that you can manage in SEMM:</span></span>

- <span data-ttu-id="e8394-162">USB 포트 도킹</span><span class="sxs-lookup"><span data-stu-id="e8394-162">Docking USB port</span></span>
- <span data-ttu-id="e8394-163">보드 오디오</span><span class="sxs-lookup"><span data-stu-id="e8394-163">On-board audio</span></span>
- <span data-ttu-id="e8394-164">디지털 그래픽 처리 장치</span><span class="sxs-lookup"><span data-stu-id="e8394-164">Digital graphics processing unit</span></span>
- <span data-ttu-id="e8394-165">표지 형식</span><span class="sxs-lookup"><span data-stu-id="e8394-165">Type cover</span></span>
- <span data-ttu-id="e8394-166">마이크로 SD 카드</span><span class="sxs-lookup"><span data-stu-id="e8394-166">Micro SD card</span></span>
- <span data-ttu-id="e8394-167">전면 카메라</span><span class="sxs-lookup"><span data-stu-id="e8394-167">Front camera</span></span>
- <span data-ttu-id="e8394-168">후면 카메라</span><span class="sxs-lookup"><span data-stu-id="e8394-168">Rear camera</span></span>
- <span data-ttu-id="e8394-169">적외선 카메라(Windows Hello용)</span><span class="sxs-lookup"><span data-stu-id="e8394-169">Infrared camera (for Windows Hello)</span></span>
- <span data-ttu-id="e8394-170">Bluetooth 전용</span><span class="sxs-lookup"><span data-stu-id="e8394-170">Bluetooth only</span></span>
- <span data-ttu-id="e8394-171">무선 네트워크 및 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e8394-171">Wireless network and Bluetooth</span></span>
- <span data-ttu-id="e8394-172">LTE(장기 발전)</span><span class="sxs-lookup"><span data-stu-id="e8394-172">Long-term evolution (LTE)</span></span>

 >[!NOTE]
><span data-ttu-id="e8394-173">UEFI 장치 페이지에서 기본 제공 장치는 장치 또는 회사 환경에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-173">On the UEFI Devices page, the built-in devices might vary, depending on your device or corporate environment.</span></span> <span data-ttu-id="e8394-174">예를 들어 UEFI 장치 페이지는 X에서 지원되지 Surface Pro 않습니다. LTE는 LTE가 탑재된 디바이스에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-174">For example, the UEFI Devices page isn't supported on Surface Pro X; LTE appears only on LTE-equipped devices.</span></span> 
### <a name="configure-advanced-settings-with-semm"></a><span data-ttu-id="e8394-175">SEMM을 사용하여 고급 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e8394-175">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="e8394-176">표 1.</span><span class="sxs-lookup"><span data-stu-id="e8394-176">Table 1.</span></span> <span data-ttu-id="e8394-177">고급 설정</span><span class="sxs-lookup"><span data-stu-id="e8394-177">Advanced settings</span></span>**

| <span data-ttu-id="e8394-178">설정</span><span class="sxs-lookup"><span data-stu-id="e8394-178">Setting</span></span>                            | <span data-ttu-id="e8394-179">설명</span><span class="sxs-lookup"><span data-stu-id="e8394-179">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="e8394-180">PXE 부팅용 IPv6</span><span class="sxs-lookup"><span data-stu-id="e8394-180">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="e8394-181">PXE 부팅에 대한 IPv6 지원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-181">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="e8394-182">이 설정을 구성하지 않은 경우 PXE 부팅에 대한 IPv6 지원을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-182">If you don't configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="e8394-183">대체 부팅</span><span class="sxs-lookup"><span data-stu-id="e8394-183">Alternate Boot</span></span>                     | <span data-ttu-id="e8394-184">부팅하는 동안 볼륨 감소 단추와 전원 단추를 모두 눌러 USB 또는 이더넷 디바이스로 직접 부팅하기 위해 대체 부팅 순서 사용을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-184">Allows you to manage the use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="e8394-185">이 설정을 구성하지 않은 경우 대체 부팅이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-185">If you don't configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="e8394-186">부팅 순서 잠금</span><span class="sxs-lookup"><span data-stu-id="e8394-186">Boot Order Lock</span></span>                    | <span data-ttu-id="e8394-187">변경을 방지하기 위해 부팅 순서를 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-187">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="e8394-188">이 설정을 구성하지 않은 경우 부팅 순서 잠금을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-188">If you don't configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="e8394-189">USB 부팅</span><span class="sxs-lookup"><span data-stu-id="e8394-189">USB Boot</span></span>                           | <span data-ttu-id="e8394-190">USB 장치에 대한 부팅을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-190">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="e8394-191">이 설정을 구성하지 않은 경우 USB 부팅이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-191">If you don't configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="e8394-192">네트워크 스택</span><span class="sxs-lookup"><span data-stu-id="e8394-192">Network Stack</span></span>                      | <span data-ttu-id="e8394-193">네트워크 스택 부팅 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-193">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="e8394-194">이 설정을 구성하지 않은 경우 네트워크 스택 부팅 설정을 관리하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-194">If you don't configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="e8394-195">자동 전원 공급</span><span class="sxs-lookup"><span data-stu-id="e8394-195">Auto Power On</span></span>                      | <span data-ttu-id="e8394-196">자동 전원 사용 부팅 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-196">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="e8394-197">이 설정을 구성하지 않은 경우 자동 전원 사용이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-197">If you don't configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="e8394-198">SMT(동시 다중 스레딩)</span><span class="sxs-lookup"><span data-stu-id="e8394-198">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="e8394-199">SMT(동시 다중 스레딩)를 관리하여 하이퍼스레딩을 활성화 또는 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-199">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="e8394-200">이 설정을 구성하지 않은 경우 SMT가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-200">If you don't configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="e8394-201">배터리 제한 사용</span><span class="sxs-lookup"><span data-stu-id="e8394-201">Enable Battery limit</span></span>| <span data-ttu-id="e8394-202">배터리 제한 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-202">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="e8394-203">이 설정을 구성하지 않은 경우 배터리 제한이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-203">If you don't configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="e8394-204">보안</span><span class="sxs-lookup"><span data-stu-id="e8394-204">Security</span></span>                           | <span data-ttu-id="e8394-205">Surface UEFI \*\*\*\* 보안 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-205">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="e8394-206">이 설정을 구성하지 않은 경우 보안 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-206">If you don't configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="e8394-207">장치</span><span class="sxs-lookup"><span data-stu-id="e8394-207">Devices</span></span>                            | <span data-ttu-id="e8394-208">Surface UEFI 장치 **페이지를** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-208">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="e8394-209">이 설정을 구성하지 않은 경우 장치 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-209">If you don't configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="e8394-210">Boot</span><span class="sxs-lookup"><span data-stu-id="e8394-210">Boot</span></span>                               | <span data-ttu-id="e8394-211">Surface UEFI \*\*\*\* 부팅 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-211">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="e8394-212">이 설정을 구성하지 않은 경우 부팅 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-212">If you don't configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="e8394-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="e8394-213">DateTime</span></span>                           | <span data-ttu-id="e8394-214">Surface UEFI **DateTime 페이지를** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-214">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="e8394-215">이 설정을 구성하지 않은 경우 DateTime 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-215">If you don't configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="e8394-216">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="e8394-216">EnableOSMigration</span></span>                          | <span data-ttu-id="e8394-217">2에서 Surface Hub 2를 마이그레이션할 Windows 10 Team Windows 10 Pro Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e8394-217">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="e8394-218">이 설정을 구성하지 않는 경우 Surface Hub 2 장치가 하나의 OS만 실행할 Windows 10 Team 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-218">If you don't configure this setting, Surface Hub 2 devices can run only the Windows 10 Team OS.</span></span> <span data-ttu-id="e8394-219">참고: Windows 10 Team 및 Windows 10 Pro/Enterprise 2에서는 이중 부팅을 사용할 Surface Hub 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-219">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise isn't available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="e8394-220">SEMM 구성 패키지를 만들면 그림 3과 같이 성공 페이지에 두 문자가 표시됩니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e8394-220">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![인증서 지문 표시](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="e8394-222">그림 3.</span><span class="sxs-lookup"><span data-stu-id="e8394-222">Figure 3.</span></span> <span data-ttu-id="e8394-223">성공 페이지에서 인증서 지문의 마지막 두 문자 표시</span><span class="sxs-lookup"><span data-stu-id="e8394-223">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="e8394-224">이러한 문자는 인증서 지문의 마지막 두 문자로, 기록하거나 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-224">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="e8394-225">그림 4에 표시된 같이 문자는 Surface 디바이스의 SEMM 등록을 확인하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-225">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM에서 등록 확인](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="e8394-227">그림 4.</span><span class="sxs-lookup"><span data-stu-id="e8394-227">Figure 4.</span></span> <span data-ttu-id="e8394-228">SEMM 인증서 지문을 통해 SEMM에 등록 확인</span><span class="sxs-lookup"><span data-stu-id="e8394-228">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="e8394-229">인증서 파일(.pfx)에 액세스할 수 있는 관리자는 CertMgr에서 .pfx 파일을 열면 지문을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-229">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="e8394-230">CertMgr을 통해 지문을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-230">To view the thumbprint with CertMgr:</span></span>
>1. <span data-ttu-id="e8394-231">.pfx 파일을 선택하고 보류(또는 마우스 오른쪽 단추 클릭)한 다음 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8394-231">Select and hold (or right-click) the .pfx file, and then select **Open**.</span></span>
>2. <span data-ttu-id="e8394-232">탐색 창에서 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-232">In the navigation pane, expand the folder.</span></span>
>3. <span data-ttu-id="e8394-233">인증서를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8394-233">Select **Certificates**.</span></span>
>4. <span data-ttu-id="e8394-234">주 창에서 인증서를 선택하고 보유(또는 마우스 오른쪽 단추 클릭)한 다음 열기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8394-234">In the main pane, select and hold (or right-click) your certificate, and then select **Open**.</span></span>
>5. <span data-ttu-id="e8394-235">세부 **정보 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-235">Select the **Details** tab.</span></span>
>6. <span data-ttu-id="e8394-236">표시 **드롭다운** 메뉴에서 **모두** 또는 속성만 **선택해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-236">In the **Show** drop-down menu, **All** or **Properties Only** must be selected.</span></span>
>7. <span data-ttu-id="e8394-237">지문 **필드를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-237">Select the **Thumbprint** field.</span></span>

<span data-ttu-id="e8394-238">SEMM에 Surface 디바이스를 등록하거나 구성 패키지에서 UEFI 구성을 적용하려면 의도한 Surface .msi 권한으로 .msi 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-238">To enroll a Surface device in SEMM or apply the UEFI configuration from a configuration package, run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="e8394-239">응용 프로그램 배포 또는 운영 체제 [](https://technet.microsoft.com/library/mt346023) 배포 기술(Microsoft Endpoint Configuration Manager [또는 Microsoft Deployment Toolkit.](https://technet.microsoft.com/windows/dn475741)</span><span class="sxs-lookup"><span data-stu-id="e8394-239">You can use application deployment or operating system deployment technologies, like [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="e8394-240">SEMM에 장치를 등록할 때 장치에 등록을 확인하려면 물리적으로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-240">When you enroll a device in SEMM, you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="e8394-241">SEMM에 이미 등록된 장치에 구성을 적용하는 경우 사용자 조작이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-241">When you apply a configuration to devices that are already enrolled in SEMM, user interaction isn’t required.</span></span>

<span data-ttu-id="e8394-242">SEMM에 Surface 디바이스를 등록하거나 SEMM을 사용하여 Surface UEFI 구성을 적용하는 방법에 대한 단계별 단계를 확인하려면 SeMM을 사용하여 Surface 디바이스 등록 및 구성을 [참조하세요.](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)</span><span class="sxs-lookup"><span data-stu-id="e8394-242">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <a name="reset-package"></a><span data-ttu-id="e8394-243">패키지 초기화</span><span class="sxs-lookup"><span data-stu-id="e8394-243">Reset package</span></span>

<span data-ttu-id="e8394-244">Surface UEFI 재설정 패키지는 SEMM에서 Surface 디바이스를 초기화하기 위해 하나의 작업만 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-244">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="e8394-245">재설정 패키지에는 장치의 펌웨어에서 SEMM 인증서를 제거하고 UEFI 설정을 공장 기본 설정으로 다시 설정하는 서명된 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-245">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to the factory default settings.</span></span> <span data-ttu-id="e8394-246">Surface UEFI 구성 패키지와 마찬가지로 초기화 패키지는 Surface 디바이스에 프로비전된 동일한 SEMM 인증서를 사용하여 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-246">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that’s provisioned on the Surface device.</span></span> <span data-ttu-id="e8394-247">SEMM 재설정 패키지를 만들 때 초기화하려는 Surface 디바이스의 일련 번호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-247">When you create a SEMM reset package, you’re required to supply the serial number of the Surface device that you intend to reset.</span></span> <span data-ttu-id="e8394-248">SEMM 초기화 패키지는 유니버설이 아니며 하나의 장치에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-248">SEMM reset packages aren’t universal — they’re specific to one device.</span></span>

### <a name="recovery-request"></a><span data-ttu-id="e8394-249">복구 요청</span><span class="sxs-lookup"><span data-stu-id="e8394-249">Recovery request</span></span>

<span data-ttu-id="e8394-250">일부 시나리오에서는 Surface UEFI 재설정 패키지를 사용하는 것이 불가능할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-250">In some scenarios, it might be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="e8394-251">예를 들어 Surface Windows 사용할 수 없는 경우) 이러한 시나리오에서는 복구 요청 작업을 사용하여 Surface UEFI의 Enterprise 관리 페이지를 통해 SeMM에서 Surface 디바이스의 설치를 해지할 수 있습니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e8394-251">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

> [!div class="mx-imgBorder"]
> ![SEMM 복구 요청 시작](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="e8394-253">그림 5.</span><span class="sxs-lookup"><span data-stu-id="e8394-253">Figure 5.</span></span> <span data-ttu-id="e8394-254">Enterprise 페이지에서 SEMM 복구 요청 시작</span><span class="sxs-lookup"><span data-stu-id="e8394-254">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="e8394-255">surface 디바이스에서 Enterprise \*\*\*\* 관리 페이지에서 프로세스를 사용하여 SEMM을 다시 설정하면 초기화 요청이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-255">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you’re given a Reset Request.</span></span> <span data-ttu-id="e8394-256">이 재설정 요청은 USB 드라이브에 파일로 저장하거나 텍스트로 복사하거나 모바일 장치를 사용하여 QR 코드로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-256">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="e8394-257">Microsoft Surface UEFI 구성기 다시 설정 요청 옵션을 사용하여 다시 설정 요청 파일을 로드하거나 요청 텍스트 또는 QR 코드 재설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-257">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or to enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="e8394-258">Microsoft Surface UEFI 구성기는 Surface 디바이스에 입력할 수 있는 확인 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-258">Microsoft Surface UEFI Configurator generates a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="e8394-259">Surface 디바이스에 코드를 입력하고 다시 \*\*\*\* 시작을 선택하면 장치가 SEMM에서 인가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-259">If you enter the code on the Surface device and select **Restart**, the device is unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="e8394-260">재설정 요청은 생성된 후 2시간 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-260">A Reset Request expires two hours after it's created.</span></span>

<span data-ttu-id="e8394-261">SEMM에서 Surface 디바이스를 인가하는 방법에 대한 단계별 실무는 SEMM에서 Surface 장치 인인을 [언인라운드를 참조합니다.](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)</span><span class="sxs-lookup"><span data-stu-id="e8394-261">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <a name="surface-enterprise-management-mode-certificate-requirements"></a><span data-ttu-id="e8394-262">Surface Enterprise 관리 모드 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8394-262">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="e8394-263">Microsoft Surface UEFI 구성기에서 SEMM을 사용하며 UEFI 설정을 적용하려면 구성 파일의 서명을 확인하는 데 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-263">When you use SEMM with Microsoft Surface UEFI Configurator and want to apply UEFI settings, a certificate is required to verify the signature of configuration files.</span></span> <span data-ttu-id="e8394-264">이 인증서는 장치가 SEMM에 등록한 후 승인된 인증서로 만든 패키지만 UEFI 설정을 수정하는 데 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-264">This certificate ensures that after a device enrolls in SEMM, only packages created with the approved certificate can be used to modify the UEFI settings.</span></span>

>[!NOTE]
><span data-ttu-id="e8394-265">등록된 Surface 디바이스에서 SEMM 또는 Surface UEFI 설정을 수정하려면 SEMM 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-265">To make any modification to SEMM or Surface UEFI settings on enrolled Surface devices, the SEMM certificate is required.</span></span> <span data-ttu-id="e8394-266">SEMM 인증서가 손상되거나 손실된 경우 SEMM을 제거하거나 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-266">If the SEMM certificate is corrupt or lost, SEMM can’t be removed or reset.</span></span> <span data-ttu-id="e8394-267">백업 및 복구를 위한 적절한 솔루션을 사용하여 SEMM 인증서를 적절하게 관리</span><span class="sxs-lookup"><span data-stu-id="e8394-267">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery</span></span>

<span data-ttu-id="e8394-268">Microsoft Surface UEFI 구성기 도구를 사용하여 만든 패키지는 인증서로 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-268">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="e8394-269">이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지만 UEFI 설정을 수정하는 데 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-269">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <a name="recommended-certificate-settings"></a><span data-ttu-id="e8394-270">권장 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="e8394-270">Recommended certificate settings</span></span>
<span data-ttu-id="e8394-271">SEMM 인증서에 권장되는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-271">The following settings are recommended for the SEMM certificate:</span></span>

- <span data-ttu-id="e8394-272">**키 알고리즘** - RSA</span><span class="sxs-lookup"><span data-stu-id="e8394-272">**Key Algorithm** – RSA</span></span> 
- <span data-ttu-id="e8394-273">**키 길이** – 2048</span><span class="sxs-lookup"><span data-stu-id="e8394-273">**Key Length** – 2048</span></span>
- <span data-ttu-id="e8394-274">**해시 알고리즘** - SHA-256</span><span class="sxs-lookup"><span data-stu-id="e8394-274">**Hash Algorithm** – SHA-256</span></span>
- <span data-ttu-id="e8394-275">**유형** - SSL 서버 인증</span><span class="sxs-lookup"><span data-stu-id="e8394-275">**Type** – SSL Server Authentication</span></span>
- <span data-ttu-id="e8394-276">**키 사용** - 디지털 서명, 키 인시퍼멘트</span><span class="sxs-lookup"><span data-stu-id="e8394-276">**Key Usage** – Digital signature, Key Encipherment</span></span>
- <span data-ttu-id="e8394-277">**공급자** - Microsoft Enhanced RSA 및 AES 암호화 공급자</span><span class="sxs-lookup"><span data-stu-id="e8394-277">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
- <span data-ttu-id="e8394-278">**만료 날짜** - 인증서 생성 후 15개월</span><span class="sxs-lookup"><span data-stu-id="e8394-278">**Expiration Date** – 15 Months from certificate creation</span></span>
- <span data-ttu-id="e8394-279">**키 내보내기 정책** - 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-279">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="e8394-280">또한 중간 CA(인증 기관)가 SEMM 전용인 2계층 PKI(공개 키 인프라) 아키텍처에서 SEMM 인증서를 인증하여 인증서 해지가 가능한 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-280">It's also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="e8394-281">2계층 PKI 구성에 대한 자세한 내용은 [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy를 참조하십시오.](https://technet.microsoft.com/library/hh831348)</span><span class="sxs-lookup"><span data-stu-id="e8394-281">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <a name="self-signed-certificate"></a><span data-ttu-id="e8394-282">자체 서명된 인증서</span><span class="sxs-lookup"><span data-stu-id="e8394-282">Self-signed certificate</span></span> 
<span data-ttu-id="e8394-283">다음 예제 PowerShell 스크립트를 사용하여 개념 증명 시나리오에서 사용할 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-283">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="e8394-284">이 스크립트를 사용 하 고 다음 텍스트를 복사 하는 메모장 파일을 PowerShell 스크립트 (.ps1).</span><span class="sxs-lookup"><span data-stu-id="e8394-284">To use this script, copy the following text into Notepad, and then save the file as a PowerShell script (.ps1).</span></span> 

> [!NOTE]
> <span data-ttu-id="e8394-285">이 스크립트는 의 암호를 사용하여 인증서를 `12345678` 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-285">This script creates a certificate with a password of `12345678`.</span></span> <span data-ttu-id="e8394-286">이 스크립트로 생성된 인증서는 프로덕션 환경에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-286">The certificate generated by this script isn't recommended for production environments.</span></span>
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
><span data-ttu-id="e8394-287">SEMM 및 Microsoft Surface UEFI 구성기에서 사용하려면 개인 키와 암호 보호를 사용하여 인증서를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-287">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="e8394-288">Microsoft Surface UEFI 구성기에서 SEMM 인증서 파일(.pfx) 및 인증서 암호를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-288">Microsoft Surface UEFI Configurator prompts you to select the SEMM certificate file (.pfx) and certificate password.</span></span>

<span data-ttu-id="e8394-289">자체 서명된 인증서를 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="e8394-289">To create a self-signed certificate:</span></span>
1.  <span data-ttu-id="e8394-290">C: 드라이브에서 스크립트를 저장할 폴더를 생성합니다. 예: C:\SEMM.</span><span class="sxs-lookup"><span data-stu-id="e8394-290">On your C: drive, create the folder where you'll save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="e8394-291">예제 스크립트를 메모장(또는 해당하는 텍스트 편집기)에 복사한 다음 파일을 PowerShell 스크립트(.ps1) 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-291">Copy the example script into Notepad (or equivalent text editor), and then save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="e8394-292">관리자 자격 증명을 사용하여 컴퓨터에 로그인한 다음 관리자 권한 PowerShell 세션을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-292">Sign in to your computer with administrator credentials, and then open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="e8394-293">스크립트 실행을 허용하도록 사용 권한이 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="e8394-293">Make sure that your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="e8394-294">기본적으로 실행 정책을 수정하지 않으면 스크립트가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-294">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="e8394-295">자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)</span><span class="sxs-lookup"><span data-stu-id="e8394-295">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="e8394-296">명령 프롬프트에서 스크립트의 전체 경로를 입력한 다음 Enter 를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8394-296">At the command prompt, enter the full path of the script and then press **Enter**.</span></span> <span data-ttu-id="e8394-297">이 스크립트는 TempOwner.pfx라는 데모 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-297">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="e8394-298">또는 PowerShell을 사용하여 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-298">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="e8394-299">자세한 내용은 [New-SelfSignedCertificate를 참조하세요.](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)</span><span class="sxs-lookup"><span data-stu-id="e8394-299">For more information, see [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

>[!NOTE]
><span data-ttu-id="e8394-300">PKI 인프라에서 오프라인 루트를 사용하는 조직의 경우 MICROSOFT Surface UEFI 구성기는 SEMM 인증서를 인증하기 위해 루트 CA에 연결된 환경에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-300">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="e8394-301">Microsoft Surface UEFI Configurator에서 생성한 패키지는 파일로 전송할 수 있으므로 USB 스틱과 같은 이동식 저장소를 사용하여 오프라인 네트워크 환경 외부로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-301">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files, so they can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <a name="managing-certificates-faq"></a><span data-ttu-id="e8394-302">인증서 관리 FAQ</span><span class="sxs-lookup"><span data-stu-id="e8394-302">Managing certificates FAQ</span></span>

<span data-ttu-id="e8394-303">권장되는 *최소* 길이는 15개월입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-303">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="e8394-304">15개월 미만으로 만료되는 인증서를 사용할 수도 있습니다. 또는 15개월보다 오래 만료되는 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-304">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="e8394-305">인증서가 만료되면 자동으로 갱신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-305">When a certificate expires, it doesn't automatically renew.</span></span> 

**<span data-ttu-id="e8394-306">만료된 인증서가 SEMM 등록 장치의 기능에 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="e8394-306">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="e8394-307">아니요. 인증서는 SEMM의 IT 관리자 관리 작업에만 영향을 미치며 만료 시 장치 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-307">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>

**<span data-ttu-id="e8394-308">SEMM 패키지 및 인증서가 있는 모든 컴퓨터의 SEMM 패키지 및 인증서를 업데이트해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="e8394-308">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**<br><br>
<span data-ttu-id="e8394-309">SEMM 재설정 또는 복구가 작동하게 하려는 경우 인증서가 유효해야 하고 만료되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-309">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="e8394-310">주문하는 각 표면에 대해 패키지를 대량 재설정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e8394-310">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="e8394-311">환경의 모든 컴퓨터를 다시 설정하는 기능을 구축할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e8394-311">Can one be built that resets all machines in our environment?</span></span>**<br><br>
<span data-ttu-id="e8394-312">특정 장치 유형에 대한 구성 패키지를 만드는 PowerShell 샘플을 사용하여 일련 번호가 독립적인 초기화 패키지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-312">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that's serial-number independent.</span></span> <span data-ttu-id="e8394-313">인증서가 여전히 유효한 경우 PowerShell을 사용하여 SEMM을 다시 설정하는 재설정 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-313">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <a name="version-history"></a><span data-ttu-id="e8394-314">버전 기록</span><span class="sxs-lookup"><span data-stu-id="e8394-314">Version history</span></span>


### <a name="version-2831390"></a><span data-ttu-id="e8394-315">버전 2.83.139.0</span><span class="sxs-lookup"><span data-stu-id="e8394-315">Version 2.83.139.0</span></span>

<span data-ttu-id="e8394-316">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-316">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-317">4 Surface Laptop 지원</span><span class="sxs-lookup"><span data-stu-id="e8394-317">Support for Surface Laptop 4</span></span>
- <span data-ttu-id="e8394-318">7에 대한 동시 다중 스레드 옵션 Surface Pro 지원</span><span class="sxs-lookup"><span data-stu-id="e8394-318">Support for simultaneous multithreading option for Surface Pro 7</span></span>
- <span data-ttu-id="e8394-319">더 이상 사용되지 않습니다. SEMM 설정 제거</span><span class="sxs-lookup"><span data-stu-id="e8394-319">Removal of obsolete SEMM settings</span></span>  
- <span data-ttu-id="e8394-320">향상된 MSI 서명</span><span class="sxs-lookup"><span data-stu-id="e8394-320">Improved MSI signing</span></span> 

### <a name="version-2791390"></a><span data-ttu-id="e8394-321">버전 2.79.139.0</span><span class="sxs-lookup"><span data-stu-id="e8394-321">Version 2.79.139.0</span></span>

<span data-ttu-id="e8394-322">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-322">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-323">7+Surface Pro 지원</span><span class="sxs-lookup"><span data-stu-id="e8394-323">Support for Surface Pro 7+.</span></span>
- <span data-ttu-id="e8394-324">사용자 환경 개선.</span><span class="sxs-lookup"><span data-stu-id="e8394-324">User experience improvements.</span></span>

### <a name="version-2781390"></a><span data-ttu-id="e8394-325">버전 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="e8394-325">Version 2.78.139.0</span></span>

<span data-ttu-id="e8394-326">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-326">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-327">이동 및 Surface Laptop 지원 Surface Pro 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-327">Support for Surface Laptop Go and Surface Pro X.</span></span>
- <span data-ttu-id="e8394-328">새 버전 릴리스에 대한 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-328">Notifications for new version releases.</span></span>
- <span data-ttu-id="e8394-329">소유권을 변경하기 위해 사용자 지정 패키지를 만드는 능력</span><span class="sxs-lookup"><span data-stu-id="e8394-329">The ability to create custom packages to change ownership.</span></span>
- <span data-ttu-id="e8394-330">버그 수정.</span><span class="sxs-lookup"><span data-stu-id="e8394-330">Bug fixes.</span></span>

### <a name="version-2731360"></a><span data-ttu-id="e8394-331">버전 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="e8394-331">Version 2.73.136.0</span></span>

<span data-ttu-id="e8394-332">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-332">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-333">SEMM을 사용하여 Surface Hub2S에서 오디오를 사용하지 않도록 설정하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-333">The ability for audio to be disabled on Surface Hub2S using SEMM.</span></span>
- <span data-ttu-id="e8394-334">Dock 2용 Surface Pro X 지원</span><span class="sxs-lookup"><span data-stu-id="e8394-334">Support for Surface Pro X for Dock 2.</span></span>
- <span data-ttu-id="e8394-335">Dock 2 관련 작업에 대한 UEFI 관리자 지원</span><span class="sxs-lookup"><span data-stu-id="e8394-335">Support for UEFI Manager for Dock 2-related operations.</span></span>
- <span data-ttu-id="e8394-336">Surface Go 패키지 버그 수정.</span><span class="sxs-lookup"><span data-stu-id="e8394-336">A Surface Go reset package bug fix.</span></span>
- <span data-ttu-id="e8394-337">Surface Hub OS에서 Windows 10 Team 또는 Windows 10 Pro 장치로 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e8394-337">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <a name="version-2711390"></a><span data-ttu-id="e8394-338">버전 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="e8394-338">Version 2.71.139.0</span></span>

<span data-ttu-id="e8394-339">이 버전의 SEMM은 Surface Book 3, Surface Laptop 3 및 Surface Pro 7에 대한 Surface Dock 2 관리 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-339">This version of SEMM adds support for Surface Dock 2 management features for Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="e8394-340">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-340">It includes:</span></span>

- <span data-ttu-id="e8394-341">오디오(잠금/잠금 해제) 및 이더넷 및 USB 포트를 사용하도록 설정하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-341">The ability to enable audio (lock/unlock), and Ethernet and USB ports.</span></span>
- <span data-ttu-id="e8394-342">인증된 호스트와 인증되지 않은 호스트 모두에 대해 Dock 패키지를 만드는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-342">The ability to create dock packages for both authenticated and unauthenticated hosts.</span></span>

### <a name="version-2701300"></a><span data-ttu-id="e8394-343">버전 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="e8394-343">Version 2.70.130.0</span></span>

<span data-ttu-id="e8394-344">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-344">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-345">Surface Go 2에 대한 지원.</span><span class="sxs-lookup"><span data-stu-id="e8394-345">Support for Surface Go 2.</span></span>
- <span data-ttu-id="e8394-346">Surface Book 지원 3.</span><span class="sxs-lookup"><span data-stu-id="e8394-346">Support for Surface Book 3.</span></span>
- <span data-ttu-id="e8394-347">버그 수정.</span><span class="sxs-lookup"><span data-stu-id="e8394-347">Bug fixes.</span></span>

### <a name="version-2591390"></a><span data-ttu-id="e8394-348">버전 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="e8394-348">Version 2.59.139.0</span></span>

<span data-ttu-id="e8394-349">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-349">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-350">Intel 프로세서가 Surface Pro 7, Surface Pro X 및 Surface Laptop 3 13.5인치 및 15인치 모델이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-350">Support for Surface Pro 7, Surface Pro X, and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span> 
    >[!NOTE]
    ><span data-ttu-id="e8394-351">Surface Laptop 3 15인치 AMD 프로세서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-351">Surface Laptop 3 15" AMD processor isn't supported.</span></span>
- <span data-ttu-id="e8394-352">절전 모드 해제 기능 지원.</span><span class="sxs-lookup"><span data-stu-id="e8394-352">Support for the Wake on Power feature.</span></span>

### <a name="version-2541390"></a><span data-ttu-id="e8394-353">버전 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="e8394-353">Version 2.54.139.0</span></span>

<span data-ttu-id="e8394-354">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-354">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-355">2S Surface Hub 지원.</span><span class="sxs-lookup"><span data-stu-id="e8394-355">Support for Surface Hub 2S.</span></span>
- <span data-ttu-id="e8394-356">버그 수정.</span><span class="sxs-lookup"><span data-stu-id="e8394-356">Bug fixes.</span></span>

### <a name="version-2431360"></a><span data-ttu-id="e8394-357">버전 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="e8394-357">Version 2.43.136.0</span></span>

<span data-ttu-id="e8394-358">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-358">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-359">동시 다중 스레드를 활성화/비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-359">Support to enable/disable simultaneous multithreading.</span></span>
- <span data-ttu-id="e8394-360">일부 디바이스에 대해 무선 네트워킹 및 Bluetooth 별도의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-360">Separate options for wireless networking and Bluetooth for some devices.</span></span>
- <span data-ttu-id="e8394-361">배터리 제한이 제거된 Surface Studio.</span><span class="sxs-lookup"><span data-stu-id="e8394-361">Battery Limit removed for Surface Studio.</span></span>

### <a name="version-2261360"></a><span data-ttu-id="e8394-362">버전 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="e8394-362">Version 2.26.136.0</span></span>

<span data-ttu-id="e8394-363">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-363">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-364">Surface Studio 지원 2.</span><span class="sxs-lookup"><span data-stu-id="e8394-364">Support for Surface Studio 2.</span></span>
- <span data-ttu-id="e8394-365">배터리 제한 기능.</span><span class="sxs-lookup"><span data-stu-id="e8394-365">Battery Limit feature.</span></span>

### <a name="version-2211360"></a><span data-ttu-id="e8394-366">버전 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="e8394-366">Version 2.21.136.0</span></span>

<span data-ttu-id="e8394-367">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-367">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-368">Surface Pro 6.</span><span class="sxs-lookup"><span data-stu-id="e8394-368">Support for Surface Pro 6.</span></span>
- <span data-ttu-id="e8394-369">Surface Laptop 지원 2.</span><span class="sxs-lookup"><span data-stu-id="e8394-369">Support for Surface Laptop 2.</span></span>

### <a name="version-2141360"></a><span data-ttu-id="e8394-370">버전 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="e8394-370">Version 2.14.136.0</span></span>

<span data-ttu-id="e8394-371">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-371">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-372">Surface Go 지원.</span><span class="sxs-lookup"><span data-stu-id="e8394-372">Support for Surface Go.</span></span>

### <a name="version-291360"></a><span data-ttu-id="e8394-373">버전 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="e8394-373">Version 2.9.136.0</span></span>

<span data-ttu-id="e8394-374">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-374">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-375">Surface Book 지원 2.</span><span class="sxs-lookup"><span data-stu-id="e8394-375">Support for Surface Book 2.</span></span>
- <span data-ttu-id="e8394-376">LTE Surface Pro 지원.</span><span class="sxs-lookup"><span data-stu-id="e8394-376">Support for Surface Pro LTE.</span></span>
- <span data-ttu-id="e8394-377">접근성 개선.</span><span class="sxs-lookup"><span data-stu-id="e8394-377">Accessibility improvements.</span></span>

### <a name="version-10740"></a><span data-ttu-id="e8394-378">버전 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="e8394-378">Version 1.0.74.0</span></span>

<span data-ttu-id="e8394-379">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8394-379">This version of SEMM includes:</span></span>

- <span data-ttu-id="e8394-380">지원 Surface Laptop.</span><span class="sxs-lookup"><span data-stu-id="e8394-380">Support for Surface Laptop.</span></span>
- <span data-ttu-id="e8394-381">지원 Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="e8394-381">Support for Surface Pro.</span></span>
- <span data-ttu-id="e8394-382">버그 수정 및 일반적인 개선</span><span class="sxs-lookup"><span data-stu-id="e8394-382">Bug fixes and general improvements.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8394-383">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e8394-383">Related topics</span></span>

- [<span data-ttu-id="e8394-384">SEMM을 사용하여 Surface 장치 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="e8394-384">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="e8394-385">SEMM에서 Surface 디바이스 등록 취소</span><span class="sxs-lookup"><span data-stu-id="e8394-385">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="e8394-386">Secure Surface Dock 2 포트(SEMM 포함)</span><span class="sxs-lookup"><span data-stu-id="e8394-386">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)
