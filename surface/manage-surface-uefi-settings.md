---
title: Surface UEFI 설정 관리
description: Surface UEFI 설정을 사용하여 디바이스나 구성 요소를 사용하거나 사용하지 않도록 설정하고, 보안 설정을 구성하고, Surface 디바이스 부팅 설정을 조정합니다.
keywords: 펌웨어, 보안, 기능, 구성, 하드웨어
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/15/2021
ms.openlocfilehash: d8d47db3bd6f69783670b285a797337373e02d72
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271432"
---
# <span data-ttu-id="c49fb-104">Surface UEFI 설정 관리</span><span class="sxs-lookup"><span data-stu-id="c49fb-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="c49fb-105">모든 현재 및 미래의 Surface 디바이스는 Microsoft에서 이러한 장치를 위해 특별히 설계된 고유한 UEFI(Unified Extensible Firmware Interface)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="c49fb-106">Surface UEFI 설정은 기본 제공 장치 및 구성 요소를 활성화 또는 비활성화하고, UEFI 설정이 변경되지 않도록 보호하고, Surface 디바이스 부팅 설정을 조정하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="c49fb-107">지원되는 제품</span><span class="sxs-lookup"><span data-stu-id="c49fb-107">Supported products</span></span>

<span data-ttu-id="c49fb-108">UEFI 관리는 다음에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="c49fb-109">Surface Pro 4, Surface Pro(5세대), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="c49fb-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="c49fb-110">Surface 노트북(1세대), Surface 노트북 2, Surface 노트북 3, Surface 노트북 이동</span><span class="sxs-lookup"><span data-stu-id="c49fb-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="c49fb-111">Surface Studio(1세대), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="c49fb-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="c49fb-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="c49fb-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="c49fb-113">Surface Go, Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="c49fb-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="c49fb-114">클라우드 기반 관리 지원</span><span class="sxs-lookup"><span data-stu-id="c49fb-114">Support for cloud-based management</span></span>

