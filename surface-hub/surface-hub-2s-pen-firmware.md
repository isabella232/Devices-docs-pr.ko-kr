---
title: Surface Hub 2S에서 펜 펌웨어 업데이트
description: 이 페이지에서는 Surface Hub 2 펜의 펌웨어를 업데이트하는 방법에 대해 설명하고 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: c94cb701fb1b7fcdc0168a795f57a4e497317902
ms.sourcegitcommit: 77b2c51f8467ac3ac37399551b0cc20d9ce57d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "11585969"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a><span data-ttu-id="f02ca-104">Surface Hub 2S에서 펜 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="f02ca-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="f02ca-105">비즈니스용 업데이트 또는 Surface Hub PC에 다운로드하여 Windows 2 펜의 펌웨어를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="f02ca-106">업데이트된 펌웨어는 2020년 2월 26일부터 Windows 업데이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <a name="update-pen-firmware-using-windows-update-for-business"></a><span data-ttu-id="f02ca-107">비즈니스용 업데이트로 Windows 펜 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="f02ca-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="f02ca-108">이 섹션에서는 기본적으로 야간 3시에 발생하도록 구성된 Windows 업데이트에 대한 자동화된 유지 관리 주기를 통해 펜 펌웨어를 업데이트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="f02ca-109">업데이트는 2 펜에 적용하기 전에 두 가지 유지 관리 주기를 Surface Hub 합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="f02ca-110">또는 다른 업데이트와 마찬가지로 WUfB(비즈니스용 Windows)를 사용하여 펜 펌웨어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-110">Alternately, like any other update, you can use Windows Update for Business (WUfB) to apply the pen firmware.</span></span> <span data-ttu-id="f02ca-111">자세한 내용은 [Managing Windows updates on Surface Hub.](manage-windows-updates-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="f02ca-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="f02ca-112">Surface Hub 2 펜이 Surface Hub: 흰색 표시등이 깜박이기 시작할 때까지 \*\*\*\* 위쪽 단추를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 펜](images/sh2-pen-1.png)

2. <span data-ttu-id="f02ca-114">모든 Surface Hub 관리자로 로그인하고, 설정 를 **연**다음 새 Bluetooth 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>

3. <span data-ttu-id="f02ca-115">페어링 프로세스를 완료하려면 펜을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-115">Select the pen to complete the pairing process.</span></span>

4. <span data-ttu-id="f02ca-116">펜의 **위쪽** 단추를 눌러 업데이트를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="f02ca-117">완료하는 데 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-117">It may take up to two hours to complete.</span></span>

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a><span data-ttu-id="f02ca-118">개별 PC로 다운로드하여 펜 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="f02ca-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="f02ca-119">2 펜의 펌웨어를 Surface Hub 실행 중인 별도의 PC에서 업데이트할 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f02ca-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="f02ca-120">또한 이 방법을 사용하면 펜 펌웨어가 최신 버전으로 성공적으로 업데이트되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="f02ca-121">Surface Hub 2 펜을 Bluetooth 가능 PC에 페어링: 흰색 \*\*\*\* 표시기 LED 표시등이 깜박이기 시작할 때까지 위쪽 단추를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 펜](images/sh2-pen-1.png)

2. <span data-ttu-id="f02ca-123">PC에서 새 디바이스를 Bluetooth 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-123">On the PC, scan for new Bluetooth devices.</span></span>

3. <span data-ttu-id="f02ca-124">페어링 프로세스를 완료하려면 펜을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-124">Select the pen to complete the pairing process.</span></span>

4. <span data-ttu-id="f02ca-125">새 업데이트를 Surface Hub 전에 다른 모든 Surface Hub 펜의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>

