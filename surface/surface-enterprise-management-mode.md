---
title: Surface (기업 엔터프라이즈 관리 모드)
description: Surface UEFI를 사용 하는 Surface 디바이스의이 기능을 사용 하 여 조직 내에서 펌웨어 설정을 보호 하 고 관리 하는 방법을 알아봅니다.
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
ms.date: 10/12/2020
ms.openlocfilehash: 463759d2dd01b9333d10a66c1781055f4a5217ac
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114646"
---
# <span data-ttu-id="e6578-104">Microsoft Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="e6578-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="e6578-105">Microsoft Surface Enterprise 관리 모드 (SEMM)는 조직 내에서 펌웨어 설정을 보호 하 고 관리 하는 데 사용할 수 있는 surface UEFI를 사용 하는 Surface 디바이스의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface UEFI that allows you to secure and manage firmware settings within your organization.</span></span> <span data-ttu-id="e6578-106">SEMM을 사용 하면 IT 전문가는 UEFI 설정의 구성을 준비 하 고 Surface 장치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-106">With SEMM, IT professionals can prepare configurations of UEFI settings and install them on a Surface device.</span></span> <span data-ttu-id="e6578-107">SEMM은 UEFI 설정을 구성 하는 기능 외에도 인증서를 사용 하 여 무단 무단 변경 또는 제거 로부터 구성을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-107">In addition to the ability to configure UEFI settings, SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="e6578-108">SEMM은 Surface Hub 2S Windows 10 Pro 및 Enterprise로 마이그레이션할 수 있어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-108">SEMM is a requirement to be able to migrate a Surface Hub 2S to Windows 10 Pro and Enterprise.</span></span>

>[!NOTE]
><span data-ttu-id="e6578-109">SEMM은 Surface UEFI 펌웨어가 있는 디바이스 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-109">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="e6578-110">이는 Surface Pro 7, Surface Pro X, Surface Hub 2S, surface 랩탑 3 상업용 Sku, 그리고 Intel 프로세서와 Surface 노트북을 포함 하는 대부분의 다른 표면 장치로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-110">This comprises most other Surface devices including Surface Pro 7, Surface Pro X, Surface Hub 2S, and Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="e6578-111">15 "Surface 랩탑 3 SKU (AMD 프로세서 포함)에서 지원 되지 않습니다 (정품 SKU로 서만 제공).</span><span class="sxs-lookup"><span data-stu-id="e6578-111">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (only available as a retail SKU).</span></span> 

<span data-ttu-id="e6578-112">Surface 디바이스는 SEMM로 구성 되 고 SEMM 인증서로 보호 되는 경우 SEMM로 *등록* 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-112">When Surface devices are configured by SEMM and secured with the SEMM certificate, they are considered *enrolled* in SEMM.</span></span> <span data-ttu-id="e6578-113">SEMM 인증서가 제거 되 고 UEFI 설정의 제어가 장치 사용자에 게 반환 되는 경우 Surface 디바이스는 *unenrolled* 로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-113">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="e6578-114">SEMM 및 Surface 디바이스를 관리 하는 데 사용할 수 있는 두 가지 관리 옵션으로 독립 실행형 도구 또는 Microsoft 끝점 구성 관리자와의 통합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-114">There are two administrative options you can use to manage SEMM and enroll Surface devices – a standalone tool or integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e6578-115">이 문서에서는 Microsoft Surface UEFI 구성자 이라고 하는 모든 독립 실행형 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-115">The SEMM standalone tool, called the Microsoft Surface UEFI Configurator, is described in this article.</span></span> <span data-ttu-id="e6578-116">Microsoft Endpoint Configuration Manager에서 SEMM을 관리 하는 방법에 대 한 자세한 내용은 [Microsoft Endpoint Configuration manager를 사용 하 여 디바이스 관리 (SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-116">For more information about how to manage SEMM with Microsoft Endpoint Configuration Manager, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>


