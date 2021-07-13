---
title: Surface Dock 2를 사용한 Wake On LAN
description: Surface Dock 2는 관리자가 원격으로 디바이스를 절전 모드로 해제하고 관리 작업을 자동으로 수행할 수 있도록 WOL(Wake on LAN)을 가장 잘 지원합니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643854"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>Surface Dock 2를 사용한 Wake On LAN

장치를 최신으로 유지하려면 IT 관리자가 사용하지 않을 때(일반적으로 야간 유지 관리 기간 동안) 장치를 관리할 수 있습니다. Surface Dock 2는 WOL(Wake on LAN)을 가장 잘 지원하여 관리자가 원격으로 디바이스를 절전 모드로 해제하고 장치 또는 기타 타사 솔루션을 사용하여 Microsoft Endpoint Manager 작업을 자동으로 수행할 수 있도록 합니다.

## <a name="requirements"></a>요구 사항

디바이스는 Surface Dock 2와 유선으로 연결되어 있어야 합니다. AC Power에 계속 연결되어 있어야 합니다.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a>지원되는 Surface 디바이스

- Surface Laptop 4(Intel 프로세서)
- Surface Laptop 4(AMD 프로세서)
- Surface Laptop 3(Intel 프로세서)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop 이동
- Surface Book 3

Surface Dock 2는 다음과 같은 전원 상태의 장치에 대해 WOL 지원을 제공합니다.

- 연결된 대기 상태
- 최대전력(S4 전원 상태)
- 종료(S5 "소프트오프" 전원 상태)

전원 상태에 대한 자세한 내용은 [시스템 전원 상태 를 참조합니다.](/windows/win32/power/system-power-states)

## <a name="how-it-works"></a>작동 방식

사용하지 않는 경우 Surface 장치는 최신 대기 상태 또는 연결된 대기 상태라고 하는 유휴 상태로 들어갈 수 있습니다. IT 관리자는 대상 Surface 디바이스의 MAC(미디어 액세스 제어) 주소가 포함된 절전 모드 해제 요청(매직 패킷)을 사용하여 디바이스를 원격으로 트리거할 수 있습니다. 앱 및 타사 Microsoft Endpoint Configuration Manager 같은 많은 관리 Microsoft Store WOL에 대한 기본 제공 지원을 제공합니다.

Surface Dock 2가 없는 장치에서 WOL을 사용하도록 설정하려면 Surface 디바이스용 [LAN에서 절전 모드 해제를 참조합니다.](wake-on-lan-for-surface-devices.md)

## <a name="learn-more"></a>자세히 알아보기

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Surface Configuration Manager에 대한 Wake On LAN](wake-on-lan-for-surface-devices.md)
- [시스템 전원 상태](/windows/win32/power/system-power-states)
- [LAN에서 절전 모드 해제 구성 - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
