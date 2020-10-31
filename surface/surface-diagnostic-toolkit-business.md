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
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145963"
---
# <span data-ttu-id="8559d-103">비즈니스용 Surface 진단 도구 키트 배포</span><span class="sxs-lookup"><span data-stu-id="8559d-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="8559d-104">Microsoft Surface (비즈니스 관련 진단 도구 키트) (SDT)는 IT 관리자가 Surface 장치에서 하드웨어, 소프트웨어 및 펌웨어 문제를 빠르게 조사, 문제 해결 및 해결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="8559d-105">장치 상태 정보 활용 및 문제 해결에 대 한 지침을 얻고, 다양 한 진단 테스트 및 소프트웨어 복구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="8559d-106">특히, 비즈니스의 SDT에서는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="8559d-107">패키지를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="8559d-108">명령을 사용 하 여 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="8559d-109">여러 하드웨어 테스트를 실행 하 여 문제를 해결 하세요.</span><span class="sxs-lookup"><span data-stu-id="8559d-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="8559d-110">문제 분석을 위한 로그를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="8559d-111">디바이스 vs 최적의 구성을 비교 하는 자세한 보고서를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="8559d-112">기본 시나리오 및 다운로드 리소스</span><span class="sxs-lookup"><span data-stu-id="8559d-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="8559d-113">비즈니스에 대해 SDT를 실행 하려면 다음 표에 나열 된 구성 요소를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="8559d-114">모드</span><span class="sxs-lookup"><span data-stu-id="8559d-114">Mode</span></span> |  <span data-ttu-id="8559d-115">기본 시나리오</span><span class="sxs-lookup"><span data-stu-id="8559d-115">Primary scenarios</span></span> | <span data-ttu-id="8559d-116">다운로드</span><span class="sxs-lookup"><span data-stu-id="8559d-116">Download</span></span> | <span data-ttu-id="8559d-117">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="8559d-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="8559d-118">데스크톱 모드</span><span class="sxs-lookup"><span data-stu-id="8559d-118">Desktop mode</span></span> |  <span data-ttu-id="8559d-119">표면 장치에서 SDT를 실행 하는 사용자가 문제를 해결 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="8559d-120">사용자가 수집 하 고 분석할 특정 로그를 선택할 수 있도록 하나 이상의 Surface 장치에 배포 하는 사용자 지정 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="8559d-121">SDT 배포 가능 MSI 패키지:</span><span class="sxs-lookup"><span data-stu-id="8559d-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="8559d-122">비즈니스 설치 관리자 용 Microsoft Surface 진단 도구 키트</span><span class="sxs-lookup"><span data-stu-id="8559d-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="8559d-123">IT용 Surface 도구</span><span class="sxs-lookup"><span data-stu-id="8559d-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="8559d-124">데스크톱 모드에서 Surface 진단 도구 키트 사용</span><span class="sxs-lookup"><span data-stu-id="8559d-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="8559d-125">명령줄</span><span class="sxs-lookup"><span data-stu-id="8559d-125">Command line</span></span> |  <span data-ttu-id="8559d-126">구성 관리자와 같은 표준 도구를 사용 하 여 사용자 조작 없이 원격으로 Surface 디바이스의 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="8559d-127">여기에는 다음 명령이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="8559d-128">모든 로그 파일 수집</span><span class="sxs-lookup"><span data-stu-id="8559d-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="8559d-129">모범 사례 분석기를 사용 하 여 상태 진단을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="8559d-130">Windows 업데이트에서 누락 된 펌웨어 또는 드라이버 업데이트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="8559d-131">무상 수리 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="8559d-132">SDT 콘솔 앱:</span><span class="sxs-lookup"><span data-stu-id="8559d-132">SDT console app:</span></span><br><span data-ttu-id="8559d-133">Microsoft Surface Diagnostics 앱 콘솔</span><span class="sxs-lookup"><span data-stu-id="8559d-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="8559d-134">IT용 Surface 도구</span><span class="sxs-lookup"><span data-stu-id="8559d-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="8559d-135">명령을 사용 하 여 Surface 진단 도구 키트 실행</span><span class="sxs-lookup"><span data-stu-id="8559d-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="8559d-136">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="8559d-136">Supported devices</span></span> 

