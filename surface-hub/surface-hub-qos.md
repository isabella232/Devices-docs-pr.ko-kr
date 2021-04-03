---
title: Surface Hub에서 서비스 품질 구현
ms.reviewer: ''
manager: laurawi
description: Surface Hub에서 QoS를 구성하는 방법을 알아보십시오.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470486"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>Surface Hub에서 QoS(서비스 품질) 구현

QoS(서비스 품질)는 관리자가 실시간 오디오/비디오 및 응용 프로그램 공유 통신 환경을 최적화할 수 있도록 하는 네트워크 기술의 조합입니다.
 
Surface Hub에서 비즈니스용 Skype에 대한 [QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 구성은 [MDM(모바일](manage-settings-with-mdm-for-surface-hub.md) 장치 관리) 공급자 또는 프로비저닝 패키지를 사용하여 구성할 [수 있습니다.](provisioning-packages-for-surface-hub.md) 
 
 
이 절차에서는 Microsoft Intune을 사용하여 Surface Hub에 대한 QoS를 구성하는 방법을 설명합니다. 

1. Intune에서 [사용자 지정 정책 을 생성합니다.](https://docs.microsoft.com/intune/custom-settings-configure)

    > [!div class="mx-imgBorder"]
    > ![Intune의 사용자 지정 정책 만들기 대화 상자 스크린샷](images/qos-create.png)

2. 사용자 **지정 OMA-URI 설정에서**추가를 **선택합니다.** 추가하는 각 설정에 대해 이름, 설명(선택 사항), 데이터 형식, OMA-URI 및 값을 입력합니다.

    > [!div class="mx-imgBorder"]
    > ![빈 OMA-URI 설정 대화 상자의 스크린샷](images/qos-setting.png)

3. 다음 사용자 지정 OMA-URI 설정을 추가합니다.<br/><br/>

    이름 | 데이터 형식 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  값
    --- | --- | --- | ---
    오디오 원본 포트 | 문자열 |  /HubAudio/SourcePortMatchCondition  |   Skype 관리자로부터 값 얻기
    오디오 DSCP | 정수 |  /HubAudio/DSCPAction  |   46
    비디오 원본 포트 | 문자열 |  /HubVideo/SourcePortMatchCondition   |  Skype 관리자로부터 값 얻기
    비디오 DSCP | 정수 |  /HubVideo/DSCPAction   |   34
    오디오 프로세스 이름 | 문자열 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    비디오 프로세스 이름 | 문자열 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >각 **OMA-URI** 경로는 로 `./Device/Vendor/MSFT/NetworkQoSPolicy` 시작됩니다. 예를 들어 오디오 원본 포트 설정의 전체 경로는 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 입니다.

4. 정책이 만들어지면 Surface Hub에 배포합니다.


>[!WARNING]
>현재 [NetworkQoSPolicy CSP에서](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) **IPProtocolMatchCondition** 설정을 구성할 수 없습니다. 이 설정을 구성하면 정책이 적용되지 않습니다.
 