5. <span data-ttu-id="f02ca-126">PC에 [Surface Hub 2 펜 펌웨어 업데이트 도구를](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>

6. <span data-ttu-id="f02ca-127">실행 **PenCfu.exe.**</span><span class="sxs-lookup"><span data-stu-id="f02ca-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="f02ca-128">설치 진행률이 도구에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="f02ca-129">업데이트를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-129">It may take several minutes to finish updating.</span></span> 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a><span data-ttu-id="f02ca-130">2 펜의 펌웨어 Surface Hub 확인</span><span class="sxs-lookup"><span data-stu-id="f02ca-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="f02ca-131">펜 **get_version.bat** 단추를 실행하고 맨 위 단추를 누릅니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f02ca-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>

2. <span data-ttu-id="f02ca-132">이 도구는 펜의 펌웨어 버전을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-132">The tool will report the firmware version of the pen.</span></span> 

   <span data-ttu-id="f02ca-133">예:</span><span class="sxs-lookup"><span data-stu-id="f02ca-133">Example:</span></span>
    - <span data-ttu-id="f02ca-134">이전 펌웨어는 468.2727.368입니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="f02ca-135">새 펌웨어는 468.3347.368입니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-135">New firmware is 468.3347.368</span></span>

## <a name="command-line-options"></a><span data-ttu-id="f02ca-136">명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="f02ca-136">Command line options</span></span>

<span data-ttu-id="f02ca-137">명령줄에서 Surface Hub 2 펜 펌웨어 업데이트 도구(PenCfu.exe)를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="f02ca-138">펜을 PC에 페어링하고 펜의 위쪽 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>

2. <span data-ttu-id="f02ca-139">펌웨어 **PenCfu.exe** 시작하려면 다음을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="f02ca-140">구성 파일 및 펌웨어 이미지 파일은 도구와 동일한 폴더에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>

3. <span data-ttu-id="f02ca-141">추가 옵션을PenCfu.exe \*\* -h를 실행하여\*\* 다음 표에 나열된 사용 가능한 매개 변수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  

   <span data-ttu-id="f02ca-142">예:</span><span class="sxs-lookup"><span data-stu-id="f02ca-142">Example:</span></span> `PenCfu.exe -h`

4. <span data-ttu-id="f02ca-143">**Ctrl+C를** 입력하여 도구를 안전하게 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>


| <span data-ttu-id="f02ca-144">명령</span><span class="sxs-lookup"><span data-stu-id="f02ca-144">Command</span></span> | <span data-ttu-id="f02ca-145">설명</span><span class="sxs-lookup"><span data-stu-id="f02ca-145">Description</span></span> |
| -------------- |---------------------------- |
| <span data-ttu-id="f02ca-146">-h 도움말</span><span class="sxs-lookup"><span data-stu-id="f02ca-146">-h help</span></span>        | <span data-ttu-id="f02ca-147">도구 명령줄 인터페이스 도움말을 표시하고 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-147">Display tool command line interface help and exit.</span></span> |
| <span data-ttu-id="f02ca-148">-v 버전</span><span class="sxs-lookup"><span data-stu-id="f02ca-148">-v version</span></span>     | <span data-ttu-id="f02ca-149">도구 버전을 표시하고 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-149">Display tool version and exit.</span></span> |
| <span data-ttu-id="f02ca-150">-l 로그 필터</span><span class="sxs-lookup"><span data-stu-id="f02ca-150">-l log-filter</span></span>  | <span data-ttu-id="f02ca-151">로그 파일의 필터 수준을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="f02ca-151">Set a filter level for the log file.</span></span> <span data-ttu-id="f02ca-152">로그 메시지의 가능한 수준은 DEBUG(가장 낮음), INFO, WARNING 및 ERROR(가장 높음)입니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="f02ca-153">로그 필터 수준을 설정하면 로그 메시지가 같은 수준 이상인 메시지로만 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="f02ca-154">예를 들어 필터 수준이 WARNING으로 설정된 경우 WARNING 및 ERROR 메시지만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="f02ca-155">기본적으로 이 옵션은 끄기로 설정되어 로깅을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="f02ca-156">-g get-version</span><span class="sxs-lookup"><span data-stu-id="f02ca-156">-g get-version</span></span> | <span data-ttu-id="f02ca-157">지정된 경우 도구는 도구와 동일한 폴더에 저장된 구성 파일과 일치하는 연결된 펜의 FW 버전만 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f02ca-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>  |

