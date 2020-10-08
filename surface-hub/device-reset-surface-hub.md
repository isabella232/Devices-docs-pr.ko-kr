---
title: Surface Hub 다시 설정 또는 복구
description: Surface Hub의 초기화 및 복구 프로세스를 설명 하 고 지침을 제공 합니다.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 다시 설정, 복구
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104820"
---
# Surface Hub 다시 설정 또는 복구

이 문서에서는 Microsoft Surface Hub를 다시 설정 하거나 복구 하는 방법에 대해 설명 합니다.  

[Surface Hub를 다시 설정](#reset-a-surface-hub) 하면 해당 운영 체제가 마지막 누적 Windows 업데이트에 반환 되 고 모든 로컬 사용자 파일 및 구성 정보는 제거 됩니다. 제거 되는 정보에는 다음이 포함 됩니다.

- 디바이스 계정
- 디바이스의 로컬 관리자에 대 한 계정 정보
- 도메인 참가 또는 Azure AD 참가 정보
- MDM (모바일 디바이스 관리) 등록 정보
- MDM 또는 설정 앱을 사용 하 여 설정 된 구성 정보

[클라우드에서 Surface Hub를 복구](#recover-a-surface-hub-from-the-cloud) 하면이 정보도 제거 됩니다. 또한 Surface Hub는 새 운영 체제 이미지를 다운로드 하 여 설치 합니다. 복구 프로세스가 Surface Hub에 저장 된 다른 정보를 유지 하는지 여부를 지정할 수 있습니다.

## Surface Hub 다시 설정

다음과 같은 이유로 Surface Hub를 다시 설정 해야 할 수 있습니다.

- 새 모임 공간을 위해 장치를 다시 purposing 하 고 다시 구성 하려고 합니다.
- 로컬에서 디바이스를 관리하는 방법을 변경하려고 합니다.
- 장치 계정 또는 관리자 계정의 사용자 이름 또는 암호가 손실 되었습니다.
- 업데이트를 설치 하면 장치의 성능이 저하 됩니다.

다시 설정 하는 동안 오랜 시간 동안 빈 화면이 표시 되는 경우에는 잠시 기다린 후 작업을 수행 하지 마세요.

> [!WARNING]
> 장치 재설정 프로세스는 최대 6 시간까지 걸릴 수 있습니다. 프로세스가 완료 될 때까지 Surface Hub를 끄거나 뽑으십시오. 프로세스를 중단 하면 장치가 작동 하지 않게 됩니다. 장치가 다시 작동 되려면 보증 서비스가 필요 합니다.

1. Surface Hub에서 **설정**을 엽니다.

   ![Surface Hub에 대 한 설정 앱을 표시 하는 이미지입니다.](images/sh-settings.png)

1. **업데이트 & 보안**을 선택 합니다.

   ![Surface Hub 용 설정 앱의 업데이트 & 보안 그룹을 표시 하는 이미지입니다.](images/sh-settings-update-security.png)

1. **복구**를 선택한 다음 **장치 초기화**에서 **시작**을 선택 합니다.

   ![Surface Hub 용 설정 앱의 장치 초기화 옵션을 표시 하는 이미지입니다.](images/sh-settings-reset-device.png)

   재설정 프로세스가 완료 되 면 Surface Hub는 [첫 번째 실행 프로그램](first-run-program-surface-hub.md) 을 다시 시작 합니다. 다시 설정 프로세스에서 문제가 발생 하면 Surface Hub를 이전 운영 체제 이미지로 롤백하고 시작 화면을 표시 합니다.

<span id="cloud-recovery" />

## 클라우드에서 Surface Hub 복구

어떤 이유로 Surface Hub를 사용할 수 없게 되 면 Microsoft Support에 대 한 지원을 거치지 않고 클라우드에서 해당 허브를 복구할 수 있습니다. Surface Hub는 클라우드에서 새로운 운영 체제 이미지를 다운로드 하 고 해당 이미지를 사용 하 여 운영 체제를 다시 설치할 수 있습니다.

다음과 같은 경우에 이러한 유형의 복구 프로세스를 사용 해야 할 수 있습니다.

- [Surface Hub 또는 관련 계정이 불안정 한 상태입니다.](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub가 잠겼습니다.](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>**클라우드로 복구** 프로세스에는 오픈 인터넷 연결을 제공 하는 유선 연결이 필요 합니다 (프록시 또는 기타 인증 메시지 표시 안 함).

### 잘못된 상태의 Surface Hub 복구

디바이스 계정이 불안정 한 상태에 도달 하거나 관리자 계정에 문제가 발생 한 경우 설정 앱을 사용 하 여 클라우드 복구 프로세스를 시작할 수 있습니다. [장치 재설정](#reset-a-surface-hub) 프로세스에서 문제를 해결 하지 못하는 경우에만 클라우드 복구 프로세스를 사용 해야 합니다.

1. Surface Hub에서 **설정** &gt; **업데이트 & 보안** &gt; **복구**를 선택 합니다.

1. **클라우드에서 복구**에서 **지금 다시 시작**을 선택 합니다.

   ![클라우드에서 복구](images/recover-from-the-cloud.png)

### 잠긴 Surface Hub 복구

드물지만 Surface Hub에서 세션 종료 시 사용자 및 앱 데이터를 정리하는 동안 오류가 발생할 수 있습니다. 이 문제가 발생 하면 장치가 자동으로 다시 시작 되 고 작업을 다시 시도 합니다. 그러나이 작업이 반복적으로 실행 되지 않으면 사용자 데이터를 보호 하기 위해 디바이스가 자동으로 잠깁니다. 잠금을 해제 하려면 [장치를 다시 설정](#reset-a-surface-hub) 하거나, 제대로 작동 하지 않는 경우 클라우드에서 복구 해야 합니다.

1. Surface Hub 아래쪽에서 전원 스위치를 찾습니다. 전원 스위치는 전원 코드 연결 옆에 있습니다. 전원 스위치에 대 한 자세한 내용은 [Surface Hub 사이트 준비 가이드 (PDF)](surface-hub-site-readiness-guide.md)를 참조 하세요.

1. Surface Hub가 시작 화면을 표시 하는 동안 power 스위치를 사용 하 여 Surface Hub를 끕니다.

1. 전원 스위치를 사용 하 여 Surface Hub를 다시 켭니다. 장치가 시작 되 고 Surface Hub 로고 화면을 표시 합니다. Surface Hub 로고 아래에 회전 점이 표시 되 면 power 스위치를 사용 하 여 Surface Hub를 다시 끕니다.  

1. 3 3 번 또는 Surface Hub에 "자동 복구 준비 중" 메시지가 표시 될 때까지 단계를 반복 합니다. 이 메시지가 표시 되 면 Surface Hub는 Windows RE 화면을 표시 합니다.

1. **고급 옵션**을 선택 합니다.

1. **클라우드에서 복구**를 선택 합니다. (선택 사항) **다시 설정을**선택할 수도 있습니다. 하지만 **클라우드에서 복구** 하는 것이 권장 되는 방법입니다.

   ![클라우드에서 복구](images/recover-from-cloud.png)
1. Bitlocker 키를 입력 하 라는 메시지가 표시 되 면 다음 중 하나를 수행 합니다.

   - Bitlocker에서 Surface Hub에 대해 보호 하는 정보를 보존 하려면 Bitlocker 키를 입력 합니다.
   - 보호 된 정보를 삭제 하려면 **이 드라이브 건너뛰기를** 선택 합니다.  

1. 메시지가 표시 되 면 **다시 설치**를 선택 합니다.

    ![다시 설치](images/reinstall.png)

1. 디스크를 다시 분할 하려면 **예**를 선택 합니다.

   ![다시 분할](images/repartition.png)

   첫 번째는 복구 프로세스가 클라우드에서 운영 체제 이미지를 다운로드 하는 것입니다.  

   ![97& 다운로드](images/recover-progress.png)

   다운로드가 완료 되 면 복구 프로세스가 선택한 옵션에 따라 Surface Hub를 복원 합니다.
   

## 고객 지원

질문이 있거나 도움이 필요한 경우 [지원 요청을 만들](https://support.microsoft.com/supportforbusiness/productselection)수 있습니다.


## 관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)
