---
title: 비즈니스용 Surface 진단 도구 키트 배포
description: 이 항목에서는 비즈니스용 Surface 진단 Toolkit 방법을 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271582"
---
# <span data-ttu-id="a6871-103">비즈니스용 Surface 진단 도구 키트 배포</span><span class="sxs-lookup"><span data-stu-id="a6871-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="a6871-104">IT Toolkit SDT(비즈니스용 Microsoft Surface Diagnostic Toolkit)를 사용하면 IT 관리자가 Surface 디바이스에서 하드웨어, 소프트웨어 및 펌웨어 문제를 신속하게 조사, 문제 해결 및 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="a6871-105">다양한 진단 테스트 및 소프트웨어 복구를 실행할 수 있으며, 문제 해결을 위한 장치 상태 정보 및 지침을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="a6871-106">특히 비즈니스용 SDT를 사용하면 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="a6871-107">패키지를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="a6871-108">명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="a6871-109">여러 하드웨어 테스트를 실행하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="a6871-110">문제를 분석하기 위한 로그를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="a6871-111">장치와 최적의 구성을 비교하는 자세한 보고서를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <a name="primary-scenarios-and-download-resources"></a><span data-ttu-id="a6871-112">기본 시나리오 및 리소스 다운로드</span><span class="sxs-lookup"><span data-stu-id="a6871-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="a6871-113">비즈니스용 SDT를 실행하려면 다음 표에 나열된 구성 요소를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="a6871-114">모드</span><span class="sxs-lookup"><span data-stu-id="a6871-114">Mode</span></span> |  <span data-ttu-id="a6871-115">기본 시나리오</span><span class="sxs-lookup"><span data-stu-id="a6871-115">Primary scenarios</span></span> | <span data-ttu-id="a6871-116">다운로드</span><span class="sxs-lookup"><span data-stu-id="a6871-116">Download</span></span> | <span data-ttu-id="a6871-117">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="a6871-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="a6871-118">데스크톱 모드</span><span class="sxs-lookup"><span data-stu-id="a6871-118">Desktop mode</span></span> |  <span data-ttu-id="a6871-119">사용자가 Surface 디바이스에서 SDT를 실행하여 문제를 해결할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="a6871-120">하나 이상의 Surface 디바이스에 배포할 사용자 지정 패키지를 만들어 사용자가 수집 및 분석할 특정 로그를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="a6871-121">SDT 배포 가능 MSI 패키지:</span><span class="sxs-lookup"><span data-stu-id="a6871-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="a6871-122">비즈니스용 Microsoft Surface Toolkit 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="a6871-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="a6871-123">IT용 Surface 도구</span><span class="sxs-lookup"><span data-stu-id="a6871-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="a6871-124">데스크톱 모드에서 Surface 진단 Toolkit 사용</span><span class="sxs-lookup"><span data-stu-id="a6871-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="a6871-125">명령줄</span><span class="sxs-lookup"><span data-stu-id="a6871-125">Command line</span></span> |  <span data-ttu-id="a6871-126">Configuration Manager와 같은 표준 도구를 사용하여 사용자 조작 없이 원격으로 Surface 디바이스 문제를 직접 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="a6871-127">여기에는 다음 명령이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="a6871-128">모든 로그 파일 수집</span><span class="sxs-lookup"><span data-stu-id="a6871-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="a6871-129">모범 사례 분석기를 사용하여 상태 진단을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="a6871-130">Windows 업데이트에서 펌웨어 또는 드라이버 업데이트 누락을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="a6871-131">보증 정보를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="a6871-132">SDT 콘솔 앱:</span><span class="sxs-lookup"><span data-stu-id="a6871-132">SDT console app:</span></span><br><span data-ttu-id="a6871-133">Microsoft Surface 진단 앱 콘솔</span><span class="sxs-lookup"><span data-stu-id="a6871-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="a6871-134">IT용 Surface 도구</span><span class="sxs-lookup"><span data-stu-id="a6871-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="a6871-135">명령을 사용하여 Surface Toolkit 실행</span><span class="sxs-lookup"><span data-stu-id="a6871-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices-"></a><span data-ttu-id="a6871-136">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="a6871-136">Supported devices</span></span> 

