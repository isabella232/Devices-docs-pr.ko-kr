---
title: Surface Hub에서 서비스 품질 구현
ms.reviewer: ''
manager: laurawi
description: 사용자에 대해 QoS를 구성하는 Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: b235ab8e19df42fa63efe5e66ac590c58c50d179
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910953"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>서비스 품질(QoS)을 Surface Hub

QoS(서비스 품질)는 관리자가 실시간 오디오/비디오 및 응용 프로그램 공유 통신 환경을 최적화할 수 있도록 하는 네트워크 기술의 조합입니다.
 
MDM(모바일 비즈니스용 Skype [관리)](manage-settings-with-mdm-for-surface-hub.md) Surface Hub 또는 프로비저닝 패키지를 사용하여 앱에 대한 [QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 구성을 [완료할 수 있습니다.](provisioning-packages-for-surface-hub.md) 
 
 
이 절차에서는 사용자 설정을 사용하여 Surface Hub QoS를 구성하는 Microsoft Intune. 

1. Intune에서 [사용자 지정 정책 을 생성합니다.](https://docs.microsoft.com/intune/custom-settings-configure)

    > [!div class="mx-imgBorder"]
    > ![Screenshot of custom policy creation dialog in Intune.](images/qos-create.png)

2. 사용자 **지정 OMA-URI**설정 추가를 **선택합니다.** 추가하는 각 설정에 대해 이름, 설명(선택 사항), 데이터 형식, OMA-URI 및 값을 입력합니다.

    > [!div class="mx-imgBorder"]
    > ![빈 OMA-URI 설정 대화 상자의 스크린샷입니다.](images/qos-setting.png)

3. 다음 사용자 지정 OMA-URI 설정을 추가합니다.<br/><br/>

    이름 | 데이터 형식 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  값
    --- | --- | --- | ---
    오디오 원본 포트 | 문자열 |  /HubAudio/SourcePortMatchCondition  |   관리자로부터 값을 Skype
    오디오 DSCP | 정수 |  /HubAudio/DSCPAction  |   46
    비디오 원본 포트 | 문자열 |  /HubVideo/SourcePortMatchCondition   |  관리자로부터 값을 Skype
    비디오 DSCP | 정수 |  /HubVideo/DSCPAction   |   34
    오디오 프로세스 이름 | 문자열 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    비디오 프로세스 이름 | 문자열 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >각 **OMA-URI** 경로는 로 `./Device/Vendor/MSFT/NetworkQoSPolicy` 시작됩니다. 예를 들어 오디오 원본 포트 설정의 전체 경로는 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 입니다.

4. 정책이 만들어지면 정책에 Surface Hub.


>[!WARNING]
>현재 [NetworkQoSPolicy CSP에서](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) **IPProtocolMatchCondition** 설정을 구성할 수 없습니다. 이 설정을 구성하면 정책이 적용되지 않습니다.
 
