---
title: Surface UEFI 설정의 Intune 관리
description: 이 문서에서는 Microsoft Intune에서 DFCI 환경을 구성하고 대상 지정된 Surface 장치에 대한 공식 엔터프라이즈 설정을 관리하는 방법을 설명합니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/19/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
ms.openlocfilehash: 9d83fe9b7febf996d2cb314399505ed050a69a92
ms.sourcegitcommit: b94832cba98e01014f7d184c85d79f8339e046c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941664"
---
# <span data-ttu-id="0d9e5-103">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="0d9e5-103">Intune management of Surface UEFI settings</span></span>

## <span data-ttu-id="0d9e5-104">소개</span><span class="sxs-lookup"><span data-stu-id="0d9e5-104">Introduction</span></span>

<span data-ttu-id="0d9e5-105">클라우드에서 장치를 관리하는 기능은 간소화된 IT 배포및 수명 주기 전반에 프로비전하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="0d9e5-106">Microsoft Intune에 기본으로 제공되는 DFCI(장치 정보 구성 인터페이스) 프로필(현재 공개 [미리 보기에](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)제공)을 사용하여 Surface UEFI 관리는 최신 관리 스키터를 UEFI 하드웨어 수준으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-106">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="0d9e5-107">DFCI는 0과 터치 프로비저닝을 지원하고, BIOS 암호를 제거하고, 부트 수능 옵션, 기본 제공 주기 등의 보안 설정을 제어하고 향후 보안 시나리오에 대한 지연력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="0d9e5-108">자주 묻는 질문에 대한 대답은 [Ignite 2019: Intune에서 Surface UEFI 설정의 원격 관리 발표를 참조하세요.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <span data-ttu-id="0d9e5-109">Background</span><span class="sxs-lookup"><span data-stu-id="0d9e5-109">Background</span></span>

