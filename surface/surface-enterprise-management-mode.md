---
title: Surface 엔터프라이즈 관리 모드(Surface)
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
ms.date: 01/15/2021
ms.openlocfilehash: e6f81639253c646f5d3956243a80f4d61c91028a
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271422"
---
# <span data-ttu-id="56370-104">Microsoft Surface 엔터프라이즈 관리 모드</span><span class="sxs-lookup"><span data-stu-id="56370-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="56370-105">Microsoft Surface SEMM(엔터프라이즈 관리 모드)은 조직 내에서 펌웨어 설정을 보호하고 관리할 수 있는 Surface UEFI가 있는 Surface 디바이스의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface UEFI that allows you to secure and manage firmware settings within your organization.</span></span> <span data-ttu-id="56370-106">SEMM을 사용하여 IT 전문가는 UEFI 설정 구성을 준비하고 Surface 디바이스에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-106">With SEMM, IT professionals can prepare configurations of UEFI settings and install them on a Surface device.</span></span> <span data-ttu-id="56370-107">UEFI 설정을 구성하는 기능 외에도 SEMM은 인증서를 사용하여 무단 변조 또는 제거로부터 구성을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-107">In addition to the ability to configure UEFI settings, SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="56370-108">SEMM은 Surface Hub 2S를 Windows 10 Pro 및 Enterprise로 마이그레이션할 수 있는 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-108">SEMM is a requirement to be able to migrate a Surface Hub 2S to Windows 10 Pro and Enterprise.</span></span>

