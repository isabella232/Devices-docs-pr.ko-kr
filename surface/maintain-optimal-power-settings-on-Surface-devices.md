---
title: Surface 장치의 모범 사례 전원 설정
description: 이 항목에서는 최적의 전원 설정을 유지 관리하기 위한 모범 사례 권장 사항을 설명하고 Surface에서 전원 관리 환경을 간소화하는 방법을 설명합니다. 이 문서는 Surface Pro 7+, Surface Pro 7, Surface Pro X 및 Surface Laptop 3을 포함하여 현재 지원되는 모든 Surface 디바이스에 적용됩니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 54aff228e8a72d413fc53bd14fe15d8ad7b15ab0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271402"
---
# Surface 장치의 모범 사례 전원 설정

Surface 디바이스는 모바일 장치 에너지 소비의 최신 발전을 활용하여 워크로드에 최적화된 간소화된 환경을 제공하도록 디자인되었습니다. 수행하는 작업에 따라 Surface는 전원이 개별 하드웨어 구성 요소로 흐르는 방법을 동적으로 미세하게 설정하고, 들어오는 전자 메일 또는 네트워크 트래픽과 같은 백그라운드 작업을 처리하기 위해 시스템 구성 요소를 잠시 깨우고 저전력 유휴 상태(S0ix)로 돌아올 수 있습니다.

## IT 관리자를 위한 권장 사항 요약

조직 전체에서 Surface 디바이스가 Surface 전원 최적화 기능을 완전히 사용할 수 있도록 보장하기 위해 다음을 수행할 수 있습니다.

-  Windows 업데이트 또는 Surface 드라이버 및 펌웨어 MSI에서 최신 드라이버 및 펌웨어를 설치합니다. 이렇게 하면 균형이 잡힌 전원 계획(전원 프로필)이 기본적으로 만들어지며 최적의 전원 설정이 구성됩니다.  자세한 내용은 Surface 드라이버 및 펌웨어 업데이트 [관리 및 배포를 참조하세요.](manage-surface-driver-and-firmware-updates.md)
- 사용자 지정 전원 프로필을 만들거나 기본 UI(시스템 전원**** 또는 절전 모드)에 표시되지 않는 고급  >  **전원 & 않습니다.**
- 네트워크에서 디바이스의 전원 프로필을 관리해야 하는 경우(예: 고도로 관리되는 조직에서) powercfg 명령 도구를 사용하여 Surface 디바이스의 출하 시 이미지에서 전원 계획을 내보운 다음 Surface 디바이스의 프로비저닝 패키지로 가져올 수 있습니다. 

    >[!NOTE]
    >동일한 유형의 Surface 디바이스에서만 전원 계획을 내보낼 수 있습니다.  예를 들어 Surface 노트북에서 전원 계획을 내보낼 수 없습니다. Surface Pro에서 가져올 수 없습니다.  자세한 내용은 전원 설정 [구성을 참조하십시오.](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)

- 기존 전원 관리 정책 설정에서 Surface 디바이스를 제외합니다. 

## Background

Surface에서 전원 관리를 구현하는 방식은 일련의 절전 상태 동안 점차적으로 전원을 줄이면서 꺼지는 이전 OS 표준과 크게 다릅니다. 예를 들어 S1, S2, S3 등에서 순환합니다.

대신 Surface는 레거시 절전 모드 및 에너지 소비 기능을 최신 대기 기능 및 동적 미세 조정으로 대체하는 사용자 지정 전원 프로필로 이미지가 작성되었습니다. 이 사용자 지정 전원 프로필은 Surface Serial Hub 드라이버 및 SAM(시스템 집계 모듈)을 통해 구현됩니다. SAM 칩은 알고리즘을 사용하여 최적의 전원 요구 사항을 계산하는 Surface 디바이스 전원 정책 소유자로 기능합니다. Windows 전원 관리자와 함께 작동하여 하드웨어 구성 요소가 작동하는 데 필요한 정확한 양의 전원만 할당하거나 스로틀합니다. 이 문서는 Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X 및 Surface Laptop 3을 포함하여 현재 지원되는 모든 Surface 디바이스에 적용됩니다.

## Surface에서 사용자 지정 전원 프로필 활용

