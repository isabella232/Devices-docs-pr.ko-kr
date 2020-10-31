---
title: 비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용
description: SDT를 사용 하 여 조직의 사용자가 Surface 디바이스의 문제를 식별 하 고 진단 하는 데 도움을 주는 방법과 도구에서 직접 지원 요청을 제출 하는 방법에 대해 알아봅니다.
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
ms.date: 7/31/2020
ms.openlocfilehash: 8b113d16f2053fe0904518b2643f1bafeaebdf64
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145943"
---
# <span data-ttu-id="ef66a-103">비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용</span><span class="sxs-lookup"><span data-stu-id="ef66a-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="ef66a-104">이 항목에서는 Surface 진단 도구 키트 (SDT)를 사용 하 여 조직의 사용자가 Surface 디바이스의 문제를 식별 하 고 진단 하는 데 도움이 되 고 도구에서 직접 지원 요청을 제출 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with their Surface device as well as submit Support requests directly from the tool.</span></span> 

<span data-ttu-id="ef66a-105">SDT를 성공적으로 실행 하면 보고 된 문제가 하드웨어 또는 사용자 오류로 인해 발생 했는지 신속 하 게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="ef66a-106">SDT의 지원 되는 Surface 디바이스 목록은 [비즈니스용 배포 Surface 진단 툴킷](surface-diagnostic-toolkit-business.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef66a-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="ef66a-107">소프트웨어 배포 지점이 나 네트워크 공유에서 사용자에 게 [SDT 패키지](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)를 설치 하도록 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) from a software distribution point or network share.</span></span> <span data-ttu-id="ef66a-108">설치 된 후에는 일련의 테스트를 통해 사용자를 안내할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="ef66a-109">사용자가 문제에 대 한 설명을 입력할 수 있는 홈 페이지에서 시작 하 고 그림 1과 같이 **계속**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="ef66a-110">데스크톱 모드에서 SDT 시작 ](images/sdt-desk-1.png)
 *그림 1. 데스크톱 모드의 SDT*</span><span class="sxs-lookup"><span data-stu-id="ef66a-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="ef66a-111">SDT가 장치에 최신 업데이트가 있음을 나타내면 **계속** 을 클릭 하 여 그림 2와 같이 사용 가능한 테스트의 카탈로그로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="ef66a-112">SDT 옵션 ](images/sdt1.png)
 *그림 2에서 선택 합니다. SDT 옵션에서 선택*</span><span class="sxs-lookup"><span data-stu-id="ef66a-112">Select from SDT options](images/sdt1.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="ef66a-113">모든 진단 테스트를 실행 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="ef66a-114">또는 잘못 된 표시 또는 전원 공급 장치 문제와 같은 특정 문제가 이미 의심 되는 경우 **선택** 을 클릭 하 여 사용 가능한 테스트 중에서 선택 하 고 다음을 클릭 하 여 그림 3에 표시 된 것 처럼 **실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="ef66a-115">각 테스트에 대 한 자세한 내용은 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef66a-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="ef66a-116">하드웨어 테스트 선택 ](images/sdt2.png)
 *그림 3. 하드웨어 테스트 선택*</span><span class="sxs-lookup"><span data-stu-id="ef66a-116">Select hardware tests](images/sdt2.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="ef66a-117">하드웨어 테스트</span><span class="sxs-lookup"><span data-stu-id="ef66a-117">Hardware test</span></span> | <span data-ttu-id="ef66a-118">설명</span><span class="sxs-lookup"><span data-stu-id="ef66a-118">Description</span></span>
    --- | ---
    <span data-ttu-id="ef66a-119">전원 공급 장치 및 배터리</span><span class="sxs-lookup"><span data-stu-id="ef66a-119">Power Supply and Battery</span></span> |  <span data-ttu-id="ef66a-120">전원 공급 장치가 최적으로 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="ef66a-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="ef66a-121">디스플레이 및 소리</span><span class="sxs-lookup"><span data-stu-id="ef66a-121">Display and Sound</span></span>   | <span data-ttu-id="ef66a-122">밝기, 정지 또는 데드 픽셀, 스피커, 마이크 작동을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="ef66a-123">포트 및 액세서리</span><span class="sxs-lookup"><span data-stu-id="ef66a-123">Ports and Accessories</span></span>   | <span data-ttu-id="ef66a-124">액세서리, 화면 연결, USB 작동을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="ef66a-125">Connectivity</span><span class="sxs-lookup"><span data-stu-id="ef66a-125">Connectivity</span></span> |  <span data-ttu-id="ef66a-126">Bluetooth, 무선 및 LTE 연결 확인</span><span class="sxs-lookup"><span data-stu-id="ef66a-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="ef66a-127">보안</span><span class="sxs-lookup"><span data-stu-id="ef66a-127">Security</span></span>    | <span data-ttu-id="ef66a-128">보안 관련 문제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-128">Checks security related issues</span></span>
    <span data-ttu-id="ef66a-129">터치</span><span class="sxs-lookup"><span data-stu-id="ef66a-129">Touch</span></span>   | <span data-ttu-id="ef66a-130">터치 관련 문제 확인</span><span class="sxs-lookup"><span data-stu-id="ef66a-130">Checks touch related issues</span></span>
    <span data-ttu-id="ef66a-131">키보드 및 터치</span><span class="sxs-lookup"><span data-stu-id="ef66a-131">Keyboard and touch</span></span> |    <span data-ttu-id="ef66a-132">통합 키보드 연결을 확인 하 고 덮개를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="ef66a-133">센서</span><span class="sxs-lookup"><span data-stu-id="ef66a-133">Sensors</span></span> | <span data-ttu-id="ef66a-134">장치에서 다른 센서의 기능을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="ef66a-135">하드웨어</span><span class="sxs-lookup"><span data-stu-id="ef66a-135">Hardware</span></span> |  <span data-ttu-id="ef66a-136">그래픽 카드, 카메라 등의 다양 한 하드웨어 구성 요소에 대 한 문제 확인</span><span class="sxs-lookup"><span data-stu-id="ef66a-136">Checks issues with different hardware components such as graphics card and camera</span></span>

5. <span data-ttu-id="ef66a-137">모든 테스트가 완료 되 면 도구가 문제 해결 여부를 확인 하는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-137">When all tests have finished, the tool asks you to confirm if your issue is fixed.</span></span> 

 ![<span data-ttu-id="ef66a-138">문제가 해결 되었습니까? ](images/sdt3.png)
 *그림 3a. 문제가 해결 되었습니까?*</span><span class="sxs-lookup"><span data-stu-id="ef66a-138">Has your problem been resolved?](images/sdt3.png)
