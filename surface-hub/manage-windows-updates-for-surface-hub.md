---
title: Surface Hub에 대한 Windows 업데이트 관리
description: Microsoft Surface Hub 또는 Surface Hub 2S에서 업데이트를 관리하기 위한 모범 사례를 설명합니다.
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: Windows 업데이트, Surface Hub, Windows Server Update Services 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: ecff961e1aaa14ed2af5e6d91ffc2254e4dcfa46
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497781"
---
# <a name="manage-windows-updates-on-surface-hub"></a>Surface Hub에 대한 Windows 업데이트 관리

Surface Hub 운영 체제의 새 릴리스는 Windows 10 또는 Windows 11 릴리스와 마찬가지로 Windows 업데이트 통해 게시됩니다. 이 페이지에서는 Surface Hub 디바이스에 대한 업데이트를 관리하는 모범 사례를 설명합니다. 

## <a name="windows-update-for-business"></a>비즈니스용 Windows 업데이트

비즈니스용 Windows 업데이트 디바이스 관리 비용을 줄이면서 Windows 업데이트 릴리스를 설치하는 방법과 시기를 기업에게 추가로 제어할 수 있도록 설계된 일련의 기능입니다. 이 방법을 사용하면 Surface Hub가 Microsoft Windows 업데이트 서비스에 직접 연결됩니다.

- 다른 인프라를 추가하지 않아도 Microsoft Windows 업데이트 서비스에서 직접 업데이트를 받습니다. 
- 테스트와 평가를 위해 추가 시간을 제공하기 위해 업데이트를 연기합니다. 
- 업데이트를 배포하여 장치 그룹을 선택합니다. 
- 업데이트를 설치할 유지 관리 기간을 정의합니다. 

> [!TIP]
> 피어 투 피어 콘텐츠 공유를 사용하여 업데이트 중에 대역폭 문제를 줄입니다. 자세한 내용은 [업데이트 업데이트 Windows 최적화](/windows/deployment/do/waas-optimize-windows-10-updates)를 참조하세요.

> [!NOTE]
> Surface Hub는 현재 업데이트 롤백을 지원하지 않습니다.


## <a name="surface-hub-servicing-model"></a>Surface Hub 서비스 모델

Surface Hub [waaS(](/windows/deployment/update/waas-overview)Windows 서비스)라고 하는 Windows 서비스 모델을 사용합니다. 일반적으로 새로운 기능은 몇 년마다 릴리스되는 새 Windows 버전에만 추가되었습니다. 각각의 새 버전을 조직에 배포하려면 오래 걸리고 비용이 많이 드는 프로세스가 필요했습니다. 따라서 최종 사용자와 조직은 보통 새로운 혁신의 이점을 누리지 못합니다. Windows as a Service의 목표는 높은 수준의 품질을 유지하면서 새 기능을 계속 제공하는 것입니다.

Microsoft는 지속적으로 두 가지 유형의 Surface Hub 릴리스를 광범위하게 게시합니다.
- **기능 업데이트** - 최신 기능, 환경 및 특징을 설치하는 업데이트입니다. Microsoft는 연간 두 개의 새로운 기능 업데이트를 게시할 것으로 예상합니다.
- **품질 업데이트** - 보안 수정, 드라이버 및 기타 서비스 업데이트의 설치에 중점을 둔 업데이트입니다. Microsoft는 매월 하나의 누적 품질 업데이트를 게시할 예정입니다.

릴리스 품질을 개선하고 배포를 간소화하기 위해 microsoft에서 Surface Hub 포함하여 Windows 10 또는 Windows 11 위해 게시하는 모든 새 릴리스가 누적됩니다. 이는 새 기능 업데이트 및 품질 업데이트가 이전의 모든 릴리스의 페이로드를 저장소 및 네트워킹 요구 사항을 줄이기 위해 최적화된 양식에 포함하고 있으며 장치에 릴리스를 설치하면 완전히 최신 상태가 된다는 것을 의미합니다. 또한 이전 버전의 Windows와 달리 Windows10 품질 업데이트 콘텐츠의 하위 집합을 설치할 수는 없습니다. 예를 들어 품질 업데이트에 세 가지 보안 취약성과 한 가지 안정성 문제에 대한 수정 사항이 포함되어 있는 경우 업데이트를 배포하면 네 가지 수정 사항이 모두 설치됩니다.

