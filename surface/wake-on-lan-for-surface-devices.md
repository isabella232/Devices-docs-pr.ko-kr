---
title: Surface Configuration Manager에 대한 Wake On LAN
description: Windows 10 버전 1607 이상을 실행하고 Surface Ethernet 어댑터를 사용하여 유선 네트워크에 연결하는 Surface 디바이스는 최신 대기 모드의 WOL(Wake On LAN)을 사용할 수 있습니다.
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
ms.date: 11/30/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: f0d2215fae1ce8aa5cdc6d55fb36158d6a95af4d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448288"
---
# <a name="wake-on-lan-for-surface-devices"></a>Surface Configuration Manager에 대한 Wake On LAN 

Windows 10 버전 1607 이상을 실행하는 Surface 디바이스는 최신 대기 모드(연결된 대기 모드라고도 알려지음)에서 WOL(Wake On LAN)을 사용할 수 있습니다. WOL을 사용하여 IT 관리자는 원격으로 디바이스를 절전 모드로 해제하고 장치 또는 타사 솔루션을 사용하여 Microsoft Endpoint Manager 작업을 자동으로 수행할 수 있습니다.

>[!NOTE]
>WOL을 지원하려면 Surface 디바이스를 AC 전원에 연결하고 유선 네트워크에 연결된 Surface Ethernet 어댑터를 사용해야 합니다.

## <a name="supported-devices"></a>지원되는 디바이스

WOL을 지원하는 이더넷 어댑터:

- Microsoft USB-C 여행 허브
- Surface Ethernet 어댑터
- Surface USB-C에서 이더넷 및 USB 3.0 어댑터로
- Surface USB 3.0 기가비트 이더넷 어댑터 
- Surface DockDocking 스테이션(Surface Pro 3) 
- Surface Dock 2
- Surface 3용 도킹 스테이션
- Surface Pro 3용 도킹 스테이션 

WOL을 지원하는 Surface 디바이스:

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro(5세대)
- Surface Pro(5세대) LTE Advanced
- Surface Pro 6
- Surface Pro 7
- Surface Pro 7+
- Surface Pro 8
- Surface Book(모든 세대)
- Surface Go(모든 세대)
- Surface Laptop(모든 세대)
- Surface Laptop Go
- Surface Laptop SE
- Surface Laptop 스튜디오
- Surface Studio 2(Surface Studio 지침 참조)


## <a name="using-wol"></a>WOL 사용 

사용하지 않는 경우 Surface 장치는 최신 대기 상태 또는 연결된 대기 상태라고 하는 저전력 상태로 들어갈 수 있습니다. IT 관리자는 대상 Surface 디바이스의 MAC(미디어 액세스 제어) 주소가 포함된 절전 모드 해제 요청(매직 패킷)을 사용하여 디바이스를 원격으로 트리거할 수 있습니다. NIC(대상 네트워크 인터페이스 카드)는 장치를 깨기 전에 MAC 주소를 자체와 비교합니다. 매직 패킷 절전 모드 해제 요청의 MAC 주소가 대상 NIC의 MAC 주소와 일치하지 않는 경우 NIC는 디바이스를 깨우지 않습니다. 자세한 내용은 [절전 모드 해제 소스 설명서를 참조하세요.](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## <a name="modern-standby"></a>최신 대기

최신 대기는 사용자가 시스템이 절전으로 들어가게 되거나 사용자가 설정한 전원 설정에 따라 Windows 절전이 됩니다. 예를 들어 사용자가 전원 단추를 누르거나  LID를 닫거나 전원 단추에서 절전을 Windows 시작 메뉴. WOL은 기본적으로 버전 1607 이상을 실행하는 최신 대기 Windows 10 Surface 디바이스에서 작동합니다. 추가 IT 구성은 필요하지 않습니다(Surface Studio 제외).

## <a name="surface-studio-2-instructions"></a>Surface Studio 2개 지침

Surface Studio 2에서 WOL을 사용하도록 설정하려면 다음 절차를 따라야 합니다.

1. 레지스트리 편집기(**StartSearch** > **** > regedit.exe)를** 열**고 다음 레지스트리 키를 생성합니다.

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. 다음 명령을 실행합니다.

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> Windows 10 2에서 Windows 10 Surface Studio 버전을 업그레이드하는 경우(예: Windows 10 20H2에서 21H1로 업그레이드) WOL을 사용하도록 설정하려면 다음 지침을 다시 따라야 합니다.


### <a name="to-wake-from-hibernation-s4-or-shutdown-s5"></a>최대 절전 모드(S4) 또는 종료(S5)에서 절전 모드 해제 

- Surface Dock 2에 연결된 장치의 경우 [Surface Dock 2용 LAN 절전 모드 해제를 참조합니다.](wake-on-lan-surface-dock2.md)
