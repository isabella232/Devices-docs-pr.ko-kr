---
title: Surface Hub에서 Miracast 문제 해결
description: Surface Hub에서 Miracast 문제를 해결하는 방법을 알아보세요.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 96c7c42fe0176f275a8657165d88bf447e57772b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836949"
---
# Surface Hub에서 Miracast 문제 해결

Surface Hub는 Miracast 프로토콜을 통해 무선 프로젝션을 지원합니다. 현재 사용할 수 있는 무선 모니터 및 어댑터는 Miracast의 기본 구현을 사용합니다. Surface Hub는 **Miracast 자율 그룹 소유자(AGO)** 라고 불리는 Miracast의 약간 다른 버전을 사용합니다. Surface Hub에 무선으로 프로젝팅하는 데 실패했을 때 일반적인 문제 해결 단계는 다른 무선 모니터 또는 어댑터에 프로젝팅을 테스트 하는 것입니다. 그러나 대부분의 경우 이러한 디바이스는 Miracast AGO를 사용하지 않으며 무선 프로젝션을 Surface Hub와 같은 방식으로 처리하지 않습니다.

기존의 Miracast에서 프로젝팅 디바이스는 Miracast 사용 모니터를 통해 액세스 지점 설정에 연결되고 모니터는 프로젝팅 디바이스의 네트워크 채널을 사용하여 트래픽을 다시 프로젝팅 디바이스에 프로젝팅합니다. Miracast AGO는 2 단계 연결 프로세스입니다.

- 첫 번째 단계는 2.4GHz를 사용하는 초기 연결입니다. 
- 해당 초기 핸드셰이크 이후 프로젝팅 장치는 모니터의 무선 채널 설정을 사용하여 모니터에 트래픽을 보냅니다. Surface Hub가 액세스 지점인 Wi-Fi 네트워크에 연결된 경우 연결된 네트워크와 같은 채널을 사용하며 그렇지 않은 경우 설정에서 Miracast 채널을 사용합니다.

