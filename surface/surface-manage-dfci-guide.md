---
title: Surface UEFI 설정의 Intune 관리
description: 이 문서에서는 대상 Surface 디바이스의 펌웨어 설정을 Microsoft Intune DFCI 환경을 구성하는 방법을 설명합니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4
ms.openlocfilehash: b74aeab45dd2354550f0dff712af5b37b853111c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576518"
---
# <a name="intune-management-of-surface-uefi-settings"></a><span data-ttu-id="fbd9a-103">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="fbd9a-103">Intune management of Surface UEFI settings</span></span>

## <a name="introduction"></a><span data-ttu-id="fbd9a-104">소개</span><span class="sxs-lookup"><span data-stu-id="fbd9a-104">Introduction</span></span>

<span data-ttu-id="fbd9a-105">클라우드에서 장치를 관리하는 기능을 통해 수명 주기 전반에 걸쳐 IT 배포 및 프로비저닝이 크게 간소화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="fbd9a-106">디바이스 펌웨어 구성 인터페이스(DFCI) 프로필을 Microsoft Intune Surface UEFI 관리는 최신 관리 스택을 UEFI 하드웨어 수준으로 확장합니다. [](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-106">With Device Firmware Configuration Interface (DFCI) profiles built into [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="fbd9a-107">DFCI는 제로 터치 프로비전을 지원하고, BIOS 암호를 제거하고, 부팅 옵션 및 기본 제공 주변 장치를 비롯한 보안 설정을 제어하며, 향후 고급 보안 시나리오를 위한 초안을 마련합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="fbd9a-108">자주 묻는 질문에 대한 답변은 [Ignite 2019: Intune에서 Surface UEFI](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)설정의 원격 관리 발표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <a name="background"></a><span data-ttu-id="fbd9a-109">Background</span><span class="sxs-lookup"><span data-stu-id="fbd9a-109">Background</span></span>

<span data-ttu-id="fbd9a-110">Surface Windows 10 실행하는 컴퓨터와 마찬가지로 Surface 디바이스는 CPU가 하드 드라이브, 디스플레이 장치, USB 포트 및 기타 장치와 인터페이스할 수 있도록 SoC에 저장된 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="fbd9a-111">이 읽기 전용 메모리(ROM)에 저장된 프로그램을 펌웨어라고 합니다(동적 미디어에 저장된 프로그램을 소프트웨어라고도 합니다).</span><span class="sxs-lookup"><span data-stu-id="fbd9a-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="fbd9a-112">현재 시장에 출시된 다른 Windows 10 디바이스와 달리 Surface는 IT 관리자에게 다양한 UEFI 구성 설정 집합을 통해 펌웨어를 구성하고 관리하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="fbd9a-113">MDM(모바일 장치 관리) 정책, Configuration Manager 또는 그룹 정책을 통해 구현되는 소프트웨어 기반 정책 관리 위에 하드웨어 제어 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="fbd9a-114">예를 들어 중요한 정보가 있는 높은 보안 영역에 장치를 배포하는 조직은 하드웨어 수준에서 기능을 제거하여 카메라 사용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="fbd9a-115">장치 관점에서 펌웨어 설정을 통해 카메라를 끄는 것은 카메라를 물리적으로 제거하는 데 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="fbd9a-116">펌웨어 수준에서 추가된 관리 보안을 운영 체제 소프트웨어 설정에만 적용하는지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="fbd9a-117">예를 들어 도메인 환경에서 정책 설정을 통해 Windows 오디오 서비스를 사용하지 않도록 설정하면 로컬 관리자가 서비스를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <a name="dfci-versus-semm"></a><span data-ttu-id="fbd9a-118">DFCI 및 SEMM</span><span class="sxs-lookup"><span data-stu-id="fbd9a-118">DFCI versus SEMM</span></span>

<span data-ttu-id="fbd9a-119">이전에 펌웨어를 관리하려면 수동 IT를 많이 사용하는 작업의 오버헤드를 Enterprise Surface Enterprise 관리 모드에 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-119">Previously, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="fbd9a-120">예를 들어 SEMM을 사용하려면 IT 직원이 인증서 관리 프로세스의 일부로 2자리 핀을 입력하기 위해 각 PC에 물리적으로 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="fbd9a-121">SEMM은 엄격하게 온-프레미스 환경의 조직에 좋은 솔루션으로 유지되어도 복잡성과 IT를 많이 사용하는 요구 사항으로 인해 비용이 많이 드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

 <span data-ttu-id="fbd9a-122">Microsoft Intune 통합된 UEFI 펌웨어 관리 기능을 사용하면 하드웨어를 잠그는 기능이 간소화되고 프로비저닝, 보안에 대한 새로운 기능과 함께 사용하기가 쉬워지며 단일 콘솔에서 모든 업데이트가 간소화되어 이제는 통합되어 [Microsoft Endpoint Manager.](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-122">With integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="fbd9a-123">다음 그림에서는 디바이스(왼쪽)에서 직접 보고 Endpoint Manager 콘솔(오른쪽)에서 UEFI 설정을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![디바이스(왼쪽) 및 Endpoint Manager UEFI 설정(오른쪽)](images/uefidfci.png)

<span data-ttu-id="fbd9a-125">중요하게 DFCI는 제로 터치 관리를 가능하게 하여 IT 관리자가 수동으로 상호 작용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="fbd9a-126">DFCI는 Intune의 장치 Windows 기능을 사용하여 Autopilot을 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="fbd9a-127">장치 프로필을 사용하면 조직 내의 관리에 등록된 장치에 배포할 수 있는 설정을 추가하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="fbd9a-128">디바이스가 장치 프로필을 받으면 기능 및 설정이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="fbd9a-129">일반적인 장치 프로필의 예로는 전자 메일, 장치 제한, VPN, Wi-Fi 및 관리 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="fbd9a-130">DFCI는 단순히 사내 인프라를 유지 관리하지 않고도 클라우드에서 UEFI 구성 설정을 관리할 수 있는 추가 장치 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <a name="supported-devices"></a><span data-ttu-id="fbd9a-131">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="fbd9a-131">Supported devices</span></span>

<span data-ttu-id="fbd9a-132">DFCI는 다음 장치에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-132">DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="fbd9a-133">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="fbd9a-133">Surface Pro 7+</span></span>
- <span data-ttu-id="fbd9a-134">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="fbd9a-134">Surface Pro 7</span></span>
- <span data-ttu-id="fbd9a-135">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="fbd9a-135">Surface Pro X</span></span>
- <span data-ttu-id="fbd9a-136">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="fbd9a-136">Surface Laptop 3</span></span>
- <span data-ttu-id="fbd9a-137">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="fbd9a-137">Surface Book 3</span></span>
- <span data-ttu-id="fbd9a-138">Surface Laptop 이동</span><span class="sxs-lookup"><span data-stu-id="fbd9a-138">Surface Laptop Go</span></span>
- <span data-ttu-id="fbd9a-139">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="fbd9a-139">Surface Laptop 4</span></span>

> [!NOTE]
> <span data-ttu-id="fbd9a-140">Surface Pro X는 기본 제공 카메라, 오디오 및 Wi-Fi/Fi/에 대한 DFCI 설정 관리를 지원하지 Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-140">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fbd9a-141">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fbd9a-141">Prerequisites</span></span>

- <span data-ttu-id="fbd9a-142">디바이스는 [CSP(Windows](https://partner.microsoft.com/membership/cloud-solution-provider) OEM 배포자)Microsoft 클라우드 솔루션 공급자 Autopilot에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-142">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="fbd9a-143">Surface에 대해 DFCI를 구성하기 전에 Azure AD(Microsoft Intune [](https://docs.microsoft.com/intune/) 및 Azure Active Directory)의 Autopilot 구성 요구 사항을 잘 알고 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-143">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fbd9a-144">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="fbd9a-144">Before you begin</span></span>

<span data-ttu-id="fbd9a-145">Azure AD 보안 그룹에 대상 Surface 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-145">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="fbd9a-146">보안 그룹을 만들고 관리하는 데 대한 자세한 내용은 [Intune 설명서 를 참조하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-146">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <a name="configure-dfci-management-for-surface-devices"></a><span data-ttu-id="fbd9a-147">Surface 디바이스에 대한 DFCI 관리 구성</span><span class="sxs-lookup"><span data-stu-id="fbd9a-147">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="fbd9a-148">DFCI 환경에서는 설정이 포함된 DFCI 프로필과 Autopilot 프로필을 설정하여 등록된 장치에 설정을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-148">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="fbd9a-149">등록 상태 프로필은 사용자가 장치를 처음 시작할 때 OOBE 설정 중에 설정이 푸시되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-149">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="fbd9a-150">이 가이드에서는 DFCI 환경을 구성하고 대상 Surface 디바이스에 대한 UEFI 구성 설정을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-150">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <a name="create-dfci-profile"></a><span data-ttu-id="fbd9a-151">DFCI 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="fbd9a-151">Create DFCI profile</span></span>

<span data-ttu-id="fbd9a-152">DFCI 정책 설정을 구성하기 전에 먼저 DFCI 프로필을 만들어 대상 장치가 포함된 Azure AD 보안 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-152">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="fbd9a-153">테넌트에 로그인하여 devicemanagement.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-153">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="fbd9a-154">Microsoft Endpoint Manager 관리 센터에서 장치 **>** 구성 프로필을 선택하고 > 프로필을 만들고 이름을 입력합니다. 예를 들어 **DFCI 구성 정책과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-154">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="fbd9a-155">플랫폼 **Windows 10 이상을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-155">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="fbd9a-156">프로필 유형 드롭다운 목록에서 \*\*\*\* 장치 펌웨어 구성 인터페이스를 선택하여 사용 가능한 모든 정책 설정이 포함된 DFCI 블레이드를 니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-156">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="fbd9a-157">DFCI 설정에 대한 자세한 내용은 이 페이지의 표 1 또는 Intune 설명서를 [참고하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-157">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="fbd9a-158">DFCI 프로필을 편집하여 초기 설치 프로세스 또는 이후 단계에서 DFCI 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-158">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![DFCI 프로필 만들기](images/df1.png)

5. <span data-ttu-id="fbd9a-160">**확인을 클릭한** 다음 **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-160">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="fbd9a-161">다음 그림과 \*\*\*\* 같이 **할당을** 선택하고 그룹 선택에서 대상 장치가 포함된 Azure AD 보안 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-161">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="fbd9a-162">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-162">Click **Save**.</span></span>

    ![보안 그룹 할당](images/df2a.png)

## <a name="create-autopilot-profile"></a><span data-ttu-id="fbd9a-164">Autopilot 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="fbd9a-164">Create Autopilot profile</span></span>

1. <span data-ttu-id="fbd9a-165">등록 Endpoint Manager devicemanagement.microsoft.com 등록할 장치를 선택하고 **> Windows** 아래로 **스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-165">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="fbd9a-166">프로필 **만들기를 선택하고** 이름을 입력합니다. 예를 들어 **내 Autopilot 프로필 을 선택하고**다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-166">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="fbd9a-167">다음 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-167">Select the following settings:</span></span>

    - <span data-ttu-id="fbd9a-168">배포 모드: **사용자 기반**.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-168">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="fbd9a-169">참가 유형: Azure **AD 가입**.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-169">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="fbd9a-170">다음 그림과 같이 나머지 기본 설정은 변경되지 않은 것으로 유지하고 **다음을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-170">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![Autopilot 프로필 만들기](images/df3b.png)

5. <span data-ttu-id="fbd9a-172">할당 페이지에서 포함할 그룹 선택을 **선택하고** Azure AD 보안 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-172">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="fbd9a-173">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-173">Select **Next**.</span></span>
6. <span data-ttu-id="fbd9a-174">요약을 수락한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-174">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="fbd9a-175">이제 Autopilot 프로필이 만들어지며 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-175">The Autopilot profile is now created and assigned to the group.</span></span>

## <a name="configure-enrollment-status-page"></a><span data-ttu-id="fbd9a-176">등록 상태 구성 페이지</span><span class="sxs-lookup"><span data-stu-id="fbd9a-176">Configure Enrollment Status Page</span></span>

<span data-ttu-id="fbd9a-177">사용자가 로그인하기 전에 OOBE 중에 DFCI 구성을 적용하려면 등록 상태를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-177">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="fbd9a-178">자세한 내용은 등록 상태 설정 [페이지를 참조하세요.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-178">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <a name="configure-dfci-settings-on-surface-devices"></a><span data-ttu-id="fbd9a-179">Surface 디바이스에서 DFCI 설정 구성</span><span class="sxs-lookup"><span data-stu-id="fbd9a-179">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="fbd9a-180">DFCI에는 하드웨어 수준에서 장치를 잠가 추가 수준의 보안을 제공하는 간소화된 UEFI 구성 정책 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-180">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="fbd9a-181">DFCI는 소프트웨어 수준에서 모바일 장치 관리 설정과 함께 사용할 수 있도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-181">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="fbd9a-182">DFCI 설정은 Surface 디바이스에 기본 제공되는 하드웨어 구성 요소에만 영향을 주며 USB 웹캠과 같은 연결된 주변 장치로 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-182">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="fbd9a-183">그러나 Intune에서 장치 제한 정책을 사용하여 소프트웨어 수준에서 연결된 주변 장치에 대한 액세스를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-183">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="fbd9a-184">아래 그림에 표시된 Endpoint Manager DFCI 프로필을 편집하여 DFCI 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-184">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="fbd9a-185">Endpoint Manager 에서 devicemanagement.microsoft.com 속성 > Windows > **"DFCI**프로필 이름"> 장치 > 선택합니다> 설정.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-185">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![DFCI 설정 구성](images/dfciconfig.png)

### <a name="block-user-access-to-uefi-settings"></a><span data-ttu-id="fbd9a-187">UEFI 설정에 대한 사용자 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="fbd9a-187">Block user access to UEFI settings</span></span>

<span data-ttu-id="fbd9a-188">많은 고객의 경우 사용자가 UEFI 설정을 변경하지 못하게 차단하는 능력이 매우 중요하며 DFCI를 사용하는 주된 이유가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-188">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="fbd9a-189">표 1에 나열된 것 처럼 이 설정은 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용 **설정을 통해 관리됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-189">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="fbd9a-190">이 설정을 편집하거나 구성하지 않는 경우 로컬 사용자는 Intune에서 관리하지 않는 UEFI 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-190">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="fbd9a-191">따라서 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용을 사용하지 않도록 **설정하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-191">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="fbd9a-192">나머지 DFCI 설정을 사용하면 사용자가 사용할 수 있는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-192">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="fbd9a-193">예를 들어 보안이 높은 영역에서 중요한 정보를 보호해야 하는 경우 카메라를 사용하지 않도록 설정하고 사용자가 USB 드라이브에서 부팅하지 못하게 하려는 경우 이 기능을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-193">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <a name="table-1-dfci-scenarios"></a><span data-ttu-id="fbd9a-194">표 1.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-194">Table 1.</span></span> <span data-ttu-id="fbd9a-195">DFCI 시나리오</span><span class="sxs-lookup"><span data-stu-id="fbd9a-195">DFCI scenarios</span></span>

| <span data-ttu-id="fbd9a-196">장치 관리 목표</span><span class="sxs-lookup"><span data-stu-id="fbd9a-196">Device management goal</span></span>                        | <span data-ttu-id="fbd9a-197">구성 단계</span><span class="sxs-lookup"><span data-stu-id="fbd9a-197">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fbd9a-198">로컬 사용자가 UEFI 설정을 변경하지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="fbd9a-198">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="fbd9a-199">보안 기능 > 로컬 사용자가 UEFI 설정을 변경할 **수 있도록 허용에서 없음을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-199">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="fbd9a-200">카메라를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbd9a-200">Disable cameras</span></span>                               | <span data-ttu-id="fbd9a-201">기본 **제공 하드웨어 > 카메라에서**사용 안 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-201">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="fbd9a-202">마이크 및 스피커를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbd9a-202">Disable Microphones and speakers</span></span>              | <span data-ttu-id="fbd9a-203">Built **in Hardware > Microphones and speakers**에서 사용 안 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-203">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="fbd9a-204">무선(Bluetooth, Wi-Fi)을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbd9a-204">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="fbd9a-205">기본 제공 하드웨어 > **라디오(Bluetooth, Wi-Fi 등)에서**사용 안 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-205">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="fbd9a-206">외부 미디어(USB, SD)에서 부팅을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbd9a-206">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="fbd9a-207">기본 제공 하드웨어 > **부팅 옵션> 외부 미디어(USB, SD)에서**부팅에서 사용 안 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-207">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="fbd9a-208">무선 **송수신 장치(Bluetooth, Wi-Fi)** 설정은 유선 이더넷 연결이 있는 디바이스에서만 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-208">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="fbd9a-209">Intune의 DFCI에는 현재 Surface 장치에 적용되지 않는 두 가지 설정, 즉 (1) CPU 및 IO 가상화와 (2) 네트워크 어댑터에서 부팅을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbd9a-209">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="fbd9a-210">Intune은 관리 권한을 위임하기 위한 범위 태그와 장치 유형을 관리하는 적용성 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-210">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="fbd9a-211">모든 DFCI 설정에 대한 정책 관리 지원 및 전체 세부 정보에 대한 자세한 내용은 Microsoft Intune [참조하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-211">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <a name="register-devices-in-autopilot"></a><span data-ttu-id="fbd9a-212">Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="fbd9a-212">Register devices in Autopilot</span></span>

<span data-ttu-id="fbd9a-213">위에서 설명한 대로 DFCI는 대리점 또는 배포자가 Windows Autopilot에 등록된 디바이스에만 적용할 수 있으며 Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X 및 Surface Laptop 3에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-213">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported on Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="fbd9a-214">보안상의 이유로 장치를 Autopilot에 "자체 프로비전"할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-214">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span> <span data-ttu-id="fbd9a-215">자세한 내용은 Autopilot 에 대한 Surface 등록 [Windows 참조합니다.](surface-autopilot-registration-support.md)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-215">To learn more, see Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).</span></span> 

## <a name="manually-sync-autopilot-devices"></a><span data-ttu-id="fbd9a-216">Autopilot 장치 수동 동기화</span><span class="sxs-lookup"><span data-stu-id="fbd9a-216">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="fbd9a-217">Intune 정책 설정은 일반적으로 거의 즉시 적용되지만 설정이 대상 장치에 적용되기까지 10분이 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-217">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="fbd9a-218">드물지만 최대 8시간의 지연이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-218">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="fbd9a-219">설정이 가능한 한 빨리 적용되도록(예: 테스트 시나리오에서) 대상 장치를 수동으로 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-219">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="fbd9a-220">Endpoint Manager Devicemanagement.microsoft.com **Autopilot** Devices에서 장치 등록 > 장치 등록 > Windows 장치로 이동한 > Windows 동기화를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-220">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="fbd9a-221">자세한 내용은 수동으로 Windows [동기화를 참조하세요.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-221">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="fbd9a-222">UEFI에서 직접 설정을 조정할 때 장치가 표준 로그인으로 완전히 다시 Windows 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-222">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a><span data-ttu-id="fbd9a-223">DFCI 관리 장치에서 UEFI 설정 확인</span><span class="sxs-lookup"><span data-stu-id="fbd9a-223">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="fbd9a-224">테스트 환경에서는 Surface UEFI 인터페이스에서 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-224">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="fbd9a-225">볼륨 + 및 전원 단추를 동시에 \*\*\*\* 누르는 \*\*\*\* 데 사용할 수 있는 Surface UEFI를 니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-225">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="fbd9a-226">장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-226">Select **Devices**.</span></span> <span data-ttu-id="fbd9a-227">UEFI 메뉴는 다음 그림과 같이 구성된 설정을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-227">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="fbd9a-229">다음 방법을 참고합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-229">Note how:</span></span>

      - <span data-ttu-id="fbd9a-230">로컬 사용자가 **UEFI를** 변경할 수 있도록 허용 설정이 없음으로 설정되어 있기 때문에 설정이 회색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-230">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="fbd9a-231">마이크와 스피커가 \*\*\*\* 사용 안 으로 설정되어 있기 때문에 오디오가 **꺼집니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-231">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <a name="removing-dfci-policy-settings"></a><span data-ttu-id="fbd9a-232">DFCI 정책 설정 제거</span><span class="sxs-lookup"><span data-stu-id="fbd9a-232">Removing DFCI policy settings</span></span>

<span data-ttu-id="fbd9a-233">DFCI 프로필을 만들면 구성된 모든 설정이 프로필 관리 범위 내의 모든 장치에서 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-233">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="fbd9a-234">DFCI 프로필을 직접 편집하여 DFCI 정책 설정만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-234">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="fbd9a-235">원본 DFCI 프로필이 삭제된 경우 새 프로필을 만들고 설정을 적절하게 편집하여 정책 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-235">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <a name="removing-dfci-management"></a><span data-ttu-id="fbd9a-236">DFCI 관리 제거</span><span class="sxs-lookup"><span data-stu-id="fbd9a-236">Removing DFCI management</span></span>

**<span data-ttu-id="fbd9a-237">DFCI 관리를 제거하고 장치를 공장 새 상태로 되 되 관리하려면:</span><span class="sxs-lookup"><span data-stu-id="fbd9a-237">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="fbd9a-238">Intune에서 디바이스를 사용 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-238">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="fbd9a-239">In Endpoint Manager at devicemanagement.microsoft.com, choose **Groups > All Devices**.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-239">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="fbd9a-240">사용 중지할 장치를 선택한 다음 사용 **중지/지우기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-240">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="fbd9a-241">자세한 내용은 장치 초기화, 사용 중지 또는 수동으로 장치 초기화 를 사용하여 장치 [제거를 참조하세요.](https://docs.microsoft.com/intune/remote-actions/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-241">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="fbd9a-242">Intune에서 Autopilot 등록을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-242">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="fbd9a-243">장치 **등록 또는 > Windows 등록을 > 을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-243">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="fbd9a-244">Autopilot Windows 아래에서 삭제할 장치를 선택한 다음 삭제를 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-244">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="fbd9a-245">커넥트 Surface 브랜드 이더넷 어댑터를 사용하여 유선 인터넷에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-245">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="fbd9a-246">장치를 다시 시작하고 UEFI 메뉴를 여십시오(전원 단추를 누를 때 볼륨 업 단추를 누르고 있습니다).</span><span class="sxs-lookup"><span data-stu-id="fbd9a-246">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="fbd9a-247">관리 > 네트워크에서 > 새로 **고침 구성을** 선택한 다음 **옵트아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbd9a-247">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="fbd9a-248">Intune을 사용하여 장치를 관리하지만 DFCI 관리 없이 장치를 Autopilot에 자체 등록하고 Intune에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-248">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="fbd9a-249">DFCI는 자체 등록 장치에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd9a-249">DFCI will not be applied to self-registered devices.</span></span>

## <a name="learn-more"></a><span data-ttu-id="fbd9a-250">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="fbd9a-250">Learn more</span></span>
- <span data-ttu-id="fbd9a-251">[Ignite 2019: Intune에서 Surface UEFI](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 설정의 원격 관리 발표 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="fbd9a-251">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="fbd9a-252">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="fbd9a-252">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="fbd9a-253">Windows 디바이스에서 DFCI 프로필을 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fbd9a-253">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