>[!NOTE]
><span data-ttu-id="56370-109">SEMM은 Surface UEFI 펌웨어가 있는 디바이스에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-109">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="56370-110">이 구성은 Surface Pro 7+, Surface Pro X, Surface Hub 2S 및 Surface Laptop 3 상업용 SKUS(Intel 프로세서 포함) 및 Surface Laptop Go를 비롯한 대부분의 다른 Surface 장치로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-110">This comprises most other Surface devices including Surface Pro 7+, Surface Pro X, Surface Hub 2S, and Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="56370-111">SEMM은 AMD 프로세서가 있는 15인치 Surface Laptop 3 SKU에서 지원되지 않습니다(일반 정품 SKU로만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="56370-111">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (only available as a retail SKU).</span></span> 

<span data-ttu-id="56370-112">Surface 디바이스가 SEMM에 의해 구성 및 SEMM 인증서로 \*\* 보호되면 SEMM에 등록된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-112">When Surface devices are configured by SEMM and secured with the SEMM certificate, they are considered *enrolled* in SEMM.</span></span> <span data-ttu-id="56370-113">SEMM 인증서가 제거되고 UEFI 설정 제어가 디바이스 사용자에게 반환되면 Surface 디바이스는 SEMM에서 등록되지 않은 것으로 간주됩니다. \*\*</span><span class="sxs-lookup"><span data-stu-id="56370-113">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="56370-114">SEMM을 관리하고 Surface 디바이스를 등록하는 데 사용할 수 있는 두 가지 관리 옵션( 독립 실행형 도구 또는 Microsoft Endpoint Configuration Manager와의 통합)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-114">There are two administrative options you can use to manage SEMM and enroll Surface devices – a standalone tool or integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="56370-115">이 문서에서는 Microsoft Surface UEFI 구성기라고 하는 SEMM 독립 실행형 도구에 대해 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-115">The SEMM standalone tool, called the Microsoft Surface UEFI Configurator, is described in this article.</span></span> <span data-ttu-id="56370-116">Microsoft Endpoint Configuration Manager를 사용하여 SEMM을 관리하는 방법에 대한 자세한 내용은 [Microsoft Endpoint Configuration Manager를 사용하여 SEMM을](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)사용하여 디바이스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-116">For more information about how to manage SEMM with Microsoft Endpoint Configuration Manager, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>


## <span data-ttu-id="56370-117">Microsoft Surface UEFI 구성기</span><span class="sxs-lookup"><span data-stu-id="56370-117">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="56370-118">SEMM의 기본 작업 영역은 그림 1에 표시된 Microsoft Surface UEFI 구성기입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-118">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> <span data-ttu-id="56370-119">Microsoft Surface UEFI 구성기는 Surface 디바이스에서 SEMM 등록, 구성 및 등록을 해지하는 데 사용되는 Windows Installer(.msi) 패키지 또는 WinPE 이미지를 만드는 데 사용되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-119">Microsoft Surface UEFI Configurator is a tool used to create Windows Installer (.msi) packages or WinPE images used to enroll, configure, and unenroll SEMM on a Surface device.</span></span> <span data-ttu-id="56370-120">이러한 패키지에는 UEFI에 대한 설정이 지정된 구성 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-120">These packages contain a configuration file where the settings for UEFI are specified.</span></span> <span data-ttu-id="56370-121">SEMM 패키지에는 펌웨어에 설치 및 저장되고 UEFI 설정이 적용되기 전에 구성 파일의 서명을 확인하는 데 사용되는 인증서도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-121">SEMM packages also contain a certificate, which is installed and stored in firmware and used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!NOTE]
><span data-ttu-id="56370-122">이제 Surface UEFI 구성기 및 SEMM을 사용하여 Surface Dock 2에서 포트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-122">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="56370-123">자세한 내용은 [SEMM을 통해 Secure Surface Dock 2 포트를 참조합니다.](secure-surface-dock-ports-semm.md)</span><span class="sxs-lookup"><span data-stu-id="56370-123">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI 구성기](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="56370-125">그림 1.</span><span class="sxs-lookup"><span data-stu-id="56370-125">Figure 1.</span></span> <span data-ttu-id="56370-126">Microsoft Surface UEFI 구성기</span><span class="sxs-lookup"><span data-stu-id="56370-126">Microsoft Surface UEFI Configurator</span></span>*


<span data-ttu-id="56370-127">Microsoft Surface UEFI 구성기 도구를 세 가지 모드로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-127">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

* <span data-ttu-id="56370-128">[Surface UEFI 구성 패키지.](#configuration-package)</span><span class="sxs-lookup"><span data-stu-id="56370-128">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="56370-129">이 모드를 사용하여 Surface UEFI 구성 패키지를 만들어 SEMM에 Surface 디바이스를 등록하고 등록된 디바이스에서 UEFI 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-129">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
* <span data-ttu-id="56370-130">[Surface UEFI 재설정 패키지.](#reset-package)</span><span class="sxs-lookup"><span data-stu-id="56370-130">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="56370-131">이 모드를 사용하여 SEMM에서 Surface 디바이스의 선택을 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="56370-131">Use this mode to unenroll a Surface device from SEMM.</span></span>
* <span data-ttu-id="56370-132">[Surface UEFI 복구 요청.](#recovery-request)</span><span class="sxs-lookup"><span data-stu-id="56370-132">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="56370-133">이 모드를 사용하여 복구 요청에 응답하여 패키지 다시 설정 작업이 성공하지 않은 SEMM에서 Surface 디바이스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-133">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>


#### <span data-ttu-id="56370-134">Microsoft Surface UEFI 구성기 다운로드</span><span class="sxs-lookup"><span data-stu-id="56370-134">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="56370-135">Microsoft Surface UEFI 구성기는 Microsoft 다운로드 센터의 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-135">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <span data-ttu-id="56370-136">구성 패키지</span><span class="sxs-lookup"><span data-stu-id="56370-136">Configuration package</span></span>

<span data-ttu-id="56370-137">Surface UEFI 구성 패키지는 Surface 디바이스에서 SEMM을 구현하고 관리하는 기본 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-137">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="56370-138">이러한 패키지에는 그림 2와 같이 Microsoft Surface UEFI 구성기에서 패키지를 만들 때 지정된 UEFI 설정의 구성 파일과 인증서 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-138">These packages contain a configuration file of UEFI settings specified during creation of the package in Microsoft Surface UEFI Configurator and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="56370-139">SEMM에 아직 등록되지 않은 Surface 디바이스에서 구성 패키지를 처음으로 실행하면 디바이스의 펌웨어에 인증서 파일을 프로비전하고 SEMM에 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-139">When a configuration package is run for the first time on a Surface device that is not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="56370-140">SEMM에 장치를 등록할 때 인증서 파일이 저장되고 등록을 완료하기 전에 SEMM 인증서 지문의 마지막 두 자리를 제공하여 작업을 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-140">When enrolling a device in SEMM, you will be prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint before the certificate file is stored and the enrollment can complete.</span></span> <span data-ttu-id="56370-141">이 확인을 수행하려면 등록 시 장치에 사용자가 실제로 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-141">This confirmation requires a user be physically present at the device at the time of enrollment to perform the confirmation.</span></span>

![인증서를 통해 SEMM 구성 패키지 보안](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="56370-143">그림 2.</span><span class="sxs-lookup"><span data-stu-id="56370-143">Figure 2.</span></span> <span data-ttu-id="56370-144">인증서를 통해 SEMM 구성 패키지 보안</span><span class="sxs-lookup"><span data-stu-id="56370-144">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="56370-145">SEMM 인증서의 요구 사항에 대한 자세한 내용은 이 문서의 [Surface 엔터프라이즈](#surface-enterprise-management-mode-certificate-requirements) 관리 모드 인증서 요구 사항 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56370-145">See the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section of this article for more information about the requirements for the SEMM certificate.</span></span>

>[!NOTE]
><span data-ttu-id="56370-146">Surface UEFI의 **보안,** **장치,** 부팅 구성 또는 엔터프라이즈 관리 \*\*\*\* 페이지를 보는 \*\*\*\* 데 필요한 SEMM을 사용하여 UEFI 암호를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-146">You can also specify a UEFI password with SEMM that is required to view the **Security**, **Devices**, **Boot Configuration**, or **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="56370-147">장치가 SEMM에 등록된 후 구성 파일을 읽고 파일에 지정된 설정이 UEFI에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-147">After a device is enrolled in SEMM, the configuration file is read and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="56370-148">SEMM에 이미 등록된 장치에서 구성 패키지를 실행하면 구성 파일의 서명이 장치 펌웨어에 저장된 인증서를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-148">When you run a configuration package on a device that is already enrolled in SEMM, the signature of the configuration file is checked against the certificate that is stored in the device firmware.</span></span> <span data-ttu-id="56370-149">서명이 일치하지 않는 경우 장치에 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-149">If the signature does not match, no changes are applied to the device.</span></span>

### <span data-ttu-id="56370-150">SEMM을 사용하여 Surface UEFI에서 디바이스를 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="56370-150">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="56370-151">다음 목록에는 SEMM에서 관리할 수 있는 모든 사용 가능한 장치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-151">The following list shows all the available devices you can manage in SEMM:</span></span>

* <span data-ttu-id="56370-152">도킹 USB 포트</span><span class="sxs-lookup"><span data-stu-id="56370-152">Docking USB Port</span></span>
* <span data-ttu-id="56370-153">탑재된 오디오</span><span class="sxs-lookup"><span data-stu-id="56370-153">On-board Audio</span></span>
* <span data-ttu-id="56370-154">DGPU</span><span class="sxs-lookup"><span data-stu-id="56370-154">DGPU</span></span>
* <span data-ttu-id="56370-155">타이핑 커버</span><span class="sxs-lookup"><span data-stu-id="56370-155">Type Cover</span></span>
* <span data-ttu-id="56370-156">Micro SD 카드</span><span class="sxs-lookup"><span data-stu-id="56370-156">Micro SD Card</span></span>
* <span data-ttu-id="56370-157">전면 카메라</span><span class="sxs-lookup"><span data-stu-id="56370-157">Front Camera</span></span>
* <span data-ttu-id="56370-158">후면 카메라</span><span class="sxs-lookup"><span data-stu-id="56370-158">Rear Camera</span></span>
* <span data-ttu-id="56370-159">적외선 카메라, Windows Hello용</span><span class="sxs-lookup"><span data-stu-id="56370-159">Infrared Camera, for Windows Hello</span></span>
* <span data-ttu-id="56370-160">Bluetooth 전용</span><span class="sxs-lookup"><span data-stu-id="56370-160">Bluetooth Only</span></span>
* <span data-ttu-id="56370-161">Wi-Fi 및 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="56370-161">Wi-Fi and Bluetooth</span></span>
* <span data-ttu-id="56370-162">             LTE           </span><span class="sxs-lookup"><span data-stu-id="56370-162">LTE</span></span>

 >[!NOTE]
><span data-ttu-id="56370-163">UEFI 장치 페이지에 나타나는 기본 제공 장치는 장치 또는 회사 환경에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-163">The built-in devices that appear in the UEFI Devices page may vary depending on your device or corporate environment.</span></span> <span data-ttu-id="56370-164">예를 들어 UEFI 장치 페이지는 Surface Pro X에서 지원되지 않습니다. LTE는 LTE가 탑재된 디바이스에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-164">For example, the UEFI Devices page is not supported on Surface Pro X; LTE only appears on LTE-equipped devices.</span></span> 
### <span data-ttu-id="56370-165">SEMM을 사용하여 고급 설정 구성</span><span class="sxs-lookup"><span data-stu-id="56370-165">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="56370-166">표 1.</span><span class="sxs-lookup"><span data-stu-id="56370-166">Table 1.</span></span> <span data-ttu-id="56370-167">고급 설정</span><span class="sxs-lookup"><span data-stu-id="56370-167">Advanced settings</span></span>**

| <span data-ttu-id="56370-168">설정</span><span class="sxs-lookup"><span data-stu-id="56370-168">Setting</span></span>                            | <span data-ttu-id="56370-169">설명</span><span class="sxs-lookup"><span data-stu-id="56370-169">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="56370-170">PXE 부팅용 IPv6</span><span class="sxs-lookup"><span data-stu-id="56370-170">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="56370-171">PXE 부팅에 대한 IPv6 지원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-171">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="56370-172">이 설정을 구성하지 않는 경우 PXE 부팅에 대한 IPv6 지원이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-172">If you do not configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="56370-173">대체 부팅</span><span class="sxs-lookup"><span data-stu-id="56370-173">Alternate Boot</span></span>                     | <span data-ttu-id="56370-174">부팅하는 동안 볼륨 다운 단추와 전원 단추를 모두 눌러 USB 또는 이더넷 디바이스로 직접 부팅하는 대체 부팅 순서 사용을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-174">Allows you to manage use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="56370-175">이 설정을 구성하지 않은 경우 대체 부팅이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-175">If you do not configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="56370-176">부팅 순서 잠금</span><span class="sxs-lookup"><span data-stu-id="56370-176">Boot Order Lock</span></span>                    | <span data-ttu-id="56370-177">변경을 방지하기 위해 부팅 순서를 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-177">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="56370-178">이 설정을 구성하지 않은 경우 부팅 순서 잠금이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-178">If you do not configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="56370-179">USB 부팅</span><span class="sxs-lookup"><span data-stu-id="56370-179">USB Boot</span></span>                           | <span data-ttu-id="56370-180">USB 장치에 대한 부팅을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-180">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="56370-181">이 설정을 구성하지 않은 경우 USB 부팅이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-181">If you do not configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="56370-182">네트워크 스택</span><span class="sxs-lookup"><span data-stu-id="56370-182">Network Stack</span></span>                      | <span data-ttu-id="56370-183">네트워크 스택 부팅 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-183">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="56370-184">이 설정을 구성하지 않는 경우 네트워크 스택 부팅 설정을 관리하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-184">If you do not configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="56370-185">자동 전원 공급</span><span class="sxs-lookup"><span data-stu-id="56370-185">Auto Power On</span></span>                      | <span data-ttu-id="56370-186">부팅 시 자동 전원 사용 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-186">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="56370-187">이 설정을 구성하지 않은 경우 자동 전원 사용이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-187">If you do not configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="56370-188">SMT(동시 다중 스레딩)</span><span class="sxs-lookup"><span data-stu-id="56370-188">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="56370-189">SMT(동시 다중 스레딩)를 관리하여 하이퍼스레딩을 활성화 또는 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-189">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="56370-190">이 설정을 구성하지 않은 경우 SMT가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-190">If you do not configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="56370-191">배터리 제한 사용</span><span class="sxs-lookup"><span data-stu-id="56370-191">Enable Battery limit</span></span>| <span data-ttu-id="56370-192">배터리 제한 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-192">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="56370-193">이 설정을 구성하지 않은 경우 배터리 제한이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-193">If you do not configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="56370-194">보안</span><span class="sxs-lookup"><span data-stu-id="56370-194">Security</span></span>                           | <span data-ttu-id="56370-195">Surface UEFI \*\*\*\* 보안 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-195">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="56370-196">이 설정을 구성하지 않은 경우 보안 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-196">If you do not configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="56370-197">장치</span><span class="sxs-lookup"><span data-stu-id="56370-197">Devices</span></span>                            | <span data-ttu-id="56370-198">Surface UEFI **장치** 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-198">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="56370-199">이 설정을 구성하지 않은 경우 장치 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-199">If you do not configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="56370-200">Boot</span><span class="sxs-lookup"><span data-stu-id="56370-200">Boot</span></span>                               | <span data-ttu-id="56370-201">Surface UEFI \*\*\*\* 부팅 페이지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-201">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="56370-202">이 설정을 구성하지 않은 경우 부팅 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-202">If you do not configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="56370-203">DateTime</span><span class="sxs-lookup"><span data-stu-id="56370-203">DateTime</span></span>                           | <span data-ttu-id="56370-204">Surface UEFI **DateTime 페이지를** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-204">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="56370-205">이 설정을 구성하지 않은 경우 DateTime 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-205">If you do not configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="56370-206">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="56370-206">EnableOSMigration</span></span>                          | <span data-ttu-id="56370-207">Surface Hub 2를 Windows 10 Team에서 Windows 10 Pro 또는 Enterprise로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-207">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="56370-208">이 설정을 구성하지 않는 경우 Surface Hub 2 장치는 Windows 10 Team OS만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-208">If you do not configure this setting, Surface Hub 2 devices can only run Windows 10 Team OS.</span></span>   <span data-ttu-id="56370-209">참고: Surface Hub 2에서는 Windows 10 Team과 Windows 10 Pro/Enterprise 간의 이중 부팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-209">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise  is not available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="56370-210">SEMM 구성 패키지를 만들면 그림 3과 같이 성공 페이지에 두 문자가 표시됩니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="56370-210">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![인증서 지문 표시](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="56370-212">그림 3.</span><span class="sxs-lookup"><span data-stu-id="56370-212">Figure 3.</span></span> <span data-ttu-id="56370-213">성공 페이지에 인증서 지문의 마지막 두 문자 표시</span><span class="sxs-lookup"><span data-stu-id="56370-213">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="56370-214">이러한 문자는 인증서 지문의 마지막 두 문자로, 기록하거나 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-214">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="56370-215">그림 4에 표시된 같이 문자는 Surface 디바이스의 SEMM 등록을 확인하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-215">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM의 등록 확인](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="56370-217">그림 4.</span><span class="sxs-lookup"><span data-stu-id="56370-217">Figure 4.</span></span> <span data-ttu-id="56370-218">SEMM 인증서 지문을 통해 SEMM의 등록 확인</span><span class="sxs-lookup"><span data-stu-id="56370-218">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="56370-219">인증서 파일(.pfx)에 액세스할 수 있는 관리자는 CertMgr에서 .pfx 파일을 열고 지문을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-219">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="56370-220">CertMgr로 지문을 보시고 다음 프로세스를 따르고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-220">To view the thumbprint with CertMgr, follow this process:</span></span>
>1. <span data-ttu-id="56370-221">.pfx 파일을 마우스 오른쪽 단추로 클릭한 다음 **열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="56370-221">Right-click the .pfx file, and then click **Open**.</span></span>
>2. <span data-ttu-id="56370-222">탐색 창에서 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-222">Expand the folder in the navigation pane.</span></span>
>3. <span data-ttu-id="56370-223">**인증서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-223">Click **Certificates**.</span></span>
>4. <span data-ttu-id="56370-224">주 창에서 인증서를 마우스 오른쪽 단추로 클릭한 다음 **열기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="56370-224">Right-click your certificate in the main pane, and then click **Open**.</span></span>
>5. <span data-ttu-id="56370-225">세부 **정보 탭을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-225">Click the **Details** tab.</span></span>
>6. <span data-ttu-id="56370-226">**전체** 또는 **속성만** 드롭다운 \*\*\*\* 표시 메뉴에서 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-226">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
>7. <span data-ttu-id="56370-227">지문 **필드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="56370-227">Select the field **Thumbprint**.</span></span>

<span data-ttu-id="56370-228">SEMM에 Surface 디바이스를 등록하거나 구성 패키지에서 UEFI 구성을 적용하려면 의도한 Surface 디바이스에 대한 관리 권한으로 .msi 파일을 실행하기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-228">To enroll a Surface device in SEMM or to apply the UEFI configuration from a configuration package, all you need to do is run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="56370-229">[Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) 또는 Microsoft Deployment Manager와 같은 응용 프로그램 배포 또는 운영 체제 배포 기술을 사용할 수 Toolkit. [](https://technet.microsoft.com/windows/dn475741)</span><span class="sxs-lookup"><span data-stu-id="56370-229">You can use application deployment or operating system deployment technologies such as [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="56370-230">SEMM에 장치를 등록할 때 디바이스에 등록을 확인하려면 물리적으로 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-230">When you enroll a device in SEMM you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="56370-231">SEMM에 이미 등록된 장치에 구성을 적용할 때 사용자 조작이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-231">User interaction is not required when you apply a configuration to devices that are already enrolled in SEMM.</span></span>

<span data-ttu-id="56370-232">SEMM에 Surface 디바이스를 등록하거나 SEMM을 사용하여 Surface UEFI 구성을 적용하는 방법에 대한 단계별 단계를 확인하려면 [SEMM을](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)사용하여 Surface 디바이스 등록 및 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56370-232">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <span data-ttu-id="56370-233">패키지 초기화</span><span class="sxs-lookup"><span data-stu-id="56370-233">Reset package</span></span>

<span data-ttu-id="56370-234">Surface UEFI 재설정 패키지는 SEMM에서 Surface 디바이스를 초기화하는 하나의 작업만 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-234">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="56370-235">재설정 패키지에는 장치의 펌웨어에서 SEMM 인증서를 제거하고 UEFI 설정을 공장 기본값으로 다시 설정하는 서명된 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-235">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to factory default.</span></span> <span data-ttu-id="56370-236">Surface UEFI 구성 패키지와 마찬가지로 초기화 패키지는 Surface 디바이스에 프로비전된 동일한 SEMM 인증서를 사용하여 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-236">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that is provisioned on the Surface device.</span></span> <span data-ttu-id="56370-237">SEMM 재설정 패키지를 만들 때 초기화하려는 Surface 디바이스의 일련 번호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-237">When you create a SEMM reset package, you are required to supply the serial number of the Surface device you intend to reset.</span></span> <span data-ttu-id="56370-238">SEMM 초기화 패키지는 범용이 아니며 한 장치에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-238">SEMM reset packages are not universal and are specific to one device.</span></span>

### <span data-ttu-id="56370-239">복구 요청</span><span class="sxs-lookup"><span data-stu-id="56370-239">Recovery request</span></span>

<span data-ttu-id="56370-240">일부 시나리오에서는 Surface UEFI 재설정 패키지를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-240">In some scenarios, it may be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="56370-241">예를 들어 Surface 디바이스에서 Windows를 사용할 수 없는 경우) 이러한 시나리오에서는 복구 요청 작업을 사용하여 Surface UEFI의 엔터프라이즈 관리 페이지(그림 5에 표시)를 통해 SEMM에서 Surface 디바이스의 설치를 회수할 수 있습니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="56370-241">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

![SEMM 복구 요청 시작](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="56370-243">그림 5.</span><span class="sxs-lookup"><span data-stu-id="56370-243">Figure 5.</span></span> <span data-ttu-id="56370-244">엔터프라이즈 관리 페이지에서 SEMM 복구 요청 시작</span><span class="sxs-lookup"><span data-stu-id="56370-244">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="56370-245">엔터프라이즈 관리 페이지의 프로세스를 \*\*\*\* 사용하여 Surface 디바이스에서 SEMM을 다시 설정하는 경우 초기화 요청이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-245">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you are provided with a Reset Request.</span></span> <span data-ttu-id="56370-246">이 재설정 요청은 USB 드라이브에 파일로 저장하거나 텍스트로 복사하거나 모바일 장치를 사용하여 QR 코드로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-246">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="56370-247">Microsoft Surface UEFI 구성기 다시 설정 요청 옵션을 사용하여 다시 설정 요청 파일을 로드하거나 다시 설정 요청 텍스트 또는 QR 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-247">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="56370-248">Microsoft Surface UEFI 구성기는 Surface 디바이스에 입력할 수 있는 확인 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-248">Microsoft Surface UEFI Configurator will generate a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="56370-249">Surface 디바이스에 코드를 입력하고 다시 \*\*\*\* 시작을 클릭하면 디바이스가 SEMM에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-249">If you enter the code on the Surface device and click **Restart**, the device will be unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="56370-250">초기화 요청은 작성된 후 2시간 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-250">A Reset Request expires two hours after it is created.</span></span>

<span data-ttu-id="56370-251">SEMM에서 Surface 디바이스의 사용을 끄는 방법에 대한 단계별 실무는 [SEMM에서 Surface](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)디바이스의 사용 안을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-251">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="56370-252">Surface 엔터프라이즈 관리 모드 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="56370-252">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="56370-253">Microsoft Surface UEFI 구성기에서 SEMM을 사용하려면 UEFI 설정을 적용하기 전에 인증서를 통해 구성 파일의 서명을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-253">Using SEMM with Microsoft Surface UEFI Configurator requires a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="56370-254">이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지만 UEFI 설정을 수정하는 데 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-254">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span>

>[!NOTE]
><span data-ttu-id="56370-255">등록된 Surface 디바이스에서 SEMM 또는 Surface UEFI 설정을 수정하려면 SEMM 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-255">The SEMM certificate is required to perform any modification to SEMM or Surface UEFI settings on enrolled Surface devices.</span></span> <span data-ttu-id="56370-256">SEMM 인증서가 손상되거나 손실된 경우 SEMM을 제거하거나 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-256">If the SEMM certificate is corrupted or lost, SEMM cannot be removed or reset.</span></span> <span data-ttu-id="56370-257">백업 및 복구를 위한 적절한 솔루션을 사용하여 SEMM 인증서를 적절하게 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-257">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery.</span></span>

<span data-ttu-id="56370-258">Microsoft Surface UEFI 구성기 도구를 사용하여 만든 패키지는 인증서로 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-258">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="56370-259">이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지만 UEFI 설정을 수정하는 데 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-259">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <span data-ttu-id="56370-260">권장 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="56370-260">Recommended certificate settings</span></span>
<span data-ttu-id="56370-261">SEMM 인증서에 권장되는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-261">The following settings are recommended for the SEMM certificate:</span></span>

* <span data-ttu-id="56370-262">**키 알고리즘** - RSA</span><span class="sxs-lookup"><span data-stu-id="56370-262">**Key Algorithm** – RSA</span></span> 
* <span data-ttu-id="56370-263">**키 길이** – 2048</span><span class="sxs-lookup"><span data-stu-id="56370-263">**Key Length** – 2048</span></span>
* <span data-ttu-id="56370-264">**해시 알고리즘** - SHA-256</span><span class="sxs-lookup"><span data-stu-id="56370-264">**Hash Algorithm** – SHA-256</span></span>
* <span data-ttu-id="56370-265">**유형** - SSL 서버 인증</span><span class="sxs-lookup"><span data-stu-id="56370-265">**Type** – SSL Server Authentication</span></span>
* <span data-ttu-id="56370-266">**키 사용** - 디지털 서명, 키 인코더ment</span><span class="sxs-lookup"><span data-stu-id="56370-266">**Key Usage** – Digital signature, Key Encipherment</span></span>
* <span data-ttu-id="56370-267">**공급자** - Microsoft Enhanced RSA 및 AES 암호화 공급자</span><span class="sxs-lookup"><span data-stu-id="56370-267">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
* <span data-ttu-id="56370-268">**만료 날짜** - 인증서 생성 후 15개월</span><span class="sxs-lookup"><span data-stu-id="56370-268">**Expiration Date** – 15 Months from certificate creation</span></span>
* <span data-ttu-id="56370-269">**키 내보내기 정책** - 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-269">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="56370-270">또한 중간 CA(인증 기관)가 SEMM 전용인 2계층 PKI(공개 키 인프라) 아키텍처에서 SEMM 인증서를 인증하여 인증서 해지가 가능하게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-270">It is also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="56370-271">2계층 PKI 구성에 대한 자세한 내용은 테스트 랩 [가이드: AD CS](https://technet.microsoft.com/library/hh831348)및 PKI 계층 구조 Two-Tier 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56370-271">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <span data-ttu-id="56370-272">자체 서명된 인증서</span><span class="sxs-lookup"><span data-stu-id="56370-272">Self-signed certificate</span></span> 
<span data-ttu-id="56370-273">다음 예제 PowerShell 스크립트를 사용하여 개념 증명 시나리오에서 사용할 자체 서명된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-273">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="56370-274">이 스크립트를 사용 하 고 다음 텍스트를 메모장에 복사 하 고 파일을 PowerShell 스크립트 (.ps1)로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-274">To use this script, copy the following text into Notepad and save the file as a PowerShell script (.ps1).</span></span> 

> [!NOTE]
> <span data-ttu-id="56370-275">이 스크립트는 암호를 사용하여 인증서를 `12345678` 만듭니다. 이 스크립트로 생성된 인증서는 프로덕션 환경에서는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-275">This script creates a certificate with a password of `12345678`.The certificate generated by this script is not recommended for production environments.</span></span>
  
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
><span data-ttu-id="56370-276">SEMM 및 Microsoft Surface UEFI 구성기에서 사용하려면 개인 키와 암호 보호를 사용하여 인증서를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-276">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="56370-277">Microsoft Surface UEFI 구성기는 필요한 경우 SEMM 인증서 파일(.pfx) 및 인증서 암호를 선택하라는 메시지를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-277">Microsoft Surface UEFI Configurator will prompt you to select the SEMM certificate file (.pfx) and certificate password when it is required.</span></span>

1.  <span data-ttu-id="56370-278">C: 드라이브에 스크립트를 저장할 폴더를 만드시다. 예: C:\SEMM.</span><span class="sxs-lookup"><span data-stu-id="56370-278">Create a folder on your C: drive where you will save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="56370-279">예제 스크립트를 메모장이나 해당 텍스트 편집기로 복사하고 파일을 PowerShell 스크립트(.ps1)로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-279">Copy the example script into Notepad or equivalent text editor and save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="56370-280">관리자 자격 증명을 사용하여 PC에 로그인하고 관리자 권한 PowerShell 세션을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-280">Sign into your PC with administrator credentials and open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="56370-281">스크립트 실행을 허용하도록 사용 권한이 설정되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-281">Ensure your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="56370-282">기본적으로 실행 정책을 수정하지 않으면 스크립트가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-282">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="56370-283">자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)</span><span class="sxs-lookup"><span data-stu-id="56370-283">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="56370-284">명령 프롬프트에서 스크립트의 전체 경로를 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-284">At the command prompt, enter the full path of the script and then press Enter.</span></span> <span data-ttu-id="56370-285">이 스크립트는 TempOwner.pfx라는 데모 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56370-285">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="56370-286">또는 PowerShell을 사용하여 자체 서명된 인증서를 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-286">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="56370-287">자세한 내용은 PowerShell 설명서인 [New-SelfSignedCertificate를 참조하세요.](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)</span><span class="sxs-lookup"><span data-stu-id="56370-287">For more information, see the following PowerShell documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>




>[!NOTE]
><span data-ttu-id="56370-288">PKI 인프라에서 오프라인 루트를 사용하는 조직의 경우 SEMM 인증서를 인증하려면 루트 CA에 연결된 환경에서 Microsoft Surface UEFI Configurator를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-288">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="56370-289">Microsoft Surface UEFI 구성기에서 생성한 패키지는 파일로 전송할 수 있으므로 USB 스틱과 같은 이동식 저장소를 사용하여 오프라인 네트워크 환경 외부로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-289">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files and therefore can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <span data-ttu-id="56370-290">인증서 관리 FAQ</span><span class="sxs-lookup"><span data-stu-id="56370-290">Managing certificates FAQ</span></span>

<span data-ttu-id="56370-291">권장되는 *최소* 길이는 15개월입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-291">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="56370-292">15개월 미만 만료되는 인증서를 사용하거나 15개월 이상 만료되는 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-292">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="56370-293">인증서가 만료되면 자동으로 갱신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-293">When a certificate expires, it does not automatically renew.</span></span> 


**<span data-ttu-id="56370-294">만료된 인증서가 SEMM 등록 장치의 기능에 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="56370-294">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="56370-295">아니요. 인증서는 SEMM의 IT 관리자 관리 작업에만 영향을 주며 만료될 때 장치 기능에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-295">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>


**<span data-ttu-id="56370-296">SEMM 패키지 및 인증서가 있는 모든 컴퓨터의 SEMM 패키지 및 인증서를 업데이트해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="56370-296">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**

<span data-ttu-id="56370-297">SEMM 재설정 또는 복구가 작동하게 하려는 경우 인증서가 유효해야 하고 만료되지 않은 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="56370-297">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="56370-298">주문한 각 표면에 대해 대량 초기화 패키지를 만들 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="56370-298">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="56370-299">환경의 모든 컴퓨터를 다시 설정하는 기본 제공 컴퓨터를 구축할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="56370-299">Can one be built that resets all machines in our environment?</span></span>**

<span data-ttu-id="56370-300">특정 장치 유형에 대해 구성 패키지를 만드는 PowerShell 샘플을 사용하여 일련 번호가 독립적인 재설정 패키지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-300">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that is serial-number independent.</span></span> <span data-ttu-id="56370-301">인증서가 여전히 유효한 경우 PowerShell을 사용하여 SEMM을 다시 설정하는 재설정 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-301">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <span data-ttu-id="56370-302">버전 기록</span><span class="sxs-lookup"><span data-stu-id="56370-302">Version History</span></span>

### <span data-ttu-id="56370-303">버전 2.79.139.0</span><span class="sxs-lookup"><span data-stu-id="56370-303">Version 2.79.139.0</span></span>

<span data-ttu-id="56370-304">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-304">This version of SEMM includes:</span></span>
- <span data-ttu-id="56370-305">Surface Pro 7+ 지원</span><span class="sxs-lookup"><span data-stu-id="56370-305">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="56370-306">사용자 환경 개선</span><span class="sxs-lookup"><span data-stu-id="56370-306">User experience improvements</span></span>


### <span data-ttu-id="56370-307">버전 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="56370-307">Version 2.78.139.0</span></span>

<span data-ttu-id="56370-308">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-308">This version of SEMM includes:</span></span>

- <span data-ttu-id="56370-309">Surface 노트북 이동 및 Surface Pro X 지원</span><span class="sxs-lookup"><span data-stu-id="56370-309">Support for Surface Laptop Go and Surface Pro X</span></span>
- <span data-ttu-id="56370-310">새 버전 릴리스에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="56370-310">Notifications for new version release</span></span>
- <span data-ttu-id="56370-311">소유권을 변경하기 위해 사용자 지정 패키지를 만드는 능력</span><span class="sxs-lookup"><span data-stu-id="56370-311">Ability to create custom packages to change ownership</span></span>
- <span data-ttu-id="56370-312">버그 수정</span><span class="sxs-lookup"><span data-stu-id="56370-312">Bug fixes</span></span>

### <span data-ttu-id="56370-313">버전 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="56370-313">Version 2.73.136.0</span></span>

<span data-ttu-id="56370-314">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-314">This version of SEMM includes:</span></span>

- <span data-ttu-id="56370-315">이제 SEMM을 사용하여 Surface Hub2S에서 오디오를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-315">Audio can now be disabled on Surface Hub2S using SEMM</span></span>
- <span data-ttu-id="56370-316">Dock 2용 Surface Pro X 지원</span><span class="sxs-lookup"><span data-stu-id="56370-316">Support to Surface Pro X for Dock 2</span></span>
- <span data-ttu-id="56370-317">Dock 2 관련 작업에 대한 UEFI 관리자 지원</span><span class="sxs-lookup"><span data-stu-id="56370-317">Support to UEFI Manager for Dock 2 related operations</span></span>
- <span data-ttu-id="56370-318">Surface Go 초기화 패키지 버그 수정</span><span class="sxs-lookup"><span data-stu-id="56370-318">Surface Go reset package bug fix</span></span>
- <span data-ttu-id="56370-319">Windows 10 Team OS에서 Windows 10 Pro 또는 Enterprise로 Surface Hub 2 장치를 마이그레이션하는 데 대한 지원.</span><span class="sxs-lookup"><span data-stu-id="56370-319">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <span data-ttu-id="56370-320">버전 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="56370-320">Version 2.71.139.0</span></span>

<span data-ttu-id="56370-321">이 버전의 SEMM은 Surface Book 3, Surface Laptop 3 및 Surface Pro 7에 대한 Surface Dock 2 관리 기능에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-321">This version of SEMM adds support for Surface Dock 2 management features  for Surface Book 3, Surface Laptop 3, and Surface Pro 7 including:</span></span>

- <span data-ttu-id="56370-322">오디오 사용(잠금/잠금 해제), 이더넷 및 USB 포트</span><span class="sxs-lookup"><span data-stu-id="56370-322">Enabling audio (locking/unlocking), Ethernet and USB ports</span></span>
- <span data-ttu-id="56370-323">인증된 호스트와 인증되지 않은 호스트 모두에 대해 Dock 패키지를 만드는 능력</span><span class="sxs-lookup"><span data-stu-id="56370-323">Ability to create dock packages for both authenticated and unauthenticated hosts</span></span>

### <span data-ttu-id="56370-324">버전 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="56370-324">Version 2.70.130.0</span></span>

<span data-ttu-id="56370-325">이 SEMM 버전에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56370-325">This version of SEMM includes:</span></span>

- <span data-ttu-id="56370-326">Surface Go 2 지원</span><span class="sxs-lookup"><span data-stu-id="56370-326">Support for Surface Go 2</span></span>
- <span data-ttu-id="56370-327">Surface Book 3 지원</span><span class="sxs-lookup"><span data-stu-id="56370-327">Support for Surface Book 3</span></span>
- <span data-ttu-id="56370-328">버그 수정</span><span class="sxs-lookup"><span data-stu-id="56370-328">Bug fixes</span></span>


### <span data-ttu-id="56370-329">버전 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="56370-329">Version 2.59.139.0</span></span>

* <span data-ttu-id="56370-330">Intel 프로세서를 사용하는 Surface Pro 7, Surface Pro X 및 Surface Laptop 3 13.5" 및 15인치 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="56370-330">Support for Surface Pro 7, Surface Pro X,  and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span> <span data-ttu-id="56370-331">참고: Surface Laptop 3 15인치 AMD 프로세서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56370-331">Note:  Surface Laptop 3 15" AMD processor is not supported.</span></span>

- <span data-ttu-id="56370-332">절전 모드 해제 기능 지원</span><span class="sxs-lookup"><span data-stu-id="56370-332">Support for Wake on Power feature</span></span>

### <span data-ttu-id="56370-333">버전 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="56370-333">Version 2.54.139.0</span></span>
* <span data-ttu-id="56370-334">Surface Hub 2S 지원</span><span class="sxs-lookup"><span data-stu-id="56370-334">Support to Surface Hub 2S</span></span>
* <span data-ttu-id="56370-335">버그 수정</span><span class="sxs-lookup"><span data-stu-id="56370-335">Bug fixes</span></span>

### <span data-ttu-id="56370-336">버전 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="56370-336">Version 2.43.136.0</span></span>
* <span data-ttu-id="56370-337">시뮬레이트된 다중 생성을 활성화/비활성화하는 지원</span><span class="sxs-lookup"><span data-stu-id="56370-337">Support to enable/disable simulatenous multithreating</span></span> 
* <span data-ttu-id="56370-338">일부 장치에 대해 WiFi 및 Bluetooth 별도의 옵션</span><span class="sxs-lookup"><span data-stu-id="56370-338">Separate options for WiFi and Bluetooth for some devices</span></span> 
* <span data-ttu-id="56370-339">Surface Studio의 배터리 제한 제거됨</span><span class="sxs-lookup"><span data-stu-id="56370-339">Battery Limit removed for Surface Studio</span></span> 

### <span data-ttu-id="56370-340">버전 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="56370-340">Version 2.26.136.0</span></span>
* <span data-ttu-id="56370-341">Surface Studio 2에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-341">Add support to Surface Studio 2</span></span>
* <span data-ttu-id="56370-342">배터리 제한 기능</span><span class="sxs-lookup"><span data-stu-id="56370-342">Battery Limit feature</span></span>

### <span data-ttu-id="56370-343">버전 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="56370-343">Version 2.21.136.0</span></span>
* <span data-ttu-id="56370-344">Surface Pro 6에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-344">Add support to Surface Pro 6</span></span>
* <span data-ttu-id="56370-345">Surface 노트북 2에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-345">Add support to Surface Laptop 2</span></span>

### <span data-ttu-id="56370-346">버전 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="56370-346">Version 2.14.136.0</span></span>
* <span data-ttu-id="56370-347">Surface Go에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-347">Add support to Surface Go</span></span>

### <span data-ttu-id="56370-348">버전 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="56370-348">Version 2.9.136.0</span></span>
* <span data-ttu-id="56370-349">Surface Book 2에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-349">Add support to Surface Book 2</span></span>
* <span data-ttu-id="56370-350">Surface Pro LTE에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-350">Add support to Surface Pro LTE</span></span>
* <span data-ttu-id="56370-351">접근성 개선</span><span class="sxs-lookup"><span data-stu-id="56370-351">Accessibility improvements</span></span>

### <span data-ttu-id="56370-352">버전 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="56370-352">Version 1.0.74.0</span></span>
* <span data-ttu-id="56370-353">Surface 노트북에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-353">Add support to Surface Laptop</span></span>
* <span data-ttu-id="56370-354">Surface Pro에 지원 추가</span><span class="sxs-lookup"><span data-stu-id="56370-354">Add support to Surface Pro</span></span>
* <span data-ttu-id="56370-355">버그 수정 및 일반 개선</span><span class="sxs-lookup"><span data-stu-id="56370-355">Bug fixes and general improvement</span></span>

## <span data-ttu-id="56370-356">관련 항목</span><span class="sxs-lookup"><span data-stu-id="56370-356">Related topics</span></span>

- [<span data-ttu-id="56370-357">SEMM을 사용하여 Surface 장치 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="56370-357">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="56370-358">SEMM에서 Surface 디바이스 등록 취소</span><span class="sxs-lookup"><span data-stu-id="56370-358">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="56370-359">Secure Surface Dock 2 포트(SEMM 포함)</span><span class="sxs-lookup"><span data-stu-id="56370-359">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)
