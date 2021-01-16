---
title: Surface UEFI 설정의 Intune 관리
description: 이 문서에서는 Microsoft Intune에서 DFCI 환경을 구성하고 대상 Surface 디바이스의 펌웨어 설정을 관리하는 방법을 설명합니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
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
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271572"
---
# <span data-ttu-id="6694a-103">Surface UEFI 설정의 Intune 관리</span><span class="sxs-lookup"><span data-stu-id="6694a-103">Intune management of Surface UEFI settings</span></span>

## <span data-ttu-id="6694a-104">소개</span><span class="sxs-lookup"><span data-stu-id="6694a-104">Introduction</span></span>

<span data-ttu-id="6694a-105">클라우드에서 장치를 관리하는 능력은 수명 주기 전반에 걸쳐 IT 배포 및 프로비저닝을 크게 간소화했습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="6694a-106">[Microsoft Intune에](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)기본 제공되는 DFCI(장치 펌웨어 구성 인터페이스) 프로필을 사용하여 Surface UEFI 관리는 최신 관리 스택을 UEFI 하드웨어 수준으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-106">With Device Firmware Configuration Interface (DFCI) profiles built into [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="6694a-107">DFCI는 제로 터치 프로비전을 지원하고, BIOS 암호를 제거하고, 부팅 옵션 및 기본 제공 주변 장치를 비롯한 보안 설정을 제어하며, 향후 고급 보안 시나리오를 위한 초안을 마련합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="6694a-108">자주 묻는 질문에 대한 답변은 [Ignite 2019: Intune에서 Surface UEFI](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)설정의 원격 관리 발표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6694a-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <span data-ttu-id="6694a-109">Background</span><span class="sxs-lookup"><span data-stu-id="6694a-109">Background</span></span>

<span data-ttu-id="6694a-110">Windows 10을 실행하는 모든 컴퓨터와 마찬가지로 Surface 디바이스는 CPU가 하드 드라이브, 디스플레이 장치, USB 포트 및 기타 장치와 연결할 수 있도록 SoC에 저장된 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="6694a-111">이 읽기 전용 메모리(ROM)에 저장된 프로그램을 펌웨어라고 합니다(동적 미디어에 저장된 프로그램을 소프트웨어라고도 합니다).</span><span class="sxs-lookup"><span data-stu-id="6694a-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="6694a-112">현재 시장에서 사용 가능한 다른 Windows 10 장치와 달리 Surface는 IT 관리자에게 다양한 UEFI 구성 설정 집합을 통해 펌웨어를 구성하고 관리하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="6694a-113">이렇게 하면 MDM(모바일 장치 관리) 정책, Configuration Manager 또는 그룹 정책을 통해 구현되는 소프트웨어 기반 정책 관리 위에 하드웨어 제어 계층이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="6694a-114">예를 들어 중요한 정보가 있는 높은 보안 영역에 장치를 배포하는 조직은 하드웨어 수준에서 기능을 제거하여 카메라 사용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="6694a-115">디바이스 관점에서 펌웨어 설정을 통해 카메라를 끄는 것은 카메라를 물리적으로 제거하는 데 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="6694a-116">펌웨어 수준에서 추가된 관리 보안을 운영 체제 소프트웨어 설정에만 적용하는지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="6694a-117">예를 들어 도메인 환경에서 정책 설정을 통해 Windows 오디오 서비스를 사용하지 않도록 설정한 경우 로컬 관리자가 서비스를 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <span data-ttu-id="6694a-118">DFCI와 SEMM</span><span class="sxs-lookup"><span data-stu-id="6694a-118">DFCI versus SEMM</span></span>

