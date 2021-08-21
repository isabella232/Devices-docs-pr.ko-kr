---
title: Microsoft Teams 룸 Surface Hub
description: 이 문서에서는 이 문서에 대한 Microsoft Teams 룸 개요를 Surface Hub.
keywords: Teams 룸, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 2d8bd08c150c1665365ae21bc87fd3485b8c69a8
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "11909978"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Microsoft Teams 룸 Surface Hub

Teams 룸 Surface Hub 9월 23일을 [](hub-teams-app.md) 시작하여 4주간의 전역 출시의 일부로 현재 Surface Hub Teams 앱을 자동으로 대체합니다. 현재 Windows 프로그램을 통해 미리 보기로 사용할 수 있는 새로운 Teams 환경의 데모는 Teams 룸 [에서](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373)Surface Hub.

## <a name="whats-new"></a>새로운 기능

- Surface Hub 시작 화면 또는 새 안건 페이지에서 참가한 모임은 "Edge를 Edge로" 참가하여 다른 사람들이 포그라운드에 넣습니다.
- 채팅 거품, 반응, 데스크톱 및 응용 프로그램 공유를 비롯한 친숙한 모임 기능, 제어 및 오디오 제공 및 사용, 전체 PowerPoint 라이브 지원, 함께 모드 및 대규모 갤러리.
- Teams 룸 응용 Surface Hub 나란히 실행하거나 최소화된 응용 프로그램을 실행할 수 있습니다.
- 관리자는 모임에 대한 협정 모임 및 근접 연결과 같은 기능을 구성할 Surface Hub. [XML 파일은](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) 지원되는 새 설정 모델로 마이그레이션됩니다.
- 새로운 QoS 옵션 및 네트워크 요구 사항. 자세한 내용은 [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub.](surface-hub-teams-rooms-networking.md)
- Teams 모드로 변경되어 비즈니스용 Skype 및 모임 앱으로 대체됩니다. 자세한 내용은 에 대한 Microsoft Teams [배포를 Surface Hub.](/MicrosoftTeams/teams-surface-hub)

## <a name="in-meeting-experience"></a>모임 환경

Teams 룸 Surface Hub 환경은 사용자가 개인 장치에서 알고 있는 친숙한 환경과 일치하고 큰 화면 디바이스에 최적화된 조정을 제공합니다. 사용자 Teams Surface Hub 사용하면 원터치 모임 참가, 모임 시작 및 PSTN 또는 피어 투 피어 통화를 위한 다이얼 패드 등의 주요 기능에 액세스할 수 있습니다.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams 룸 안건에 Surface Hub 수 있습니다.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams 룸 모임에서 Surface Hub 수 있습니다.":::

## <a name="manage-teams-rooms-on-surface-hub"></a>사용자 Teams 룸 관리 Surface Hub

 다음을 포함하여 Teams 자격 증명을 입력한 후 설정 사용자 지정할 수 있습니다.

- [협정 모임 및](/microsoftteams/rooms/coordinated-meetings) 근접 참가를 구성합니다.
- 기본 마이크, 카메라 및 스피커에 대한 설정을 조정합니다.
- 클라이언트 버전을 확인하고 최신 업데이트를 검색합니다.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams 룸 설정.":::

Teams 룸 클라이언트에 Surface Hub XML 파일, 프로비저닝 패키지 또는 MDM 공급자를 통해 구성된 기존 설정을 자동으로 적용합니다. [Microsoft Teams](/microsoftteams/rooms/surface-hub-manage-config)구성 관리에서 설명하는 이러한 방법은 Surface Hub 에 제공될 Teams 관리의 간소화된 관리에 설명된 새로운 클라우드 기반 [솔루션으로 Surface Hub.](#simplified-management-of-teams-coming-to-surface-hub)

### <a name="prepare-networking-for-teams-rooms"></a>보안에 대한 네트워킹 Teams 룸

최적화 Teams 룸 에 설명된 요구 사항 및 권장 사항은 [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub.](surface-hub-teams-rooms-networking.md)

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>사용자에 대한 Teams 간소화된 관리 Surface Hub

올해 Teams 룸 Surface Hub 릴리스될 때 관리자는 다음 솔루션을 활용할 수 있습니다.

- **Teams 관리 센터.** Teams 관리 센터는 모든 장치에서 Teams 룸 관리하기 위한 포괄적인 Teams 플랫폼을 제공합니다. Teams 관리 센터는 추가 Microsoft Teams 룸 사용할 수 있습니다.
- **Microsoft Teams 룸 관리되는 서비스입니다.** Microsoft Teams 룸 [](/microsoftteams/rooms/microsoft-teams-rooms-premium) 관리 서비스는 클라우드 기반 IT 관리 및 모니터링 서비스로, Microsoft Teams 룸 장치 및 주변 장치를 최신으로 유지하며 사전 모니터링을 통해 훌륭한 사용자 환경에 최적화된 환경을 지원합니다.
