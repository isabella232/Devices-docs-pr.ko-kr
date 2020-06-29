---
title: 회의실 제어 시스템 사용(Surface Hub)
description: Microsoft Surface Hub와 함께 회의실 제어 시스템을 사용할 수 있습니다.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: 회의실 제어 시스템, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834847"
---
# <span data-ttu-id="96afc-104">회의실 제어 시스템 사용(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="96afc-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="96afc-105">Microsoft Surface Hub와 함께 회의실 제어 시스템을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="96afc-106">Surface Hub와 함께 회의실 제어 시스템을 사용하려면 일반적으로 Surface Hub의 맨 아래에 있는 RJ11 직렬 포트를 통해 회의실 제어 하드웨어를 Surface Hub에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <span data-ttu-id="96afc-107">터미널 설정</span><span class="sxs-lookup"><span data-stu-id="96afc-107">Terminal settings</span></span>

<span data-ttu-id="96afc-108">회의실 제어 시스템 제어판에 연결하기 위해 Surface Hub에서 터미널 설정을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="96afc-109">PC 또는 노트북을 Surface Hub에 연결하고 Surface Hub에서 연속 명령을 보내려는 경우 Tera Term이나 PuTTY와 같은 터미널 에뮬레이터 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="96afc-110">설정</span><span class="sxs-lookup"><span data-stu-id="96afc-110">Setting</span></span> | <span data-ttu-id="96afc-111">값</span><span class="sxs-lookup"><span data-stu-id="96afc-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="96afc-112">전송 속도</span><span class="sxs-lookup"><span data-stu-id="96afc-112">Baud rate</span></span> | <span data-ttu-id="96afc-113">115200</span><span class="sxs-lookup"><span data-stu-id="96afc-113">115200</span></span> |
| <span data-ttu-id="96afc-114">데이터 비트</span><span class="sxs-lookup"><span data-stu-id="96afc-114">Data bits</span></span> | <span data-ttu-id="96afc-115">20cm(8</span><span class="sxs-lookup"><span data-stu-id="96afc-115">8</span></span> | 
| <span data-ttu-id="96afc-116">정지 비트</span><span class="sxs-lookup"><span data-stu-id="96afc-116">Stop bits</span></span> | <span data-ttu-id="96afc-117">raid-1</span><span class="sxs-lookup"><span data-stu-id="96afc-117">1</span></span> |
| <span data-ttu-id="96afc-118">패리티</span><span class="sxs-lookup"><span data-stu-id="96afc-118">Parity</span></span> | <span data-ttu-id="96afc-119">없음</span><span class="sxs-lookup"><span data-stu-id="96afc-119">none</span></span> |
| <span data-ttu-id="96afc-120">흐름 제어</span><span class="sxs-lookup"><span data-stu-id="96afc-120">Flow control</span></span> | <span data-ttu-id="96afc-121">없음</span><span class="sxs-lookup"><span data-stu-id="96afc-121">none</span></span> |
| <span data-ttu-id="96afc-122">줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="96afc-122">Line feed</span></span> | <span data-ttu-id="96afc-123">모든 캐리지 리턴</span><span class="sxs-lookup"><span data-stu-id="96afc-123">every carriage return</span></span> |
 

## <span data-ttu-id="96afc-124">연결 다이어그램</span><span class="sxs-lookup"><span data-stu-id="96afc-124">Wiring diagram</span></span>

<span data-ttu-id="96afc-125">표준 RJ-11(6P6C) 커넥터를 사용하여 Surface Hub 직렬 포트를 회의실 제어 시스템에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="96afc-126">이것은 권장 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-126">This is the recommended method.</span></span> <span data-ttu-id="96afc-127">RJ-11 4선 케이블을 사용할 수도 있지만 이 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="96afc-128">다음 다이어그램은 RJ-11(6P6C) - DB9 케이블에 사용되는 올바른 핀아웃을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![연결 다이어그램을 보여 주는 이미지](images/room-control-wiring-diagram.png)

## <span data-ttu-id="96afc-130">명령 집합</span><span class="sxs-lookup"><span data-stu-id="96afc-130">Command sets</span></span>

<span data-ttu-id="96afc-131">회의실 제어 시스템은 일반적인 회의실 시나리오를 명령에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="96afc-132">명령은 회의실 제어 시스템에서 시작되어 직렬 연결을 통해 Surface Hub로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="96afc-133">명령은 ASCII 기반이며, Surface Hub에서 상태 변경 시기를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="96afc-134">다음 명령 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-134">The following command modifiers are available.</span></span> <span data-ttu-id="96afc-135">명령은 새 줄 문자(\n)로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="96afc-136">관리 포트 명령에 의해 직접 트리거되지 않은 상태 변경에 대한 응답으로 언제든지 응답이 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="96afc-137">보조키</span><span class="sxs-lookup"><span data-stu-id="96afc-137">Modifier</span></span> | <span data-ttu-id="96afc-138">결과</span><span class="sxs-lookup"><span data-stu-id="96afc-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="96afc-139">값 높이기</span><span class="sxs-lookup"><span data-stu-id="96afc-139">Increment a value</span></span> |
| - | <span data-ttu-id="96afc-140">값 낮추기</span><span class="sxs-lookup"><span data-stu-id="96afc-140">Decrease a value</span></span> |
| = | <span data-ttu-id="96afc-141">개별 값 설정</span><span class="sxs-lookup"><span data-stu-id="96afc-141">Set a discrete value</span></span> |
| <span data-ttu-id="96afc-142">?</span><span class="sxs-lookup"><span data-stu-id="96afc-142">?</span></span> | <span data-ttu-id="96afc-143">현재 값 쿼리</span><span class="sxs-lookup"><span data-stu-id="96afc-143">Queries for a current value</span></span> |
 

## <span data-ttu-id="96afc-144">전원</span><span class="sxs-lookup"><span data-stu-id="96afc-144">Power</span></span>

<span data-ttu-id="96afc-145">Surface Hub는 다음 전원 상태 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="96afc-146">상태</span><span class="sxs-lookup"><span data-stu-id="96afc-146">State</span></span> | <span data-ttu-id="96afc-147">Energy Star 상태</span><span class="sxs-lookup"><span data-stu-id="96afc-147">Energy Star state</span></span>| <span data-ttu-id="96afc-148">설명</span><span class="sxs-lookup"><span data-stu-id="96afc-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-149">0</span><span class="sxs-lookup"><span data-stu-id="96afc-149">0</span></span> | <span data-ttu-id="96afc-150">S5</span><span class="sxs-lookup"><span data-stu-id="96afc-150">S5</span></span> | <span data-ttu-id="96afc-151">꺼짐</span><span class="sxs-lookup"><span data-stu-id="96afc-151">Off</span></span> |
| <span data-ttu-id="96afc-152">raid-1</span><span class="sxs-lookup"><span data-stu-id="96afc-152">1</span></span> | - | <span data-ttu-id="96afc-153">전원 켜짐(확정되지 않음)</span><span class="sxs-lookup"><span data-stu-id="96afc-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="96afc-154">2</span><span class="sxs-lookup"><span data-stu-id="96afc-154">2</span></span> | <span data-ttu-id="96afc-155">S3</span><span class="sxs-lookup"><span data-stu-id="96afc-155">S3</span></span> | <span data-ttu-id="96afc-156">절전</span><span class="sxs-lookup"><span data-stu-id="96afc-156">Sleep</span></span> |
| <span data-ttu-id="96afc-157">5mb</span><span class="sxs-lookup"><span data-stu-id="96afc-157">5</span></span> | <span data-ttu-id="96afc-158">S0</span><span class="sxs-lookup"><span data-stu-id="96afc-158">S0</span></span> | <span data-ttu-id="96afc-159">준비</span><span class="sxs-lookup"><span data-stu-id="96afc-159">Ready</span></span> |


<span data-ttu-id="96afc-160">대체 PC 모드에서는 전원 상태는 준비 및 해제 상태만 가능하여 디스플레이만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="96afc-161">대체 PC에서는 전원 관리 포트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="96afc-162">상태</span><span class="sxs-lookup"><span data-stu-id="96afc-162">State</span></span> | <span data-ttu-id="96afc-163">Energy Star 상태</span><span class="sxs-lookup"><span data-stu-id="96afc-163">Energy Star state</span></span>| <span data-ttu-id="96afc-164">설명</span><span class="sxs-lookup"><span data-stu-id="96afc-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-165">0</span><span class="sxs-lookup"><span data-stu-id="96afc-165">0</span></span> | <span data-ttu-id="96afc-166">S5</span><span class="sxs-lookup"><span data-stu-id="96afc-166">S5</span></span> | <span data-ttu-id="96afc-167">꺼짐</span><span class="sxs-lookup"><span data-stu-id="96afc-167">Off</span></span> |
| <span data-ttu-id="96afc-168">5mb</span><span class="sxs-lookup"><span data-stu-id="96afc-168">5</span></span> | <span data-ttu-id="96afc-169">S0</span><span class="sxs-lookup"><span data-stu-id="96afc-169">S0</span></span> | <span data-ttu-id="96afc-170">준비</span><span class="sxs-lookup"><span data-stu-id="96afc-170">Ready</span></span> |

<span data-ttu-id="96afc-171">제어 장치의 경우 5/준비 외에는 어떤 항목도 끄는 것을 고려할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="96afc-172">각 PowerOn는 두 가지 상태의 변경 및 응답을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="96afc-173">명령</span><span class="sxs-lookup"><span data-stu-id="96afc-173">Command</span></span> | <span data-ttu-id="96afc-174">상태 변경</span><span class="sxs-lookup"><span data-stu-id="96afc-174">State change</span></span>| <span data-ttu-id="96afc-175">응답</span><span class="sxs-lookup"><span data-stu-id="96afc-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="96afc-176">PowerOn</span></span> | <span data-ttu-id="96afc-177">장치가 켜집니다(디스플레이 + PC).</span><span class="sxs-lookup"><span data-stu-id="96afc-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="96afc-178">PC 서비스에서는 PC가 준비되었음을 SMC에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="96afc-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="96afc-179">Power=0</span></span></br></br><span data-ttu-id="96afc-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="96afc-180">Power=5</span></span> |
| <span data-ttu-id="96afc-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="96afc-181">PowerOff</span></span> | <span data-ttu-id="96afc-182">장치가 주변 상태로 전환됩니다(PC는 켜지고 디스플레이는 어두워짐)</span><span class="sxs-lookup"><span data-stu-id="96afc-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="96afc-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="96afc-183">Power=0</span></span> |
| <span data-ttu-id="96afc-184">Power?</span><span class="sxs-lookup"><span data-stu-id="96afc-184">Power?</span></span> |  <span data-ttu-id="96afc-185">SMC는 마지막으로 알려진 전원 상태를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="96afc-186">Power=<#></span><span class="sxs-lookup"><span data-stu-id="96afc-186">Power=<#></span></span> |



## <span data-ttu-id="96afc-187">밝기</span><span class="sxs-lookup"><span data-stu-id="96afc-187">Brightness</span></span>

<span data-ttu-id="96afc-188">현재 밝기 수준은 0에서 100 사이의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="96afc-189">밝기 수준의 변경 내용은 회의실 제어 시스템이나 다른 시스템에서 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="96afc-190">명령</span><span class="sxs-lookup"><span data-stu-id="96afc-190">Command</span></span> | <span data-ttu-id="96afc-191">상태 변경</span><span class="sxs-lookup"><span data-stu-id="96afc-191">State change</span></span> |<span data-ttu-id="96afc-192">응답</span><span class="sxs-lookup"><span data-stu-id="96afc-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="96afc-193">Brightness+</span></span> | <span data-ttu-id="96afc-194">SMC(시스템 관리 컨트롤러)가 밝기 높이기 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="96afc-195">회의실 제어 시스템의 PC 서비스가 SMC에 새 밝기 수준을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="96afc-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="96afc-196">Brightness = 51</span></span> |
| <span data-ttu-id="96afc-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="96afc-197">Brightness-</span></span> |  <span data-ttu-id="96afc-198">SMC가 밝기 낮추기 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="96afc-199">PC 서비스가 SMC에 새 밝기 수준을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="96afc-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="96afc-200">Brightness = 50</span></span> |

## <span data-ttu-id="96afc-201">볼륨</span><span class="sxs-lookup"><span data-stu-id="96afc-201">Volume</span></span>

<span data-ttu-id="96afc-202">현재 볼륨 수준은 0에서 100 사이의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="96afc-203">볼륨 수준의 변경 내용은 회의실 제어 시스템이나 다른 시스템에서 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="96afc-204">볼륨 명령은 [게스트 원본](connect-and-display-with-surface-hub.md)가 아니라 포함 또는 대체 PC 모드의 볼륨만을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="96afc-205">명령</span><span class="sxs-lookup"><span data-stu-id="96afc-205">Command</span></span> | <span data-ttu-id="96afc-206">상태 변경</span><span class="sxs-lookup"><span data-stu-id="96afc-206">State change</span></span> | <span data-ttu-id="96afc-207">응답</span><span class="sxs-lookup"><span data-stu-id="96afc-207">Response</span></span></br><span data-ttu-id="96afc-208">([대체 PC 모드](connect-and-display-with-surface-hub.md#replacement-pc-mode)에서 사용)</span><span class="sxs-lookup"><span data-stu-id="96afc-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-209">볼륨+</span><span class="sxs-lookup"><span data-stu-id="96afc-209">Volume+</span></span> |  <span data-ttu-id="96afc-210">SMC가 볼륨 크게 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="96afc-211">PC 서비스가 SMC에 새 볼륨 수준을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="96afc-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="96afc-212">Volume = 51</span></span> |
| <span data-ttu-id="96afc-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="96afc-213">Volume-</span></span> |  <span data-ttu-id="96afc-214">SMC가 볼륨 작게 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="96afc-215">PC 서비스가 SMC에 새 볼륨 수준을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="96afc-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="96afc-216">Volume = 50</span></span> |


 

## <span data-ttu-id="96afc-217">오디오 음소거</span><span class="sxs-lookup"><span data-stu-id="96afc-217">Mute for audio</span></span>

<span data-ttu-id="96afc-218">오디오가 음소거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-218">Audio can be muted.</span></span>

| <span data-ttu-id="96afc-219">명령</span><span class="sxs-lookup"><span data-stu-id="96afc-219">Command</span></span> | <span data-ttu-id="96afc-220">상태 변경</span><span class="sxs-lookup"><span data-stu-id="96afc-220">State change</span></span> | <span data-ttu-id="96afc-221">응답</span><span class="sxs-lookup"><span data-stu-id="96afc-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="96afc-222">AudioMute+</span></span> |  <span data-ttu-id="96afc-223">SMC가 오디오 음소거 명령을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="96afc-224">PC 서비스가 SMC에 오디오가 음소거되었다고 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="96afc-225">없음</span><span class="sxs-lookup"><span data-stu-id="96afc-225">none</span></span> |


 

## <span data-ttu-id="96afc-226">비디오 원본</span><span class="sxs-lookup"><span data-stu-id="96afc-226">Video source</span></span>

<span data-ttu-id="96afc-227">여러 디스플레이 소스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-227">Several display sources can be used.</span></span>

| <span data-ttu-id="96afc-228">상태</span><span class="sxs-lookup"><span data-stu-id="96afc-228">State</span></span> | <span data-ttu-id="96afc-229">설명</span><span class="sxs-lookup"><span data-stu-id="96afc-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="96afc-230">0</span><span class="sxs-lookup"><span data-stu-id="96afc-230">0</span></span> |  <span data-ttu-id="96afc-231">온보드 PC</span><span class="sxs-lookup"><span data-stu-id="96afc-231">Onboard PC</span></span> |
| <span data-ttu-id="96afc-232">raid-1</span><span class="sxs-lookup"><span data-stu-id="96afc-232">1</span></span> |  <span data-ttu-id="96afc-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="96afc-233">DisplayPort</span></span> |
| <span data-ttu-id="96afc-234">2</span><span class="sxs-lookup"><span data-stu-id="96afc-234">2</span></span> |  <span data-ttu-id="96afc-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="96afc-235">HDMI</span></span> |
| <span data-ttu-id="96afc-236">3-4</span><span class="sxs-lookup"><span data-stu-id="96afc-236">3</span></span> |  <span data-ttu-id="96afc-237">VGA</span><span class="sxs-lookup"><span data-stu-id="96afc-237">VGA</span></span> |


 

<span data-ttu-id="96afc-238">디스플레이 소스의 변경 내용은 회의실 제어 시스템이나 다른 시스템에서 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="96afc-239">명령</span><span class="sxs-lookup"><span data-stu-id="96afc-239">Command</span></span> | <span data-ttu-id="96afc-240">상태 변경</span><span class="sxs-lookup"><span data-stu-id="96afc-240">State change</span></span> | <span data-ttu-id="96afc-241">응답</span><span class="sxs-lookup"><span data-stu-id="96afc-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96afc-242">Source=#</span><span class="sxs-lookup"><span data-stu-id="96afc-242">Source=#</span></span> |  <span data-ttu-id="96afc-243">SMC가 원하는 소스로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="96afc-244">PC 서비스가 SMC에 디스플레이 소스가 전환되었다고 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="96afc-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="96afc-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="96afc-246">Source+</span><span class="sxs-lookup"><span data-stu-id="96afc-246">Source+</span></span> |  <span data-ttu-id="96afc-247">SMC가 다음 활성 입력 소스로 순환합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="96afc-248">PC 서비스가 SMC에 현재 입력 소스를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="96afc-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="96afc-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="96afc-250">Source-</span><span class="sxs-lookup"><span data-stu-id="96afc-250">Source-</span></span> | <span data-ttu-id="96afc-251">SMC가 이전 활성 입력 소스로 순환합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="96afc-252">PC 서비스가 SMC에 현재 입력 소스를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="96afc-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="96afc-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="96afc-254">원본?</span><span class="sxs-lookup"><span data-stu-id="96afc-254">Source?</span></span> |  <span data-ttu-id="96afc-255">SMC가 PC 서비스에서 활성 입력 소스를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="96afc-256">PC 서비스가 SMC에 현재 입력 소스를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="96afc-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="96afc-257">Source=&lt;#&gt;</span></span> |

## <span data-ttu-id="96afc-258">오류</span><span class="sxs-lookup"><span data-stu-id="96afc-258">Errors</span></span>

<span data-ttu-id="96afc-259">이 표에 있는 형식에 따라 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="96afc-260">오류</span><span class="sxs-lookup"><span data-stu-id="96afc-260">Error</span></span> | <span data-ttu-id="96afc-261">참고</span><span class="sxs-lookup"><span data-stu-id="96afc-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="96afc-262">오류: '&lt;입력&gt;'은(는) 알 수 없는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="96afc-263">명령에 알 수 없는 초기 명령이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="96afc-264">예를 들어 &quot;VOL+&quot;는 잘못되었으며 &quot;오류: 'VOL'은(는) 알 수 없는 명령입니다.&quot;가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="96afc-265">오류: '&lt;입력&gt;'은(는) 알 수 없는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="96afc-266">명령에 알 수 없는 연산자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="96afc-267">예를 들어 &quot;볼륨!&quot;이 잘못되었으며 &quot; 오류: '!'은(는) 알 수 없는 연산자입니다.&quot;가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="96afc-268">오류: '&lt;입력&gt;'은(는) 알 수 없는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="96afc-269">명령에 알 수 없는 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="96afc-270">예를 들어 &quot;Volume=abc&quot;는 잘못되었으며 &quot;오류: 'abc'은(는) 알 수 없는 매개 변수입니다.&quot;가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="96afc-271">오류: '&lt;입력&gt;'을(를) 끄면 명령을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="96afc-272">Surface Hub가 꺼진 경우 전원 이외의 명령에서 이 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="96afc-273">예를 들어 &quot;Volume+&quot;는 잘못되었으며 &quot;오류: 'Volume'을(를) 끄면 명령을 사용할 수 없습니다.&quot;가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="96afc-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <span data-ttu-id="96afc-274">관련 항목</span><span class="sxs-lookup"><span data-stu-id="96afc-274">Related topics</span></span>


[<span data-ttu-id="96afc-275">Microsoft Surface Hub 관리</span><span class="sxs-lookup"><span data-stu-id="96afc-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="96afc-276">Microsoft Surface Hub 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="96afc-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





