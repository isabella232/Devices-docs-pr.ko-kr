---
title: 서피스 도크의 새로운 기능
description: 이 문서에서는 차세대 서피스 도크에 대 한 새로운 기능과 기능을 중점적으로 설명 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: e96242ab9cef127238bda3ee3ea797c943479798
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114686"
---
# 서피스 도크의 새로운 기능 

서피스 도크 2, 차세대 서피스 도크는 사용자가 외부 모니터와 여러 주변 기기를 연결 하 여 Surface device에서 완전히 현대적인 데스크톱 환경을 얻을 수 있도록 합니다. Office, 유연한 작업 영역 또는 가정에서 효율성을 최대화 하기 위해 기본으로 제공 되는 Surface Dock 2는 전면 USB 2 포트를 포함 하는 7 개의 포트와 전화 및 액세서리에 대 한 빠른 충전 전력의 15 와트를 갖추고 있습니다. 

### 전체 장치 관리 지원

Surface Dock 2는 IT 관리를 단순화 하 여 관리자가 Windows Update를 사용 하 여 펌웨어 업데이트를 자동화 하 고 내부 소프트웨어 배포 도구를 통해 업데이트를 중앙 집중화할 수 있도록 설계 되었습니다.

- Surface 엔터프라이즈 관리 모드 (SEMM)는 IT 관리자가 Surface Dock 2의 포트를 보호할 수 있도록 합니다. 자세한 내용은 [Surface Enterprise 관리 모드를 사용 하는 보안 Surface Dock 2 포트](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)를 참조 하세요.
-  WMI (Windows Management Instrumentation) 지원을 통해 IT 관리자는 Surface Dock 2 장치에서 최신 펌웨어, 정책 상태 및 관련 데이터를 원격으로 모니터링 하 고 관리할 수 있습니다. 자세한 내용은 [WMI를 사용 하 여 Surface Dock 2 관리](surface-dock2-wmi.md)를 참조 하세요.

## 일반 시스템 요구 사항

- Windows 10 버전 1809. Windows 7, Windows 8 또는 비 Surface host 장치는 지원 되지 않습니다. 서피스 도크 2는 다음 Surface 장치에서 작동 합니다.

  - Surface Pro (다섯째 Gen)
  - Surface 노트북 (첫번째 Gen)
  - Surface Pro 6
  - Surface Book 2
  - Surface Laptop 2
  - Surface Go
  - Surface Pro 7
  - Surface Pro X 
  - Surface 노트북 3
  - Surface Book 3
  - Surface Go 2
  - Surface 랩톱 이동

## 서피스 도크 2 구성 요소

![서피스 도크 2 구성 요소](./images/surface-dock2.png)
 
### USB

- 전면 USB-C 포트 2 개.
- 2 개의 후면 USB-C (gen 2) 포트.
- 후면 전면 USB-A 포트. 

### 비디오
    
- 듀얼 4K@60hz. 다음 장치에서 최대 2 개의 디스플레이를 지원 합니다.

  - Surface Book 3
  - Surface Go 2
  - Surface Pro 7
  - Surface Pro X
  - Surface 노트북 3

- 듀얼 4K@ 4K@30Hz. 다음 장치에서 최대 2 개의 디스플레이를 지원 합니다.

  - Surface Pro 6
  - Surface Pro (다섯째 Gen)
  - Surface Laptop 2
  - Surface 노트북 (첫번째 Gen)
  - Surface Go
  - Surface Book 2.

### Ethernet

- 1 기가 비트 이더넷 포트. 

### 외부 전원 공급 장치

- 100V-240V를 지 원하는 199 와트.


## 서피스 도크 비교 

**표 1. Surface Dock 및 USB-C 이동 허브**