Surface 디바이스의 전원 옵션으로 이동하면 사용 가능한 하나의 전원 플랜이 있는 것입니다. 사용자 지정 전원 프로필입니다. 고급 전원 설정으로 이동하면 Windows 10을 실행하는 일반 PC에 비해 훨씬 더 작은 전원 옵션 하위 집합이 표시됩니다. 일반 디바이스와 달리 Surface에는 이러한 전원 옵션을 관리하는 펌웨어 및 사용자 지정 구성 요소가 있습니다.


## 최신 대기

알고리즘에 포함된 사용자 지정 전원 프로필을 사용하면 일반적인 스마트폰의 인스턴트 설정/인스턴트 해제 기능에 대해 낮은 전원 상태를 유지 관리하여 Surface에 대한 최신 대기 상태를 사용할 수 있습니다. DRIPS(심층 런타임 유휴 플랫폼 상태)라고도 하는 S0ix는 Surface 디바이스의 기본 전원 모드입니다. 최신 대기 모드에는 두 가지 모드가 있습니다.

- **연결된 대기입니다.** 전자 메일, 메시징 및 클라우드 동기화 데이터를 최신으로 배달하는 기본 모드인 연결된 대기 상태는 계속 Wi-Fi 네트워크 연결을 유지합니다.

- **연결이 끊어진 대기 중입니다.** 배터리 사용 시간을 연장하기 위한 선택적 모드, 연결이 끊긴 대기 상태는 Wi-Fi, 네트워크 연결 및 관련 네트워크 연결을 해제하여 동일한 즉각적인 Bluetooth 환경을 제공하고 전원을 절약합니다.

