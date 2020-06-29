---
title: Surface Hub 2S 포트 및 키패드 개요
description: 이 페이지에서는 Surface Hub 2S에 연결 하는 데 필요한 포트, 물리적 단추 및 구성 정보에 대해 설명 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: c79a2b86d1e697a1839c2c4d945ed385bc1eccde
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835351"
---
# Surface Hub 2S 포트 및 키패드 개요

이 페이지에서는 유선, Wi-fi 또는 블루투스 메서드를 통해 Surface Hub에 연결 하는 데 필요한 포트, 물리적 단추, 구성 정보에 대해 설명 합니다 2S. 또한 주요 연결 시나리오에 대 한 모범 사례 권장 사항을 제공 합니다.

> [!NOTE]
> 포장 외부의 일련 번호, 전원 코드에의 한 디스플레이 또는 Surface 앱을 사용 하 여 찾을 수 있습니다. 

아래 그림에서는 장치의 아래쪽에 연결 된 키패드의 포트와 물리적 단추의 위치를 보여 줍니다. 표에는 각 요소에 대 한 자세한 설명이 포함 되어 있습니다.

 ![I/o 연결 및 물리적 단추의 전면 및 아래쪽 보기](images/hub2s-schematic.png)

## 포트 및 키패드 구성 요소 참조

|**Key**|**구성 요소**|**설명**|**키 매개 변수**|
|:--- |:--------- |:----------- |:-------------- |
| raid-1 | **USB C** | **USB 3.1 Gen 1** <br> 위치 조정 드라이브와 같은 주변 장치에 연결 하기 위한 정리 포트로 사용 합니다. 게스트 포트는 디바이스의 각 측면에 있습니다 (4).<br> <br> *참고:이 포트는 외부 카메라에 연결 하는 것이 좋습니다. 추가 카메라 탑재 기능은 연결 된 카메라의 보존을 지원 하기 위해 디자인에 통합 되어 있습니다.*<br> <br> 참고: TouchBack 및 비디오 수집은 이러한 포트에서 지원 되지 않습니다. | C 입력 <br> <br> 15 W 포트 (5V/3A)       |
| 2 | **AC 전원** | **100-240 V 입력** <br> 표준 AC 전원 및 Surface Hub 2S에 연결 하 여 미국 및 캐나다의 as110 볼트 또는 영국에 220 볼트에 있는 지역 표준으로 자동 전환 합니다. | IEC 60320 C14 |
| 3-4 | **DC 전원** | **24V DC 입력 포트** <br> 모바일 배터리에 연결 하는 데 사용 합니다. | Anderson 커넥터에 듀얼 배럴 Xbox1 |
| 4(tcp/ipv4) | **Ethernet** | **1000/100/10 기본-T** <br> 회사 환경에서 지속적인 연결을 제공 하 고, 최대 안정성 또는 용량을 요구 하는 관련 시나리오를 사용 합니다. | RJ45 |
| 5mb | **USB-A** | **USB 3.1 Gen 1** <br> 위치 조정 드라이브와 같은 주변 장치에 연결 하기 위한 정리 포트로 사용 합니다. | 입력 하십시오<br>7.5 W 포트 (5V/1.5 A) |
| 26 | **USB-C** | **USB 3.1 Gen 1** <br> 외부 Pc 및 관련 장치를 연결 하 고 위치 조정-드라이브와 같은 주변 장치를 사용 하는 데 사용할 작업 포트를 만듭니다.<br> <br> *참고:이는 비디오, TouchBack, InkBack에 권장 되는 입력 포트입니다.* | C 입력 <br> 18 W 포트 (5V/3A, 9V/2A) |
| 7 | **HDMI-in** | **HDMI 2.0, HDCP 2.2/1.4** <br> HDMI에서 HDMI로의 게스트 입력을 비롯 한 여러 시나리오에 사용 합니다. | 표준 HDMI |
| 20cm(8 | **미니 DP-out** | **미니 DP 1.2 출력** <br> Surface Hub 2S 디스플레이를 대형 프로젝터에 미러링 하는 등의 비디오 출력 시나리오에 사용 합니다.<br> <br> *참고:이는 최대 해상도 3840 x 2160 (4K UHD) @60Hz를 지원 합니다.* | 미니 DP |
| 되었는지 | **소스**  | 연결 된 수집 원본 (외부 PC, HDMI 및 미니 DP 모드) 간에 전환 하는 데 사용 합니다. | 해당 없음 |
| 1천만 | **Volume** | 장치에서 로컬로 오디오를 조정 하려면 +/-를 사용 합니다. <br> <br> *참고: 밝기 컨트롤로 이동할 때 볼륨 슬라이더에서 +/-를 사용 하 여 디스플레이 밝기를 제어 합니다.* | 해당 없음 |
| mb | **전원** | 전원 장치 켜기/끄기. <br> 표시 메뉴를 탐색 하 고 항목을 선택 하는 데도 사용 합니다. | 해당 없음 |

 ![무선, 오디오, & 관련 구성 요소의 후면 보기](images/hub2s-rear.png)
