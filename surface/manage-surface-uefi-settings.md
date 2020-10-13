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
ms.date: 10/12/2020
ms.openlocfilehash: 218f98b23adcb7bae2af92655d85144c6e5665e6
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114726"
---
# <span data-ttu-id="77f12-104">Surface UEFI 설정 관리</span><span class="sxs-lookup"><span data-stu-id="77f12-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="77f12-105">모든 현재 및 향후 세대의 Surface 디바이스는 특별히 이러한 장치용으로 Microsoft에서 엔지니어링 한 고유한 통합 확장 가능 펌웨어 인터페이스 (UEFI)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="77f12-106">Surface UEFI 설정은 기본 제공 디바이스 및 구성 요소를 사용 하거나 사용 하지 않도록 설정 하 고, UEFI 설정이 변경 되지 않도록 보호 하 고, Surface device boot 설정을 조정할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="77f12-107">지원 되는 제품</span><span class="sxs-lookup"><span data-stu-id="77f12-107">Supported products</span></span>

<span data-ttu-id="77f12-108">UEFI 관리는 다음에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="77f12-109">Surface Pro 4, Surface Pro (다섯 번째 Gen), Surface Pro 6, Surface pro 7, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="77f12-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro X</span></span>
- <span data-ttu-id="77f12-110">Surface 노트북 (1 Gen), Surface 노트북 2, Surface 노트북 3, Surface 랩톱 이동</span><span class="sxs-lookup"><span data-stu-id="77f12-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="77f12-111">Surface Studio (1 번째 Gen), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="77f12-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="77f12-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="77f12-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="77f12-113">서피스 이동, Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="77f12-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="77f12-114">클라우드 기반 관리 지원</span><span class="sxs-lookup"><span data-stu-id="77f12-114">Support for cloud-based management</span></span>

<span data-ttu-id="77f12-115">Microsoft Intune (공개 미리 보기에서 사용 가능)에 빌드된 DFCI (디바이스 펌웨어 구성 인터페이스) 프로필을 사용 하면 Surface UEFI 관리에서 최신 관리 스택을 UEFI 하드웨어 수준으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="77f12-116">DFCI는 0 터치 프로비저닝을 지원 하 고, BIOS 암호를 제거 하 고, 부팅 옵션 및 기본 제공 주변 장치를 비롯 한 보안 설정 제어를 제공 하며, 앞으로 고급 보안 시나리오의 토대를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="77f12-117">현재 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에는 DFCI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-117">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="77f12-118">자세한 내용은 [SURFACE UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77f12-118">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="77f12-119">서피스 UEFI 메뉴 열기</span><span class="sxs-lookup"><span data-stu-id="77f12-119">Open Surface UEFI menu</span></span>

<span data-ttu-id="77f12-120">시스템 시작 중에 UEFI 설정을 조정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-120">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="77f12-121">화면을 종료 하 고 10 초의 시간이 지난 후 종료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-121">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="77f12-122">**볼륨 위로** 단추를 길게 누르고 나 서 **전원 단추** 를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-122">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="77f12-123">화면에 Microsoft 또는 Surface 로고가 표시 됨에 따라 UEFI 화면이 나타날 때까지 **볼륨** 단추를 계속 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-123">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="77f12-124">UEFI PC 정보 페이지</span><span class="sxs-lookup"><span data-stu-id="77f12-124">UEFI PC information page</span></span>

