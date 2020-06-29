---
title: Surface 밝기 제어
description: 이 항목에서는 Surface 명도 컨트롤 앱을 사용 하 여 판매 시점 및 키오스크 시나리오에서 디스플레이 밝기를 관리 하는 방법에 대해 설명 합니다.
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
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835807"
---
# <span data-ttu-id="224e4-103">Surface 밝기 제어</span><span class="sxs-lookup"><span data-stu-id="224e4-103">Surface Brightness Control</span></span>

<span data-ttu-id="224e4-104">판매 시점이 나 다른 "항상 켜져 있는" 키오스크 시나리오에서 Surface 디바이스를 배포 하는 경우 새 Surface 밝기 제어 앱을 사용 하 여 전원 관리를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-104">When deploying Surface devices in point of sale or other “always-on” kiosk scenarios, you can optimize power management using the new Surface Brightness Control app.</span></span>

<span data-ttu-id="224e4-105">[해당 앱에 대 한 Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703)를 사용 하 여 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-105">Available for download with [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
<span data-ttu-id="224e4-106">Surface 밝기 제어는 열 로드를 줄이고 배포 된 Surface 디바이스의 전체 지원 공간을 낮출 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-106">Surface Brightness Control is designed to help reduce thermal load and lower the overall carbon footprint for deployed Surface devices.</span></span>
<span data-ttu-id="224e4-107">다운로드 페이지에서이 도구만 가져오려는 경우 사용 가능한 목록에서 **Surface_Brightness_Control_v1.16.137.0.msi** 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-107">If you plan to get only this tool from the download page, select the file **Surface_Brightness_Control_v1.16.137.0.msi** in the available list.</span></span>
<span data-ttu-id="224e4-108">이 도구는 사용 하지 않는 경우 화면을 자동으로 어둡게 하 고 다음 구성 옵션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-108">The tool automatically dims the screen when not in use and includes the following configuration options:</span></span>

- <span data-ttu-id="224e4-109">디스플레이를 흐리게 하기 전의 비활성 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-109">Period of inactivity before dimming the display.</span></span>

- <span data-ttu-id="224e4-110">흐리게 표시 되는 경우 밝기 수준</span><span class="sxs-lookup"><span data-stu-id="224e4-110">Brightness level when dimmed.</span></span>

- <span data-ttu-id="224e4-111">사용 중인 경우 최대 밝기 수준</span><span class="sxs-lookup"><span data-stu-id="224e4-111">Maximum brightness level when in use.</span></span>

**<span data-ttu-id="224e4-112">Surface 밝기 제어를 실행 하려면:</span><span class="sxs-lookup"><span data-stu-id="224e4-112">To run Surface Brightness Control:</span></span>**

- <span data-ttu-id="224e4-113">대상 장치에 surfacebrightnesscontrol.msi 설치 하 고 Surface 명도 컨트롤이 즉시 작동을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-113">Install surfacebrightnesscontrol.msi on the target device and Surface Brightness Control will begin working immediately.</span></span>

## <span data-ttu-id="224e4-114">표면 밝기 제어 구성</span><span class="sxs-lookup"><span data-stu-id="224e4-114">Configuring Surface Brightness Control</span></span>

<span data-ttu-id="224e4-115">Windows 레지스트리를 통해 기본 값을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-115">You can adjust the default values via the Windows Registry.</span></span> <span data-ttu-id="224e4-116">Windows 레지스트리를 사용 하는 방법에 대 한 자세한 내용은 [레지스트리 설명서](https://docs.microsoft.com/windows/desktop/sysinfo/registry)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="224e4-116">For more information about using the Windows Registry, refer to the [Registry documentation](https://docs.microsoft.com/windows/desktop/sysinfo/registry).</span></span>

1.  <span data-ttu-id="224e4-117">명령 프롬프트에서 regedit를 실행 하 여 Windows 레지스트리 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-117">Run regedit from a command prompt to open the Windows Registry Editor.</span></span>
    
      - <span data-ttu-id="224e4-118">Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 밝기 제어 </span><span class="sxs-lookup"><span data-stu-id="224e4-118">Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control</span></span>\ 
    
    <span data-ttu-id="224e4-119">이전 버전의 Surface 명도 컨트롤을 실행 중인 경우에는 대신 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-119">If you're running an older version of Surface Brightness control, run the following command instead:</span></span>
    
      - <span data-ttu-id="224e4-120">Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface 밝기 제어 </span><span class="sxs-lookup"><span data-stu-id="224e4-120">Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\Surface Brightness Control</span></span>\