<span data-ttu-id="0d9e5-110">Windows 10을 실행하는 모든 컴퓨터와 마치 Surface 장치는 CPU가 하드 드라이브, 디스플레이 디바이스, USB 포트 및 기타 장치와 인터페이스할 수 있게 해주는 소프트에 저장된 코드에 의해 의도하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="0d9e5-111">이 읽기 전용 메모리(ROM)에 저장된 프로그램을 친숙한 미디어에 저장된 프로그램을 사자라고 합니다. (동적 미디어에 저장된 프로그램을 소프트웨어라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="0d9e5-112">현재 시장에 제공되는 다른 Windows 10 장치와 달리, Surface는 UEFI 구성 설정 집합을 통해 금지를 구성하고 관리할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="0d9e5-113">이는 MDM(모바일 장치 관리) 정책, Configuration Manager 또는 그룹 정책을 사용하여 구현된 소프트웨어 기반 정책 관리를 위한 하드웨어 집단을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="0d9e5-114">예를 들어 중요한 정보가 있는 장단점에 장치를 배포하는 조직은 하드웨어 수준에서 기능을 제거하여 카메라에서 사용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="0d9e5-115">디바이스 스위치에서 시끄러지 설정을 통한 카메라를 꺼서 카메라를 실제로 제거하는 것과 상관이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="0d9e5-116">사운드 시스템 소프트웨어 설정을 사용하기 위해 사기 기호 수준에서 관리하는 추가 보안을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="0d9e5-117">예를 들어 도메인 환경의 정책 설정을 사용하여 Windows 오디오 서비스를 사용하지 않도록 설정하면 로컬 관리자가 계속 서비스를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <span data-ttu-id="0d9e5-118">DFCI와 SEMM</span><span class="sxs-lookup"><span data-stu-id="0d9e5-118">DFCI versus SEMM</span></span>

<span data-ttu-id="0d9e5-119">지금까지는 계속해서 수동 IT 을 사용하는 수동 작업의 오버헤드를 사용하여 필요한 프리웨어를 SEMM(엔터프라이즈 관리 모드)로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-119">Until now, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="0d9e5-120">예를 들어 SEMM에는 IT 직원이 인증서 관리 프로세스의 일부로 두 자리 PC에 물리적으로 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="0d9e5-121">SEMM은 원주운 전통 환경에서의 조직에서 원격 솔루션을 유지하지만, It 복잡성 및 IT 사용을 많이 사용하는 요구 사항으로 인해 SEMM을 유용하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

<span data-ttu-id="0d9e5-122">이제 Microsoft Intune에서 새로 통합된 UEFI firmware management 기능을 통해 하드웨어를 잠그는 기능이 간소화되어 단일 본체에서 Microsoft 끝점 관리자로 통합된 단일 본체에서 새로운 기능을 제공하고 보안을 설정하고 다시 [관리하는 기능을 사용하기가 더 쉽습니다.](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-122">Now with newly integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="0d9e5-123">다음 그림은 장치(왼쪽)에서 직접 보고 끝점 관리자 본체(오른쪽)에서 본 UEFI 설정을 보여주는 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![장치(왼쪽) 및 끝점 관리자 본체에 표시된 UEFI 설정(오른쪽)](images/uefidfci.png)

<span data-ttu-id="0d9e5-125">전에 DFCI는 터치 관리를 지원하있으면 IT 관리자가 수동 상호 작용을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="0d9e5-126">DFCI는 Intune의 장치 프로필 기능을 사용하여 Windows Autopilot을 사용하여 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="0d9e5-127">장치 프로필을 사용해 조직 내 관리에 등록된 장치에 배포할 수 있는 설정을 추가하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="0d9e5-128">장치가 장치 프로필을 받으면 기능 및 설정이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="0d9e5-129">일반적인 장치 프로필의 예로는 전자 메일, 장치 제한, VPN, Wi-Fi 및 관리 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="0d9e5-130">DFCI는 간단히, 프레미스 인프라를 유지 관리하지 않고도 클라우드에서 UEFI 구성 설정을 관리할 수 있는 추가 장치 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <span data-ttu-id="0d9e5-131">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="0d9e5-131">Supported devices</span></span>

<span data-ttu-id="0d9e5-132">DFCI는 다음과 같은 장치에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-132">DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="0d9e5-133">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="0d9e5-133">Surface Pro 7</span></span>
- <span data-ttu-id="0d9e5-134">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="0d9e5-134">Surface Pro X</span></span>
- <span data-ttu-id="0d9e5-135">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="0d9e5-135">Surface Laptop 3</span></span>
- <span data-ttu-id="0d9e5-136">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="0d9e5-136">Surface Book 3</span></span>

> [!NOTE]
> <span data-ttu-id="0d9e5-137">Surface Pro X는 기본 제공 카메라, 오디오 및 Wi-Fi/Bluetooth 을 위한 DFCI 설정 관리를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-137">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <span data-ttu-id="0d9e5-138">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0d9e5-138">Prerequisites</span></span>

- <span data-ttu-id="0d9e5-139">장치는 [Microsoft CSP(클라우드](https://partner.microsoft.com/membership/cloud-solution-provider) 솔루션 공급자) 파트너 또는 OEM 배포자에 의해 Windows Autopilot에 등록되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-139">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="0d9e5-140">Surface용 DFCI를 구성하기 전에  [Microsoft Intune](https://docs.microsoft.com/intune/) 및 Azure AD(Azure [Active Directory)에서](https://docs.microsoft.com/azure/active-directory/) Autopilot 구성 요구 사항을 숙지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-140">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <span data-ttu-id="0d9e5-141">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="0d9e5-141">Before you begin</span></span>

<span data-ttu-id="0d9e5-142">Azure AD 보안 그룹에 대상 Surface 장치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-142">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="0d9e5-143">보안 그룹 만들기 및 관리에 대한 자세한 내용은 [Intune 설명서를 참조하세요.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-143">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <span data-ttu-id="0d9e5-144">Surface 장치에 대해 DFCI 관리 구성</span><span class="sxs-lookup"><span data-stu-id="0d9e5-144">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="0d9e5-145">DFCI 환경을 사용하려면 등록된 장치에 설정을 적용하려면 설정과 Autopilot 프로필이 포함된 DFCI 프로필을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-145">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="0d9e5-146">사용자가 디바이스를 처음 시작할 때 OOBE 설정 중에 설정이 제거되게 하려면 등록 상태 프로필을 보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-146">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="0d9e5-147">이 가이드에서는 DFCI 환경을 구성하고 대상이 지정된 Surface 장치에 대한 UEFI 구성 설정을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-147">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <span data-ttu-id="0d9e5-148">DFCI 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="0d9e5-148">Create DFCI profile</span></span>

<span data-ttu-id="0d9e5-149">DFCI 정책 설정을 구성하기 전에 먼저 DFCI 프로필을 만들어 대상 디바이스가 포함된 Azure AD 보안 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-149">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="0d9e5-150">비디오에서 테넌트에 devicemanagement.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-150">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="0d9e5-151">Microsoft 끝점 관리자 관리 센터에서 장치 구성 **프로필을 > 선택하고 > 입력합니다.** 예를 들어 **DFCI 구성 정책.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-151">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="0d9e5-152">**플랫폼 유형의 경우 Windows 10** 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-152">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="0d9e5-153">프로필 유형 드롭다운 목록에서 장치 팩트 **구성** 인터페이스를 선택하여 사용 가능한 모든 정책 설정이 포함된 DFCI 블레이드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-153">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="0d9e5-154">DFCI 설정에 대한 자세한 내용은 이 페이지의 표 1 또는 [Intune 설명서를 참조하세요.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-154">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="0d9e5-155">초기 설정 프로세스 중에 DFCI 설정을 구성하려면 DFCI 프로필을 편집하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-155">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![DFCI 프로필 만들기](images/df1.png)

5. <span data-ttu-id="0d9e5-157">확인을 **클릭한** 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-157">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="0d9e5-158">다음 **그림에 표시된** **대로 과제를** 선택하고 선택하여 대상 장치가 포함된 Azure AD 보안 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-158">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="0d9e5-159">**Save**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-159">Click **Save**.</span></span>

    ![보안 그룹 지정 그룹](images/df2a.png)

## <span data-ttu-id="0d9e5-161">Autopilot 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="0d9e5-161">Create Autopilot profile</span></span>

1. <span data-ttu-id="0d9e5-162">네트워크 기준 끝점에서 devicemanagement.microsoft.com **장치를 선택하고 아래 >로** 스크롤하여 배포 **프로필을 배포합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-162">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="0d9e5-163">프로필 **만들기를 선택하고** 이름입력; 예를 들어 **내 Autopilot 프로필을 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-163">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="0d9e5-164">다음 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-164">Select the following settings:</span></span>

    - <span data-ttu-id="0d9e5-165">배포 모드: **사용자 고정용.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-165">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="0d9e5-166">조인 유형: Azure **AD에 가입됨.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-166">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="0d9e5-167">나머지 기본 설정은 변경되지 않은 상태로 그대로 두고 다음 그림에 표시된 다음중 선택합니다. **Next**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-167">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![Autopilot 프로필 만들기](images/df3b.png)

5. <span data-ttu-id="0d9e5-169">과제 페이지에서 포함할 **그룹을 선택하고** Azure AD 보안 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-169">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="0d9e5-170">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-170">Select **Next**.</span></span>
6. <span data-ttu-id="0d9e5-171">요약을 수락한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-171">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="0d9e5-172">이제 Autopilot 프로필이 만들어지고 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-172">The Autopilot profile is now created and assigned to the group.</span></span>

## <span data-ttu-id="0d9e5-173">등록 상태 구성 페이지</span><span class="sxs-lookup"><span data-stu-id="0d9e5-173">Configure Enrollment Status Page</span></span>

<span data-ttu-id="0d9e5-174">사용자가 로그인하기 전에 장치가 OOBE 중에 DFCI 구성을 적용하도록 하려면 등록 상태를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-174">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="0d9e5-175">자세한 내용은 [등록 상태 페이지를 참조하세요.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-175">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <span data-ttu-id="0d9e5-176">Surface 장치에서 DFCI 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0d9e5-176">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="0d9e5-177">DFCI에는 하드웨어 수준에서 디바이스를 잠그어 추가 수준의 보안을 제공하는 간소화된 UEFI 구성 정책 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-177">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="0d9e5-178">DFCI는 소프트웨어 수준의 모바일 장치 관리 설정과 함께 사용하라고 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-178">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="0d9e5-179">DFCI 설정은 Surface 장치에 기본으로 제공되는 하드웨어 구성 요소에만 영향을 주며 USB 웹cam과 같은 주위사용 장치에 첨부되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-179">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="0d9e5-180">(그러나 Intune의 장치 제한 정책을 사용하여 소프트웨어 수준에서 첨부된 주기 장치에 대한 액세스를 해제할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-180">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="0d9e5-181">아래 그림과 같이 끝점 관리자의 DFCI 프로필을 편집하여 DFCI 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-181">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="0d9e5-182">Office의 끝점 devicemanagement.microsoft.com 관리자에서 Windows > > > 구성 프로필 **id > 속성 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-182">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![DFCI 설정 구성](images/dfciconfig.png)

### <span data-ttu-id="0d9e5-184">사용자가 UEFI 설정에 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="0d9e5-184">Block user access to UEFI settings</span></span>

<span data-ttu-id="0d9e5-185">많은 고객의 경우 UEFI 설정을 변경하지 못하도록 차단하는 기능은 중요하고 DFCI를 사용해야 하는 주된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-185">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="0d9e5-186">표 1에 나열된 것처레코드는 로컬 사용자가 **UEFI 설정을 변경할 수 있도록 설정을 통해 관리됩니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-186">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="0d9e5-187">이 설정을 편집하거나 구성하지 않는 경우 로컬 사용자는 Intune에서 관리하지 않는 UEFI 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-187">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="0d9e5-188">따라서 로컬 사용자가 UEFI 설정을 변경할 **수 있도록 허용을 해제하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-188">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="0d9e5-189">DFCI 설정의 나비 부분을 사용하면 사용자가 사용할 수 있는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-189">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="0d9e5-190">예를 들어 중요한 정보를 고도로 안전하게 보호해야 하는 경우 카메라를 사용하지 않도록 설정할 수 있습니다. USB 드라이브의 부부를 받지 않으려면 이 기능을 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-190">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <span data-ttu-id="0d9e5-191">표 1.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-191">Table 1.</span></span> <span data-ttu-id="0d9e5-192">DFCI 시나리오</span><span class="sxs-lookup"><span data-stu-id="0d9e5-192">DFCI scenarios</span></span>

| <span data-ttu-id="0d9e5-193">장치 관리 목표</span><span class="sxs-lookup"><span data-stu-id="0d9e5-193">Device management goal</span></span>                        | <span data-ttu-id="0d9e5-194">구성 단계</span><span class="sxs-lookup"><span data-stu-id="0d9e5-194">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0d9e5-195">로컬 사용자가 UEFI 설정을 변경하지 차단</span><span class="sxs-lookup"><span data-stu-id="0d9e5-195">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="0d9e5-196">보안 **기능>에서 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용하고**증명을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-196">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="0d9e5-197">디스메이너 비활성화</span><span class="sxs-lookup"><span data-stu-id="0d9e5-197">Disable cameras</span></span>                               | <span data-ttu-id="0d9e5-198">기본 **제공 하드웨어 > 성격에서 사용**안 함을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-198">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="0d9e5-199">마이크 및 스피커 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0d9e5-199">Disable Microphones and speakers</span></span>              | <span data-ttu-id="0d9e5-200">**하드웨어 새로 > 내레이터마크 및 스피커에서 사용**안 함을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-200">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="0d9e5-201">라디오 디오오(Bluetooth, Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-201">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="0d9e5-202">**하드웨어 장치 > 라디오(Bluetooth, Wi-Fi 등)에서**사용 안 **함을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-202">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="0d9e5-203">외부 미디어에서 부트수 비활성화(USB, SD)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-203">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="0d9e5-204">**기본 하드웨어 > Boot 옵션> 외부 미디어(USB, SD)에서 부스부를**받도록 선택하도록 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-204">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="0d9e5-205">유선 **이더넷 연결이 설치된 장치에서만 사용 안 함(Bluetooth, Wi-Fi)** 설정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-205">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="0d9e5-206">Intune의 DFCI에는 현재 Surface 장치에 적용되지 않는 두 가지 설정이 포함되어 있습니다. (1) CPU 및 IO 가상화 및 (2) 네트워크 어터터에서 부피를 부스 해제하는 2개의 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-206">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="0d9e5-207">Intune은 범위 태그를 제공하여 관리 권한과 장치 유형을 관리하기 위한 합법적인 권한과 계열사 규칙을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-207">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="0d9e5-208">정책 관리 지원 및 모든 DFCI 설정에 대한 자세한 내용은 [Microsoft Intune 문서를 참조하세요.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-208">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <span data-ttu-id="0d9e5-209">Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="0d9e5-209">Register devices in Autopilot</span></span>

<span data-ttu-id="0d9e5-210">위에서 설명한 것 과정에서 하며, DFCI는 재판매인 또는 배포자가 Windows Autopilot에 등록된 장치에서만 적용될 수 있으며 현재는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-210">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported, at this time, on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="0d9e5-211">보안상의 이유로 디바이스를 Autopilot에 "자체 프로비저닝"할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-211">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span>

## <span data-ttu-id="0d9e5-212">Autopilot 장치를 수동으로 동기화</span><span class="sxs-lookup"><span data-stu-id="0d9e5-212">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="0d9e5-213">일반적으로 Intune 정책 설정은 즉시 적용되지만 설정이 대상 디바이스에 적용되기 10분 지연이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-213">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="0d9e5-214">드문 경우이스크인 경우 최대 8시간의 지연이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-214">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="0d9e5-215">설정이 가능한 한 빠르게 적용되도록 하려면(예: 테스트 시나리오)을 수동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-215">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="0d9e5-216">현재 Microsoft devicemanagement.microsoft.com 엔드 관리자에서 장치 > 장치 등록 **> Windows Autopilot 장치에 만든 > 동기화를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-216">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="0d9e5-217">자세한 내용은 Windows [장치를 수동으로 동기화를 참조하세요.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-217">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="0d9e5-218">UEFI에서 직접 설정을 조정하는 경우 장치가 표준 Windows 로그인으로 전체 다시 시작되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-218">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <span data-ttu-id="0d9e5-219">DFCI 관리 장치에서 UEFI 설정 확인</span><span class="sxs-lookup"><span data-stu-id="0d9e5-219">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="0d9e5-220">테스트 환경에서는 Surface UEFI 인터페이스에서 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-220">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="0d9e5-221">축소판 + 및 전원 버튼을 **동시에** **누르는 작업을** 하는 Surface UEFI를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-221">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="0d9e5-222">장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-222">Select **Devices**.</span></span> <span data-ttu-id="0d9e5-223">UEFI 메뉴는 다음 그림에 표시된 대로 구성된 설정을 반정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-223">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="0d9e5-225">참고 방법:</span><span class="sxs-lookup"><span data-stu-id="0d9e5-225">Note how:</span></span>

      - <span data-ttu-id="0d9e5-226">로컬 사용자가 UEFI 설정을 없음으로 변경할 수 **있도록 허용하므로 설정은 회색으로** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-226">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="0d9e5-227">마이크 및 **스피커가 사용 안 함으로 설정되어 있으므로 오디오가** 꺼져 **설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-227">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <span data-ttu-id="0d9e5-228">DFCI 정책 설정 제거</span><span class="sxs-lookup"><span data-stu-id="0d9e5-228">Removing DFCI policy settings</span></span>

<span data-ttu-id="0d9e5-229">DFCI 프로필을 만들면, 구성된 모든 설정이 관리 프로필 범위 내의 모든 장치에서 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-229">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="0d9e5-230">DFCI 프로필을 직접 편집하여만 DFCI 정책 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-230">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="0d9e5-231">원래 DFCI 프로필이 삭제된 경우 새 프로필을 만들고 적절한 대로 설정을 편집하여 정책 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-231">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <span data-ttu-id="0d9e5-232">DFCI 관리 제거</span><span class="sxs-lookup"><span data-stu-id="0d9e5-232">Removing DFCI management</span></span>

**<span data-ttu-id="0d9e5-233">DFCI 관리를 제거하고 장치를 새 상태로 반환하려면:</span><span class="sxs-lookup"><span data-stu-id="0d9e5-233">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="0d9e5-234">Intune에서 장치 사용 중지:</span><span class="sxs-lookup"><span data-stu-id="0d9e5-234">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="0d9e5-235">PC의 끝점 관리자에서 devicemanagement.microsoft.com **모든 장치> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-235">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="0d9e5-236">사용 중지할 장치를 선택한 다음 사용 **중지/지우기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-236">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="0d9e5-237">장치 데이터 지우기를 사용하거나 사용 중지 또는 수동으로 장치를 등록 [취소하여 디바이스 제거를 참조하세요.](https://docs.microsoft.com/intune/remote-actions/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-237">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="0d9e5-238">Intune에서 Autopilot 레지스트리를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-238">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="0d9e5-239">**장치등록에서 장치 > 등록을 > 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-239">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="0d9e5-240">Windows Autopilot 장치에서 삭제할 장치를 선택한 다음 삭제를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-240">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="0d9e5-241">Surface 대역계 어플레이어를 사용하여 장치를 유선 인터넷에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-241">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="0d9e5-242">장치를 다시 시작하고 UEFI 메뉴를 엽니다(볼륨 크게 단추를 길게 누른 상태에서 전원 단추를 눌러</span><span class="sxs-lookup"><span data-stu-id="0d9e5-242">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="0d9e5-243">네트워크에서 **새로 > 새 >로 고침 구성을 선택한 다음** **Opt out을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d9e5-243">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="0d9e5-244">Intune으로 장치 관리를 계속 유지하고 DFCI 관리는 생각하지 않으려면 장치를 Autopilot에 등록하고 Intune에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-244">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="0d9e5-245">DFCI는 자체 등록 디바이스에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e5-245">DFCI will not be applied to self-registered devices.</span></span>

## <span data-ttu-id="0d9e5-246">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="0d9e5-246">Learn more</span></span>
- <span data-ttu-id="0d9e5-247">[Ignite 2019: Intune에서 Surface UEFI 설정의 원격 관리 발표](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="0d9e5-247">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="0d9e5-248">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="0d9e5-248">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="0d9e5-249">Microsoft Intune에서 Windows 장치의 DFCI 프로필 사용</span><span class="sxs-lookup"><span data-stu-id="0d9e5-249">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
