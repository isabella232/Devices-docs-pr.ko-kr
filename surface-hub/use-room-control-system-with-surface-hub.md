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
# 회의실 제어 시스템 사용(Surface Hub)


Microsoft Surface Hub와 함께 회의실 제어 시스템을 사용할 수 있습니다.

Surface Hub와 함께 회의실 제어 시스템을 사용하려면 일반적으로 Surface Hub의 맨 아래에 있는 RJ11 직렬 포트를 통해 회의실 제어 하드웨어를 Surface Hub에 연결해야 합니다.

## 터미널 설정

회의실 제어 시스템 제어판에 연결하기 위해 Surface Hub에서 터미널 설정을 구성할 필요는 없습니다. PC 또는 노트북을 Surface Hub에 연결하고 Surface Hub에서 연속 명령을 보내려는 경우 Tera Term이나 PuTTY와 같은 터미널 에뮬레이터 프로그램을 사용할 수 있습니다. 

| 설정 | 값 |
| --- | --- |
| 전송 속도 | 115200 |
| 데이터 비트 | 20cm(8 | 
| 정지 비트 | raid-1 |
| 패리티 | 없음 |
| 흐름 제어 | 없음 |
| 줄 바꿈 | 모든 캐리지 리턴 |
 

## 연결 다이어그램

표준 RJ-11(6P6C) 커넥터를 사용하여 Surface Hub 직렬 포트를 회의실 제어 시스템에 연결할 수 있습니다. 이것은 권장 방법입니다. RJ-11 4선 케이블을 사용할 수도 있지만 이 방법은 권장되지 않습니다.

다음 다이어그램은 RJ-11(6P6C) - DB9 케이블에 사용되는 올바른 핀아웃을 보여 줍니다.

![연결 다이어그램을 보여 주는 이미지](images/room-control-wiring-diagram.png)

## 명령 집합

회의실 제어 시스템은 일반적인 회의실 시나리오를 명령에 사용합니다. 명령은 회의실 제어 시스템에서 시작되어 직렬 연결을 통해 Surface Hub로 전달됩니다. 명령은 ASCII 기반이며, Surface Hub에서 상태 변경 시기를 승인합니다.

다음 명령 한정자를 사용할 수 있습니다. 명령은 새 줄 문자(\n)로 종료됩니다. 관리 포트 명령에 의해 직접 트리거되지 않은 상태 변경에 대한 응답으로 언제든지 응답이 제공될 수 있습니다.

| 보조키 | 결과 |
| --- | --- |
| + | 값 높이기 |
| - | 값 낮추기 |
| = | 개별 값 설정 |
| ? | 현재 값 쿼리 |
 

## 전원

Surface Hub는 다음 전원 상태 중 하나일 수 있습니다.

| 상태 | Energy Star 상태| 설명 |
| --- | --- | --- |
| 0 | S5 | 꺼짐 |
| raid-1 | - | 전원 켜짐(확정되지 않음) |
| 2 | S3 | 절전 |
| 5mb | S0 | 준비 |


대체 PC 모드에서는 전원 상태는 준비 및 해제 상태만 가능하여 디스플레이만 변경됩니다. 대체 PC에서는 전원 관리 포트를 사용할 수 없습니다. 

| 상태 | Energy Star 상태| 설명 |
| --- | --- | --- |
| 0 | S5 | 꺼짐 |
| 5mb | S0 | 준비 |

제어 장치의 경우 5/준비 외에는 어떤 항목도 끄는 것을 고려할 수 없습니다. 각 PowerOn는 두 가지 상태의 변경 및 응답을 발생 합니다. 

| 명령 | 상태 변경| 응답 |
| --- | --- | --- |
| PowerOn | 장치가 켜집니다(디스플레이 + PC).</br></br>PC 서비스에서는 PC가 준비되었음을 SMC에 알립니다. |  Power=0</br></br>Power=5 |
| PowerOff | 장치가 주변 상태로 전환됩니다(PC는 켜지고 디스플레이는 어두워짐) |  Power=0 |
| Power? |  SMC는 마지막으로 알려진 전원 상태를 보고합니다. |  Power=<#> |



## 밝기

현재 밝기 수준은 0에서 100 사이의 범위입니다.

밝기 수준의 변경 내용은 회의실 제어 시스템이나 다른 시스템에서 보낼 수 있습니다.

| 명령 | 상태 변경 |응답 |
| --- | --- | --- |
| Brightness+ | SMC(시스템 관리 컨트롤러)가 밝기 높이기 명령을 보냅니다.</br></br>회의실 제어 시스템의 PC 서비스가 SMC에 새 밝기 수준을 알립니다. |  Brightness = 51 |
| Brightness- |  SMC가 밝기 낮추기 명령을 보냅니다.</br></br>PC 서비스가 SMC에 새 밝기 수준을 알립니다. | Brightness = 50 |

## 볼륨

현재 볼륨 수준은 0에서 100 사이의 범위입니다.

볼륨 수준의 변경 내용은 회의실 제어 시스템이나 다른 시스템에서 보낼 수 있습니다.

>[!NOTE]
>볼륨 명령은 [게스트 원본](connect-and-display-with-surface-hub.md)가 아니라 포함 또는 대체 PC 모드의 볼륨만을 제어합니다.

| 명령 | 상태 변경 | 응답</br>([대체 PC 모드](connect-and-display-with-surface-hub.md#replacement-pc-mode)에서 사용) |
| --- | --- | --- |
| 볼륨+ |  SMC가 볼륨 크게 명령을 보냅니다.</br></br>PC 서비스가 SMC에 새 볼륨 수준을 알립니다. |  Volume = 51 |
| Volume- |  SMC가 볼륨 작게 명령을 보냅니다.</br></br>PC 서비스가 SMC에 새 볼륨 수준을 알립니다. |  Volume = 50 |


 

## 오디오 음소거

오디오가 음소거될 수 있습니다.

| 명령 | 상태 변경 | 응답 |
| --- | --- | --- |
| AudioMute+ |  SMC가 오디오 음소거 명령을 보냅니다.</br></br>PC 서비스가 SMC에 오디오가 음소거되었다고 알립니다. |  없음 |


 

## 비디오 원본

여러 디스플레이 소스를 사용할 수 있습니다.

| 상태 | 설명 | 
| --- | --- |
| 0 |  온보드 PC |
| raid-1 |  DisplayPort |
| 2 |  HDMI |
| 3-4 |  VGA |


 

디스플레이 소스의 변경 내용은 회의실 제어 시스템이나 다른 시스템에서 보낼 수 있습니다.

| 명령 | 상태 변경 | 응답 |
| --- | --- | --- |
| Source=# |  SMC가 원하는 소스로 변경됩니다.</br></br>PC 서비스가 SMC에 디스플레이 소스가 전환되었다고 알립니다. |  Source=&lt;#&gt; |
| Source+ |  SMC가 다음 활성 입력 소스로 순환합니다.</br></br>PC 서비스가 SMC에 현재 입력 소스를 알립니다. |  Source=&lt;#&gt; |
| Source- | SMC가 이전 활성 입력 소스로 순환합니다.</br></br>PC 서비스가 SMC에 현재 입력 소스를 알립니다. |  Source=&lt;#&gt; |
| 원본? |  SMC가 PC 서비스에서 활성 입력 소스를 쿼리합니다.</br></br>PC 서비스가 SMC에 현재 입력 소스를 알립니다. | Source=&lt;#&gt; |

## 오류

이 표에 있는 형식에 따라 오류가 반환됩니다.

| 오류 | 참고 |
| --- | --- |
| 오류: '&lt;입력&gt;'은(는) 알 수 없는 명령입니다. |  명령에 알 수 없는 초기 명령이 포함되어 있습니다. 예를 들어 &quot;VOL+&quot;는 잘못되었으며 &quot;오류: 'VOL'은(는) 알 수 없는 명령입니다.&quot;가 반환됩니다. |
| 오류: '&lt;입력&gt;'은(는) 알 수 없는 연산자입니다. |  명령에 알 수 없는 연산자가 포함되어 있습니다. 예를 들어 &quot;볼륨!&quot;이 잘못되었으며 &quot; 오류: '!'은(는) 알 수 없는 연산자입니다.&quot;가 반환됩니다. |
| 오류: '&lt;입력&gt;'은(는) 알 수 없는 매개 변수입니다. |  명령에 알 수 없는 매개 변수가 포함되어 있습니다. 예를 들어 &quot;Volume=abc&quot;는 잘못되었으며 &quot;오류: 'abc'은(는) 알 수 없는 매개 변수입니다.&quot;가 반환됩니다. |
| 오류: '&lt;입력&gt;'을(를) 끄면 명령을 사용할 수 없습니다. |  Surface Hub가 꺼진 경우 전원 이외의 명령에서 이 오류가 반환됩니다. 예를 들어 &quot;Volume+&quot;는 잘못되었으며 &quot;오류: 'Volume'을(를) 끄면 명령을 사용할 수 없습니다.&quot;가 반환됩니다. |


 

## 관련 항목


[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)

 

 





