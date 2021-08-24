---
title: Surface Hub 복구 도구 사용
description: 복구 도구를 Surface Hub 사용하여 SSD를 다시 이미지화하는 방법
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: f472d42bba9270b117cfa8cb9b54eaeb020aefc4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910983"
---
# <a name="using-the-surface-hub-recovery-tool"></a>Surface Hub 복구 도구 사용

Microsoft Surface Hub [복구](https://www.microsoft.com/download/details.aspx?id=52210) 도구를 사용하면 지원을 호출하거나 SSD를 교체하지 않고 Surface Hub 데스크톱 Windows 10 사용하여 SSD(Solid State Drive)를 다시 이미지화할 수 있습니다. 이 도구를 사용하면 알 수 없는 관리자 암호, 부팅 오류, 클라우드 복구를 완료할 수 없는 SSD 또는 이전 버전의 운영 체제가 있는 장치의 경우 SSD를 다시 시연할 수 있습니다. 이 도구는 물리적으로 손상된 SDD를 수정하지 않습니다.

복구 도구를 사용하여 Surface Hub SSD를 다시 이미지화하려면 Surface Hub에서 SSD를 제거하고 드라이브를 USB-SATA 케이블에 연결한 다음 복구 도구가 설치된 데스크톱 PC에 케이블을 연결해야 합니다. 기존 드라이브를 사용자 계정에서 제거하는 방법에 대한 자세한 내용은 SURFACE HUB SSD Surface Hub [참조하세요.](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> 장치가 절전 또는 이미지 파일 다운로드를 중단할 수 없습니다.

이 도구가 드라이브를 다시 이미징하지 못하면 지원에 [Surface Hub 문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## <a name="prerequisites"></a>필수 구성 요소

### <a name="mandatory"></a>Mandatory

- 64비트 버전의 Windows 10 1607 이상을 실행하는 호스트 PC입니다.
- 인터넷 액세스
- USB 2.0 이상 포트 열기
- USB-SATA 케이블
- 호스트 컴퓨터에서 10GB의 사용성 있는 디스크 공간
- 대체 제품으로 Surface Hub 또는 지원에서 제공하는 SSD와 함께 제공되는 SSD입니다. Microsoft에서 제공하지 않는 SSD는 지원되지 않습니다.

### <a name="recommended"></a>권장 사항

- 고속 인터넷 연결
- USB 3.0 포트 열기
- USB 3.0 이상 USB-SATA 케이블
- 이미징 도구는 다음과 같은 케이블 만들기 및 모델을 사용하여 테스트했습니다.
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## <a name="download-surface-hub-recovery-tool"></a>복구 Surface Hub 다운로드

Surface Hub 복구 도구는 의 파일 이름에 Surface Hub [IT용](https://www.microsoft.com/download/details.aspx?id=52210) 도구에서 다운로드할 **SurfaceHub_Recovery_v2.7.139.0.msi. **

> [!IMPORTANT]
> 2021년 2월 11일 릴리스된 이 버전은 더 이상 기능이 없는 이전 빌드를 대체합니다. 이전에 이 도구를 다운로드한 경우 제거하고 현재 버전을 설치하세요.

다운로드를 시작하려면 **** 다운로드를 클릭하고 **목록에서**SurfaceHub_Recovery_v2.7.139.0.msi선택하고 다음 을 **클릭합니다.** 팝업에서 다음 중 하나를 선택하십시오.

- **실행을** 클릭하여 설치를 즉시 시작합니다.
- **저장을** 클릭하여 나중에 설치할 수 있도록 다운로드를 컴퓨터에 복사합니다.

호스트 Surface Hub 복구 도구를 설치합니다.

## <a name="run-surface-hub-recovery-tool"></a>복구 Surface Hub 실행

1. 호스트 PC에서 시작 **** 단추를 선택하고 왼쪽의 사전순 목록을 스크롤한 다음 복구 도구 바로 가기를 선택합니다.

    ![Microsoft Surface Hub 복구 도구 바로 가기.](images/shrt-shortcut.png)

2. **시작**을 클릭합니다.

    ![복구 도구 시작 단추입니다.](images/shrt-start.png)


3. 지침 **창에서** 다음 을 **클릭합니다.**

    ![컴퓨터 절전 지침으로 이동하지 않습니다.](images/shrt-guidance.png)

4. 이미지 선택 창에서 **RS2** 또는 후속 **20H2를**클릭하고 계속을 선택한 **다음** 이미지 **다운로드를 선택합니다.**

     ![복구 도구 이미지 선택.](images/shrt-select-image.png)
    ![복구 도구 이미지 다운로드.](images/shrt-download-image.png)

5. 복구 이미지를 다운로드하는 시간은 인터넷 연결 속도에 따라 달라집니다. 평균 회사 연결에서 8GB 이미지 파일을 다운로드하는 데 최대 1시간이 걸릴 수 있습니다.

    ![이미지 다운로드.](images/shrt-download.png)



5. 다운로드가 완료되면 이 도구는 SSD 드라이브를 연결합니다. 도구가 연결된 드라이브를 찾을 수 없는 경우 사용되는 케이블이 해당 드라이브에 SSD의 이름을 보고하지 Windows.  이미징 도구는 드라이브 이름을 "LITEON L CH-128V2S USB Device"로 찾아야 계속할 수 있습니다.  기존 드라이브를 사용자 계정에서 제거하는 방법에 대한 자세한 내용은 SURFACE HUB SSD Surface Hub [참조하세요.](surface-hub-ssd-replacement.md)

    ![커넥트 SSD.](images/shrt-drive.png)

6. 드라이브가 인식되면 시작을 **클릭하여** 이미징 프로세스를 다시 시작할 수 있습니다. 드라이브의 모든 데이터가 지워졌다는 경고에서 확인 을 **클릭합니다.**



    드라이브에 시스템 이미지를 적용하기 전에 SSD가 다시 지정되어 포맷됩니다. 시스템 이진 파일을 복사하는 데는 약 30분이 소요되지만 USB 버스의 속도, 사용되는 케이블 또는 시스템에 설치된 바이러스 백신 소프트웨어에 따라 시간이 오래 걸릴 수 있습니다.



## <a name="troubleshooting-and-common-problems"></a>문제 해결 및 일반적인 문제

문제 | 참고
--- | ---
도구가 SSD 이미지에 실패 | 공장에서 제공하는 SSD와 테스트된 케이블 중 하나를 사용하고 있는지 확인
다시Imaging 프로세스가 중단/고정된 것으로 표시 | SSD에 영향을 주지 않는 Surface Hub 복구 도구를 닫았다가 다시 시작하는 것이 안전합니다.
드라이브가 도구에서 인식되지 않습니다. | SURFACE HUB SSD가 "LITEON L CH-128V2S USB Lite-On 드라이브"로 열호가 열립니다.  드라이브가 다른 명명된 장치로 인식되는 경우 현재 케이블이 호환되지 않습니다. 위에 나열된 다른 케이블 또는 테스트된 케이블 중 하나를 시도해 보아야 합니다.
오류: -2147024809 | 디스크 관리자를 열고 드라이브의 Surface Hub 제거합니다.  드라이브 연결을 끊고 호스트 컴퓨터로 다시 연결합니다. 이미징 도구를 다시 시작합니다.

이 도구가 드라이브를 다시 이미징하지 못하면 지원에 [Surface Hub 문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## <a name="version-history"></a>버전 기록


### <a name="version-v271390"></a>버전 v2.7.139.0

*릴리스 날짜: 2021년 2월 11일*<br>
이 버전의 Surface Hub 복구 도구는 다음에 대한 지원을 추가합니다.

- 보안 업데이트


### <a name="version-v201390"></a>버전 v2.0.139.0

> [!IMPORTANT]
> 이 버전은 더 이상 작동하지 않습니다. 위에 나열된 현재 버전을 다운로드하십시오. 

*릴리스 날짜: 2020년 12월 18일*<br>
이 버전의 Surface Hub 복구 도구는 다음에 대한 지원을 추가합니다.
- 2020 Windows 10 Team 지원하기 위한 업데이트(20H2)
- 사용자 환경 개선
- 아키텍처 변경 사항
- 원격 분석 추가

