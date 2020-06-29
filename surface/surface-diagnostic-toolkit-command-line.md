---
title: 명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행
description: 명령 콘솔에서 Surface 진단 도구 키트를 실행 하는 방법
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834295"
---
# <span data-ttu-id="f7cd4-103">명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행</span><span class="sxs-lookup"><span data-stu-id="f7cd4-103">Run Surface Diagnostic Toolkit for Business using commands</span></span>

<span data-ttu-id="f7cd4-104">명령 프롬프트에서 SDT (Surface 진단 도구 키트)를 실행 하려면 STD 앱 콘솔을 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-104">Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the STD app console.</span></span> <span data-ttu-id="f7cd4-105">설치 된 후에는 명령 프롬프트에서 Windows 명령 콘솔 (cmd.exe) 또는 windows PowerShell을 사용 하 여 명령에 대 한 자동 완성, 복사/붙여넣기 및 기타 기능에 대 한 지원을 제공 하는 ISE (PowerShell 통합 스크립팅 환경)를 통해 SDT를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-105">After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.</span></span>  <span data-ttu-id="f7cd4-106">SDT의 지원 되는 Surface 디바이스 목록은 [비즈니스용 배포 Surface 진단 툴킷](surface-diagnostic-toolkit-business.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>

>[!NOTE]
><span data-ttu-id="f7cd4-107">명령을 사용 하 여 SDT를 실행 하려면 관리자 계정에 로그인 하거나 Surface device의 관리자 그룹 구성원 인 계정에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-107">To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.</span></span>

## <span data-ttu-id="f7cd4-108">SDT 앱 콘솔 실행</span><span class="sxs-lookup"><span data-stu-id="f7cd4-108">Running SDT app console</span></span>

<span data-ttu-id="f7cd4-109">[IT 다운로드 화면 도구](https://www.microsoft.com/download/details.aspx?id=46703)에서 sdt 앱 콘솔을 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-109">Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="f7cd4-110">Windows 명령 프롬프트 (cmd.exe) 또는 Windows PowerShell을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-110">You can use the Windows command prompt (cmd.exe) or Windows PowerShell to:</span></span> 

- <span data-ttu-id="f7cd4-111">모든 로그 파일을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-111">Collect all log files.</span></span>
- <span data-ttu-id="f7cd4-112">모범 사례 분석기를 사용 하 여 상태 진단을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-112">Run health diagnostics using Best Practice Analyzer.</span></span>
- <span data-ttu-id="f7cd4-113">누락 된 펌웨어 또는 드라이버 업데이트에 대 한 업데이트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-113">Check update for missing firmware or driver updates.</span></span>

>[!NOTE]
><span data-ttu-id="f7cd4-114">이 릴리스에서는 SDT 앱 콘솔에서 단일 명령만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-114">In this release, the SDT app console supports single commands only.</span></span> <span data-ttu-id="f7cd4-115">명령줄 옵션을 여러 개 실행 하려면 각 명령에 대해 개별적으로 콘솔 exe를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-115">Running multiple command line options requires running the console exe separately for each command.</span></span> 

<span data-ttu-id="f7cd4-116">기본적으로 출력 파일은 콘솔 앱과 같은 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-116">By default, output files are saved in the same location as the console app.</span></span> <span data-ttu-id="f7cd4-117">명령에 대 한 전체 목록은 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-117">Refer to the following table for a complete list of commands.</span></span>

<span data-ttu-id="f7cd4-118">명령</span><span class="sxs-lookup"><span data-stu-id="f7cd4-118">Command</span></span> | <span data-ttu-id="f7cd4-119">참고</span><span class="sxs-lookup"><span data-stu-id="f7cd4-119">Notes</span></span>
--- | ---
<span data-ttu-id="f7cd4-120">-DataCollector "출력 파일"</span><span class="sxs-lookup"><span data-stu-id="f7cd4-120">-DataCollector "output file"</span></span> | <span data-ttu-id="f7cd4-121">시스템 세부 정보를 zip 파일로 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-121">Collects system details into a zip file.</span></span> <span data-ttu-id="f7cd4-122">"출력 파일"은 시스템 정보 zip 파일을 만들기 위한 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-122">"output file" is the file path to create system details zip file.</span></span><br><br><span data-ttu-id="f7cd4-123">**예**:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-123">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
<span data-ttu-id="f7cd4-124">-bpa "출력 파일"</span><span class="sxs-lookup"><span data-stu-id="f7cd4-124">-bpa "output file"</span></span> | <span data-ttu-id="f7cd4-125">장치에서 여러 설정 및 상태 표시기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-125">Checks several settings and health indicators in the device.</span></span> <span data-ttu-id="f7cd4-126">"출력 파일"은 HTML 보고서를 만들기 위한 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-126">“output file" is the file path to create the HTML report.</span></span><br><br><span data-ttu-id="f7cd4-127">**예**:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-127">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
<span data-ttu-id="f7cd4-128">-windows</span><span class="sxs-lookup"><span data-stu-id="f7cd4-128">-windowsupdate</span></span> | <span data-ttu-id="f7cd4-129">Windows Update online 서버에 누락 된 펌웨어 및/또는 드라이버 업데이트가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-129">Checks Windows Update online servers for missing firmware and/or driver updates.</span></span><br><br><span data-ttu-id="f7cd4-130">**예**:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-130">**Example**:</span></span><br><span data-ttu-id="f7cd4-131">Microsoft.Surface.Diagnostics.App.Console.exe-windows</span><span class="sxs-lookup"><span data-stu-id="f7cd4-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span></span>
<span data-ttu-id="f7cd4-132">-무상 수리 "출력 파일"</span><span class="sxs-lookup"><span data-stu-id="f7cd4-132">-warranty "output file"</span></span> | <span data-ttu-id="f7cd4-133">장치에 대 한 무상 수리 정보를 확인 합니다 (유효 하거나 유효 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="f7cd4-133">Checks warranty information on the device (valid or invalid).</span></span> <span data-ttu-id="f7cd4-134">선택적 "출력 파일"은 xml 파일을 만들기 위한 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-134">The optional “output file” is the file path to create the xml file.</span></span> <br><br><span data-ttu-id="f7cd4-135">**예**:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-135">**Example**:</span></span> <br><span data-ttu-id="f7cd4-136">Microsoft.Surface.Diagnostics.App.Console.exe – 무상 수리 "warranty.xml"</span><span class="sxs-lookup"><span data-stu-id="f7cd4-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”</span></span>


>[!NOTE]
><span data-ttu-id="f7cd4-137">대상 장치에서 원격으로 SDT 앱 콘솔을 실행 하려면 Microsoft 끝점 구성 관리자와 같은 구성 관리 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-137">To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="f7cd4-138">또는 콘솔 앱과 적절 한 콘솔 명령을 포함 하는 .zip 파일을 만들고 조직의 소프트웨어 배포 프로세스에 따라 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-138">Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.</span></span> 

## <span data-ttu-id="f7cd4-139">모범 사례 분석기 실행</span><span class="sxs-lookup"><span data-stu-id="f7cd4-139">Running Best Practice Analyzer</span></span> 

<span data-ttu-id="f7cd4-140">BitLocker, 보안 부팅, TPM (신뢰할 수 있는 플랫폼 모듈) 등의 주요 구성 요소에 대해 BPA 테스트를 실행 한 다음 해당 결과를 공유 가능한 파일에 출력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-140">You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file.</span></span> <span data-ttu-id="f7cd4-141">이 도구는 색으로 구분 된 제목 및 조건 설명자와 문제 해결 방법에 대 한 지침과 함께 일련의 표를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-141">The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.</span></span> 

- <span data-ttu-id="f7cd4-142">녹색은 구성 요소가 최적의 조건으로 실행 중임을 나타냅니다 (최적).</span><span class="sxs-lookup"><span data-stu-id="f7cd4-142">Green indicates the component is running in an optimal condition (optimal).</span></span>
- <span data-ttu-id="f7cd4-143">주황색은 구성 요소가 최적의 조건으로 실행 되 고 있지 않음을 나타냅니다 (최적화 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="f7cd4-143">Orange indicates the component is not running in an optimal condition (not optimal).</span></span>
- <span data-ttu-id="f7cd4-144">빨간색은 구성 요소가 비정상 상태임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-144">Red indicates the component is in an abnormal state.</span></span> 

### <span data-ttu-id="f7cd4-145">샘플 BPA 결과 출력</span><span class="sxs-lookup"><span data-stu-id="f7cd4-145">Sample BPA results output</span></span>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-146">BitLocker</span><span class="sxs-lookup"><span data-stu-id="f7cd4-146">BitLocker</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-147">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-147">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-148">시스템 드라이브에서 BitLocker를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-148">Checks if BitLocker is enabled on the system drive.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-149">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-149">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-150">보호 설정</span><span class="sxs-lookup"><span data-stu-id="f7cd4-150">Protection On</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-151">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-151">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-152">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-152">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-153">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-153">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-154">BitLocker를 사용 하 여 데이터를 보호할 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-154">It is highly recommended to enable BitLocker to protect your data.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-155">보안 부팅</span><span class="sxs-lookup"><span data-stu-id="f7cd4-155">Secure Boot</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-156">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-156">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-157">보안 부팅이 활성화 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-157">Checks if Secure Boot is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-158">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-158">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-159">True</span><span class="sxs-lookup"><span data-stu-id="f7cd4-159">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-160">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-160">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-161">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-161">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-162">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-162">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-163">PC를 보호 하기 위해 보안 부팅을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-163">It is highly recommended to enable Secure Boot to protect your PC.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-164">신뢰할 수 있는 플랫폼 모듈</span><span class="sxs-lookup"><span data-stu-id="f7cd4-164">Trusted Platform Module</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-165">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-165">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-166">TPM이 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-166">Ensures that the TPM is functional.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-167">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-167">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-168">True</span><span class="sxs-lookup"><span data-stu-id="f7cd4-168">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-169">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-169">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-170">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-170">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-171">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-171">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-172">기능적 TPM이 없으면 BitLocker와 같은 보안 기반 기능이 제대로 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-172">Without a functional TPM, security-based functions such as BitLocker may not work properly.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-173">연결 된 대기 상태</span><span class="sxs-lookup"><span data-stu-id="f7cd4-173">Connected Standby</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-174">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-174">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-175">연결 된 대기 모드가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-175">Checks if Connected Standby is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-176">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-176">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-177">True</span><span class="sxs-lookup"><span data-stu-id="f7cd4-177">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-178">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-178">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-179">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-179">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-180">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-180">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-181">연결 된 대기 모드에서는 Surface 장치에서 사용 하지 않는 동안 업데이트 및 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-181">Connected Standby allows a Surface device to receive updates and notifications while not being used.</span></span> <span data-ttu-id="f7cd4-182">최상의 환경을 위해서는 연결 된 대기 모드를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-182">For best experience, Connected Standby should be enabled.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-183">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f7cd4-183">Bluetooth</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-184">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-184">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-185">Bluetooth를 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-185">Checks if Bluetooth is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-186">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-186">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-187">설정됨</span><span class="sxs-lookup"><span data-stu-id="f7cd4-187">Enabled</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-188">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-188">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-189">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-189">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-190">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-190">Guidance:</span></span></strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-191">디버그 모드</span><span class="sxs-lookup"><span data-stu-id="f7cd4-191">Debug Mode</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-192">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-192">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-193">운영 체제가 디버그 모드 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-193">Checks if the operating system is in Debug mode.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-194">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-194">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-195">중</span><span class="sxs-lookup"><span data-stu-id="f7cd4-195">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-196">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-196">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-197">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-197">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-198">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-198">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-199">디버그 부팅 옵션은 Windows 운영 체제의 커널 디버깅을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-199">The debug boot option enables or disables kernel debugging of the Windows operating system.</span></span> <span data-ttu-id="f7cd4-200">이 옵션을 사용 하도록 설정 하면 시스템이 불안정 해질 수 있으며 DRM (디지털 권한 managemend)이 재생 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-200">Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-201">서명 테스트</span><span class="sxs-lookup"><span data-stu-id="f7cd4-201">Test Signing</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-202">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-202">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-203">테스트 서명이 활성화 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-203">Checks if Test Signing is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-204">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-204">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-205">중</span><span class="sxs-lookup"><span data-stu-id="f7cd4-205">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-206">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-206">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-207">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-207">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-208">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-208">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-209">서명 테스트는 시험판 드라이버를 테스트 하는 데만 사용 해야 하는 Windows 시작 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-209">Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-210">현재 전원 관리 옵션</span><span class="sxs-lookup"><span data-stu-id="f7cd4-210">Active Power Plan</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-211">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-211">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-212">올바른 전원 계획이 활성화 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-212">Checks that the correct power plan is active.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-213">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-213">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-214">적절</span><span class="sxs-lookup"><span data-stu-id="f7cd4-214">Balanced</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-215">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-215">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-216">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-216">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-217">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-217">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-218">"균형" 전원 관리 옵션을 사용 하 여 생산성과 배터리 수명을 최대화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-218">It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500"><span data-ttu-id="f7cd4-219">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="f7cd4-219">Windows Update</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-220">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-220">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-221">장치가 Windows 업데이트를 사용 하 여 최신 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-221">Checks if the device is up to date with Windows updates.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-222">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-222">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-223">Microsoft Silverlight (KB4023307), Windows Defender Antivirus 용 정의 업데이트-KB2267602 (정의 1.279.1433.0)</span><span class="sxs-lookup"><span data-stu-id="f7cd4-223">Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-224">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-224">Condition:</span></span></strong></td><td><font color="ff9500"><span data-ttu-id="f7cd4-225">최적이 아님</span><span class="sxs-lookup"><span data-stu-id="f7cd4-225">Not Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-226">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-226">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-227">최신 windows로 업데이트 하면 최신 펌웨어와 드라이버를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-227">Updating to the latest windows makes sure you are on the latest firmware and drivers.</span></span> <span data-ttu-id="f7cd4-228">장치를 항상 최신 상태로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-228">It is recommended to always keep your device up to date</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-229">무료 하드 드라이브 공간</span><span class="sxs-lookup"><span data-stu-id="f7cd4-229">Free Hard Drive Space</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-230">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-230">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-231">사용 가능한 하드 드라이브 공간이 부족 한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-231">Checks for low free hard drive space.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-232">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-232">Value:</span></span></strong></td><td><span data-ttu-id="f7cd4-233">66%</span><span class="sxs-lookup"><span data-stu-id="f7cd4-233">66%</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-234">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-234">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-235">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-235">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-236">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-236">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-237">최상의 성능을 위해 하드 드라이브에는 사용 가능한 공간으로 최소한 10%의 용량이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-237">For best performance, your hard drive should have at least 10% of its capacity as free space.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-238">작동 하지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="f7cd4-238">Non-Functioning Devices</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-239">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-239">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-240">장치 관리자에서 작동 하지 않는 디바이스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-240">List of non-functioning devices in Device Manager.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-241">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-241">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-242">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-242">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-243">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-243">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-244">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-244">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-245">장치 관리자에서 작동 하지 않는 장치는 해당 하드웨어 구성 요소에 대 한 절전 기능을 제외한 화면 장치에서 예기치 않은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-245">Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="f7cd4-246">외부 모니터</span><span class="sxs-lookup"><span data-stu-id="f7cd4-246">External Monitor</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="f7cd4-247">설명:</span><span class="sxs-lookup"><span data-stu-id="f7cd4-247">Description:</span></span></strong></td><td><span data-ttu-id="f7cd4-248">호환성 문제가 있을 수 있는 외부 모니터가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-248">Checks for an external monitor that may have compatibility issues.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-249">값</span><span class="sxs-lookup"><span data-stu-id="f7cd4-249">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-250">상황이</span><span class="sxs-lookup"><span data-stu-id="f7cd4-250">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="f7cd4-251">위해</span><span class="sxs-lookup"><span data-stu-id="f7cd4-251">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="f7cd4-252">지침</span><span class="sxs-lookup"><span data-stu-id="f7cd4-252">Guidance:</span></span></strong></td><td><span data-ttu-id="f7cd4-253">원본 장비 제조업체에 문의 하 여 Surface 디바이스와의 호환성을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7cd4-253">Check with the original equipment manufacturer for compatibility with your Surface device.</span></span></td></tr>
</table>
