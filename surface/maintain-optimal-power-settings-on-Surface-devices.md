---
title: Surface 장치의 모범 사례 전원 설정
description: 이 항목에서는 최적의 전원 설정을 유지 관리하기 위한 모범 사례 권장 사항을 설명하고 Surface가 전원 관리 환경을 간소화하는 방법을 설명합니다. 이 문서는 Surface Pro 7+, Surface Pro 7, Surface Pro X 및 Surface Laptop 3을 포함하여 현재 지원되는 모든 Surface 장치에 적용됩니다.
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: b4a9a1756abc4d7a45c5b4eb5081e8f5a72565eb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448311"
---
# <a name="best-practice-power-settings-for-surface-devices"></a>Surface 장치의 모범 사례 전원 설정

Surface 디바이스는 모바일 장치 에너지 소비의 최신 발전을 활용하여 워크로드에 최적화된 간소화된 환경을 제공하도록 디자인되었습니다. Surface는 수행하는 작업에 따라 전원이 개별 하드웨어 구성 요소로 흐르는 방법을 동적으로 미세하게 설정하고, 들어오는 전자 메일 또는 네트워크 트래픽과 같은 백그라운드 작업을 처리하기 위해 시스템 구성 요소를 잠시 깨우고 저전력 유휴 상태(S0ix)로 돌아올 수 있습니다.

## <a name="summary-of-recommendations-for-it-administrators"></a>IT 관리자를 위한 권장 사항 요약

조직 전체에서 Surface 디바이스가 Surface 전원 최적화 기능을 완전히 사용할 수 있도록 보장하기 위해 다음을 수행할 수 있습니다.

-  Windows 또는 Surface 드라이버 및 펌웨어 MSI에서 최신 드라이버 및 펌웨어를 설치합니다. 이렇게 하면 기본적으로 균형 조정된 전원 계획(전원 프로필)이 만들어지며 최적의 전원 설정을 구성합니다.  자세한 내용은 Surface 드라이버 및 펌웨어 업데이트 [관리 및 배포를 참조하세요](manage-surface-driver-and-firmware-updates.md).
- 사용자 지정 전원 프로필을 만들거나 기본 UI에 표시되지 않는 고급 전원 설정을 조정하지 않도록 합니다 **(SystemPower****** >  & 절전 모드).
- 고도로 관리되는 조직과 같이 네트워크를 통해 디바이스의 전원 프로필을 관리해야 하는 경우 powercfg 명령 도구를 사용하여 Surface 디바이스의 출하 시 이미지에서 전원 계획을 내보친 다음 Surface 디바이스의 프로비저닝 패키지로 가져올 수 있습니다. 

    >[!NOTE]
    >동일한 유형의 Surface 디바이스에서만 전원 계획을 내보낼 수 있습니다.  예를 들어 Power Plan을 2016에서 내보낼 수 Surface Laptop 수 없습니다. Surface Pro.  자세한 내용은 전원 설정 [구성을 참조하세요](/windows-hardware/customize/power-settings/configure-power-settings).

- 기존 전원 관리 정책 설정에서 Surface 디바이스를 제외합니다. 

## <a name="background"></a>Background

Surface에서 전원 관리를 구현하는 방식은 일련의 절전 상태의 전원을 점진적으로 줄여 전원을 끄는 이전 OS 표준과 크게 다릅니다. 예를 들어 S1, S2, S3 등에서 순환합니다.

대신 Surface는 레거시 절전 모드 및 에너지 소비 기능을 최신 대기 기능 및 동적 미세 조정으로 대체하는 사용자 지정 전원 프로필로 이미지가 작성되었습니다. 이 사용자 지정 전원 프로필은 Surface 직렬 허브 드라이버 및 SAM(시스템 집계 모듈)을 통해 구현됩니다. SAM 칩은 알고리즘을 사용하여 최적의 전원 요구 사항을 계산하는 Surface 디바이스 전원 정책 소유자의 기능을 합니다. 하드웨어 구성 요소의 작동에 필요한 정확한 Windows 전원만 할당하거나 스로틀하기 위해 전원 관리자와 함께 작동합니다. 이 문서는 Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X 및 Surface Laptop 3을 포함하여 현재 지원되는 모든 Surface 장치에 적용됩니다.

## <a name="utilizing-the-custom-power-profile-in-surface"></a>Surface에서 사용자 지정 전원 프로필 사용