<span data-ttu-id="77f12-125">PC 정보 페이지에는 Surface device에 대 한 자세한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-125">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="77f12-126">**모델** – surface Book 2 또는 surface Pro 7과 같이 surface 디바이스의 모델이 여기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-126">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="77f12-127">프로세서, 디스크 크기, 메모리 크기와 같은 정확한 디바이스 구성은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-127">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="77f12-128">**UUID** – 이 Universally Unique Identifier 번호는 디바이스별로 고유하며, 배포 또는 관리하는 동안 디바이스를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-128">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="77f12-129">**일련 번호** - 이 번호는 자산 태깅 및 지원 시나리오에서 이 특정 Surface 디바이스를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-129">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="77f12-130">**자산 태그** – 자산 태그는 [자산 태그 도구](https://docs.microsoft.com/surface/assettag)를 사용하여 Surface 디바이스에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-130">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="77f12-131">Surface 디바이스의 펌웨어에 대한 자세한 정보도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-131">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="77f12-132">Surface 디바이스에는 각각 다른 버전의 펌웨어를 실행하는 몇 가지 내부 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-132">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="77f12-133">다음 디바이스 각각의 펌웨어 버전은 **PC 정보** 페이지에 표시됩니다(그림 1 참조).</span><span class="sxs-lookup"><span data-stu-id="77f12-133">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="77f12-134">시스템 UEFI</span><span class="sxs-lookup"><span data-stu-id="77f12-134">System UEFI</span></span> 

- <span data-ttu-id="77f12-135">SAM 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="77f12-135">SAM Controller</span></span> 

- <span data-ttu-id="77f12-136">Intel 관리 엔진</span><span class="sxs-lookup"><span data-stu-id="77f12-136">Intel Management Engine</span></span> 

- <span data-ttu-id="77f12-137">시스템 포함 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="77f12-137">System Embedded Controller</span></span> 

- <span data-ttu-id="77f12-138">터치 펌웨어</span><span class="sxs-lookup"><span data-stu-id="77f12-138">Touch Firmware</span></span> 