<span data-ttu-id="a6871-137">비즈니스용 SDT는 다음을 포함하여 Surface 3 이상 디바이스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="a6871-138">Surface Book - 모든 세대</span><span class="sxs-lookup"><span data-stu-id="a6871-138">Surface Book - all generations</span></span>
- <span data-ttu-id="a6871-139">Surface Go - 모든 세대</span><span class="sxs-lookup"><span data-stu-id="a6871-139">Surface Go - all generations</span></span>
- <span data-ttu-id="a6871-140">Surface 노트북 - 모든 세대</span><span class="sxs-lookup"><span data-stu-id="a6871-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="a6871-141">Surface Pro 3 이상</span><span class="sxs-lookup"><span data-stu-id="a6871-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="a6871-142">Surface Pro X - 모든 세대</span><span class="sxs-lookup"><span data-stu-id="a6871-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="a6871-143">Surface Studio - 모든 세대</span><span class="sxs-lookup"><span data-stu-id="a6871-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="a6871-144">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="a6871-144">Surface 3 LTE</span></span>
- <span data-ttu-id="a6871-145">Surface 3</span><span class="sxs-lookup"><span data-stu-id="a6871-145">Surface 3</span></span>


## <a name="installing-surface-diagnostic-toolkit-for-business"></a><span data-ttu-id="a6871-146">비즈니스용 Surface 진단 Toolkit 설치</span><span class="sxs-lookup"><span data-stu-id="a6871-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="a6871-147">조직의 사용자에게 배포할 수 있는 SDT 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="a6871-148">관리자 계정을 사용하여 Surface 디바이스에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="a6871-149">[Surface Tools for IT 다운로드](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 SDT Windows Installer 패키지(.msi)를 다운로드하여 Surface 디바이스의 기본 설정 위치(예: 데스크톱)에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="a6871-150">그림 1과 같이 SDT 설정 마법사가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="a6871-151">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="a6871-152">설치 마법사가 나타나지 않는 경우 컴퓨터의 관리자 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Surface Diagnostic Toolkit 마법사 시작](images/sdt-1.png)

    *<span data-ttu-id="a6871-154">그림 1.</span><span class="sxs-lookup"><span data-stu-id="a6871-154">Figure 1.</span></span> <span data-ttu-id="a6871-155">Surface 진단 Toolkit 설정 마법사</span><span class="sxs-lookup"><span data-stu-id="a6871-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="a6871-156">SDT 설정 마법사가 나타나면 다음을 **클릭하고**EULA(최종 사용자 사용권 계약)에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="a6871-157">설치 옵션 화면에서 원하는 경우 기본 설치 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="a6871-158">설치 유형에서 고급을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6871-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="a6871-159">표준 옵션을 사용하면 관리자 계정을 사용하여 장치에 로그인한 경우 Surface 장치에서 직접 진단 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![설치 옵션: 고급](images/sdt-install.png)

7. <span data-ttu-id="a6871-161">다음을 **클릭하고** 설치를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a6871-161">Click **Next** and then click **Install**.</span></span> 

## <a name="installing-using-the-command-line"></a><span data-ttu-id="a6871-162">명령줄을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="a6871-162">Installing using the command line</span></span>
<span data-ttu-id="a6871-163">원하는 경우 명령 프롬프트에서 SDT를 설치하고 사용자 지정 플래그를 설정하여 관리 모드로 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="a6871-164">SDT에는 다음과 같은 설치 옵션 플래그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="a6871-165">원격 분석 데이터를 Microsoft로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="a6871-166">플래그를 사용할 수 없습니다. 또는 `0` `1` 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="a6871-167">기본값은 원격 분석 `1` 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="a6871-168">관리 모드로 설치할 도구를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="a6871-169">플래그는 클라이언트 모드 또는 IT 관리자 `0` `1` 모드에 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="a6871-170">기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-170">The default value is `0`.</span></span>

