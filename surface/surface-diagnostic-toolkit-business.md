---
title: 비즈니스용 Surface 진단 도구 키트 배포
description: 이 항목에서는 비즈니스를 위해 Surface 진단 도구 키트를 사용 하는 방법에 대해 설명 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 05/11/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 9233ca1f7e32e2017424e9fb6ceb0556de9d37bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834300"
---
# <span data-ttu-id="bbbea-103">비즈니스용 Surface 진단 도구 키트 배포</span><span class="sxs-lookup"><span data-stu-id="bbbea-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="bbbea-104">Microsoft Surface (비즈니스 관련 진단 도구 키트) (SDT)는 IT 관리자가 Surface 장치에서 하드웨어, 소프트웨어 및 펌웨어 문제를 빠르게 조사, 문제 해결 및 해결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="bbbea-105">장치 상태 정보 활용 및 문제 해결에 대 한 지침을 얻고, 다양 한 진단 테스트 및 소프트웨어 복구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="bbbea-106">특히, 비즈니스의 SDT에서는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="bbbea-107">패키지를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="bbbea-108">명령을 사용 하 여 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="bbbea-109">여러 하드웨어 테스트를 실행 하 여 문제를 해결 하세요.</span><span class="sxs-lookup"><span data-stu-id="bbbea-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="bbbea-110">문제 분석을 위한 로그를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="bbbea-111">디바이스 vs 최적의 구성을 비교 하는 자세한 보고서를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="bbbea-112">기본 시나리오 및 다운로드 리소스</span><span class="sxs-lookup"><span data-stu-id="bbbea-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="bbbea-113">비즈니스에 대해 SDT를 실행 하려면 다음 표에 나열 된 구성 요소를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="bbbea-114">모드</span><span class="sxs-lookup"><span data-stu-id="bbbea-114">Mode</span></span> |  <span data-ttu-id="bbbea-115">기본 시나리오</span><span class="sxs-lookup"><span data-stu-id="bbbea-115">Primary scenarios</span></span> | <span data-ttu-id="bbbea-116">다운로드</span><span class="sxs-lookup"><span data-stu-id="bbbea-116">Download</span></span> | <span data-ttu-id="bbbea-117">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="bbbea-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="bbbea-118">데스크톱 모드</span><span class="sxs-lookup"><span data-stu-id="bbbea-118">Desktop mode</span></span> |  <span data-ttu-id="bbbea-119">표면 장치에서 SDT를 실행 하는 사용자가 문제를 해결 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="bbbea-120">사용자가 수집 하 고 분석할 특정 로그를 선택할 수 있도록 하나 이상의 Surface 장치에 배포 하는 사용자 지정 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="bbbea-121">SDT 배포 가능 MSI 패키지:</span><span class="sxs-lookup"><span data-stu-id="bbbea-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="bbbea-122">비즈니스 설치 관리자 용 Microsoft Surface 진단 도구 키트</span><span class="sxs-lookup"><span data-stu-id="bbbea-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="bbbea-123">IT용 Surface 도구</span><span class="sxs-lookup"><span data-stu-id="bbbea-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="bbbea-124">데스크톱 모드에서 Surface 진단 도구 키트 사용</span><span class="sxs-lookup"><span data-stu-id="bbbea-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="bbbea-125">명령줄</span><span class="sxs-lookup"><span data-stu-id="bbbea-125">Command line</span></span> |  <span data-ttu-id="bbbea-126">구성 관리자와 같은 표준 도구를 사용 하 여 사용자 조작 없이 원격으로 Surface 디바이스의 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="bbbea-127">여기에는 다음 명령이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="bbbea-128">모든 로그 파일 수집</span><span class="sxs-lookup"><span data-stu-id="bbbea-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="bbbea-129">모범 사례 분석기를 사용 하 여 상태 진단을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="bbbea-130">Windows 업데이트에서 누락 된 펌웨어 또는 드라이버 업데이트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="bbbea-131">무상 수리 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="bbbea-132">SDT 콘솔 앱:</span><span class="sxs-lookup"><span data-stu-id="bbbea-132">SDT console app:</span></span><br><span data-ttu-id="bbbea-133">Microsoft Surface Diagnostics 앱 콘솔</span><span class="sxs-lookup"><span data-stu-id="bbbea-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="bbbea-134">IT용 Surface 도구</span><span class="sxs-lookup"><span data-stu-id="bbbea-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="bbbea-135">명령을 사용 하 여 Surface 진단 도구 키트 실행</span><span class="sxs-lookup"><span data-stu-id="bbbea-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="bbbea-136">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="bbbea-136">Supported devices</span></span> 