<span data-ttu-id="8559d-137">다음을 포함 하 여 Surface 3 및 이후 장치에서 비즈니스의 SDT가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="8559d-138">Surface 랩톱 이동</span><span class="sxs-lookup"><span data-stu-id="8559d-138">Surface Laptop Go</span></span>
- <span data-ttu-id="8559d-139">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="8559d-139">Surface Book 3</span></span>
- <span data-ttu-id="8559d-140">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="8559d-140">Surface Go 2</span></span>
- <span data-ttu-id="8559d-141">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="8559d-141">Surface Pro X</span></span>
- <span data-ttu-id="8559d-142">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8559d-142">Surface Pro 7</span></span>
- <span data-ttu-id="8559d-143">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="8559d-143">Surface Laptop 3</span></span>
- <span data-ttu-id="8559d-144">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="8559d-144">Surface Pro 6</span></span>
- <span data-ttu-id="8559d-145">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="8559d-145">Surface Laptop 2</span></span>
- <span data-ttu-id="8559d-146">Surface Go</span><span class="sxs-lookup"><span data-stu-id="8559d-146">Surface Go</span></span>
- <span data-ttu-id="8559d-147">LTE를 사용 하 여 Surface Go</span><span class="sxs-lookup"><span data-stu-id="8559d-147">Surface Go with LTE</span></span>
- <span data-ttu-id="8559d-148">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="8559d-148">Surface Book 2</span></span>
- <span data-ttu-id="8559d-149">Surface Pro LTE Advanced(모델 1807)</span><span class="sxs-lookup"><span data-stu-id="8559d-149">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="8559d-150">Surface Pro(모델 1796)</span><span class="sxs-lookup"><span data-stu-id="8559d-150">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="8559d-151">Surface 노트북</span><span class="sxs-lookup"><span data-stu-id="8559d-151">Surface Laptop</span></span>
- <span data-ttu-id="8559d-152">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="8559d-152">Surface Studio</span></span>
- <span data-ttu-id="8559d-153">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="8559d-153">Surface Studio 2</span></span>
- <span data-ttu-id="8559d-154">Surface Book</span><span class="sxs-lookup"><span data-stu-id="8559d-154">Surface Book</span></span>
- <span data-ttu-id="8559d-155">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8559d-155">Surface Pro 4</span></span>
- <span data-ttu-id="8559d-156">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="8559d-156">Surface 3 LTE</span></span>
- <span data-ttu-id="8559d-157">Surface 3</span><span class="sxs-lookup"><span data-stu-id="8559d-157">Surface 3</span></span>
- <span data-ttu-id="8559d-158">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="8559d-158">Surface Pro 3</span></span>

## <span data-ttu-id="8559d-159">비즈니스를 위한 Surface 진단 도구 키트 설치</span><span class="sxs-lookup"><span data-stu-id="8559d-159">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="8559d-160">조직의 사용자에 게 배포할 수 있는 SDT 패키지를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-160">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="8559d-161">관리자 계정을 사용 하 여 Surface device에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-161">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="8559d-162">[IT 다운로드 페이지의 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 Sdt Windows Installer 패키지 (.msi)를 다운로드 하 고 데스크톱 등의 surface 장치에서 원하는 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-162">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="8559d-163">SDT 설정 마법사가 표시 됩니다 (그림 1).</span><span class="sxs-lookup"><span data-stu-id="8559d-163">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="8559d-164">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-164">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="8559d-165">설치 마법사가 표시 되지 않으면 컴퓨터에서 관리자 계정에 로그인 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-165">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Surface 진단 도구 키트 설정 마법사 시작](images/sdt-1.png)

    *<span data-ttu-id="8559d-167">그림 1.</span><span class="sxs-lookup"><span data-stu-id="8559d-167">Figure 1.</span></span> <span data-ttu-id="8559d-168">Surface 진단 도구 키트 설정 마법사</span><span class="sxs-lookup"><span data-stu-id="8559d-168">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="8559d-169">SDT 설정 마법사가 나타나면 **다음**을 클릭 하 여 최종 사용자 사용권 계약 (EULA)에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-169">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="8559d-170">설치 옵션 화면에서 원하는 경우 기본 설치 위치를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-170">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="8559d-171">설치 유형 아래에서 **고급**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-171">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="8559d-172">표준 옵션을 사용 하면 관리자 계정으로 장치에 로그인 한 경우 사용자는 Surface device에서 진단 도구를 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-172">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![설치 옵션: 고급](images/sdt-install.png)