### <a name="to-install-sdt-from-the-command-line"></a><span data-ttu-id="a6871-171">명령줄에서 SDT를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="a6871-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="a6871-172">명령 프롬프트를 열고 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="a6871-173">예제:</span><span class="sxs-lookup"><span data-stu-id="a6871-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a><span data-ttu-id="a6871-174">Surface 디바이스에서 SDT 찾기</span><span class="sxs-lookup"><span data-stu-id="a6871-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="a6871-175">SDT와 SDT 앱 콘솔이 모두 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="a6871-176">SDT는 .exe 파일 외에 그림 2와 같이 JSON 파일과 admin.dll 파일(modules\admin.dll)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![파일 탐색기에서 설치된 SDT 파일 목록](images/sdt-2.png)

*<span data-ttu-id="a6871-178">그림 2.</span><span class="sxs-lookup"><span data-stu-id="a6871-178">Figure 2.</span></span> <span data-ttu-id="a6871-179">SDT에서 설치한 파일</span><span class="sxs-lookup"><span data-stu-id="a6871-179">Files installed by SDT</span></span>*

## <a name="preparing-the-sdt-package-for-distribution"></a><span data-ttu-id="a6871-180">배포를 위해 SDT 패키지 준비</span><span class="sxs-lookup"><span data-stu-id="a6871-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="a6871-181">사용자 지정 패키지를 만들면 도구를 알려진 특정 문제로 대상으로 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="a6871-182">시작> **실행을 클릭하고** **Surface를** 입력한 다음 **비즈니스용 Surface 진단**Toolkit 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="a6871-183">도구가 열리면 \*\*\*\* 그림 3과 같이 사용자 지정 패키지 만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![사용자 지정 패키지 옵션 만들기](images/sdt-3.png)

    *<span data-ttu-id="a6871-185">그림 3.</span><span class="sxs-lookup"><span data-stu-id="a6871-185">Figure 3.</span></span> <span data-ttu-id="a6871-186">사용자 지정 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="a6871-186">Create custom package</span></span>*

### <a name="language-and-telemetry-settings"></a><span data-ttu-id="a6871-187">언어 및 원격 분석 설정</span><span class="sxs-lookup"><span data-stu-id="a6871-187">Language and telemetry settings</span></span>

  <span data-ttu-id="a6871-188">패키지를 만들 때 언어 설정을 선택하거나 Microsoft에 원격 분석 정보를 보내지 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="a6871-189">기본적으로 SDT는 Microsoft 개인 정보 취급 방침에 따라 응용 프로그램을 개선하는 데 사용되는 원격 분석 [기능을 Microsoft로 전송합니다.](https://privacy.microsoft.com/privacystatement)</span><span class="sxs-lookup"><span data-stu-id="a6871-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="a6871-190">거부할 경우 아래와 같이 사용자 지정 패키지를 만들 때 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="a6871-191">또는 SDT 설치 중에 설치 옵션 \*\*\*\* 페이지에서 **Microsoft로** 원격 분석 보내기 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="a6871-192">이 설정은 Windows 업데이트 및 소프트웨어 복구와 같은 인터넷 연결이 필요한 테스트 및 복구를 실행하거나 앱 도구 모음의 스마일 또는 까다로워진 단추를 사용하여 피드백을 제공하는 경우 Microsoft 서버에 자동으로 저장되는 최소 원격 분석에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![언어 및 원격 분석 설정 선택](images/sdt-4.png)

*<span data-ttu-id="a6871-194">그림 4.</span><span class="sxs-lookup"><span data-stu-id="a6871-194">Figure 4.</span></span> <span data-ttu-id="a6871-195">언어 및 원격 분석 설정 선택</span><span class="sxs-lookup"><span data-stu-id="a6871-195">Select language and telemetry settings</span></span>*


### <a name="windows-update-page"></a><span data-ttu-id="a6871-196">Windows 업데이트 페이지</span><span class="sxs-lookup"><span data-stu-id="a6871-196">Windows Update page</span></span>

<span data-ttu-id="a6871-197">조직에 적합한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="a6871-198">일반적으로 사용자가 여러 명인 조직에서는 그림 5와 같이 WSUS(Windows Server Update Services)를 통해 업데이트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="a6871-199">로컬 Windows 업데이트 패키지 또는 WSUS를 사용하는 경우 경로를 적절하게 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Windows 업데이트 옵션 선택](images/sdt-5.png)

