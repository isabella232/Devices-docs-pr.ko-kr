---
title: 표면 지우기 펜 2  haptics 개발 참고 사항
description: 이 페이지에서는 비즈니스용 Surface에디션 펜 2의 Windows 11 기능을 확장하려는 앱 개발자를 위한 구현 참고를 제공합니다.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: 8a3dbbdde85cfdceaf5674750a68fc21d3fcd877
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338706"
---
# <a name="surface-slim-pen-2-haptics-dev-notes"></a>표면 지우기 펜 2  haptics 개발 참고 사항

이 페이지에서는 비즈니스용 Surface에디션 펜 2의 Windows 11 기능을 확장하려는 앱 개발자[를 위한 구현 참고를 제공합니다](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?). 사용자 지정 가능한  Haptics 기능에는 다음이 포함됩니다.

- **펜,** 연필 및 기타 쓰기 또는 그리기 도구의 느낌을 시뮬레이트하는 피드백을 제공합니다.
- **단추를** 마우스로 누르거나 단추를 클릭하거나 펜으로 작업을 완료하는 등의 사용자 작업에 직접 응답하는 조작 피드백입니다.

Surface에 연필 펜 2용 앱을 사용자 지정하는 경우 펜 조작 및 [haptic](/windows/apps/design/input/pen-haptics) 피드백에 설명된 Windows Ink 지침을 참조한 다음 아래 참고를 참조하세요.

## <a name="implementation-notes"></a>구현 참고 사항

표면 표면 처리 펜 2는 다음과 같은 Windows 11 지침에 따릅니다.

- **조작 파형입니다.** 조작 피드백 보내기 및 [중지" 섹션](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback)에 설명된 것 처럼, Inking 파형이 재생될 때 조작 파형을 보내면 해당 웨이브폼이 일시적으로 중단됩니다. 그러나 현재의 지우기 펜 2 구현에서는 조작 파형이 중지될 때 Inking 파형이 다시 시작되지 않을 수 있습니다. 따라서 필요한 경우 조작 피드백 후에도 웨이브폼을 다시 활성화해야 합니다. 조작 피드백이 완료될 때까지 기다릴 필요가 없습니다.
- **미지원 기능.** [Haptic feedback customizations( Haptic feedback customizations](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations)) 섹션에 설명된 다음과 같은 선택적 기능은 Surface의 펜 2: 재생 횟수 및 재생 일시 중지 간격에서 지원되지 않습니다. 이러한 사용법은 설명자에 나타나지만 현재 지원되지 않습니다. 따라서 IsPlayCountSupported, IsPlayDurationSupported, IsReplayPauseIntervalSupported 함수는 잘못된 값을 반환합니다.

## <a name="learn-more"></a>세부 정보

- [앱의 펜 Windows Ink 및 Windows 수 있습니다.](/windows/apps/design/input/pen-and-stylus-interactions)
- [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Surface 펜 기능 및 호환성](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)