<span data-ttu-id="c49fb-115">Microsoft Intune에 기본 제공되는 DFCI(장치 펌웨어 구성 인터페이스) 프로필을 사용하여(공개 미리 보기에서 사용 가능) Surface UEFI 관리는 최신 관리 스택을 UEFI 하드웨어 수준으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="c49fb-116">DFCI는 제로 터치 프로비전을 지원하고, BIOS 암호를 제거하고, 부팅 옵션 및 기본 제공 주변 장치를 비롯한 보안 설정을 제어하며, 향후 고급 보안 시나리오를 위한 초안을 마련합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="c49fb-117">DFCI는 현재 Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 및 Surface Pro X에 사용할 수 있습니다.  자세한 내용은 Surface [UEFI 설정의 Intune 관리를 참조하세요.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="c49fb-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="c49fb-118">Surface UEFI 메뉴 열기</span><span class="sxs-lookup"><span data-stu-id="c49fb-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="c49fb-119">시스템 시작 중에 UEFI 설정을 조정하려면</span><span class="sxs-lookup"><span data-stu-id="c49fb-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="c49fb-120">Surface를 종료하고 꺼지기 위해 10초 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="c49fb-121">볼륨 업 단추를 **누르고** 동시에 전원 단추를 **누르고 해제합니다.**</span><span class="sxs-lookup"><span data-stu-id="c49fb-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="c49fb-122">화면에 Microsoft 또는 Surface 로고가 표시될 때 \*\*\*\* UEFI 화면이 나타날 때까지 볼륨 업 단추를 계속 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="c49fb-123">UEFI PC 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="c49fb-123">UEFI PC information page</span></span>

<span data-ttu-id="c49fb-124">PC 정보 페이지에는 Surface 디바이스에 대한 자세한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="c49fb-125">**Model** – Surface Book 2 또는 Surface Pro 7과 같이 Surface 디바이스의 모델이 여기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="c49fb-126">프로세서, 디스크 크기, 메모리 크기와 같은 정확한 디바이스 구성은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="c49fb-127">**UUID** – 이 Universally Unique Identifier 번호는 디바이스별로 고유하며, 배포 또는 관리하는 동안 디바이스를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="c49fb-128">**일련 번호** - 이 번호는 자산 태깅 및 지원 시나리오에서 이 특정 Surface 디바이스를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="c49fb-129">**자산 태그** – 자산 태그는 [자산 태그 도구](https://docs.microsoft.com/surface/assettag)를 사용하여 Surface 디바이스에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="c49fb-130">Surface 디바이스의 펌웨어에 대한 자세한 정보도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="c49fb-131">Surface 디바이스에는 각각 다른 버전의 펌웨어를 실행하는 몇 가지 내부 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="c49fb-132">다음 디바이스 각각의 펌웨어 버전은 **PC 정보** 페이지에 표시됩니다(그림 1 참조).</span><span class="sxs-lookup"><span data-stu-id="c49fb-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="c49fb-133">시스템 UEFI</span><span class="sxs-lookup"><span data-stu-id="c49fb-133">System UEFI</span></span> 

- <span data-ttu-id="c49fb-134">SAM 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="c49fb-134">SAM Controller</span></span> 

- <span data-ttu-id="c49fb-135">Intel 관리 엔진</span><span class="sxs-lookup"><span data-stu-id="c49fb-135">Intel Management Engine</span></span> 

- <span data-ttu-id="c49fb-136">시스템 포함 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="c49fb-136">System Embedded Controller</span></span> 

- <span data-ttu-id="c49fb-137">터치 펌웨어</span><span class="sxs-lookup"><span data-stu-id="c49fb-137">Touch Firmware</span></span> 

![시스템 정보 및 펌웨어 버전 정보](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="c49fb-139">그림 1.</span><span class="sxs-lookup"><span data-stu-id="c49fb-139">Figure 1.</span></span> <span data-ttu-id="c49fb-140">시스템 정보 및 펌웨어 버전 정보</span><span class="sxs-lookup"><span data-stu-id="c49fb-140">System information and firmware version information</span></span>*

<span data-ttu-id="c49fb-141">Surface 디바이스의 최신 펌웨어 버전에 대한 최신 정보는 디바이스의 [Surface 업데이트 기록](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="c49fb-142">UEFI 보안 페이지</span><span class="sxs-lookup"><span data-stu-id="c49fb-142">UEFI Security page</span></span> 

![Surface UEFI 보안 설정 구성](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="c49fb-144">그림 2.</span><span class="sxs-lookup"><span data-stu-id="c49fb-144">Figure 2.</span></span> <span data-ttu-id="c49fb-145">Surface UEFI 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c49fb-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="c49fb-146">보안 페이지에서는 암호를 설정하여 UEFI 설정을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="c49fb-147">Surface 디바이스를 UEFI로 부팅할 때 이 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="c49fb-148">그림 3과 같이 암호에는 다음 문자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="c49fb-149">대문자: A-Z</span><span class="sxs-lookup"><span data-stu-id="c49fb-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="c49fb-150">소문자: a-z</span><span class="sxs-lookup"><span data-stu-id="c49fb-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="c49fb-151">숫자: 1-0</span><span class="sxs-lookup"><span data-stu-id="c49fb-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="c49fb-152">특수 문자: !@#$%^&\*()?<>{} []-_=+|.,;:''"</span><span class="sxs-lookup"><span data-stu-id="c49fb-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="c49fb-153">암호는 6자 이상이어야 하며 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Surface UEFI 설정 보호를 위해 암호 추가](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="c49fb-155">그림 3.</span><span class="sxs-lookup"><span data-stu-id="c49fb-155">Figure 3.</span></span> <span data-ttu-id="c49fb-156">Surface UEFI 설정 보호를 위해 암호 추가</span><span class="sxs-lookup"><span data-stu-id="c49fb-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="c49fb-157">보안 페이지에서 Surface 디바이스에 대한 보안 부팅 구성을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="c49fb-158">보안 부팅 기술은 무단 부팅 코드가 Surface 디바이스에서 부팅되는 문제를 방지하여 bootkit 및 루트킷 형식의 맬웨어 감염으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="c49fb-159">Surface 디바이스에서 타사 운영 체제 또는 부팅 가능한 미디어를 허용하기 위해 보안 부팅을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="c49fb-160">그림 4와 같이 타사 인증서에서 작동하도록 보안 부팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="c49fb-161">TechNet 라이브러리에서 [보안 부팅](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c49fb-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![보안 부팅 구성](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="c49fb-163">그림 4.</span><span class="sxs-lookup"><span data-stu-id="c49fb-163">Figure 4.</span></span> <span data-ttu-id="c49fb-164">보안 부팅 구성</span><span class="sxs-lookup"><span data-stu-id="c49fb-164">Configure Secure Boot</span></span>*

<span data-ttu-id="c49fb-165">장치에 따라 TPM이 활성화 또는 비활성화되어 있는지 여부도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="c49fb-166">**TPM** 사용 설정이 없는 경우 그림 5와 같이 Windows에서 tpm.msc를 열고 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="c49fb-167">TPM은 BitLocker로 디바이스 데이터에 대한 암호화를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="c49fb-168">자세한 내용은 [BitLocker 개요를 참조하세요.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)</span><span class="sxs-lookup"><span data-stu-id="c49fb-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM 콘솔](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="c49fb-170">그림 5.</span><span class="sxs-lookup"><span data-stu-id="c49fb-170">Figure 5.</span></span> <span data-ttu-id="c49fb-171">TPM 콘솔</span><span class="sxs-lookup"><span data-stu-id="c49fb-171">TPM console</span></span>*


## <span data-ttu-id="c49fb-172">UEFI 메뉴: 장치</span><span class="sxs-lookup"><span data-stu-id="c49fb-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="c49fb-173">장치 페이지에서는 다음을 비롯한 특정 장치 및 구성 요소를 활성화 또는 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="c49fb-174">도킹 및 USB 포트</span><span class="sxs-lookup"><span data-stu-id="c49fb-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="c49fb-175">MicroSD 또는 SD 카드 슬롯</span><span class="sxs-lookup"><span data-stu-id="c49fb-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="c49fb-176">후면 카메라</span><span class="sxs-lookup"><span data-stu-id="c49fb-176">Rear Camera</span></span> 

- <span data-ttu-id="c49fb-177">전면 카메라</span><span class="sxs-lookup"><span data-stu-id="c49fb-177">Front Camera</span></span> 

- <span data-ttu-id="c49fb-178">IR(적외선) 카메라</span><span class="sxs-lookup"><span data-stu-id="c49fb-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="c49fb-179">Wi-Fi 및 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="c49fb-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="c49fb-180">온보드 오디오(스피커 및 마이크)</span><span class="sxs-lookup"><span data-stu-id="c49fb-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="c49fb-181">그림 6과 같이 각 디바이스에는 설정(사용) 또는 \*\*\*\* 해제(비활성화) 위치로 이동할 수 있는 슬라이더 단추가 표시됩니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c49fb-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![특정 디바이스를 사용하거나 사용하지 않도록 설정](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="c49fb-183">그림 6.</span><span class="sxs-lookup"><span data-stu-id="c49fb-183">Figure 6.</span></span> <span data-ttu-id="c49fb-184">특정 디바이스를 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="c49fb-184">Enable and disable specific devices</span></span>*

## <span data-ttu-id="c49fb-185">UEFI 메뉴: 부팅 구성</span><span class="sxs-lookup"><span data-stu-id="c49fb-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="c49fb-186">부팅 구성 페이지에서는 부팅 디바이스의 순서를 변경하고 다음 디바이스의 부팅을 활성화 또는 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="c49fb-187">Windows 부팅 관리자</span><span class="sxs-lookup"><span data-stu-id="c49fb-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="c49fb-188">USB 저장소</span><span class="sxs-lookup"><span data-stu-id="c49fb-188">USB Storage</span></span> 

- <span data-ttu-id="c49fb-189">PXE 네트워크</span><span class="sxs-lookup"><span data-stu-id="c49fb-189">PXE Network</span></span> 

- <span data-ttu-id="c49fb-190">내부 저장소</span><span class="sxs-lookup"><span data-stu-id="c49fb-190">Internal Storage</span></span> 

<span data-ttu-id="c49fb-191">특정 디바이스에서 즉시 부팅할 수도 있고, 터치 스크린을 사용하여 목록에서 해당 디바이스 항목을 왼쪽으로 살짝 밀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="c49fb-192">또한 Surface 디바이스 전원이 꺼질 때 **볼륨 작게** 단추 및 **전원** 단추를 동시에 눌러 USB 디바이스 또는 USB 이더넷 어댑터로 즉시 부팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="c49fb-193">지정된 부팅 순서를 적용하려면 그림 7과 같이 대체 부팅 시퀀스 사용 옵션을 **On으로**설정해야 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c49fb-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Surface 디바이스에 대한 부팅 순서 구성](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="c49fb-195">그림 7.</span><span class="sxs-lookup"><span data-stu-id="c49fb-195">Figure 7.</span></span> <span data-ttu-id="c49fb-196">Surface 디바이스에 대한 부팅 순서 구성</span><span class="sxs-lookup"><span data-stu-id="c49fb-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="c49fb-197">예를 들어 PXE를 사용하여 Windows 배포를 수행하는 경우(여기서 PXE 서버는 IPv4 전용으로 구성됨) **Enable IPv6 for PXE Network Boot**(PXE 네트워크 부팅을 위해 IPv6 사용) 옵션을 사용하여 PXE용 IPv6 지원을 켜거나 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="c49fb-198">UEFI 메뉴: 관리</span><span class="sxs-lookup"><span data-stu-id="c49fb-198">UEFI menu: Management</span></span>
<span data-ttu-id="c49fb-199">관리 페이지에서는 Surface Pro 7, Surface Pro X 및 Surface Laptop 3을 비롯한 적합한 장치에서 제로 터치 UEFI 관리 및 기타 기능 사용을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="c49fb-200">제로 터치 UEFI 관리 및 기타 기능에 대한 액세스를 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *관리합니다. 그림 8. 제로 터치 UEFI 관리 및 기타* 기능에 대한 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="c49fb-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="c49fb-201">제로 터치 UEFI 관리를 사용하면 DFCI(장치 펌웨어 구성 인터페이스)라는 Intune 내의 장치 프로필을 사용하여 UEFI 설정을 원격으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="c49fb-202">이 설정을 구성하지 않는 경우 DFCI를 사용하여 적합한 장치를 관리할 수 있는 능력이 Ready로 **설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c49fb-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="c49fb-203">DFCI를 방지하려면 **옵트아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c49fb-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c49fb-204">UEFI 관리 설정 페이지 및 DFCI 사용은 현재 Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 및 Surface Pro X에 사용할 수 있습니다. 자세한 내용은 [Surface UEFI 설정의 Intune 관리를 참조하세요.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="c49fb-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="c49fb-205">UEFI 메뉴: 종료</span><span class="sxs-lookup"><span data-stu-id="c49fb-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="c49fb-206">그림 9와 같이 \*\*\*\* 종료 **페이지의** 지금 다시 시작 단추를 사용하여 UEFI 설정을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![UEFI 화면을 종료하고 디바이스를 다시 시작](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="c49fb-208">그림 9.</span><span class="sxs-lookup"><span data-stu-id="c49fb-208">Figure 9.</span></span> <span data-ttu-id="c49fb-209">지금 다시 시작을 클릭하여 UEFI 화면을 종료하고 디바이스를 다시 시작</span><span class="sxs-lookup"><span data-stu-id="c49fb-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="c49fb-210">Surface UEFI 부팅 화면</span><span class="sxs-lookup"><span data-stu-id="c49fb-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="c49fb-211">Surface 디바이스 펌웨어를 업데이트할 때 Windows 업데이트나 수동 설치를 사용하여 업데이트가 디바이스에 즉시 적용되지 않고 다음 다시 부팅 주기 동안 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="c49fb-212">Surface 펌웨어 업데이트 프로세스에 대한 자세한 내용은 [Surface 드라이버 및 펌웨어 업데이트 관리](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c49fb-212">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="c49fb-213">펌웨어 업데이트 진행률이 화면에 표시되고 진행률 표시줄은 각 구성 요소의 펌웨어를 나타내는 여러 색으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="c49fb-214">그림 9에서 18까지의 그림에는 각 구성 요소의 진행률 표시줄이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="c49fb-216">그림 10.</span><span class="sxs-lookup"><span data-stu-id="c49fb-216">Figure 10.</span></span> <span data-ttu-id="c49fb-217">파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="c49fb-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="c49fb-219">그림 11.</span><span class="sxs-lookup"><span data-stu-id="c49fb-219">Figure 11.</span></span> <span data-ttu-id="c49fb-220">녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어</span><span class="sxs-lookup"><span data-stu-id="c49fb-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="c49fb-222">그림 12.</span><span class="sxs-lookup"><span data-stu-id="c49fb-222">Figure 12.</span></span> <span data-ttu-id="c49fb-223">주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="c49fb-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="c49fb-225">그림 13.</span><span class="sxs-lookup"><span data-stu-id="c49fb-225">Figure 13.</span></span> <span data-ttu-id="c49fb-226">빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="c49fb-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="c49fb-228">그림 14.</span><span class="sxs-lookup"><span data-stu-id="c49fb-228">Figure 14.</span></span> <span data-ttu-id="c49fb-229">회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="c49fb-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![밝은 녹색 진행률 표시줄이 있는 Surface KIP 펌웨어](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="c49fb-231">그림 15.</span><span class="sxs-lookup"><span data-stu-id="c49fb-231">Figure 15.</span></span> <span data-ttu-id="c49fb-232">Surface KIP 펌웨어 업데이트에 밝은 녹색 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![분홍색 진행률 표시줄이 있는 Surface ISH 펌웨어](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="c49fb-234">그림 16 Surface ISH 펌웨어 업데이트에 밝은 분홍색 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![회색 진행률 표시줄이 있는 Surface 트랙 패드 펌웨어](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="c49fb-236">그림 17.</span><span class="sxs-lookup"><span data-stu-id="c49fb-236">Figure 17.</span></span> <span data-ttu-id="c49fb-237">Surface Trackpad 펌웨어 업데이트에 분홍색 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![밝은 회색 진행률 표시줄이 있는 Surface TCON 펌웨어](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="c49fb-239">그림 18.</span><span class="sxs-lookup"><span data-stu-id="c49fb-239">Figure 18.</span></span> <span data-ttu-id="c49fb-240">Surface TCON 펌웨어 업데이트에 밝은 회색 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![밝은 자주색 진행률 표시줄이 있는 Surface TPM 펌웨어](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="c49fb-242">그림 19.</span><span class="sxs-lookup"><span data-stu-id="c49fb-242">Figure 19.</span></span> <span data-ttu-id="c49fb-243">Surface TPM 펌웨어 업데이트에 자주색 진행률 표시줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="c49fb-244">그림 19에 표시된 같이 보안 부팅이 사용되지 않도록 설정되어 있는 경우를 나타내는 추가 경고 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c49fb-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="c49fb-246">그림 20.</span><span class="sxs-lookup"><span data-stu-id="c49fb-246">Figure 20.</span></span> <span data-ttu-id="c49fb-247">Surface UEFI 설정에서 보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면</span><span class="sxs-lookup"><span data-stu-id="c49fb-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="c49fb-248">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c49fb-248">Related topics</span></span>

- [<span data-ttu-id="c49fb-249">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="c49fb-249">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="c49fb-250">Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="c49fb-250">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