<span data-ttu-id="6694a-119">이전에 펌웨어를 관리하려면 수동 IT를 많이 사용하는 작업의 오버헤드를 통해 Surface SEMM(엔터프라이즈 관리 모드)에 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-119">Previously, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="6694a-120">예를 들어 SEMM을 사용하려면 IT 직원이 인증서 관리 프로세스의 일부로 두 자리 핀을 입력하기 위해 각 PC에 물리적으로 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="6694a-121">SEMM은 엄격하게 온-프레미스 환경의 조직에 좋은 솔루션으로 유지되어도 복잡성과 IT를 많이 사용하는 요구 사항으로 인해 비용이 많이 드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

 <span data-ttu-id="6694a-122">Microsoft Intune의 통합된 UEFI 펌웨어 관리 기능을 통해 하드웨어를 잠그는 기능이 간소화되고 프로비저닝, 보안 및 간소화된 업데이트에 대한 새로운 기능을 단일 콘솔에서 사용할 수 있으며, [이제는 Microsoft Endpoint Manager로](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-122">With integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="6694a-123">다음 그림에서는 디바이스(왼쪽)에서 직접 보고 끝점 관리자 콘솔(오른쪽)에 표시한 UEFI 설정을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![디바이스(왼쪽) 및 Endpoint Manager 콘솔에 표시되는 UEFI 설정(오른쪽)](images/uefidfci.png)

<span data-ttu-id="6694a-125">중요하게 DFCI는 제로 터치 관리를 가능하게 하여 IT 관리자가 수동으로 상호 작용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="6694a-126">DFCI는 Intune의 장치 프로필 기능을 사용하여 Windows Autopilot을 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="6694a-127">장치 프로필을 사용하면 조직 내의 관리에 등록된 장치에 배포할 수 있는 설정을 추가하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="6694a-128">디바이스가 장치 프로필을 받으면 기능 및 설정이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="6694a-129">일반적인 장치 프로필의 예로는 전자 메일, 장치 제한, VPN, Wi-Fi 및 관리 템플릿이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="6694a-130">DFCI는 단순히 클라우드에서 UEFI 구성 설정을 관리할 수 있는 추가 장치 프로필로, 프레미스 인프라를 유지 관리하지 않고도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <span data-ttu-id="6694a-131">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="6694a-131">Supported devices</span></span>

<span data-ttu-id="6694a-132">DFCI는 다음 장치에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-132">DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="6694a-133">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="6694a-133">Surface Pro 7+</span></span>
- <span data-ttu-id="6694a-134">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="6694a-134">Surface Pro 7</span></span>
- <span data-ttu-id="6694a-135">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="6694a-135">Surface Pro X</span></span>
- <span data-ttu-id="6694a-136">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="6694a-136">Surface Laptop 3</span></span>
- <span data-ttu-id="6694a-137">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="6694a-137">Surface Book 3</span></span>
- <span data-ttu-id="6694a-138">Surface 노트북 이동</span><span class="sxs-lookup"><span data-stu-id="6694a-138">Surface Laptop Go</span></span>

> [!NOTE]
> <span data-ttu-id="6694a-139">Surface Pro X는 기본 제공 카메라, 오디오 및 Wi-Fi/에 대한 DFCI 설정 관리를 지원하지 Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="6694a-139">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <span data-ttu-id="6694a-140">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6694a-140">Prerequisites</span></span>

- <span data-ttu-id="6694a-141">디바이스는 [Microsoft CSP(클라우드](https://partner.microsoft.com/membership/cloud-solution-provider) 솔루션 공급자) 파트너 또는 OEM 배포자가 Windows Autopilot에 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-141">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="6694a-142">Surface에 대한 DFCI를 구성하기 전에  [Microsoft Intune](https://docs.microsoft.com/intune/) 및 Azure [AD(Azure Active](https://docs.microsoft.com/azure/active-directory/) Directory)의 Autopilot 구성 요구 사항에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-142">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <span data-ttu-id="6694a-143">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6694a-143">Before you begin</span></span>

<span data-ttu-id="6694a-144">Azure AD 보안 그룹에 대상 Surface 디바이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-144">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="6694a-145">보안 그룹을 만들고 관리하는 데 대한 자세한 내용은 [Intune 설명서를 참조하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)</span><span class="sxs-lookup"><span data-stu-id="6694a-145">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <span data-ttu-id="6694a-146">Surface 디바이스에 대한 DFCI 관리 구성</span><span class="sxs-lookup"><span data-stu-id="6694a-146">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="6694a-147">DFCI 환경에서는 등록된 장치에 설정을 적용하기 위한 설정 및 Autopilot 프로필이 포함된 DFCI 프로필을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-147">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="6694a-148">등록 상태 프로필은 사용자가 장치를 처음 시작할 때 OOBE 설정 중에 설정이 푸시되도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-148">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="6694a-149">이 가이드에서는 대상 Surface 디바이스에 대한 DFCI 환경을 구성하고 UEFI 구성 설정을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-149">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <span data-ttu-id="6694a-150">DFCI 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="6694a-150">Create DFCI profile</span></span>

<span data-ttu-id="6694a-151">DFCI 정책 설정을 구성하기 전에 먼저 DFCI 프로필을 만들어 대상 장치가 포함된 Azure AD 보안 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-151">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="6694a-152">테넌트에 로그인하여 devicemanagement.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6694a-152">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="6694a-153">Microsoft Endpoint Manager 관리 센터에서 장치 및 > 프로필을 선택하고 > 프로필을 만들고 이름을 입력합니다. \*\*\*\* 예: **DFCI 구성 정책**</span><span class="sxs-lookup"><span data-stu-id="6694a-153">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="6694a-154">플랫폼 **유형으로 Windows 10 이상을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-154">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="6694a-155">프로필 유형 드롭다운 목록에서 장치 펌웨어 **구성** 인터페이스를 선택하여 사용 가능한 모든 정책 설정이 포함된 DFCI 블레이드를 니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-155">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="6694a-156">DFCI 설정에 대한 자세한 내용은 이 페이지 또는 [Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)설명서의 표 1을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6694a-156">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="6694a-157">DFCI 프로필을 편집하여 초기 설치 프로세스 또는 이후 단계에서 DFCI 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-157">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![DFCI 프로필 만들기](images/df1.png)

5. <span data-ttu-id="6694a-159">확인을 **클릭한** 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-159">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="6694a-160">다음 그림과 \*\*\*\* 같이 **할당을** 선택하고 그룹 선택에 대상 장치가 포함된 Azure AD 보안 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-160">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="6694a-161">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-161">Click **Save**.</span></span>

    ![보안 그룹 할당](images/df2a.png)

## <span data-ttu-id="6694a-163">Autopilot 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="6694a-163">Create Autopilot profile</span></span>

1. <span data-ttu-id="6694a-164">In Endpoint Manager at devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles.**</span><span class="sxs-lookup"><span data-stu-id="6694a-164">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="6694a-165">프로필 **만들기를 선택하고** 이름을 입력합니다. 예를 들어 **내 Autopilot 프로필을 선택하고**다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-165">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="6694a-166">다음 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-166">Select the following settings:</span></span>

    - <span data-ttu-id="6694a-167">배포 모드: **사용자 기반**.</span><span class="sxs-lookup"><span data-stu-id="6694a-167">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="6694a-168">가입 유형: Azure **AD 가입**.</span><span class="sxs-lookup"><span data-stu-id="6694a-168">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="6694a-169">다음 그림과 같이 나머지 기본 \*\*\*\* 설정은 변경되지 않은 그대로 유지하고 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-169">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![Autopilot 프로필 만들기](images/df3b.png)

5. <span data-ttu-id="6694a-171">배정 페이지에서 포함할 \*\*\*\* 그룹 선택을 선택하고 Azure AD 보안 그룹을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-171">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="6694a-172">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-172">Select **Next**.</span></span>
6. <span data-ttu-id="6694a-173">요약을 수락한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-173">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="6694a-174">이제 Autopilot 프로필이 만들어지며 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-174">The Autopilot profile is now created and assigned to the group.</span></span>

## <span data-ttu-id="6694a-175">등록 상태 구성 페이지</span><span class="sxs-lookup"><span data-stu-id="6694a-175">Configure Enrollment Status Page</span></span>

<span data-ttu-id="6694a-176">사용자가 로그인하기 전에 OOBE 중에 DFCI 구성을 적용하려면 등록 상태를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-176">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="6694a-177">자세한 내용은 등록 상태 설정 [페이지를 참조하십시오.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="6694a-177">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <span data-ttu-id="6694a-178">Surface 디바이스에서 DFCI 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6694a-178">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="6694a-179">DFCI에는 하드웨어 수준에서 장치를 잠가 추가 수준의 보안을 제공하는 간소화된 UEFI 구성 정책 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-179">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="6694a-180">DFCI는 소프트웨어 수준에서 모바일 장치 관리 설정과 함께 사용할 수 있도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-180">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="6694a-181">DFCI 설정은 Surface 디바이스에 기본 제공되는 하드웨어 구성 요소에만 영향을 주며 USB 웹캠과 같은 연결된 주변 장치로 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-181">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="6694a-182">그러나 Intune에서 장치 제한 정책을 사용하여 소프트웨어 수준에서 연결된 주변 장치에 대한 액세스를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-182">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="6694a-183">아래 그림과 같이 끝점 관리자에서 DFCI 프로필을 편집하여 DFCI 정책 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-183">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="6694a-184">Devicemanagement.microsoft.com 끝점 관리자에서 Windows > 구성 프로필 > **"DFCI 프로필 이름">** 속성 > 선택 > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-184">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![DFCI 설정 구성](images/dfciconfig.png)

### <span data-ttu-id="6694a-186">UEFI 설정에 대한 사용자 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="6694a-186">Block user access to UEFI settings</span></span>

<span data-ttu-id="6694a-187">많은 고객의 경우 사용자가 UEFI 설정을 변경하지 못하게 차단하는 능력이 매우 중요하고 DFCI를 사용하는 주된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-187">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="6694a-188">표 1에 나열된 것 처럼 이 설정은 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용 설정을 **통해 관리됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-188">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="6694a-189">이 설정을 편집하거나 구성하지 않는 경우 로컬 사용자는 Intune에서 관리되지 않는 UEFI 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-189">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="6694a-190">따라서 로컬 사용자가 **UEFI** 설정을 변경할 수 있도록 허용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-190">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="6694a-191">나머지 DFCI 설정을 사용하면 사용자가 사용할 수 있는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-191">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="6694a-192">예를 들어 보안이 높은 영역에서 중요한 정보를 보호해야 하는 경우 카메라를 사용하지 않도록 설정할 수 있으며, 사용자가 USB 드라이브에서 부팅하지 못하게 하려는 경우 이 기능도 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-192">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <span data-ttu-id="6694a-193">표 1.</span><span class="sxs-lookup"><span data-stu-id="6694a-193">Table 1.</span></span> <span data-ttu-id="6694a-194">DFCI 시나리오</span><span class="sxs-lookup"><span data-stu-id="6694a-194">DFCI scenarios</span></span>

| <span data-ttu-id="6694a-195">장치 관리 목표</span><span class="sxs-lookup"><span data-stu-id="6694a-195">Device management goal</span></span>                        | <span data-ttu-id="6694a-196">구성 단계</span><span class="sxs-lookup"><span data-stu-id="6694a-196">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="6694a-197">로컬 사용자가 UEFI 설정을 변경하지 못하게 차단</span><span class="sxs-lookup"><span data-stu-id="6694a-197">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="6694a-198">보안 **기능 > UEFI 설정을**변경할 수 있도록 허용하려면 없음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-198">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="6694a-199">카메라를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6694a-199">Disable cameras</span></span>                               | <span data-ttu-id="6694a-200">기본 제공 하드웨어 > **카메라에서**사용 안 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-200">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="6694a-201">마이크 및 스피커 사용 안</span><span class="sxs-lookup"><span data-stu-id="6694a-201">Disable Microphones and speakers</span></span>              | <span data-ttu-id="6694a-202">Built **in Hardware > Microphones and speakers,** select **Disabled**.</span><span class="sxs-lookup"><span data-stu-id="6694a-202">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="6694a-203">라디오 사용 안 Bluetooth(Bluetooth, Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="6694a-203">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="6694a-204">기본 제공 하드웨어 > **라디오(Bluetooth, Wi-Fi 등)에서**사용 안 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-204">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="6694a-205">외부 미디어(USB, SD)에서 부팅을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6694a-205">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="6694a-206">기본 제공 하드웨어 > **부팅 옵션에서 >(USB, SD)에서**부팅하려면 사용 **안 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-206">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="6694a-207">무선 **송수신 장치(Bluetooth, Wi-Fi)** 설정은 유선 이더넷 연결이 있는 디바이스에서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-207">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="6694a-208">Intune의 DFCI에는 현재 Surface 장치에 적용되지 않는 두 가지 설정, 즉 (1) CPU 및 IO 가상화와 (2) 네트워크 어댑터에서 부팅을 사용하지 않도록 설정.</span><span class="sxs-lookup"><span data-stu-id="6694a-208">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="6694a-209">Intune은 관리 권한 및 적용성 규칙을 위임하여 장치 유형을 관리하는 범위 태그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-209">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="6694a-210">모든 DFCI 설정에 대한 정책 관리 지원 및 전체 세부 정보에 대한 자세한 내용은 [Microsoft Intune 설명서를 참조하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)</span><span class="sxs-lookup"><span data-stu-id="6694a-210">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <span data-ttu-id="6694a-211">Autopilot에서 장치 등록</span><span class="sxs-lookup"><span data-stu-id="6694a-211">Register devices in Autopilot</span></span>

<span data-ttu-id="6694a-212">위에서 설명한 대로 DFCI는 대리점 또는 배포자에 의해 Windows Autopilot에 등록된 디바이스에만 적용될 수 있으며 Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X 및 Surface Laptop 3에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-212">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported on Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="6694a-213">보안상의 이유로 Autopilot에 장치를 "자체 프로비전"할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-213">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span> <span data-ttu-id="6694a-214">자세한 내용은 Windows [Autopilot에](surface-autopilot-registration-support.md)대한 Surface 등록 지원을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-214">To learn more, see Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).</span></span> 

## <span data-ttu-id="6694a-215">Autopilot 장치 수동 동기화</span><span class="sxs-lookup"><span data-stu-id="6694a-215">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="6694a-216">Intune 정책 설정은 일반적으로 거의 즉시 적용되지만 설정이 대상 장치에 적용되기까지 10분의 지연이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-216">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="6694a-217">드물지만 최대 8시간의 지연이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-217">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="6694a-218">설정이 가능한 한 빨리 적용되도록(예: 테스트 시나리오) 대상 장치를 수동으로 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-218">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="6694a-219">In Endpoint Manager at devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync.**</span><span class="sxs-lookup"><span data-stu-id="6694a-219">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="6694a-220">자세한 내용은 Windows 장치 수동 [동기화를 참조하세요.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)</span><span class="sxs-lookup"><span data-stu-id="6694a-220">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="6694a-221">UEFI에서 직접 설정을 조정할 때 장치가 표준 Windows 로그인으로 완전히 다시 시작되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-221">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <span data-ttu-id="6694a-222">DFCI 관리 장치에서 UEFI 설정 확인</span><span class="sxs-lookup"><span data-stu-id="6694a-222">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="6694a-223">테스트 환경에서는 Surface UEFI 인터페이스에서 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-223">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="6694a-224">볼륨 + 및 전원 단추를 동시에 \*\*\*\* 누르는 \*\*\*\* 데 관련된 Surface UEFI를 니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-224">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="6694a-225">디바이스를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-225">Select **Devices**.</span></span> <span data-ttu-id="6694a-226">UEFI 메뉴는 다음 그림과 같이 구성된 설정을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-226">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="6694a-228">다음 방법을 참고합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-228">Note how:</span></span>

      - <span data-ttu-id="6694a-229">로컬 사용자가 **UEFI** 설정을 변경할 수 있도록 허용이 없음으로 설정되어 있기 때문에 설정이 회색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-229">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="6694a-230">마이크와 스피커가 \*\*\*\* 사용 안 하게 설정되어 있기 때문에 오디오가 **꺼집니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-230">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <span data-ttu-id="6694a-231">DFCI 정책 설정 제거</span><span class="sxs-lookup"><span data-stu-id="6694a-231">Removing DFCI policy settings</span></span>

<span data-ttu-id="6694a-232">DFCI 프로필을 만들면 구성된 모든 설정이 프로필 관리 범위 내의 모든 디바이스에서 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-232">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="6694a-233">DFCI 프로필을 직접 편집하여 DFCI 정책 설정만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-233">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="6694a-234">원래 DFCI 프로필이 삭제된 경우 새 프로필을 만들고 설정을 적절하게 편집하여 정책 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-234">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <span data-ttu-id="6694a-235">DFCI 관리 제거</span><span class="sxs-lookup"><span data-stu-id="6694a-235">Removing DFCI management</span></span>

**<span data-ttu-id="6694a-236">DFCI 관리를 제거하고 장치를 공장 새 상태로 되 되 관리하려면</span><span class="sxs-lookup"><span data-stu-id="6694a-236">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="6694a-237">Intune에서 디바이스를 사용 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-237">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="6694a-238">In Endpoint Manager at devicemanagement.microsoft.com, choose **Groups > All Devices.**</span><span class="sxs-lookup"><span data-stu-id="6694a-238">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="6694a-239">사용 중지할 장치를 선택한 다음 사용 **중지/지우기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-239">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="6694a-240">자세한 내용은 장치 지우기, 사용 중지 또는 수동으로 장치 초기화를 사용하여 장치 제거를 [참조하세요.](https://docs.microsoft.com/intune/remote-actions/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="6694a-240">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="6694a-241">Intune에서 Autopilot 등록을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-241">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="6694a-242">Windows 등록 또는 > **장치 등록을 > 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="6694a-242">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="6694a-243">Windows Autopilot 디바이스에서 삭제할 장치를 선택한 다음 삭제를 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="6694a-243">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="6694a-244">Surface 브랜드 이더넷 어댑터를 사용하여 장치를 유선 인터넷에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-244">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="6694a-245">장치를 다시 시작하고 UEFI 메뉴를 열어서(전원 단추를 누르고 하면서 볼륨 업 단추를 누르고 있습니다).</span><span class="sxs-lookup"><span data-stu-id="6694a-245">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="6694a-246">네트워크에서 **> 관리** > 구성한 다음 **옵트아웃을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6694a-246">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="6694a-247">Intune을 사용하여 디바이스를 계속 관리하지만 DFCI 관리가 없는 경우 장치를 Autopilot에 자체 등록하고 Intune에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-247">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="6694a-248">DFCI는 자체 등록 장치에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6694a-248">DFCI will not be applied to self-registered devices.</span></span>

## <span data-ttu-id="6694a-249">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6694a-249">Learn more</span></span>
- <span data-ttu-id="6694a-250">[Ignite 2019: Intune에서 Surface UEFI](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 설정의 원격 관리 발표 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="6694a-250">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="6694a-251">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="6694a-251">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="6694a-252">Microsoft Intune에서 Windows 장치에서 DFCI 프로필 사용</span><span class="sxs-lookup"><span data-stu-id="6694a-252">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
