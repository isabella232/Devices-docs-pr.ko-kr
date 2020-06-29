---
title: Surface Hub에서 서비스 품질 구현
ms.reviewer: ''
manager: laurawi
description: Surface Hub에서 QoS를 구성 하는 방법에 대해 알아봅니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835191"
---
# Surface Hub에서 QoS (서비스 품질)를 구현 합니다.

QoS (서비스 품질)는 관리자가 실시간 오디오/비디오 및 응용 프로그램 공유 통신 환경을 최적화 하는 데 사용할 수 있는 네트워크 기술의 조합입니다.
 
Surface Hub에서 비즈니스용 [Skype에 대해 QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 를 구성 하려면 [MDM (모바일 디바이스 관리) 공급자](manage-settings-with-mdm-for-surface-hub.md) 를 사용 하거나 [제공 패키지](provisioning-packages-for-surface-hub.md)를 통해 수행할 수 있습니다. 
 
 
이 절차에서는 Microsoft Intune을 사용 하 여 Surface Hub에 대 한 QoS를 구성 하는 방법을 설명 합니다. 

1. Intune에서 [사용자 지정 정책을 만듭니다](https://docs.microsoft.com/intune/custom-settings-configure).

    ![Intune의 사용자 지정 정책 만들기 대화 상자 스크린샷](images/qos-create.png)

2. **사용자 지정 OMA-URI 설정**에서 **추가**를 선택 합니다. 추가 하는 각 설정에 대해 이름, 설명 (선택 사항), 데이터 형식, OMA-URI 및 값을 입력 합니다.

    ![빈 OMA-URI 설정 대화 상자 스크린샷](images/qos-setting.png)

3. 다음 사용자 지정 OMA-URI 설정을 추가 합니다.

    이름 | 데이터 형식 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  값
    --- | --- | --- | ---
    오디오 원본 포트 | 문자열 |  /HubAudio/SourcePortMatchCondition  |   Skype 관리자에 게 서 값을 구합니다.
    오디오 DSCP | 정수 |  /HubAudio/DSCPAction  |   46
    비디오 원본 포트 | 문자열 |  /HubVideo/SourcePortMatchCondition   |  Skype 관리자에 게 서 값을 구합니다.
    비디오 DSCP | 정수 |  /HubVideo/DSCPAction   |   34
    오디오 프로세스 이름 | 문자열 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    비디오 프로세스 이름 | 문자열 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >각 **OMA URI** 경로는로 시작 `./Device/Vendor/MSFT/NetworkQoSPolicy` 됩니다. 예를 들어 오디오 원본 포트 설정의 전체 경로는 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 입니다.




4. 정책이 만들어졌으면 [Surface Hub에 배포 합니다.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>현재 [Networkqospolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)에서 **Ipprotocolmatchcondition** 설정을 구성할 수 없습니다. 이 설정이 구성 되 면 정책이 적용 되지 않습니다.
 