Surface 디바이스의 전원 옵션으로 이동하면 사용 가능한 하나의 전원 플랜이 있는 것입니다. 사용자 지정 전원 프로필입니다. 고급 전원 설정으로 이동하면 전원 옵션의 하위 집합이 일반 PC에 비해 훨씬 더 작은 전원 Windows 10 Windows 11. 일반 디바이스와 달리 Surface에는 이러한 전원 옵션을 관리하는 펌웨어 및 사용자 지정 구성 요소가 있습니다.


## <a name="modern-standby"></a>최신 대기

알고리즘에 포함된 사용자 지정 전원 프로필을 사용하면 스마트폰의 일반적인 즉각적인 사용/즉시 끄기 기능에 낮은 전원 상태를 유지하여 Surface에 대한 최신 대기 상태를 사용할 수 있습니다. DRIPS(심층 런타임 유휴 플랫폼 상태)라고도 하는 S0ix는 Surface 디바이스의 기본 전원 모드입니다. 최신 대기 모드에는 두 가지 모드가 있습니다.

- **연결된 대기입니다.** 전자 메일, 메시징 및 클라우드 동기화 데이터의 최신 배달을 위한 기본 모드인 연결된 대기 상태는 Wi-Fi 유지 관리하며 네트워크 연결을 유지합니다.

- **연결이 끊어진 대기입니다.** 배터리 사용 시간을 연장하기 위한 선택적 모드, 연결이 끊긴 대기 상태는 동일한 인스턴트 켜기 환경을 제공하고 Wi-Fi, Bluetooth 및 관련 네트워크 연결을 해제하여 전원을 절약합니다.

최신 대기에 대한 자세한 내용은 [Microsoft](/windows-hardware/design/device-experiences/modern-standby-wake-sources) 하드웨어 개발자 센터.

## <a name="how-surface-streamlines-the-power-management-experience"></a>Surface에서 전원 관리 환경을 간소화하는 방법 

Surface는 사용자가 전원 관리 환경을 최적화할 수 있도록 설계된 다음 기능을 통합합니다.