<span data-ttu-id="bbbea-137">다음을 포함 하 여 Surface 3 및 이후 장치에서 비즈니스의 SDT가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="bbbea-138">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="bbbea-138">Surface Book 3</span></span>
- <span data-ttu-id="bbbea-139">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="bbbea-139">Surface Go 2</span></span>
- <span data-ttu-id="bbbea-140">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="bbbea-140">Surface Pro X</span></span>
- <span data-ttu-id="bbbea-141">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="bbbea-141">Surface Pro 7</span></span>
- <span data-ttu-id="bbbea-142">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="bbbea-142">Surface Laptop 3</span></span>
- <span data-ttu-id="bbbea-143">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="bbbea-143">Surface Pro 6</span></span>
- <span data-ttu-id="bbbea-144">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="bbbea-144">Surface Laptop 2</span></span>
- <span data-ttu-id="bbbea-145">Surface Go</span><span class="sxs-lookup"><span data-stu-id="bbbea-145">Surface Go</span></span>
- <span data-ttu-id="bbbea-146">LTE를 사용 하 여 Surface Go</span><span class="sxs-lookup"><span data-stu-id="bbbea-146">Surface Go with LTE</span></span>
- <span data-ttu-id="bbbea-147">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="bbbea-147">Surface Book 2</span></span>
- <span data-ttu-id="bbbea-148">Surface Pro LTE Advanced(모델 1807)</span><span class="sxs-lookup"><span data-stu-id="bbbea-148">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="bbbea-149">Surface Pro(모델 1796)</span><span class="sxs-lookup"><span data-stu-id="bbbea-149">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="bbbea-150">Surface 노트북</span><span class="sxs-lookup"><span data-stu-id="bbbea-150">Surface Laptop</span></span>
- <span data-ttu-id="bbbea-151">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="bbbea-151">Surface Studio</span></span>
- <span data-ttu-id="bbbea-152">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="bbbea-152">Surface Studio 2</span></span>
- <span data-ttu-id="bbbea-153">Surface Book</span><span class="sxs-lookup"><span data-stu-id="bbbea-153">Surface Book</span></span>
- <span data-ttu-id="bbbea-154">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="bbbea-154">Surface Pro 4</span></span>
- <span data-ttu-id="bbbea-155">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="bbbea-155">Surface 3 LTE</span></span>
- <span data-ttu-id="bbbea-156">Surface 3</span><span class="sxs-lookup"><span data-stu-id="bbbea-156">Surface 3</span></span>
- <span data-ttu-id="bbbea-157">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="bbbea-157">Surface Pro 3</span></span>

## <span data-ttu-id="bbbea-158">비즈니스를 위한 Surface 진단 도구 키트 설치</span><span class="sxs-lookup"><span data-stu-id="bbbea-158">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="bbbea-159">조직의 사용자에 게 배포할 수 있는 SDT 패키지를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-159">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="bbbea-160">관리자 계정을 사용 하 여 Surface device에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-160">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="bbbea-161">[IT 다운로드 페이지의 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 Sdt Windows Installer 패키지 (.msi)를 다운로드 하 고 데스크톱 등의 surface 장치에서 원하는 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-161">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="bbbea-162">SDT 설정 마법사가 표시 됩니다 (그림 1).</span><span class="sxs-lookup"><span data-stu-id="bbbea-162">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="bbbea-163">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-163">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="bbbea-164">설치 마법사가 표시 되지 않으면 컴퓨터에서 관리자 계정에 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-164">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Surface 진단 도구 키트 설정 마법사 시작](images/sdt-1.png)

    *<span data-ttu-id="bbbea-166">그림 1.</span><span class="sxs-lookup"><span data-stu-id="bbbea-166">Figure 1.</span></span> <span data-ttu-id="bbbea-167">Surface 진단 도구 키트 설정 마법사</span><span class="sxs-lookup"><span data-stu-id="bbbea-167">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="bbbea-168">SDT 설정 마법사가 나타나면 **다음**을 클릭 하 여 최종 사용자 사용권 계약 (EULA)에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-168">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="bbbea-169">설치 옵션 화면에서 원하는 경우 기본 설치 위치를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-169">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="bbbea-170">설치 유형 아래에서 **고급**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-170">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="bbbea-171">표준 옵션을 사용 하면 관리자 계정으로 장치에 로그인 한 경우 사용자는 Surface device에서 진단 도구를 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-171">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![설치 옵션: 고급](images/sdt-install.png)

