---
title: Microsoft Endpoint Configuration Manager를 사용 하 여 SEMM (Surface)을 사용 하 여 장치 관리
description: 끝점 구성 관리자를 사용 하 여 Microsoft Surface Enterprise 관리 모드 (SEMM)를 관리 하는 방법에 대해 알아봅니다.
keywords: 등록, 업데이트, 스크립트, 설정
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 2d31f520d8c4da54f47b2b89b58b43e2cb983f1a
ms.sourcegitcommit: 7f5b97275fe301ef700f9c77954a1054e2e8d046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145619"
---
# <span data-ttu-id="75d0e-104">Microsoft Endpoint Configuration Manager를 사용하여 SEMM에서 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="75d0e-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="75d0e-105">Surface UEFI 장치의 Microsoft Surface Enterprise 관리 모드 (SEMM) 기능을 통해 관리자는 Surface UEFI 설정의 구성을 관리 하 고 보안을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="75d0e-106">대부분의 조직에서는 Microsoft Surface UEFI 구성자 도구를 사용 하 여 Windows Installer (.msi) 패키지를 만들어이 프로세스를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="75d0e-107">그런 다음 해당 패키지를 클라이언트 화면 장치에 실행 하거나 배포 하 여 디바이스를 SEMM에 등록 하 고 Surface UEFI 설정 구성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="75d0e-108">Microsoft Endpoint Configuration Manager를 사용 하는 조직의 경우 Microsoft Surface UEFI Configurator 프로세스를 사용 하 여 SEMM을 배포 하 고 관리 하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="75d0e-109">Microsoft Surface UEFI 관리자는 디바이스에서 SEMM 관리를 사용할 수 있는 필수 어셈블리를 만드는 간단한 설치 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="75d0e-110">관리 되는 클라이언트에 Microsoft Surface UEFI Manager를 사용 하 여 이러한 어셈블리를 설치 하면 PowerShell 스크립트를 사용 하 여 구성 관리자가 SEMM을 관리 하 고 응용 프로그램으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="75d0e-111">이 프로세스를 사용 하 여 구성 관리자에서 SEMM 관리를 수행 하므로 외부 Microsoft Surface UEFI 구성자 도구가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="75d0e-112">이 문서에서 설명 하는 프로세스는 이전 버전의 끝점 구성 관리자나 다른 타사 관리 솔루션과 함께 사용할 수 있지만, Microsoft Surface UEFI 관리자와 PowerShell의 관리는 끝점 구성 관리자의 현재 분기 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <span data-ttu-id="75d0e-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="75d0e-113">Prerequisites</span></span>

