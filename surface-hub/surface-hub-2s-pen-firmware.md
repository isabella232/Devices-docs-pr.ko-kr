---
title: Surface Hub 2S에서 펜 펌웨어 업데이트
description: 이 페이지에서는 Surface Hub 2 펜에 대 한 펌웨어를 업데이트 하는 방법을 설명 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835383"
---
# <span data-ttu-id="a9c64-104">Surface Hub 2S에서 펜 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9c64-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="a9c64-105">Surface Hub 2에서 비즈니스용 Windows 업데이트 또는 펌웨어 업데이트를 별도의 PC에 다운로드 하 여 펌웨어를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="a9c64-106">업데이트 된 펌웨어는 2020 년 2 월 26 일부터 Windows 업데이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <span data-ttu-id="a9c64-107">비즈니스용 Windows 업데이트를 사용 하 여 펜 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9c64-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="a9c64-108">이 섹션에서는 Windows Update에 대 한 자동화 된 유지 관리 주기를 통해 펜 펌웨어를 업데이트 하는 방법에 대해 설명 하며 기본적으로 오전 3 시에 발생 하도록 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="a9c64-109">Surface Hub 2 펜에 업데이트를 적용 하기 전에 2 개의 유지 관리 주기가 완료 되도록 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="a9c64-110">또는 다른 업데이트와 마찬가지로 WSUS (Windows Server Update Services)를 사용 하 여 펜 펌웨어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-110">Alternately, like any other update, you can use Windows Server Update Services (WSUS) to apply the pen firmware.</span></span> <span data-ttu-id="a9c64-111">자세한 내용은 [Surface Hub에서 Windows 업데이트 관리](manage-windows-updates-for-surface-hub.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9c64-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="a9c64-112">Surface Hub 2 펜이 Surface Hub 2S와 쌍을 이루어야 함: 흰색 표시기 LED 표시등이 깜박일 때까지 **위쪽** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 펜](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="a9c64-114">Surface Hub에서 관리자로 로그인 하 고, **설정을**열고, 새 Bluetooth 장치를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="a9c64-115">펜을 선택 하 여 페어링 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-115">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="a9c64-116">펜의 **위쪽** 단추를 눌러 업데이트를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="a9c64-117">완료 하는 데 최대 2 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-117">It may take up to two hours to complete.</span></span>

## <span data-ttu-id="a9c64-118">별도 PC로 다운로드 하 여 펜 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9c64-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="a9c64-119">Windows 10을 실행 하는 별도의 PC에서 Surface Hub 2 펜의 펌웨어를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="a9c64-120">이 방법을 사용 하면 펜 펌웨어가 최신 버전으로 성공적으로 업데이트 되었는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="a9c64-121">Surface Hub 2 펜을 블루투스 가능 PC에 연결: 흰색 표시기 LED 표시등이 깜박일 때까지 **위쪽** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 펜](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="a9c64-123">PC에서 새 Bluetooth 장치를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-123">On the PC, scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="a9c64-124">펜을 선택 하 여 페어링 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-124">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="a9c64-125">새 업데이트를 시작 하기 전에 다른 Surface Hub 2s 펜을 모두 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>
3. <span data-ttu-id="a9c64-126">PC에 [Surface Hub 2 펜 펌웨어 업데이트 도구](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>
4. <span data-ttu-id="a9c64-127">**PenCfu.exe를 실행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a9c64-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="a9c64-128">설치 진행률이 도구에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="a9c64-129">업데이트를 완료 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-129">It may take several minutes to finish updating.</span></span> 


## <span data-ttu-id="a9c64-130">Surface Hub 2 펜의 펌웨어 버전 확인</span><span class="sxs-lookup"><span data-stu-id="a9c64-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="a9c64-131">**get_version.bat** 를 실행 하 고 펜의 **위쪽** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>
2. <span data-ttu-id="a9c64-132">이 도구는 펜의 펌웨어 버전을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-132">The tool will report the firmware version of the pen.</span></span> <span data-ttu-id="a9c64-133">예:</span><span class="sxs-lookup"><span data-stu-id="a9c64-133">Example:</span></span>
    - <span data-ttu-id="a9c64-134">오래 된 펌웨어를 468.2727.368.</span><span class="sxs-lookup"><span data-stu-id="a9c64-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="a9c64-135">새 펌웨어를 468.2863.369.</span><span class="sxs-lookup"><span data-stu-id="a9c64-135">New firmware is 468.2863.369</span></span>

## <span data-ttu-id="a9c64-136">명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="a9c64-136">Command line options</span></span>

<span data-ttu-id="a9c64-137">명령줄에서 Surface Hub 2 펜 펌웨어 업데이트 도구 (PenCfu.exe)를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="a9c64-138">펜을 PC에 연결 하 고 펜의 **위쪽** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>
2. <span data-ttu-id="a9c64-139">펌웨어 업데이트를 시작 하려면 **PenCfu.exe** 를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="a9c64-140">구성 파일과 펌웨어 이미지 파일은 도구와 같은 폴더에 저장 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>
3. <span data-ttu-id="a9c64-141">추가 옵션을 보려면 다음 표에 나열 된 대로 **PenCfu.exe-h** 를 실행 하 여 사용 가능한 매개 변수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  
    - <span data-ttu-id="a9c64-142">예: PenCfu.exe-h</span><span class="sxs-lookup"><span data-stu-id="a9c64-142">Example: PenCfu.exe -h</span></span>
4. <span data-ttu-id="a9c64-143">도구를 안전 하 게 종료 하려면 **Ctrl + C** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>

 

| **<span data-ttu-id="a9c64-144">명령</span><span class="sxs-lookup"><span data-stu-id="a9c64-144">Command</span></span>**    | **<span data-ttu-id="a9c64-145">설명</span><span class="sxs-lookup"><span data-stu-id="a9c64-145">Description</span></span>**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a9c64-146">-h 도움말</span><span class="sxs-lookup"><span data-stu-id="a9c64-146">-h help</span></span>        | <span data-ttu-id="a9c64-147">디스플레이 도구 명령줄 인터페이스 도움말 및 종료</span><span class="sxs-lookup"><span data-stu-id="a9c64-147">Display tool command line interface help and exit.</span></span>                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="a9c64-148">-v 버전</span><span class="sxs-lookup"><span data-stu-id="a9c64-148">-v version</span></span>     | <span data-ttu-id="a9c64-149">도구 버전을 표시 하 고 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-149">Display tool version and exit.</span></span>                                                                                                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="a9c64-150">-l 로그-필터</span><span class="sxs-lookup"><span data-stu-id="a9c64-150">-l log-filter</span></span>  | <span data-ttu-id="a9c64-151">로그 파일에 대 한 필터 수준을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-151">Set a filter level for the log file.</span></span> <span data-ttu-id="a9c64-152">로그 메시지에는 디버그 (최하위), 정보, 경고 및 오류 (가장 높음)의 네 가지 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="a9c64-153">로그 필터 수준을 설정 하면 수준이 같은 메시지에만 로그 메시지가 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="a9c64-154">예를 들어 필터 수준이 WARNING으로 설정 된 경우에는 경고 및 오류 메시지만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="a9c64-155">기본적으로이 옵션은 OFF로 설정 되어 있으며 로깅이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="a9c64-156">-g get-버전</span><span class="sxs-lookup"><span data-stu-id="a9c64-156">-g get-version</span></span> | <span data-ttu-id="a9c64-157">지정 하는 경우 도구는 도구와 같은 폴더에 저장 된 구성 파일과 일치 하는 연결 된 펜의 FW 버전만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9c64-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>                                                                                                                                                                                                                                    