## <span data-ttu-id="e6578-117">Microsoft Surface UEFI 구성자</span><span class="sxs-lookup"><span data-stu-id="e6578-117">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="e6578-118">그림 1에 나와 있는 것 처럼 SEMM의 기본 작업 영역은 Microsoft Surface UEFI 구성자입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-118">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> <span data-ttu-id="e6578-119">Microsoft Surface UEFI 구성자는 Surface 장치에서 SEMM을 등록, 구성 및 등록 해제 하는 데 사용 되는 Windows Installer (.msi) 패키지 또는 WinPE 이미지를 만드는 데 사용 되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-119">Microsoft Surface UEFI Configurator is a tool used to create Windows Installer (.msi) packages or WinPE images used to enroll, configure, and unenroll SEMM on a Surface device.</span></span> <span data-ttu-id="e6578-120">이러한 패키지에는 UEFI에 대 한 설정을 지정 하는 구성 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-120">These packages contain a configuration file where the settings for UEFI are specified.</span></span> <span data-ttu-id="e6578-121">SEMM 패키지에는 또한 펌웨어에 설치 되 고 저장 되며 UEFI 설정이 적용 되기 전에 구성 파일의 서명을 확인 하는 데 사용 되는 인증서가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-121">SEMM packages also contain a certificate, which is installed and stored in firmware and used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!NOTE]
><span data-ttu-id="e6578-122">이제 Surface UEFI 구성자 및 SEMM을 사용 하 여 Surface Dock 2의 포트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-122">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="e6578-123">자세한 내용은 [SEMM의 보안 Surface Dock 2 포트](secure-surface-dock-ports-semm.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-123">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI 구성자](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="e6578-125">그림 1.</span><span class="sxs-lookup"><span data-stu-id="e6578-125">Figure 1.</span></span> <span data-ttu-id="e6578-126">Microsoft Surface UEFI 구성자</span><span class="sxs-lookup"><span data-stu-id="e6578-126">Microsoft Surface UEFI Configurator</span></span>*


<span data-ttu-id="e6578-127">다음 세 가지 모드에서 Microsoft Surface UEFI 구성자 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-127">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

* <span data-ttu-id="e6578-128">[SURFACE UEFI 구성 패키지](#configuration-package)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-128">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="e6578-129">이 모드를 사용 하 여 surface UEFI 구성 패키지를 만들어 surface device를 SEMM에 등록 하 고 등록 된 디바이스에서 UEFI 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-129">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
* <span data-ttu-id="e6578-130">[SURFACE UEFI Reset 패키지](#reset-package)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-130">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="e6578-131">이 모드를 사용 하 여 Surface 디바이스의 등록을 SEMM로 등록 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-131">Use this mode to unenroll a Surface device from SEMM.</span></span>
* <span data-ttu-id="e6578-132">[SURFACE UEFI 복구 요청](#recovery-request)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-132">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="e6578-133">패키지 다시 설정 작업이 실패 하는 경우이 모드를 사용 하 여 복구 요청에 응답 하 여 Surface device를 SEMM에서 등록 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-133">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>


#### <span data-ttu-id="e6578-134">Microsoft Surface UEFI 구성자 다운로드</span><span class="sxs-lookup"><span data-stu-id="e6578-134">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="e6578-135">Microsoft Surface UEFI Configurator를 다운로드 센터의 IT 페이지의 [Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-135">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <span data-ttu-id="e6578-136">구성 패키지</span><span class="sxs-lookup"><span data-stu-id="e6578-136">Configuration package</span></span>

<span data-ttu-id="e6578-137">Surface UEFI 구성 패키지는 Surface 디바이스의 SEMM을 구현 하 고 관리 하는 기본 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-137">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="e6578-138">이러한 패키지에는 그림 2와 같이 Microsoft Surface UEFI 구성자 및 인증서 파일에 패키지를 만드는 동안 지정 된 UEFI 설정의 구성 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-138">These packages contain a configuration file of UEFI settings specified during creation of the package in Microsoft Surface UEFI Configurator and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="e6578-139">SEMM에 등록 되지 않은 Surface 장치에서 처음으로 구성 패키지를 실행 하는 경우 디바이스 펌웨어의 인증서 파일을 프로 비전 하 고이 장치를 SEMM에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-139">When a configuration package is run for the first time on a Surface device that is not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="e6578-140">SEMM에서 디바이스를 등록 하는 경우 인증서 파일을 저장 하기 전에 SEMM 인증서 손도장의 마지막 두 자리를 제공 하 고 등록을 완료 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-140">When enrolling a device in SEMM, you will be prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint before the certificate file is stored and the enrollment can complete.</span></span> <span data-ttu-id="e6578-141">이 확인을 위해서는 등록 시 사용자가 디바이스에 실제로 설치 되어 확인을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-141">This confirmation requires a user be physically present at the device at the time of enrollment to perform the confirmation.</span></span>

![인증서를 사용 하 여 SEMM 구성 패키지 보호](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="e6578-143">그림 2.</span><span class="sxs-lookup"><span data-stu-id="e6578-143">Figure 2.</span></span> <span data-ttu-id="e6578-144">인증서를 사용 하 여 SEMM 구성 패키지 보호</span><span class="sxs-lookup"><span data-stu-id="e6578-144">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="e6578-145">SEMM 인증서에 대 한 요구 사항에 대 한 자세한 내용은이 문서의 [Surface Enterprise 관리 모드 인증서 요구 사항](#surface-enterprise-management-mode-certificate-requirements) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-145">See the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section of this article for more information about the requirements for the SEMM certificate.</span></span>

>[!NOTE]
><span data-ttu-id="e6578-146">Surface UEFI의 **보안**, **장치**, **부팅 구성**또는 **엔터프라이즈 관리** 페이지를 보는 데 필요한 semm의 암호를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-146">You can also specify a UEFI password with SEMM that is required to view the **Security**, **Devices**, **Boot Configuration**, or **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="e6578-147">디바이스가 SEMM에 등록 되 면 구성 파일을 읽고 파일에 지정 된 설정이 UEFI에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-147">After a device is enrolled in SEMM, the configuration file is read and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="e6578-148">SEMM로 등록 된 장치에서 구성 패키지를 실행 하는 경우 구성 파일의 서명이 디바이스 펌웨어에 저장 된 인증서를 기준으로 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-148">When you run a configuration package on a device that is already enrolled in SEMM, the signature of the configuration file is checked against the certificate that is stored in the device firmware.</span></span> <span data-ttu-id="e6578-149">서명이 일치 하지 않으면 장치에 변경 내용이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-149">If the signature does not match, no changes are applied to the device.</span></span>

### <span data-ttu-id="e6578-150">Surface UEFI에서 장치 사용 또는 사용 안 함 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="e6578-150">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="e6578-151">다음 목록에는 SEMM에서 관리할 수 있는 모든 장치가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-151">The following list shows all the available devices you can manage in SEMM:</span></span>

* <span data-ttu-id="e6578-152">도킹 USB 포트</span><span class="sxs-lookup"><span data-stu-id="e6578-152">Docking USB Port</span></span>
* <span data-ttu-id="e6578-153">온보드 오디오</span><span class="sxs-lookup"><span data-stu-id="e6578-153">On-board Audio</span></span>
* <span data-ttu-id="e6578-154">DGPU</span><span class="sxs-lookup"><span data-stu-id="e6578-154">DGPU</span></span>
* <span data-ttu-id="e6578-155">타이핑 커버</span><span class="sxs-lookup"><span data-stu-id="e6578-155">Type Cover</span></span>
* <span data-ttu-id="e6578-156">마이크로 SD 카드</span><span class="sxs-lookup"><span data-stu-id="e6578-156">Micro SD Card</span></span>
* <span data-ttu-id="e6578-157">전면 카메라</span><span class="sxs-lookup"><span data-stu-id="e6578-157">Front Camera</span></span>
* <span data-ttu-id="e6578-158">후면 카메라</span><span class="sxs-lookup"><span data-stu-id="e6578-158">Rear Camera</span></span>
* <span data-ttu-id="e6578-159">적외선 카메라, Windows Hello</span><span class="sxs-lookup"><span data-stu-id="e6578-159">Infrared Camera, for Windows Hello</span></span>
* <span data-ttu-id="e6578-160">블루투스만</span><span class="sxs-lookup"><span data-stu-id="e6578-160">Bluetooth Only</span></span>
* <span data-ttu-id="e6578-161">Wi-Fi 및 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e6578-161">Wi-Fi and Bluetooth</span></span>
* <span data-ttu-id="e6578-162">             LTE           </span><span class="sxs-lookup"><span data-stu-id="e6578-162">LTE</span></span>

 >[!NOTE]
><span data-ttu-id="e6578-163">UEFI 장치 페이지에 표시 되는 기본 제공 디바이스는 장치 또는 회사 환경에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-163">The built-in devices that appear in the UEFI Devices page may vary depending on your device or corporate environment.</span></span> <span data-ttu-id="e6578-164">예를 들어 UEFI 장치 페이지는 Surface Pro X에서 지원 되지 않습니다. LTE는 LTE 장착 장치에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-164">For example, the UEFI Devices page is not supported on Surface Pro X; LTE only appears on LTE-equipped devices.</span></span> 
### <span data-ttu-id="e6578-165">SEMM을 사용 하 여 고급 설정 구성</span><span class="sxs-lookup"><span data-stu-id="e6578-165">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="e6578-166">표 1.</span><span class="sxs-lookup"><span data-stu-id="e6578-166">Table 1.</span></span> <span data-ttu-id="e6578-167">고급 설정</span><span class="sxs-lookup"><span data-stu-id="e6578-167">Advanced settings</span></span>**

| <span data-ttu-id="e6578-168">설정</span><span class="sxs-lookup"><span data-stu-id="e6578-168">Setting</span></span>                            | <span data-ttu-id="e6578-169">설명</span><span class="sxs-lookup"><span data-stu-id="e6578-169">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="e6578-170">PXE 부팅용 IPv6</span><span class="sxs-lookup"><span data-stu-id="e6578-170">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="e6578-171">PXE 부팅에 대 한 IPv6 지원을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-171">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="e6578-172">이 설정을 구성 하지 않으면 PXE 부팅에 대 한 IPv6 지원이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-172">If you do not configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="e6578-173">대체 부팅</span><span class="sxs-lookup"><span data-stu-id="e6578-173">Alternate Boot</span></span>                     | <span data-ttu-id="e6578-174">부팅 중에 볼륨 아래로 단추와 전원 단추를 모두 눌러 USB 또는 이더넷 장치로 직접 부팅 하는 대체 부팅 순서의 사용을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-174">Allows you to manage use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="e6578-175">이 설정을 구성 하지 않으면, 대체 부팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-175">If you do not configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="e6578-176">부팅 순서 잠금</span><span class="sxs-lookup"><span data-stu-id="e6578-176">Boot Order Lock</span></span>                    | <span data-ttu-id="e6578-177">부팅 순서를 잠궈 변경 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-177">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="e6578-178">이 설정을 구성 하지 않으면, 부팅 순서 잠금을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-178">If you do not configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="e6578-179">USB 부팅</span><span class="sxs-lookup"><span data-stu-id="e6578-179">USB Boot</span></span>                           | <span data-ttu-id="e6578-180">USB 장치에 대 한 부팅을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-180">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="e6578-181">이 설정을 구성 하지 않으면, USB Boot를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-181">If you do not configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="e6578-182">네트워크 스택</span><span class="sxs-lookup"><span data-stu-id="e6578-182">Network Stack</span></span>                      | <span data-ttu-id="e6578-183">네트워크 스택 부팅 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-183">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="e6578-184">이 설정을 구성 하지 않으면 네트워크 스택 부팅 설정을 관리 하는 기능이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-184">If you do not configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="e6578-185">자동 전원 켜기</span><span class="sxs-lookup"><span data-stu-id="e6578-185">Auto Power On</span></span>                      | <span data-ttu-id="e6578-186">자동 전원 켜기 부팅 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-186">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="e6578-187">이 설정을 구성 하지 않으면 자동 전원을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-187">If you do not configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="e6578-188">SMT (동시 다중 스레드)</span><span class="sxs-lookup"><span data-stu-id="e6578-188">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="e6578-189">하이퍼스레딩을 사용 하거나 사용 하지 않도록 설정 하는 동시 다중 스레드 (SMT)를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-189">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="e6578-190">이 설정을 구성 하지 않으면 SMT가 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-190">If you do not configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="e6578-191">배터리 한도 사용</span><span class="sxs-lookup"><span data-stu-id="e6578-191">Enable Battery limit</span></span>| <span data-ttu-id="e6578-192">배터리 제한 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-192">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="e6578-193">이 설정을 구성 하지 않으면 배터리 한도가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-193">If you do not configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="e6578-194">보안</span><span class="sxs-lookup"><span data-stu-id="e6578-194">Security</span></span>                           | <span data-ttu-id="e6578-195">Surface UEFI **보안** 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-195">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="e6578-196">이 설정을 구성 하지 않으면 보안 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-196">If you do not configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="e6578-197">장치</span><span class="sxs-lookup"><span data-stu-id="e6578-197">Devices</span></span>                            | <span data-ttu-id="e6578-198">Surface UEFI **장치** 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-198">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="e6578-199">이 설정을 구성 하지 않으면 장치 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-199">If you do not configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="e6578-200">Boot</span><span class="sxs-lookup"><span data-stu-id="e6578-200">Boot</span></span>                               | <span data-ttu-id="e6578-201">Surface UEFI **부팅** 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-201">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="e6578-202">이 설정을 구성 하지 않으면 부팅 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-202">If you do not configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="e6578-203">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6578-203">DateTime</span></span>                           | <span data-ttu-id="e6578-204">Surface UEFI **날짜/시간** 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-204">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="e6578-205">이 설정을 구성 하지 않으면 날짜/시간 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-205">If you do not configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="e6578-206">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="e6578-206">EnableOSMigration</span></span>                          | <span data-ttu-id="e6578-207">Windows 10 Team에서 Surface Hub 2를 Windows 10 Pro 또는 Enterprise로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-207">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="e6578-208">이 설정을 구성 하지 않으면 Surface Hub 2 장치는 Windows 10 Team OS만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-208">If you do not configure this setting, Surface Hub 2 devices can only run Windows 10 Team OS.</span></span>   <span data-ttu-id="e6578-209">참고: Surface Hub 2에서는 Windows 10 Team 및 Windows 10 Pro/Enterprise 간 듀얼 부팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-209">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise  is not available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="e6578-210">SEMM 구성 패키지를 만들면 그림 3과 같이 **성공적** 페이지에 두 개의 문자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-210">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![인증서 지문 표시](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="e6578-212">그림 3.</span><span class="sxs-lookup"><span data-stu-id="e6578-212">Figure 3.</span></span> <span data-ttu-id="e6578-213">성공 페이지에서 인증서 손도장의 마지막 두 문자 표시</span><span class="sxs-lookup"><span data-stu-id="e6578-213">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="e6578-214">이러한 문자는 인증서 손도장의 마지막 두 자 이며, 적어 서 기록 하거나 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-214">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="e6578-215">그림 4와 같이 Surface 장치에서 등록을 확인 하는 데 문자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-215">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![등록 확인 (SEMM)](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="e6578-217">그림 4.</span><span class="sxs-lookup"><span data-stu-id="e6578-217">Figure 4.</span></span> <span data-ttu-id="e6578-218">Semm 인증서 지문이 있는 SEMM의 등록 확인</span><span class="sxs-lookup"><span data-stu-id="e6578-218">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="e6578-219">인증서 파일 (.pfx)에 대 한 액세스 권한이 있는 관리자는 CertMgr에서 .pfx 파일을 열어 언제 든 지 지문을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-219">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="e6578-220">CertMgr를 사용 하 여 지문을 보려면 다음 프로세스를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-220">To view the thumbprint with CertMgr, follow this process:</span></span>
>1. <span data-ttu-id="e6578-221">.Pfx 파일을 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-221">Right-click the .pfx file, and then click **Open**.</span></span>
>2. <span data-ttu-id="e6578-222">탐색 창에서 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-222">Expand the folder in the navigation pane.</span></span>
>3. <span data-ttu-id="e6578-223">**인증서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-223">Click **Certificates**.</span></span>
>4. <span data-ttu-id="e6578-224">기본 창에서 인증서를 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-224">Right-click your certificate in the main pane, and then click **Open**.</span></span>
>5. <span data-ttu-id="e6578-225">**세부 정보** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-225">Click the **Details** tab.</span></span>
>6. <span data-ttu-id="e6578-226">**표시** 드롭다운 메뉴에서 **모두** 또는 **속성만** 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-226">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
>7. <span data-ttu-id="e6578-227">필드 **지문을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-227">Select the field **Thumbprint**.</span></span>

<span data-ttu-id="e6578-228">Surface 장치를 SEMM에 등록 하거나 구성 패키지에서 UEFI 구성을 적용 하려면 의도 된 Surface 장치에서 관리자 권한으로 .msi 파일을 실행 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-228">To enroll a Surface device in SEMM or to apply the UEFI configuration from a configuration package, all you need to do is run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="e6578-229">[Microsoft 끝점 구성 관리자](https://technet.microsoft.com/library/mt346023) 또는 [microsoft 배포 툴킷](https://technet.microsoft.com/windows/dn475741)등의 운영 체제 배포 기술 또는 응용 프로그램 배포를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-229">You can use application deployment or operating system deployment technologies such as [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="e6578-230">H m e m e에 디바이스를 등록 하는 경우 디바이스의 등록을 확인 하려면 실제로 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-230">When you enroll a device in SEMM you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="e6578-231">SEMM에 이미 등록 된 장치에 구성을 적용 하는 경우 사용자 조작이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-231">User interaction is not required when you apply a configuration to devices that are already enrolled in SEMM.</span></span>

<span data-ttu-id="e6578-232">SEMM에서 Surface device를 등록 하거나 SEMM을 사용 하 여 Surface UEFI 구성을 적용 하는 방법에 대 한 단계별 연습을 보려면 [surface 장치 등록 및 구성 (SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-232">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <span data-ttu-id="e6578-233">패키지 다시 설정</span><span class="sxs-lookup"><span data-stu-id="e6578-233">Reset package</span></span>

<span data-ttu-id="e6578-234">Surface UEFI reset 패키지는 한 작업을 수행 하는 데 사용 되며, Surface device는 SEMM에서 등록을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-234">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="e6578-235">패키지 초기화에는 디바이스의 펌웨어에서 SEMM 인증서를 제거 하 고 UEFI 설정을 출고시 기본값으로 다시 설정 하는 서명 된 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-235">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to factory default.</span></span> <span data-ttu-id="e6578-236">Surface UEFI 구성 패키지와 마찬가지로 reset 패키지는 Surface device에서 프로 비전 되는 동일한 SEMM 인증서로 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-236">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that is provisioned on the Surface device.</span></span> <span data-ttu-id="e6578-237">SEMM reset 패키지를 만들 때, 다시 설정 하려는 Surface 디바이스의 일련 번호를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-237">When you create a SEMM reset package, you are required to supply the serial number of the Surface device you intend to reset.</span></span> <span data-ttu-id="e6578-238">SEMM 재설정 패키지는 유니버설 하지 않으며 한 장치에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-238">SEMM reset packages are not universal and are specific to one device.</span></span>

### <span data-ttu-id="e6578-239">복구 요청</span><span class="sxs-lookup"><span data-stu-id="e6578-239">Recovery request</span></span>

<span data-ttu-id="e6578-240">일부 시나리오에서는 Surface UEFI reset 패키지를 사용 하는 것이 불가능할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-240">In some scenarios, it may be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="e6578-241">(예를 들어 Surface 장치에서 Windows를 사용할 수 없게 되는 경우) 이러한 시나리오에서는 surface UEFI (그림 5에 표시 됨)의 **엔터프라이즈 관리** 페이지를 통해 복구 요청 작업으로 surface 디바이스의 등록을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-241">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

![SEMM 복구 요청 시작](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="e6578-243">그림 5.</span><span class="sxs-lookup"><span data-stu-id="e6578-243">Figure 5.</span></span> <span data-ttu-id="e6578-244">엔터프라이즈 관리 페이지에서 SEMM 복구 요청 시작</span><span class="sxs-lookup"><span data-stu-id="e6578-244">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="e6578-245">**엔터프라이즈 관리** 페이지의 프로세스를 사용 하 여 Surface DEVICE에서 semm을 다시 설정 하는 경우 초기화 요청이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-245">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you are provided with a Reset Request.</span></span> <span data-ttu-id="e6578-246">이 재설정 요청은 USB 드라이브에 파일로 저장 하거나, 텍스트로 복사 하거나, 모바일 장치를 사용 하 여 쉽게 전자 메일로 또는 messaged QR 코드로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-246">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="e6578-247">Microsoft Surface UEFI 구성자 초기화 요청 옵션을 사용 하 여 초기화 요청 파일을 로드 하거나 재설정 요청 텍스트 또는 QR 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-247">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="e6578-248">Microsoft Surface UEFI 구성자는 Surface device에 입력할 수 있는 확인 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-248">Microsoft Surface UEFI Configurator will generate a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="e6578-249">Surface 장치에 코드를 입력 하 고 **다시 시작**을 클릭 하면 디바이스는 semm에서 unenrolled 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-249">If you enter the code on the Surface device and click **Restart**, the device will be unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="e6578-250">재설정 요청은 생성 된 후 두 시간 후에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-250">A Reset Request expires two hours after it is created.</span></span>

<span data-ttu-id="e6578-251">Surface 디바이스의 등록을 해제 하는 방법에 대 한 단계별 연습을 보려면 semm에서 등록 해제 [화면 장치](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-251">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="e6578-252">Surface 엔터프라이즈 관리 모드 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6578-252">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="e6578-253">Microsoft Surface UEFI 구성자에 SEMM을 사용 하면 UEFI 설정을 적용 하기 전에 구성 파일의 서명을 확인 하는 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-253">Using SEMM with Microsoft Surface UEFI Configurator requires a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="e6578-254">이 인증서는 디바이스를 SEMM에 등록 한 후 승인 된 인증서로 만든 패키지만 UEFI의 설정을 수정 하는 데 사용할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-254">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span>

>[!NOTE]
><span data-ttu-id="e6578-255">등록 된 Surface 디바이스에서 SEMM 또는 Surface UEFI 설정에 대 한 수정 작업을 수행 하려면 SEMM 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-255">The SEMM certificate is required to perform any modification to SEMM or Surface UEFI settings on enrolled Surface devices.</span></span> <span data-ttu-id="e6578-256">SEMM 인증서가 손상 되거나 손실 된 경우 SEMM을 제거 하거나 재설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-256">If the SEMM certificate is corrupted or lost, SEMM cannot be removed or reset.</span></span> <span data-ttu-id="e6578-257">적절 한 백업 및 복구 솔루션을 사용 하 여 SEMM 인증서를 관리 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-257">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery.</span></span>

<span data-ttu-id="e6578-258">Microsoft Surface UEFI 구성자 도구를 사용 하 여 만든 패키지는 인증서를 사용 하 여 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-258">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="e6578-259">이 인증서는 디바이스를 SEMM에 등록 한 후 승인 된 인증서로 만든 패키지만 UEFI의 설정을 수정 하는 데 사용할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-259">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <span data-ttu-id="e6578-260">권장 되는 인증서 설정</span><span class="sxs-lookup"><span data-stu-id="e6578-260">Recommended certificate settings</span></span>
<span data-ttu-id="e6578-261">SEMM 인증서에 대해 다음 설정을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-261">The following settings are recommended for the SEMM certificate:</span></span>

* <span data-ttu-id="e6578-262">**키 알고리즘** – RSA</span><span class="sxs-lookup"><span data-stu-id="e6578-262">**Key Algorithm** – RSA</span></span> 
* <span data-ttu-id="e6578-263">**키 길이** – 2048</span><span class="sxs-lookup"><span data-stu-id="e6578-263">**Key Length** – 2048</span></span>
* <span data-ttu-id="e6578-264">**해시 알고리즘** – sha-1-256</span><span class="sxs-lookup"><span data-stu-id="e6578-264">**Hash Algorithm** – SHA-256</span></span>
* <span data-ttu-id="e6578-265">**유형** – SSL 서버 인증</span><span class="sxs-lookup"><span data-stu-id="e6578-265">**Type** – SSL Server Authentication</span></span>
* <span data-ttu-id="e6578-266">**키 사용** – 디지털 서명, 키 암호화</span><span class="sxs-lookup"><span data-stu-id="e6578-266">**Key Usage** – Digital signature, Key Encipherment</span></span>
* <span data-ttu-id="e6578-267">**공급자** – Microsoft 향상 된 RSA 및 AES 암호화 공급자</span><span class="sxs-lookup"><span data-stu-id="e6578-267">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
* <span data-ttu-id="e6578-268">**만료 날짜** – 인증서 생성 시 15 개월</span><span class="sxs-lookup"><span data-stu-id="e6578-268">**Expiration Date** – 15 Months from certificate creation</span></span>
* <span data-ttu-id="e6578-269">**키 내보내기 정책** – 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-269">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="e6578-270">또한 인증서 해지를 활성화 하는 중간 CA (인증 기관)가 SEMM 인 2 계층 PKI (공개 키 인프라) 아키텍처에서 SEMM 인증서를 인증 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-270">It is also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="e6578-271">2 계층 PKI 구성에 대 한 자세한 내용은 [테스트 랩 가이드: PKI 계층 Two-Tier AD CS 배포](https://technet.microsoft.com/library/hh831348)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-271">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <span data-ttu-id="e6578-272">자체 서명 된 인증서</span><span class="sxs-lookup"><span data-stu-id="e6578-272">Self-signed certificate</span></span> 
<span data-ttu-id="e6578-273">다음 예제 PowerShell 스크립트를 사용 하 여 개념 증명 시나리오에서 사용할 자체 서명 된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-273">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="e6578-274">이 스크립트를 사용 하려면 다음 텍스트를 메모장에 복사 하 고 파일을 PowerShell 스크립트 (. ps1)로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-274">To use this script, copy the following text into Notepad and save the file as a PowerShell script (.ps1).</span></span> <span data-ttu-id="e6578-275">참고:이 스크립트는 암호를 사용 하 여 인증서를 만듭니다 `12345678` . 이 스크립트에서 생성 된 인증서는 프로덕션 환경에는 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-275">Note: This script creates a certificate with a password of `12345678`.The certificate generated by this script is not recommended for production environments.</span></span>
  
   ```
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
><span data-ttu-id="e6578-276">SEMM 및 Microsoft Surface UEFI 구성자와 함께 사용 하려면 인증서를 개인 키와 암호 보호를 사용 하 여 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-276">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="e6578-277">Microsoft Surface UEFI 구성자는 필요할 때 SEMM 인증서 파일 (.pfx) 및 인증서 암호를 선택 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-277">Microsoft Surface UEFI Configurator will prompt you to select the SEMM certificate file (.pfx) and certificate password when it is required.</span></span>

1.  <span data-ttu-id="e6578-278">C: 드라이브에서 스크립트를 저장할 폴더를 만듭니다. 예를 들어 C:\SEMM.</span><span class="sxs-lookup"><span data-stu-id="e6578-278">Create a folder on your C: drive where you will save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="e6578-279">예제 스크립트를 메모장 이나 해당 텍스트 편집기에 복사 하 고 파일을 PowerShell 스크립트 (. ps1)로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-279">Copy the example script into Notepad or equivalent text editor and save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="e6578-280">관리자 자격 증명으로 PC에 로그인 하 고 관리자 권한 PowerShell 세션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-280">Sign into your PC with administrator credentials and open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="e6578-281">스크립트 실행을 허용 하도록 사용 권한이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-281">Ensure your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="e6578-282">기본적으로 실행 정책을 수정 하지 않으면 스크립트가 실행 되지 않도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-282">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="e6578-283">자세히 알아보려면 [실행 정책 정보](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-283">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="e6578-284">명령 프롬프트에서 스크립트의 전체 경로를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-284">At the command prompt, enter the full path of the script and then press Enter.</span></span> <span data-ttu-id="e6578-285">이 스크립트는 TempOwner 이라는 데모 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-285">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="e6578-286">또는 PowerShell을 사용 하 여 고유한 자체 서명 된 인증서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-286">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="e6578-287">자세한 내용은 PowerShell 설명서: [New-new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6578-287">For more information, see the following PowerShell documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>




>[!NOTE]
><span data-ttu-id="e6578-288">PKI 인프라에서 오프 라인 루트를 사용 하는 조직의 경우 Microsoft Surface UEFI 구성자을 루트 CA에 연결 된 환경에서 실행 해야 SEMM 인증서를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-288">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="e6578-289">Microsoft Surface UEFI 구성자에서 생성 된 패키지는 파일로 전송 될 수 있으므로 USB 스틱 같은 이동식 저장소를 사용 하 여 오프 라인 네트워크 환경 외부에서 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-289">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files and therefore can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <span data-ttu-id="e6578-290">인증서 관리 FAQ</span><span class="sxs-lookup"><span data-stu-id="e6578-290">Managing certificates FAQ</span></span>

<span data-ttu-id="e6578-291">권장 되는 *최소* 길이는 15 개월입니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-291">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="e6578-292">15 개월 이내로 만료 되는 인증서를 사용 하거나 15 개월 넘게 만료 되는 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-292">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="e6578-293">인증서가 만료 되 면 자동으로 갱신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-293">When a certificate expires, it does not automatically renew.</span></span> 


**<span data-ttu-id="e6578-294">만료 된 인증서가 \ m m-등록 디바이스의 기능에 영향을 줍니까?</span><span class="sxs-lookup"><span data-stu-id="e6578-294">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="e6578-295">아니요, 인증서는이를 SEMM의 관리 관리 작업에만 영향을 주는 반면, 만료 되는 장치 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-295">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>


**<span data-ttu-id="e6578-296">SEMM 패키지와 인증서를 보유 하 고 있는 모든 컴퓨터에서이를 업데이트 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e6578-296">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**

<span data-ttu-id="e6578-297">SEMM 재설정 또는 복구가 작동 하도록 하려면 인증서가 유효 하 고 만료 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-297">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="e6578-298">주문 하는 각 표면에 대해 패키지를 대량으로 다시 설정할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="e6578-298">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="e6578-299">환경에서 모든 컴퓨터를 다시 설정 하는 빌드를 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e6578-299">Can one be built that resets all machines in our environment?</span></span>**

<span data-ttu-id="e6578-300">특정 디바이스 유형에 대 한 구성 패키지를 만드는 PowerShell 샘플을 사용 하 여 일련 번호를 독립적으로 설정 패키지를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-300">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that is serial-number independent.</span></span> <span data-ttu-id="e6578-301">인증서가 여전히 유효한 경우 PowerShell을 사용 하 여 reset 패키지를 만들어 SEMM을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-301">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <span data-ttu-id="e6578-302">버전 기록</span><span class="sxs-lookup"><span data-stu-id="e6578-302">Version History</span></span>


### <span data-ttu-id="e6578-303">버전 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="e6578-303">Version 2.78.139.0</span></span>

<span data-ttu-id="e6578-304">이 SEMM 버전에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-304">This version of SEMM includes:</span></span>

- <span data-ttu-id="e6578-305">Surface 랩톱 이동 및 Surface Pro X에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-305">Support for Surface Laptop Go and Surface Pro X</span></span>
- <span data-ttu-id="e6578-306">새 버전 출시에 대 한 알림</span><span class="sxs-lookup"><span data-stu-id="e6578-306">Notifications for new version release</span></span>
- <span data-ttu-id="e6578-307">소유권을 변경 하기 위해 사용자 지정 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-307">Ability to create custom packages to change ownership</span></span>
- <span data-ttu-id="e6578-308">버그 수정</span><span class="sxs-lookup"><span data-stu-id="e6578-308">Bug fixes</span></span>




### <span data-ttu-id="e6578-309">버전 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="e6578-309">Version 2.73.136.0</span></span>

<span data-ttu-id="e6578-310">이 SEMM 버전에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-310">This version of SEMM includes:</span></span>

- <span data-ttu-id="e6578-311">이제 Surface Hub2S에서 오디오를 사용 하지 않도록 설정할 수 있음 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="e6578-311">Audio can now be disabled on Surface Hub2S using SEMM</span></span>
- <span data-ttu-id="e6578-312">Dock 2 용 Surface Pro X에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-312">Support to Surface Pro X for Dock 2</span></span>
- <span data-ttu-id="e6578-313">2에 고정 연결 작업에 대 한 UEFI 관리자 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-313">Support to UEFI Manager for Dock 2 related operations</span></span>
- <span data-ttu-id="e6578-314">Surface Go 패키지 버그 수정 다시 설정</span><span class="sxs-lookup"><span data-stu-id="e6578-314">Surface Go reset package bug fix</span></span>
- <span data-ttu-id="e6578-315">Windows 10 Team OS에서 Windows 10 Pro 또는 Enterprise로 Surface Hub 2 장치를 마이그레이션하는 데 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-315">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <span data-ttu-id="e6578-316">버전 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="e6578-316">Version 2.71.139.0</span></span>

<span data-ttu-id="e6578-317">이 SEMM에는 surface Book 3, Surface 랩톱 3 및 Surface Pro 7에 대 한 Surface Dock 2 관리 기능에 대 한 지원이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-317">This version of SEMM adds support for Surface Dock 2 management features  for Surface Book 3, Surface Laptop 3, and Surface Pro 7 including:</span></span>

- <span data-ttu-id="e6578-318">오디오 사용 (잠금/잠금 해제), 이더넷 및 USB 포트</span><span class="sxs-lookup"><span data-stu-id="e6578-318">Enabling audio (locking/unlocking), Ethernet and USB ports</span></span>
- <span data-ttu-id="e6578-319">인증 된 호스트나 인증 되지 않은 호스트 모두에 대해 dock 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-319">Ability to create dock packages for both authenticated and unauthenticated hosts</span></span>

### <span data-ttu-id="e6578-320">버전 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="e6578-320">Version 2.70.130.0</span></span>

<span data-ttu-id="e6578-321">이 SEMM 버전에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-321">This version of SEMM includes:</span></span>

- <span data-ttu-id="e6578-322">Surface Go 2 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-322">Support for Surface Go 2</span></span>
- <span data-ttu-id="e6578-323">Surface Book 3에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-323">Support for Surface Book 3</span></span>
- <span data-ttu-id="e6578-324">버그 수정</span><span class="sxs-lookup"><span data-stu-id="e6578-324">Bug fixes</span></span>


### <span data-ttu-id="e6578-325">버전 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="e6578-325">Version 2.59.139.0</span></span>

* <span data-ttu-id="e6578-326">인텔 프로세서를 사용 하는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3 13.5 "및 15" 모델에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="e6578-326">Support for Surface Pro 7, Surface Pro X,  and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span> <span data-ttu-id="e6578-327">참고: Surface 랩탑 3 15 "AMD 프로세서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6578-327">Note:  Surface Laptop 3 15" AMD processor is not supported.</span></span>

- <span data-ttu-id="e6578-328">절전 모드 종료 기능 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-328">Support for Wake on Power feature</span></span>

### <span data-ttu-id="e6578-329">버전 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="e6578-329">Version 2.54.139.0</span></span>
* <span data-ttu-id="e6578-330">Surface Hub 2S 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-330">Support to Surface Hub 2S</span></span>
* <span data-ttu-id="e6578-331">버그 수정</span><span class="sxs-lookup"><span data-stu-id="e6578-331">Bug fixes</span></span>

### <span data-ttu-id="e6578-332">버전 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="e6578-332">Version 2.43.136.0</span></span>
* <span data-ttu-id="e6578-333">Simulatenous multithreating 사용/사용 안 함 지원</span><span class="sxs-lookup"><span data-stu-id="e6578-333">Support to enable/disable simulatenous multithreating</span></span> 
* <span data-ttu-id="e6578-334">일부 장치에 대 한 WiFi 및 블루투스 옵션 구분</span><span class="sxs-lookup"><span data-stu-id="e6578-334">Separate options for WiFi and Bluetooth for some devices</span></span> 
* <span data-ttu-id="e6578-335">Surface Studio에 대 한 배터리 제한 제거 됨</span><span class="sxs-lookup"><span data-stu-id="e6578-335">Battery Limit removed for Surface Studio</span></span> 

### <span data-ttu-id="e6578-336">버전 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="e6578-336">Version 2.26.136.0</span></span>
* <span data-ttu-id="e6578-337">Surface Studio 2에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-337">Add support to Surface Studio 2</span></span>
* <span data-ttu-id="e6578-338">배터리 제한 기능</span><span class="sxs-lookup"><span data-stu-id="e6578-338">Battery Limit feature</span></span>

### <span data-ttu-id="e6578-339">버전 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="e6578-339">Version 2.21.136.0</span></span>
* <span data-ttu-id="e6578-340">Surface Pro 6에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-340">Add support to Surface Pro 6</span></span>
* <span data-ttu-id="e6578-341">Surface 노트북 2에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-341">Add support to Surface Laptop 2</span></span>

### <span data-ttu-id="e6578-342">버전 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="e6578-342">Version 2.14.136.0</span></span>
* <span data-ttu-id="e6578-343">Surface Go에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-343">Add support to Surface Go</span></span>

### <span data-ttu-id="e6578-344">버전 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="e6578-344">Version 2.9.136.0</span></span>
* <span data-ttu-id="e6578-345">Surface Book 2에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-345">Add support to Surface Book 2</span></span>
* <span data-ttu-id="e6578-346">Surface Pro LTE에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-346">Add support to Surface Pro LTE</span></span>
* <span data-ttu-id="e6578-347">접근성 개선</span><span class="sxs-lookup"><span data-stu-id="e6578-347">Accessibility improvements</span></span>

### <span data-ttu-id="e6578-348">버전 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="e6578-348">Version 1.0.74.0</span></span>
* <span data-ttu-id="e6578-349">Surface 노트북에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-349">Add support to Surface Laptop</span></span>
* <span data-ttu-id="e6578-350">Surface Pro에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e6578-350">Add support to Surface Pro</span></span>
* <span data-ttu-id="e6578-351">버그 수정 및 일반적인 개선</span><span class="sxs-lookup"><span data-stu-id="e6578-351">Bug fixes and general improvement</span></span>

## <span data-ttu-id="e6578-352">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e6578-352">Related topics</span></span>

- [<span data-ttu-id="e6578-353">SEMM을 사용하여 Surface 장치 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="e6578-353">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="e6578-354">SEMM에서 Surface 디바이스 등록 취소</span><span class="sxs-lookup"><span data-stu-id="e6578-354">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="e6578-355">Secure Surface Dock 2 포트(SEMM 포함)</span><span class="sxs-lookup"><span data-stu-id="e6578-355">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)
