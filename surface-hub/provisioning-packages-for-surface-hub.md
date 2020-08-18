---
title: 프로비저닝 패키지 만들기(Surface Hub)
description: Windows 10의 경우 프로비저닝 패키지를 통해 레지스트리 또는 CSP(콘텐츠 서비스 제공자)를 사용하는 설정을 구성할 수 있습니다.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: 인증서 추가, 프로비저닝 패키지
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: 9158bec3d2285e5e8d4f9f56e582ff2320a34024
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934878"
---
# <span data-ttu-id="3031c-104">프로비저닝 패키지 만들기(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="3031c-104">Create provisioning packages (Surface Hub)</span></span>

<span data-ttu-id="3031c-105">이 항목에서는 Windows 구성 디자이너를 사용하여 프로비저닝 패키지를 만들고 Surface Hub 디바이스에 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-105">This topic explains how to create a provisioning package using the Windows Configuration Designer, and apply it to Surface Hub devices.</span></span> <span data-ttu-id="3031c-106">Surface Hub의 경우 프로비저닝 패키지를 사용하여 인증서를 추가하고 UWP(유니버설 Windows 플랫폼) 앱을 설치하고 정책과 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-106">For Surface Hub, you can use provisioning packages to add certificates, install Universal Windows Platform (UWP) apps, and customize policies and settings.</span></span>

<span data-ttu-id="3031c-107">첫 실행 설정 중에 USB 메모리를 사용하거나 **설정** 앱을 통해 프로비저닝 패키지를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-107">You can apply a provisioning package using a USB stick during first-run setup, or through the **Settings** app.</span></span> 


## <span data-ttu-id="3031c-108">장점</span><span class="sxs-lookup"><span data-stu-id="3031c-108">Advantages</span></span>
-   <span data-ttu-id="3031c-109">MDM(모바일 장치 관리) 제공자를 사용하지 않고 빠르게 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-109">Quickly configure devices without using a mobile device management (MDM) provider.</span></span>

-   <span data-ttu-id="3031c-110">네트워크 연결이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-110">No network connectivity required.</span></span>

-   <span data-ttu-id="3031c-111">적용이 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-111">Simple to apply.</span></span>

