---
title: 기존 무선 네트워크 또는 LAN의 Miracast
description: Windows 10에서는 로컬 네트워크를 통해 Miracast 스트림을 보낼 수 있습니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b99c1010e6caedabeb72cc7b99df88aaa7c9cdcb
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497508"
---
# <a name="miracast-over-infrastructure"></a>인프라를 통해 Miracast

Windows 10 버전 1703부터 Microsoft는 직접 무선 링크가 아닌 로컬 네트워크를 통해 Miracast 스트림을 보내는 기능을 확장했습니다. 이 기능은 [인프라 연결 설정 프로토콜을 통한 Miracast(MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)를 기반으로 합니다.

인프라를 통한 Miracast는 다양한 혜택을 제공합니다.

- Windows는 비디오 스트림을 전송할 때 자동으로 이 경로가 적용 가능한지 검색합니다.
- Windows는 연결이 이더넷 또는 보안 Wi-Fi 네트워크를 통한 경우에만 이 경로를 선택합니다.
- 사용자가 Miracast 수신기에 연결하는 방법을 변경할 필요가 없습니다. 표준 Miracast 연결과 동일한 UX를 사용합니다.
- 현재 무선 드라이버 또는 PC의 하드웨어에 변경이 필요하지 않습니다.
- Wi-Fi Direct를 통한 Miracast에 최적화되지 않은 오래된 무선 하드웨어에도 잘 작동합니다.
- 기존 연결을 활용하여 연결 시간을 줄이며 매우 안정적인 스트림을 제공합니다.


## <a name="how-it-works"></a>작동 방식

사용자는 이전과 마찬가지로 Wi-Fi 어댑터를 통해 Miracast 수신기에 연결하려고 합니다. Miracast 수신기 목록이 채워지면 Windows 10에서 해당 수신기가 인프라에 대한 연결을 지원할 수 있는지 식별합니다. 사용자가 Miracast 수신기를 선택하면 Windows 10은 표준 DNS 및 멀티캐스트 DNS(mDNS)를 통해 장치의 호스트 이름을 확인하려고 합니다. DNS 방법 중 하나를 통해 이름을 분해할 수 없는 경우 Windows 10은 표준 Wi-Fi Direct 연결을 사용하여 Miracast 세션을 구축합니다.

> [!NOTE]
> 연결 협상 순서에 대한 자세한 내용은 [MS-MICE(인프라 연결 설정 프로토콜)를 통해 Miracast](https://msdn.microsoft.com/library/mt796768.aspx) 참조하세요.




## <a name="enabling-miracast-over-infrastructure"></a>인프라에 대해 Miracast 사용 

Windows 10 버전 1703로 업데이트된 Surface Hub 또는 다른 Windows 10 디바이스가 있으면 자동으로 이 새로운 기능을 사용할 수 있습니다. 귀하의 환경에서 이를 활용하려면 배포 시 다음에 해당하는지 확인해야 합니다.

- Surface Hub 또는 디바이스(Windows PC 또는 휴대폰)에서 Windows 10 버전 1703을 실행해야 합니다.
- TCP 포트 열기: **7250**
- Surface Hub 또는 Windows PC가 인프라를 통한 Miracast *수신기* 역할을 할 수 있어야 합니다. Windows PC 또는 휴대폰이 인프라를 통한 Miracast *소스* 역할을 할 수 있어야 합니다.
    - Miracast 수신기로서 Surface Hub 또는 장치는 이더넷 또는 보안 Wi-Fi 연결을 통해(예 WPA2-PSK 또는 WPA2-Enterprise 보안 사용) 회사 네트워크에 연결되어 있어야 합니다. Surface Hub 또는 디바이스가 열린 Wi-Fi 연결에 연결된 경우 인프라를 통해 Miracast 자체 비활성화됩니다.
    - Miracast 소스로서 Windows PC 또는 휴대폰은 이더넷 또는 보안 Wi-Fi 연결을 통해 동일한 엔터프라이즈 네트워크에 연결되어 있어야 합니다.
- Surface Hub 또는 디바이스의 DNS 호스트 이름(디바이스 이름)은 DNS 서버를 통해 확인할 수 있어야 합니다. Surface Hub가 동적 DNS를 통해 자동으로 등록하도록 하거나 수동으로 Surface Hub의 호스트 이름에 대한 A 또는 AAAA 레코드를 만들어 검색할 수 있습니다. 
- Windows 10 PC는 이더넷 또는 보안 Wi-Fi 연결을 통해 동일한 엔터프라이즈 네트워크에 연결되어 있어야 합니다. 


인프라를 통한 Miracast는 표준 Miracast를 대체하지 않습니다. 대신, 이 기능은 보완적이며 엔터프라이즈 네트워크의 일부인 사용자에게 혜택을 제공합니다. 특정 위치의 게스트이며 엔터프라이즈 네트워크에 액세스할 수 없 사용자는 Wi-Fi Direct 연결 방법을 사용하여 계속 연결할 수 있습니다.

[SurfaceHub 구성 서비스 공급자(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp)의 **InBoxApps/WirelessProjection/PinRequired** 설정은 인프라를 통한 Miracast에 필요하지 않습니다. 인프라를 통한 Miracast는 두 디바이스가 같은 엔터프라이즈 네트워크에 연결된 경우에만 작동하기 때문입니다. 이렇게 하면 이전에 Miracast에서 누락된 보안 제한을 제거합니다. 인프라 연결이 작동하지 않는 경우 Miracast가 일반 Miracast로 돌아가므로 이 설정을 계속 사용하는 것이 좋습니다(이전에 이를 사용한 경우). 

## <a name="faq"></a>FAQ
**인프라를 통해 Miracast 사용하기 위해 여전히 Wi-Fi 필요한 이유는 무엇인가요?**<br>
Miracast 수신기를 식별하는 검색 요청은 Wi-Fi 어댑터를 통해서만 발생할 수 있습니다. 수신기가 식별되면 Windows 10 네트워크에 대한 연결을 시도할 수 있습니다.
