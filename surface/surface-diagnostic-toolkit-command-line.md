---
title: 명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행
description: 명령 콘솔에서 Surface 진단 Toolkit 실행 방법
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327332"
---
# <span data-ttu-id="4377c-103">명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행</span><span class="sxs-lookup"><span data-stu-id="4377c-103">Run Surface Diagnostic Toolkit for Business using commands</span></span>

<span data-ttu-id="4377c-104">명령 프롬프트에서 SDT(Surface Diagnostic Toolkit)를 실행하려면 SDT 앱 콘솔을 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-104">Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the SDT app console.</span></span> <span data-ttu-id="4377c-105">설치 후 Windows 명령 콘솔(cmd.exe)을 통해 명령 프롬프트에서 또는 명령, 복사/붙여넣기 및 기타 기능의 자동 Windows PowerShell 기능을 제공하는 PowerShell ISE(통합 스크립팅 환경)를 포함하여 SDT를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-105">After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.</span></span>  <span data-ttu-id="4377c-106">SDT에서 지원되는 Surface 디바이스 목록은 비즈니스용 Surface 진단 Toolkit [참조하세요.](surface-diagnostic-toolkit-business.md)</span><span class="sxs-lookup"><span data-stu-id="4377c-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>

>[!NOTE]
><span data-ttu-id="4377c-107">명령을 사용하여 SDT를 실행하려면 관리자 계정에 로그인하거나 Surface 디바이스에서 Administrator 그룹의 구성원인 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-107">To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.</span></span>

## <span data-ttu-id="4377c-108">SDT 앱 콘솔 실행</span><span class="sxs-lookup"><span data-stu-id="4377c-108">Running SDT app console</span></span>

