---
title: SEMM (Surface)을 사용 하 여 Surface 장치 등록 및 구성
description: Surface uefi의 설정을 제어 하는 Surface UEFI 구성 패키지를 만드는 방법과 surface 디바이스를 SEMM에 등록 하는 방법에 대해 알아봅니다.
keywords: surface enterprise 관리
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835951"
---
# <span data-ttu-id="1de8d-104">SEMM을 사용하여 Surface 장치 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="1de8d-104">Enroll and configure Surface devices with SEMM</span></span>

<span data-ttu-id="1de8d-105">Microsoft Surface Enterprise 관리 모드 (SEMM)를 사용 하 여 surface device의 Surface UEFI 설정을 안전 하 게 구성 하 고 조직의 Surface 장치에서 해당 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-105">With Microsoft Surface Enterprise Management Mode (SEMM), you can securely configure the settings of Surface UEFI on a Surface device and manage those settings on Surface devices in your organization.</span></span> <span data-ttu-id="1de8d-106">Surface 디바이스를 SEMM로 관리 하는 경우 해당 디바이스를 *등록* 하는 것으로 간주 됩니다 (활성화 됨이 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="1de8d-106">When a Surface device is managed by SEMM, that device is considered to be *enrolled* (sometimes referred to as activated).</span></span> <span data-ttu-id="1de8d-107">이 문서에서는 Surface UEFI의 설정을 제어 하는 데만 사용할 수 있는 Surface UEFI 구성 패키지를 만드는 방법에 대해 설명 하 고, Surface 디바이스를 SEMM에도 등록 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-107">This article shows you how to create a Surface UEFI configuration package that will not only control the settings of Surface UEFI, but will also enroll a Surface device in SEMM.</span></span>

