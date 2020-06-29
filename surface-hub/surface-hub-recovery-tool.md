---
title: Surface Hub 복구 도구 사용
description: Surface Hub 복구 도구를 사용 하 여 SSD를 다시 이미지 하는 방법을 설명 합니다.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836896"
---
# Surface Hub 복구 도구 사용

[Microsoft Surface Hub 복구 도구](https://www.microsoft.com/download/details.aspx?id=52210) 는 지원 또는 ssd 교체 없이 Windows 10 데스크톱 장치를 사용 하 여 SURFACE hub Ssd (고체 상태 드라이브)를 다시 이미지 하는 데 도움이 됩니다. 이 도구를 사용 하 여 알 수 없는 관리자 암호를 가진 SSD, 부팅 오류, 클라우드 복구를 완료할 수 없거나 이전 버전의 운영 체제가 있는 장치에 대 한 목록을 이미지로 삽입할 수 있습니다. 도구가 물리적으로 손상 된 SSDs를 수정 하지 않습니다.

복구 도구를 사용 하 여 Surface Hub SSD를 다시 이미지 하려면 Surface Hub에서 SSD를 제거 하 고 드라이브를 USB에서 SATA 케이블로 연결한 다음 복구 도구가 설치 된 데스크톱 PC에 케이블을 연결 해야 합니다. Surface Hub에서 기존 드라이브를 제거 하는 방법에 대 한 자세한 내용은 [Surface HUB SSD 대체](surface-hub-ssd-replacement.md)를 참조 하세요.

> [!IMPORTANT]
> 장치를 절전 모드로 전환 하거나 이미지 파일의 다운로드를 중단 하지 마세요.

도구가 드라이브 reimaging에 실패 하는 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.

## 필수 구성 요소

### Mandatory

- 64 비트 버전의 Windows 10, 버전 1607 이상에서 실행 되는 호스트 PC
- 인터넷 액세스
- USB 2.0 이상 포트 열기
- USB 대 SATA 케이블
- 호스트 컴퓨터에서 10gb의 사용 가능한 디스크 공간
- SSDs는 Surface Hub 또는 지원 자가 제공 하는 SSD (대체)와 함께 제공 됩니다. Microsoft에서 제공 하지 않은 SSDs는 지원 되지 않습니다.

### 권장 사항

- 고속 인터넷 연결
- USB 3.0 포트 열기
- USB 3.0 이상 USB-SATA 케이블
- 이미징 도구는 다음 케이블의 제조업체와 모델로 테스트 했습니다.
    - Startech USB312SAT3CB
    - RCUC16001 예정
    - Ugreen 20231

## Surface Hub 복구 도구 다운로드

Surface Hub 복구 도구는 [Surface Hub 도구](https://www.microsoft.com/download/details.aspx?id=52210) 에서 다운로드할 수 있는 파일 이름 **SurfaceHub_Recovery_v1.14.137.0.msi**에 있습니다.

다운로드를 시작 하려면 **다운로드**를 클릭 하 고 목록에서 **SurfaceHub_Recovery_v1.14.137.0.msi** 를 선택한 후 **다음**을 클릭 합니다. 팝업 창에서 다음 중 하나를 선택 합니다.

- **실행** 을 클릭 하 여 바로 설치를 시작 합니다.
- **저장** 을 클릭 하 여 나중에 설치 하기 위해 다운로드를 컴퓨터에 복사 합니다.

호스트 PC에 Surface Hub 복구 도구를 설치 합니다.

## Surface Hub 복구 도구 실행

1. 호스트 PC에서 **시작** 단추를 선택 하 고 왼쪽에 있는 알파벳순 목록을 스크롤한 다음 복구 도구 바로 가기를 선택 합니다.

    ![Microsoft Surface Hub 복구 도구 바로 가기](images/shrt-shortcut.png)

2. **시작**을 클릭합니다.

    ![복구 도구 시작 단추](images/shrt-start.png)

3. **지침** 창에서 **다음**을 클릭 합니다.

    ![컴퓨터가 절전 지침으로 이동 하지 않도록 합니다.](images/shrt-guidance.png)

4. **예** 를 클릭 하 여 이미지를 다운로드 합니다. 복구 이미지를 다운로드 하는 데 걸리는 시간은 인터넷 연결 속도에 따라 다릅니다. 평균 기업 연결에서는 8GB 이미지 파일을 다운로드 하는 데 최대 1 시간까지 걸릴 수 있습니다.

    ![이미지를 다운로드 하 시겠습니까?](images/shrt-download.png)

5. 다운로드가 완료 되 면이 도구는 SSD 드라이브에 연결 하도록 지시 합니다. 도구가 연결 된 드라이브를 찾을 수 없는 경우 사용 중인 케이블이 Windows에 SSD의 이름을 보고 하지 않는 것이 좋습니다.  계속 하려면 이미징 도구가 "LITEON L CH-128V2S USB Device"로 드라이브의 이름을 찾아야 합니다.  Surface Hub에서 기존 드라이브를 제거 하는 방법에 대 한 자세한 내용은 [Surface HUB SSD 대체](surface-hub-ssd-replacement.md)를 참조 하세요.

    ![SSD 연결](images/shrt-drive.png)

6. 드라이브가 인식 되 면 **시작** 을 클릭 하 여 다시 이미징 프로세스를 시작 합니다. 드라이브의 모든 데이터가 삭제 된다는 경고 메시지가 표시 되 면 **확인**을 클릭 합니다.

    ![SSD 다시 이미징 시작](images/shrt-drive-start.png)

    시스템 이미지를 드라이브에 적용 하기 전에 SSD는 repartitioned이 고 형식이 지정 됩니다. 시스템 바이너리 복사에는 약 30 분이 소요 되지만, USB 버스 속도, 사용 하는 케이블 또는 시스템에 설치 된 바이러스 백신 소프트웨어에 따라 시간이 더 걸릴 수 있습니다.

    ![복사 완료](images/shrt-done.png)

    ![Reimaging 완료](images/shrt-complete.png)

## 문제 해결 및 일반적인 문제

문제 | 참고
--- | ---
도구가 SSD를 이미지 하는 데 실패 함 | 출하 시 제공 된 SSD와 테스트 된 케이블 중 하나를 사용 하 고 있는지 확인 합니다.
Reimaging 프로세스가 중지/동결 된 것 처럼 나타남 | SSD에 아무런 영향도 주지 않고 Surface Hub 복구 도구를 닫았다가 다시 시작 하는 것이 안전 합니다.
도구가이 드라이브를 인식 하지 못합니다. | Surface Hub SSD는 Lite 드라이브 "LITEON L CH-128V2S USB 장치"로 열거 되는지 확인 합니다.  드라이브가 다른 명명 된 장치로 인식 되 면 현재 케이블이 호환 되지 않는 것입니다. 다른 케이블을 사용 하거나 위에 나열 된 테스트 되는 케이블 중 하나를 사용해 봅니다.
오류:-2147024809 | 디스크 관리자를 열고 Surface Hub 드라이브에서 파티션을 제거 합니다.  호스트 컴퓨터에 드라이브의 연결을 끊었다가 다시 연결 합니다. 이미징 도구를 다시 시작 합니다.

도구가 드라이브 reimaging에 실패 하는 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.