Surface Hub 운영 체제 시스템은 [반기 채널](/windows/deployment/update/waas-overview#naming-changes)에 대한 업데이트를 받습니다. 다른 버전의 Windows 10 또는 Windows 11 마찬가지로 서비스 수명은 유한합니다. 품질 업데이트를 계속 받으려면 이러한 분기를 실행하는 컴퓨터에 새로운 기능 업데이트를 설치해야 합니다.

Windows as a Service에 대한 자세한 내용은 [Windows as a Service 개요](/windows/deployment/update/waas-overview)를 참조하세요.


## <a name="use-windows-update-for-business"></a>비즈니스용 Windows 업데이트 사용

모든 Windows10 장치처럼 Surface Hub에는 장치가 업데이트되는 방식을 제어할 수 있는 **WUfB(비즈니스용 Windows 업데이트)** 가 포함됩니다. 비즈니스용 Windows 업데이트를 통해 장치 관리 비용을 줄이고, 업데이트 배포를 제어하며, 보안 업데이트에 빠르게 액세스할 수 있을 뿐만 아니라 지속적으로 Microsoft에서 제공하는 혁신적인 최신 기능에 액세스할 수 있습니다. 자세한 내용은 [비즈니스용 Windows 업데이트를 사용하여 업데이트 관리](/windows/deployment/update/waas-manage-updates-wufb)를 참조하세요.

> [!IMPORTANT]
> Microsoft는 일반적으로 매월 하나의 필수 Windows 보안 업데이트를 릴리스합니다(2일 화요일에 릴리스되고 종종 "B" 릴리스라고도 함). 대역 외 보안 업데이트와 함께 WUfB를 사용하여 디바이스에서 사용할 수 있는 유일한 업데이트입니다. 그러나 Surface Hub 개선 사항은 일반적으로 매월 3일 화요일("C" 릴리스)에 대한 선택적 비보안 업데이트를 통해 제공됩니다. 따라서 Surface Hubs에서 비즈니스용 Windows 업데이트 사용하는 고객은 다음 달의 "B" 릴리스까지 대기하여 이러한 디바이스의 최신 개선 사항을 확인할 수 있습니다.

**비즈니스용 Windows 업데이트를 설정하려면**
1. [Surface Hub를 배포 링으로 그룹화](#group-surface-hub-into-deployment-rings)
2. [Surface Hub가 업데이트를 받는 시기를 구성합니다](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> Microsoft Intune, Microsoft Endpoint Configuration Manager 또는 지원되는 타사 MDM 공급자를 사용하여 WUfB를 설정할 수 있습니다. [연습: Microsoft Intune을 사용하여 비즈니스용 Windows 업데이트 구성.](/windows/deployment/update/waas-wufb-intune)


### <a name="group-surface-hub-into-deployment-rings"></a>Surface Hub를 배포 링으로 그룹화

배포 링을 통해 업데이트가 Surface Hub에 출시되는 시기를 제어하여 유효성을 검사할 시간을 제공할 수 있습니다. 예를 들어 먼저 작업 장치 풀을 업데이트하여 조직에 더 광범위하게 출시하기 전에 품질을 확인할 수 있습니다. 조직에서 Surface Hub 관리하는 사람에 따라 다른 Windows 10 또는 Windows 11 디바이스용으로 빌드한 배포 링에 Surface Hub 통합하는 것이 좋습니다. 배포 링에 대한 자세한 내용은 [Windows 클라이언트 업데이트에 대한 서비스 전략 준비를 참조하세요](/windows/deployment/update/waas-servicing-strategy-windows-10-updates).

배포 링의 예는 다음 표를 참조하세요.

| 배포 링 | 링 크기 | 서비스 분기 | 기능 업데이트 지연 | 품질 업데이트 지연(보안 수정, 드라이버 및 기타 업데이트) | 유효성 검사 단계 |
| --------- | --------- | --------- | --------- | --------- | --------- |
| 미리 보기(예: 중요하지 않은 또는 테스트용 장치) | 적음 | Windows Insider Preview | 없음.  | 없음.  | 새 기능을 수동으로 테스트 및 평가합니다. 문제가 있는 경우 업데이트를 일시 중지합니다. |
| 릴리스(예: 선택 팀에서 사용하는 장치) | 보통 | 반기 채널  | 없음. | 없음.  | 장치 사용 및 사용자 피드백을 모니터링합니다. 문제가 있는 경우 업데이트를 일시 중지합니다. |
| 광범위한 배포(예: 조직에 있는 대부분 장치) | 큼 | 반기 채널 |  릴리스 후 120일 | 릴리스 후 7~14일 | 장치 사용 및 사용자 피드백을 모니터링합니다. 문제가 있는 경우 업데이트를 일시 중지합니다. |
| 중요 업무용(예: 중역 회의실) | 적음 | 반기 채널 |  릴리스 후 180일(기능 업데이트 최대 지연). | 릴리스 후 30일(품질 업데이트 최대 지연). | 장치 사용 및 사용자 피드백을 모니터링합니다. |


### <a name="configure-when-surface-hub-receives-updates"></a>Surface Hub가 업데이트를 받는 시기 구성

Surface Hub에 대한 배포 링을 확인한 후 각 링에 대한 업데이트 지연 정책을 구성합니다.
- 기능 업데이트를 연기하려면 각 링에 대한 적절한 [Update/DeferFeatureUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) 정책을 설정합니다.
- 품질 업데이트를 연기하려면 각 링에 대한 적절한 [Update/DeferQualityUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) 정책을 설정합니다.

> [!NOTE]
> 업데이트 출시 중에 문제가 발생하면 [Update/PauseFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) 및 [Update/PauseQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates)를 사용하여 업데이트를 일시 중지할 수 있습니다.

**프록시 서버 또는 기타 방법을 사용하여 URL을 차단하는 경우**

다음 Windows 신뢰할 수 있는 사이트 URL을 "허용 목록"으로 업데이트합니다.
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Windows 10 Team 1주년 업데이트를 설치한 다음에는 이들 주소를 제거하여 Surface Hub를 이전 상태로 되돌릴 수 있습니다.

## <a name="maintenance-window"></a>유지 관리 기간

업무 시간 중에 항상 장치를 사용할 수 있도록 Surface Hub는 지정된 유지 관리 기간 동안 관리 기능을 수행합니다. 유지 관리 기간 동안 Surface Hub Windows 업데이트 통해 업데이트를 자동으로 설치하고 창이 끝나기 20분 전에 디바이스를 다시 부팅합니다.

Surface Hub는 다음 지침에 따라 업데이트를 적용합니다.
- 다음 유지 관리 기간 동안 업데이트를 설치합니다. 모임이 유지 관리 기간 중에 시작되도록 예약되었거나 Surface Hub 센서에서 장치가 사용되고 있음을 감지할 경우 보류 중인 업데이트가 다음 유지 관리 기간까지 연기됩니다.
- 다음 유지 관리 기간이 업데이트의 지정된 유예 기간을 지난 경우 장치는 업데이트 메타데이터의 예상 설치 시간을 사용하여 업무 시간 중에 다음 사용 가능한 슬롯을 계산합니다. 모임이 예약되었거나 Surface Hub 센서가 장치가 사용되고 있음을 감지할 경우 업데이트가 계속 연기됩니다.
- 다음 유지 관리 기간이 업데이트 유예 기간을 넘**지 않으면** Surface Hub 업데이트를 계속 연기합니다.
- 다시 시작이 필요할 경우 Surface Hub는 다음 유지 관리 기간 중에 자동으로 다시 시작됩니다.

> [!NOTE]
> Surface Hub를 처음 설치할 때 업데이트 시간을 허용합니다. 예를 들어 즉시 설치되어야 하는 바이러스 정의의 백로그가 있을 수 있습니다.

모든 새 Surface Hub에 대해 기본 유지 관리 기간이 설정됩니다.
-   **시작 시간:** 오전 2:00
-   **기간:** 2시간

**유지 관리 기간을 수동으로 변경하려면**
1.  Surface Hub에서 **설정**을 엽니다.
2.  **업데이트 및 보안** > **Windows 업데이트** > **고급 옵션**으로 이동합니다.
3.  **유지 관리 시간**에서 **변경**을 선택합니다.

MDM을 사용하여 유지 관리 기간을 변경하려면 [SurfaceHub 구성 서비스 공급자](/windows/client-management/mdm/surfacehub-csp)에서 **MaintenanceHoursSimple** 노드를 설정합니다. 자세한 내용은 [MDM 공급자 설정 관리](manage-settings-with-mdm-for-surface-hub.md)를 참조하세요.


## <a name="more-information"></a>추가 정보

- [블로그 게시물: Surface Hub 대한 서비스, 플라이팅 및 업데이트 관리(물론 Intune 포함!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## <a name="related-topics"></a>관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)

