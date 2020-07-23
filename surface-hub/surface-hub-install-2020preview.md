---
title: Windows 10 Team 2020 업데이트 Preview 빌드 설치
description: Surface Hub 운영 체제, Windows 10 Team 2020 업데이트의 최신 업데이트를 지금 사용할 수 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894114"
---
# Windows 10 Team 2020 업데이트 Preview 빌드 설치 

Surface hub 운영 체제, **windows 10 Team 2020 업데이트**의 최신 업데이트는 [windows 참가자 프로그램](https://insider.windows.com)에서 surface hub 50-인치 및 surface hub 2S 55-인치 장치에 대 한 추가 비용 없이 제공 됩니다. Surface Hub 84 인치 모델은 Windows 10 Team 2020 업데이트의 최종 릴리스에서 지원 됩니다.

Windows 10 Team 2020 업데이트는 Windows 10의 최신 기능과 함께 장치 배포 및 관리 효율성을 대폭 개선 합니다. 새로운 기능에 대해 자세히 알아보려면 다음 블로그 게시물을 참조 하세요. [공개 미리 보기에 대 한 새 Surface HUB OS 업데이트를 해제 했습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) 알려진 문제점은 아래의 "알려진 문제" 섹션을 참조 하세요.
 
## 필수 구성 요소

- [Windows 참가자 프로그램](https://insider.windows.com/)을 사용 하 여 등록 합니다.
- Windows 참가자 프로그램의 빠른 채널에서 Windows 10 Team 2020 업데이트 Preview 빌드를 다운로드 합니다.
- Preview 빌드를 설치한 후 필요한 펌웨어 업데이트를 다운로드 합니다. 참고: Windows 참가자 프로그램을 종료 하기로 결정 한 경우에도 펌웨어 업데이트를 제거할 수 없습니다.

## Surface Hub 준비

시작 하기 전에 Surface Hub에 Windows 업데이트에서 최신 업데이트가 있는지 확인 하 고 장치와 연결 된 BitLocker 키를 저장 해야 합니다.

**수동으로 업데이트를 확인 하려면 다음을 수행 합니다.**

1. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
2. **업데이트 & 보안**  >  **Windows 업데이트** 를 탐색 한 다음 **업데이트 확인**을 선택 합니다.

자세한 내용은 [Surface Hub에서 Windows 업데이트 관리](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)를 참조 하세요.

**BitLocker 키를 수동으로 저장 하려면 다음을 수행 합니다.**

1. Surface Hub에 USB 드라이브를 삽입 합니다.
2. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
3. **& 보안**  >  **복구**업데이트로 이동 합니다.
4. **BitLocker**에서 **저장**을 선택 합니다. BitLocker 키가 USB 드라이브의 텍스트 파일에 저장 됩니다.

자세한 내용은 [BitLocker 키 저장](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)을 참조 하세요.
 
## Windows 10 Team 2020 업데이트 Preview 빌드 설치

1. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
2. **& 보안**  >  **Windows 참가자 프로그램** 업데이트로 이동한 다음 **시작**을 선택 합니다.
3. 메시지에 따라 회사 계정 (권장) 또는 개인 Microsoft 계정을 사용 하 여 Windows 참가자에 등록 합니다. 회사 계정으로 등록 하는 이점에 대 한 자세한 내용은 [비즈니스용 Windows 참가자 프로그램 등록](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)을 참조 하세요.
4. **참가자 설정 선택**에서 **빠른**을 선택 합니다.
5. Surface Hub에서 미리 보기 빌드와 필요한 펌웨어 업데이트를 다음 3 ~ 4 일 동안 자동으로 설치 하도록 허용 합니다. 이 장치는 일상적인 [유지 관리 창](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)에서 자동으로 업데이트를 다운로드 하 고 설치 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

- 첫 번째 유지 관리 창에서 Surface Hub는 Windows 업데이트에서 Preview 빌드를 다운로드 하기 시작 합니다.
- 두 번째 유지 관리 기간 동안 장치가 다시 시작 되어 업데이트를 완료 합니다.
- 세 번째 유지 관리 창에서 장치는 필요한 펌웨어 업데이트를 다운로드 하 여 설치 합니다.

> [!IMPORTANT]
> Microsoft는 장치에서 미리 보기 빌드와 필요한 펌웨어 업데이트 설치를 완료할 수 있도록 3-4 일간 Surface Hub를 예약 하는 것이 좋습니다. 이 과정 중 장치를 사용 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 발생할 수 있습니다.

### Preview 빌드 및 필수 펌웨어 업데이트를 수동으로 설치 하도록 선택 하는 경우:

1. Windows 참가자 프로그램에 등록 한 후에는 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로** 이동한 다음 **업데이트 확인** 을 선택 하 여 Preview 빌드를 설치 합니다.
2. Preview 빌드를 설치한 후 (최대 14 시간까지 소요 될 수 있음) **지금 다시 시작** 을 선택 하 여 설치를 완료 합니다.
3. 장치가 다시 시작 되 면 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로**이동한 다음 **업데이트 확인을 선택 하 여 필요한 펌웨어 업데이트를 설치**합니다.
4. 펌웨어가 설치 되 면 **지금 다시 시작**을 선택 합니다.

> [!WARNING]
> 필요한 펌웨어 업데이트를 설치 하지 않고 Preview 빌드를 설치 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 표시 될 수 있습니다.

> [!NOTE]
> Windows 참가자 프로그램을 종료 하 고 Surface Hub를 이전 버전의 운영 체제로 되돌리려는 경우 먼저 [장치를 재설정](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)해야 합니다. 나중에 장치를 다시 구성 하려면 [첫 번째 실행 프로그램](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 을 거쳐야 합니다.
 
## 알려진 문제점: Windows 10 Team 2020 업데이트 Preview 빌드

### 그래픽, 오디오 및 사용자 인터페이스 문제 

미리 보기 빌드를 설치 하 고 나중에 필요한 펌웨어 업데이트를 즉시 설치 하지 않는 경우 다양 한 그래픽 및 사용자 인터페이스 문제가 발생할 수 있습니다. Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서 이러한 문제를 해결 하는 계획입니다.

### Surface Hub 84-인치: 그래픽 및 사용자 인터페이스 문제

첫 번째 세대 Surface Hub 84 인치 장치에서 Preview 빌드를 설치 하는 경우 다양 한 그래픽 및 사용자 인터페이스 문제가 발생할 수 있습니다. Surface Hub 84-인치는 Windows 10 Team 2020 업데이트의 최종 릴리스에서 지원 됩니다.

### 조건부 액세스 정책이 적용 되는 경우 로그인에 영향을 미칩니다.

- Microsoft 화이트 보드와 같은 앱에 로그인 하려고 하면 로그인이 실패 합니다. 사용자는 먼저 시작 메뉴에서 [내 모임 및 파일](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) 에 로그인 해야 합니다.

- 사용자 계정이 Surface Hub에서 Azure AD 조인에 사용 하는 것과 다른 Azure AD 테 넌 트에 등록 되어 있으면 로그인이 실패 합니다.

Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서 이러한 문제를 해결 하는 계획입니다.

### 사용할 수 없는 경우 Windows 업데이트에서 새 드라이버를 설치 하 라는 메시지가 표시 됨

**Settings**  >  **Update & Security**  >  Windows 10 Team 2020 업데이트와 필요한 펌웨어 업데이트를 설치한 후 설정 업데이트 & 보안**Windows 업데이트로** 이동 하면 다음 오류가 표시 될 수 있습니다. 

- "PC의 현재 드라이버가 설치 하려고 하는 드라이버 보다 더 좋을 수 있습니다. 설치를 계속 시도 합니다. " 

이 오류는 무시 해도 됩니다. Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.

### 프로비저닝 패키지를 사용 하 여 Surface Hub 정책을 설치할 수 없음

Surface Hub CSP (구성 서비스 공급자)의 정책을 사용 하는 배포 패키지를 설치 하지 못했습니다. 지금은 Microsoft Intune 또는 다른 MDM (모바일 디바이스 관리) 공급자를 사용 하 여 Surface Hub 정책을 적용 합니다. Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서이 문제를 해결 하기 위한 계획입니다.

### 처음 실행할 때 USB 드라이브를 중간에 제거 하 라는 메시지 표시

처음 실행 하는 동안 배포 패키지를 사용 하 여 Surface Hub를 설정 하는 경우 장치가 Surface Hub 구성 파일을 읽을 수 있으려면 먼저 USB 드라이브를 제거 하 라는 메시지가 표시 됩니다. 구성 파일을 사용 하 여 장치 계정을 설정 하는 경우에는 메시지를 무시 합니다. Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.
 
### 처음 실행 하는 동안 프록시 설정을 설정할 수 없음

프록시를 사용 하 여 인터넷에 연결 하는 경우 첫 번째 실행 프로그램에서 인터넷 연결이 제한 될 수 있습니다. Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서이 문제를 해결 하기 위한 계획입니다.
 
### Microsoft Store에서 앱을 다운로드 하면 오류가 표시 됩니다.

Microsoft Store에서 앱을 다운로드 하려면 로그인 하 라는 메시지가 표시 됩니다. 알려진 문제로 인해 로그인 중 오류가 표시 되지만 앱을 다운로드 하는 기능에는 영향을 주지 않습니다. Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.

### Surface Hub 2S가 Wi-fi 연결을 일시적으로 잃는 경우

장치를 분리 하 여 다시 연결 하거나 이더넷 케이블을 사용 하 여 인터넷에 연결 해 봅니다. Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.

### Surface Hub 2S 일시적으로 절전 모드에서 다시 시작 되지 않음

Surface Hub 2S 일시적으로 절전 모드에서 완전히 다시 시작 되지 않고 Microsoft 로고를 표시 하는 화면에서 응답 하지 않는 것 처럼 보일 수 있습니다. 장치를 분리 하 고 다시 연결 해 보세요. 

이 문제가 발생 하지 않도록 하려면 다음을 수행 합니다.

1. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
2. **Surface Hub**  >  **세션 & 전원을**탐색 합니다. 
3. **장치가 절전 모드로 전환 되는 경우 다음 전원 설정을 사용 하 여** **연결 된 대기 모드를 선택 합니다.**
4. 아무도 없는 경우에는 **장치를 다음으로 절전 모드로 전환 하**고 사용 **안 함을 선택 합니다.**

Microsoft는 Windows 10 Team 2020 업데이트의 최종 릴리스 이전에 펌웨어 업데이트로이 문제를 해결 하기 위한 계획입니다.

### 연결 앱이 보기에 없는 경우의 프로젝션 문제

- 케이블을 사용 하 여 Surface Hub에 프로젝션 할 때 연결 앱에서 다른 위치로 이동 하면 touchback 작동이 중지 됩니다.
- Miracast를 사용 하 여 허브에 투영할 때 연결 앱에서 다른 위치로 이동 하면 무선 연결이 곧 삭제 됩니다.

Microsoft는 이러한 문제를 적극적으로 조사 하 고 있습니다.

### 비즈니스용 Skype가 미디어 트래픽에 대 한 프록시를 사용 하 고 있지 않습니다.

프록시를 사용 하는 일부 장치에서는 비즈니스용 Skype가 로그인 할 수 있지만, 미디어 트래픽에 대 한 프록시 서버는 사용 되지 않습니다. Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.

Microsoft 지원으로 사용자의 의견 및 제안을 공유 하도록 초대 합니다.

## 자세히 알아보기

- [공개 미리 보기에 대 한 새로운 Surface Hub OS 업데이트를 해제 했습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [비즈니스용 Windows 참가자 프로그램 시작하기](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)