*<span data-ttu-id="a6871-201">그림 5.</span><span class="sxs-lookup"><span data-stu-id="a6871-201">Figure 5.</span></span> <span data-ttu-id="a6871-202">Windows 업데이트 옵션</span><span class="sxs-lookup"><span data-stu-id="a6871-202">Windows Update option</span></span>*

### <a name="software-repair-page"></a><span data-ttu-id="a6871-203">소프트웨어 복구 페이지</span><span class="sxs-lookup"><span data-stu-id="a6871-203">Software repair page</span></span>

<span data-ttu-id="a6871-204">이렇게 하면 소프트웨어 복구 업데이트를 실행하기 위한 옵션을 선택하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![소프트웨어 복구 옵션 선택](images/sdt-6.png)

*<span data-ttu-id="a6871-206">그림 6.</span><span class="sxs-lookup"><span data-stu-id="a6871-206">Figure 6.</span></span> <span data-ttu-id="a6871-207">소프트웨어 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="a6871-207">Software repair option</span></span>*

### <a name="collecting-logs-and-saving-package-page"></a><span data-ttu-id="a6871-208">로그 수집 및 패키지 저장 페이지</span><span class="sxs-lookup"><span data-stu-id="a6871-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="a6871-209">응용 프로그램, 드라이버, 하드웨어 및 운영 체제에서 다양한 로그를 실행하기로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="a6871-210">적절한 영역을 클릭하고 사용 가능한 로그의 메뉴에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="a6871-211">그런 다음 사용자가 액세스할 수 있는 소프트웨어 배포 지점 또는 이에 상응하는 위치에 패키지를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![로그 옵션 선택](images/sdt-7.png)

*<span data-ttu-id="a6871-213">그림 7.</span><span class="sxs-lookup"><span data-stu-id="a6871-213">Figure 7.</span></span> <span data-ttu-id="a6871-214">로그 옵션 및 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="a6871-214">Log option and save package</span></span>*

## <a name="next-steps"></a><span data-ttu-id="a6871-215">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a6871-215">Next steps</span></span>

