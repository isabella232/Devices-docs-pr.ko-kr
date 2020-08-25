---
title: Surface Hub 2S 다시 설정 및 복구
description: Surface Hub 2S를 복구 하 고 다시 설정 하는 방법을 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 7d79fab22b62e6ef29832be6241c484e9caf72e0
ms.sourcegitcommit: 537fa38bdd21fcd679af0764e734f4b8efb6a03f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "10959950"
---
# Surface Hub 2S 다시 설정 및 복구

Surface Hub 2S에 문제가 발생 하는 경우 디바이스를 공장 설정으로 초기화 하거나 USB 드라이브를 사용 하 여 복원할 수 있습니다.

시작 하려면 관리자 자격 증명을 사용 하 여 Surface Hub 2S에 로그인 하 고 **설정** 앱을 열고 **업데이트 & 보안**을 선택한 다음 **복구**를 선택 합니다.

## 장치 초기화

1. 장치를 다시 설정 하려면 **시작**하기를 선택 합니다.

2. **이 장치를 재설정할 준비가 되었습니다** 창이 나타나면 **재설정**을 선택 합니다. 
  
   > [!NOTE]
   > Surface Hub 2S 복구 파티션에서 운영 체제를 다시 설치 합니다. 완료 되는 데 최대 1 시간이 걸릴 수 있습니다.
  
3. 장치를 다시 구성 하려면 첫 번째 설치 프로그램을 실행 합니다.

4. Microsoft Intune 또는 다른 모바일 장치 관리 솔루션을 사용 하 여 장치를 관리 하는 경우 이전 레코드를 중지 하 고 삭제 한 다음 새 장치를 다시 등록 합니다. 자세한 내용은 [닦아내기, 사용 중지 또는 수동으로 디바이스를 unenrolling 하 여 장치 제거](https://docs.microsoft.com/intune/devices-wipe)를 참조 하세요.

> [!div class="mx-imgBorder"]
> ![* Surface Hub 2S 다시 설정 및 복구 *](images/sh2-reset.png)
<br/>*그림 1. Surface Hub 2S 다시 설정 및 복구* 

## USB 복구 드라이브를 사용 하 여 Surface Hub 2S 복구

Surface Hub 2S에서 새로 만들기 이제 복구 이미지를 사용 하 여 디바이스를 다시 설치할 수 있습니다.

### USB 드라이브에서 복구

Surface Hub 2S를 사용 하 여 복구 이미지를 사용 하 여 디바이스를 다시 설치할 수 있습니다. 이렇게 하면 BitLocker 키를 잃어버린 경우 또는 설정 앱에 대 한 관리자 자격 증명이 더 이상 없는 경우 디바이스를 공장 설정에 다시 설치할 수 있습니다.

>[!NOTE]
>8 GB 또는 16gb의 저장소가 있는 USB 3.0 드라이브와 FAT32로 포맷 된 저장소를 사용 합니다.

1. 별도의 PC에서 [Surface recovery 웹 사이트](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 의 .zip 파일 복구 이미지를 다운로드 하 고 다음 지침으로 돌아갑니다. 

1. 다운로드 한 파일의 압축을 USB 드라이브의 루트에 놓습니다.  

1. USB 드라이브를 usb-C 또는 USB-A Surface Hub 2S의 포트에 연결 합니다.

1. 디바이스 끄기:

   1. 볼륨 크게 단추를 누른 상태에서 전원 단추를 누릅니다.
   1. Windows 로고가 나타날 때까지 두 단추를 계속 누릅니다.
   1. 전원 단추를 해제 하 고 설치 UI가 시작 될 때까지 계속 볼륨 단추를 누르고 있습니다.

   ![* 볼륨 작게 및 전원 단추를 사용 하 여 복구 시작 *](images/sh2-keypad.png) <br>
   **그림 2. 볼륨 및 전원 단추**

1. 언어 선택 화면에서 Surface Hub 2S 표시 언어를 선택 합니다.

1. **드라이브에서 복구** 를 선택 하 고 **드라이브를 완전히 정리한**다음 **복구**를 선택 합니다. BitLocker 키를 요청 하는 메시지가 표시 되 면 **이 드라이브 건너뛰기를**선택 합니다. Surface Hub 2S는 여러 번 재부팅 되며 복구 프로세스를 완료 하는 데 30 분 정도 걸립니다.

첫 번째 설정 화면이 나타나면 USB 드라이브를 제거 합니다.

## 고객 지원

질문이 있거나 도움이 필요한 경우 [지원 요청을 만들](https://support.microsoft.com/supportforbusiness/productselection)수 있습니다.