7. <span data-ttu-id="8559d-174">**다음** 을 클릭 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-174">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="8559d-175">명령줄을 사용 하 여 설치</span><span class="sxs-lookup"><span data-stu-id="8559d-175">Installing using the command line</span></span>
<span data-ttu-id="8559d-176">필요한 경우 명령 프롬프트에서 SDT를 설치 하 고 사용자 지정 플래그를 설정 하 여 해당 도구를 관리 모드로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-176">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="8559d-177">SDT에는 다음 설치 옵션 플래그가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-177">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="8559d-178">원격 분석 데이터를 Microsoft에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-178">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="8559d-179">플래그는 `0` 사용 안 함 또는 `1` 사용으로 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-179">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="8559d-180">기본값은 `1` 원격 분석을 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-180">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="8559d-181">관리 모드에서 설치 되도록 도구를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-181">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="8559d-182">플래그는 `0` 클라이언트 모드 또는 `1` IT 관리자 모드에 대해 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-182">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="8559d-183">기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-183">The default value is `0`.</span></span>

### <span data-ttu-id="8559d-184">명령줄에서 SDT를 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-184">To install SDT from the command line:</span></span>

1. <span data-ttu-id="8559d-185">명령 프롬프트를 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-185">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="8559d-186">예제:</span><span class="sxs-lookup"><span data-stu-id="8559d-186">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="8559d-187">Surface 장치에서 SDT 찾기</span><span class="sxs-lookup"><span data-stu-id="8559d-187">Locating SDT on your Surface device</span></span>

<span data-ttu-id="8559d-188">SDT 및 SDT 앱 콘솔 모두에 설치 됩니다 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="8559d-188">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="8559d-189">SDT는 .exe 파일 외에도 그림 2와 같이 JSON 파일과 admin.dll 파일 (modules\admin.dll)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-189">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![파일 탐색기에 설치 된 SDT의 파일 목록](images/sdt-2.png)

*<span data-ttu-id="8559d-191">그림 2.</span><span class="sxs-lookup"><span data-stu-id="8559d-191">Figure 2.</span></span> <span data-ttu-id="8559d-192">SDT에서 설치 된 파일</span><span class="sxs-lookup"><span data-stu-id="8559d-192">Files installed by SDT</span></span>*

## <span data-ttu-id="8559d-193">배포를 위해 SDT 패키지 준비</span><span class="sxs-lookup"><span data-stu-id="8559d-193">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="8559d-194">사용자 지정 패키지를 만들면 도구가 알려진 특정 문제를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-194">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="8559d-195">**시작 > 실행**을 클릭 하 고 **화면** 을 입력 한 다음 **surface 진단 도구 키트**를 클릭 하 여 비즈니스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-195">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="8559d-196">도구가 열리면 그림 3에 나와 있는 것 처럼 **사용자 지정 패키지 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-196">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![사용자 지정 패키지 만들기 옵션](images/sdt-3.png)

    *<span data-ttu-id="8559d-198">그림 3.</span><span class="sxs-lookup"><span data-stu-id="8559d-198">Figure 3.</span></span> <span data-ttu-id="8559d-199">사용자 지정 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="8559d-199">Create custom package</span></span>*

### <span data-ttu-id="8559d-200">언어 및 원격 분석 설정</span><span class="sxs-lookup"><span data-stu-id="8559d-200">Language and telemetry settings</span></span>

  <span data-ttu-id="8559d-201">패키지를 만들 때 언어 설정을 선택 하거나 Microsoft에 원격 분석 정보를 보내는 것을 옵트아웃 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-201">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="8559d-202">기본적으로 SDT는 [microsoft](https://privacy.microsoft.com/privacystatement)에 대 한 원격 분석을 전송 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-202">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="8559d-203">거절 하려는 경우 아래와 같이 사용자 지정 패키지를 만들 때 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-203">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="8559d-204">또는 SDT 설치 중 **옵션 설치** 페이지에서 **Microsoft로 원격 분석 보내기** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-204">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="8559d-205">이 설정은 Windows Update 및 소프트웨어 복구와 같은 인터넷 연결이 필요한 테스트 및 복구를 실행 하거나 앱 도구 모음에서 웃는 얼굴 또는 찡그린 얼굴 보내기 단추를 사용 하 여 피드백을 제공 하는 경우 Microsoft 서버에 자동으로 저장 되는 최소 원격 분석에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-205">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![언어 및 원격 분석 설정 선택](images/sdt-4.png)