| 구성 요소                           | Surface 도크                                                | 서피스 도크 2                                                                                      | USB-C 이동 허브 |
| ----------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ---------------- |
| Surflink                            | 예                                                         | 예                                                                                                 | 아니오               |
| USB-A                               | 전면 USB 3.1 Gen 1<br>2 후면 전면 USB 3.1 Gen 1 | 2 후면 전면 USB 3.2 Gen 2 (7.5 W 전원)                                                            | 1 USB 3.1 Gen 2  |
| 미니 디스플레이 포트                   | 2 후면 방향 (DP 1.2)                                       | 없음                                                                                                | 없음             |
| USB-C                               | 없음                                                        | 전면 USB 3.2 Gen 2 2<br>(15W 전원)<br>2 후면 전면 USB 3.2 Gen 2 (DP 1.4 a)<br>(7.5 w 전원) | 1 USB 3.2 Gen 2  |
| 3.5 mm 오디오/출력                 | 예                                                         | 예                                                                                                 | 예              |
| Ethernet                            | 예, 1 기가 비트                                              | 예 1 기가 비트                                                                                       | 예, 1 기가 비트   |
| DC 전원 켜 짐                         | 예                                                         | 예                                                                                                 |                  |
| Kensington 잠금                     | 예                                                         | 예                                                                                                 |                  |
| Surflink 케이블 길이               | 65cm                                                        | 80cm                                                                                                | 20cm             |
| Surflink 호스트 파워                 | 60W                                                         | 120W                                                                                                | 해당 없음              |
| USB 로드 전원                      | 30W                                                         | 60W                                                                                                 |                  |
| USB 비트 전송률                        | 5gbps                                                      | 10gbps                                                                                             | 10gbps          |
| 모니터 지원                     | 2 x 4k @30fps 또는<br>1 x 4k @ 60fps                         | 2 x 4K @ 60fps                                                                                      | 1 x 4K @ 60fps   |
| 연결 대기 1에서 Wake on wake-on-lan <sup></sup> | 예                                                         | 예                                                                                                 |                  |
| S4/S5 절전 모드에서 Wake on wake-on-lan  | 아니오                                                          | 예                                                                                                 |          예        |
| 네트워크 PXE 부팅                    | 예                                                         | 예                                                                                                 |        예          |
| SEMM 호스트 액세스 제어            | 아니오                                                          | 예                                                                                                 | 아니오               |
| SEMM 포트 액세스 제어 <sup> 2</sup>          | 아니오                                                          | 예                                                                                                 | 아니오               |
| 서비스 지원                   | MSI                                                         | Windows 업데이트 또는 MSI                                                                               |                  |

 



1. *장치는 Surface Enterprise 관리 모드 (SEMM) 또는 장치 펌웨어 제어 인터페이스 (DFCI)를 통해 절전 모드 해제 또는 Power-Off 상태에서 종료 되도록 구성 해야 합니다. 최대 절전 모드 또는 Power-Off는 Surface Pro 7, Surface 랩탑 3, Surface Pro X, Surface Book 3에서 지원 됩니다.  일부 기능에는 소프트웨어 라이선스가 필요 합니다. 별도로 판매.*

2. *일부 기능에는 소프트웨어 라이선스가 필요 합니다. 별도로 판매.*

## 능률적인 장치 관리

Surface에서 Windows Update를 통해 능률적인 관리 기능을 해제 하 고 IT 관리자가 다음 엔터프라이즈 등급 기능을 활용할 수 있도록 합니다.

- **Frictionless** Windows Update 또는 Microsoft 끝점 구성 관리자, (이전의 System Center Configuration Manager-SCCM) 또는 기타 MSI 배포 도구를 사용 하 여 자동으로 항구를 업데이트 합니다. 
- **네트워크에서 깨우기**. 디바이스를 전원이 켜진 상태로 유지 하도록 사용자에 게 알리지 않고 회사 장치를 관리 하 고 액세스 합니다. 도킹 된 장치가 절전 모드, 절전 모드 또는 전원 끄기 모드일 때도 끝점 구성 관리자 또는 기타 엔터프라이즈 관리 도구를 사용 하 여 서비스 및 관리를 위해 네트워크에서 절전 모드를 해제할 수 있습니다.
- **중앙 집중화 된 IT 제어**. 포트를 켜고 끄려면 Surface Dock 2에 연결할 수 있는 사용자를 제어 합니다. Surface Dock 2에서 사용할 수 있는 호스트 장치를 제한 합니다. 단일 사용자에 대 한 dock 액세스를 제한 하거나, 팀의 특정 사용자 또는 전체 회사에서 액세스할 수 있도록 도크를 구성 합니다.

## 다음 단계

- [Surface Enterprise 관리 모드를 사용 하는 보안 Surface Dock 2 포트](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)
- [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
- [Surface 장치의 모범 사례 전원 설정](maintain-optimal-power-settings-on-Surface-devices.md)