| <span data-ttu-id="224e4-121">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="224e4-121">Registry Setting</span></span> | <span data-ttu-id="224e4-122">데이터</span><span class="sxs-lookup"><span data-stu-id="224e4-122">Data</span></span>| <span data-ttu-id="224e4-123">설명</span><span class="sxs-lookup"><span data-stu-id="224e4-123">Description</span></span>  
|-----------|------------|---------------
| <span data-ttu-id="224e4-124">밝기 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="224e4-124">Brightness Control Enabled</span></span>  |  <span data-ttu-id="224e4-125">기본값: 01</span><span class="sxs-lookup"><span data-stu-id="224e4-125">Default: 01</span></span>  <br> <span data-ttu-id="224e4-126">옵션: 01, 00</span><span class="sxs-lookup"><span data-stu-id="224e4-126">Option: 01, 00</span></span> <br> <span data-ttu-id="224e4-127">종류: REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="224e4-127">Type: REG_BINARY</span></span> |  <span data-ttu-id="224e4-128">이 설정을 통해 Surface 명도 컨트롤을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-128">This setting allows you to turn Surface Brightness Control on or off.</span></span> <span data-ttu-id="224e4-129">Surface 밝기 제어를 해제 하려면 값을 00으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-129">To disable Surface Brightness Control, set the value to 00.</span></span> <span data-ttu-id="224e4-130">이 설정을 구성 하지 않으면 Surface 밝기 컨트롤이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-130">If you do not configure this setting, Surface Brightness Control is on.</span></span> |
| <span data-ttu-id="224e4-131">전원을 사용할 때 밝기 제어</span><span class="sxs-lookup"><span data-stu-id="224e4-131">Brightness Control On Power Enabled</span></span>| <span data-ttu-id="224e4-132">기본값: 01</span><span class="sxs-lookup"><span data-stu-id="224e4-132">Default: 01</span></span> <br> <span data-ttu-id="224e4-133">옵션: 01, 00</span><span class="sxs-lookup"><span data-stu-id="224e4-133">Options: 01, 00</span></span> <br> <span data-ttu-id="224e4-134">종류: REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="224e4-134">Type: REG_BINARY</span></span> | <span data-ttu-id="224e4-135">이 설정을 사용 하면 디바이스가 직접 전원에 연결 되어 있을 때 Surface 명도 컨트롤을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-135">This setting allows you to turn off Surface Brightness Control when the device is directly connected to power.</span></span> <span data-ttu-id="224e4-136">전원이 연결 된 상태에서 Surface 밝기 제어를 비활성화 하려면 값을 00으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-136">To disable Surface Brightness Control when power is plugged in, set the value to 00.</span></span> <span data-ttu-id="224e4-137">이 설정을 구성 하지 않으면 Surface 밝기 컨트롤이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-137">If you do not configure this setting, Surface Brightness Control is on.</span></span> |
| <span data-ttu-id="224e4-138">흐린 밝기</span><span class="sxs-lookup"><span data-stu-id="224e4-138">Dimmed Brightness</span></span>   | <span data-ttu-id="224e4-139">기본값: 20</span><span class="sxs-lookup"><span data-stu-id="224e4-139">Default: 20</span></span>  <br><span data-ttu-id="224e4-140">옵션: 0-100% 화면 밝기의 범위</span><span class="sxs-lookup"><span data-stu-id="224e4-140">Option: Range of 0-100 percent of screen brightness</span></span> <br> <span data-ttu-id="224e4-141">데이터 형식: 양의 정수</span><span class="sxs-lookup"><span data-stu-id="224e4-141">Data Type: Positive integer</span></span> <br> <span data-ttu-id="224e4-142">종류: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="224e4-142">Type: REG_DWORD</span></span> | <span data-ttu-id="224e4-143">이 설정을 사용 하면 비활성 기간 동안 밝기 범위를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-143">This setting allows you to manage brightness range during periods of inactivity.</span></span> <span data-ttu-id="224e4-144">이 설정을 구성 하지 않으면 약 30 초 후에 밝기 수준이 전체 밝기의 20%로 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-144">If you do not configure this setting, the brightness level will drop to 20 percent of full brightness after 30 seconds of inactivity.</span></span> |
<span data-ttu-id="224e4-145">전체 밝기</span><span class="sxs-lookup"><span data-stu-id="224e4-145">Full Brightness</span></span>   | <span data-ttu-id="224e4-146">기본값: 100</span><span class="sxs-lookup"><span data-stu-id="224e4-146">Default: 100</span></span>  <br><span data-ttu-id="224e4-147">옵션: 0-100% 화면 밝기의 범위</span><span class="sxs-lookup"><span data-stu-id="224e4-147">Option: Range of 0-100 percent of screen brightness</span></span> <br> <span data-ttu-id="224e4-148">데이터 형식: 양의 정수</span><span class="sxs-lookup"><span data-stu-id="224e4-148">Data Type: Positive integer</span></span> <br> <span data-ttu-id="224e4-149">종류: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="224e4-149">Type: REG_DWORD</span></span>  | <span data-ttu-id="224e4-150">이 설정을 통해 디바이스의 최대 밝기 범위를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-150">This setting allows you to manage the maximum brightness range for the device.</span></span> <span data-ttu-id="224e4-151">이 설정을 구성 하지 않으면 최대 밝기 범위는 100%입니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-151">If you do not configure this setting, the maximum brightness range is 100 percent.</span></span>|  
| <span data-ttu-id="224e4-152">비활성 시간 제한</span><span class="sxs-lookup"><span data-stu-id="224e4-152">Inactivity Timeout</span></span>| <span data-ttu-id="224e4-153">기본값: 30 초</span><span class="sxs-lookup"><span data-stu-id="224e4-153">Default: 30 seconds</span></span> <br><span data-ttu-id="224e4-154">옵션: 모든 숫자 값</span><span class="sxs-lookup"><span data-stu-id="224e4-154">Option: Any numeric value</span></span>  <br><span data-ttu-id="224e4-155">데이터 형식: Integer</span><span class="sxs-lookup"><span data-stu-id="224e4-155">Data Type: Integer</span></span>  <br> <span data-ttu-id="224e4-156">종류: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="224e4-156">Type: REG_DWORD</span></span> | <span data-ttu-id="224e4-157">이 설정을 사용 하면 장치를 흐리게 표시 하기 전에 비활동 기간을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-157">This setting allows you to manage the period of inactivity before dimming the device.</span></span> <span data-ttu-id="224e4-158">이 설정을 구성 하지 않으면 비활동 제한 시간이 30 초입니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-158">If you do not configure this setting, the inactivity timeout is 30 seconds.</span></span>|
| <span data-ttu-id="224e4-159">원격 분석 사용</span><span class="sxs-lookup"><span data-stu-id="224e4-159">Telemetry  Enabled</span></span> | <span data-ttu-id="224e4-160">기본값: 01</span><span class="sxs-lookup"><span data-stu-id="224e4-160">Default: 01</span></span> <br><span data-ttu-id="224e4-161">옵션: 01, 00</span><span class="sxs-lookup"><span data-stu-id="224e4-161">Option: 01, 00</span></span> <br> <span data-ttu-id="224e4-162">종류: REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="224e4-162">Type: REG_BINARY</span></span>  | <span data-ttu-id="224e4-163">이 설정을 사용 하면 앱 사용 정보의 공유를 관리 하 여 소프트웨어를 개선 하 고 더 나은 사용자 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-163">This setting allows you to manage the sharing of app usage information to improve software and provide better user experience.</span></span> <span data-ttu-id="224e4-164">원격 분석을 사용 하지 않으려면 값을 00으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-164">To disable telemetry, set the value to 00.</span></span> <span data-ttu-id="224e4-165">이 설정을 구성 하지 않으면 [microsoft](https://privacy.microsoft.com/privacystatement)에서 원격 분석 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-165">If you do not configure this setting, telemetry information is shared with Microsoft in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> |

## <span data-ttu-id="224e4-166">변경 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="224e4-166">Changes and updates</span></span>

### <span data-ttu-id="224e4-167">버전 1.16.137</span><span class="sxs-lookup"><span data-stu-id="224e4-167">Version 1.16.137</span></span><br>
*<span data-ttu-id="224e4-168">릴리스 날짜: 2019 년 10 월 22 일</span><span class="sxs-lookup"><span data-stu-id="224e4-168">Release Date: 22 October 2019</span></span>*<br>
<span data-ttu-id="224e4-169">이 버전의 Surface light 컨트롤은 x86 용으로 다시 컴파일한 다음이에 대 한 지원을 추가 하 고 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-169">This version of Surface Brightness Control adds support for the following: -Recompiled for x86, adding support for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

### <span data-ttu-id="224e4-170">버전 1.12.239.0</span><span class="sxs-lookup"><span data-stu-id="224e4-170">Version 1.12.239.0</span></span>
*<span data-ttu-id="224e4-171">릴리스 날짜: 26 년 4 월 2019</span><span class="sxs-lookup"><span data-stu-id="224e4-171">Release Date: 26 April 2019</span></span>*<br>
<span data-ttu-id="224e4-172">이 버전의 Surface 명도 컨트롤은 다음에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="224e4-172">This version of Surface Brightness Control adds support for the following:</span></span>
- <span data-ttu-id="224e4-173">터치 지연 수정.</span><span class="sxs-lookup"><span data-stu-id="224e4-173">Touch delay fixes.</span></span>


## <span data-ttu-id="224e4-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="224e4-174">Related topics</span></span>

- [<span data-ttu-id="224e4-175">배터리 용량 한도 설정</span><span class="sxs-lookup"><span data-stu-id="224e4-175">Battery limit setting</span></span>](battery-limit.md)
