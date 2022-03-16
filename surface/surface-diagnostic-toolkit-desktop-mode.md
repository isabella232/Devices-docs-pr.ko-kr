---
title: 비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용
description: SDT를 사용하여 조직의 사용자가 도구를 실행하여 Surface 디바이스의 문제를 식별하고 진단하고 도구에서 직접 지원 요청을 제출하는 방법
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 811fc2875e6865c5160594b36c5166457b678ebb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449441"
---
# <a name="use-surface-diagnostic-toolkit-for-business-in-desktop-mode"></a>비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용

이 항목에서는 SDT(Surface Diagnostic Toolkit)를 사용하여 조직의 사용자가 도구를 실행하여 Surface 디바이스의 문제를 식별하고 진단하고 도구에서 직접 지원 요청을 제출하는 방법에 대해 설명합니다. 

SDT를 성공적으로 실행하면 하드웨어 오류 또는 사용자 오류로 인해 보고된 문제가 발생하는지 빠르게 확인할 수 있습니다. SDT에서 지원되는 Surface 디바이스 목록은 [Deploy Surface Diagnostic Toolkit for Business를 참조하세요](surface-diagnostic-toolkit-business.md).


1. 사용자에게 소프트웨어 배포 지점 또는 네트워크 공유에서 [SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution) 패키지를 설치하도록 지시합니다. 설치가 완료된 후 일련의 테스트를 통해 사용자를 안내할 수 있습니다. 

2. 사용자가 문제 설명을 입력할 수 있는 홈 페이지에서 시작하고 그림 1과 같이 **계속**을 클릭합니다.

    ![데스크톱 모드에서 SDT를 시작하십시오.](images/sdt-desk-1.png)<br/>
    *그림 1. 데스크톱 모드의 SDT*

3. SDT가 장치에 최신 업데이트가 있는 것으로 표시되면 그림 2와 같이 **계속** 을 클릭하여 사용 가능한 테스트 카탈로그로 진행합니다.

    ![SDT 옵션에서 선택합니다.](images/sdt1.png)<br/>
    *그림 2. SDT 옵션에서 선택*

4. 모든 진단 테스트를 실행 하게 선택할 수 있습니다. 또는 결함이 있는 디스플레이 또는 전원 공급 장치 문제와 같은 특정 문제가 이미 의심되는 경우 선택을 클릭하여 사용 **** 가능한 테스트에서 선택하고 선택된 실행을 클릭합니다****( 그림 3). 각 테스트에 대한 자세한 내용은 다음 표를 참조합니다. 

    ![하드웨어 테스트를 선택합니다.](images/sdt2.png)<br/>
    *그림 3. 하드웨어 테스트 선택*

    하드웨어 테스트 | 설명
    --- | ---
    전원 공급 장치 및 배터리 |  전원 공급 기능이 최적으로 작동하고 있는지 확인
    디스플레이 및 소리   | 밝기, 픽스 또는 데드 픽셀, 스피커 및 마이크 작동 확인
    포트 및 액세서리   | 액세서리, 화면 연결 및 USB 작동 확인
    Connectivity |  연결 Bluetooth, 무선 및 LTE 연결 확인
    보안    | 보안 관련 문제 확인
    터치   | 터치 관련 문제 확인
    키보드 및 터치 |    통합 키보드 연결 및 유형 커버 확인
    센서 | 장치에서 여러 센서의 작동 확인
    하드웨어 |  그래픽 카드 및 카메라와 같은 다양한 하드웨어 구성 요소의 문제 확인

5. 모든 테스트가 완료되면 도구에서 문제가 해결된지 확인을 요청합니다. 

    ![문제가 해결된 경우](images/sdt3.png)<br/>
    *그림 3a. 문제가 해결된 경우*

6. 문제가 해결되지 않은 경우 또는 모르는 경우 지금 도움을 받을 수 있도록 문의를 선택하여 지원 티켓**을 제출할 수 있습니다.** ****
 
    ![지원 티켓을 제출합니다.](images/sdt4.png)<br/>
    *그림 3b. 지원 티켓 제출*

<span id="multiple" />

## <a name="running-multiple-hardware-tests-to-troubleshoot-issues"></a>여러 하드웨어 테스트를 실행하여 문제 해결

SDT는 일련의 테스트를 실행하는 대화형 도구로 디자인되었습니다. 각 테스트에 대해 SDT는 테스트의 특성과 테스트가 성공하기 위해 사용자가 기대하거나 찾아야 하는 사항을 요약하는 지침을 제공합니다. 예를 들어 디스플레이 밝기가 제대로 작동하고 있는지 진단하기 위해 SDT는 0부터 시작하여 밝기를 100%로 늘리며 사용자에게 그림 4에 표시된 예 또는 아니요 **** 에 응답 **** 하여 해당 밝기가 예상대로 작동하고 있는지 확인하게 합니다. 

각 테스트에서 기능이 예상대로 작동하지 않는 경우 **사용자가 아니**요를 클릭하면 SDT는 가능한 원인 및 문제 해결 방법에 대한 보고서를 생성합니다. 

![하드웨어 진단 실행.](images/sdt-desk-4.png)
 *그림 4. 하드웨어 진단 실행*

1. 밝기가 예상대로 0~100%에서 조정되는 경우 사용자에게 예를 클릭한 다음 **계속을 클릭합니다**.**** 
2. 밝기가 예상대로 0~100%에서 조정되지 않을 경우 사용자에게 아니요를 클릭한 다음 계속을 **** 클릭하도록 **지시합니다**. 
3. 남은 테스트를 적절하게 안내합니다. 완료되면 SDT는 하드웨어 문제의 가능한 원인과 해결 지침을 포함하여 보고서에 대한 높은 수준의 요약을 자동으로 제공합니다.


### <a name="repairing-applications"></a>응용 프로그램 복구

SDT를 사용하면 그림 5와 같이 문제를 유발할 수 있는 응용 프로그램을 진단하고 복구할 수 있습니다.

![복구 실행.](images/sdt-desk-5.png)
 *그림 5. 복구 실행*
<span id="logs" />

### <a name="generating-logs-for-analyzing-issues"></a>문제 분석에 대한 로그 생성 

SDT는 그림 6과 같이 응용 프로그램, 드라이버, 하드웨어 및 운영 체제 문제 전반에 걸쳐 광범위한 로그 사용 진단 지원을 제공합니다.

![로그 생성.](images/sdt-desk-6.png)
 *그림 6. 로그 생성*

<span id="detailed-report" />

### <a name="generating-detailed-report-comparing-device-vs-optimal-configuration"></a>장치와 최적의 구성을 비교하는 자세한 보고서 생성

로그에 따라 SDT는 기본 위치에 저장할 수 있는 소프트웨어 및 펌웨어 기반 문제에 대한 보고서를 생성합니다.

## <a name="related-topics"></a>관련 항목

- [비즈니스용 Surface 진단 앱을 사용하여 명령줄 Toolkit 실행](surface-diagnostic-toolkit-command-line.md)
