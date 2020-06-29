---
title: Surface Hub 2S에 디바이스 연결
description: 이 페이지에서는 외부 장치를 Surface Hub 2S에 연결 하는 방법에 대해 설명 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/24/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1c4f9b4a74b50edb5587185f28a18163a02d62f9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835743"
---
# Surface Hub 2S에 디바이스 연결
Surface Hub 2S를 사용 하 여 외부 장치를 연결 하 고, Surface Hub에 디스플레이를 미러링 2S, 다른 장치에 연결 하 고, 비디오 컨퍼런스 카메라, 전화 회의 전화, 실내 시스템 장치를 포함 하 여 여러 개의 타사 주변 장치를 연결할 수 있습니다.

디바이스의 콘텐츠를 Surface Hub 2S에 표시할 수 있습니다. 원본 장치가 Windows 기반 인 경우 해당 디바이스는 연결 된 장치에서 비디오 및 오디오를 가져와 Surface Hub 2S에 표시 하는 TouchBack 및 InkBack을 제공할 수도 있습니다. Surface Hub 2S가 블루레이 DVD 플레이어와 같은 HDCP (고대역폭 디지털 콘텐츠 보호) 신호를 만나면 원본이 검정색 이미지로 표시 됩니다.

> [!NOTE]
> Surface Hub 2S 새 연결을 설정 하거나 기존 연결이 중단 되거나 연결 앱이 닫혀 있을 때까지 선택한 비디오 입력을 사용 합니다.

## 권장 되는 유선 구성 

일반적으로 USB-C와 같이 가능 하면 usb-c 또는 HDMI에서 HDMI로 기본 케이블 연결을 사용 하는 것이 좋습니다. MiniDP 또는 MiniDP에 대 한 다른 조합도 USB-C에 적용 됩니다. 이 페이지에서 설명 하는 것 처럼 일부 추가 구성은 비디오 출력 환경을 최적화 하는 데 필요할 수 있습니다.

| **연결** | **기능** | **설명**|
| --- | --- | ---|
| HDMI + USB-C | 오디오 및 비디오에 대 한 HDMI-in<br><br>TouchBack 용 USB-C 및 InkBack | USB-C는 HDMI A/V 연결을 통해 TouchBack 및 InkBack을 지원 합니다.<br><br>Usb-C를 사용 하 여 레거시 컴퓨터에 연결<br><br>**참고:** 최상의 결과를 위해서는 USB-C 케이블을 연결 하기 전에 HDMI를 연결 합니다. HDMI 용으로 사용 하는 컴퓨터가 TouchBack와 호환 되지 않고 InkBack 하는 경우 USB-C 케이블이 필요 하지 않습니다. |
| USB-C <br> (compute 모듈을 통해) | 비디오-인 <br>오디오-인 | A/V에 필요한 싱글 케이블<br><br>TouchBack 및 InkBack이 지원 됩니다.<br><br>HDCP 사용 |
| HDMI (포트) | 영상, Surface Hub 2S 오디오 | A/V에 필요한 싱글 케이블<br><br>TouchBack 및 InkBack이 지원 되지 않음<br><br>HDCP 사용 |
| MiniDP 1.2 출력 | 대형 프로젝터를 미러링 하는 등의 비디오 출력 | A/V에 필요한 싱글 케이블 |

USB 컴퓨터를 2S 포트를 통해 Surface Hub에 연결 하면 몇 가지 USB 장치가 검색 되 고 구성 됩니다. 이러한 주변 장치는 TouchBack 및 InkBack으로 생성 됩니다. 다음 표에 표시 된 대로 장치 관리자에서 주변 장치를 볼 수 있으며,이 경우 다음 표에 나와 있는 것 처럼 일부 디바이스의 중복 이름을 표시 합니다.

 
|**주변 장치**| **장치 관리자 목록** |
| ---------------------------- |------------- | ------------------------------|
| 휴먼 인터페이스 장치 | HID 규격 소비자 제어 장치<br>HID 규격 펜<br>HID 규격 펜(중복된 항목)<br>HID 규격 펜(중복된 항목)<br>HID 규격 터치 스크린<br>USB 입력 장치<br>USB 입력 장치(중복된 항목) |
| 키보드 | 표준 PS/2 키보드 |
| 마우스 및 기타 포인팅 장치 | HID 규격 마우스 |
| USB 컨트롤러 | 일반 USB 허브<br>USB 복합 장치 |

## Surface Hub 2S에 비디오 연결

다음 표에 표시 된 대로 USB-C 또는 HDMI를 사용 하 여 허브 2S Surface Hub에 비디오를 입력할 수 있습니다.  

### Surface Hub 2S 비디오-인 설정

| **신호 유형** | **해상도** | **프레임 속도** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| PC              | 720 x 480      | 60             | X        | X         |
| PC              | 1024 x 768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> 4K UHD 해상도 (3840 × 2560)는 compute 모듈의 포트에 연결 하는 경우에만 지원 됩니다. 디바이스의 왼쪽, 위쪽, 오른쪽에 있는 "게스트" USB 포트에서 지원 되지 않습니다.

> [!NOTE]
> Surface Hub 2S에 표시 되 면 연결 된 외부 PC의 비디오가 더 작게 표시 될 수 있습니다.

## 다른 장치에 디스플레이 2S 미러링 Surface Hub