Surface Hub에서 Miracast 관련 문제는 일반적으로 [연결](#connect-issues) 및 [성능](#performance-issues)의 두 가지 유형의 문제가 있습니다. 두 경우 모두 Surface Hub 위치에 무선 네트워크 활동에 대 한 일반적인 그림을 가져오는 것이 좋습니다. 네트워크 검색 도구를 실행하여 환경에서 사용 가능한 네트워크 및 채널 사용을 표시할 수 있습니다.

## 연결 문제

Wi Fi 및 Miracast 모두 Surface Hub의 설정에서 활성화되어 있는지 확인합니다. 

네트워크 검사를 실행한 경우 Surface Hub Miracast가 액세스 지점으로 나열됩니다. Surface Hub의 Miracast 네트워크가 스캔에 표시 되지만 사용 가능한 장치로 표시 되지 않는 경우 Surface Hub에서 사용 하는 Miracast 채널을 조정할 수 있습니다. 

Surface Hub가 Wi-Fi 네트워크에 연결되면 해당 Miracast 액세스 포인트에 대해 Wi-Fi 액세스 지점과 동일한 채널 설정을 사용합니다. 문제 해결을 위해 모든 Wi-Fi 네트워크와 Surface Hub의 연결을 끊어(Wi-Fi는 그대로 사용하도록 둠) Miracast에 사용되는 채널을 제어할 수 있습니다. 설정에서 수동으로 Miracast 채널을 선택할 수 있습니다. 각 변경 후에 Surface Hub를 다시 시작해야 합니다. 일반적으로 네트워크 검사에서 사용량이 많은 것으로 표시되지 않는 채널을 사용하고자 할 것입니다.

연결 문제는 연결하는 장치에서 문제가 발생했기 때문일 수도 있습니다. 프로젝팅 디바이스에서 Windows를 실행 중인 경우 전체 Miracast 지원을 위해 Windows 8.1 이상이어야 합니다. 다시 말하자면 문제 해결을 위해 모든 Wi-Fi 네트워크에서 프로젝팅 장치를 분리합니다. 이렇게 하면 Surface Hub의 액세스 지점 채널과 Miracast 채널 사이의 모든 채널 전환이 제거됩니다. 또한 일부 그룹 정책 및 방화벽 설정이 Wi-Fi 네트워크에 연결될 수 있습니다.

### 드라이버 확인

프로젝팅 디바이스에 최신 드라이버 및 업데이트가 설치되었는지 확인하는 것 또한 좋은 생각입니다. 장치 관리자에서 Wi-Fi 어댑터와 비디오 어댑터를 열어 업데이트된 드라이버 버전을 확인합니다. 이전 Wi-Fi 드라이버의 경우 Surface Pro 3 및 Surface Pro 4에 대해 [핫픽스 3120232](https://support.microsoft.com/help/3120232/poor-wireless-performance-on-5-ghz-connections-on-surface-pro-3-and-surface-3)가 적극 권장됩니다. 

### Miracast 지원 확인

그런 다음 디바이스에서 Miracast를 사용할 수 있는지 확인합니다. 

1. Windows 키+R을 누르고 `dxdiag`를 입력합니다. 
2. "모든 정보 저장"을 클릭 합니다. 
3. 저장된 dxdiag.txt를 열고 **Miracast**를 찾습니다. **사용 가능(HDCP)** 이 나타나야 합니다. 
    
### 방화벽 확인
    
Windows 방화벽은 Miracast 트래픽을 차단할 수 있습니다. 가장 단순한 테스트 방법은 방화벽을 해제하고 프로젝션을 테스트하는 것입니다. 방화벽이 해제된 상태에서 Miracast가 작동하는 경우 다음에 대해 예외를 추가합니다.

    C:\Windows\System32\WUDFHost.exe
    Allow In/Out connections for TCP and UDP, Ports: All.

### 그룹 정책 설정 확인

도메인 가입 장치에서는 그룹 정책이 Miracast를 차단할 수도 있습니다. 

1. Windows 키 + R을 누른 다음 `rsop.msc`를 입력하여 **정책 결과 집합** 스냅인을 실행합니다. 이 PC에 적용된 최신 정책이 표시됩니다. 
2. **컴퓨터 구성** > **Windows 설정** > **보안 설정** > **무선 네트워크(IEEE 802.11) 정책**을 검토합니다. 무선 정책에 대한 설정이 포함됩니다. 
3. 무선 정책에 대한 설정을 두 번 클릭하면 대화 상자가 나타납니다. 
4. **네트워크 사용 권한** 탭을 열고 **모든 사용자에게 모든 사용자 프로필 만들기 허용**을 선택합니다.

### 이벤트 로그 확인

마지막으로 확인할 사항은 이벤트 로그입니다. Miracast 이벤트는 **Wlanautoconfig**에 기록됩니다. 이는 Surface Hub와 프로젝팅 디바이스에서 동일합니다. Surface Hub 로그를 내보내는 경우 Surface Hub의 Wlanautoconfig을 **WindowsEventLog** 폴더에서 볼 수 있습니다. 이벤트 로그의 오류는 연결이 실패한 위치에 대한 몇 가지 추가 세부 정보를 제공할 수 있습니다.

## 성능 문제

무선 프로젝션이 연결된 후에 성능 문제가 대기 시간을 야기할 수 있습니다. 이는 일반적으로 전반적인 채널 포화 또는 채널 전환을 야기하는 상황 때문입니다. 

채널 포화의 경우 네트워크 스캔을 참조하여 적은 트래픽으로 채널을 사용해 보세요.

채널 전환은 Wi-Fi 어댑터가 여러 채널에 트래픽을 전송해야 할 때 발생합니다. 특정 채널은 동적 주파수 선택(DFS)을 지원합니다. DFS는 49에서 148 채널에서 사용됩니다. 일부 Wi-Fi 드라이버는 DFS 채널에 연결될 때 성능이 저하됩니다. DFS 채널에 연결되었을 때 Miracast 성능이 저하된 경우 DFS 이외의 채널에서 프로젝션을 시도합니다. Surface Hub와 프로젝팅 장치 모두 DFS 이외의 채널을 사용해야 합니다.

Surface Hub와 프로젝팅 디바이스가 모두 Wi-Fi에 연결되어 있지만 다양한 채널의 서로 다른 액세스 지점을 사용하는 경우 Miracast가 연결되어 있는 동안 채널에 대한 Surface Hub와 프로젝팅 장치의 채널이 전환됩니다. 이로 인해 Wi-Fi 사용 시 무선 프로젝트 및 네트워크 성능이 저하됩니다. 채널 전환은 무선 프로젝션만이 아니라 모든 무선 트래픽의 성능에 영향을 미칩니다. 

프로젝팅 디바이스가 Miracast에 대해 Surface Hub에서 사용하는 것과 다른 채널을 사용하여 Wi-Fi 네트워크에 연결된 경우에도 채널 전환이 발생합니다. 따라서 가장 좋은 방법은 Surface Hub의 Miracast 채널을 가장 일반적으로 사용 되는 액세스 지점과 동일한 채널로 설정 하는 것입니다. 

환경에 여러 개의 Wi-Fi 네트워크 또는 액세스 지점이 있는 경우 일부 채널 전환은 불가피합니다. 모든 Wi-Fi 드라이버를 최신 상태로 유지하는 것이 이를 해결하는 가장 좋은 방법입니다.

## 고객 지원 문의

질문이 있거나 도움이 필요한 경우 [지원 요청을 만들](https://support.microsoft.com/supportforbusiness/productselection)수 있습니다.
