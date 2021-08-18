---
title: Surface Hub가 업데이트를 설치하고 유지 관리 시간 외에 다시 시작할 수 있음
description: 자동 업데이트와 Surface Hub 대한 문제 해결 정보
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub, 유지 관리 기간, 업데이트
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7c023256750ee997ce50d0adcd392207f47a298f
ms.sourcegitcommit: 3810c4310e9f5b5b9ad7b4584eaede2789ccd946
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902887"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a>Surface Hub가 업데이트를 설치하고 유지 관리 시간 외에 다시 시작할 수 있음

특정 상황에서는 Surface Hub 유지 관리 기간이 아닌 업무 시간 동안 업데이트를 설치합니다. 그런 다음 필요한 경우 장치가 다시 시작됩니다. 프로세스가 완료될 때까지 디바이스를 사용할 수 없습니다.

> [!NOTE]  
> 유지 관리 기간이 누락되는 경우의 동작은 예상되지 않습니다. 디바이스가 오래 된 경우만 발생합니다.

## <a name="cause"></a>원인

업무 Surface Hub 사용할 수 있도록 허브는 설정(아래 "참조")에 정의된 유지 관리 기간 동안 관리 기능을 수행하도록 구성됩니다. 이 유지 관리 기간 동안 허브는 WUfB(비즈니스용 업데이트)Windows 또는 Windows 업데이트를 통해 사용 가능한 업데이트를 자동으로 설치합니다. 업데이트가 완료되면 허브가 다시 시작될 수 있습니다.

업데이트는 유지 관리 기간 동안 설치될 수 있습니다Surface Hub 설정되어 있지만 사용 중 또는 예약되지는 않습니다. 예를 들어 Surface Hub 예약된 모임의 경우 설치 예정된 업데이트는 다음 유지 관리 기간 동안 허브를 사용할 수 있을 때까지 지연됩니다. 허브가 계속 사용 중일 때 여러 유지 관리 기간이 누락되면 결국 허브는 업데이트를 설치하고 다운로드하기 시작하게 됩니다. 이 경우 유지 관리 기간 중이나 외부에서 발생할 수 있습니다. 다운로드 및 설치가 시작된 후 장치가 다시 시작될 수 있습니다.

## <a name="to-avoid-this-issue"></a>이 문제를 방지

관리 기능을 수행하기 위해 유지 관리 시간을 Surface Hub 것이 중요합니다. 24시간 Surface Hub 또는 유지 관리 기간 동안 디바이스를 사용하여 업데이트 설치를 지연합니다. 예약된 유지 관리 기간 동안 허브를 사용하지 않는 것이 좋습니다. 2시간 동안의 기간은 업데이트로 예약해야 합니다.

업데이트의 가용성을 제어하는 데 사용할 수 있는 한 가지 옵션은 비즈니스용 Windows 것입니다.

## <a name="learn-more"></a>자세히 알아보기
  
- [유지 관리 기간](manage-windows-updates-for-surface-hub.md#maintenance-window) 