<span data-ttu-id="1de8d-108">SEMM에 대 한 더 높은 수준의 개요는 [Microsoft Surface Enterprise 관리 모드](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1de8d-108">For a more high-level overview of SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="1de8d-109">Surface Pro 7의 클라우드에서 펌웨어를 관리 하는 효율적인 방법으로 이제 공개 미리 보기를 통해 surface Pro X 및 Surface 랩톱 3을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-109">A streamlined method of managing firmware from the cloud on Surface Pro 7,Surface Pro X and Surface Laptop 3 is now available via public preview.</span></span> <span data-ttu-id="1de8d-110">자세한 내용은 [SURFACE UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1de8d-110">For more information,refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1de8d-111">SEMM은 UEFI 관리자를 통해 Surface Pro X에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-111">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="1de8d-112">자세한 내용은 [Surface Pro X 배포, 관리 및 서비스](surface-pro-arm-app-management.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1de8d-112">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

#### <span data-ttu-id="1de8d-113">Microsoft Surface UEFI 구성자 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="1de8d-113">Download and install Microsoft Surface UEFI Configurator</span></span>
<span data-ttu-id="1de8d-114">SEMM 패키지를 만드는 데 사용 되는 도구는 Microsoft Surface UEFI 구성자입니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-114">The tool used to create SEMM packages is Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="1de8d-115">Microsoft Surface UEFI Configurator를 다운로드 센터의 IT 페이지의 [Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-115">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>
<span data-ttu-id="1de8d-116">Microsoft Surface UEFI Configurator Windows Installer (.msi) 파일을 실행 하 여 도구의 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-116">Run the Microsoft Surface UEFI Configurator Windows Installer (.msi) file to start the installation of the tool.</span></span> <span data-ttu-id="1de8d-117">설치 관리자가 완료 되 면 시작 메뉴의 모든 앱 섹션에서 Microsoft Surface UEFI 구성자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-117">When the installer completes, find Microsoft Surface UEFI Configurator in the All Apps section of your Start menu.</span></span>

>[!NOTE]
><span data-ttu-id="1de8d-118">Microsoft Surface UEFI 구성자는 Windows 10 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-118">Microsoft Surface UEFI Configurator is supported only on Windows 10.</span></span>

## <span data-ttu-id="1de8d-119">Surface UEFI 구성 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1de8d-119">Create a Surface UEFI configuration package</span></span>

<span data-ttu-id="1de8d-120">Surface UEFI 구성 패키지는 SEMM으로 관리 되는 surface 장치에 Surface UEFI 설정의 새 구성을 적용 하는 역할을 모두 수행 하 고, SEMM의 Surface 디바이스를 등록 하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-120">The Surface UEFI configuration package performs both the role of applying a new configuration of Surface UEFI settings to a Surface device managed with SEMM and the role of enrolling Surface devices in SEMM.</span></span> <span data-ttu-id="1de8d-121">구성 패키지를 만들려면 각 Surface 디바이스에서 UEFI 설정의 구성을 보호 하기 위해 SEMM와 함께 서명 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-121">The creation of a configuration package requires you to have a signing certificate to be used with SEMM to secure the configuration of UEFI settings on each Surface device.</span></span> <span data-ttu-id="1de8d-122">SEMM 인증서의 요구 사항에 대 한 자세한 내용은 [Microsoft Surface Enterprise 관리 모드](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1de8d-122">For more information about the requirements for the SEMM certificate, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="1de8d-123">Surface UEFI 구성 패키지를 만들려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-123">To create a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="1de8d-124">시작 메뉴에서 Microsoft Surface UEFI 구성자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-124">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="1de8d-125">**시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-125">Click **Start**.</span></span>
3. <span data-ttu-id="1de8d-126">그림 1에 표시 된 대로 **구성 패키지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-126">Click **Configuration Package**, as shown in Figure 1.</span></span>

   ![SEMM 등록 패키지 만들기](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *<span data-ttu-id="1de8d-128">그림 1.</span><span class="sxs-lookup"><span data-stu-id="1de8d-128">Figure 1.</span></span> <span data-ttu-id="1de8d-129">구성 패키지를 선택 하 여 SEMM 등록 및 구성에 대 한 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-129">Select Configuration Package to create a package for SEMM enrollment and configuration</span></span>*

4. <span data-ttu-id="1de8d-130">그림 2와 같이 개인 키 (.pfx)를 사용 하 여 내보낸 인증서 파일을 추가 하려면 **인증서 보호** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-130">Click **Certificate Protection** to add your exported certificate file with private key (.pfx), as shown in Figure 2.</span></span> <span data-ttu-id="1de8d-131">인증서 파일의 위치로 이동 하 여 파일을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-131">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![SEM certificate 및 Surface UEFI 암호를 구성 패키지에 추가](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *<span data-ttu-id="1de8d-133">그림 2.</span><span class="sxs-lookup"><span data-stu-id="1de8d-133">Figure 2.</span></span> <span data-ttu-id="1de8d-134">Surface UEFI 구성 패키지에 SEMM 인증서 및 Surface UEFI 암호 추가</span><span class="sxs-lookup"><span data-stu-id="1de8d-134">Add the SEMM certificate and Surface UEFI password to a Surface UEFI configuration package</span></span>*

5. <span data-ttu-id="1de8d-135">인증서 암호를 확인 하 라는 메시지가 나타나면 인증서 파일에 대 한 암호를 입력 하 고 확인 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-135">When you are prompted to confirm the certificate password, enter and confirm the password for your certificate file, and then click **OK**.</span></span>
6. <span data-ttu-id="1de8d-136">**암호 보호** 를 클릭 하 여 Surface UEFI에 암호를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-136">Click **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="1de8d-137">UEFI로 부팅할 때마다이 암호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-137">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="1de8d-138">이 암호를 입력 하지 않으면 **PC 정보**, **정보**, **엔터프라이즈 관리**및 **종료** 페이지만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-138">If this password is not entered, only the **PC information**, **About**, **Enterprise management**, and **Exit** pages will be displayed.</span></span> <span data-ttu-id="1de8d-139">이것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-139">This step is optional.</span></span>
7. <span data-ttu-id="1de8d-140">메시지가 표시 되 면 Surface UEFI에 대해 선택한 암호를 입력 하 고 확인 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-140">When you are prompted, enter and confirm your chosen password for Surface UEFI, and then click **OK**.</span></span> <span data-ttu-id="1de8d-141">기존 Surface UEFI 암호를 지우려면 암호 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-141">If you want to clear an existing Surface UEFI password, leave the password field blank.</span></span>
8. <span data-ttu-id="1de8d-142">Surface UEFI 패키지를 특정 장치에 적용 하지 않으려면 **대상으로 지정할 표면 유형 선택** 페이지에서 해당 surface Book 또는 Surface Pro 4 이미지 아래에 있는 슬라이더를 클릭 하 여 **해당 위치에 놓습니다.**</span><span class="sxs-lookup"><span data-stu-id="1de8d-142">If you do not want the Surface UEFI package to apply to a particular device, on the **Choose which Surface type you want to target** page, click the slider beneath the corresponding Surface Book or Surface Pro 4 image so that it is in the **Off** position.</span></span> <span data-ttu-id="1de8d-143">(그림 3에 표시 된 것과 같습니다.)</span><span class="sxs-lookup"><span data-stu-id="1de8d-143">(As shown in Figure 3.)</span></span>
   > [!NOTE] 
   > <span data-ttu-id="1de8d-144">기본적으로 선택 되어 있지 않은 장치를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-144">You must select a device as none are selected by default.</span></span>

   ![패키지 호환성 장치 선택](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *<span data-ttu-id="1de8d-146">그림 3.</span><span class="sxs-lookup"><span data-stu-id="1de8d-146">Figure 3.</span></span> <span data-ttu-id="1de8d-147">패키지 호환성 장치 선택</span><span class="sxs-lookup"><span data-stu-id="1de8d-147">Choose the devices for package compatibility</span></span>*

9. <span data-ttu-id="1de8d-148">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-148">Click **Next**.</span></span>
10. <span data-ttu-id="1de8d-149">관리 되는 Surface 디바이스에서 구성 요소를 비활성화 하려면 **활성화할 구성 요소 선택** 페이지에서 비활성화할 장치 또는 장치 그룹 옆에 있는 슬라이더를 클릭 하 여 슬라이더가 **꺼짐** 위치에 오도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-149">If you want to deactivate a component on managed Surface devices, on the **Choose which components you want to activate or deactivate** page, click the slider next to any device or group of devices you want to deactivate so that the slider is in the **Off** position.</span></span> <span data-ttu-id="1de8d-150">(그림 4에 표시 됩니다.) 각 장치에 대 한 기본 구성은 **켜져**있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-150">(Shown in Figure 4.) The default configuration for each device is **On**.</span></span> <span data-ttu-id="1de8d-151">모든 슬라이더를 기본 위치로 되돌리려면 **원래 대로** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-151">Click the **Reset** button if you want to return all sliders to the default position.</span></span>

    ![Surface 구성 요소를 사용 하지 않거나 사용 하도록 설정](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *<span data-ttu-id="1de8d-153">그림 4.</span><span class="sxs-lookup"><span data-stu-id="1de8d-153">Figure 4.</span></span> <span data-ttu-id="1de8d-154">개별 Surface 구성 요소 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1de8d-154">Disable or enable individual Surface components</span></span>*

11. <span data-ttu-id="1de8d-155">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-155">Click **Next**.</span></span>
12. <span data-ttu-id="1de8d-156">Surface UEFI의 고급 옵션을 사용 하거나 사용 하지 않도록 설정 하거나 Surface UEFI 페이지를 표시 하려면 **장치에 대 한 고급 설정 선택** 페이지에서 원하는 설정 옆에 있는 슬라이더를 클릭 하 여 해당 옵션을 **on** 또는 **Off** 로 구성 합니다 (그림 5에 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="1de8d-156">To enable or disable advanced options in Surface UEFI or the display of Surface UEFI pages, on the **Choose the advanced settings for your devices** page, click the slider beside the desired setting to configure that option to **On** or **Off** (shown in Figure 5).</span></span> <span data-ttu-id="1de8d-157">**Uefi 프론트 페이지** 섹션에서 **보안**, **장치**, **부팅** 슬라이더를 사용 하 여 Surface UEFI로 부팅 하는 사용자가 사용할 수 있는 페이지를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-157">In the **UEFI Front Page** section, you can use the sliders for **Security**, **Devices**, and **Boot** to control what pages are available to users who boot into Surface UEFI.</span></span> <span data-ttu-id="1de8d-158">Surface UEFI 설정에 대 한 자세한 내용은 [SURFACE uefi 설정 관리](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)를 참조 하세요. 패키지를 생성 하 고 저장 하는 옵션을 선택 했으면 **빌드** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-158">(For more information about Surface UEFI settings, see [Manage Surface UEFI settings](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Click **Build** when you have finished selecting options to generate and save the package.</span></span>

    ![고급 표면 UEFI 설정 및 Surface UEFI 페이지 제어](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *<span data-ttu-id="1de8d-160">그림 5.</span><span class="sxs-lookup"><span data-stu-id="1de8d-160">Figure 5.</span></span> <span data-ttu-id="1de8d-161">고급 표면 UEFI 설정 및 Surface UEFI 페이지 (SEMM 사용) 제어</span><span class="sxs-lookup"><span data-stu-id="1de8d-161">Control advanced Surface UEFI settings and Surface UEFI pages with SEMM</span></span>*

13. <span data-ttu-id="1de8d-162">다른 이름 **으로 저장** 대화 상자에서 Surface UEFI 구성 패키지의 이름을 지정 하 고 파일을 저장할 위치로 이동한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-162">In the **Save As** dialog box, specify a name for the Surface UEFI configuration package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
14. <span data-ttu-id="1de8d-163">패키지를 만들고 저장 하면 **성공** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-163">When the package is created and saved, the **Successful** page is displayed.</span></span>

>[!NOTE]
><span data-ttu-id="1de8d-164">그림 6과 같이이 페이지에 표시 되는 인증서 지문 문자를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-164">Record the certificate thumbprint characters that are displayed on this page, as shown in Figure 6.</span></span> <span data-ttu-id="1de8d-165">이 문자는 새 Surface 디바이스의 등록을 확인 하는 데 필요 합니다 (SEMM).</span><span class="sxs-lookup"><span data-stu-id="1de8d-165">You will need these characters to confirm enrollment of new Surface devices in SEMM.</span></span> <span data-ttu-id="1de8d-166">**끝내기** 를 클릭 하 여 패키지 만들기를 완료 하 고 MICROSOFT Surface UEFI 구성자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-166">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

![인증서 지문 문자 표시](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*<span data-ttu-id="1de8d-168">그림 6.</span><span class="sxs-lookup"><span data-stu-id="1de8d-168">Figure 6.</span></span> <span data-ttu-id="1de8d-169">인증서 손도장의 마지막 두 문자가 성공한 페이지에 표시 됨</span><span class="sxs-lookup"><span data-stu-id="1de8d-169">The last two characters of the certificate thumbprint are displayed on the Successful page</span></span>*

<span data-ttu-id="1de8d-170">이제 Surface UEFI 구성 패키지를 만들었으므로 Surface 디바이스를 등록 하거나 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-170">Now that you have created your Surface UEFI configuration package, you can enroll or configure Surface devices.</span></span>

>[!NOTE]
><span data-ttu-id="1de8d-171">Surface UEFI 구성 패키지가 만들어지면 바탕 화면에 구성 패키지 설정 및 옵션에 대 한 세부 정보가 포함 된 로그 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-171">When a Surface UEFI configuration package is created, a log file is created on the desktop with details of the configuration package settings and options.</span></span>

## <span data-ttu-id="1de8d-172">Surface device를 SEMM로 등록</span><span class="sxs-lookup"><span data-stu-id="1de8d-172">Enroll a Surface device in SEMM</span></span>
<span data-ttu-id="1de8d-173">Surface UEFI 구성 패키지가 실행 되 면 SEMM 인증서 및 Surface UEFI 구성 파일은 Surface 디바이스의 펌웨어 저장소에 준비 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-173">When the Surface UEFI configuration package is executed, the SEMM certificate and Surface UEFI configuration files are staged in the firmware storage of the Surface device.</span></span> <span data-ttu-id="1de8d-174">Surface 장치를 다시 부팅 하면 Surface UEFI는 이러한 파일을 처리 하 고 그림 7과 같이 surface UEFI 구성을 적용 하거나 Surface device를 등록 하는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-174">When the Surface device reboots, Surface UEFI processes these files and begins the process of applying the Surface UEFI configuration or enrolling the Surface device in SEMM, as shown in Figure 7.</span></span>

![Surface UEFI 또는 등록을 구성 하기 위한 SEMM 프로세스](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*<span data-ttu-id="1de8d-176">그림 7.</span><span class="sxs-lookup"><span data-stu-id="1de8d-176">Figure 7.</span></span> <span data-ttu-id="1de8d-177">Surface UEFI 또는 Surface device의 등록 구성에 대 한 SEMM 프로세스</span><span class="sxs-lookup"><span data-stu-id="1de8d-177">The SEMM process for configuration of Surface UEFI or enrollment of a Surface device</span></span>*

<span data-ttu-id="1de8d-178">Surface device를 SEMM에 등록 하기 위한 프로세스를 시작 하기 전에 먼저 인증서 손도장의 마지막 두 문자를 보유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-178">Before you begin the process to enroll a Surface device in SEMM, ensure that you have the last two characters of the certificate thumbprint on hand.</span></span> <span data-ttu-id="1de8d-179">디바이스의 등록을 확인 하는 데 다음 문자가 필요 합니다 (그림 6 참조).</span><span class="sxs-lookup"><span data-stu-id="1de8d-179">You will need these characters to confirm the device’s enrollment (see Figure 6).</span></span>

<span data-ttu-id="1de8d-180">Surface UEFI 구성 패키지를 사용 하 여 Surface device를 SEMM에 등록 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-180">To enroll a Surface device in SEMM with a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="1de8d-181">등록 하려는 Surface 장치에서 Surface UEFI 구성 패키지 .msi 파일을 SEMM에 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-181">Run the Surface UEFI configuration package .msi file on the Surface device you want to enroll in SEMM.</span></span> <span data-ttu-id="1de8d-182">이는 디바이스의 펌웨어에 Surface UEFI 구성 파일을 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-182">This will provision the Surface UEFI configuration file in the device’s firmware.</span></span>
2. <span data-ttu-id="1de8d-183">**사용권 계약에 동의** 확인란을 선택 하 여 EULA (최종 사용자 사용권 계약)를 수락 하 고 **설치** 를 클릭 하 여 설치 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-183">Select the **I accept the terms in the License Agreement** check box to accept the End User License Agreement (EULA), and then click **Install** to begin the installation process.</span></span>
3. <span data-ttu-id="1de8d-184">**마침을** 클릭 하 여 surface UEFI 구성 패키지 설치를 완료 하 고 메시지가 표시 되 면 surface 장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-184">Click **Finish** to complete the Surface UEFI configuration package installation and restart the Surface device when you are prompted to do so.</span></span>
4. <span data-ttu-id="1de8d-185">Surface UEFI는 구성 파일을 로드 하 고 디바이스에서 SEMM이 활성화 되지 않은 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-185">Surface UEFI will load the configuration file and determine that SEMM is not enabled on the device.</span></span> <span data-ttu-id="1de8d-186">Surface UEFI는 다음과 같이 SEMM 등록 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-186">Surface UEFI will then begin the SEMM enrollment process, as follows:</span></span>
   * <span data-ttu-id="1de8d-187">Surface UEFI는 SEMM 구성 파일에 SEMM 인증서가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-187">Surface UEFI will verify that the SEMM configuration file contains a SEMM certificate.</span></span>
   * <span data-ttu-id="1de8d-188">Surface UEFI는 그림 8과 같이 Surface 디바이스의 등록을 확인 하기 위해 인증서 손도장의 마지막 두 문자를 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-188">Surface UEFI will prompt you to enter the last two characters of the certificate thumbprint to confirm enrollment of the Surface device in SEMM, as shown in Figure 8.</span></span>

      ![SEMM 등록에는 인증서 손도장의 마지막 두 문자가 필요 합니다.](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *<span data-ttu-id="1de8d-190">그림 8.</span><span class="sxs-lookup"><span data-stu-id="1de8d-190">Figure 8.</span></span> <span data-ttu-id="1de8d-191">SEMM의 등록에는 인증서 손도장의 마지막 두 문자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-191">Enrollment in SEMM requires the last two characters of the certificate thumbprint</span></span>*

   * <span data-ttu-id="1de8d-192">Surface UEFI는 펌웨어에 SEMM 인증서를 저장 하 고 Surface UEFI 구성 파일에 지정 된 구성 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-192">Surface UEFI will store the SEMM certificate in firmware and apply the configuration settings that are specified in the Surface UEFI configuration file.</span></span>
   
5. <span data-ttu-id="1de8d-193">Surface 디바이스는 이제 SEMM에 등록 되어 있으며 Windows로 부팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-193">The Surface device is now enrolled in SEMM and will boot to Windows.</span></span>

<span data-ttu-id="1de8d-194">화면 장치가 **프로그램 및 기능** (그림 9에 표시 된 대로) 또는 **Microsoft surface UEFI 구성자** 로그에 저장 되어 있는 이벤트 (그림 10의 이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 에 있음 **)에서 성공적** 으로 등록 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-194">You can verify that a Surface device has been successfully enrolled in SEMM by looking for **Microsoft Surface Configuration Package** in **Programs and Features** (as shown in Figure 9), or in the events stored in the **Microsoft Surface UEFI Configurator** log, found under **Applications and Services Logs** in Event Viewer (as shown in Figure 10).</span></span>

![프로그램 및 기능에서 Surface device의 등록 확인 (SEMM)](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*<span data-ttu-id="1de8d-196">그림 9.</span><span class="sxs-lookup"><span data-stu-id="1de8d-196">Figure 9.</span></span> <span data-ttu-id="1de8d-197">프로그램 및 기능에서 Surface device 등록 확인 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="1de8d-197">Verify the enrollment of a Surface device in SEMM in Programs and Features</span></span>*

![이벤트 뷰어에서 SEMM의 Surface device 등록 확인](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*<span data-ttu-id="1de8d-199">그림 10.</span><span class="sxs-lookup"><span data-stu-id="1de8d-199">Figure 10.</span></span> <span data-ttu-id="1de8d-200">이벤트 뷰어에서 SEMM의 Surface 장치 등록 확인</span><span class="sxs-lookup"><span data-stu-id="1de8d-200">Verify the enrollment of a Surface device in SEMM in Event Viewer</span></span>*

<span data-ttu-id="1de8d-201">디바이스를 Surface UEFI의 SEMM에 등록 했는지 확인할 수도 있습니다. 디바이스를 등록 하는 동안 Surface UEFI에는 **엔터프라이즈 관리** 페이지가 포함 됩니다 (그림 11 참조).</span><span class="sxs-lookup"><span data-stu-id="1de8d-201">You can also verify that the device is enrolled in SEMM in Surface UEFI – while the device is enrolled, Surface UEFI will contain the **Enterprise management** page (as shown in Figure 11).</span></span>

![Surface UEFI 엔터프라이즈 관리 페이지](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*<span data-ttu-id="1de8d-203">그림 11.</span><span class="sxs-lookup"><span data-stu-id="1de8d-203">Figure 11.</span></span> <span data-ttu-id="1de8d-204">Surface UEFI Enterprise 관리 페이지</span><span class="sxs-lookup"><span data-stu-id="1de8d-204">The Surface UEFI Enterprise management page</span></span>*


## <span data-ttu-id="1de8d-205">SEMM을 사용 하 여 Surface UEFI 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1de8d-205">Configure Surface UEFI settings with SEMM</span></span>

<span data-ttu-id="1de8d-206">디바이스가 SEMM에 등록 되 면 동일한 SEMM 인증서로 서명 된 Surface UEFI 구성 패키지를 실행 하 여 새 Surface UEFI 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-206">After a device is enrolled in SEMM, you can run Surface UEFI configuration packages signed with the same SEMM certificate to apply new Surface UEFI settings.</span></span> <span data-ttu-id="1de8d-207">이러한 설정은 사용자가 개입할 필요 없이 다음에 장치가 부팅 될 때 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-207">These settings are applied automatically the next time the device boots, without any interaction from the user.</span></span> <span data-ttu-id="1de8d-208">Microsoft 끝점 구성 관리자와 같은 응용 프로그램 배포 솔루션을 사용 하 여 surface 장치에 surface UEFI 구성 패키지를 배포 하 여 surface UEFI의 설정을 변경 하거나 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-208">You can use application deployment solutions like Microsoft Endpoint Configuration Manager to deploy Surface UEFI configuration packages to Surface devices to change or manage the settings in Surface UEFI.</span></span>

<span data-ttu-id="1de8d-209">구성 관리자를 사용 하 여 Windows Installer (.msi) 파일을 배포 하는 방법에 대 한 자세한 내용은 [Microsoft Endpoint Configuration Manager를 사용 하 여 응용 프로그램 배포 및 관리](https://technet.microsoft.com/library/mt627959)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1de8d-209">For more information about how to deploy Windows Installer (.msi) files with Configuration Manager, see [Deploy and manage applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).</span></span>

<span data-ttu-id="1de8d-210">암호를 사용 하 여 Surface UEFI를 보호 하는 경우 Surface UEFI로 부팅 하려고 시도 하는 암호 없이는 **PC 정보**, **엔터프라이즈 관리**및 해당 **사용자에 게**표시 되는 **종료** 페이지만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-210">If you have secured Surface UEFI with a password, users without the password who attempt to boot to Surface UEFI will only have the **PC information**, **About**, **Enterprise management**, and **Exit** pages displayed to them.</span></span>

<span data-ttu-id="1de8d-211">암호를 사용 하 여 Surface UEFI 보안을 설정 하지 않은 경우 또는 사용자가 암호를 올바르게 입력 하는 경우 SEMM을 사용 하 여 구성한 설정이 흐리게 표시 되 고 (사용할 수 없음) 조직에서 관리 하는 일부 설정이 페이지 위쪽에 표시 됩니다 (그림 12).</span><span class="sxs-lookup"><span data-stu-id="1de8d-211">If you have not secured Surface UEFI with a password or a user enters the password correctly, settings that are configured with SEMM will be dimmed (unavailable) and the text Some settings are managed by your organization will be displayed at the top of the page, as shown in Figure 12.</span></span>

![Surface UEFI에서 SEMM을 사용 하 여 관리 되는 설정](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*<span data-ttu-id="1de8d-213">그림 12.</span><span class="sxs-lookup"><span data-stu-id="1de8d-213">Figure 12.</span></span> <span data-ttu-id="1de8d-214">SEMM로 관리 되는 설정은 Surface UEFI에서 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de8d-214">Settings managed by SEMM will be disabled in Surface UEFI</span></span>*
