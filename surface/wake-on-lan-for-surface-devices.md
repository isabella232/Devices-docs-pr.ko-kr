---
title: Surface Configuration Manager에 대한 Wake On LAN
description: Wake On LAN을 사용하여 원격으로 디바이스 절전 모드 해제를 통해 관리 작업을 자동으로 수행하는 방법을 참조합니다.
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613805"
---
# <a name="wake-on-lan-for-surface-devices"></a>Surface Configuration Manager에 대한 Wake On LAN

장치를 최신으로 유지하려면 IT 관리자가 사용하지 않을 때(일반적으로 야간 유지 관리 기간 동안) 장치를 관리할 수 있습니다. WOL(Wake on LAN)을 사용하면 관리자가 원격으로 디바이스를 절전 모드로 해제하고 자동 Microsoft Endpoint Manager 또는 타사 솔루션을 사용하여 관리 작업을 수행할 수 있습니다.

## <a name="requirements"></a>요구 사항

디바이스는 AC 전원에 연결되어 있어야하며 다음 호환 이더넷 어댑터 중 하나와 유선으로 연결되어 있어야 합니다.

- Surface USB 3.0 기가비트 이더넷 어댑터
- Surface Ethernet Adapter
- Surface USB-C에서 이더넷 및 USB 어댑터로
- Microsoft USB-C Travel Adapter Hub
- Surface 도크
- Surface Dock 2

> [!NOTE]
> Surface Dock 2는 추가 IT 구성 없이도 LAN에서 Wake on LAN을 가장 잘 지원할 수 있습니다. 자세한 내용은 [Surface Dock 2용 LAN 절전 모드 해제를 참조합니다.](wake-on-lan-surface-dock2.md)

## <a name="how-it-works"></a>작동 방식

사용하지 않는 경우 Surface 장치는 최신 대기 상태 또는 연결된 대기 상태라고 하는 유휴 상태로 들어갈 수 있습니다. IT 관리자는 대상 Surface 디바이스의 MAC(미디어 액세스 제어) 주소가 포함된 절전 모드 해제 요청(매직 패킷)을 사용하여 디바이스를 원격으로 트리거할 수 있습니다. 앱 및 타사 Microsoft Endpoint Configuration Manager 같은 많은 관리 Microsoft Store WOL에 대한 기본 제공 지원을 제공합니다. Endpoint Configuration Manager를 통해 디바이스를 깨우는 방법을 알아보는 자세한 내용은 [Configure Wake on LAN - Configuration Manager을 참조합니다.](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

LAN에서 절전 모드 해제 지원은 절전 상태, 연결된 대기 상태 또는 최대 절전 모드(S4 전원 상태)에 따라 다릅니다.

## <a name="connected-standby"></a>연결된 대기

기본적으로 연결된 Windows 10 Surface 디바이스에 대해 LAN 절전 모드 해제를 지원합니다.

### <a name="supported-surface-devices---connected-standby"></a>지원되는 Surface 장치 - 연결된 대기

- Surface Laptop 4(Intel 프로세서만 해당)
- Surface Laptop 3(Intel 프로세서만 해당)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop 이동
- Surface Book 3

## <a name="hibernation"></a>최대 최대화

최대 절전 모드를 해제하려면 Surface Enterprise Management [Mode(SEMM)를 통해](surface-enterprise-management-mode.md) UEFI 정책 설정을 사용하도록 설정해야 합니다(Surface Dock 2에 연결된 디바이스에는 필요하지 않습니다).

### <a name="supported-surface-devices---hibernation"></a>지원되는 Surface 장치 - 최대 사용

- Surface Laptop 4(Intel 프로세서만 해당)
- Surface Laptop 3(Intel 프로세서만 해당)
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 이동
- Surface Book 3

### <a name="to-enable-wake-on-lan-uefi-setting"></a>LAN UEFI에서 절전 모드 해제 설정을 사용하도록 설정하려면

LAN UEFI 절전 모드 해제 설정을 사용하도록 설정하려면 대상 장치를 SEMM에 등록하고 구성 패키지를 만든 다음 장치에 패키지를 적용해야 합니다. 자세한 내용은 다음을 참고하십시오.

- [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
- [SEMM을 사용하여 Surface 장치 등록 및 구성](enroll-and-configure-surface-devices-with-semm.md)

1. [**Surface UEFI 구성기 를 다운로드하여 설치합니다.**](https://www.microsoft.com/download/details.aspx?id=46703)
2. 구성 **패키지**  >  **만들기**+  >  **인증서**보호  > **시작을 선택합니다.**
3. 고급 **설정으로 이동하고** **LAN의 절전 모드 해제를 으로** **전환합니다.**
4. 대상 장치에 패키지를 적용합니다.

    > [!div class="mx-imgBorder"]
    > ![LAN UEFI에서 절전 모드 해제 정책 설정 사용](images/wol-uefi.png)

## <a name="learn-more"></a>자세히 알아보기

- [Surface Dock 2용 LAN 절전 모드 해제](wake-on-lan-surface-dock2.md)
- [Microsoft Surface USB-C에서 이더넷 및 USB 어댑터로](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Surface USB 3.0 기가비트 이더넷 어댑터](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
