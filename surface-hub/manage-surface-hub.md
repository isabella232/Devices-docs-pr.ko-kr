---
title: Microsoft Surface Hub 관리
description: 첫 실행 프로그램을 완료한 후 Surface Hub를 관리하는 방법
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 04eb2b08ebc8fc7034ab5d27a038c5d517a2eda3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10837009"
---
# Microsoft Surface Hub 관리

Microsoft Surface Hub의 초기 설정 후에 다음과 같은 몇 가지 방법으로 디바이스 설정 및 구성을 수정하거나 변경할 수 있습니다.

- **로컬 관리** - 디바이스에서 **설정** 앱을 사용하여 모든 Surface Hub를 로컬에서 구성할 수 있습니다. 권한이 없는 사용자가 설정을 변경하지 못하도록 설정 앱에서는 관리자 자격 증명을 사용하여 앱을 열어야 합니다. 자세한 내용은 [Surface Hub 설정에 대한 로컬 관리](local-management-surface-hub-settings.md)를 참조하세요.
- **원격 관리** -Surface Hub를 통해 IT 관리자는 microsoft Intune, Microsoft Endpoint Configuration Manager 및 기타 타사 공급자와 같은 MDM (모바일 디바이스 관리) 공급자를 사용 하 여 설정 및 정책을 관리할 수 있습니다. 또한 관리자는 Microsoft OMS(Operations Management Suite)를 사용하여 Surface Hub를 모니터링할 수 있습니다. 자세한 내용은 [MDM 공급자 설정 관리](manage-settings-with-mdm-for-surface-hub.md) 및 [Microsoft Surface Hub 모니터링](monitor-surface-hub.md)을 참조하세요. 

> [!NOTE]
> 이러한 관리 방법은 함께 사용할 수 있습니다. 선택할 경우 디바이스를 로컬 및 원격으로 둘 다 관리할 수 있습니다. 그러나 Surface Hub가 관리 서버와 동기화될 때 MDM 정책 및 설정이 로컬 변경 내용을 덮어씁니다. 

## 이 섹션의 내용

Surface Hub 관리 및 업데이트에 대해 알아봅니다.

| 항목 | 설명 |
| ----- | ----------- |
| [원격 Surface Hub 관리](remote-surface-hub-management.md) |Surface Hub 원격 관리에 관련된 항목입니다. MDM을 사용하여 설정을 관리하고 Operations Management Suite를 사용하여 모니터링하는 설치 앱을 포함합니다. |
| [Surface Hub 설정 관리](manage-surface-hub-settings.md) |접근성, 디바이스 계정, 디바이스 초기화, 정규화된 도메인 이름, Windows 업데이트 설정, 무선 네트워크 등의 Surface Hub 설정 관리에 관련된 항목입니다. |
| [Surface Hub에 앱 설치]( https://technet.microsoft.com/itpro/surface-hub/install-apps-on-surface-hub) | 관리자는 Microsoft Store 또는 비즈니스용 Microsoft Store에서 앱을 설치할 수 있습니다.|
[Surface Hub 시작 메뉴 구성](surface-hub-start-menu.md) | MDM를 사용하여 Surface Hub에 대한 시작 메뉴를 사용자 지정합니다.
| [Microsoft Whiteboard 설정 및 사용](whiteboard-collaboration.md)  | Microsoft Whiteboard의 최신 업데이트에는 실시간으로 동일한 보드에서 공동 작업하기 위한 두 개의 Surface Hub에 대한 기능이 포함되어 있습니다.   |
| [세션 종료를 사용하여 모임 종료](https://technet.microsoft.com/itpro/surface-hub/i-am-done-finishing-your-surface-hub-meeting) | 모임이 끝나면 사용자가 **세션 종료**를 탭하여 중요한 데이터를 정리하고 다음 모임을 위해 장치를 준비할 수 있습니다.|
| [Microsoft Authenticator로 Surface Hub 로그인](surface-hub-authenticator-app.md) | Android 및 iOS에서 사용 가능한 Microsoft Authenticator 앱을 사용하여 암호 없이 Surface Hub에 로그인할 수 있습니다.   |
| [BitLocker 키 저장](https://technet.microsoft.com/itpro/surface-hub/save-bitlocker-key-surface-hub) | 모든 Surface Hub가 BitLocker 드라이브 암호화 소프트웨어를 사용하여 자동으로 설정됩니다. BitLocker 복구 키를 백업하는 것이 좋습니다.|
| [다른 디바이스를 연결하여 Surface Hub에서 표시](https://technet.microsoft.com/itpro/surface-hub/connect-and-display-with-surface-hub) | 다른 디바이스를 Surface Hub에 연결하여 콘텐츠를 표시할 수 있습니다.|
| [기존 무선 네트워크 또는 LAN의 Miracast](miracast-over-infrastructure.md) | 무선 네트워크 또는 LAN에서 Miracast를 사용하여 Surface Hub에 연결할 수 있습니다. |
 [802.1 x 유선 인증 사용](enable-8021x-wired-authentication.md) | Surface Hub 디바이스에 802.1x 유선 인증 MDM 정책이 활성화되었습니다. 
| [회의실 제어 시스템 사용](https://technet.microsoft.com/itpro/surface-hub/use-room-control-system-with-surface-hub) | Microsoft Surface Hub와 함께 회의실 제어 시스템을 사용할 수 있습니다.|
[Surface Hub 복구 도구 사용](surface-hub-recovery-tool.md) | Surface Hub 복구 도구를 사용 하 여 Surface Hub SSD를 다시 이미지 합니다.
[Surface Hub SSD 교체](surface-hub-ssd-replacement.md) | Surface Hub의 고체 상태 드라이브를 제거 하 고 바꾸는 방법에 대해 알아봅니다.

## 관련 항목

- [Surface Hub 및 Windows 10에서 Power BI 프레젠테이션 모드 보기](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