- [단수 전원 계획](#singular-power-plan)

- [간소화된 전원 설정 사용자 인터페이스](#simplified-power-settings-user-interface)

- [Windows 전원 슬라이더](#windows-performance-power-slider)

### <a name="singular-power-plan"></a>단수 전원 계획

Surface는 사용자 지정 전원 계획을 만들거나 전원 설정을 수동으로 구성할 필요가 없습니다. Microsoft는 표준 전원 빌드에서 여러 전원 계획을 대체하는 단일 전원 계획(균형 조정된)을 제공하여 사용자 환경을 Windows 간소화합니다.

### <a name="simplified-power-settings-user-interface"></a>간소화된 전원 설정 사용자 인터페이스

Surface는 모범 사례 전원 설정 권장 사항과 어코드된 간소화된 UI를 제공합니다. 일반적으로 기본 사용자 인터페이스에 표시되는 설정만 조정하고 고급 전원 설정 또는 그룹 정책 설정을 구성하지 않는 것이 좋습니다. 최대 밝기 수준을 피하면서 기본 화면 및 절전 모드 시간 제한을 사용하는 것이 사용자가 배터리 사용 시간을 연장하는 가장 효과적인 방법입니다.

![그림 1. 절전 설정이 & 간소화되었습니다.](images/powerintrofig1.png)

그림 1. 전원 및 절전 설정 간소화

### <a name="windows-performance-power-slider"></a>Windows 전원 슬라이더

Windows 10 빌드 1709 이상을 실행하는 Surface 디바이스에는 필요한 경우 배터리 수명의 우선 순위를 지정하거나 원하는 경우 성능을 선호할 수 있는 전원 슬라이더가 포함되어 있습니다. 배터리 아이콘을 클릭하여 작업 표시줄에서 전원 슬라이더에 액세스할 수 있습니다. 배터리 사용 시간이 길어지거나(배터리 절약 모드) 오른쪽으로 밀어 성능을 향상합니다.

![그림 2. 전원 슬라이더.](images/powerintrofig2a.png)

그림 2. 전원 슬라이더

전원 슬라이더는 다음 표에 설명된 네 가지 상태의 사용이 가능하게 합니다.

| 슬라이더 모드| 설명 |
|---|---|
| 배터리 절약 모드| 전원과의 연결이 끊어진 경우 전원을 절약하고 배터리 수명을 연장할 수 있습니다. 배터리 절약 기능이 설정되어 있는 경우 일부 Windows 기능이 사용되지 않도록 설정되거나, 스로틀되거나, 다르게 작동됩니다. 화면 밝기도 줄어듭니다. 배터리 절약은 DC(배터리 전원)를 사용할 때만 사용할 수 있습니다. 자세한 내용은 배터리 절약 [을 참조합니다](/windows-hardware/design/component-guidelines/battery-saver).|
| 권장 사항 | 이전 버전의 2013에서 기본 설정보다 배터리 사용 시간이 더 길어 Windows. |
| 성능 향상 | 기본 슬라이더 모드로 작동하기 위해 배터리 사용 시간이 약간 더 많은 성능을 선호합니다. |
| 최상의 성능 | 배터리 전원 소비에 관계없이 성능을 최대화하고 응답성이 필요한 워크로드의 경우 전원 성능에 대한 성능을 선호합니다.|

전원 슬라이더 모드는 다음 표에 나와 있는 특정 하드웨어 구성 요소를 직접 제어합니다.

| 구성 요소 | 슬라이더 기능 |
|---|---|
| Intel 속도 교대조(CPU 에너지 레지스터) 및 에너지 성능 기본 설정 힌트. | 최적의 성능과 전원을 위해 최적의 작동 빈도와 전원을 선택합니다. PERFEPP(에너지 성능 기본 설정)는 CPU에 대한 전역 전원 효율성 힌트입니다. |
| RPM(팬 속도)| 해당하는 경우 배터리 절약 모드 슬라이더 모드에서 팬 자동 유지와 같은 변경 조건에 맞게 조정합니다.|
| 프로세서 패키지 전원 제한(PL1/PL2).| CPU에서 PL1(정적 상태) 및 PL2(터보) 워크로드에 대해 실행 중인 평균 전원 제한을 수용하기 위해 해당 주파수 선택을 관리해야 합니다.|
| 프로세서 터보 주파수 제한(IA 터보 제한). | 프로세서 및 그래픽 성능을 조정하여 프로세서 코어가 정격 작동 빈도보다 더 빠르거나 느리게 실행될 수 있습니다.                                                |

>[!NOTE]
>전원 슬라이더는 제어판/ 전원 옵션, 그룹 정책 또는 관련 방법에서 구성한 운영 체제 전원 설정과 완전히 독립적입니다.

자세한 내용은 다음을 참조합니다.

-   [성능 Windows 슬라이더 사용자 지정](/windows-hardware/customize/desktop/customize-power-slider)

-   [배터리 절약](/windows-hardware/design/component-guidelines/battery-saver)

## <a name="best-practices-for-extended-battery-life"></a>배터리 사용 기간 연장 모범 사례


| 모범 사례 | 이동: | 다음 단계 |
|---|---|---|                                                                                                                                    
| Surface 디바이스를 최신으로 유지| Windows 업데이트 | 작업 표시줄 검색 상자에 업데이트 Windows **입력**하고 업데이트 **확인을 선택합니다**. |
| 수행하고 있는 작업을 위한 최상의 전원 설정 선택 | 전원 슬라이더 | 작업 표시줄에서 배터리 아이콘을 선택한 다음 최상의 **성능, 최상의** 배터리 사용 **** 가능 또는 그 사이에 있는 곳을 선택합니다.|
| 부족한 배터리 절약 | 배터리 절약 모드 | 작업 표시줄에서 배터리 아이콘을 선택하고 배터리 **설정을 클릭합니다**. 배터리 **사용 시간이** 길어지기 위해 배터리가 아래로 떨어지면 자동으로 배터리 절약 기능을 켜고 슬라이더를 오른쪽으로 끄십시오. |
| 최적의 화면 밝기 구성 | 배터리 절약 모드 | 작업 표시줄에서 배터리 아이콘을 선택하고 배터리 설정을 **클릭**하고 배터리 절약에 있는 동안 화면 밝기를 **낮게 선택합니다**. |
| 연결되어 있지 않을 때마다 전원 절약 | 배터리 절약 모드| 다음 **충전까지 배터리 절약 상태 켜기 를 선택합니다**.|
| 전원 설정 문제를 조사합니다. | 전원 문제 해결사 | 문제 해결을 위한 작업 표시줄 검색에서 문제 해결 **을 선택한 다음** **전원** 을 선택하고 지침을 따릅니다.|
| 앱 사용 현황 확인 | 앱 | 앱을 닫습니다.|
| 전원 코드에 손상이 없는지 검사합니다.| 전원 코드 | 전원 코드가 손상된 경우 전원 코드를 교체합니다.|

## <a name="learn-more"></a>세부 정보 

- [최신 대기](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [성능 Windows 슬라이더 사용자 지정](/windows-hardware/customize/desktop/customize-power-slider)

- [배터리 절약](/windows-hardware/design/component-guidelines/battery-saver)
- [Surface 드라이버 및 펌웨어 업데이트 관리 및 배포](manage-surface-driver-and-firmware-updates.md)
