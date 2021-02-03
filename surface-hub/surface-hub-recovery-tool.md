---
title: Surface Hub 복구 도구 사용
description: Surface Hub 복구 도구를 사용하여 SSD를 다시 이미지로 하는 방법
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/18/2020
ms.localizationpriority: medium
ms.openlocfilehash: 9df9de731ac5c8f8acb393db3d4b16e9d1c98a9e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312034"
---
# Surface Hub 복구 도구 사용

[Microsoft Surface Hub 복구 도구를](https://www.microsoft.com/download/details.aspx?id=52210) 사용하면 지원을 호출하거나 SSD를 교체하지 않고 Windows 10 데스크톱 장치를 사용하여 Surface Hub SSD(Solid State Drive)를 다시 이미지로 만듭니다. 이 도구를 사용하면 알 수 없는 관리자 암호, 부팅 오류, 클라우드 복구를 완료할 수 없는 SSD 또는 이전 버전의 운영 체제가 있는 장치의 경우 SSD를 다시 설치합니다. 이 도구는 물리적으로 손상된 SSD를 수정하지 않습니다.

복구 도구를 사용하여 Surface Hub SSD를 다시 이미지화하려면 Surface Hub에서 SSD를 제거하고 드라이브를 USB-SATA 케이블에 연결한 다음 복구 도구가 설치된 데스크톱 PC에 케이블을 연결해야 합니다. Surface Hub에서 기존 드라이브를 제거하는 방법에 대한 자세한 내용은 [Surface Hub SSD 교체를 참조하세요.](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> 디바이스가 절전 또는 이미지 파일 다운로드를 중단할 수 없습니다.

이 도구가 드라이브를 다시 이미징하지 못하면 Surface Hub 지원에 [문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## 필수 구성 요소

### Mandatory

- 64비트 버전의 Windows 10 버전 1607 이상을 실행하는 호스트 PC
- 인터넷 액세스
- USB 2.0 이상 포트 열기
- USB-SATA 케이블
- 호스트 컴퓨터의 10GB의 사용성 있는 디스크 공간
- Surface Hub 또는 지원 서비스에서 대체로 제공하는 SSD와 함께 제공되는 SSD입니다. Microsoft에서 제공하지 않는 SSD는 지원되지 않습니다.

### 권장 사항

- 고속 인터넷 연결
- USB 3.0 포트 열기
- USB 3.0 이상 USB-SATA 케이블
- 이미징 도구는 다음과 같은 케이블 만들기 및 모델을 사용하여 테스트했습니다.
    - Startech USB312SAT3CB
    - 일광 RCUC16001
    - Ugreen 20231

## Surface Hub 복구 도구 다운로드

Surface Hub 복구 도구는 [IT용 Surface Hub 도구의](https://www.microsoft.com/download/details.aspx?id=52210) 파일 이름 아래에서 다운로드할 수 **SurfaceHub_Recovery_v2.0.139.0.msi. **

다운로드를 시작하려면 **다운로드를**클릭하고 **목록에서**SurfaceHub_Recovery_v2.0.139.0.msi선택하고 다음을 **클릭합니다.** 팝업에서 다음 중 하나를 선택하십시오.

- **실행을** 클릭하여 설치를 즉시 시작합니다.
- 나중에 **설치할** 수 있도록 저장을 클릭하여 컴퓨터에 다운로드를 복사합니다.

호스트 PC에 Surface Hub 복구 도구를 설치합니다.

## Surface Hub 복구 도구 실행

1. 호스트 PC에서 시작 **** 단추를 선택하고 왼쪽의 사전순 목록을 스크롤한 다음 복구 도구 바로 가기를 선택합니다.

    ![Microsoft Surface Hub 복구 도구 바로 가기](images/shrt-shortcut.png)

2. **시작**을 클릭합니다.

    ![복구 도구 시작 단추](images/shrt-start.png)


3. 지침 **창에서** 다음을 **클릭합니다.**

    ![컴퓨터 절전 지침으로 이동하지 않습니다.](images/shrt-guidance.png)

4. 이미지 선택 창에서 **RS2** 또는 후속 **20H2를** **** 클릭하고 계속을 선택한 다음 이미지 **다운로드를 선택합니다.**

     ![복구 도구 이미지 복구 ](images/shrt-select-image.png) ![ 도구 다운로드 이미지 선택](images/shrt-download-image.png)

5. 복구 이미지를 다운로드하는 시간은 인터넷 연결 속도에 따라 달라집니다. 평균 회사 연결에서 8GB 이미지 파일을 다운로드하는 데 최대 1시간이 걸릴 수 있습니다.

    ![이미지 다운로드](images/shrt-download.png)



5. 다운로드가 완료되면 이 도구는 SSD 드라이브를 연결합니다. 도구가 연결된 드라이브를 찾을 수 없는 경우 사용되는 케이블이 SSD의 이름을 Windows에 보고하지 않을 가능성이 있습니다.  이미징 도구는 드라이브 이름을 "LITEON L CH-128V2S USB Device"로 찾아야 계속할 수 있습니다.  Surface Hub에서 기존 드라이브를 제거하는 방법에 대한 자세한 내용은 [Surface Hub SSD 교체를 참조하세요.](surface-hub-ssd-replacement.md)

    ![SSD 연결](images/shrt-drive.png)

6. 드라이브가 인식되면 **시작을** 클릭하여 다시 이미징 프로세스를 시작할 수 있습니다. 드라이브의 모든 데이터가 지워지리라 경고하고 확인을 **클릭합니다.**



    드라이브에 시스템 이미지를 적용하기 전에 SSD가 다시 지정되어 포맷됩니다. 시스템 이진 파일을 복사하는 데는 약 30분이 소요되지만 USB 버스의 속도, 사용되는 케이블 또는 시스템에 설치된 바이러스 백신 소프트웨어에 따라 시간이 더 오래 걸릴 수 있습니다.



## 문제 해결 및 일반적인 문제

문제 | 참고
--- | ---
도구가 SSD 이미지에 실패 | 팩터리 제공 SSD와 테스트된 케이블 중 하나를 사용하고 있는지 확인
다시imaging 프로세스가 중단/고정된 것으로 표시 | SSD에 영향을 주지 않는 Surface Hub 복구 도구를 닫았다가 다시 시작하는 것이 안전합니다.
도구에서 드라이브를 인식하지 못합니다. | Surface Hub SSD가 "LITEON L CH-128V2S USB 장치Lite-On 드라이브로 열에 있는지 확인합니다.  드라이브가 다른 명명된 장치로 인식되는 경우 현재 케이블이 호환되지 않습니다. 위에 나열된 다른 케이블 또는 테스트된 케이블 중 하나를 시도합니다.
오류: -2147024809 | 디스크 관리자를 열고 Surface Hub 드라이브에서 파티션을 제거합니다.  드라이브 연결을 끊고 호스트 컴퓨터로 다시 연결합니다. 이미징 도구를 다시 시작합니다.

이 도구가 드라이브를 다시 이미징하지 못하면 Surface Hub 지원에 [문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## 버전 기록

### 버전 v2.0.139.0

*릴리스 날짜: 2020년 12월 18일*<br>
이 버전의 Surface Hub 복구 도구는 다음에 대한 지원을 추가합니다.
- Windows 10 Team 2020 업데이트(20H2)를 지원하기 위해 업데이트
- 사용자 환경 개선
- 아키텍처 변경 사항
- 원격 분석 추가