7. <span data-ttu-id="bbbea-173">**다음** 을 클릭 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-173">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="bbbea-174">명령줄을 사용 하 여 설치</span><span class="sxs-lookup"><span data-stu-id="bbbea-174">Installing using the command line</span></span>
<span data-ttu-id="bbbea-175">필요한 경우 명령 프롬프트에서 SDT를 설치 하 고 사용자 지정 플래그를 설정 하 여 해당 도구를 관리 모드로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-175">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="bbbea-176">SDT에는 다음 설치 옵션 플래그가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-176">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="bbbea-177">원격 분석 데이터를 Microsoft에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-177">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="bbbea-178">플래그는 `0` 사용 안 함 또는 `1` 사용으로 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-178">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="bbbea-179">기본값은 `1` 원격 분석을 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-179">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="bbbea-180">관리 모드에서 설치 되도록 도구를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-180">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="bbbea-181">플래그는 `0` 클라이언트 모드 또는 `1` IT 관리자 모드에 대해 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-181">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="bbbea-182">기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-182">The default value is `0`.</span></span>

### <span data-ttu-id="bbbea-183">명령줄에서 SDT를 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-183">To install SDT from the command line:</span></span>

1. <span data-ttu-id="bbbea-184">명령 프롬프트를 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-184">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="bbbea-185">예:</span><span class="sxs-lookup"><span data-stu-id="bbbea-185">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="bbbea-186">Surface 장치에서 SDT 찾기</span><span class="sxs-lookup"><span data-stu-id="bbbea-186">Locating SDT on your Surface device</span></span>

<span data-ttu-id="bbbea-187">SDT 및 SDT 앱 콘솔 모두에 설치 됩니다 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="bbbea-187">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="bbbea-188">SDT는 .exe 파일 외에도 그림 2와 같이 JSON 파일과 admin.dll 파일 (modules\admin.dll)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-188">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![파일 탐색기에 설치 된 SDT의 파일 목록](images/sdt-2.png)

*<span data-ttu-id="bbbea-190">그림 2.</span><span class="sxs-lookup"><span data-stu-id="bbbea-190">Figure 2.</span></span> <span data-ttu-id="bbbea-191">SDT에서 설치 된 파일</span><span class="sxs-lookup"><span data-stu-id="bbbea-191">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="bbbea-192">배포를 위해 SDT 패키지 준비</span><span class="sxs-lookup"><span data-stu-id="bbbea-192">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="bbbea-193">사용자 지정 패키지를 만들면 도구가 알려진 특정 문제를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-193">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="bbbea-194">**시작 > 실행**을 클릭 하 고 **화면** 을 입력 한 다음 **surface 진단 도구 키트**를 클릭 하 여 비즈니스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-194">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="bbbea-195">도구가 열리면 그림 3에 나와 있는 것 처럼 **사용자 지정 패키지 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-195">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![사용자 지정 패키지 만들기 옵션](images/sdt-3.png)

    *<span data-ttu-id="bbbea-197">그림 3.</span><span class="sxs-lookup"><span data-stu-id="bbbea-197">Figure 3.</span></span> <span data-ttu-id="bbbea-198">사용자 지정 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="bbbea-198">Create custom package</span></span>*

