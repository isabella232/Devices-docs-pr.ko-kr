---
title: 프로비전 패키지 만들기
description: Windows 10의 경우 프로비저닝 패키지를 통해 레지스트리 또는 CSP(콘텐츠 서비스 제공자)를 사용하는 설정을 구성할 수 있습니다.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 인증서 추가, 프로비저닝 패키지
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/28/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 087826a7a0cba7a47accc0d3d66714289f2ae9d2
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613993"
---
# <a name="create-provisioning-packages-for-surface-hub"></a><span data-ttu-id="03c0b-104">사용자용 프로비저닝 패키지 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="03c0b-104">Create provisioning packages for Surface Hub</span></span>

<span data-ttu-id="03c0b-105">프로비저닝 패키지를 사용하면 주요 기능 배포를 자동화하여 조직의 모든 Surface Hub에서 일관된 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-105">Provisioning packages allow you to automate deployment of key features, helping deliver a consistent experience across all Surface Hubs in your organization.</span></span>  <span data-ttu-id="03c0b-106">별도의 Windows WCD(구성 디자이너)를 사용하여 다음 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-106">Using  Windows Configuration Designer (WCD) on a separate PC, you can complete the following tasks:</span></span>

- <span data-ttu-id="03c0b-107">Active Directory 또는 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="03c0b-107">Enroll in Active Directory or Azure Active Directory</span></span>
- <span data-ttu-id="03c0b-108">장치 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="03c0b-108">Create a device administrator account</span></span>
- <span data-ttu-id="03c0b-109">응용 프로그램 및 인증서 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-109">Add applications and certificates</span></span>
- <span data-ttu-id="03c0b-110">프록시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="03c0b-110">Configure proxy settings</span></span>
- <span data-ttu-id="03c0b-111">Surface Hub 구성 파일 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-111">Add a Surface Hub configuration file</span></span>
- <span data-ttu-id="03c0b-112">[CSP(구성 서비스 공급자) 설정 구성](/windows/client-management/mdm/surfacehub-csp)</span><span class="sxs-lookup"><span data-stu-id="03c0b-112">Configure [Configuration Service Provider (CSP) settings](/windows/client-management/mdm/surfacehub-csp)</span></span>

## <a name="overview"></a><span data-ttu-id="03c0b-113">개요</span><span class="sxs-lookup"><span data-stu-id="03c0b-113">Overview</span></span>