*<span data-ttu-id="8559d-207">그림 4.</span><span class="sxs-lookup"><span data-stu-id="8559d-207">Figure 4.</span></span> <span data-ttu-id="8559d-208">언어 및 원격 분석 설정 선택</span><span class="sxs-lookup"><span data-stu-id="8559d-208">Select language and telemetry settings</span></span>*


### <span data-ttu-id="8559d-209">Windows 업데이트 페이지</span><span class="sxs-lookup"><span data-stu-id="8559d-209">Windows Update page</span></span>

<span data-ttu-id="8559d-210">조직에 적합 한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-210">Select the option appropriate for your organization.</span></span> <span data-ttu-id="8559d-211">일반적으로 여러 사용자가 있는 조직에서는 그림 5와 같이 WSUS (Windows Server Update Services)를 통해 업데이트를 받도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-211">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="8559d-212">로컬 Windows 업데이트 패키지 또는 WSUS를 사용 하는 경우 적절 하 게 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-212">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Windows 업데이트 옵션 선택](images/sdt-5.png)

*<span data-ttu-id="8559d-214">그림 5.</span><span class="sxs-lookup"><span data-stu-id="8559d-214">Figure 5.</span></span> <span data-ttu-id="8559d-215">Windows 업데이트 옵션</span><span class="sxs-lookup"><span data-stu-id="8559d-215">Windows Update option</span></span>*

### <span data-ttu-id="8559d-216">소프트웨어 복구 페이지</span><span class="sxs-lookup"><span data-stu-id="8559d-216">Software repair page</span></span>

<span data-ttu-id="8559d-217">이렇게 하면 소프트웨어 복구 업데이트를 실행 하는 옵션을 선택 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-217">This allows you to select or remove the option to run software repair updates.</span></span> 

![소프트웨어 복구 옵션 선택](images/sdt-6.png)

*<span data-ttu-id="8559d-219">그림 6.</span><span class="sxs-lookup"><span data-stu-id="8559d-219">Figure 6.</span></span> <span data-ttu-id="8559d-220">소프트웨어 복구 옵션</span><span class="sxs-lookup"><span data-stu-id="8559d-220">Software repair option</span></span>*

### <span data-ttu-id="8559d-221">로그 수집 및 패키지 저장 페이지</span><span class="sxs-lookup"><span data-stu-id="8559d-221">Collecting logs and saving package page</span></span>

<span data-ttu-id="8559d-222">다양 한 로그를 응용 프로그램, 드라이버, 하드웨어 및 운영 체제 간에 실행 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-222">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="8559d-223">적절 한 영역을 클릭 하 고 사용 가능한 로그 메뉴에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-223">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="8559d-224">그런 다음 패키지를 사용자가 액세스할 수 있는 소프트웨어 배포 지점이 나 동등한 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-224">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![로그 옵션 선택](images/sdt-7.png)

*<span data-ttu-id="8559d-226">그림 7.</span><span class="sxs-lookup"><span data-stu-id="8559d-226">Figure 7.</span></span> <span data-ttu-id="8559d-227">로그 옵션 및 패키지 저장</span><span class="sxs-lookup"><span data-stu-id="8559d-227">Log option and save package</span></span>*

## <span data-ttu-id="8559d-228">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8559d-228">Next steps</span></span>

