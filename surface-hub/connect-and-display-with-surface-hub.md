---
title: 다른 장치를 연결하여 Surface Hub에서 표시
description: 다른 장치를 Surface Hub에 연결하여 콘텐츠를 표시할 수 있습니다.
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: ''
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 2d8d814d5e33a878fab066321a0d7800ae5104c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836703"
---
# 다른 장치를 연결하여 Surface Hub에서 표시


다른 장치를 Microsoft Surface Hub에 연결하여 콘텐츠를 표시할 수 있습니다. 이 항목에서는 유선 연결을 통해 사용할 수 있는 게스트 모드, 대체 PC 모드 및 비디오 출력 기능을 설명하며 [Bluetooth](#bluetooth-accessories)를 사용하여 Surface Hub에 연결할 수 있는 액세서리를 나열합니다.

>[!NOTE]
>Surface Hub는 새 연결을 설정 하거나 기존 연결이 중단 되거나 연결 앱이 닫혀 있을 때까지 선택 하는 비디오 입력을 사용 합니다.

## 어떤 방법을 선택해야 하나요?

외부 장치 및 디스플레이를 Surface Hub에 연결할 때 사용 가능한 몇 가지 옵션이 있습니다. 사용하는 방법은 해당 시나리오와 요구에 따라 달라집니다. 

| 수행할 작업 | 사용할 방법 |
| --- | --- |
| Surface Hub의 디스플레이를 다른 장치에 미러링합니다. | [비디오 출력](#video-out) |
| 다른 장치의 디스플레이를 Surface Hub 화면에 표시하고 장치의 콘텐츠와 기본 제공 Surface Hub 환경을 둘 다 조작합니다. | [게스트 모드](#guest-mode) |
| 외부 Windows 10 PC에서 Surface Hub의 전원을 공급하고 Surface Hub에 포함된 컴퓨터를 끕니다. 펜과 터치뿐 아니라 카메라, 마이크, 스피커 및 기타 주변 장치도 외부 PC로 전송됩니다. | [대체 PC 모드](#replacement-pc-mode) |


## 게스트 모드


게스트 모드는 사용자가 장치의 콘텐츠를 Surface Hub에 표시할 수 있도록 유선 연결을 사용합니다. 원본 장치가 Windows 기반이면 해당 장치는 Touchback 및 Inkback도 제공할 수 있습니다. Surface Hub의 내부 PC는 연결된 장치에서 비디오 및 오디오를 가져와 Surface Hub에 표시합니다. Surface Hub에서 고대역폭 디지털 콘텐츠 보호 (HDCP) 신호를 발견 하면 원본이 검정색 이미지로 표시 됩니다. HDCP 요구 사항을 위반하지 않고 콘텐츠를 표시하려면 Surface Hub의 오른쪽 키패드를 사용하여 외부 소스를 직접 선택합니다.

>[!NOTE]
>HDCP 원본이 연결된 경우 측면 키패드를 사용하여 소스 입력을 변경합니다.

### 포트

Surface Hub의 다음 포트를 게스트 모드에 사용합니다.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>인터페이스</th>
<th>유형</th>
<th>설명</th>
<th>기능</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>디스플레이 포트 1.1a</p></td>
<td><p>비디오 입력</p></td>
<td><p>게스트 입력 #1</p></td>
<td><ul>
<li><p>게스트 입력 #2 및 게스트 입력 #3(전체 해상도 1개, 미리 보기 2개)과 함께 동시 게스트 입력 디스플레이를 지원합니다.</p></li>
<li><p>HDCP 규격(바이패스 모드)</p></li>
<li><p>Touchback 사용</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>HDMI 1.4</p></td>
<td><p>비디오 입력</p></td>
<td><p>게스트 입력 #2</p></td>
<td><ul>
<li><p>게스트 입력 #1 및 게스트 입력 #3(하나의 전체 해상도, 두 개의 미리 보기)과 함께 동시 게스트 입력 디스플레이를 지원합니다.</p></li>
<li><p>HDCP 규격(바이패스 모드)</p></li>
<li><p>Touchback 사용</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VGA</p></td>
<td><p>비디오 입력</p></td>
<td><p>게스트 입력 #3</p></td>
<td><ul>
<li><p>게스트 입력 #1 및 게스트 입력 #2(하나의 전체 해상도, 두 개의 미리 보기)와 함께 동시 게스트 입력 디스플레이를 지원합니다.</p></li>
<li><p>HDCP 규격(바이패스 모드)</p></li>
<li><p>Touchback 사용</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>3.5mm 잭</p></td>
<td><p>오디오 입력</p></td>
<td><p>아날로그 오디오 입력</p></td>
<td><ul>
<li><p>일반적으로 VGA 비디오 입력과 함께 Surface Hub PC로 수집됩니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 2.0, B형</p></td>
<td><p>USB 출력</p></td>
<td><p>Touchback</p></td>
<td><ul>
<li><p>게스트 PC에서 HID 입력 장치의 마우스, 터치, 키보드 및 스타일러스에 액세스할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### 포트 위치

다음은 55인치 및 84인치 Surface Hub의 게스트 모드에 사용되는 포트 연결입니다.

![55인치 Surface Hub의 게스트 포트를 보여 주는 이미지](images/sh-55-guest-ports.png)

55인치 Surface Hub의 유선 포트 연결

![84인치 Surface Hub의 게스트 포트를 보여 주는 이미지](images/sh-84-guest-ports.png)

84인치 Surface Hub의 유선 포트 연결

### 포트 열거

유선 연결 USB 포트를 통해 Surface Hub를 게스트 컴퓨터에 연결하면 여러 USB 장치가 검색되고 구성됩니다. 이러한 주변 장치는 Touchback 및 Inkback을 위해 고안되었습니다. 주변 장치는 장치 관리자에서 확인할 수 있습니다. 장치 관리자는 일부 장치에 대해 중복된 이름을 표시합니다.

**휴먼 인터페이스 장치**

-   HID 규격 소비자 제어 장치

-   HID 규격 펜

-   HID 규격 펜(중복된 항목)

-   HID 규격 펜(중복된 항목)

-   HID 규격 터치 스크린

-   USB 입력 장치

-   USB 입력 장치(중복된 항목)

**키보드**

-   표준 PS/2 키보드

**마우스 및 기타 포인팅 장치**

-   HID 규격 마우스

**범용 직렬 버스 컨트롤러**

-   일반 USB 허브

-   USB 복합 장치

### 게스트 모드 연결

비디오 케이블은 원본 입력에서 사용 가능한 항목에 따라 결정됩니다. Surface Hub의 비디오 입력 옵션은 DisplayPort, HDMI, VGA 등 세 가지입니다. 사용 가능한 해상도는 다음 차트를 참조하세요.

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>신호 유형</th>
<th>해상도</th>
<th>프레임 속도</th>
<th>HDMI - RGB</th>
<th>DisplayPort</th>
<th>VGA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PC</p></td>
<td><p>640 x 480</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>PC</p></td>
<td><p>720 x 480</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>PC</p></td>
<td><p>1024 x 768</p></td>
<td><p>60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>HDTV</p></td>
<td><p>720p</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>HDTV</p></td>
<td><p>1080p</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

 

원본 오디오는 DisplayPort 및 HDMI 케이블로 제공됩니다. VGA를 사용해야 하는 경우 Surface Hub에는 3.5mm 플러그를 사용하는 오디오 입력 포트가 있습니다. 또한 Surface Hub는 USB 케이블을 사용하여 Surface Hub의 Touchback 및 Inkback을 호환되는 Windows 10 장치에 제공합니다. 이미 케이블로 연결된 모든 비디오 입력에 USB 케이블을 사용할 수 있습니다.

게스트 모드를 사용하여 PC를 연결하는 사람은 다음 옵션 중 하나를 사용합니다.

**DisplayPort** - DisplayPort 케이블 및 USB 2.0 케이블

**HDMI** -- HDMI 케이블 및 USB 2.0 케이블

**VGA** - VGA케이블, 3.5mm 오디오 케이블 및 USB 2.0 케이블

게스트 모드에 사용 중인 컴퓨터가 Touchback 및 Inkback과 호환되지 않으면 USB 케이블이 필요하지 않습니다.

## 대체 PC 모드


대체 PC 모드에서는 Surface Hub에 포함된 컴퓨터가 꺼져 있고 외부 PC가 Surface Hub에 연결되어 있습니다. 대체 PC 포트에 연결하면 화면, 펜 및 터치 기능을 비롯하여 Surface Hub의 주요 주변 장치에 액세스할 수 있습니다. 이는 Surface Hub에서 Windows 팀 환경의 이점을 이용할 수 없지만 자신의 고유한 Windows 컴퓨터를 제공하여 관리하는 데 따른 유연성을 활용할 수 있음을 의미합니다.

### 소프트웨어 요구 사항

64비트 버전의 Windows 10 Home, Windows 10 Pro 및 Windows 10 Enterprise에서 대체 PC 모드로 Surface Hub를 실행할 수 있습니다. Microsoft 다운로드 센터에서 [Surface Hub 대체 PC 드라이버 패키지](https://www.microsoft.com/download/details.aspx?id=52210)를 다운로드할 수 있습니다. 대체 PC로 사용하려는 모든 컴퓨터에 이러한 드라이버를 설치하는 것이 좋습니다.

### 하드웨어 요구 사항

Surface Hub는 다양한 하드웨어와 호환됩니다. 사용할 프로그램을 지원하도록 대체 PC의 프로세서 및 메모리를 확인하고 선택합니다. 대체 PC 하드웨어가 64비트 버전의 Windows 10을 지원해야 합니다.

### 그래픽 어댑터

대체 PC 모드에서는 Surface Hub가 DisplayPort 신호를 생성할 수 있는 모든 그래픽 어댑터를 지원합니다. Surface Hub의 해상도 및 새로 고침 빈도에 부합되는 그래픽 어댑터를 사용하여 환경을 개선할 수 있습니다. 예를 들어 Surface Hub에서 권장되는 최상의 대체 PC 경험은 120Hz 비디오 신호 사용입니다.

**55인치 Surface Hub** - 최상의 환경을 얻으려면 120Hz에서 1080p 해상도를 지원하는 그래픽 카드를 사용합니다.

**84인치 Surface Hub** - 최상의 환경을 위해 4개의 DisplayPort 1.2 스트림을 출력하여 120Hz에서 2160p(120Hz 수직 새로 고침에서 3840 x 2160)를 구현할 수 있는 그래픽 카드를 사용합니다. 이러한 그래픽 카드는 NVIDIA Quadro K2200, NVIDIA Quadro K4200 및 NVIDIA Quadro M6000, AMD FirePro W5100, AMD FirePro W7100 및 AMD FirePro W9100에서 작동됩니다. 이러한 그래픽 카드뿐 아니라 다른 공급업체의 다른 제품도 사용할 수 있습니다. 

최신 드라이버에 대해서는 그래픽 카드 공급업체에 직접 확인하세요.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>그래픽 카드 공급업체</th>
<th>드라이버 다운로드 페이지</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NVIDIA</p></td>
<td><p><a href="http://nvidia.com/Download/index.aspx" data-raw-source="[http://nvidia.com/Download/index.aspx](http://nvidia.com/Download/index.aspx)">http://nvidia.com/Download/index.aspx</a></p></td>
</tr>
<tr class="even">
<td><p>AMD</p></td>
<td><p><a href="http://support.amd.com/en-us/download" data-raw-source="[http://support.amd.com/en-us/download](http://support.amd.com/en-us/download)">http://support.amd.com/en-us/download</a></p></td>
</tr>
<tr class="odd">
<td><p>Intel</p></td>
<td><p><a href="https://downloadcenter.intel.com/" data-raw-source="[https://downloadcenter.intel.com/](https://downloadcenter.intel.com/)">https://downloadcenter.intel.com/</a></p></td>
</tr>
</tbody>
</table>

 

### 포트

55인치 Surface Hub의 대체 PC 포트입니다.

![55인치 Surface Hub의 대체 PC 포트를 보여 주는 이미지](images/sh-55-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>유형</th>
<th>인터페이스</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PC 비디오</p></td>
<td><p>비디오 입력</p></td>
<td><p>DP 1.2</p></td>
<td><ul>
<li><p>120Hz에서 1080p의 전체 화면 디스플레이 및 오디오</p></li>
<li><p>HDCP 규격</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>내부 주변 장치</p></td>
<td><p>USB 출력</p></td>
<td><p>USB 2.0, B형</p></td>
<td><ul>
<li><p>터치</p></li>
<li><p>펜</p></li>
<li><p>스피커</p></li>
<li><p>마이크</p></li>
<li><p>카메라</p></li>
<li><p>NFC 센서</p></li>
<li><p>주변 광원 센서</p></li>
<li><p>수동 적외선 센서</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 허브</p></td>
<td><p>USB 출력</p></td>
<td><p>USB 2.0, B형</p></td>
<td><ul>
<li><p>USB 포트 아래</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

84인치 Surface Hub의 대체 PC 포트입니다.

![84인치 Surface Hub의 대체 PC 포트를 보여 주는 이미지](images/sh-84-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>유형</th>
<th>인터페이스</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PC 비디오</p></td>
<td><p>비디오 입력</p></td>
<td><p>DP 1.2(2x)</p></td>
<td><ul>
<li><p>120Hz에서 2160p의 전체 화면 디스플레이 및 오디오</p></li>
<li><p>HDCP 규격</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>내부 주변 장치</p></td>
<td><p>USB 출력</p></td>
<td><p>USB 2.0, B형</p></td>
<td><ul>
<li><p>터치</p></li>
<li><p>펜</p></li>
<li><p>스피커</p></li>
<li><p>마이크</p></li>
<li><p>카메라</p></li>
<li><p>NFC 센서</p></li>
<li><p>주변 광원 센서</p></li>
<li><p>수동 적외선 센서</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 허브</p></td>
<td><p>USB 출력</p></td>
<td><p>USB 2.0, B형</p></td>
<td><ul>
<li><p>USB 포트 아래</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### 대체 PC 설치 지침

**대체 PC 모드를 사용하려면**

1.  대체 PC에서 [Surface Hub 대체 PC 드라이버 패키지](https://www.microsoft.com/download/details.aspx?id=52210)를 다운로드하여 설치합니다.

    >[!NOTE]
    >대체 PC에서 절전 또는 최대 절전 모드를 설정하는 것이 좋습니다. 그러면 사용하지 않을 때 Surface Hub가 디스플레이를 끕니다.

2.  전원 케이블 옆에 있는 전원 스위치를 사용하여 Surface Hub를 끕니다.

3.  Surface Hub의 대체 PC 포트에서 대체 PC로 케이블을 연결합니다. 이러한 포트는 일반적으로 탈부착형 플라스틱 덮개로 보호되어 있습니다.

    55인치 Surface Hub -- 하나의 DisplayPort 케이블 및 두 개의 USB 케이블을 연결합니다.

    84인치 Surface Hub -- 두 개의 DisplayPort 케이블 및 두 개의 USB 케이블을 연결합니다.

4.  모드 스위치를 **대체 PC**로 전환합니다. 모드 스위치는 대체 PC 포트 옆에 있습니다.

5.  전원 케이블 옆에 있는 전원 스위치를 사용하여 Surface Hub를 켭니다.

6.  Surface Hub의 오른쪽에 있는 전원 단추를 누릅니다.

Surface Hub를 전환하여 내부 PC를 사용할 수 있습니다.

**내부 PC로 다시 전환하려면**

1.  전원 케이블 옆에 있는 전원 스위치를 사용하여 Surface Hub를 끕니다.

2.  모드 스위치를 내부 PC로 전환합니다. 모드 스위치는 대체 PC 포트 옆에 있습니다.

3.  전원 케이블 옆에 있는 전원 스위치를 사용하여 Surface Hub를 켭니다.

 
## 비디오 출력
 
Surface Hub에는 Surface Hub의 시각적 콘텐츠를 다른 디스플레이에서 미러링하기 위한 비디오 출력 포트가 포함되어 있습니다.

### 포트

55인치 Surface Hub의 비디오 출력 포트

![비디오 출력 포트 그림](images/video-out-55.png)

84인치 Surface Hub의 비디오 출력 포트

![비디오 출력 포트 그림](images/video-out-84.png)

<table>
<thead>
<tr class="header">
<th>설명</th>
<th>유형</th>
<th>인터페이스</th>
<th>접근 권한 값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>비디오 출력 미러</p></td>
<td><p>비디오 출력</p></td>
<td><p>비디오 출력</p></td>
<td><ul>
<li><p>표준 DisplayPort 모니터에 대한 연결을 지원합니다(24bpp에서 1080p60 해상도를 표시하는 x4 링크만 지원함).</p></li>
<li><p>DisplayPort-HDMI 어댑터를 사용하여 HDMI 모니터(1080p60 지원) 사용을 지원함</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 케이블

55인치 및 84인치 Surface Hub 장치는 인증된 DisplayPort 및 HDMI 케이블과 함께 작동하도록 테스트되었습니다.  여러 공급업체에서 Surface Hub와 함께 작동할 수도 있는 더 긴 케이블을 판매하지만 테스트 랩을 통해 인증된 케이블만 Surface Hub와 작동합니다. 예를 들어 DisplayPort 케이블은 최대 3미터로 인증되었지만 많은 공급업체에서 이보다 3배 긴 케이블을 판매합니다. 긴 케이블이 필요한 경우 HDMI를 사용하는 것이 좋습니다.  HDMI는 리피터 사용을 포함하여 장거리 케이블에 대한 경제적인 솔루션을 제공합니다. HDMI 싱크가 감지되는 경우 거의 모든 DisplayPort 소스가 HDMI 신호로 자동 전환됩니다.


## Bluetooth 액세서리

다음 액세서리를 Bluetooth를 사용하여 Surface Hub에 연결할 수 있습니다.

- 마우스
- 키보드
- 헤드셋
- 스피커

>[!NOTE]
>Bluetooth 헤드셋 또는 스피커를 연결한 후 [기본 마이크와 스피커 설정](local-management-surface-hub-settings.md)을 변경해야 할 수 있습니다.
