---
title: Surface Hub 2S에 장치 연결
description: 이 페이지에서는 외부 디바이스를 Surface Hub 2S에 연결하는 방법을 설명합니다.
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
ms.openlocfilehash: e3d1aa79ad056e790d5dc6a46f299cbaa9b5f9b0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497478"
---
# <a name="connect-devices-to-surface-hub-2s"></a>Surface Hub 2S에 장치 연결

Surface Hub 2S를 사용하면 외부 디바이스를 연결하고, Surface Hub 2S의 디스플레이를 다른 장치에 미러링하고, 화상 회의 카메라, 전화 회의 전화 및 회의실 시스템 장치를 포함한 여러 타사 주변 장치를 연결할 수 있습니다.

디바이스의 콘텐츠를 Surface Hub 2S로 표시할 수 있습니다. 원본 디바이스가 Windows 기반인 경우 해당 디바이스는 연결된 디바이스에서 비디오 및 오디오를 가져와 Surface Hub 2S에 표시하는 TouchBack 및 InkBack을 제공할 수도 있습니다. Surface Hub 2S에서 블루레이 DVD 플레이어와 같은 High-Bandwidth HDCP(디지털 콘텐츠 보호) 신호가 발생하면 원본이 검은색 이미지로 표시됩니다.

> [!NOTE]
> Surface Hub 2S는 새 연결이 만들어지거나, 기존 연결이 중단되거나, 커넥트 앱이 닫혀 있을 때까지 선택한 비디오 입력을 사용합니다.

## <a name="recommended-wired-configurations"></a>권장 유선 구성 

일반적으로 USB-C에서 USB-C로 또는 HDMI-HDMI와 같이 가능하면 네이티브 케이블 연결을 사용하는 것이 좋습니다. MiniDP에서 HDMI로, MiniDP에서 USB-C로의 다른 조합도 작동합니다. 이 페이지에 설명된 대로 비디오 출력 환경을 최적화하려면 몇 가지 추가 구성이 필요할 수 있습니다.

| **연결** | **기능** | **설명**|
| --- | --- | ---|
| HDMI + USB-C | 오디오 및 비디오용 HDMI 인<br><br>TouchBack 및 InkBack용 USB-C | USB-C는 HDMI A/V 연결을 사용하여 TouchBack 및 InkBack을 지원합니다.<br><br>USB-C에서 USB-A로 레거시 컴퓨터에 연결합니다.<br><br>**참고:** 최상의 결과를 얻으려면 USB-C 케이블을 연결하기 전에 HDMI를 연결합니다. HDMI에 사용 중인 컴퓨터가 TouchBack 및 InkBack과 호환되지 않는 경우 USB-C 케이블이 필요하지 않습니다. |
| USB-C <br> (컴퓨팅 모듈을 통해) | 비디오 인 <br>오디오 인 | A/V에 필요한 단일 케이블<br><br>TouchBack 및 InkBack이 지원됩니다.<br><br>HDCP 사용 |
| HDMI(포트 내) | 비디오, 오디오를 Surface Hub 2S로 | A/V에 필요한 단일 케이블<br><br>TouchBack 및 InkBack이 지원되지 않음<br><br>HDCP 사용 |
| MiniDP 1.2 출력 | 더 큰 프로젝터에 미러링과 같은 비디오 출력. | A/V에 필요한 단일 케이블 |

게스트 컴퓨터를 USB-C 포트를 통해 Surface Hub 2S에 연결하면 여러 USB 디바이스가 검색되고 구성됩니다. 이러한 주변 장치는 TouchBack 및 InkBack용으로 만들어집니다. 다음 표와 같이 주변 장치는 장치 관리자 볼 수 있으며, 다음 표와 같이 일부 디바이스에 대해 중복 이름을 표시합니다.

 
|**주변 장치**| **장치 관리자 목록** |
| ---------------------------- |------------- | ------------------------------|
| 휴먼 인터페이스 장치 | HID 규격 소비자 제어 장치<br>HID 규격 펜<br>HID 규격 펜(중복된 항목)<br>HID 규격 펜(중복된 항목)<br>HID 규격 터치 스크린<br>USB 입력 장치<br>USB 입력 장치(중복된 항목) |
| 키보드 | 표준 PS/2 키보드 |
| 마우스 및 기타 포인팅 장치 | HID 규격 마우스 |
| USB 컨트롤러 | 일반 USB 허브<br>USB 복합 장치 |

## <a name="connecting-video-in-to-surface-hub-2s"></a>Surface Hub 2S에 비디오 인 연결

다음 표에 표시된 대로 USB-C 또는 HDMI를 사용하여 2S를 Surface Hub 비디오를 입력할 수 있습니다.  

### <a name="surface-hub-2s-video-in-settings"></a>Surface Hub 2S 비디오 기능 설정

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
> 4K UHD 해상도(3840×2560)는 컴퓨팅 모듈의 포트에 연결할 때만 지원됩니다. 디바이스의 왼쪽, 위쪽 및 오른쪽에 있는 "게스트" USB 포트에서는 지원되지 않습니다.

> [!NOTE]
> 연결된 외부 PC의 비디오는 Surface Hub 2S에 표시될 때 더 작게 표시될 수 있습니다.

## <a name="mirroring-surface-hub-2s-display-on-another-device"></a>다른 디바이스에 미러링 Surface Hub 2S 디스플레이

