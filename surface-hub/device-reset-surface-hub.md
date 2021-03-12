---
title: Surface Hub 초기화 또는 복구
description: Surface Hub의 초기화 및 복구 프로세스를 설명하고 지침을 제공합니다.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 초기화, 복구
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406646"
---
# <a name="reset-or-recover-a-surface-hub"></a>Surface Hub 초기화 또는 복구

이 문서에서는 Microsoft Surface Hub를 초기화하거나 복구하는 방법을 설명합니다.  

[Surface Hub를](#reset-a-surface-hub) 초기화하면 운영 체제가 마지막 누적 Windows 업데이트로 돌아가고 모든 로컬 사용자 파일 및 구성 정보가 제거됩니다. 제거되는 정보는 다음과 같습니다.

- 디바이스 계정
- 디바이스의 로컬 관리자에 대한 계정 정보
- 도메인 가입 또는 Azure AD 가입 정보
- MDM(모바일 장치 관리) 등록 정보
- MDM 또는 설정 앱을 사용하여 설정한 구성 정보

[클라우드에서 Surface Hub를 복구하면](#recover-a-surface-hub-from-the-cloud) 이 정보도 제거됩니다. 또한 Surface Hub는 새 운영 체제 이미지를 다운로드하여 설치합니다. 복구 프로세스에서 Surface Hub에 저장된 다른 정보를 보존할지 여부를 지정할 수 있습니다. 이러한 옵션을 모두 사용할 수 없는 [Surface Hub를](surface-hub-recovery-tool.md) 복구해야 하는 경우 Surface Hub 복구 도구에서 동일한 운영 체제 이미지가 사용됩니다.

## <a name="reset-a-surface-hub"></a>Surface Hub 초기화

다음과 같은 이유로 Surface Hub를 초기화해야 할 수 있습니다.

- 새 모임 공간에 대해 장치를 다시 비우고 다시 구성하려는 경우
- 로컬에서 디바이스를 관리하는 방법을 변경하려고 합니다.
- 장치 계정 또는 관리자 계정의 사용자 이름 또는 암호가 손실된 경우
- 업데이트를 설치하면 장치의 성능이 저하됩니다.

초기화 프로세스 동안 오랜 시간 동안 빈 화면이 표시되면 기다렸다가 아무 작업도 수행하지 않습니다.

> [!WARNING]
> 장치 초기화 프로세스는 최대 6시간이 걸릴 수 있습니다. 프로세스가 완료될 때까지 Surface Hub를 끄거나 끄지 마십시오. 프로세스를 중단하면 디바이스를 사용할 수 없습니다. 장치를 다시 작동하려면 보증 서비스가 필요합니다.

1. Surface Hub에서 **설정**을 엽니다.

   ![Surface Hub에 대한 설정 앱을 보여 주는 이미지입니다.](images/sh-settings.png)

2. 보안 **및 & 업데이트를 선택합니다.**

   ![Surface Hub용 설정 & 보안 그룹 업데이트 표시 이미지.](images/sh-settings-update-security.png)

3. **복구를**선택하고 장치 **초기화에서** **시작을 선택합니다.**

   > [!IMPORTANT]
   > 디바이스를 초기화하기 전에 BitLocker 키를 사용할 수 있도록 하세요. 나중에 다시하라는 메시지가 표시됩니다. 자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md) 허브가 복구 파티션으로 다시 시작하면 BitLocker 키를 입력하라는 메시지가 표시됩니다. 이 프롬프트를 건너뛰면 재설정이 실패합니다.
   
   ![Surface Hub용 설정 앱의 디바이스 초기화 옵션을 보여 주는 이미지입니다.](images/sh-settings-reset-device.png)

   초기화 프로세스가 완료되면 Surface Hub가 첫 번째 실행 [프로그램을 다시](first-run-program-surface-hub.md) 시작합니다. 초기화 프로세스에서 문제가 발생하면 Surface Hub를 다시 기존 운영 체제 이미지로 롤백한 다음 시작 화면을 표시합니다.

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>클라우드에서 Surface Hub 복구

어떤 이유로 Surface Hub를 사용할 수 없는 경우 Microsoft 지원의 도움 없이 클라우드에서 복구할 수 있습니다. Surface Hub는 클라우드에서 새 운영 체제 이미지를 다운로드하고 해당 이미지를 사용하여 운영 체제를 다시 설치합니다.

다음과 같은 상황에서는 이 유형의 복구 프로세스를 사용해야 할 수 있습니다.

- [Surface Hub 또는 관련 계정이 불안정한 상태로 들어오고 있습니다.](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub가 잠겨 있습니다.](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>클라우드에서 **복구를** 사용하려면 개방형 인터넷 연결을 제공하는 유선 연결이 필요합니다(프록시 또는 기타 인증 프롬프트 없음).

### <a name="recover-a-surface-hub-in-a-bad-state"></a>잘못된 상태의 Surface Hub 복구

장치 계정이 불안정한 상태가 되거나 관리자 계정에 문제가 발생하는 경우 설정 앱을 사용하여 클라우드 복구 프로세스를 시작할 수 있습니다. 장치 초기화 프로세스로 문제가 [](#reset-a-surface-hub) 해결되지 않는 경우 클라우드 복구 프로세스만 사용해야 합니다.

1. Surface Hub에서 설정 **업데이트** 및 &gt; **보안 &** &gt; **를 선택합니다.**

2. 클라우드에서 **복구에서**지금 다시 **시작을 선택합니다.**

   ![클라우드에서 복구](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>잠긴 Surface Hub 복구

드물지만 Surface Hub에서 세션 종료 시 사용자 및 앱 데이터를 정리하는 동안 오류가 발생할 수 있습니다. 이 경우 장치가 자동으로 다시 시작되고 작업을 다시 시작합니다. 그러나 이 작업이 반복적으로 실패하면 장치가 자동으로 잠겨 사용자 데이터를 보호합니다. 잠금을 해제하려면 [](#reset-a-surface-hub) 디바이스를 초기화해야 합니다. 그렇지 않은 경우 클라우드에서 복구해야 합니다.

1. Surface Hub 아래쪽에서 전원 스위치를 찾습니다. 전원 스위치는 전원 코드 연결 옆에 있습니다. 전원 스위치에 대한 자세한 내용은 Surface Hub 사이트 준비 [가이드(PDF)를 참조하세요.](surface-hub-site-readiness-guide.md)

2. Surface Hub가 시작 화면을 표시하는 동안 전원 스위치를 사용하여 Surface Hub를 끄십시오.

3. 전원 스위치를 사용하여 Surface Hub를 다시 켜십시오. 디바이스가 시작하고 Surface Hub 로고 화면을 표시합니다. Surface Hub 로고 아래에 회전하는 점이 표시하면 전원 스위치를 사용하여 Surface Hub를 다시 끄십시오.  

4. 3단계를 세 번 반복하거나 Surface Hub에 "자동 복구 준비" 메시지가 표시될 때까지 반복합니다. 이 메시지를 표시하면 Surface Hub에 Windows RE 화면이 표시됩니다.

 
5. 초기화 **를 선택하여 Windows를 다시 설치합니다.** 
![다시 설치로 재설정](images/recover-from-cloud.png)

8. 클라우드 **다운로드를 선택합니다.** 

   ![클라우드 다운로드](images/recover-cloud-download.png)

>[!IMPORTANT]
>다운로드할 수 **없습니다.를**나타내는 오류 메시지가 표시되면 **취소를** 선택하고 다시 시도하십시오.

9. 드라이브 **완전 정리를 선택합니다.**  
![ 복구 및 완전히 정리된 드라이브](images/recover-fully-clean-drive.png)

10. 이 장치를 초기화할 준비가 **되나요?를 묻는 질문이 표시됩니다.** **다시 설정**을 선택합니다. 
![복구 및 재설정 확인](images/recover-confirm-reset.png)

11. 다운로드가 시작되면 복구 프로세스가 이 장치 **초기화 를 나타냅니다.** 
![진행 중으로 표시된 복구](images/recover-in-progress.png)

## <a name="contact-support"></a>고객 지원

질문이 있는 경우 또는 도움이 필요한 경우 지원 [요청을 만들 수 있습니다.](https://support.microsoft.com/supportforbusiness/productselection)


## <a name="related-topics"></a>관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)