- [<span data-ttu-id="8559d-229">비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용</span><span class="sxs-lookup"><span data-stu-id="8559d-229">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="8559d-230">명령을 사용 하 여 비즈니스를 위한 Surface 진단 도구 키트 사용</span><span class="sxs-lookup"><span data-stu-id="8559d-230">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="8559d-231">변경 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="8559d-231">Changes and updates</span></span>

### <span data-ttu-id="8559d-232">버전 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="8559d-232">Version 2.124.139.0</span></span>

<span data-ttu-id="8559d-233">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8559d-234">원활한 통합 지원</span><span class="sxs-lookup"><span data-stu-id="8559d-234">Seamless integrated support</span></span>
- <span data-ttu-id="8559d-235">모든 테스트 결과 저장</span><span class="sxs-lookup"><span data-stu-id="8559d-235">Save all test results</span></span>
- <span data-ttu-id="8559d-236">이미지가 사용자 지정 만들어졌는지 확인</span><span class="sxs-lookup"><span data-stu-id="8559d-236">Check if the image is custom created</span></span>
- <span data-ttu-id="8559d-237">장치 관리자에서 경고 포함</span><span class="sxs-lookup"><span data-stu-id="8559d-237">Include warnings from device manager</span></span>
- <span data-ttu-id="8559d-238">Dock 펌웨어 버전</span><span class="sxs-lookup"><span data-stu-id="8559d-238">Dock firmware version</span></span>
- <span data-ttu-id="8559d-239">드라이브에 저장소 테스트의 잠재적인 오류로 플래그 지정</span><span class="sxs-lookup"><span data-stu-id="8559d-239">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="8559d-240">스토어 링크 제거</span><span class="sxs-lookup"><span data-stu-id="8559d-240">Remove store link</span></span> 

### <span data-ttu-id="8559d-241">버전 2.121.139</span><span class="sxs-lookup"><span data-stu-id="8559d-241">Version 2.121.139</span></span>
*<span data-ttu-id="8559d-242">릴리스 날짜: 31 2020 년 7 월</span><span class="sxs-lookup"><span data-stu-id="8559d-242">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="8559d-243">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-243">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8559d-244">원활한 지원 환경</span><span class="sxs-lookup"><span data-stu-id="8559d-244">Seamless support experience</span></span>
- <span data-ttu-id="8559d-245">버그 수정</span><span class="sxs-lookup"><span data-stu-id="8559d-245">Bug fixes</span></span>

### <span data-ttu-id="8559d-246">버전 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="8559d-246">Version 2.94.139.0</span></span>
*<span data-ttu-id="8559d-247">릴리스 날짜: 5 월 11 일 2020</span><span class="sxs-lookup"><span data-stu-id="8559d-247">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="8559d-248">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-248">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8559d-249">Windows 업데이트를 건너뛰고 하드웨어 검사를 수행 하는 기능</span><span class="sxs-lookup"><span data-stu-id="8559d-249">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="8559d-250">최신 버전 업데이트에 대 한 알림을 받을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="8559d-250">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="8559d-251">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="8559d-251">Surface Go 2</span></span>
- <span data-ttu-id="8559d-252">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="8559d-252">Surface Book 3</span></span>
- <span data-ttu-id="8559d-253">진행률 표시기 표시</span><span class="sxs-lookup"><span data-stu-id="8559d-253">Show progress indicator</span></span>


### <span data-ttu-id="8559d-254">버전 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="8559d-254">Version 2.43.139.0</span></span>
*<span data-ttu-id="8559d-255">릴리스 날짜: 2019 년 10 월 21 일</span><span class="sxs-lookup"><span data-stu-id="8559d-255">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="8559d-256">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8559d-257">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8559d-257">Surface Pro 7</span></span>
- <span data-ttu-id="8559d-258">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="8559d-258">Surface Laptop 3</span></span>

### <span data-ttu-id="8559d-259">버전 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="8559d-259">Version 2.42.139.0</span></span>
*<span data-ttu-id="8559d-260">릴리스 날짜: 2019 년 9 월 24 일</span><span class="sxs-lookup"><span data-stu-id="8559d-260">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="8559d-261">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="8559d-262">하드웨어 보고서를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-262">Ability to download hardware reports.</span></span>
- <span data-ttu-id="8559d-263">도구에서 바로 Microsoft Support에 문의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-263">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="8559d-264">버전 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="8559d-264">Version 2.41.139.0</span></span>
*<span data-ttu-id="8559d-265">릴리스 날짜: 2019 년 6 월 24 일</span><span class="sxs-lookup"><span data-stu-id="8559d-265">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="8559d-266">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-266">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="8559d-267">로그 및 보고서에 포함 된 드라이버 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-267">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="8559d-268">앱에 대 한 피드백을 제공 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-268">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="8559d-269">버전 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="8559d-269">Version 2.36.139.0</span></span>
*<span data-ttu-id="8559d-270">릴리스 날짜: 2019 년 4 월 26 일</span><span class="sxs-lookup"><span data-stu-id="8559d-270">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="8559d-271">이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-271">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="8559d-272">명령줄 구성을 요구 하지 않고 설치 관리자 UI를 통해 관리 기능을 잠금 해제 하는 고급 설정 옵션</span><span class="sxs-lookup"><span data-stu-id="8559d-272">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="8559d-273">접근성 개선.</span><span class="sxs-lookup"><span data-stu-id="8559d-273">Accessibility improvements.</span></span>
- <span data-ttu-id="8559d-274">화면 밝기 제어 설정이 로그에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-274">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="8559d-275">보고서 생성기의 외부 모니터 호환성 지원 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="8559d-275">External monitor compatibility support link in report generator.</span></span>