[<span data-ttu-id="3031c-112">프로비저닝 패키지의 이점 및 사용에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-112">Learn more about the benefits and uses of provisioning packages.</span></span>](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## <span data-ttu-id="3031c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3031c-113">Requirements</span></span> 

<span data-ttu-id="3031c-114">프로비저닝 패키지를 만들고 Surface Hub에 적용하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-114">To create and apply a provisioning package to a Surface Hub, you'll need the following:</span></span>

-   <span data-ttu-id="3031c-115">Windows 구성 디자이너는 Microsoft Store 또는 Windows 10 ADK(Assessment and Deployment Kit)을 통해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-115">Windows Configuration Designer, which can be installed from Microsoft Store or from the Windows 10 Assessment and Deployment Kit (ADK).</span></span> [<span data-ttu-id="3031c-116">Windows 구성 디자이너를 설치하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-116">Learn how to install Windows Configuration Designer.</span></span>](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   <span data-ttu-id="3031c-117">USB 메모리.</span><span class="sxs-lookup"><span data-stu-id="3031c-117">A USB stick.</span></span>
-   <span data-ttu-id="3031c-118">**설정** 앱을 사용하여 패키지를 적용할 경우 디바이스 관리자 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-118">If you apply the package using the **Settings** app, you'll need device admin credentials.</span></span>

<span data-ttu-id="3031c-119">Windows 10을 실행하는 PC에서 프로비저닝 패키지를 만들고 해당 패키지를 USB 드라이브에 저장한 다음 Surface Hub에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-119">You create the provisioning package on a PC running Windows 10, save the package to a USB drive, and then deploy it to your Surface Hub.</span></span>


## <span data-ttu-id="3031c-120">Surface Hub 프로비저닝 패키지의 지원되는 항목</span><span class="sxs-lookup"><span data-stu-id="3031c-120">Supported items for Surface Hub provisioning packages</span></span>

<span data-ttu-id="3031c-121">**Surface Hub 장치 프로비전** 마법사를 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-121">Using the **Provision Surface Hub devices** wizard, you can:</span></span>

- <span data-ttu-id="3031c-122">Active Directory, Azure Active Directory 또는 MDM 등록</span><span class="sxs-lookup"><span data-stu-id="3031c-122">Enroll in Active Directory, Azure Active Directory, or MDM</span></span> 
- <span data-ttu-id="3031c-123">장치 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="3031c-123">Create an device administrator account</span></span> 
- <span data-ttu-id="3031c-124">응용 프로그램 및 인증서 추가</span><span class="sxs-lookup"><span data-stu-id="3031c-124">Add applications and certificates</span></span>
- <span data-ttu-id="3031c-125">프록시 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3031c-125">Configure proxy settings</span></span>
- <span data-ttu-id="3031c-126">Surface Hub 구성 파일 추가</span><span class="sxs-lookup"><span data-stu-id="3031c-126">Add a Surface Hub configuration file</span></span>

>[!WARNING]
><span data-ttu-id="3031c-127">마법사를 사용하여 Windows 10에서 Windows 구성 디자이너를 실행해 Azure Active Directory 등록을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-127">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using the wizard.</span></span>

<span data-ttu-id="3031c-128">고급 프로비저닝 편집기를 사용하면 Surface Hub에서 프로비저닝 패키지에 다음 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-128">Using the advanced provisioning editor, you can add these items to provisioning packages for Surface Hub:</span></span>

- <span data-ttu-id="3031c-129">**정책** - Surface Hub에서는 [정책 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies)의 정책 하위 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-129">**Policies** - Surface Hub supports a subset of the policies in the [Policy configuration service provider](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies).</span></span> 
- <span data-ttu-id="3031c-130">**설정** - [SurfaceHub 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)에서 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-130">**Settings** - You can configure any setting in the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx).</span></span>

>[!TIP]
> <span data-ttu-id="3031c-131">마법사를 사용하여 일반 설정이 포함된 패키지를 만든 후 기타 설정을 추가하려면 고급 편집기로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-131">Use the wizard to create a package with the common settings, then switch to the advanced editor to add other settings.</span></span>
>
>![고급 편집기 열기](images/icd-simple-edit.png)

## <span data-ttu-id="3031c-133">Surface Hub 프로비저닝 마법사 사용</span><span class="sxs-lookup"><span data-stu-id="3031c-133">Use the Surface Hub provisioning wizard</span></span>

<span data-ttu-id="3031c-134">[Windows 구성 디자이너를 설치](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)한 다음 이를 사용해 프로비저닝 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-134">After you [install Windows Configuration Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), you can create a provisioning package.</span></span>

### <span data-ttu-id="3031c-135">프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="3031c-135">Create the provisioning package</span></span> 

1. <span data-ttu-id="3031c-136">Windows 구성 디자이너 열기:</span><span class="sxs-lookup"><span data-stu-id="3031c-136">Open Windows Configuration Designer:</span></span>
   - <span data-ttu-id="3031c-137">시작 화면 또는 시작 메뉴 검색에서 'Windows 구성 디자이너'를 입력하고 Windows 구성 디자이너 바로 가기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-137">From either the Start screen or Start menu search, type 'Windows Configuration Designer' and click on the Windows Configuration Designer shortcut,</span></span> 
    
     <span data-ttu-id="3031c-138">또는</span><span class="sxs-lookup"><span data-stu-id="3031c-138">or</span></span>
    
   - <span data-ttu-id="3031c-139">ADK에서 Windows 구성 디자이너를 설치한 경우 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`(x64 컴퓨터) 또는 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`(x86 컴퓨터)로 이동하여 **ICD.exe**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-139">If you installed Windows Configuration Designer from the ADK, navigate to `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (on an x64 computer) or `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (on an x86 computer), and then double-click **ICD.exe**.</span></span>

2. <span data-ttu-id="3031c-140">**Surface Hub 장치 프로비전**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-140">Click **Provision Surface Hub devices**.</span></span>

3. <span data-ttu-id="3031c-141">프로젝트 이름을 지정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-141">Name your project and click **Next**.</span></span>

### <span data-ttu-id="3031c-142">설정 구성</span><span class="sxs-lookup"><span data-stu-id="3031c-142">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="3031c-143">인증서를 사용하여 디바이스를 프로비전하려면 <strong>인증서 추가</strong>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-143">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="3031c-144">인증서 이름을 입력하고 사용할 인증서를 찾아서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-144">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br><span data-ttu-id="3031c-145">프록시 설정에서 <strong>예</strong> 또는 <strong>아니오</strong>를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-145">Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings.</span></span> <span data-ttu-id="3031c-146">Surface Hub 기본 구성은 자동으로 프록시 설정을 검색하도록 설정되어 있습니다. 이를 원하지 않는 경우 <strong>아니오</strong>를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-146">The default configuration for Surface Hub is to automatically detect proxy settings, so you can select <strong>No</strong> if that is the setting that you want.</span></span> <span data-ttu-id="3031c-147">단, 기존에 프록시 서버가 요구되었다가 프록시 서버를 요구하지 않도록 변경된 인프라의 경우 프로비저닝 패키지를 사용하여 <strong>예s</strong>를 선택하고 <strong>설정 자동 검색</strong>을 선택하여 Surface Hub 장치를 기본 설정으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-147">However, if your infrastructure previously required using a proxy server and has changed to not require a proxy server, you can use a provisioning package to revert your Surface Hub devices to the default settings by selecting <strong>Yes</strong> and <strong>Automatically detect settings</strong>.</span></span> </br></br><span data-ttu-id="3031c-148"><strong>예</strong>를 선택하면 자동으로 프록시 설정을 검색하거나 초기 설정 스크립트에 URL 또는 고정 프록시 서버 주소를 입력해 수동으로 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-148">If you toggle <strong>Yes</strong>, you can select to automatically detect proxy settings, or you can manually configure the settings by entering a URL to a setup script, or a static proxy server address.</span></span> <span data-ttu-id="3031c-149">또한 로컬 주소에 프록시 서버를 사용할지 여부를 선택하고 제외(Surface Hub에서 프록시 서버 없이 직접 연결해야 하는 주소)를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-149">You can also identify whether to use the proxy server for local addresses, and enter exceptions (addresses that Surface Hub should connect to directly without using the proxy server).</span></span>  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br><span data-ttu-id="3031c-150">Active Directory에 장치를 등록하고 설정 앱을 사용할 보안 그룹을 지정할 수 있으며 전역 관리자가 설정 앱을 사용할 수 있도록 Azure Active Directory에 등록하거나 장치에 로컬 관리자 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-150">You can enroll the device in Active Directory and specify a security group to use the Settings app, enroll in Azure Active Directory to allow global admins to use the Settings app, or create a local administrator account on the device.</span></span></br></br><span data-ttu-id="3031c-151">Active Directory에 장치를 등록하려면 권한이 가장 낮은 사용자 계정의 자격 증명을 입력하여 장치를 도메인에 추가하고 Surface Hub에서 관리자 자격 증명을 보유할 보안 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-151">To enroll the device in Active Directory, enter the credentials for a least-privileged user account to join the device to the domain, and specify the security group to have admin credentials on Surface Hub.</span></span> <span data-ttu-id="3031c-152">Active Directory에 장치를 등록한 프로비저닝 패키지를 초기화된 Surface Hub에 적용하는 경우, 동일한 도메인 계정을 사용하려면 해당 계정이 도메인 관리자로 등록되어 있거나 최초로 Surface Hub을 설정할 때 사용했던 계정이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-152">If a provisioning package that enrolls a device in Active Directory is going to be applied to a Surface Hub that was reset, the same domain account can only be used if the account listed is a domain administrator or is the same account that set up the Surface Hub initially.</span></span> <span data-ttu-id="3031c-153">그렇지 않은 경우 프로비저닝 패키지에 다른 도메인의 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-153">Otherwise, a different domain account must be used in the provisioning package.</span></span></br></br><span data-ttu-id="3031c-154">Windows 구성 디자이너 마법사를 사용하여 대량 Azure AD 등록을 구성하려면 먼저 <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">조직에서 Azure AD 가입을 설정</a>합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="3031c-155">Azure AD 테넌트의 <strong>사용자당 최대 장치 수</strong>는 마법사에서 얻은 대량 토큰을 사용할 수 있는 횟수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="3031c-156">Azure AD에 디바이스를 등록하려면 해당 옵션을 선택하고 마법사를 사용하여 가져올 대량 토큰의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="3031c-157">토큰의 만료 날짜를 설정합니다(토큰을 가져온 날로부터 최대 30일).</span><span class="sxs-lookup"><span data-stu-id="3031c-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="3031c-158"><strong>대량 토큰 가져오기</strong>를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-158">Click <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="3031c-159"><strong>S에 로그인&#39;허용 창에서 장치를 </strong> Azure AD에 참가 시킬 수 있는 권한이 있는 계정을 입력 한 다음 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="3031c-160"><strong>수락</strong>을 클릭하여 Windows 구성 디자이너에 필요한 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-160">Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span></br></br><span data-ttu-id="3031c-161">로컬 관리자 계정을 만들려면 해당 옵션을 선택하고 사용자 이름 및 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-161">To create a local administrator account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="3031c-162">중요:</strong> 프로비전 패키지에서 로컬 계정을 생성하는 경우 42일마다 <strong>설정</strong> 앱을 사용하여 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-162">Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="3031c-163">기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-163">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br><span data-ttu-id="3031c-164">MDM 등록 설정에서 <strong>예</strong> 또는 <strong>아니오</strong>를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-164">Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM.</span></span> </br></br><span data-ttu-id="3031c-165"><strong>예</strong>를 선택한 경우 장치 등록에 사용할 수 있는 승인된 서비스 계정과 암호 또는 인증서 손도장을 제공해야 하며, 인증 유형 또한 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-165">If you toggle <strong>Yes</strong>, you must provide a service account and password or certificate thumbprint that is authorized to enroll the device, and also specify the authentication type.</span></span> <span data-ttu-id="3031c-166">또한 MDM 제공자가 요구하는 경우 검색 서비스, 등록 서비스, 정책 서비스의 URL을 함께 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-166">If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service.</span></span> <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)"><span data-ttu-id="3031c-167">MDM을 사용한 Surface Hub 관리에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-167">Learn more about managing Surface Hub with MDM.</span></span></a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br><span data-ttu-id="3031c-168">단일 프로비저닝 패키지로 다수의 UWP(유니버설 Windows 플랫폼)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-168">You can install multiple Universal Windows Platform (UWP) apps in a provisioning package.</span></span> <span data-ttu-id="3031c-169">설정에 대한 도움말은 <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">앱을 사용하여 PC 프로비전</a>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-169">For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>.</span></span> </br></br><strong><span data-ttu-id="3031c-170">중요: </strong> 마법사 인터페이스를 통해 클래식 Win32 앱을 선택할 수 있지만 Surface Hub에 적용 되는 프로비저닝 패키지에는 UWP 앱만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-170">Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub.</span></span> <span data-ttu-id="3031c-171">클래식 Win32 앱을 포함하면 프로비저닝을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-171">If you include a Classic Win32 app, provisioning will fail.</span></span> </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br><span data-ttu-id="3031c-172">이 단계에서는&#39;t 설정을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-172">You don&#39;t configure any settings in this step.</span></span> <span data-ttu-id="3031c-173">장치 계정 목록을 포함된 구성 파일을 비롯한 지침을 제공하빈다.</span><span class="sxs-lookup"><span data-stu-id="3031c-173">It provides instructions for including a configuration file that contains a list of device accounts.</span></span> <span data-ttu-id="3031c-174">구성 파일은 열 머리글을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-174">The configuration file must not contain column headers.</span></span> <span data-ttu-id="3031c-175">프로비저닝 패키지를 Surface Hub에 적용할 때 Surface Hub 구성 파일이 USB 드라이브에 포함된 경우, 파일에서 장치에 사용할 계정과 식별 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-175">When you apply the provisioning package to Surface Hub, if a Surface Hub configuration file is included on the USB drive, you can select the account and friendly name for the device from the file.</span></span> <span data-ttu-id="3031c-176">예시는 <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">샘플 구성 파일</a>을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-176">See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</span></span></br></br><strong><span data-ttu-id="3031c-177">중요: </strong> 구성 파일은 OOBE (최신 설치 환경) 중에만 적용할 수 있으며 windows 10, 버전 1703에서 릴리스된 Windows 구성 디자이너를 사용 하 여 만든 프로비저닝 패키지만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-177">Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.</span></span>  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br><span data-ttu-id="3031c-178">프로비전 패키지를 보호하기 위한 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-178">You can set a password to protect your provisioning package.</span></span> <span data-ttu-id="3031c-179">디바이스에 프로비전 패키지를 적용할 때 이 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-179">You must enter this password when you apply the provisioning package to a device.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="3031c-180">작업을 마쳤으면 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-180">After you're done, click **Create**.</span></span> <span data-ttu-id="3031c-181">몇 초 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-181">It only takes a few seconds.</span></span> <span data-ttu-id="3031c-182">패키지가 빌드되면 패키지가 저장된 위치가 페이지 맨 위에 하이퍼링크로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-182">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

## <span data-ttu-id="3031c-183">샘플 구성 파일</span><span class="sxs-lookup"><span data-stu-id="3031c-183">Sample configuration file</span></span>

<span data-ttu-id="3031c-184">Surface Hub 구성 파일에는 장치에서 Exchange 및 비즈니스용 Skype에 연결할 때 사용할 수 있는 계정 목록을 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-184">A Surface Hub configuration file contains a list of device accounts that your device can use to connect to Exchange and Skype for Business.</span></span> <span data-ttu-id="3031c-185">Surface Hub에 프로비저닝 패키지를 적용할 때 USB 플래시 드라이브의 루트 디렉터리에 구성 파일을 저장한 다음 장치에 적용할 계정을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-185">When you apply a provisioning package to Surface Hub, you can include a configuration file in the root directory of the USB flash drive, and then select the desired account to apply to that device.</span></span> <span data-ttu-id="3031c-186">구성 파일은 OOBE(최초 설정)에만 적용되며 Windows 10 버전 1703과 함께 릴리스된 Windows 구성 디자이너를 사용해 만든 프로비저닝 패키지만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-186">The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.</span></span>

<span data-ttu-id="3031c-187">Microsoft Excel 또는 다른 CSV 편집 소프트웨어를 사용해 파일명이 `SurfaceHubConfiguration.csv`인 CSV 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-187">Use Microsoft Excel or other CSV editor to create a CSV file named `SurfaceHubConfiguration.csv`.</span></span> <span data-ttu-id="3031c-188">파일 안에 다음 형식으로 장치 계정 및 식별 이름 목록을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-188">In the file, enter a list of device accounts and friendly names in this format:</span></span>

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
><span data-ttu-id="3031c-189">구성 파일에서는 장치 계정의 암호가 일반 텍스트로 저장되기 때문에 프로비저닝 패키지를 장치에 적용한 후 암호를 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-189">Because the configuration file stores the device account passwords in plaintext, we recommend that you update the passwords after you've applied the provisioning package to your devices.</span></span> <span data-ttu-id="3031c-190">[Surface Hub CSP(구성 서비스 제공자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp)의 [DeviceAccount 노드](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount)를 사용해 MDM에서 암호를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-190">You can use the [DeviceAccount node](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) in the [Surface Hub configuration service provider (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) to update the passwords via MDM.</span></span>


<span data-ttu-id="3031c-191">다음은 `SurfaceHubConfiguration.csv`를 사용한 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-191">The following is an example of `SurfaceHubConfiguration.csv`.</span></span> 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## <span data-ttu-id="3031c-192">고급 프로비저닝 사용</span><span class="sxs-lookup"><span data-stu-id="3031c-192">Use advanced provisioning</span></span>

<span data-ttu-id="3031c-193">[Windows 구성 디자이너를 설치](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)한 다음 이를 사용해 프로비저닝 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-193">After you [install Windows Configuration Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), you can create a provisioning package.</span></span>

### <span data-ttu-id="3031c-194">프로비저닝 패키지 만들기(고급)</span><span class="sxs-lookup"><span data-stu-id="3031c-194">Create the provisioning package (advanced)</span></span>

1. <span data-ttu-id="3031c-195">Windows 구성 디자이너 열기:</span><span class="sxs-lookup"><span data-stu-id="3031c-195">Open Windows Configuration Designer:</span></span>
   - <span data-ttu-id="3031c-196">시작 화면 또는 시작 메뉴 검색에서 'Windows 구성 디자이너'를 입력하고 Windows 구성 디자이너 바로 가기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-196">From either the Start screen or Start menu search, type 'Windows Configuration Designer' and click on the Windows Configuration Designer shortcut,</span></span> 
    
     <span data-ttu-id="3031c-197">또는</span><span class="sxs-lookup"><span data-stu-id="3031c-197">or</span></span>
    
   - <span data-ttu-id="3031c-198">ADK에서 Windows 구성 디자이너를 설치한 경우 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`(x64 컴퓨터) 또는 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`(x86 컴퓨터)로 이동하여 **ICD.exe**를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-198">If you installed Windows Configuration Designer from the ADK, navigate to `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (on an x64 computer) or `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (on an x86 computer), and then double-click **ICD.exe**.</span></span>

2. <span data-ttu-id="3031c-199">**Advanced provisioning**(고급 프로비전)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-199">Click **Advanced provisioning**.</span></span>
   
3. <span data-ttu-id="3031c-200">프로젝트 이름을 지정하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-200">Name your project and click **Next**.</span></span>

4. <span data-ttu-id="3031c-201">**Windows 10 팀에 공통**을 선택 하 고 **다음**을 클릭 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-201">Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.</span></span>

    ![ICD 새 프로젝트](images/icd-new-project.png)

5. <span data-ttu-id="3031c-203">프로젝트의 **사용 가능한 사용자 지정**에서 **일반 팀 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-203">In the project, under **Available customizations**, select **Common Team settings**.</span></span>

    ![ICD 공통 설정](images/icd-common-settings.png)


### <span data-ttu-id="3031c-205">패키지에 인증서 추가</span><span class="sxs-lookup"><span data-stu-id="3031c-205">Add a certificate to your package</span></span>
<span data-ttu-id="3031c-206">프로비저닝 패키지를 사용하여 디바이스가 Microsoft Exchange에 인증할 수 있는 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-206">You can use provisioning packages to install certificates that will allow the device to authenticate to Microsoft Exchange.</span></span>

> [!NOTE]
> <span data-ttu-id="3031c-207">프로비저닝 패키지를 사용할 경우 디바이스(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있고 사용자 저장소에는 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-207">Provisioning packages can only install certificates to the device (local machine) store, and not to the user store.</span></span> <span data-ttu-id="3031c-208">조직에서 사용자 저장소에 인증서를 설치하도록 요구하는 경우 MDM(모바일 디바이스 관리) 솔루션을 사용하여 해당 인증서를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-208">If your organization requires that certificates must be installed to the user store, use Mobile Device Management (MDM) to deploy these certificates.</span></span> <span data-ttu-id="3031c-209">자세한 내용은 MDM 솔루션 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-209">See your MDM solution documentation for details.</span></span>

1. <span data-ttu-id="3031c-210">**사용 가능한 사용자 지정** 창에서 **런타임 설정** > **인증서** > **ClientCertificates**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-210">In the **Available customizations** pane, go to **Runtime settings** > **Certificates** > **ClientCertificates**.</span></span> 

2. <span data-ttu-id="3031c-211">**CertificateName**을 입력한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-211">Enter a **CertificateName** and then click **Add**.</span></span> 

2. <span data-ttu-id="3031c-212">**CertificatePassword**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-212">Enter the **CertificatePassword**.</span></span> 

3. <span data-ttu-id="3031c-213">**CertificatePath**의 경우 인증서를 찾아보고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-213">For **CertificatePath**, browse and select the certificate.</span></span> 

4. <span data-ttu-id="3031c-214">**ExportCertificate**를 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-214">Set **ExportCertificate** to **False**.</span></span>

5. <span data-ttu-id="3031c-215">**KeyLocation**의 경우 **소프트웨어만**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-215">For **KeyLocation**, select **Software only**.</span></span>


### <span data-ttu-id="3031c-216">패키지에 UWP(유니버설 Windows 플랫폼) 앱 추가</span><span class="sxs-lookup"><span data-stu-id="3031c-216">Add a Universal Windows Platform (UWP) app to your package</span></span>
<span data-ttu-id="3031c-217">UWP 앱을 프로비저닝 패키지에 추가하기 전에 앱 패키지(.appx 또는 .appxbundle)와 임의 종속성 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-217">Before adding a UWP app to a provisioning package, you need the app package (either an .appx, or .appxbundle) and any dependency files.</span></span> <span data-ttu-id="3031c-218">비즈니스용 Microsoft Store에서 앱을 구매한 경우 *인코드되지 않은* 앱 라이선스도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-218">If you acquired the app from the Microsoft Store for Business, you will also need the *unencoded* app license.</span></span> <span data-ttu-id="3031c-219">비즈니스용 Microsoft Store에서 이러한 항목을 다운로드하는 방법에 대한 자세한 내용은 [오프라인 앱 배포](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-219">See [Distribute offline apps](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) to learn how to download these items from the Microsoft Store for Business.</span></span>

1. <span data-ttu-id="3031c-220">**사용 가능한 사용자 지정** 창에서 **런타임 설정** > **UniversalAppInstall** > **DeviceContextApp**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-220">In the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextApp**.</span></span>

2. <span data-ttu-id="3031c-221">앱의 **PackageFamilyName**을 입력하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-221">Enter a **PackageFamilyName** for the app and then click **Add**.</span></span> <span data-ttu-id="3031c-222">일관성을 위해 앱의 패키지 패밀리 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-222">For consistency, use the app's package family name.</span></span> <span data-ttu-id="3031c-223">비즈니스용 Microsoft Store에서 앱을 구매한 경우 앱 라이선스에서 패키지 패밀리 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-223">If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license.</span></span> <span data-ttu-id="3031c-224">텍스트 편집기를 사용 하 여 라이선스 파일을 열고 \<PFM\> ... 태그 사이의 값을 사용 합니다. \</PFM\></span><span class="sxs-lookup"><span data-stu-id="3031c-224">Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.</span></span>

3. <span data-ttu-id="3031c-225">**ApplicationFile**의 경우 **찾아보기**를 클릭하여 대상 앱(\*.appx 또는 \*.appxbundle)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-225">For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).</span></span>

4. <span data-ttu-id="3031c-226">**DependencyAppxFiles**의 경우 **찾아보기**를 클릭하여 앱에 대한 종속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-226">For **DependencyAppxFiles**, click **Browse** to find and add any dependencies for the app.</span></span> <span data-ttu-id="3031c-227">Surface Hub에는 이러한 종속성의 64비트 버전만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-227">For Surface Hub, you will only need the x64 versions of these dependencies.</span></span>

<span data-ttu-id="3031c-228">비즈니스용 Microsoft Store에서 앱을 구매한 경우 앱 라이선스를 프로비저닝 패키지에도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-228">If you acquired the app from the Microsoft Store for Business, you will also need to add the app license to your provisioning package.</span></span>

1. <span data-ttu-id="3031c-229">앱 라이선스의 복사본을 만들고 **.ms-windows-store-license** 확장명을 사용하도록 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-229">Make a copy of the app license, and rename it to use a **.ms-windows-store-license** extension.</span></span> <span data-ttu-id="3031c-230">예를 들면 "example.xml" becomes "example.ms-windows-store-license"입니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-230">For example, "example.xml" becomes "example.ms-windows-store-license".</span></span>

2. <span data-ttu-id="3031c-231">ICD의 **사용 가능한 사용자 지정** 창에서 **런타임 설정** > **UniversalAppInstall** > **DeviceContextAppLicense**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-231">In ICD, in the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextAppLicense**.</span></span>

3. <span data-ttu-id="3031c-232">**LicenseProductId**를 입력한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-232">Enter a **LicenseProductId** and then click **Add**.</span></span> <span data-ttu-id="3031c-233">일관성을 위해 앱 라이선스에 있는 앱의 라이선스 ID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-233">For consistency, use the app's license ID from the app license.</span></span> <span data-ttu-id="3031c-234">텍스트 편집기를 사용하여 라이선스 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-234">Open the license file using a text editor.</span></span> <span data-ttu-id="3031c-235">그런 다음 태그에서 \<License\> **LicenseID** 특성의 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-235">Then, in the \<License\> tag, use the value in the **LicenseID** attribute.</span></span>

4. <span data-ttu-id="3031c-236">새 **LicenseProductId** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-236">Select the new **LicenseProductId** node.</span></span> <span data-ttu-id="3031c-237">**LicenseInstall**의 경우 **찾아보기**를 클릭하여 1단계에서 이름을 바꾼 라이선스 파일을 찾고 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-237">For **LicenseInstall**, click **Browse** to find and select the license file that you renamed in Step 1.</span></span>


### <span data-ttu-id="3031c-238">패키지에 정책 추가</span><span class="sxs-lookup"><span data-stu-id="3031c-238">Add a policy to your package</span></span>
<span data-ttu-id="3031c-239">Surface Hub에서는 [정책 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)의 정책 하위 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-239">Surface Hub supports a subset of the policies in the [Policy configuration service provider](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx).</span></span> <span data-ttu-id="3031c-240">해당 정책 중 일부는 ICD를 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-240">Some of those policies can be configured with ICD.</span></span>

1. <span data-ttu-id="3031c-241">**사용 가능한 사용자 지정** 창에서 **런타임 설정** > **Policies**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-241">In the **Available customizations** pane, go to **Runtime settings** > **Policies**.</span></span>

2. <span data-ttu-id="3031c-242">사용 가능한 정책 영역 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-242">Select one of the available policy areas.</span></span>

3. <span data-ttu-id="3031c-243">프로비저닝 패키지에 추가할 정책을 선택하고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-243">Select and set the policy you want to add to your provisioning package.</span></span>


### <span data-ttu-id="3031c-244">패키지에 Surface Hub 설정 추가</span><span class="sxs-lookup"><span data-stu-id="3031c-244">Add Surface Hub settings to your package</span></span> 

<span data-ttu-id="3031c-245">[SurfaceHub 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)의 설정을 프로비저닝 패키지에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-245">You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package.</span></span> 

1. <span data-ttu-id="3031c-246">**사용 가능한 사용자 지정** 창에서 **런타임 설정** > **WindowsTeamSettings**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-246">In the **Available customizations** pane, go to **Runtime settings** > **WindowsTeamSettings**.</span></span>

2. <span data-ttu-id="3031c-247">사용 가능한 설정 영역 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-247">Select one of the available setting areas.</span></span>

3. <span data-ttu-id="3031c-248">프로비저닝 패키지에 추가할 설정을 선택하고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-248">Select and set the setting you want to add to your provisioning package.</span></span> 


## <span data-ttu-id="3031c-249">패키지 빌드</span><span class="sxs-lookup"><span data-stu-id="3031c-249">Build your package</span></span>

1. <span data-ttu-id="3031c-250">프로비저닝 패키지 구성을 완료한 경우 **파일** 메뉴에서 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-250">When you are done configuring the provisioning package, on the **File** menu, click **Save**.</span></span>

2. <span data-ttu-id="3031c-251">프로젝트 파일에 중요한 정보가 포함될 수 있다는 경고를 읽고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-251">Read the warning that project files may contain sensitive information, and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3031c-252">프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-252">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="3031c-253">.ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-253">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="3031c-254">안전한 장소에 프로젝트 파일을 저장하고 더 이상 필요하지 않은 경우에는 프로젝트 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-254">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

3. <span data-ttu-id="3031c-255">**내보내기** 메뉴에서 **프로비저닝 패키지**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-255">On the **Export** menu, click **Provisioning package**.</span></span>

4. <span data-ttu-id="3031c-256">**소유자**를 **IT 관리자**로 변경합니다. 이렇게 하면 이 프로비저닝 패키지의 우선 순위가 다른 소스에서 이 디바이스에 적용된 프로비저닝 패키지보다 더 높게 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-256">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span>

5. <span data-ttu-id="3031c-257">**패키지 버전**에 대한 값을 설정하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-257">Set a value for **Package Version**, and then select **Next.**</span></span>

    > [!TIP]
    > <span data-ttu-id="3031c-258">기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-258">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

6. <span data-ttu-id="3031c-259">선택 사항: 패키지 암호화 및 패키지 서명 사용을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-259">Optional: You can choose to encrypt the package and enable package signing.</span></span>

    -   <span data-ttu-id="3031c-260">**패키지 암호화 사용** - 이 옵션을 선택하는 경우 자동 생성된 암호가 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-260">**Enable package encryption** - If you select this option, an auto-generated password will be shown on the screen.</span></span>

    -   <span data-ttu-id="3031c-261">**패키지 서명 사용** - 이 옵션을 선택하는 경우 패키지 서명에 사용할 유효한 인증서를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-261">**Enable package signing** - If you select this option, you must select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="3031c-262">**찾아보기...** 를 클릭하고 패키지에 서명하는 데 사용할 인증서를 선택하여 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-262">You can specify the certificate by clicking **Browse...** and choosing the certificate you want to use to sign the package.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="3031c-263">프로비저닝 패키지에 신뢰할 수 있는 프로비저닝 인증서를 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-263">We recommend that you include a trusted provisioning certificate in your provisioning package.</span></span> <span data-ttu-id="3031c-264">패키지를 장치에 적용하면 인증서가 시스템 저장소에 추가되고 그 후에 해당 인증서로 서명된 모든 패키지는 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-264">When the package is applied to a device, the certificate is added to the system store and any package signed with that certificate thereafter can be applied silently.</span></span> 

7. <span data-ttu-id="3031c-265">**다음**을 클릭하여 빌드가 끝난 프로비저닝 패키지를 저장할 출력 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-265">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="3031c-266">기본적으로 Windows ICD에서는 프로젝트 폴더를 출력 위치로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-266">By default, Windows ICD uses the project folder as the output location.</span></span><p>
<span data-ttu-id="3031c-267">필요한 경우 **찾아보기**를 클릭하여 기본 출력 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-267">Optionally, you can click **Browse** to change the default output location.</span></span>

8. <span data-ttu-id="3031c-268">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-268">Click **Next**.</span></span>

9. <span data-ttu-id="3031c-269">패키지 빌드를 시작하려면 **빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-269">Click **Build** to start building the package.</span></span> <span data-ttu-id="3031c-270">빌드 페이지에서 프로젝트 정보가 표시되며 진행률 표시줄은 빌드 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-270">The project information is displayed in the build page and the progress bar indicates the build status.</span></span><p>
<span data-ttu-id="3031c-271">빌드를 취소해야 하는 경우 **취소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-271">If you need to cancel the build, click **Cancel**.</span></span> <span data-ttu-id="3031c-272">이렇게 하면 현재 빌드 프로세스를 취소하며 마법사를 닫고 **사용자 지정 페이지**를 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-272">This cancels the current build process, closes the wizard, and takes you back to the **Customizations Page**.</span></span>

10. <span data-ttu-id="3031c-273">빌드에 실패하면 프로젝트 폴더에 대한 링크가 포함된 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-273">If your build fails, an error message will show up that includes a link to the project folder.</span></span> <span data-ttu-id="3031c-274">오류 원인을 파악하기 위해 로그를 스캔할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-274">You can scan the logs to determine what caused the error.</span></span> <span data-ttu-id="3031c-275">문제를 해결 한 후에 패키지를 다시 빌드 해보세요.</span><span class="sxs-lookup"><span data-stu-id="3031c-275">Once you fix the issue, try building the package again.</span></span><p>
<span data-ttu-id="3031c-276">빌드가 성공한 경우 프로비저닝 패키지, 출력 디렉터리 및 프로젝트 디렉터리의 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-276">If your build is successful, the name of the provisioning package, output directory, and project directory will be shown.</span></span>

    -   <span data-ttu-id="3031c-277">원하는 경우 프로비저닝 패키지를 다시 빌드하고 출력 패키지 경로를 다르게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-277">If you choose, you can build the provisioning package again and pick a different path for the output package.</span></span> <span data-ttu-id="3031c-278">이렇게 하려면 **뒤로**를 클릭해서 출력 패키지 이름과 경로를 바꾼 다음 **다음**을 클릭해 다른 빌드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-278">To do this, click **Back** to change the output package name and path, and then click **Next** to start another build.</span></span>
    
    -   <span data-ttu-id="3031c-279">완료되면 **마침**을 클릭해 마법사를 닫고 다시 **사용자 지정 페이지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-279">If you are done, click **Finish** to close the wizard and go back to the **Customizations Page**.</span></span>

11. <span data-ttu-id="3031c-280">**출력 위치** 링크를 선택하여 패키지 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-280">Select the **output location** link to go to the location of the package.</span></span> <span data-ttu-id="3031c-281">.ppkg를 빈 USB 플래시 드라이브에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-281">Copy the .ppkg to an empty USB flash drive.</span></span>


## <span data-ttu-id="3031c-282">Surface Hub에 프로비저닝 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="3031c-282">Apply a provisioning package to Surface Hub</span></span>

<span data-ttu-id="3031c-283">Surface Hub에 프로비저닝 패키지를 배포할 수 있는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-283">There are two options for deploying provisioning packages to a Surface Hub.</span></span> <span data-ttu-id="3031c-284">[첫 번째 실행 마법사](#apply-a-provisioning-package-during-first-run)에서는 인증서를 설치 하는 프로비저닝 패키지를 적용 하거나, 첫 실행 프로그램이 완료 된 후 [설정을](#apply-a-package-using-settings)사용 하 여 설정, 앱, 인증서를 구성 하는 프로비저닝 패키지를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-284">[During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings).</span></span> 


### <span data-ttu-id="3031c-285">첫 실행 중에 프로비저닝 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="3031c-285">Apply a provisioning package during first run</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3031c-286">첫 번째 실행 프로그램 중에는 프로비저닝 패키지만 사용 하 여 인증서를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-286">During the first-run program, you can only use provisioning packages to install certificates.</span></span> <span data-ttu-id="3031c-287">**설정** 앱을 사용하여 앱을 설치하고 다른 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-287">Use the **Settings** app to install apps and apply other settings.</span></span>

1. <span data-ttu-id="3031c-288">처음으로 Surface Hub를 켜면 첫 실행 프로그램에서 [**안녕하세요 페이지**](first-run-program-surface-hub.md#first-page)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-288">When you turn on the Surface Hub for the first time, the first-run program will display the [**Hi there page**](first-run-program-surface-hub.md#first-page).</span></span> <span data-ttu-id="3031c-289">계속하기 전에 설정이 제대로 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-289">Make sure that the settings are properly configured before proceeding.</span></span>

2. <span data-ttu-id="3031c-290">.ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-290">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span> <span data-ttu-id="3031c-291">패키지가 드라이브의 루트 디렉터리에 있으면 첫 실행 프로그램이 이를 인식하고 디바이스를 설정할지 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-291">If the package is in the root directory of the drive, the first-run program will recognize it and ask if you want to set up the device.</span></span> <span data-ttu-id="3031c-292">**설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-292">Select **Set up**.</span></span>

    ![디바이스를 설정하시겠습니까?](images/provisioningpackageoobe-01.png)

3. <span data-ttu-id="3031c-294">다음 화면에서 프로비전 소스를 선택하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-294">The next screen asks you to select a provisioning source.</span></span> <span data-ttu-id="3031c-295">**이동식 미디어** 탭을 선택하고 **다음**을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-295">Select **Removable Media** and tap **Next**.</span></span>

    ![이 디바이스를 프로비전](images/provisioningpackageoobe-02.png)
    
4. <span data-ttu-id="3031c-297">적용할 프로비저닝 패키지(\*.ppkg)를 선택하고 **다음**을 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-297">Select the provisioning package (\*.ppkg) that you want to apply, and tap **Next**.</span></span> <span data-ttu-id="3031c-298">첫 실행  중에는 패키지 한 개만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-298">Note that you can only install one package during first run.</span></span>

    ![패키지 선택](images/provisioningpackageoobe-03.png)

5. <span data-ttu-id="3031c-300">첫 실행 프로그램은 프로비저닝 패키지가 적용될 변경 내용의 요약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-300">The first-run program will show you a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="3031c-301">**예, 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-301">Select **Yes, add it**.</span></span>  

    ![이 패키지를 신뢰할 수 있습니까?](images/provisioningpackageoobe-04.png)
    
6. <span data-ttu-id="3031c-303">구성 파일이 USB 플래시 드라이브의 루트 디렉터리에 저장된 경우 **구성 선택** 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-303">If a configuration file is included in the root directory of the USB flash drive, you will see **Select a configuration**.</span></span> <span data-ttu-id="3031c-304">구성 파일의 첫 장치 계정과 Surface Hub에 적용될 해당 계정의 정보 요약이 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-304">The first device account in the configuration file will be shown with a summary of the account information that will be applied to the Surface Hub.</span></span>

    ![구성 선택](images/ppkg-config.png)    

7. <span data-ttu-id="3031c-306">**구성 선택**에서 적용할 장치 이름을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-306">In **Select a configuration**, select the device name to apply, and then click **Next**.</span></span>

    ![장치 식별 이름 선택](images/ppkg-csv.png)
    
<span data-ttu-id="3031c-308">프로비저닝 패키지의 설정이 장치에 적용되고 OOBE 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-308">The settings from the provisioning package will be applied to the device and OOBE will be complete.</span></span> <span data-ttu-id="3031c-309">장치를 다시 시작하면 USB 플래시 드라이브를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-309">After the device restarts, you can remove the USB flash drive.</span></span>

### <span data-ttu-id="3031c-310">설정을 사용하여 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="3031c-310">Apply a package using Settings</span></span>

1. <span data-ttu-id="3031c-311">.ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-311">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span>

2. <span data-ttu-id="3031c-312">Surface Hub에서 **설정**을 시작하고 메시지가 표시되면 관리자 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-312">From the Surface Hub, start **Settings** and enter the admin credentials when prompted.</span></span>

3. <span data-ttu-id="3031c-313">**Surface Hub** > **장치 관리**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-313">Navigate to **Surface Hub** > **Device management**.</span></span> <span data-ttu-id="3031c-314">**프로비저닝 패키지**에서 **프로비저닝 패키지 추가 또는 제거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-314">Under **Provisioning packages**, select **Add or remove a provisioning package**.</span></span>

4. <span data-ttu-id="3031c-315">**패키지 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-315">Select **Add a package**.</span></span>

5. <span data-ttu-id="3031c-316">프로비저닝 패키지를 선택하고 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-316">Choose your provisioning package and select **Add**.</span></span> <span data-ttu-id="3031c-317">메시지가 표시되면 관리자 자격 증명을 다시 입력해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-317">You may have to re-enter the admin credentials if prompted.</span></span>

6. <span data-ttu-id="3031c-318">프로비저닝 패키지가 적용될 변경 내용의 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-318">You'll see a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="3031c-319">**예, 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3031c-319">Select **Yes, add it**.</span></span>


