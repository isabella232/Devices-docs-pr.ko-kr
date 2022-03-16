---
title: 사용자에 대한 초기화 및 Surface Hub
description: 사용자에 대한 초기화 및 복구 프로세스를 Surface Hub 지침을 제공합니다.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 초기화 Surface Hub, 복구
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: f0292d4c2ec599ba620ab87930fbecf3bab9e078
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449281"
---
# <a name="reset-and-recovery-for-surface-hub"></a>사용자에 대한 초기화 및 Surface Hub

이 문서에서는 사용자 설정을 다시 설정하는 Microsoft Surface Hub.  

[이 Surface Hub](#reset-a-surface-hub) 다시 설정하면 운영 체제가 마지막 누적 업데이트로 Windows 모든 로컬 사용자 파일 및 구성 정보가 제거됩니다. 제거되는 정보는 다음과 같습니다.

- 디바이스 계정
- 디바이스의 로컬 관리자에 대한 계정 정보
- 도메인 가입 또는 Azure AD 가입 정보
- MDM(모바일 장치 관리) 등록 정보
- MDM 또는 앱 앱을 사용하여 설정 정보

복구 프로세스에서 복구 프로세스에 저장된 다른 정보를 보존할지 여부를 Surface Hub. 초기화 옵션을 사용할 수 없는 경우 Surface Hub 복구 도구를 [](surface-hub-recovery-tool.md) 사용하여 SSD의 Surface Hub 수 있습니다.

## <a name="reset-a-surface-hub"></a>사용자 Surface Hub

다음과 같은 이유로 Surface Hub 다시 설정해야 할 수 있습니다.

- 새 모임 공간에 대해 장치를 다시 구성하고 있습니다.
- 로컬에서 디바이스를 관리하는 방법을 변경하려고 합니다.

초기화 프로세스 동안 오랜 시간 동안 빈 화면이 표시되면 기다렸다가 아무 작업도 수행하지 않습니다.

> [!WARNING]
> 장치 초기화 프로세스는 최대 6시간이 걸릴 수 있습니다. 프로세스가 완료될 때까지 Surface Hub 해제하거나 끄지 않습니다. 프로세스를 중단하면 디바이스를 사용할 수 없습니다. 장치를 다시 작동하려면 보증 서비스가 필요합니다.

1. Surface Hub에서 **설정**을 엽니다.

   > [!div class="mx-imgBorder"]
   > ![앱에 설정 앱을 보여 Surface Hub.](images/sh-settings.png)

2. 보안 **업데이트 & 선택합니다**.

   > [!div class="mx-imgBorder"]
   > ![설정 앱의 & 보안 그룹을 보여 Surface Hub.](images/sh-settings-update-security.png)

3. 복구 **를** 선택한 다음 장치 초기 **화에서** 시작 **을 선택합니다**.

   > [!IMPORTANT]
   > 디바이스를 초기화하기 전에 BitLocker 키를 사용할 수 있도록 하세요. 나중에 다시하라는 메시지가 표시됩니다. 자세한 내용은 [BitLocker 키 저장을 참조합니다](save-bitlocker-key-surface-hub.md). 허브가 복구 파티션으로 다시 시작하면 BitLocker 키를 입력하라는 메시지가 표시됩니다. 이 프롬프트를 건너뛰면 재설정이 실패합니다.
   
   > [!div class="mx-imgBorder"]
   > ![설정 앱의 디바이스 초기화 옵션을 보여 Surface Hub.](images/sh-settings-reset-device.png)

   초기화 프로세스가 완료되면 Surface Hub [프로그램을 다시 시작합니다](first-run-program-surface-hub.md). 초기화 프로세스에서 문제가 발생하면 다시 Surface Hub 운영 체제 이미지로 다시 롤백한 다음 시작 화면을 표시합니다.

## <a name="recover-a-locked-surface-hub"></a>잠긴 Surface Hub 복구

어떤 이유로 Surface Hub 사용할 수 없게 되어 설정 앱에서 초기화할 수 없는 경우 BitLocker 복구 키가 있는 경우 Surface Hub 다시 설정할 수 있습니다.

1. 전원 스위치를 아래쪽에 Surface Hub. 전원 스위치는 전원 코드 연결 옆에 있습니다. 전원 스위치에 대한 자세한 내용은 Surface Hub 사이트 준비 가이드([PDF)를 참조하세요](surface-hub-site-readiness-guide.md).

2. 시작 Surface Hub 표시하는 동안 전원 스위치를 사용하여 시작 화면을 Surface Hub.

3. 전원 스위치를 사용하여 전원을 Surface Hub 켜야 합니다. 디바이스가 시작되어 로고 Surface Hub 표시됩니다. 로고 아래 회전하는 점은 Surface Hub 전원 스위치를 사용하여 다시 Surface Hub 끄는 것입니다.  

4. 3단계를 두 번 반복하거나 "Surface Hub 복구 준비" 메시지가 표시될 때까지 반복합니다. 이 메시지를 표시하면 Surface Hub 화면이 Windows RE 표시됩니다.
 
5. **다시 설정**을 선택합니다.

6. 로컬 **다시 설치를 선택합니다.**

7. 드라이브 **완전 정리를 선택합니다.**
 
   ![복구하고 드라이브를 완전히 정리합니다.](images/recover-fully-clean-drive.png)

8. 이 장치를 초기화할 준비가 되 **나요?를 묻는 질문이 표시됩니다**. **다시 설정**을 선택합니다. 
   
   ![recover and confirm reset.](images/recover-confirm-reset.png)


## <a name="contact-support"></a>고객 지원

질문이 있는 경우나 도움이 필요한 경우 지원 [요청을 만들 수 있습니다](https://support.microsoft.com/supportforbusiness/productselection).


## <a name="related-topics"></a>관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)