다음 표에 표시 된 대로 MiniDP를 사용 하 여 비디오를 다른 디스플레이로 출력할 수 있습니다.

### Surface Hub 2S 영상 출력 설정

| **신호 유형** | **해상도** | **프레임 속도** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640 x 480      | 60             | X          |
| PC              | 720 x 480      | 60             | X          |
| PC              | 1024 x 768     | 60             | X          |
| PC              | 1920 x 1080    | 60             | X          |
| PC              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S에는 Surface Hub 2S의 시각적 콘텐츠를 다른 디스플레이로 프로젝션 하는 MiniDP 비디오 출력 포트가 포함 됩니다. Surface Hub 2S를 사용 하 여 다른 디스플레이에 투영할 계획 이라면 다음 권장 사항을 참조 하세요.

- **키보드가 필요 합니다.** 시작 하기 전에 유선 또는 블루투스를 사용 하는 외부 키보드를 Surface Hub 2S에 연결 해야 합니다. 원본 Surface Hub와 달리 Surface Hub 2S 키보드는 별도로 판매 되며 배송 패키지에 포함 되지 않습니다.<br><br>
- **중복 모드를 설정 합니다.** Surface Hub 2S는 중복 모드 에서만 비디오 출력을 지원 합니다. 그러나 처음 연결 하는 경우에도 표시 모드를 수동으로 구성 해야 합니다.
    1. **Windows logo key**  +  Surface Hub 2S의 오른쪽에 프로젝트 창을 연 Windows 로고 키**P**를 입력 한 다음 **복제** 모드를 선택 합니다.
    2. Surface Hub 2S 세션을 마치면 **세션 종료**를 선택 합니다. 이렇게 하면 다음 세션에 대 한 중복 설정이 저장 됩니다.<br><br>
- **다양 한 가로 세로 비율에 대 한 계획** 다른 표면 장치와 마찬가지로 Surface Hub 2S는 3:2 표시 가로 세로 비율 (표시 너비와 높이 사이의 관계)을 사용 합니다. 다른 가로 세로 비율이 있는 디스플레이에 Surface Hub 2S을 프로젝션 하는 기능이 지원 됩니다. Surface Hub 2S 디스플레이를 복제 하기 때문에 MiniDP 출력은 수신 디스플레이의 가로 세로 비율에 따라 letterboxing 또는 curtaining 발생할 수 있는 3:2 가로 세로 비율로만 표시 됩니다. 

> [!NOTE]
> 두 번째 모니터에서 16:9 가로 세로 비율 (대부분의 TV 모니터의 주요 비율)을 사용 하는 경우에는 검은 막대가 미러링된 디스플레이의 왼쪽 및 오른쪽에 표시 될 수 있습니다. 이런 경우에는 두 번째 디스플레이를 조정할 필요가 없다는 것을 사용자에 게 알려줄 수 있습니다.

## 케이블 선택 하기

다음 권장 사항을 참고 하세요.

- **USB를 선택합니다.** USB 3.1 Gen 2 케이블.
- **MiniDP.** 최대 3 미터 길이의 DisplayPort 케이블을 인증 합니다.
- **HDMI.** 긴 케이블이 필요한 경우, 필요한 경우 repeaters를 설치 하는 기능과 함께 저렴 한 장거리 케이블의 가용성으로 인해 HDMI가 권장 됩니다.

> [!NOTE]
> HDMI가 감지 된 경우 대부분의 DisplayPort 원본이 자동으로 HDMI 신호로 전환 됩니다.

## Surface Hub 2S 무선 연결

Windows 10은 기본적으로 화면 허브 2S 무선 연결을 가능 하 게 하는 Miracast를 지원 합니다.<br><br>

### Miracast를 사용 하 여 연결 하려면:

1. Windows 10 장치에서 **windows 로고 키**  +  **K**를 입력 합니다. 
2. 연결 창에서 가까운 디바이스 목록에 있는 Surface Hub 2S의 이름을 찾습니다. 디스플레이의 왼쪽 아래 모서리에 있는 Surface Hub 2S의 이름을 찾을 수 있습니다.
3. 시스템 관리자가 Miracast 연결에 대 한 PIN 설정을 사용 하도록 설정한 경우 PIN을 입력 합니다. 이를 위해서는 처음으로 Surface Hub 2S에 연결할 때 PIN 번호를 입력 해야 합니다.

> [!NOTE]
>Surface Hub 2S 디바이스의 이름이 예상 대로 표시 되지 않으면 이전 세션이 중간에 닫혀 있을 수 있습니다. 그런 경우 Surface Hub 2S에 직접 로그인 하 여 이전 세션을 종료 한 다음 외부 장치에서 연결 합니다.

## Surface Hub 2S 주변 장치 연결

### Bluetooth 액세서리

Bluetooth를 사용 하 여 다음 액세서리를 Surface Hub 2S에 연결할 수 있습니다.

- 마우스
- 키보드
- 헤드셋
- 스피커
- Surface Hub 2 펜

> [!NOTE]
> Bluetooth 헤드셋 또는 스피커를 연결한 후 기본 마이크와 스피커 설정을 변경해야 할 수 있습니다. 자세한 내용은 [**Surface Hub 설정의 로컬 관리**](https://docs.microsoft.com/surface-hub/local-management-surface-hub-settings)를 참조 하세요.