*Figure 3a. Has your problem been resolved?*</span></span>

6. <span data-ttu-id="ef66a-139">문제가 해결 되지 않았거나 알 수 없는 경우 **에** 는 문의처를 선택 하 여 지원 티켓을 제출 하 여 **도움을 받으세요.**</span><span class="sxs-lookup"><span data-stu-id="ef66a-139">If the issue isn't resolved or you don't know, you can submit a Support ticket by selecting **Contact us** to **Get help now.**</span></span>
 
 ![<span data-ttu-id="ef66a-140">지원 티켓 제출 ](images/sdt4.png)
 *그림 3B. 지원 티켓 제출*</span><span class="sxs-lookup"><span data-stu-id="ef66a-140">Submit a Support ticket](images/sdt4.png)
*Figure 3b. Submit a Support ticket*</span></span>

<span id="multiple" />

## <span data-ttu-id="ef66a-141">여러 하드웨어 테스트를 실행 하 여 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ef66a-141">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="ef66a-142">SDT는 일련의 테스트를 실행 하는 대화형 도구로 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-142">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="ef66a-143">각 테스트에 대해 SDT는 테스트의 특성을 요약 하는 지침과 테스트 성공에 대 한 사용자의 기대 또는 검색을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-143">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="ef66a-144">예를 들어 디스플레이 밝기가 제대로 작동 하 고 있는지 진단 하려면 그림 4에 표시 된 대로 SDT는 0에서 시작 하 여 사용자에 게 해당 밝기가 올바르게 작동 **Yes** 하는지 확인 **No** 하도록 요청 하 여 밝기를 100%로 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-144">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="ef66a-145">각 테스트에 대해 기능이 예상 대로 작동 하지 않고 사용자가 **아니요**를 클릭 하면 sdt에서 문제를 해결 하는 데 사용할 수 있는 원인과 방법에 대 한 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-145">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="ef66a-146">하드웨어 진단 실행 ](images/sdt-desk-4.png)
 *그림 4. 하드웨어 진단 실행*</span><span class="sxs-lookup"><span data-stu-id="ef66a-146">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="ef66a-147">밝기가 성공적으로 0-100%에서 조정 되 면 **예** 를 클릭 하 고 **계속**을 클릭 하 여 사용자에 게 알려 보세요.</span><span class="sxs-lookup"><span data-stu-id="ef66a-147">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="ef66a-148">밝기를 예상 대로 0-100%에서 조정 하지 못하면 사용자에 게 **아니요** 를 클릭 하 고 **계속**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-148">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="ef66a-149">사용자에 게 적절 하 게 나머지 테스트를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-149">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="ef66a-150">완료 되 면, SDT가 해상도 가이드와 함께 하드웨어 문제의 가능한 원인을 포함 하 여 보고서에 대 한 고급 요약을 자동으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-150">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="ef66a-151">응용 프로그램 복구</span><span class="sxs-lookup"><span data-stu-id="ef66a-151">Repairing applications</span></span>

<span data-ttu-id="ef66a-152">SDT는 그림 5와 같이 문제를 일으킬 수 있는 응용 프로그램을 진단 하 고 복구할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-152">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="ef66a-153">실행 중 ](images/sdt-desk-5.png)
 *에는 그림 5가 복구 됩니다. 실행 중인 복구*</span><span class="sxs-lookup"><span data-stu-id="ef66a-153">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="ef66a-154">문제 분석을 위한 로그 생성</span><span class="sxs-lookup"><span data-stu-id="ef66a-154">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="ef66a-155">SDT는 그림 6과 같이 응용 프로그램, 드라이버, 하드웨어 및 운영 체제 문제에 걸친 광범위 한 로그 가능 진단 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-155">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="ef66a-156">로그 생성 ](images/sdt-desk-6.png)
 *그림 6. 로그 생성*</span><span class="sxs-lookup"><span data-stu-id="ef66a-156">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="ef66a-157">디바이스와 최적 구성 비교 및 자세한 보고서 생성</span><span class="sxs-lookup"><span data-stu-id="ef66a-157">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="ef66a-158">SDT는 로그를 기반으로 하 여 기본 위치에 저장할 수 있는 소프트웨어 및 펌웨어 기반 문제에 대 한 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef66a-158">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="ef66a-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ef66a-159">Related topics</span></span>

- [<span data-ttu-id="ef66a-160">명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행</span><span class="sxs-lookup"><span data-stu-id="ef66a-160">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