![시스템 정보 및 펌웨어 버전 정보](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="77f12-140">그림 1.</span><span class="sxs-lookup"><span data-stu-id="77f12-140">Figure 1.</span></span> <span data-ttu-id="77f12-141">시스템 정보 및 펌웨어 버전 정보</span><span class="sxs-lookup"><span data-stu-id="77f12-141">System information and firmware version information</span></span>*

<span data-ttu-id="77f12-142">Surface 디바이스의 최신 펌웨어 버전에 대한 최신 정보는 디바이스의 [Surface 업데이트 기록](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-142">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="77f12-143">UEFI 보안 페이지</span><span class="sxs-lookup"><span data-stu-id="77f12-143">UEFI Security page</span></span> 

![Surface UEFI 보안 설정 구성](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="77f12-145">그림 2.</span><span class="sxs-lookup"><span data-stu-id="77f12-145">Figure 2.</span></span> <span data-ttu-id="77f12-146">Surface UEFI 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="77f12-146">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="77f12-147">보안 페이지에서는 UEFI 설정을 보호 하는 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-147">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="77f12-148">Surface 디바이스를 UEFI로 부팅할 때 이 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-148">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="77f12-149">암호에는 다음 문자를 포함할 수 있습니다 (그림 3).</span><span class="sxs-lookup"><span data-stu-id="77f12-149">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="77f12-150">대문자: A-Z</span><span class="sxs-lookup"><span data-stu-id="77f12-150">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="77f12-151">소문자: a-z</span><span class="sxs-lookup"><span data-stu-id="77f12-151">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="77f12-152">숫자: 1-0</span><span class="sxs-lookup"><span data-stu-id="77f12-152">Numbers: 1-0</span></span> 

- <span data-ttu-id="77f12-153">특수 문자:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: ' ' "</span><span class="sxs-lookup"><span data-stu-id="77f12-153">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="77f12-154">암호는 6자 이상이어야 하며 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-154">The password must be at least 6 characters and is case sensitive.</span></span> 

![Surface UEFI 설정 보호를 위해 암호 추가](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="77f12-156">그림 3.</span><span class="sxs-lookup"><span data-stu-id="77f12-156">Figure 3.</span></span> <span data-ttu-id="77f12-157">Surface UEFI 설정 보호를 위해 암호 추가</span><span class="sxs-lookup"><span data-stu-id="77f12-157">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="77f12-158">보안 페이지에서 Surface 디바이스에 대한 보안 부팅 구성을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-158">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="77f12-159">보안 부팅 기술은 무단 부팅 코드가 Surface 디바이스에서 부팅되는 문제를 방지하여 bootkit 및 루트킷 형식의 맬웨어 감염으로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-159">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="77f12-160">Surface 디바이스에서 타사 운영 체제 또는 부팅 가능한 미디어를 허용하기 위해 보안 부팅을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-160">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="77f12-161">그림 4와 같이 타사 인증서와 작동 하도록 보안 부팅을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-161">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="77f12-162">TechNet 라이브러리에서 [보안 부팅](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="77f12-162">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![보안 부팅 구성](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="77f12-164">그림 4.</span><span class="sxs-lookup"><span data-stu-id="77f12-164">Figure 4.</span></span> <span data-ttu-id="77f12-165">보안 부팅 구성</span><span class="sxs-lookup"><span data-stu-id="77f12-165">Configure Secure Boot</span></span>*

<span data-ttu-id="77f12-166">장치에 따라 TPM을 사용 하거나 사용 하지 않도록 설정 하는 방법도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-166">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="77f12-167">**Tpm 사용** 설정이 표시 되지 않으면 그림 5와 같이 Windows에서 tpm을 열어 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-167">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="77f12-168">TPM은 BitLocker로 디바이스 데이터에 대한 암호화를 인증하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-168">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="77f12-169">자세히 알아보려면 [BitLocker 개요](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77f12-169">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM 콘솔](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="77f12-171">그림 5.</span><span class="sxs-lookup"><span data-stu-id="77f12-171">Figure 5.</span></span> <span data-ttu-id="77f12-172">TPM 콘솔</span><span class="sxs-lookup"><span data-stu-id="77f12-172">TPM console</span></span>*


## <span data-ttu-id="77f12-173">UEFI 메뉴: 장치</span><span class="sxs-lookup"><span data-stu-id="77f12-173">UEFI menu: Devices</span></span> 

<span data-ttu-id="77f12-174">Devices (장치) 페이지에서는 다음과 같은 특정 장치 및 구성 요소를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-174">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="77f12-175">도킹 및 USB 포트</span><span class="sxs-lookup"><span data-stu-id="77f12-175">Docking and USB Ports</span></span> 

- <span data-ttu-id="77f12-176">MicroSD 또는 SD 카드 슬롯</span><span class="sxs-lookup"><span data-stu-id="77f12-176">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="77f12-177">후면 카메라</span><span class="sxs-lookup"><span data-stu-id="77f12-177">Rear Camera</span></span> 

- <span data-ttu-id="77f12-178">전면 카메라</span><span class="sxs-lookup"><span data-stu-id="77f12-178">Front Camera</span></span> 

- <span data-ttu-id="77f12-179">IR(적외선) 카메라</span><span class="sxs-lookup"><span data-stu-id="77f12-179">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="77f12-180">Wi-Fi 및 Bluetooth</span><span class="sxs-lookup"><span data-stu-id="77f12-180">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="77f12-181">온보드 오디오(스피커 및 마이크)</span><span class="sxs-lookup"><span data-stu-id="77f12-181">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="77f12-182">각 장치에는 그림 6과 같이 **On** (enabled) 또는 **Off** (사용 안 함) 위치로 이동할 수 있는 슬라이더 단추가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-182">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![특정 디바이스를 사용하거나 사용하지 않도록 설정](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="77f12-184">그림 6.</span><span class="sxs-lookup"><span data-stu-id="77f12-184">Figure 6.</span></span> <span data-ttu-id="77f12-185">특정 디바이스를 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="77f12-185">Enable and disable specific devices</span></span>*

## <span data-ttu-id="77f12-186">UEFI 메뉴: 부팅 구성</span><span class="sxs-lookup"><span data-stu-id="77f12-186">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="77f12-187">부팅 구성 페이지를 통해 부팅 장치의 순서를 변경 하 고 다음 장치의 부팅을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-187">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="77f12-188">Windows 부팅 관리자</span><span class="sxs-lookup"><span data-stu-id="77f12-188">Windows Boot Manager</span></span> 

- <span data-ttu-id="77f12-189">USB 저장소</span><span class="sxs-lookup"><span data-stu-id="77f12-189">USB Storage</span></span> 

- <span data-ttu-id="77f12-190">PXE 네트워크</span><span class="sxs-lookup"><span data-stu-id="77f12-190">PXE Network</span></span> 

- <span data-ttu-id="77f12-191">내부 저장소</span><span class="sxs-lookup"><span data-stu-id="77f12-191">Internal Storage</span></span> 

<span data-ttu-id="77f12-192">특정 디바이스에서 즉시 부팅할 수도 있고, 터치 스크린을 사용하여 목록에서 해당 디바이스 항목을 왼쪽으로 살짝 밀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-192">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="77f12-193">또한 Surface 디바이스 전원이 꺼질 때 **볼륨 작게** 단추 및 **전원** 단추를 동시에 눌러 USB 디바이스 또는 USB 이더넷 어댑터로 즉시 부팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-193">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="77f12-194">지정한 부팅 순서를 적용 하려면 그림 7과 같이 **대체 부팅 순서 사용** 옵션을 **On**으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-194">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Surface 디바이스에 대한 부팅 순서 구성](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="77f12-196">그림 7.</span><span class="sxs-lookup"><span data-stu-id="77f12-196">Figure 7.</span></span> <span data-ttu-id="77f12-197">Surface 디바이스에 대한 부팅 순서 구성</span><span class="sxs-lookup"><span data-stu-id="77f12-197">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="77f12-198">예를 들어 PXE를 사용하여 Windows 배포를 수행하는 경우(여기서 PXE 서버는 IPv4 전용으로 구성됨) **Enable IPv6 for PXE Network Boot**(PXE 네트워크 부팅을 위해 IPv6 사용) 옵션을 사용하여 PXE용 IPv6 지원을 켜거나 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-198">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="77f12-199">UEFI 메뉴: 관리</span><span class="sxs-lookup"><span data-stu-id="77f12-199">UEFI menu: Management</span></span>
<span data-ttu-id="77f12-200">관리 페이지에서 0 터치 UEFI 관리 및 Surface Pro 7, Surface Pro X, Surface 랩톱 3을 비롯 한 적격 디바이스의 기타 기능 사용을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-200">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="77f12-201">0 터치 UEFI 관리 및 기타 기능에 대 한 액세스를 관리 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *합니다 (그림 8). 제로 터치 UEFI 관리 및 기타 기능에 대 한 액세스 관리*</span><span class="sxs-lookup"><span data-stu-id="77f12-201">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="77f12-202">0 터치 UEFI 관리를 사용 하면 Intune CI (디바이스 펌웨어 구성 인터페이스) 라는 장치 프로필을 통해 UEFI 설정을 원격으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-202">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="77f12-203">이 설정을 구성 하지 않으면 DFCI를 사용 하 여 적격 장치를 관리 하는 기능이 **준비**됨으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-203">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="77f12-204">DFCI를 방지 하려면 **옵트아웃**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-204">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="77f12-205">UEFI 관리 설정 페이지와 DFCI의 사용은 Surface Pro 7, Surface Pro X 및 Surface 노트북 3 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-205">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="77f12-206">자세한 내용은 [SURFACE UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77f12-206">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="77f12-207">UEFI 메뉴: 종료</span><span class="sxs-lookup"><span data-stu-id="77f12-207">UEFI menu: Exit</span></span> 

<span data-ttu-id="77f12-208">그림 9와 같이 **끝내기** 페이지의 **지금 다시 시작** 단추를 사용 하 여 UEFI 설정을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-208">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![UEFI 화면을 종료하고 디바이스를 다시 시작](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="77f12-210">그림 9.</span><span class="sxs-lookup"><span data-stu-id="77f12-210">Figure 9.</span></span> <span data-ttu-id="77f12-211">지금 다시 시작을 클릭하여 UEFI 화면을 종료하고 디바이스를 다시 시작</span><span class="sxs-lookup"><span data-stu-id="77f12-211">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="77f12-212">Surface UEFI 부팅 화면</span><span class="sxs-lookup"><span data-stu-id="77f12-212">Surface UEFI boot screens</span></span>

<span data-ttu-id="77f12-213">Surface 디바이스 펌웨어를 업데이트할 때 Windows 업데이트나 수동 설치를 사용하여 업데이트가 디바이스에 즉시 적용되지 않고 다음 다시 부팅 주기 동안 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-213">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="77f12-214">Surface 펌웨어 업데이트 프로세스에 대한 자세한 내용은 [Surface 드라이버 및 펌웨어 업데이트 관리](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77f12-214">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="77f12-215">펌웨어 업데이트 진행률이 화면에 표시되고 진행률 표시줄은 각 구성 요소의 펌웨어를 나타내는 여러 색으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-215">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="77f12-216">각 구성 요소의 진행률 표시줄은 그림 9 ~ 18에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-216">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="77f12-218">그림 10.</span><span class="sxs-lookup"><span data-stu-id="77f12-218">Figure 10.</span></span> <span data-ttu-id="77f12-219">파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="77f12-219">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="77f12-221">그림 11.</span><span class="sxs-lookup"><span data-stu-id="77f12-221">Figure 11.</span></span> <span data-ttu-id="77f12-222">녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어</span><span class="sxs-lookup"><span data-stu-id="77f12-222">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="77f12-224">그림 12.</span><span class="sxs-lookup"><span data-stu-id="77f12-224">Figure 12.</span></span> <span data-ttu-id="77f12-225">주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="77f12-225">The SAM Controller firmware update displays an orange progress bar</span></span>*

![빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="77f12-227">그림 13.</span><span class="sxs-lookup"><span data-stu-id="77f12-227">Figure 13.</span></span> <span data-ttu-id="77f12-228">빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="77f12-228">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="77f12-230">그림 14.</span><span class="sxs-lookup"><span data-stu-id="77f12-230">Figure 14.</span></span> <span data-ttu-id="77f12-231">회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="77f12-231">The Surface touch firmware update displays a gray progress bar</span></span>*

![연한 녹색 진행률 표시줄이 있는 Surface KIP 펌웨어](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="77f12-233">그림 15.</span><span class="sxs-lookup"><span data-stu-id="77f12-233">Figure 15.</span></span> <span data-ttu-id="77f12-234">Surface KIP 펌웨어 업데이트는 연한 녹색 진행률 표시줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-234">The Surface KIP firmware update displays a light green progress bar</span></span>*

![분홍색 진행률 표시줄이 있는 Surface ISH 펌웨어](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="77f12-236">그림 16 연한 분홍 진행률 표시줄을 표시 하는 Surface ISH 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="77f12-236">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![회색 진행률 표시줄이 있는 Surface 트랙 패드 펌웨어](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="77f12-238">그림 17.</span><span class="sxs-lookup"><span data-stu-id="77f12-238">Figure 17.</span></span> <span data-ttu-id="77f12-239">Surface 트랙 패드 펌웨어 업데이트는 분홍색 진행률 표시줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-239">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![연한 회색 진행률 막대가 있는 펌웨어의 표면 tc](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="77f12-241">그림 18.</span><span class="sxs-lookup"><span data-stu-id="77f12-241">Figure 18.</span></span> <span data-ttu-id="77f12-242">펌웨어 업데이트의 Surface TCON 밝은 회색 진행률 표시줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-242">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![연한 자주색 진행률 표시줄이 있는 Surface TPM 펌웨어](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="77f12-244">그림 19.</span><span class="sxs-lookup"><span data-stu-id="77f12-244">Figure 19.</span></span> <span data-ttu-id="77f12-245">Surface TPM 펌웨어 업데이트는 자주색 진행률 표시줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-245">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="77f12-246">그림 19와 같이 보안 부팅이 비활성화 됨을 나타내는 추가 경고 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f12-246">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="77f12-248">그림 20.</span><span class="sxs-lookup"><span data-stu-id="77f12-248">Figure 20.</span></span> <span data-ttu-id="77f12-249">Surface UEFI 설정에서 보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면</span><span class="sxs-lookup"><span data-stu-id="77f12-249">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="77f12-250">관련 항목</span><span class="sxs-lookup"><span data-stu-id="77f12-250">Related topics</span></span>

- [<span data-ttu-id="77f12-251">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="77f12-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="77f12-252">Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="77f12-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