다음 표에 표시된 대로 MiniDP를 사용하여 다른 디스플레이에 비디오를 출력할 수 있습니다.

### <a name="surface-hub-2s-video-out-settings"></a>Surface Hub 2S 비디오 출력 설정

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


 
Surface Hub 2S에는 Surface Hub 2S에서 다른 디스플레이로 시각적 콘텐츠를 프로젝션하기 위한 MiniDP 비디오 출력 포트가 포함되어 있습니다. Surface Hub 2S를 사용하여 다른 디스플레이에 프로젝트하려는 경우 다음 권장 사항에 유의하세요.

- **키보드가 필요합니다.** 시작하기 전에 유선 또는 Bluetooth 사용 가능한 외부 키보드를 Surface Hub 2S에 연결해야 합니다. 원래 Surface Hub 달리 Surface Hub 2S용 키보드는 별도로 판매되며 배송 패키지에 포함되지 않습니다.<br><br>
- **중복 모드를 설정합니다.** Surface Hub 2S는 중복 모드에서만 비디오 출력을 지원합니다. 그러나 처음 연결할 때는 디스플레이 모드를 수동으로 구성해야 합니다.
    1. Surface Hub 2S의 오른쪽에 있는 Project 창을 여는 Windows **로고 키** + **P**를 입력한 다음 **중복 모드를** 선택합니다.
    2. Surface Hub 2S 세션을 마쳤으면 **세션 종료**를 선택합니다. 이렇게 하면 다음 세션에 대해 중복 설정이 저장됩니다.<br><br>
- **다양한 가로 세로 비율을 계획합니다.** 다른 Surface 디바이스와 마찬가지로 Surface Hub 2S는 3:2 디스플레이 가로 세로 비율(디스플레이의 너비와 높이 간의 관계)을 사용합니다. 가로 세로 비율이 다른 디스플레이에 Surface Hub 2S를 프로젝팅할 수 있습니다. 그러나 Surface Hub 2S는 디스플레이를 복제하므로 MiniDP 출력은 3:2 가로 세로 비율에만 표시되므로 수신 디스플레이의 가로 세로 비율에 따라 레터박스 또는 커튼이 발생할 수 있습니다. 

> [!NOTE]
> 두 번째 모니터가 16:9 가로 세로 비율(대부분의 TV 모니터에 대한 우세 비율)을 사용하는 경우 미러 디스플레이의 왼쪽과 오른쪽에 검은색 막대가 나타날 수 있습니다. 이 경우 두 번째 디스플레이를 조정할 필요가 없음을 사용자에게 알릴 수 있습니다.

## <a name="selecting-cables"></a>케이블 선택

다음 권장 사항에 유의하세요.

- **USB를 선택합니다.** USB 3.1 Gen 2 케이블.
- **MiniDP.** 최대 3미터 길이로 인증된 DisplayPort 케이블.
- **HDMI.** 긴 케이블이 필요한 경우 필요한 경우 반복기를 설치할 수 있는 비용 효율적인 장거리 케이블의 광범위한 가용성으로 인해 HDMI를 사용하는 것이 좋습니다.

> [!NOTE]
> HDMI가 감지되면 대부분의 DisplayPort 원본은 자동으로 HDMI 신호로 전환됩니다.

## <a name="wirelessly-connect-to-surface-hub-2s"></a>Surface Hub 2S에 무선으로 연결

Windows 10/11은 기본적으로 Miracast 지원하므로 무선으로 Surface Hub 2S에 연결할 수 있습니다.<br><br>

### <a name="to-connect-using-miracast"></a>Miracast 사용하여 연결하려면 다음을 수행합니다.

1. Windows 10/11 디바이스에서 **Windows 로고 키를** +  입력**합니다**. 
2. 커넥트 창의 근처 디바이스 목록에서 Surface Hub 2S의 이름을 찾습니다. 디스플레이의 왼쪽 아래 모서리에서 Surface Hub 2S의 이름을 찾을 수 있습니다.
3. 시스템 관리자가 Miracast 연결에 PIN 설정을 사용하도록 설정한 경우 PIN을 입력합니다. 이렇게 하려면 처음으로 Surface Hub 2S에 연결할 때 PIN 번호를 입력해야 합니다.

> [!NOTE]
>Surface Hub 2S 디바이스의 이름이 예상대로 표시되지 않으면 이전 세션이 조기에 닫혔을 수 있습니다. 이 경우 Surface Hub 2S에 직접 로그인하여 이전 세션을 종료한 다음 외부 디바이스에서 연결합니다.

## <a name="connecting-peripherals-to-surface-hub-2s"></a>Surface Hub 2S에 주변 장치 연결

### <a name="bluetooth-accessories"></a>Bluetooth 액세서리

Bluetooth 사용하여 다음 액세서리를 Surface Hub-2S에 연결할 수 있습니다.

- 마우스
- 키보드
- 헤드셋
- 스피커
- 펜 2개 Surface Hub

> [!NOTE]
> Bluetooth 헤드셋 또는 스피커를 연결한 후 기본 마이크와 스피커 설정을 변경해야 할 수 있습니다. 자세한 내용은 [Surface Hub 설정에 대한 로컬 관리](local-management-surface-hub-settings.md)를 참조하세요.