### <span data-ttu-id="bbbea-199">언어 및 원격 분석 설정</span><span class="sxs-lookup"><span data-stu-id="bbbea-199">Language and telemetry settings</span></span>

  <span data-ttu-id="bbbea-200">패키지를 만들 때 언어 설정을 선택 하거나 Microsoft에 원격 분석 정보를 보내는 것을 옵트아웃 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-200">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="bbbea-201">기본적으로 SDT는 [microsoft](https://privacy.microsoft.com/privacystatement)에 대 한 원격 분석을 전송 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-201">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="bbbea-202">거절 하려는 경우 아래와 같이 사용자 지정 패키지를 만들 때 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-202">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="bbbea-203">또는 SDT 설치 중 **옵션 설치** 페이지에서 **Microsoft로 원격 분석 보내기** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-203">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="bbbea-204">이 설정은 Windows Update 및 소프트웨어 복구와 같은 인터넷 연결이 필요한 테스트 및 복구를 실행 하거나 앱 도구 모음에서 웃는 얼굴 또는 찡그린 얼굴 보내기 단추를 사용 하 여 피드백을 제공 하는 경우 Microsoft 서버에 자동으로 저장 되는 최소 원격 분석에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-204">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![언어 및 원격 분석 설정 선택](images/sdt-4.png)

*<span data-ttu-id="bbbea-206">그림 4.</span><span class="sxs-lookup"><span data-stu-id="bbbea-206">Figure 4.</span></span> <span data-ttu-id="bbbea-207">언어 및 원격 분석 설정 선택</span><span class="sxs-lookup"><span data-stu-id="bbbea-207">Select language and telemetry settings</span></span>*


### <span data-ttu-id="bbbea-208">Windows 업데이트 페이지</span><span class="sxs-lookup"><span data-stu-id="bbbea-208">Windows Update page</span></span>

<span data-ttu-id="bbbea-209">조직에 적합 한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-209">Select the option appropriate for your organization.</span></span> <span data-ttu-id="bbbea-210">일반적으로 여러 사용자가 있는 조직에서는 그림 5와 같이 WSUS (Windows Server Update Services)를 통해 업데이트를 받도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-210">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="bbbea-211">로컬 Windows 업데이트 패키지 또는 WSUS를 사용 하는 경우 적절 하 게 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-211">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Windows 업데이트 옵션 선택](images/sdt-5.png)

*<span data-ttu-id="bbbea-213">그림 5.</span><span class="sxs-lookup"><span data-stu-id="bbbea-213">Figure 5.</span></span> <span data-ttu-id="bbbea-214">Windows 업데이트 옵션</span><span class="sxs-lookup"><span data-stu-id="bbbea-214">Windows Update option</span></span>*

### <span data-ttu-id="bbbea-215">소프트웨어 복구 페이지</span><span class="sxs-lookup"><span data-stu-id="bbbea-215">Software repair page</span></span>

<span data-ttu-id="bbbea-216">이렇게 하면 소프트웨어 복구 업데이트를 실행 하는 옵션을 선택 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-216">This allows you to select or remove the option to run software repair updates.</span></span> 

![소프트웨어 복구 옵션 선택](images/sdt-6.png)

*<span data-ttu-id="bbbea-218">그림 6.</span><span class="sxs-lookup"><span data-stu-id="bbbea-218">Figure 6.</span></span> <span data-ttu-id="bbbea-219">소프트웨어 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="bbbea-219">Software repair option</span></span>*

### <span data-ttu-id="bbbea-220">로그 수집 및 패키지 저장 페이지</span><span class="sxs-lookup"><span data-stu-id="bbbea-220">Collecting logs and saving package page</span></span>

<span data-ttu-id="bbbea-221">다양 한 로그를 응용 프로그램, 드라이버, 하드웨어 및 운영 체제 간에 실행 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-221">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="bbbea-222">적절 한 영역을 클릭 하 고 사용 가능한 로그 메뉴에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-222">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="bbbea-223">그런 다음 패키지를 사용자가 액세스할 수 있는 소프트웨어 배포 지점이 나 동등한 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-223">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![로그 옵션 선택](images/sdt-7.png)