- [<span data-ttu-id="a6871-216">비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용</span><span class="sxs-lookup"><span data-stu-id="a6871-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="a6871-217">명령을 사용하여 비즈니스용 Surface Toolkit 프로그램 사용</span><span class="sxs-lookup"><span data-stu-id="a6871-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a><span data-ttu-id="a6871-218">변경 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="a6871-218">Changes and updates</span></span>

### <a name="version-2.131.139.0"></a><span data-ttu-id="a6871-219">버전 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-219">Version 2.131.139.0</span></span>

<span data-ttu-id="a6871-220">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a6871-221">Surface Pro 7+ 지원</span><span class="sxs-lookup"><span data-stu-id="a6871-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="a6871-222">Surface Pro X의 원활한 지원 환경</span><span class="sxs-lookup"><span data-stu-id="a6871-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="a6871-223">보안 개선</span><span class="sxs-lookup"><span data-stu-id="a6871-223">Security improvements</span></span>
- <span data-ttu-id="a6871-224">포괄 사용자 환경 개선</span><span class="sxs-lookup"><span data-stu-id="a6871-224">Inclusive user experience improvements</span></span>

### <a name="version-2.124.139.0"></a><span data-ttu-id="a6871-225">버전 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-225">Version 2.124.139.0</span></span>

<span data-ttu-id="a6871-226">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a6871-227">원활한 통합 지원</span><span class="sxs-lookup"><span data-stu-id="a6871-227">Seamless integrated support</span></span>
- <span data-ttu-id="a6871-228">모든 테스트 결과 저장</span><span class="sxs-lookup"><span data-stu-id="a6871-228">Save all test results</span></span>
- <span data-ttu-id="a6871-229">이미지를 사용자 지정으로 만들지 확인</span><span class="sxs-lookup"><span data-stu-id="a6871-229">Check if the image is custom created</span></span>
- <span data-ttu-id="a6871-230">장치 관리자의 경고 포함</span><span class="sxs-lookup"><span data-stu-id="a6871-230">Include warnings from device manager</span></span>
- <span data-ttu-id="a6871-231">Dock 펌웨어 버전</span><span class="sxs-lookup"><span data-stu-id="a6871-231">Dock firmware version</span></span>
- <span data-ttu-id="a6871-232">저장소 테스트에서 잠재적인 오류로 드라이브 플래그 지정</span><span class="sxs-lookup"><span data-stu-id="a6871-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="a6871-233">저장소 링크 제거</span><span class="sxs-lookup"><span data-stu-id="a6871-233">Remove store link</span></span> 

### <a name="version-2.121.139"></a><span data-ttu-id="a6871-234">버전 2.121.139</span><span class="sxs-lookup"><span data-stu-id="a6871-234">Version 2.121.139</span></span>
*<span data-ttu-id="a6871-235">릴리스 날짜: 2020년 7월 31일</span><span class="sxs-lookup"><span data-stu-id="a6871-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="a6871-236">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a6871-237">원활한 지원 환경</span><span class="sxs-lookup"><span data-stu-id="a6871-237">Seamless support experience</span></span>
- <span data-ttu-id="a6871-238">버그 수정</span><span class="sxs-lookup"><span data-stu-id="a6871-238">Bug fixes</span></span>

### <a name="version-2.94.139.0"></a><span data-ttu-id="a6871-239">버전 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="a6871-240">릴리스 날짜: 2020년 5월 11일</span><span class="sxs-lookup"><span data-stu-id="a6871-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="a6871-241">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a6871-242">하드웨어 검사를 수행하기 위해 Windows 업데이트를 건너뛰는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="a6871-243">최신 버전 업데이트에 대한 알림을 받을 수 있는 능력</span><span class="sxs-lookup"><span data-stu-id="a6871-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="a6871-244">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="a6871-244">Surface Go 2</span></span>
- <span data-ttu-id="a6871-245">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="a6871-245">Surface Book 3</span></span>
- <span data-ttu-id="a6871-246">진행률 표시기 표시</span><span class="sxs-lookup"><span data-stu-id="a6871-246">Show progress indicator</span></span>


### <a name="version-2.43.139.0"></a><span data-ttu-id="a6871-247">버전 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="a6871-248">릴리스 날짜: 2019년 10월 21일</span><span class="sxs-lookup"><span data-stu-id="a6871-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="a6871-249">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="a6871-250">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a6871-250">Surface Pro 7</span></span>
- <span data-ttu-id="a6871-251">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="a6871-251">Surface Laptop 3</span></span>

### <a name="version-2.42.139.0"></a><span data-ttu-id="a6871-252">버전 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="a6871-253">릴리스 날짜: 2019년 9월 24일</span><span class="sxs-lookup"><span data-stu-id="a6871-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="a6871-254">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="a6871-255">하드웨어 보고서를 다운로드하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="a6871-256">도구에서 직접 Microsoft 지원에 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <a name="version-2.41.139.0"></a><span data-ttu-id="a6871-257">버전 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="a6871-258">릴리스 날짜: 2019년 6월 24일</span><span class="sxs-lookup"><span data-stu-id="a6871-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="a6871-259">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="a6871-260">로그 및 보고서에 포함된 드라이버 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="a6871-261">앱에 대한 피드백을 제공하는 능력.</span><span class="sxs-lookup"><span data-stu-id="a6871-261">Ability to provide feedback about the app.</span></span><br>


### <a name="version-2.36.139.0"></a><span data-ttu-id="a6871-262">버전 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="a6871-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="a6871-263">릴리스 날짜: 2019년 4월 26일</span><span class="sxs-lookup"><span data-stu-id="a6871-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="a6871-264">이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="a6871-265">명령줄 구성 없이 설치 관리자 UI를 통해 관리자 기능을 잠금 해제하는 고급 설치 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="a6871-266">접근성 개선.</span><span class="sxs-lookup"><span data-stu-id="a6871-266">Accessibility improvements.</span></span>
- <span data-ttu-id="a6871-267">로그에 포함된 표면 밝기 컨트롤 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="a6871-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="a6871-268">보고서 생성기의 외부 모니터 호환성 지원 링크</span><span class="sxs-lookup"><span data-stu-id="a6871-268">External monitor compatibility support link in report generator.</span></span>