최신 대기에 대한 자세한 내용은 Microsoft 하드웨어 개발자 센터를 [참조합니다.](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## Surface에서 전원 관리 환경을 간소화하는 방법 

Surface는 사용자가 전원 관리 환경을 최적화할 수 있도록 설계된 다음 기능을 통합합니다.

- [단수 전원 계획](#singular-power-plan)

- [간소화된 전원 설정 사용자 인터페이스](#simplified-power-settings-user-interface)

- [Windows 성능 전원 슬라이더](#windows-performance-power-slider)

### 단수 전원 계획

Surface는 사용자 지정 전원 계획을 만들거나 전원 설정을 수동으로 구성할 필요가 없어 간소화된 전원 관리 환경을 위해 디자인됩니다. Microsoft는 표준 Windows 빌드의 여러 전원 계획을 대체하는 단일 전원 계획(균형 조정)을 제공하여 사용자 환경을 간소화합니다.

### 간소화된 전원 설정 사용자 인터페이스

Surface는 모범 사례 전원 설정 권장 사항과 어코드된 간소화된 UI를 제공합니다. 일반적으로 기본 사용자 인터페이스에 표시되는 설정만 조정하고 고급 전원 설정 또는 그룹 정책 설정을 구성하지 않는 것이 좋습니다. 최대 밝기 수준을 피하면서 기본 화면 및 절전 시간 제한을 사용하는 것이 사용자가 배터리 사용 시간을 연장하는 가장 효과적인 방법입니다.

![그림 1. 절전 & 간소화](images/powerintrofig1.png)

그림 1. 전원 및 절전 설정 간소화

### Windows 성능 전원 슬라이더

Windows 10 빌드 1709 이상을 실행하는 Surface 디바이스에는 필요한 경우 배터리 사용의 우선 순위를 지정하거나 원할 경우 성능을 선호할 수 있는 전원 슬라이더가 포함되어 있습니다. 배터리 아이콘을 클릭하여 작업 표시줄에서 전원 슬라이더에 액세스할 수 있습니다. 배터리 사용 시간이 길어지거나(배터리 절약 모드) 성능을 향상하기 위해 왼쪽으로 미끄러지거나 오른쪽으로 밀어 갑니다.

![그림 2. 전원 슬라이더](images/powerintrofig2a.png)

그림 2. 전원 슬라이더

전원 슬라이더는 다음 표에 설명된 네 가지 상태의 사용이 가능하게 합니다.

| 슬라이더 모드| 설명 |
|---|---|
| 배터리 절약 모드| 전원에서 시스템 연결이 끊어지면 전원을 절약하고 배터리 사용 수명을 연장할 수 있습니다. 배터리 절약형이 설정되어 있는 경우 일부 Windows 기능은 사용하지 않도록 설정되거나, 스로틀되거나, 다르게 작동됩니다. 화면 밝기도 줄어듭니다. 배터리 절약형은 DC(배터리 전원)를 사용할 때만 사용할 수 있습니다. 자세한 내용은 배터리 [절약을 참조합니다.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)|
| 권장 사항 | 이전 버전의 Windows에서 기본 설정보다 배터리 사용 시간이 길어졌다. |
| 성능 향상 | 배터리 사용 시간이 약간 지난 후 기본 슬라이더 모드로 작동하면 성능이 약간 향상됩니다. |
| 최상의 성능 | 배터리 전원 소비에 관계없이 성능을 최대화하고 응답성을 요구하는 워크로드의 경우 전원을 통해 성능을 향상합니다.|

전원 슬라이더 모드는 다음 표에 나와 있는 특정 하드웨어 구성 요소를 직접 제어합니다.

| 구성 요소 | 슬라이더 기능 |
|---|---|
| Intel 속도 전환(CPU 에너지 레지스터) 및 에너지 성능 기본 설정 힌트입니다. | 최적의 성능과 전원을 위해 최적의 작동 빈도와 사용 빈도를 선택합니다. PERFEPP(에너지 성능 기본 설정)는 CPU에 대한 전역 전원 효율성 힌트입니다. |
| RPM(팬 속도)| 해당하는 경우 배터리 절약 모드의 팬 자동 유지와 같은 변경 조건에 맞게 조정합니다.|
| 프로세서 패키지 전원 제한(PL1/PL2)| CPU에서 PL1(유지 상태) 및 PL2(터보) 워크로드에 대해 실행 중인 평균 전원 제한을 수용하기 위해 해당 주파수 선택을 관리해야 합니다.|
| 프로세서 터보 주파수 제한(IA turbo 제한) | 프로세서 및 그래픽 성능을 조정하여 프로세서 코어가 정격된 작동 빈도보다 더 빠르거나 느리게 실행될 수 있습니다.                                                |

>[!NOTE]
>전원 슬라이더는 제어판/ 전원 옵션, 그룹 정책 또는 관련 방법에서 구성한 운영 체제 전원 설정과 완전히 독립적입니다.

자세한 내용은 다음을 참조합니다.

-   [Windows 성능 전원 슬라이더 사용자 지정](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [배터리 절약](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## 배터리 사용 기간 연장을 위한 모범 사례


| 모범 사례 | 이동: | 다음 단계 |
|---|---|---|                                                                                                                                    
| Surface 디바이스를 최신으로 유지| Windows 업데이트 | 작업 표시줄 검색 상자에 **Windows 업데이트를** 입력하고 업데이트 **확인을 선택합니다.** |
| 수행하고 있는 작업을 위한 최상의 전원 설정 선택 | 전원 슬라이더 | 작업 표시줄에서 배터리 아이콘을 선택한 **** 다음 **** 최상의 성능, 최상의 배터리 사용 가능 또는 그 사이에 있는 아무 곳에나 선택합니다.|
| 부족한 경우 배터리 절약 | 배터리 절약 모드 | 작업 표시줄에서 배터리 아이콘을 선택하고 배터리 **설정을 클릭합니다.** 배터리 **사용 시간이** 길어질 경우 배터리 절약을 자동으로 켜고 슬라이더를 오른쪽으로 끄십시오. |
| 최적의 화면 밝기 구성 | 배터리 절약 모드 | 작업 표시줄에서 배터리 아이콘을 선택하고 배터리 설정을 **클릭하고**배터리 절약에 있는 동안 화면 밝기를 **더 낮게 선택합니다.** |
| 연결되어 있지 않을 때마다 전원 절약 | 배터리 절약 모드| 다음 충전까지 배터리 **절약 상태 켜기를 선택합니다.**|
| 전원 설정 문제를 조사합니다. | 전원 문제 해결사 | 문제 해결을 위해 작업 **** 표시줄 검색에서 문제 해결을 선택한 다음 **전원을** 선택하고 지침을 따릅니다.|
| 앱 사용 현황 확인 | 앱 | 앱을 닫습니다.|
| 전원 코드에 손상이 없는지 검사합니다.| 전원 코드 | 전원 코드가 손상된 경우 교체합니다.|

## 자세히 알아보기 

- [최신 대기](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Windows 성능 전원 슬라이더 사용자 지정](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [배터리 절약](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Surface 드라이버 및 펌웨어 업데이트 관리 및 배포](manage-surface-driver-and-firmware-updates.md)
