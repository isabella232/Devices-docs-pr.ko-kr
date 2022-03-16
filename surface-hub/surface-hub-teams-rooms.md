---
title: Surface Hub Microsoft Teams 룸
description: 이 문서에서는 이 문서에 대한 Microsoft Teams 룸 개요를 Surface Hub.
keywords: Teams 룸, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d607a34b532420123941a77d510d19db65531c85
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448731"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Surface Hub Microsoft Teams 룸

Teams 룸 Surface Hub [KB5004196, KB5004198 및 KB5004199](surface-hub-update-history.md)를 설치하면 이전 Surface Hub Teams 앱이 자동으로 대체되었습니다.[](hub-teams-app.md)

## <a name="whats-new"></a>새로운 기능

- 시작 화면 또는 Surface Hub 새 안건 페이지에서 참가한 모임은 "Edge를 Edge로" 참가하여 포그라운드에 넣습니다.
- 채팅 거품, 반응, 데스크톱 및 응용 프로그램 공유를 비롯한 친숙한 모임 기능, 제어 및 오디오 제공 및 사용, 전체 PowerPoint 라이브 지원, 함께 모드 및 대규모 갤러리.
- Teams 룸 응용 Surface Hub 나란히 실행하거나 최소화된 응용 프로그램을 실행할 수 있습니다.
- 관리자는 모임에 대한 협정 모임 및 근접 연결과 같은 기능을 구성할 Surface Hub. [XML 파일은](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) 지원되는 새 설정 모델로 마이그레이션됩니다.
- 새로운 QoS 옵션 및 네트워크 요구 사항. 자세한 내용은 [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).
- 기본 설정 **** >  이 아닌 경우 Teams 오디오에서 모임 및 통화에 대한 기본 설정 **Surface Hub** >  **설정할 & 있습니다**. 모임 모드를 알아보고 MDM 정책을 통해 모임 모드를 구성하는 데 대한 자세한 내용은 [Manage Surface Hub with an MDM provider를 참조하세요](manage-settings-with-mdm-for-surface-hub.md#changing-default-app-for-meetings--calls).

## <a name="in-meeting-experience"></a>모임 환경

Teams 룸 Surface Hub 환경은 사용자가 개인 장치에서 알고 있는 친숙한 환경과 일치하도록 조정되어 큰 화면 디바이스에 최적화됩니다. 사용자가 Teams Surface Hub 원터치 모임 참가, 모임 시작 및 PSTN 또는 피어 투 피어 통화를 위한 다이얼 패드 등의 주요 기능에 액세스할 수 있습니다.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams 룸 안건에 Surface Hub 수 있습니다.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams 룸 모임에서 Surface Hub 수 있습니다.":::

## <a name="manage-teams-rooms-on-surface-hub"></a>사용자 Teams 룸 관리 Surface Hub

 관리 자격 증명을 Teams 다음을 포함하여 설정 메뉴에서 직접 사용자 지정할 수 있습니다.

- [협정 모임 및](/microsoftteams/rooms/coordinated-meetings) 근접 참가를 구성합니다.
- 기본 마이크, 카메라 및 스피커에 대한 설정을 조정합니다.
- 클라이언트 버전을 확인하고 최신 업데이트를 검색합니다.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams 룸 설정.":::

Teams 룸 클라이언트에 Surface Hub XML 파일, 프로비저닝 패키지 또는 MDM 공급자를 통해 구성된 기존 설정을 자동으로 적용합니다. Microsoft Teams 구성 관리에 설명된 [](/microsoftteams/rooms/surface-hub-manage-config)Surface Hub 이러한 방법은 새로운 클라우드 기반 솔루션으로 Teams 솔루션으로 [Surface Hub.](#simplified-management-of-teams-coming-to-surface-hub)

### <a name="prepare-networking-for-teams-rooms"></a>보안에 대한 네트워킹 Teams 룸

최적화 Teams 룸 내용은 [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>사용자에 대한 Teams 간소화된 관리 Surface Hub

올해 Teams 룸 Surface Hub 릴리스될 때 관리자는 다음 솔루션을 활용할 수 있습니다.

- **Teams 관리 센터.** Teams 관리 센터는 모든 장치에서 Teams 룸 환경을 모니터링하고 관리하기 위한 포괄적인 Teams 플랫폼을 제공합니다. Teams 추가 비용 없는 Microsoft Teams 룸 관리 센터를 사용할 수 있습니다.
- **Microsoft Teams 룸 관리되는 서비스입니다.** [Microsoft Teams 룸 관리](/microsoftteams/rooms/microsoft-teams-rooms-premium) 서비스는 클라우드 기반 IT 관리 및 모니터링 서비스로, Microsoft Teams 룸 장치 및 주변 장치를 최신으로 유지하고 사전 예방적으로 모니터링하여 훌륭한 사용자 환경에 최적화된 환경을 지원합니다.


## <a name="support-for-teams-rooms-in-government-community-cloud-high-gcc-h"></a>Teams 룸(정부 커뮤니티 클라우드-H)에서 GCC 지원

Teams 룸 클라이언트에서 버전 1.4.00.25354로 일회성 수동 업데이트가 필요하여 GCC-H 테넌트에 연결한 다음 자동으로 최신 정보를 유지할 수 있습니다.

 - 허브에 KB5005611 이상이 설치되어 Windows 확인
 - [Teams_Uninstall_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Uninstall_Win32.ppkg)를 사용하여 Teams 룸 버전에서 현재 Surface Hub 제거
 - 장치 다시 시작
 - [Teams_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Win32.ppkg)를 설치하여 버전 1.4.00.25354 설치
 - 장치 다시 시작

세부 단계:

1. USB 드라이브의 루트에 프로비저닝 패키지를 모두 저장합니다.
2.  USB 드라이브를 디바이스에 Surface Hub.
3.  사용자 Surface Hub 열고 시작 메뉴 모든 앱을 선택한 다음 앱을 설정.
4.  메시지가 표시될 때 허브 관리자 자격 증명을 제공합니다.
5.  **** >  Surface Hub **관리** > **로 이동하거나** 프로비저닝 패키지를 제거한 다음 패키지 추가**를 선택합니다**.
6.  패키지 **선택에서** Teams_Uninstall_win32.ppkg 프로비저닝 패키지를 선택한 다음 패키지를 다시 Surface Hub.
7.  사용자 Surface Hub 열고 시작 메뉴 모든 앱을 선택한 다음 앱을 설정.
8.  메시지가 표시될 때 허브 관리자 자격 증명을 제공합니다.
9.  **** >  Surface Hub **관리** > **로 이동하거나** 프로비저닝 패키지를 제거한 다음 패키지 추가**를 선택합니다**.
10. 패키지 **선택에서** Teams_win32.ppkg 프로비저닝 패키지를 선택한 다음 패키지를 다시 Surface Hub.