<span data-ttu-id="4377c-109">Surface Tools for IT 다운로드 페이지에서 SDT 앱 [콘솔을 다운로드하여 설치합니다.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="4377c-109">Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="4377c-110">Windows 명령 프롬프트(cmd.exe)를 사용하여 다음을 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-110">You can use the Windows command prompt (cmd.exe) or Windows PowerShell to:</span></span> 

- <span data-ttu-id="4377c-111">모든 로그 파일을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-111">Collect all log files.</span></span>
- <span data-ttu-id="4377c-112">모범 사례 분석기를 사용하여 상태 진단을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-112">Run health diagnostics using Best Practice Analyzer.</span></span>
- <span data-ttu-id="4377c-113">펌웨어 또는 드라이버 업데이트가 누락되어 있는지 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-113">Check update for missing firmware or driver updates.</span></span>

>[!NOTE]
><span data-ttu-id="4377c-114">이 릴리스에서 SDT 앱 콘솔은 단일 명령만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-114">In this release, the SDT app console supports single commands only.</span></span> <span data-ttu-id="4377c-115">여러 명령줄 옵션을 실행하려면 각 명령에 대해 콘솔 exe를 별도로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-115">Running multiple command line options requires running the console exe separately for each command.</span></span> 

<span data-ttu-id="4377c-116">기본적으로 출력 파일은 콘솔 앱과 동일한 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-116">By default, output files are saved in the same location as the console app.</span></span> <span data-ttu-id="4377c-117">전체 명령 목록은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4377c-117">Refer to the following table for a complete list of commands.</span></span>

<span data-ttu-id="4377c-118">명령</span><span class="sxs-lookup"><span data-stu-id="4377c-118">Command</span></span> | <span data-ttu-id="4377c-119">참고</span><span class="sxs-lookup"><span data-stu-id="4377c-119">Notes</span></span>
--- | ---
<span data-ttu-id="4377c-120">-DataCollector "출력 파일"</span><span class="sxs-lookup"><span data-stu-id="4377c-120">-DataCollector "output file"</span></span> | <span data-ttu-id="4377c-121">시스템 세부 정보를 zip 파일로 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-121">Collects system details into a zip file.</span></span> <span data-ttu-id="4377c-122">"출력 파일"은 시스템 세부 정보 zip 파일을 만드는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-122">"output file" is the file path to create system details zip file.</span></span><br><br><span data-ttu-id="4377c-123">**예**:</span><span class="sxs-lookup"><span data-stu-id="4377c-123">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
<span data-ttu-id="4377c-124">-bpa "출력 파일"</span><span class="sxs-lookup"><span data-stu-id="4377c-124">-bpa "output file"</span></span> | <span data-ttu-id="4377c-125">디바이스의 여러 설정 및 상태 표시기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-125">Checks several settings and health indicators in the device.</span></span> <span data-ttu-id="4377c-126">"출력 파일"은 HTML 보고서를 만드는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-126">“output file" is the file path to create the HTML report.</span></span><br><br><span data-ttu-id="4377c-127">**예**:</span><span class="sxs-lookup"><span data-stu-id="4377c-127">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
<span data-ttu-id="4377c-128">-windowsupdate</span><span class="sxs-lookup"><span data-stu-id="4377c-128">-windowsupdate</span></span> | <span data-ttu-id="4377c-129">Windows 업데이트 온라인 서버에서 펌웨어 및/또는 드라이버 업데이트가 누락되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-129">Checks Windows Update online servers for missing firmware and/or driver updates.</span></span><br><br><span data-ttu-id="4377c-130">**예**:</span><span class="sxs-lookup"><span data-stu-id="4377c-130">**Example**:</span></span><br><span data-ttu-id="4377c-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span><span class="sxs-lookup"><span data-stu-id="4377c-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span></span>
<span data-ttu-id="4377c-132">-warranty "output file"</span><span class="sxs-lookup"><span data-stu-id="4377c-132">-warranty "output file"</span></span> | <span data-ttu-id="4377c-133">장치에서 보증 정보를 확인합니다(유효하거나 잘못).</span><span class="sxs-lookup"><span data-stu-id="4377c-133">Checks warranty information on the device (valid or invalid).</span></span> <span data-ttu-id="4377c-134">선택적 "출력 파일"은 xml 파일을 만드는 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-134">The optional “output file” is the file path to create the xml file.</span></span> <br><br><span data-ttu-id="4377c-135">**예**:</span><span class="sxs-lookup"><span data-stu-id="4377c-135">**Example**:</span></span> <br><span data-ttu-id="4377c-136">Microsoft.Surface.Diagnostics.App.Console.exe –보증 "warranty.xml"</span><span class="sxs-lookup"><span data-stu-id="4377c-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”</span></span>


>[!NOTE]
><span data-ttu-id="4377c-137">대상 디바이스에서 원격으로 SDT 앱 콘솔을 실행하려면 Microsoft Endpoint Configuration Manager와 같은 구성 관리 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-137">To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="4377c-138">또는 콘솔 앱 및 적절한 콘솔 명령을 포함하는 .zip 파일을 만들고 조직의 소프트웨어 배포 프로세스에 따라 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-138">Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.</span></span> 

## <span data-ttu-id="4377c-139">모범 사례 분석기 실행</span><span class="sxs-lookup"><span data-stu-id="4377c-139">Running Best Practice Analyzer</span></span> 

<span data-ttu-id="4377c-140">BitLocker, 보안 부팅 및 TPM(신뢰할 수 있는 플랫폼 모듈)과 같은 주요 구성 요소에서 BPA 테스트를 실행한 다음 공유 가능한 파일에 결과를 출력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-140">You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file.</span></span> <span data-ttu-id="4377c-141">이 도구는 색으로 코딩된 제목과 조건 설명자가 있는 일련의 표를 생성하고 문제 해결 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-141">The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.</span></span> 

- <span data-ttu-id="4377c-142">녹색은 구성 요소가 최적의 조건(최적)에서 실행되고 있는 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-142">Green indicates the component is running in an optimal condition (optimal).</span></span>
- <span data-ttu-id="4377c-143">주황색은 구성 요소가 최적의 조건(최적화되지 않은)에서 실행되고 있지 않다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-143">Orange indicates the component is not running in an optimal condition (not optimal).</span></span>
- <span data-ttu-id="4377c-144">빨간색은 구성 요소가 비정상 상태인 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-144">Red indicates the component is in an abnormal state.</span></span> 

### <span data-ttu-id="4377c-145">샘플 BPA 결과 출력</span><span class="sxs-lookup"><span data-stu-id="4377c-145">Sample BPA results output</span></span>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-146">BitLocker</span><span class="sxs-lookup"><span data-stu-id="4377c-146">BitLocker</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-147">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-147">Description:</span></span></strong></td><td><span data-ttu-id="4377c-148">시스템 드라이브에서 BitLocker가 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-148">Checks if BitLocker is enabled on the system drive.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-149">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-149">Value:</span></span></strong></td><td><span data-ttu-id="4377c-150">보호 기능</span><span class="sxs-lookup"><span data-stu-id="4377c-150">Protection On</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-151">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-151">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-152">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-152">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-153">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-153">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-154">BitLocker를 사용하여 데이터를 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-154">It is highly recommended to enable BitLocker to protect your data.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-155">보안 부팅</span><span class="sxs-lookup"><span data-stu-id="4377c-155">Secure Boot</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-156">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-156">Description:</span></span></strong></td><td><span data-ttu-id="4377c-157">보안 부팅이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-157">Checks if Secure Boot is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-158">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-158">Value:</span></span></strong></td><td><span data-ttu-id="4377c-159">True</span><span class="sxs-lookup"><span data-stu-id="4377c-159">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-160">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-160">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-161">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-161">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-162">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-162">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-163">PC를 보호하기 위해 보안 부팅을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-163">It is highly recommended to enable Secure Boot to protect your PC.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-164">신뢰할 수 있는 플랫폼 모듈</span><span class="sxs-lookup"><span data-stu-id="4377c-164">Trusted Platform Module</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-165">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-165">Description:</span></span></strong></td><td><span data-ttu-id="4377c-166">TPM이 작동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-166">Ensures that the TPM is functional.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-167">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-167">Value:</span></span></strong></td><td><span data-ttu-id="4377c-168">True</span><span class="sxs-lookup"><span data-stu-id="4377c-168">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-169">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-169">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-170">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-170">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-171">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-171">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-172">기능 TPM이 없는 경우 BitLocker와 같은 보안 기반 기능이 제대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-172">Without a functional TPM, security-based functions such as BitLocker may not work properly.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-173">연결된 대기</span><span class="sxs-lookup"><span data-stu-id="4377c-173">Connected Standby</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-174">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-174">Description:</span></span></strong></td><td><span data-ttu-id="4377c-175">연결된 대기실이 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-175">Checks if Connected Standby is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-176">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-176">Value:</span></span></strong></td><td><span data-ttu-id="4377c-177">True</span><span class="sxs-lookup"><span data-stu-id="4377c-177">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-178">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-178">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-179">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-179">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-180">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-180">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-181">연결된 대기를 통해 Surface 디바이스는 사용되지 않는 동안 업데이트 및 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-181">Connected Standby allows a Surface device to receive updates and notifications while not being used.</span></span> <span data-ttu-id="4377c-182">최상의 환경을 위해 연결된 대기 환경을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-182">For best experience, Connected Standby should be enabled.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-183">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="4377c-183">Bluetooth</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-184">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-184">Description:</span></span></strong></td><td><span data-ttu-id="4377c-185">사용 가능한 Bluetooth 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-185">Checks if Bluetooth is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-186">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-186">Value:</span></span></strong></td><td><span data-ttu-id="4377c-187">설정됨</span><span class="sxs-lookup"><span data-stu-id="4377c-187">Enabled</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-188">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-188">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-189">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-189">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-190">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-190">Guidance:</span></span></strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-191">디버그 모드</span><span class="sxs-lookup"><span data-stu-id="4377c-191">Debug Mode</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-192">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-192">Description:</span></span></strong></td><td><span data-ttu-id="4377c-193">운영 체제가 디버그 모드에 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-193">Checks if the operating system is in Debug mode.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-194">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-194">Value:</span></span></strong></td><td><span data-ttu-id="4377c-195">중</span><span class="sxs-lookup"><span data-stu-id="4377c-195">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-196">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-196">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-197">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-197">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-198">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-198">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-199">디버그 부팅 옵션은 Windows 운영 체제의 커널 디버깅을 활성화 또는 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-199">The debug boot option enables or disables kernel debugging of the Windows operating system.</span></span> <span data-ttu-id="4377c-200">이 옵션을 사용하도록 설정하면 시스템 문제가 발생할 수 있으며 DRM(디지털 권한 관리 권한)으로 보호된 미디어가 재생되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-200">Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-201">테스트 서명</span><span class="sxs-lookup"><span data-stu-id="4377c-201">Test Signing</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-202">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-202">Description:</span></span></strong></td><td><span data-ttu-id="4377c-203">테스트 서명이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-203">Checks if Test Signing is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-204">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-204">Value:</span></span></strong></td><td><span data-ttu-id="4377c-205">중</span><span class="sxs-lookup"><span data-stu-id="4377c-205">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-206">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-206">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-207">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-207">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-208">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-208">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-209">테스트 서명은 시험판 드라이버를 테스트하는 데만 사용할 수 있는 Windows 시작 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-209">Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-210">활성 전원 계획</span><span class="sxs-lookup"><span data-stu-id="4377c-210">Active Power Plan</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-211">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-211">Description:</span></span></strong></td><td><span data-ttu-id="4377c-212">올바른 전원 계획이 활성 상태인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-212">Checks that the correct power plan is active.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-213">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-213">Value:</span></span></strong></td><td><span data-ttu-id="4377c-214">균형 조정</span><span class="sxs-lookup"><span data-stu-id="4377c-214">Balanced</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-215">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-215">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-216">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-216">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-217">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-217">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-218">생산성과 배터리 수명을 최대화하기 위해 "균형 조정된" 전원 계획을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-218">It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500"><span data-ttu-id="4377c-219">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="4377c-219">Windows Update</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-220">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-220">Description:</span></span></strong></td><td><span data-ttu-id="4377c-221">디바이스가 Windows 업데이트를 사용하여 최신 버전이면 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-221">Checks if the device is up to date with Windows updates.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-222">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-222">Value:</span></span></strong></td><td><span data-ttu-id="4377c-223">Microsoft Silverlight(KB4023307), Windows Defender 바이러스 백신에 대한 정의 업데이트 - KB2267602(정의 1.279.1433.0)</span><span class="sxs-lookup"><span data-stu-id="4377c-223">Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-224">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-224">Condition:</span></span></strong></td><td><font color="ff9500"><span data-ttu-id="4377c-225">최적화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-225">Not Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-226">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-226">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-227">최신 창으로 업데이트하면 최신 펌웨어 및 드라이버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-227">Updating to the latest windows makes sure you are on the latest firmware and drivers.</span></span> <span data-ttu-id="4377c-228">장치를 항상 최신으로 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-228">It is recommended to always keep your device up to date</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-229">무료 하드 드라이브 공간</span><span class="sxs-lookup"><span data-stu-id="4377c-229">Free Hard Drive Space</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-230">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-230">Description:</span></span></strong></td><td><span data-ttu-id="4377c-231">사용이 없는 하드 드라이브 공간이 부족한지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-231">Checks for low free hard drive space.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-232">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-232">Value:</span></span></strong></td><td><span data-ttu-id="4377c-233">66%</span><span class="sxs-lookup"><span data-stu-id="4377c-233">66%</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-234">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-234">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-235">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-235">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-236">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-236">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-237">최상의 성능을 위해 하드 드라이브 용량의 10% 이상을 사용 가능 공간으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-237">For best performance, your hard drive should have at least 10% of its capacity as free space.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-238">작동하지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="4377c-238">Non-Functioning Devices</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-239">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-239">Description:</span></span></strong></td><td><span data-ttu-id="4377c-240">장치 관리자의 작동하지 않는 장치 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-240">List of non-functioning devices in Device Manager.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-241">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-241">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="4377c-242">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-242">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-243">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-243">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-244">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-244">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-245">장치 관리자에서 작동하지 않는 장치는 각 하드웨어 구성 요소의 절전과 같이 Surface 디바이스에서 예측할 수 없는 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-245">Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="4377c-246">외부 모니터</span><span class="sxs-lookup"><span data-stu-id="4377c-246">External Monitor</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="4377c-247">설명:</span><span class="sxs-lookup"><span data-stu-id="4377c-247">Description:</span></span></strong></td><td><span data-ttu-id="4377c-248">호환성 문제가 있을 수 있는 외부 모니터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4377c-248">Checks for an external monitor that may have compatibility issues.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="4377c-249">값:</span><span class="sxs-lookup"><span data-stu-id="4377c-249">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="4377c-250">조건:</span><span class="sxs-lookup"><span data-stu-id="4377c-250">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="4377c-251">최적</span><span class="sxs-lookup"><span data-stu-id="4377c-251">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="4377c-252">지침:</span><span class="sxs-lookup"><span data-stu-id="4377c-252">Guidance:</span></span></strong></td><td><span data-ttu-id="4377c-253">Surface 디바이스와 호환되는지 원래 장비 제조업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="4377c-253">Check with the original equipment manufacturer for compatibility with your Surface device.</span></span></td></tr>
</table>