1. <span data-ttu-id="03c0b-114">설치 프로그램을 실행하는 별도의 PC에 Windows 10 Windows [구성](https://www.microsoft.com/store/apps/9nblggh4tx22) 디자이너를 Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="03c0b-114">On a separate PC running Windows 10, install [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) from the Microsoft Store.</span></span>
1. <span data-ttu-id="03c0b-115">장치 [**Surface Hub 프로비전을**](#use-surface-hub-provisioning-wizard) 선택하여 마법사를 사용하여 일반 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-115">Select [**Provision Surface Hub devices**](#use-surface-hub-provisioning-wizard) to configure common settings using a wizard.</span></span> <span data-ttu-id="03c0b-116">또는 고급 [프로비전을 선택하여](#use-advanced-provisioning) 가능한 모든 설정을 보고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-116">Or select [Advanced provisioning](#use-advanced-provisioning) to view and configure all possible settings.</span></span>
1. <span data-ttu-id="03c0b-117">프로비저닝 패키지를 만들고 USB 드라이브에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-117">Create the provisioning package and save it to a USB drive.</span></span>
1. <span data-ttu-id="03c0b-118">첫 실행 설치 중에 Surface Hub 또는 앱 앱을 통해 패키지를 설정 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-118">Deploy the package to your Surface Hub during first-run setup, or through the Settings app.</span></span> <span data-ttu-id="03c0b-119">자세한 내용은 에 대한 프로비저닝 [패키지 만들기를 Windows 10.](/windows/configuration/provisioning-packages/provisioning-create-package)</span><span class="sxs-lookup"><span data-stu-id="03c0b-119">To learn more, see [Create a provisioning package for Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package).</span></span>

## <a name="use-surface-hub-provisioning-wizard"></a><span data-ttu-id="03c0b-120">프로비전 Surface Hub 사용</span><span class="sxs-lookup"><span data-stu-id="03c0b-120">Use Surface Hub provisioning wizard</span></span>

1. <span data-ttu-id="03c0b-121">구성 Windows 열고 장치 **프로비전을 Surface Hub 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-121">Open Windows Configuration Designer and select **Provision Surface Hub devices**.</span></span><br>
    ![Surface Hub 프로비저닝 마법사 사용](images/sh-prov-start.png)
    
2. <span data-ttu-id="03c0b-123">프로젝트 이름을 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-123">Name your project and select **Next**.</span></span>

### <a name="add-certificates"></a><span data-ttu-id="03c0b-124">인증서 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-124">Add certificates</span></span>

> [!div class="mx-imgBorder"]
> ![인증서 추가](images/sh-prov-cert.png)

<span data-ttu-id="03c0b-126">인증서를 사용하여 장치를 프로비전하려면 인증서 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-126">To provision the device with a certificate, select **Add a certificate**.</span></span> <span data-ttu-id="03c0b-127">인증서 이름을 입력한 다음 사용할 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-127">Enter a name for the certificate, and then browse to select the certificate to be used.</span></span>  <span data-ttu-id="03c0b-128">고급 프로비저닝 옵션은 패키지에 인증서 추가 아래의 [섹션을 참조하세요.](#add-a-certificate-to-your-package)</span><span class="sxs-lookup"><span data-stu-id="03c0b-128">For advanced provisioning options, refer to the section below [Add a certificate to your package](#add-a-certificate-to-your-package).</span></span>

### <a name="configure-proxy-settings"></a><span data-ttu-id="03c0b-129">프록시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="03c0b-129">Configure proxy settings</span></span>

> [!div class="mx-imgBorder"]
> ![프록시 설정 구성](images/sh-prov-proxy.png)

1. <span data-ttu-id="03c0b-131">프록시 설정에서 **예** 또는 **아니오**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-131">Toggle **Yes** or **No** for proxy settings.</span></span> <span data-ttu-id="03c0b-132">기본적으로 프록시 Surface Hub 자동으로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-132">By default, Surface Hub automatically detects proxy settings.</span></span> <span data-ttu-id="03c0b-133">단, 기존에 프록시 서버가 요구되었다가 프록시 서버를 요구하지 않도록 변경된 인프라의 경우 프로비저닝 패키지를 사용하여 **예s**를 선택하고 **설정 자동 검색**을 선택하여 Surface Hub 장치를 기본 설정으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-133">However, if your infrastructure previously required using a proxy server and has changed to not require a proxy server, you can use a provisioning package to revert your Surface Hub devices to the default settings by selecting **Yes** and **Automatically detect settings**.</span></span>
2. <span data-ttu-id="03c0b-134">예를 전환하는 \*\*\*\* 경우 프록시 설정을 자동으로 검색하도록 선택하거나 다음 중 하나를 입력하여 설정을 수동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-134">If you toggle **Yes**, you can select to automatically detect proxy settings or manually configure the settings by entering one of the following:</span></span>

    - <span data-ttu-id="03c0b-135">설치 스크립트의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-135">A URL to a setup script.</span></span>
    - <span data-ttu-id="03c0b-136">정적 프록시 서버 주소 및 포트 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-136">A static proxy server address and port information.</span></span>

3. <span data-ttu-id="03c0b-137">설치 스크립트 또는 프록시 서버를 사용하려는 경우 자동으로 설정 **검색을 끄면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-137">If you intend to use a setup script or proxy server, turn off **Automatically detect settings**.</span></span> <span data-ttu-id="03c0b-138">설치 스크립트나 프록시 \*\* 서버는 둘 다 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-138">You can use a setup script *or* a proxy server, not both.</span></span>
4. <span data-ttu-id="03c0b-139">예외를 입력합니다(Surface Hub 서버를 사용하지 않고 직접 연결해야 하는 주소).</span><span class="sxs-lookup"><span data-stu-id="03c0b-139">Enter exceptions (addresses that Surface Hub should connect to directly without using the proxy server).</span></span> <span data-ttu-id="03c0b-140">**예:** \*.office365.com</span><span class="sxs-lookup"><span data-stu-id="03c0b-140">**Example:** \*.office365.com</span></span>
5. <span data-ttu-id="03c0b-141">로컬 주소에 프록시 서버를 사용할지 여부를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-141">Identify whether to use the proxy server for local addresses.</span></span>

### <a name="set-up-device-admins"></a><span data-ttu-id="03c0b-142">장치 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="03c0b-142">Set up device admins</span></span>

 > [!div class="mx-imgBorder"]
 > ![Active Directory, Azure AD에 가입하거나 로컬 관리자 계정 만들기](images/sh2-wcd.png)

<span data-ttu-id="03c0b-144">Active Directory에 장치를 등록하고 설정 앱을 사용할 보안 그룹을 지정할 수 있으며 전역 관리자가 설정 앱을 사용할 수 있도록 Azure Active Directory에 등록하거나 장치에 로컬 관리자 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-144">You can enroll the device in Active Directory and specify a security group to use the Settings app, enroll in Azure Active Directory to allow global admins to use the Settings app, or create a local administrator account on the device.</span></span>

1. <span data-ttu-id="03c0b-145">Active Directory에 장치를 등록하려면 권한이 가장 낮은 사용자 계정의 자격 증명을 입력하여 장치를 도메인에 추가하고 Surface Hub에서 관리자 자격 증명을 보유할 보안 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-145">To enroll the device in Active Directory, enter the credentials for a least-privileged user account to join the device to the domain, and specify the security group to have admin credentials on Surface Hub.</span></span> <span data-ttu-id="03c0b-146">초기화한 Surface Hub 패키지에 패키지를 적용하는 경우 처음에 패키지를 설정한 계정과 동일한 도메인 계정을 Surface Hub 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-146">If applying the package to a Surface Hub that was reset, you can use the same domain account as long as it's the same account that set up the Surface Hub initially.</span></span> <span data-ttu-id="03c0b-147">그렇지 않은 경우 프로비저닝 패키지에 다른 도메인의 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-147">Otherwise, a different domain account must be used in the provisioning package.</span></span>
2. <span data-ttu-id="03c0b-148">Windows 구성 디자이너를 사용하여 대량 Azure AD 등록을 구성하기 전에 Azure AD 조인 [구현을 계획하세요.](/azure/active-directory/devices/azureadjoin-plan)</span><span class="sxs-lookup"><span data-stu-id="03c0b-148">Before you use Windows Configuration Designer to configure bulk Azure AD enrollment, [Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="03c0b-149">Azure AD 테넌트의 **사용자당 최대 장치 수**는 마법사에서 얻은 대량 토큰을 사용할 수 있는 횟수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-149">The **maximum number of devices per user** setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span>
3. <span data-ttu-id="03c0b-150">Azure AD에 디바이스를 등록하려면 해당 옵션을 선택하고 마법사를 사용하여 가져올 대량 토큰의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-150">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="03c0b-151">토큰의 만료 날짜를 설정합니다(토큰을 가져온 날로부터 최대 30일).</span><span class="sxs-lookup"><span data-stu-id="03c0b-151">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="03c0b-152">대량 **토큰을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-152">Select **Get bulk token**.</span></span> <span data-ttu-id="03c0b-153">**로그인** 창에서 디바이스를 Azure AD에 가입할 권한이 있는 계정을 입력한 다음 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-153">In the **Let's get you signed in** window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="03c0b-154">**수락을** 선택하여 Windows 구성 디자이너에 필요한 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-154">Select **Accept** to give Windows Configuration Designer the necessary permissions.</span></span>
4. <span data-ttu-id="03c0b-155">로컬 관리자 계정을 만들려면 해당 옵션을 선택하고 사용자 이름 및 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-155">To create a local administrator account, select that option and enter a user name and password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03c0b-156">프로비저닝 패키지에서 로컬 계정을 생성하는 경우 42일마다 **설정** 앱을 사용하여 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-156">If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="03c0b-157">기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-157">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>

### <a name="enroll-in-third-party-mdm-provider"></a><span data-ttu-id="03c0b-158">타사 MDM 공급자에 등록</span><span class="sxs-lookup"><span data-stu-id="03c0b-158">Enroll in third party MDM provider</span></span>

> [!div class="mx-imgBorder"]
> ![타사 모바일 장치 관리에 등록](images/sh-prov-mdm.png)

<span data-ttu-id="03c0b-160">타사 MDM(모바일 장치 관리) 공급자를 사용하는 경우 이 섹션을 사용하여 MDM을 등록할 수 Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="03c0b-160">If you use a third party mobile device management (MDM) provider, you can use this section to enroll Surface Hub.</span></span> <span data-ttu-id="03c0b-161">Intune에 등록하려면 먼저 이전 섹션에 설명된 바와 같이 Azure AD 가입을 설정하고 다음 Intune 설명서의 지침에 따라 Windows 10 [장치를 등록합니다.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="03c0b-161">To enroll in Intune, first setup Azure AD join, as described in the previous section, and follow the instructions in the following Intune documentation: [Set up automatic enrollment for Windows 10 devices](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

1. <span data-ttu-id="03c0b-162">타사 MDM에 등록을 위해 예 또는 아니요를 전환합니다. \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03c0b-162">Toggle **Yes** or **No** for enrollment in third party MDM.</span></span>
2. <span data-ttu-id="03c0b-163">예를 전환하는 \*\*\*\* 경우 장치를 등록하고 인증 유형을 지정할 수 있는 서비스 계정과 암호 또는 인증서 지문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-163">If you toggle **Yes**, provide a service account and password or certificate thumbprint that is authorized to enroll the device and specify the authentication type.</span></span>
3. <span data-ttu-id="03c0b-164">MDM 공급자가 요구하는 경우 검색 서비스, 등록 서비스 및 정책 서비스의 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-164">If required by your MDM provider, enter the URLs for the discovery service, enrollment service, and policy service.</span></span>

 <span data-ttu-id="03c0b-165">자세한 내용은 [Manage Surface Hub with an MDM provider를 참조하세요.](manage-settings-with-mdm-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="03c0b-165">To learn more, see [Manage Surface Hub with an MDM provider.](manage-settings-with-mdm-for-surface-hub.md)</span></span>

### <a name="add-applications"></a><span data-ttu-id="03c0b-166">응용 프로그램 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-166">Add applications</span></span>

> [!div class="mx-imgBorder"]
> ![응용 프로그램 추가](images/sh-prov-apps.png)

<span data-ttu-id="03c0b-168">단일 프로비저닝 패키지로 다수의 UWP(유니버설 Windows 플랫폼)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-168">You can install multiple Universal Windows Platform (UWP) apps in a provisioning package.</span></span> <span data-ttu-id="03c0b-169">자세한 내용은 앱으로 [PC 프로비전을 참조하세요.](/windows/configuration/provisioning-packages/provision-pcs-with-apps)</span><span class="sxs-lookup"><span data-stu-id="03c0b-169">To learn more, see [Provision PCs with apps](/windows/configuration/provisioning-packages/provision-pcs-with-apps).</span></span>

> [!NOTE]
> <span data-ttu-id="03c0b-170">구성 Windows 프로비저닝 패키지에 클래식 Win32 앱을 추가할 수 Surface Hub 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-170">Although Windows Configuration Designer lets you add a Classic Win32 app to a provisioning package, Surface Hub only accepts UWP apps.</span></span> <span data-ttu-id="03c0b-171">클래식 Win32 앱을 포함하면 프로비저닝을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-171">If you include a Classic Win32 app, provisioning will fail.</span></span>

### <a name="add-a-configuration-file"></a><span data-ttu-id="03c0b-172">구성 파일 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-172">Add a configuration file</span></span>

<span data-ttu-id="03c0b-173">이 프로비저닝 패키지 외에도 Surface Hub 구성 파일을 사용하여 장치를 보다 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-173">In addition to this provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="03c0b-174">Surface Hub 구성 파일에는 Exchange, Microsoft Teams 또는 비즈니스용 Skype 연결하기 위한 장치 계정 목록과 무선 투영에 대한 "친숙한 이름"이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-174">A Surface Hub configuration file contains a list of device accounts for connecting to Exchange, Microsoft Teams, or Skype for Business, as well as "friendly names" for wireless projection.</span></span>

**<span data-ttu-id="03c0b-175">구성 파일을 Surface Hub:</span><span class="sxs-lookup"><span data-stu-id="03c0b-175">To create a Surface Hub configuration file:</span></span>**

1. <span data-ttu-id="03c0b-176">파일 Microsoft Excel(또는 기타 .csv 편집기)를 열고 .csv 파일로 SurfaceHubConfiguration.csv</span><span class="sxs-lookup"><span data-stu-id="03c0b-176">Open Microsoft Excel (or other .csv editor), create a .csv file named SurfaceHubConfiguration.csv</span></span>
2. <span data-ttu-id="03c0b-177">디바이스 계정 및 이름 목록을 다음 형식으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-177">Enter a list of device accounts and friendly names in this format:</span></span>

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > <span data-ttu-id="03c0b-178">구성 파일은 열 머리글을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-178">The configuration file must not contain column headers.</span></span> <span data-ttu-id="03c0b-179">사용자 지정에 적용된 프로비저닝 패키지에 Surface Hub 파일에서 디바이스의 계정 및 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-179">When included in a provisioning package applied to Surface Hub, you can select the account and friendly name for the device from the file.</span></span> <span data-ttu-id="03c0b-180">새 .csv 만들하려면 UPN 주소 형식(rainier@contoso.com) 또는 하한 수준 로그온 이름 형식(contoso\rainier)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03c0b-180">To create the .csv file,  use either a UPN address format (rainier@contoso.com) or down-level logon name format (contoso\rainier).</span></span>

- <span data-ttu-id="03c0b-181">rainier@contoso.com,password,Rainier Surface Hub</span><span class="sxs-lookup"><span data-stu-id="03c0b-181">rainier@contoso.com,password,Rainier Surface Hub</span></span>

3. <span data-ttu-id="03c0b-182">파일을 프로젝트 폴더에 저장하고 프로비저닝 패키지를 사용하여 USB 키에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-182">Save the file to your project folder and copy it to the USB key with your provisioning package.</span></span>

> [!NOTE]
> <span data-ttu-id="03c0b-183">구성 파일은 첫 실행 설치 중에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-183">The configuration file can only be applied during first run setup.</span></span>

### <a name="password-protect-provisioning-package"></a><span data-ttu-id="03c0b-184">암호 보호 프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="03c0b-184">Password protect provisioning package</span></span>

<span data-ttu-id="03c0b-185">암호를 사용하기로 선택한 경우 장치에 프로비저닝 패키지를 적용할 때마다 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-185">If you choose to use a password,  you will need to enter it each time you apply the provisioning package to a device.</span></span>

### <a name="complete-provisioning-wizard"></a><span data-ttu-id="03c0b-186">프로비저닝 완료 마법사</span><span class="sxs-lookup"><span data-stu-id="03c0b-186">Complete provisioning wizard</span></span>

<span data-ttu-id="03c0b-187">일반 설정만 구성해야 하는 \*\*\*\* 경우 만들기 완료를 선택하고 패키지 빌드  >  \*\*\*\* [섹션으로 건너뜁니다.](#build-your-package)</span><span class="sxs-lookup"><span data-stu-id="03c0b-187">If you only need to configure common settings, select **Finish** > **Create** and skip to the section [Build your package](#build-your-package).</span></span> <span data-ttu-id="03c0b-188">또는 고급 프로비전으로 전환하여 설정을 계속 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-188">Or continue configuring settings by switching to Advanced provisioning.</span></span>

## <a name="use-advanced-provisioning"></a><span data-ttu-id="03c0b-189">고급 프로비전 사용</span><span class="sxs-lookup"><span data-stu-id="03c0b-189">Use Advanced provisioning</span></span>

> [!TIP]
> <span data-ttu-id="03c0b-190">마법사를 사용하여 일반 설정이 포함된 패키지를 만든 후 기타 설정을 추가하려면 고급 편집기로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-190">Use the wizard to create a package with the common settings, then switch to the advanced editor to add other settings.</span></span><br><br> ![고급 편집기로 전환](images/icd-simple-edit.png)

1. <span data-ttu-id="03c0b-192">이전 섹션에서 계속하는 경우 \*\*\*\* 고급 편집기로 전환을 선택하고 그렇지 않으면 구성 디자이너에서 Windows 고급 프로비전을 **선택합니다.** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03c0b-192">If continuing from the previous section, select **Switch to advanced editor** otherwise open **Windows Configuration Designer** and select **Advanced provisioning**.</span></span><br>
  ![고급 프로비저닝 사용](images/sh-prov-adv.png)

2. <span data-ttu-id="03c0b-194">프로젝트 이름을 지정하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-194">Name your project and select **Next**.</span></span>
3. <span data-ttu-id="03c0b-195">일반을 **선택하여 Windows 10 Team**를 \*\*\*\* 선택하고 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-195">Select **Common to Windows 10 Team**, select **Next**, and then select **Finish**.</span></span><br>
     ![WCD 새 프로젝트](images/icd-new-project.png)

4. <span data-ttu-id="03c0b-197">프로젝트의 사용 **가능한 사용자 지정에서**공통 팀 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-197">In the project, under **Available customizations**, select **Common Team settings**.</span></span><br>
     ![WCD 일반 설정](images/icd-common-settings.png)

### <a name="add-a-certificate-to-your-package"></a><span data-ttu-id="03c0b-199">패키지에 인증서 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-199">Add a certificate to your package</span></span>

<span data-ttu-id="03c0b-200">프로비저닝 패키지를 사용하여 디바이스가 Microsoft Exchange에 인증할 수 있는 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-200">You can use provisioning packages to install certificates that will allow the device to authenticate to Microsoft Exchange.</span></span>

> [!NOTE]
> <span data-ttu-id="03c0b-201">프로비저닝 패키지를 사용할 경우 디바이스(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있고 사용자 저장소에는 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-201">Provisioning packages can only install certificates to the device (local machine) store, and not to the user store.</span></span> <span data-ttu-id="03c0b-202">조직에서 사용자 저장소에 인증서를 설치해야 하는 경우 **Hub** 설정 앱: **Update & Security**  >  **Certificates**Import  >  **Certificate를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-202">If your organization requires that certificates be installed to the user store, use the Hub **Settings** app: **Update & Security** > **Certificates** > **Import Certificate**.</span></span>
<span data-ttu-id="03c0b-203">또는  [**MDM**](manage-settings-with-mdm-for-surface-hub.md) 정책을 사용하여 장치 저장소 또는 사용자 저장소에 인증서를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-203">Alternatively, you can use  [**MDM policies**](manage-settings-with-mdm-for-surface-hub.md) to deploy certificates to either the device store or the user store.</span></span>

> [!TIP]
> <span data-ttu-id="03c0b-204">**ClientCertificates** 섹션은 개인 키가 있는 .pfx 파일용입니다. 루트 CA에 대한 .cer 파일은 **RootCertificates** 섹션에 배치하고 **CACertificates** 섹션의 중간 CA에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-204">The **ClientCertificates** section is for .pfx files with a private key; .cer files for root CAs should be placed in the **RootCertificates** section and for Intermediate CAs in the **CACertificates** section.</span></span>

1. <span data-ttu-id="03c0b-205">구성 **Windows**사용 가능한 사용자 지정에서 런타임 설정  >  \*\*\*\* 인증서 \*\*\*\*  >  \*\*\*\*  >  **ClientCertificates 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-205">In **Windows Configuration Designer** > **Available customizations** , go to **Runtime settings** > **Certificates** > **ClientCertificates**.</span></span>
2. <span data-ttu-id="03c0b-206">**CertificateName에 대한 레이블을 입력한** 다음 추가 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-206">Enter a label for **CertificateName** and then select **Add**.</span></span>
3. <span data-ttu-id="03c0b-207">**CertificatePassword**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-207">Enter the **CertificatePassword**.</span></span>
4. <span data-ttu-id="03c0b-208">**CertificatePath**의 경우 인증서를 찾아보고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-208">For **CertificatePath**, browse and select the certificate.</span></span>
5. <span data-ttu-id="03c0b-209">**ExportCertificate**를 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-209">Set **ExportCertificate** to **False**.</span></span>
6. <span data-ttu-id="03c0b-210">**KeyLocation**의 경우 **소프트웨어만**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-210">For **KeyLocation**, select **Software only**.</span></span>

### <a name="add-a-uwp-app-to-your-package"></a><span data-ttu-id="03c0b-211">패키지에 UWP 앱 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-211">Add a UWP app to your package</span></span>

<span data-ttu-id="03c0b-212">프로비저닝 패키지에 UWP 앱을 추가하려면 앱 패키지(.appx 또는 .appxbundle 파일) 및 종속성 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-212">To add a UWP app to a provisioning package, you will need the app package (.appx or .appxbundle files) and any dependency files.</span></span> <span data-ttu-id="03c0b-213">비즈니스용 Microsoft Store에서 앱을 구매한 경우 *인코드되지 않은* 앱 라이선스도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-213">If you acquired the app from the Microsoft Store for Business, you will also need the *unencoded* app license.</span></span> <span data-ttu-id="03c0b-214">비즈니스용 Microsoft Store에서 이러한 항목을 다운로드하는 방법에 대한 자세한 내용은 [오프라인 앱 배포](/microsoft-store/distribute-offline-apps)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03c0b-214">See [Distribute offline apps](/microsoft-store/distribute-offline-apps) to learn how to download these items from the Microsoft Store for Business.</span></span>

**<span data-ttu-id="03c0b-215">UWP 앱을 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="03c0b-215">To add a UWP app:</span></span>**

1. <span data-ttu-id="03c0b-216">**사용 가능한 사용자 지정** 창에서 **런타임 설정** > **UniversalAppInstall** > **DeviceContextApp**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-216">In the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextApp**.</span></span>
2. <span data-ttu-id="03c0b-217">앱에 **대한 PackageFamilyName을** 입력한 다음 추가 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-217">Enter a **PackageFamilyName** for the app and then select **Add**.</span></span> <span data-ttu-id="03c0b-218">일관성을 위해 앱의 패키지 패밀리 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-218">For consistency, use the app's package family name.</span></span> <span data-ttu-id="03c0b-219">비즈니스용 Microsoft Store에서 앱을 구매한 경우 앱 라이선스에서 패키지 패밀리 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-219">If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license.</span></span> <span data-ttu-id="03c0b-220">텍스트 편집기를 사용하여 라이선스 파일을 열고 PFM 태그 사이의 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-220">Open the license file using a text editor, and use the value between the PFM tags.</span></span>
3. <span data-ttu-id="03c0b-221">**ApplicationFile의**경우 **찾아보기를** 선택하여 대상 앱( .appx 또는 .appxbundle)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-221">For **ApplicationFile**, select **Browse** to find and select the target app ( .appx or .appxbundle).</span></span>
4. <span data-ttu-id="03c0b-222">**DependencyAppxFiles의**경우 **찾아보기를** 선택하여 앱에 대한 종속을 찾아 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-222">For **DependencyAppxFiles**, select **Browse** to find and add any dependencies for the app.</span></span> <span data-ttu-id="03c0b-223">Surface Hub에는 이러한 종속성의 64비트 버전만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-223">For Surface Hub, you will only need the x64 versions of these dependencies.</span></span>

<span data-ttu-id="03c0b-224">앱에서 앱을 구입한 비즈니스용 Microsoft Store 프로비저닝 패키지에 앱 라이선스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-224">If you acquired the app from the Microsoft Store for Business, you will need to add the app license to your provisioning package.</span></span>

**<span data-ttu-id="03c0b-225">앱 라이선스를 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="03c0b-225">To add app license:</span></span>**

1. <span data-ttu-id="03c0b-226">앱 라이선스의 복사본을 만들고 **.ms-windows-store-license** 확장명을 사용하도록 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-226">Make a copy of the app license, and rename it to use a **.ms-windows-store-license** extension.</span></span> <span data-ttu-id="03c0b-227">예를 들어 "example.xml"의 이름을 "example.ms-windows-store-license"로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-227">For example, rename "example.xml" to "example.ms-windows-store-license".</span></span>
2. <span data-ttu-id="03c0b-228">구성 Windows 사용 가능한 사용자 \*\*\*\* 지정 런타임 설정  >  \*\*\*\*  >  **UniversalAppInstall**  >  **DeviceContextAppLicense 로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-228">In Windows Configuration Designer, go to **Available customizations** > **Runtime settings** > **UniversalAppInstall** > **DeviceContextAppLicense**.</span></span>
3. <span data-ttu-id="03c0b-229">**LicenseProductId를 입력한** 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-229">Enter a **LicenseProductId** and then select **Add**.</span></span> <span data-ttu-id="03c0b-230">일관성을 위해 앱 라이선스에 있는 앱의 라이선스 ID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-230">For consistency, use the app's license ID from the app license.</span></span> <span data-ttu-id="03c0b-231">텍스트 편집기를 사용하여 라이선스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-231">Open the license file using a text editor.</span></span> <span data-ttu-id="03c0b-232">그런 다음 **License** 태그에서 **LicenseID** 특성의 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-232">Then, in the **License** tag, use the value in the **LicenseID** attribute.</span></span>
4. <span data-ttu-id="03c0b-233">새 **LicenseProductId** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-233">Select the new **LicenseProductId** node.</span></span> <span data-ttu-id="03c0b-234">**LicenseInstall의**경우 \*\*\*\* 찾아보기를 선택하여 이름 변경된 라이선스 파일(example.ms-windows-store-license)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-234">For **LicenseInstall**, select **Browse** to find and select your renamed license file (example.ms-windows-store-license).</span></span>

### <a name="add-a-policy-to-your-package"></a><span data-ttu-id="03c0b-235">패키지에 정책 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-235">Add a policy to your package</span></span>

<span data-ttu-id="03c0b-236">Surface Hub에서는 [정책 구성 서비스 공급자](/windows/client-management/mdm/policy-configuration-service-provider)의 정책 하위 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-236">Surface Hub supports a subset of the policies in the [Policy configuration service provider](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="03c0b-237">이러한 정책 중 일부는 구성 디자이너를 사용하여 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-237">Some of those policies can be configured with Windows Configuration Designer.</span></span>

 **<span data-ttu-id="03c0b-238">[CSP 정책을 추가하는 경우:](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)</span><span class="sxs-lookup"><span data-stu-id="03c0b-238">To add [CSP policies](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub):</span></span>**

1. <span data-ttu-id="03c0b-239">사용 가능한 사용자 지정 \*\*\*\*  >  **런타임 설정 정책으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-239">Go to  **Available customizations** > **Runtime settings** > **Policies**.</span></span>
2. <span data-ttu-id="03c0b-240">정책 설정을 적절하게 관리하고 구성할 구성 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-240">Select the component you want to manage and configure the policy setting as appropriate.</span></span> <span data-ttu-id="03c0b-241">예를 들어 직원이 2013에서 InPrivate 웹 사이트 브라우징을 사용하지 못하도록 Surface Hub **허용을** 선택한 다음 사용 안 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-241">For example, to prevent employees from using InPrivate website browsing on Surface Hub, select **AllowInPrivate** and then select **Disable**.</span></span>  

    > [!div class="mx-imgBorder"]
    > ![정책 설정 구성](images/sh-prov-policies.png)

### <a name="add-surface-hub-settings-to-your-package"></a><span data-ttu-id="03c0b-243">패키지에 Surface Hub 설정 추가</span><span class="sxs-lookup"><span data-stu-id="03c0b-243">Add Surface Hub settings to your package</span></span>

<span data-ttu-id="03c0b-244">[SurfaceHub 구성 서비스 공급자](/windows/client-management/mdm/surfacehub-csp)의 설정을 프로비저닝 패키지에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-244">You can add settings from the [SurfaceHub configuration service provider](/windows/client-management/mdm/surfacehub-csp) to your provisioning package.</span></span>

1. <span data-ttu-id="03c0b-245">사용 가능한 **사용자 지정**Common  >  **Team Edition**설정.</span><span class="sxs-lookup"><span data-stu-id="03c0b-245">Go to **Available customizations** > **Common Team Edition Settings**.</span></span>
1. <span data-ttu-id="03c0b-246">정책 설정을 적절하게 관리하고 구성할 구성 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-246">Select the component you want to manage and configure the policy setting as appropriate.</span></span>
1. <span data-ttu-id="03c0b-247">프로비저닝 패키지 구성이 완료되면 파일 저장 **을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-247">When you are done configuring the provisioning package, select  **File** > **Save**.</span></span>
1. <span data-ttu-id="03c0b-248">프로젝트 파일에 중요한 정보가 포함될 수 있는 경고를 읽고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-248">Read the warning that project files may contain sensitive information, and select **OK**</span></span>

### <a name="build-your-package"></a><span data-ttu-id="03c0b-249">패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="03c0b-249">Build your package</span></span>

<span data-ttu-id="03c0b-250">프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-250">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="03c0b-251">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-251">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span>  <span data-ttu-id="03c0b-252">프로젝트 파일을 안전한 위치에 저장하거나 더 이상 필요하지 않는 경우 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-252">Store the project files in a secure location or delete if no longer needed.</span></span>

1. <span data-ttu-id="03c0b-253">구성 **Windows**  >  **내보내기 프로비저닝**  >  **패키지 를 열기**</span><span class="sxs-lookup"><span data-stu-id="03c0b-253">Open **Windows Configuration Designer** > **Export** > **Provisioning package**.</span></span>
2. <span data-ttu-id="03c0b-254">\*\*\*\* **소유자를 IT 관리자로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-254">Change **Owner** to **IT Admin**.</span></span>  
3. <span data-ttu-id="03c0b-255">**패키지 버전**에 대한 값을 설정하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-255">Set a value for **Package Version**, and then select **Next.**</span></span>

> [!TIP]
> <span data-ttu-id="03c0b-256">소유자를 IT 관리자로 설정하면 패키지 설정이 적절한 "우선 순위 속성"을 유지 관리하고 다른 프로비저닝 Surface Hub 이후에 다른 소스에서 적용되는 경우 해당 속성에 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-256">Setting the owner to IT Admin ensures that package settings maintain the appropriate "precedence properties" and remain in effect on Surface Hub if other provisioning packages are subsequently applied from other sources.</span></span>

> [!TIP]
> <span data-ttu-id="03c0b-257">기존 패키지를 수정하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-257">You can modify existing packages and change the version number to update previously applied packages.</span></span>

4. <span data-ttu-id="03c0b-258">선택 사항: 패키지를 암호화하고 패키지 서명을 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-258">Optional: You can choose to encrypt the package and enable package signing:</span></span>

    1. <span data-ttu-id="03c0b-259">패키지 **암호화를** 선택한 다음 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-259">Select **Encrypt package** and then enter a password.</span></span>
    1. <span data-ttu-id="03c0b-260">패키지 **서명**  >  **찾아보기를 선택하고** 인증서를 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-260">Select **Sign package** > **Browse** and choose the certificate as appropriate.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="03c0b-261">프로비저닝 패키지에 신뢰할 수 있는 프로비저닝 인증서를 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-261">Including a trusted provisioning certificate in your provisioning package is recommended.</span></span> <span data-ttu-id="03c0b-262">패키지를 장치에 적용하면 인증서가 시스템 저장소에 추가되어 후속 패키지가 자동으로 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-262">When the package is applied to a device, the certificate is added to the system store, enabling subsequent packages to be applied silently.</span></span>

5. <span data-ttu-id="03c0b-263">**다음을** 선택하여 출력 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-263">Select **Next** to specify the output location.</span></span> <span data-ttu-id="03c0b-264">기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-264">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="03c0b-265">또는 **찾아보기를** 선택하여 기본 출력 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-265">Or select **Browse** to change the default output location.</span></span> <span data-ttu-id="03c0b-266">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-266">Select **Next**.</span></span>
6. <span data-ttu-id="03c0b-267">**빌드를** 선택하여 패키지 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-267">Select **Build** to start building the package.</span></span> <span data-ttu-id="03c0b-268">프로젝트 정보가 빌드 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-268">The project information is displayed in the build page.</span></span>
7. <span data-ttu-id="03c0b-269">빌드가 실패하면 프로젝트 폴더에 대한 링크가 있는 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-269">If your build fails, an error message appears with a link to the project folder.</span></span> <span data-ttu-id="03c0b-270">로그를 검토하여 오류를 진단하고 패키지를 다시 작성해 하세요.</span><span class="sxs-lookup"><span data-stu-id="03c0b-270">Review the logs to diagnose the error and try building the package again.</span></span>
8. <span data-ttu-id="03c0b-271">빌드가 성공하면 프로비저닝 패키지, 출력 디렉터리 및 프로젝트 디렉터리의 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-271">If your build succeeds, the name of the provisioning package, output directory, and project directory are displayed.</span></span> <span data-ttu-id="03c0b-272">**마쳤습니다를** 선택하여 마법사를 닫고 사용자 지정 페이지로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-272">Select **Finish** to close the wizard and go back to the Customizations page.</span></span>
9. <span data-ttu-id="03c0b-273">패키지의  **위치로**  이동하려면 출력 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-273">Select  **output location**  to go to the location of the package.</span></span> <span data-ttu-id="03c0b-274">.ppkg를 빈 USB 플래시 드라이브에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-274">Copy the .ppkg to an empty USB flash drive.</span></span>

## <a name="apply-a-provisioning-package-to-surface-hub"></a><span data-ttu-id="03c0b-275">Surface Hub에 프로비저닝 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="03c0b-275">Apply a provisioning package to Surface Hub</span></span>

<span data-ttu-id="03c0b-276">Surface Hub에 프로비저닝 패키지를 배포할 수 있는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-276">There are two options for deploying provisioning packages to a Surface Hub.</span></span> <span data-ttu-id="03c0b-277">첫 [실행](#apply-a-provisioning-package-during-first-run)마법사 에서 인증서를 설치하는 프로비저닝 패키지를 적용할 수 있습니다. 또는 첫 실행 프로그램이 완료된 후 를 사용하여 설정, 앱 및 인증서를 구성하는 프로비저닝 [패키지를 적용할 설정.](#apply-a-provisioning-package-using-settings-app)</span><span class="sxs-lookup"><span data-stu-id="03c0b-277">[During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-provisioning-package-using-settings-app).</span></span>

### <a name="apply-a-provisioning-package-during-first-run"></a><span data-ttu-id="03c0b-278">첫 실행 중에 프로비저닝 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="03c0b-278">Apply a provisioning package during first run</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03c0b-279">첫 실행 프로그램에서는 프로비저닝 패키지를 사용하여 인증서를 설치할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-279">During the first-run program, you can only use provisioning packages to install certificates.</span></span> <span data-ttu-id="03c0b-280">**설정** 앱을 사용하여 앱을 설치하고 다른 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-280">Use the **Settings** app to install apps and apply other settings.</span></span>

1. <span data-ttu-id="03c0b-281">처음 Surface Hub 프로그램을 켜면 처음 실행 프로그램에 안녕 페이지가 [**표시됩니다.**](first-run-program-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="03c0b-281">When you turn on the Surface Hub for the first time, the first-run program displays the [**Hi there page**](first-run-program-surface-hub.md).</span></span> <span data-ttu-id="03c0b-282">계속하기 전에 설정이 제대로 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-282">Make sure that the settings are properly configured before proceeding.</span></span>
2. <span data-ttu-id="03c0b-283">.ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-283">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span> <span data-ttu-id="03c0b-284">패키지가 드라이브의 루트 디렉터리에 있으면 첫 실행 프로그램이 이를 인식하고 디바이스를 설정할지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-284">If the package is in the root directory of the drive, the first-run program will recognize it and ask if you want to set up the device.</span></span> <span data-ttu-id="03c0b-285">**설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-285">Select **Set up**.</span></span>
3. <span data-ttu-id="03c0b-286">다음 화면에서 프로비전 소스를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-286">The next screen asks you to select a provisioning source.</span></span> <span data-ttu-id="03c0b-287">**이동식 미디어** 탭을 선택하고 **다음**을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-287">Select **Removable Media** and tap **Next**.</span></span>
4. <span data-ttu-id="03c0b-288">적용할 프로비저닝 패키지(\*.ppkg)를 선택하고 다음 을 **탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-288">Select the provisioning package (\*.ppkg) that you want to apply, and tap **Next**.</span></span> <span data-ttu-id="03c0b-289">첫 실행  중에는 패키지 한 개만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-289">Note that you can only install one package during first run.</span></span>
5. <span data-ttu-id="03c0b-290">첫 실행 프로그램은 프로비저닝 패키지가 적용될 변경 내용의 요약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-290">The first-run program will show you a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="03c0b-291">**예, 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-291">Select **Yes, add it**.</span></span>
6. <span data-ttu-id="03c0b-292">구성 파일이 USB 플래시 드라이브의 루트 디렉터리에 저장된 경우 **구성 선택** 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-292">If a configuration file is included in the root directory of the USB flash drive, you will see **Select a configuration**.</span></span> <span data-ttu-id="03c0b-293">구성 파일의 첫 장치 계정과 Surface Hub에 적용될 해당 계정의 정보 요약이 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-293">The first device account in the configuration file will be shown with a summary of the account information that will be applied to the Surface Hub.</span></span>
7. <span data-ttu-id="03c0b-294">구성 **선택에서**적용할 장치 이름을 선택하고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-294">In **Select a configuration**, select the device name to apply, and then select **Next**.</span></span>

<span data-ttu-id="03c0b-295">프로비저닝 패키지의 설정이 장치에 적용되고 OOBE 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-295">The settings from the provisioning package will be applied to the device and OOBE will be complete.</span></span> <span data-ttu-id="03c0b-296">장치를 다시 시작하면 USB 플래시 드라이브를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-296">After the device restarts, you can remove the USB flash drive.</span></span>

### <a name="apply-a-provisioning-package-using-settings-app"></a><span data-ttu-id="03c0b-297">앱 앱을 사용하여 프로비저닝 설정 적용</span><span class="sxs-lookup"><span data-stu-id="03c0b-297">Apply a provisioning package using Settings app</span></span>

1. <span data-ttu-id="03c0b-298">.ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-298">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span>
2. <span data-ttu-id="03c0b-299">시작 Surface Hub **시작하고** 설정 관리자 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-299">From Surface Hub, start **Settings** and enter the admin credentials when prompted.</span></span>
3. <span data-ttu-id="03c0b-300">**Surface Hub** > **장치 관리**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-300">Navigate to **Surface Hub** > **Device management**.</span></span> <span data-ttu-id="03c0b-301">**프로비저닝 패키지에서**프로비저닝 패키지 추가 **또는 제거**패키지  >  **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03c0b-301">Under **Provisioning packages**, select **Add or remove a provisioning package** > **Add a package**.</span></span>
4. <span data-ttu-id="03c0b-302">프로비저닝 패키지를 선택하고 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-302">Choose your provisioning package and select **Add**.</span></span>  <span data-ttu-id="03c0b-303">메시지가 표시될 경우 관리자 자격 증명을 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-303">If prompted, enter your admin credentials again.</span></span>
5. <span data-ttu-id="03c0b-304">적용할 변경 내용을 요약하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-304">You'll see a summary of the changes to be applied.</span></span> <span data-ttu-id="03c0b-305">**예, 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03c0b-305">Select **Yes, add it**.</span></span>

## <a name="learn-more"></a><span data-ttu-id="03c0b-306">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="03c0b-306">Learn more</span></span>

- [<span data-ttu-id="03c0b-307">구성 Windows 다운로드</span><span class="sxs-lookup"><span data-stu-id="03c0b-307">Download Windows Configuration Designer</span></span>](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [<span data-ttu-id="03c0b-308">Windows 10용 프로비저닝 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="03c0b-308">Create a provisioning package for Windows 10</span></span>](/windows/configuration/provisioning-packages/provisioning-create-package)
- [<span data-ttu-id="03c0b-309">MDM 공급자를 사용하여 Surface Hub 관리</span><span class="sxs-lookup"><span data-stu-id="03c0b-309">Manage Surface Hub with an MDM provider</span></span>](manage-settings-with-mdm-for-surface-hub.md)