<span data-ttu-id="75d0e-114">이 문서에서 설명 하는 프로세스를 시작 하기 전에 다음 기술과 도구에 대해 숙지 하세요.</span><span class="sxs-lookup"><span data-stu-id="75d0e-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="75d0e-115">Surface UEFI</span><span class="sxs-lookup"><span data-stu-id="75d0e-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="75d0e-116">Surface 엔터프라이즈 관리 모드(SEMM)</span><span class="sxs-lookup"><span data-stu-id="75d0e-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="75d0e-117">PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="75d0e-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="75d0e-118">System Center Configuration Manager 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="75d0e-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="75d0e-119">인증서 관리</span><span class="sxs-lookup"><span data-stu-id="75d0e-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="75d0e-120">또한, 사용 하려는 인증서에 대 한 액세스 권한이 필요 합니다 (SEMM).</span><span class="sxs-lookup"><span data-stu-id="75d0e-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="75d0e-121">이 인증서에 대 한 요구 사항에 대 한 자세한 내용은 [Surface 엔터프라이즈 관리 모드 인증서 요구 사항을](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75d0e-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="75d0e-122">이 인증서는 안전한 위치에 보관 하 고 제대로 백업 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="75d0e-123">이 인증서가 손실 되거나 사용할 수 없게 되 면 Surface UEFI를 다시 설정 하거나, 관리 되는 표면 UEFI 설정을 변경 하거나, 등록 된 Surface 장치에서 SEMM을 제거 하는 것이 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="75d0e-124">Microsoft Surface UEFI 관리자 다운로드</span><span class="sxs-lookup"><span data-stu-id="75d0e-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="75d0e-125">Configuration Manager에서 SEMM을 관리 하려면 각 클라이언트 화면 장치에 Microsoft Surface UEFI 관리자를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="75d0e-126">Microsoft 다운로드 센터의 [IT 페이지에 대 한 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 MICROSOFT Surface UEFI 관리자 (SurfaceUEFIManager.msi)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="75d0e-127">Configuration Manager에 대 한 SEMM 스크립트 다운로드</span><span class="sxs-lookup"><span data-stu-id="75d0e-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="75d0e-128">Microsoft Surface UEFI 관리자가 클라이언트 화면 장치에 설치 된 후에는 PowerShell 스크립트를 사용 하 여 배포 및 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="75d0e-129">다운로드 센터에서 [Semm 관리 스크립트](https://www.microsoft.com/download/details.aspx?id=46703) 의 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <span data-ttu-id="75d0e-130">Microsoft Surface UEFI 관리자 배포</span><span class="sxs-lookup"><span data-stu-id="75d0e-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="75d0e-131">Microsoft Surface UEFI 관리자의 배포는 일반적인 응용 프로그램 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="75d0e-132">Microsoft Surface UEFI 관리자 설치 관리자 파일은 [표준 자동 옵션](https://msdn.microsoft.com/library/windows/desktop/aa367988)을 사용 하 여 설치할 수 있는 표준 Windows installer 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="75d0e-133">Microsoft Surface UEFI 관리자를 설치 하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="75d0e-134">Microsoft Surface UEFI 관리자를 제거 하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="75d0e-135">새 응용 프로그램을 만들고 Surface 장치를 포함 하는 컬렉션에 배포 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="75d0e-136">**시작** 화면이 나 **시작** 메뉴에서 Configuration Manager 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="75d0e-137">창의 왼쪽 아래 모서리에 있는 **소프트웨어 라이브러리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="75d0e-138">소프트웨어 라이브러리의 **응용 프로그램 관리** 노드를 확장 한 다음 **응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="75d0e-139">창 위쪽의 **홈** 탭에서 **응용 프로그램 만들기** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="75d0e-140">그러면 응용 프로그램 만들기 마법사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="75d0e-141">응용 프로그램 만들기 마법사는 일련의 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="75d0e-142">**일반** – **이 응용 프로그램에 대 한 정보를 자동으로 설치 파일에서 검색** 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="75d0e-143">**형식** 필드에서 **Windows Installer (.msi 파일)** 도 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="75d0e-144">**찾아보기를** 선택 하 여 이동 하 고 **SurfaceUEFIManagerSetup.msi**를 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="75d0e-145">SurfaceUEFIManagerSetup.msi의 위치는 네트워크 공유에 있어야 하며 다른 파일을 포함 하지 않는 폴더에 위치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="75d0e-146">로컬 파일 위치를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="75d0e-147">**정보 가져오기** -응용 프로그램 만들기 마법사가 .msi 파일을 구문 분석 하 고 **응용 프로그램 이름** 및 **제품 코드**를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="75d0e-148">그림 1에 나와 있는 것 처럼, SurfaceUEFIManagerSetup.msi는 라인 **컨텐트 파일**아래에 유일한 파일로 나열 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="75d0e-149">계속 하려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-149">Select **Next** to proceed.</span></span>

      ![Surface UEFI 관리자 설정의 정보는 자동으로 구문 분석 됩니다.](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="75d0e-151">그림 1.</span><span class="sxs-lookup"><span data-stu-id="75d0e-151">Figure 1.</span></span> <span data-ttu-id="75d0e-152">Microsoft Surface UEFI Manager 설치 프로그램의 정보가 자동으로 구문 분석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="75d0e-153">**일반 정보** -응용 프로그램의 이름 및 게시자 및 버전에 대 한 정보를 수정 하거나이 페이지에서 메모를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="75d0e-154">Microsoft Surface UEFI 관리자의 설치 명령이 설치 프로그램 필드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="75d0e-155">시스템 설치의 기본 설치 동작을 통해 사용자가 Surface device에 로그온 되어 있지 않은 경우에도 Microsoft Surface UEFI 관리자가 SEMM에 필요한 어셈블리를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="75d0e-156">계속 하려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="75d0e-157">**요약** - **정보 가져오기** 단계에서 구문 분석 되 고 **일반 정보** 단계의 선택 내용이이 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="75d0e-158">선택을 확인 하 고 응용 프로그램을 만들려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="75d0e-159">**진행률** -응용 프로그램을 가져와 소프트웨어 라이브러리에 추가할 때 진행률 표시줄과 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="75d0e-160">**완료** – 응용 프로그램 만들기 프로세스가 완료 되 면 성공적인 응용 프로그램 만들기에 대 한 확인이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="75d0e-161">**닫기를** 선택 하 여 응용 프로그램 만들기 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="75d0e-162">구성 관리자에서 응용 프로그램을 만든 후 배포 지점에 배포 하 고 Surface 장치를 포함 하 여 컬렉션에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="75d0e-163">이 응용 프로그램은 Surface device에서 설치 하거나 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="75d0e-164">이는 SEMM에 필요한 어셈블리만 PowerShell 스크립트를 사용 하 여 사용 하도록 하는 데만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="75d0e-165">SEMM로 관리 되지 않는 장치에 Microsoft Surface UEFI 관리자 어셈블리를 설치 하지 않으려는 경우 Microsoft Surface UEFI 관리자를 SEMM 구성 관리자 스크립트의 종속성으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="75d0e-166">이 시나리오는이 문서의 뒷부분에 나오는 [SEMM 구성 관리자 스크립트](#deploy-semm-configuration-manager-scripts) 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <span data-ttu-id="75d0e-167">SEMM 구성 관리자 스크립트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="75d0e-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="75d0e-168">장치에 필요한 어셈블리가 설치 된 후에는 SEMM에 디바이스를 등록 하 고 Surface UEFI를 구성 하는 프로세스는 PowerShell 스크립트를 사용 하 여 수행 하 고 구성 관리자를 사용 하 여 스크립트 응용 프로그램으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="75d0e-169">이러한 스크립트는 조직과 환경의 필요에 맞게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="75d0e-170">예를 들어 다양 한 부서나 역할에 관리 되는 Surface 디바이스에 대 한 여러 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="75d0e-171">이 문서의 시작 부분에 있는 [필수 구성 요소](#prerequisites) 섹션의 링크에서 semm 및 Configuration Manager 스크립트의 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="75d0e-172">구성 관리자를 사용 하 여 SEMM 배포를 수행 하는 데 필요한 두 가지 주요 스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="75d0e-173">**ConfigureSEMM.ps1** –이 스크립트를 사용 하 여 surface device에 대해 지정 된 설정을 적용 하 고, 디바이스를 semm에 등록 하 고, 디바이스의 등록을 식별 하는 데 사용 되는 레지스트리 키를 semm로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="75d0e-174">**ResetSEMM.ps1** –이 스크립트를 사용 하 여 surface DEVICE에서 semm을 초기화 하 고, semm에서 등록을 취소 하 고, surface UEFI 설정에 대 한 컨트롤을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="75d0e-175">예제 스크립트에는 Surface UEFI 설정을 설정 하는 방법과 이러한 설정에 대 한 사용 권한을 제어 하는 방법에 대 한 예제가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="75d0e-176">이러한 설정을 수정 하 여 Surface UEFI를 보호 하 고 환경의 필요에 따라 Surface UEFI 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="75d0e-177">이 문서의 다음 섹션에서는 ConfigureSEMM.ps1 스크립트에 대해 설명 하 고 요구 사항에 맞게 스크립트에 대해 수행 해야 하는 수정 사항을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="75d0e-178">SEMM 구성 관리자 스크립트와 내보낸 SEMM 인증서 파일 (.pfx)은 다른 파일이 없는 동일한 폴더에 배치 해야 Configuration Manager에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <span data-ttu-id="75d0e-179">인증서 및 패키지 이름 지정</span><span class="sxs-lookup"><span data-stu-id="75d0e-179">Specify certificate and package names</span></span>

<span data-ttu-id="75d0e-180">수정 해야 하는 스크립트의 첫 번째 영역은 SEMM 인증서를 지정 하 고 로드 하는 부분으로, SurfaceUEFIManager 버전 및 SEMM 구성 패키지 및 SEMM 설정 패키지의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="75d0e-181">인증서 이름 및 SurfaceUEFIManager 버전은 ConfigureSEMM.ps1 스크립트의 56 ~ 73 줄에 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="75d0e-182">**$CertName** 변수의 **FabrikamSEMMSample** 값을 58 줄의 semm 인증서 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="75d0e-183">이 스크립트는 스크립트가 있는 폴더에 작업 디렉터리 (명명 된 Config)를 만든 다음이 작업 디렉토리에 인증서 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="75d0e-184">소유자 패키지 및 재설정 패키지도 구성 디렉터리에 만들어지고,이 스크립트에서 생성 된 Surface UEFI 설정 및 사용 권한에 대 한 구성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="75d0e-185">73 줄에서 **$password** 변수의 값을 **1234** 에서 인증서 파일의 암호로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="75d0e-186">암호가 필요 하지 않은 경우 **1234** 텍스트를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="75d0e-187">인증서 손도장의 마지막 두 문자는 디바이스를 SEMM에 등록 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="75d0e-188">이 스크립트는 사용자에 게 이러한 자리 숫자를 표시 하 여, 시스템을 다시 부팅 하기 전에 사용자 또는 기술자에 게 해당 숫자를 기록 하 여 장치를 SEMM에 등록할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="75d0e-189">이 스크립트는 150-155 줄에 있는 다음 코드를 사용 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

인증서 파일 (.pfx)에 대 한 액세스 권한이 있는 관리자는 CertMgr에서 .pfx 파일을 열어 언제 든 지 지문을 읽을 수 있습니다. <span data-ttu-id="75d0e-191">CertMgr를 사용 하 여 지문을 보려면 다음 프로세스를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="75d0e-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="75d0e-192">.Pfx 파일을 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="75d0e-193">탐색 창에서 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="75d0e-194">**인증서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="75d0e-195">기본 창에서 인증서를 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="75d0e-196">**세부 정보** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="75d0e-197">**표시** 드롭다운 메뉴에서 **모두** 또는 **속성만** 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="75d0e-198">필드 **지문을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="75d0e-199">구성 관리자가 제거 작업을 사용 하 여 디바이스에서 SEMM을 제거 하도록 설정 하려면 ResetSEMM.ps1 스크립트의이 섹션에 SEMM 인증서 이름과 암호를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <span data-ttu-id="75d0e-200">사용 권한 구성</span><span class="sxs-lookup"><span data-stu-id="75d0e-200">Configure permissions</span></span>

<span data-ttu-id="75d0e-201">Surface UEFI에 대 한 구성을 지정할 스크립트의 첫 번째 영역은 **사용 권한 구성** 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="75d0e-202">이 지역은 sample 스크립트의 210 줄에서 시작 하 여 **사용 권한을 구성** 하 고 계속 해 서 247 줄까지 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="75d0e-203">다음 코드 조각에서는 먼저 모든 Surface UEFI 설정에 대 한 사용 권한을 설정 하 여 해당 사용자가 SEMM에 의해서만 수정할 수 있도록 하 고, 로컬 사용자가 Surface UEFI 암호, TPM, 프론트 및 후면 카메라를 수정할 수 있도록 하는 명시적 권한을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="75d0e-204">각 **$uefiV 2** 변수는 이름 또는 ID를 설정 하 여 Surface UEFI 설정을 식별 하 고 다음 값 중 하나로 사용 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="75d0e-205">**$ownerOnly** –이 설정을 수정할 수 있는 권한은 semm에만 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="75d0e-206">**$ownerAndLocalUser** –이 설정을 수정할 수 있는 권한은 물론, Surface UEFI에 대 한 로컬 사용자 부팅 및 semm에 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="75d0e-207">이 문서의 [설정 이름 및 id](#settings-names-and-ids) 섹션에서 Surface UEFI에 대해 사용 가능한 설정 이름 및 id에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <span data-ttu-id="75d0e-208">설정 구성</span><span class="sxs-lookup"><span data-stu-id="75d0e-208">Configure settings</span></span>

<span data-ttu-id="75d0e-209">Surface UEFI에 대 한 구성을 지정할 스크립트의 두 번째 영역은 각 설정을 사용할지 여부를 구성 하는 ConfigureSEMM.ps1 스크립트의 설정 영역을 **구성** 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="75d0e-210">샘플 스크립트에는 모든 설정을 기본값으로 설정 하는 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="75d0e-211">그런 다음 스크립트는 PXE 부팅에 IPv6을 사용 하지 않도록 설정 하 고 Surface UEFI 관리자 암호를 변경 하지 않고 유지 하는 명시적인 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="75d0e-212">이 지역은 샘플 스크립트의 291 줄에서 335 줄에 있는 **# 설정 설명 구성** 으로 시작 하 여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="75d0e-213">지역이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="75d0e-214">스크립트의 **사용 권한 구성** 섹션에 설정 된 권한과 마찬가지로, 각 표면 UEFI 설정의 구성은 **$uefiV 2** 변수를 정의 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="75d0e-215">**$UefiV 2** 변수를 정의 하는 각 줄에 대해 Surface UEFI 설정은 설정 이름 또는 ID로 식별 되 고, 구성 된 값은 **Enabled** 또는 **Disabled**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="75d0e-216">Surface uefi 설정의 구성을 변경 하지 않으려는 경우, 예를 들어 모든 Surface UEFI 설정을 기본값으로 다시 설정 하는 작업으로 Surface UEFI 관리자 암호가 지워지지 않도록 하려면 **ClearConfiguredValue ()** 를 사용 하 여이 설정이 변경 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="75d0e-217">예제 스크립트에서이는 줄 323에서 설정 ID ( **501**)로 샘플 스크립트에서 식별 된 Surface UEFI 관리자 암호의 지우기를 방지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="75d0e-218">이 문서의 뒷부분에 나오는 [설정 이름 및 id](#settings-names-and-ids) 섹션에서 Surface UEFI에 대해 사용 가능한 설정 이름 및 id에 대 한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <span data-ttu-id="75d0e-219">설정 레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="75d0e-219">Settings registry key</span></span>

<span data-ttu-id="75d0e-220">구성 관리자의 등록 된 시스템을 식별 하기 위해 ConfigureSEMM.ps1 스크립트는 SEMM 구성 스크립트를 사용 하 여 등록 된 시스템을 식별 하는 데 사용할 수 있는 레지스트리 키를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="75d0e-221">이러한 키는 다음 위치에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="75d0e-222">380-477 줄에 있는 다음 코드 단편은 이러한 레지스트리 키를 작성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <span data-ttu-id="75d0e-223">설정 이름 및 Id</span><span class="sxs-lookup"><span data-stu-id="75d0e-223">Settings names and IDs</span></span>

<span data-ttu-id="75d0e-224">Surface uefi 설정 또는 Surface UEFI 설정에 대 한 사용 권한을 구성 하려면 각 설정을 해당 설정 이름 또는 설정 ID 중에서 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="75d0e-225">Surface UEFI에 대 한 새로운 업데이트 각각에 대해 새 설정이 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="75d0e-226">Surface 장치에서 사용할 수 있는 설정의 전체 목록 (설정 이름 및 설정 Id)을 가져오는 가장 좋은 방법은 [IT 다운로드에 대 한 Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 에서 SEMM_Powershell.zip의 ShowSettingsOptions.ps1 스크립트를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="75d0e-227">ShowSettingsOptions.ps1를 실행 하는 컴퓨터에는 Microsoft Surface UEFI 관리자가 설치 되어 있어야 하지만, 스크립트에는 Surface device가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>


## <span data-ttu-id="75d0e-228">SEMM 구성 관리자 스크립트 배포</span><span class="sxs-lookup"><span data-stu-id="75d0e-228">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="75d0e-229">클라이언트 장치에서 스크립트를 구성 하 고 사용할 준비가 되 면 다음 단계는 이러한 스크립트를 구성 관리자의 응용 프로그램으로 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-229">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="75d0e-230">구성 관리자를 열기 전에 다음 파일이 다른 파일을 포함 하지 않는 공유 폴더에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-230">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="75d0e-231">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="75d0e-231">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="75d0e-232">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="75d0e-232">ResetSEMM.ps1</span></span>
* <span data-ttu-id="75d0e-233">SEMM 인증서 (예: SEMMCertificate. .pfx)</span><span class="sxs-lookup"><span data-stu-id="75d0e-233">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="75d0e-234">SEMM 구성 관리자 스크립트는 구성 관리자에 스크립트 응용 프로그램으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-234">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="75d0e-235">ConfigureSEMM.ps1를 사용 하 여 SEMM을 설치 하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-235">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="75d0e-236">ResetSEMM.ps1를 사용 하 여 SEMM을 제거 하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-236">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="75d0e-237">구성 관리자에 SEMM 구성 관리자 스크립트를 응용 프로그램으로 추가 하려면 다음 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-237">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="75d0e-238">이 문서의 앞부분에 있는 [Microsoft SURFACE UEFI Manager 배포](#deploy-microsoft-surface-uefi-manager) 섹션의 1 ~ 5 단계를 사용 하 여 응용 프로그램 만들기 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-238">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="75d0e-239">아래와 같이 응용 프로그램 만들기 마법사를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-239">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="75d0e-240">**일반** - **응용 프로그램 정보를 수동으로 지정**을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-240">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="75d0e-241">**일반 정보** –이 페이지에서 응용 프로그램의 이름 (예: semm)과 publisher, 버전 또는 메모와 같은 기타 원하는 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-241">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="75d0e-242">계속 하려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-242">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="75d0e-243">**Application Catalog** –이 페이지의 필드에 기본값을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-243">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="75d0e-244">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-244">Select **Next**.</span></span>

   - <span data-ttu-id="75d0e-245">**배포 유형** – **추가** 를 선택 하 여 배포 유형 만들기 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-245">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="75d0e-246">다음과 같이 배포 형식 만들기 마법사의 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-246">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="75d0e-247">**일반** - **형식** 드롭다운 메뉴에서 **스크립트 설치 관리자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-247">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="75d0e-248">**수동으로 배포 유형 정보 지정** 옵션이 자동으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-248">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="75d0e-249">계속 하려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-249">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="75d0e-250">**일반 정보** -배포 유형의 이름 (예: Semm 구성 스크립트)을 입력 하 고 **다음** 을 선택 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-250">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="75d0e-251">**콘텐츠** – **콘텐츠 위치** 필드 옆에 있는 **찾아보기를** 선택한 다음 semm 구성 관리자 스크립트가 있는 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-251">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="75d0e-252">**설치 프로그램** 필드에이 문서의 앞부분에 있는 [설치 명령을](#deploy-semm-configuration-manager-scripts) 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-252">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="75d0e-253">**프로그램 제거** 필드에이 문서의 앞부분에 있는 [제거 명령](#deploy-semm-configuration-manager-scripts) (그림 2에 표시 됨)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-253">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="75d0e-254">다음 **을 선택 하** 여 다음 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-254">Select **Next** to move to the next page.</span></span>
    
     ![SEMM 구성 관리자 스크립트를 설치 및 제거 명령으로 설정 합니다.](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="75d0e-256">그림 2.</span><span class="sxs-lookup"><span data-stu-id="75d0e-256">Figure 2.</span></span> <span data-ttu-id="75d0e-257">SEMM 구성 관리자 스크립트를 설치 및 제거 명령으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-257">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="75d0e-258">**감지 메서드** – Semm 구성 관리자 스크립트 레지스트리 키 검색 규칙을 추가 하려면 **절 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-258">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="75d0e-259">그림 3과 같이 **검색 규칙** 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-259">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="75d0e-260">다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-260">Use the following settings:</span></span>

       - <span data-ttu-id="75d0e-261">**설정 유형** 드롭다운 메뉴에서 **레지스트리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-261">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="75d0e-262">**하이브** 드롭다운 메뉴에서 **HKEY_LOCAL_MACHINE** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-262">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="75d0e-263">**키** 필드에 **SOFTWARE\Microsoft\Surface\SEMM** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-263">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="75d0e-264">**값** 필드에 **CertName** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-264">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="75d0e-265">**데이터 형식** 드롭다운 메뉴에서 **문자열** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-265">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="75d0e-266">이 **앱의 현재 상태를 표시 하려면이 레지스트리 설정을 다음 규칙에 맞아야 합니다 .를 선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="75d0e-266">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="75d0e-267">**값** 필드에서 스크립트의 58 줄에 입력 한 인증서의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-267">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="75d0e-268">**확인** 을 선택 하 여 **검색 규칙** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-268">Select **OK** to close the **Detection Rule** window.</span></span>

     ![레지스트리 키를 사용 하 여 SEMM에 등록 된 장치 식별](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="75d0e-270">그림 3.</span><span class="sxs-lookup"><span data-stu-id="75d0e-270">Figure 3.</span></span> <span data-ttu-id="75d0e-271">레지스트리 키를 사용 하 여 SEMM에 등록 된 장치 식별</span><span class="sxs-lookup"><span data-stu-id="75d0e-271">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="75d0e-272">다음 **을 선택 하** 여 다음 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-272">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="75d0e-273">**사용자 환경** - **설치 동작** 드롭다운 메뉴에서 **시스템에 대 한 설치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-273">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="75d0e-274">사용자가 인증서 지문 자체를 기록 하 고 입력 하도록 하려면 **사용자가 로그온 할 때만**로그온 요구 사항을 설정 된 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-274">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="75d0e-275">관리자가 사용자에 대 한 지문을 입력 하 고 사용자가 지문을 볼 필요가 없도록 하려면 **로그온 요구 사항** 드롭다운 메뉴에서 **사용자가 로그온 되었는지 여부** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-275">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="75d0e-276">**요구 사항** – ConfigureSEMM.ps1 스크립트는 장치가 Surface device가 자동으로 확인 된 후 semm을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-276">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="75d0e-277">그러나 SEMM을 사용 하 여 관리 하지 않는 장치를 사용 하 여이 스크립트 응용 프로그램을 컬렉션에 배포 하려는 경우 여기에 요구 사항을 추가 하 여이 응용 프로그램이 관리 하려는 Surface 장치 또는 디바이스 에서만 실행 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-277">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="75d0e-278">**Next (다음** )를 선택 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-278">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="75d0e-279">**종속성** – **추가** 를 선택 하 여 **종속성 추가** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-279">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="75d0e-280">**추가** 를 선택 하 여 **필요한 응용 프로그램 지정** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-280">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="75d0e-281">**종속성 그룹 이름** 필드에 semm 종속성의 이름을 입력 합니다 (예: *semm 어셈블리*).</span><span class="sxs-lookup"><span data-stu-id="75d0e-281">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="75d0e-282">**사용할 수 있는 응용 프로그램** 및 MSI 배포 유형 목록에서 **Microsoft Surface UEFI 관리자** 를 선택한 다음 **확인** 을 선택 하 여 **필요한 응용 프로그램 지정** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-282">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="75d0e-283">Configuration Manager 스크립트를 사용 하 여 SEMM을 설정 하려고 할 때 장치에 Microsoft Surface UEFI 관리자가 자동으로 설치 되도록 하려면 **자동 설치** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-283">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="75d0e-284">**확인** 을 선택 하 여 **종속성 추가** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-284">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="75d0e-285">계속 하려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-285">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="75d0e-286">**요약** -배포 형식 만들기 마법사에서 입력 한 정보가이 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-286">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="75d0e-287">선택을 확인 하려면 **다음** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-287">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="75d0e-288">**진행률** – semm 스크립트 응용 프로그램에 대 한 배포 유형을 추가 하는 진행률 표시줄과 상태가이 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-288">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="75d0e-289">**완료** – 프로세스가 완료 되 면 배포 유형 만들기에 대 한 확인이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-289">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="75d0e-290">**닫기를** 선택 하 여 배포 유형 만들기 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-290">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="75d0e-291">**요약** -응용 프로그램 만들기 마법사에서 입력 한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-291">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="75d0e-292">**다음** 을 선택 하 여 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-292">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="75d0e-293">**진행률** – 응용 프로그램이 소프트웨어 라이브러리에 추가 되는 진행률 표시줄과 상태가이 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-293">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="75d0e-294">**완료** – 응용 프로그램 만들기 프로세스가 완료 되 면 성공적인 응용 프로그램 만들기에 대 한 확인이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-294">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="75d0e-295">**닫기를** 선택 하 여 응용 프로그램 만들기 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-295">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="75d0e-296">구성 관리자의 소프트웨어 라이브러리에서 스크립트 응용 프로그램을 사용할 수 있게 되 면 장치 또는 컬렉션에 준비한 스크립트를 사용 하 여 SEMM을 배포 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-296">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="75d0e-297">Microsoft Surface UEFI 관리자 어셈블리를 자동으로 설치 되는 종속성으로 구성한 경우에는 한 번에 SEMM을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-297">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="75d0e-298">어셈블리를 종속성으로 구성 하지 않은 경우 SEMM을 설정 하기 전에 관리 하려는 장치에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-298">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="75d0e-299">이 스크립트 응용 프로그램을 사용 하 고 최종 사용자에 게 표시 되는 구성으로 SEMM을 배포 하면 PowerShell 스크립트가 시작 되 고 PowerShell 창에 해당 인증서의 지문이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-299">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="75d0e-300">장치를 다시 부팅 한 후 Surface UEFI에서 메시지가 표시 되 면 사용자가이 지문을 기록 하 여 입력 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-300">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="75d0e-301">또는 자동으로 다시 부팅 하 고 사용자에 게 표시 되지 않는 설치 하도록 응용 프로그램 설치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-301">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="75d0e-302">이 시나리오에서 기술자는 다시 부팅 하면 각 장치에 지문을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-302">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="75d0e-303">인증서 파일에 대 한 액세스 권한이 있는 모든 기술자는 CertMgr를 사용 하 여 인증서를 보고 지문을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-303">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="75d0e-304">CertMgr를 사용 하 여 지문을 보는 방법에 대 한 지침은이 문서의 [SEMM Configuration Manager 스크립트 만들기 또는 수정](#create-or-modify-the-semm-configuration-manager-scripts) 섹션을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="75d0e-304">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="75d0e-305">이 스크립트를 사용 하 여 구성 관리자로 배포 된 장치에서 SEMM을 제거 하는 것은 구성 관리자로 응용 프로그램을 제거 하는 것 만큼 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-305">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="75d0e-306">이 작업은 ResetSEMM.ps1 스크립트를 시작 하 고 SEMM 배포 중에 사용 된 것과 동일한 인증서 파일을 사용 하 여 장치를 올바르게 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-306">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="75d0e-307">장치를 등록을 해제 해야 하는 경우에만 다시 설정 패키지를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-307">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="75d0e-308">이러한 재설정 패키지는 일반적으로 하나의 디바이스에 대해서만 유효 하며 일련 번호로 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-308">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="75d0e-309">그러나이 인증서를 사용 하 여 SEMM에 등록 된 모든 장치에서 작동 하는 범용 재설정 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-309">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="75d0e-310">유니버설 재설정 패키지는 디바이스를 등록 하는 데 사용한 인증서의 경우에 따라 신중 하 게 보호 하는 것이 좋습니다 (SEMM).</span><span class="sxs-lookup"><span data-stu-id="75d0e-310">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="75d0e-311">인증서 자체와 마찬가지로,이 범용 재설정 패키지를 사용 하 여 조직의 Surface 디바이스를 SEMM에서 등록을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-311">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="75d0e-312">다시 설정 패키지를 설치할 때 지원 되는 최저 값 (LSV)은 값 1로 다시 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-312">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="75d0e-313">기존 구성 패키지를 사용 하 여 디바이스를 reenroll 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-313">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="75d0e-314">장치가 소유권을 가져오기 전에 인증서 지문을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-314">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="75d0e-315">이러한 이유로 SEMM의 디바이스 reenrollment 해당 장치에 새 패키지를 만들고 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-315">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="75d0e-316">이 작업은 새 등록 이므로 SEMM로 등록 된 디바이스의 구성은 변경 되지 않으므로, 소유권을 가져오기 전에 장치에서 인증서 지문을 확인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d0e-316">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>
