---
title: 디바이스 계정에 ActiveSync 정책 적용(Surface Hub)
description: Microsoft Surface Hub의 디바이스 계정은 ActiveSync를 사용하여 메일과 일정을 동기화합니다. 이렇게 하면 사용자가 Surface Hub에서 예약된 모임에 참가하고 시작할 수 있으며, 모임 중에 작성한 모든 화이트보드를 메일로 보낼 수 있습니다.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, ActiveSync 정책
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: fa393eca697897ee620732b543ebb6889aa035d1
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472577"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>디바이스 계정에 ActiveSync 정책 적용(Surface Hub)

Windows 10 Team 1703 및 이전 버전의 Surface Hub는 ActiveSync를 사용하여 메일 & 일정을 동기화했습니다.

조직의 ActiveSync 정책에 대한 Surface Hub 요구 사항은 다음과 같습니다.

-   Surface Hub 디바이스 계정에서 사용 중인 리소스 사서함의 동기화를 차단하는 전역 정책은 없습니다. 이러한 차단 정책이 있는 경우 Surface Hub 허용된 디바이스로 추가해야 합니다.
-   **PasswordEnabled** 설정이 False로 설정된 모바일 디바이스 사서함 정책을 설정해야 합니다. 기타 모바일 디바이스 사서함 정책 설정은 Surface Hub와 호환되지 않습니다.

## <a name="allowing-the-deviceid"></a>DeviceID 허용

조직에 Surface Hub에서 프로비전된 디바이스 계정의 동기화를 차단하는 전역 정책이 있을 수 있습니다. 이 속성을 구성하려면 [ActiveSync에 디바이스 ID 허용](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync)을 참조하세요.

## <a name="setting-passwordenabled"></a>PasswordEnabled 설정

디바이스 계정에 **PasswordEnabled** 특성이 False 또는 0으로 설정된 ActiveSync 정책이 있어야 합니다. 이 속성을 구성하려면 [Microsoft Surface Hub 호환 Exchange ActiveSync 정책 만들기](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)를 참조하세요.

 

 