*<span data-ttu-id="bbbea-225">그림 7.</span><span class="sxs-lookup"><span data-stu-id="bbbea-225">Figure 7.</span></span> <span data-ttu-id="bbbea-226">로그 옵션 및 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="bbbea-226">Log option and save package</span></span>*

## <span data-ttu-id="bbbea-227">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bbbea-227">Next steps</span></span>

- [<span data-ttu-id="bbbea-228">비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용</span><span class="sxs-lookup"><span data-stu-id="bbbea-228">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="bbbea-229">명령을 사용 하 여 비즈니스를 위한 Surface 진단 도구 키트 사용</span><span class="sxs-lookup"><span data-stu-id="bbbea-229">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="bbbea-230">변경 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="bbbea-230">Changes and updates</span></span>

### <span data-ttu-id="bbbea-231">버전 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="bbbea-231">Version 2.94.139.0</span></span>
*<span data-ttu-id="bbbea-232">릴리스 날짜: 5 월 11 일 2020</span><span class="sxs-lookup"><span data-stu-id="bbbea-232">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="bbbea-233">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="bbbea-234">Windows 업데이트를 건너뛰고 하드웨어 검사를 수행 하는 기능</span><span class="sxs-lookup"><span data-stu-id="bbbea-234">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="bbbea-235">최신 버전 업데이트에 대 한 알림을 받을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="bbbea-235">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="bbbea-236">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="bbbea-236">Surface Go 2</span></span>
- <span data-ttu-id="bbbea-237">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="bbbea-237">Surface Book 3</span></span>
- <span data-ttu-id="bbbea-238">진행률 표시기 표시</span><span class="sxs-lookup"><span data-stu-id="bbbea-238">Show progress indicator</span></span>


### <span data-ttu-id="bbbea-239">버전 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="bbbea-239">Version 2.43.139.0</span></span>
*<span data-ttu-id="bbbea-240">릴리스 날짜: 2019 년 10 월 21 일</span><span class="sxs-lookup"><span data-stu-id="bbbea-240">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="bbbea-241">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="bbbea-242">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="bbbea-242">Surface Pro 7</span></span>
- <span data-ttu-id="bbbea-243">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="bbbea-243">Surface Laptop 3</span></span>

### <span data-ttu-id="bbbea-244">버전 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="bbbea-244">Version 2.42.139.0</span></span>
*<span data-ttu-id="bbbea-245">릴리스 날짜: 2019 년 9 월 24 일</span><span class="sxs-lookup"><span data-stu-id="bbbea-245">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="bbbea-246">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-246">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="bbbea-247">하드웨어 보고서를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-247">Ability to download hardware reports.</span></span>
- <span data-ttu-id="bbbea-248">도구에서 바로 Microsoft Support에 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-248">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="bbbea-249">버전 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="bbbea-249">Version 2.41.139.0</span></span>
*<span data-ttu-id="bbbea-250">릴리스 날짜: 2019 년 6 월 24 일</span><span class="sxs-lookup"><span data-stu-id="bbbea-250">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="bbbea-251">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-251">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="bbbea-252">로그 및 보고서에 포함 된 드라이버 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-252">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="bbbea-253">앱에 대 한 피드백을 제공 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-253">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="bbbea-254">버전 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="bbbea-254">Version 2.36.139.0</span></span>
*<span data-ttu-id="bbbea-255">릴리스 날짜: 2019 년 4 월 26 일</span><span class="sxs-lookup"><span data-stu-id="bbbea-255">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="bbbea-256">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="bbbea-257">명령줄 구성을 요구 하지 않고 설치 관리자 UI를 통해 관리 기능을 잠금 해제 하는 고급 설정 옵션</span><span class="sxs-lookup"><span data-stu-id="bbbea-257">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="bbbea-258">접근성 개선.</span><span class="sxs-lookup"><span data-stu-id="bbbea-258">Accessibility improvements.</span></span>
- <span data-ttu-id="bbbea-259">화면 밝기 제어 설정이 로그에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-259">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="bbbea-260">보고서 생성기의 외부 모니터 호환성 지원 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="bbbea-260">External monitor compatibility support link in report generator.</span></span>
