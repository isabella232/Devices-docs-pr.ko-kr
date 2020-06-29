---
title: Surface Hub가 업데이트를 설치하고 유지 관리 시간 외에 다시 시작할 수 있음
description: 자동 업데이트와 관련 된 Surface Hub의 문제 해결 정보
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub, 유지 관리 창, 업데이트
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836404"
---
# Surface Hub가 업데이트를 설치하고 유지 관리 시간 외에 다시 시작할 수 있음

특정 상황에서 Surface Hub는 정기 유지 관리 기간 대신 비즈니스 시간 동안 업데이트를 설치 합니다. 필요한 경우 장치가 다시 시작 됩니다. 이 장치는 프로세스가 완료 될 때까지 사용할 수 없습니다.

> [!NOTE]  
> 유지 관리 기간이 누락 된 경우이 동작은 필요 하지 않습니다. 이는 장치가 오랜 시간 동안 만료 된 경우에만 발생 합니다.

## 원인
비즈니스 시간 동안 Surface Hub를 계속 사용할 수 있도록 하려면 설정에 정의 된 유지 관리 기간 동안 허브가 관리 기능을 수행 하도록 구성 되어 있는지 확인 합니다 (아래 "참조" 참조). 이 유지 관리 기간 동안 허브는 Windows Update 또는 WSUS (Windows Server Update Service)를 통해 사용 가능한 업데이트를 자동으로 설치 합니다. 업데이트가 완료 되 면 허브가 다시 시작 될 수 있습니다.

Surface Hub가 켜져 있지만 사용 되지 않거나 예약 되어 있지 않은 경우에만 유지 관리 기간 동안 업데이트를 설치할 수 있습니다. 예를 들어 Surface Hub가 24 시간 동안 지속 되는 모임에 대해 예약 된 경우 설치 하도록 예약 된 업데이트는 다음 유지 관리 창에서 허브를 사용할 수 있을 때까지 지연 됩니다. 허브가 계속 사용 중이 고 여러 유지 관리 창이 누락 되는 경우에는 허브가 결국 업데이트를 설치 하 고 다운로드 하기 시작 합니다. 이는 유지 관리 기간 중 또는 외부에 발생할 수 있습니다. 다운로드 및 설치가 시작 되 면 디바이스가 다시 시작 될 수 있습니다.

## 이 문제를 방지 하려면

관리 기능을 수행 하기 위해 Surface Hub에 대해 유지 관리 시간을 따로 설정 하는 것이 중요 합니다. 화면 허브를 24 시간 간격으로 예약 하거나 유지 관리 창에서 장치를 사용 하 여 업데이트를 설치 하는 동안 지연 됩니다. 예약 된 유지 관리 기간에 허브를 사용 하거나 예약 하지 않는 것이 좋습니다. 업데이트를 위해 2 시간 윈도를 예약 해야 합니다.

업데이트 가용성을 제어 하는 데 사용할 수 있는 한 가지 옵션은 WSUS (Windows Server Update Service)입니다. WSUS는 설치 되는 업데이트 및 시기에 대 한 제어권을 제공 합니다.

## 참조 
 
[Surface Hub 업데이트](first-run-program-surface-hub.md#update-the-surface-hub) 

[유지 관리 기간](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[WSUS(WindowsServer Update Services)를 사용하여 Windows10 업데이트 배포](/windows/deployment/update/waas-manage-updates-wsus) 


