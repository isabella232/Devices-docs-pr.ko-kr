---
title: Intune으로 Surface Hub 2S 관리하기
description: Intune으로 Surface Hub 2S를 업데이트하고 관리하는 방법을 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1d1b836c18a41982497bb28c57f379408c04f8a5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836636"
---
# Intune으로 Surface Hub 2S 관리하기

## Intune으로 Surface Hub 2S 등록하기

Surface Hub 2S에서는 IT 관리자가 MDM(모바일 장치 관리) 공급자를 사용하여 설정 및 정책을 관리할 수 있습니다. Surface Hub 2S에는 관리 서버와 통신하는 기본 제공 관리 구성 요소가 있어서 장치에 추가 클라이언트를 설치할 필요가 없습니다.

### 수동 등록

1. Surface Hub 2S에서 로컬 관리자로 로그인하고 앱 **설정**을 엽니다. **Surface Hub** > **장치 관리**를 선택한 다음 **+** 를 선택하여 추가합니다.
2. 인증 후 장치는 자동으로 Intune에 등록됩니다.

   ![Intune으로 Surface Hub 2S 등록하기](images/sh2-set-intune1.png)<br>

### 자동 등록 - Azure Active Directory 연결

초기 설정 프로세스 중에 Intune 자동 등록이 설정된 Azure AD 테넌트로 Surface Hub를 연결하는 경우 장치가 자동으로 Intune에 등록됩니다. 자세한 내용은 [Windows 장치에 대한 Intune 등록 방법](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)을 참조하세요. Surface Hub가 Intune에서 "호환 장치"가 되려면 Azure AD에 연결과 Intune 자동 등록이 필요합니다. 

## Windows 10 Team 버전 설정

Surface Hub 및 Surface Hub 2S에 대한 사전 설정된 장치 제한을 보려면 Windows 10 Teams을 선택하세요.

 ![Surface Hub 2S에 대한 장치 제한을 설정합니다.](images/sh2-set-intune3.png) <br>

이러한 설정에는 사용자 환경과 앱 동작, Azure Log Analytics 등록, 유지 관리 기간 구성, 세션 설정, Miracast 설정 등이 포함됩니다. 사용 가능한 Windows 10 Team 설정의 전체 목록은 [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)를 참조하세요.

## 추가 지원되는 CSP(구성 서비스 공급자)

추가 지원되는 CSP에 대한 자세한 내용은 [Windows 10의 Surface Hub CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)를 참조하세요.

## QoS(서비스 품질) 설정

Surface Hub 2S에서 최적의 비디오 및 오디오 품질을 보장하려면 장치에 다음 QoS 설정을 추가하세요. 

### Microsoft Teams QoS 설정 

|**이름**|**설명**|**OMA-URI**|**형식**|**값**|
|:------ |:------------- |:--------- |:------ |:------- |
|**오디오 포트**| 오디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | 문자열  | 3478-3479 |
|**오디오 DSCP**| 오디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | 정수 | 46 |
|**비디오 포트**| 비디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | 문자열  | 3480 |
|**비디오 DSCP**| 비디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | 정수 | 34 |
|**P2P 오디오 포트**| 오디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | 문자열  | 50000-50019 |
|**P2P 오디오 DSCP**| 오디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | 정수 | 46 |
|**P2P 비디오 포트**| 비디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | 문자열  | 50020-50039 |
|**P2P 비디오 DSCP**| 비디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | 정수 | 34 |


### 비즈니스용 Skype QoS 설정

| 이름               | 설명         | OMA-URI                                                                  | 형식    | 값                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| 오디오 포트        | 오디오 포트 범위    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | 문자열  | 50000-50019                    |
| 오디오 DSCP         | 오디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | 정수 | 46                             |
| 오디오 미디어 원본 | Skype 앱 이름      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | 문자열  | Microsoft.PPISkype.Windows.exe |
| 비디오 포트        | 비디오 포트 범위    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | 문자열  | 50020-50039                    |
| 비디오 DSCP         | 비디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | 정수 | 34                             |
| 비디오 미디어 원본 | Skype 앱 이름      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | 문자열  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 두 표 모두 기본 포트 범위를 보여줍니다. 관리자는 비즈니스용 Skype 및 Teams 제어판에서 포트 범위를 변경할 수 있습니다.

## Microsoft Teams 모드 설정

Intune을 사용하여 Microsoft Teams 앱 모드를 설정할 수 있습니다. Surface Hub 2S는 Microsoft Teams와 비즈니스용 Skype를 모두 지원하는 모드 0에서 Microsoft Teams와 함께 설치됩니다. 아래 그림과 같이 모드를 조정할 수 있습니다.

### 모드:

- 모드 0 - 예약된 모임을 위한 Microsoft Teams 기능이 있는 비즈니스용 Skype
- 모드 1 - 예약된 모임을 위한 비즈니스용 Skype 기능이 있는 Microsoft Teams
- 모드 2 - Microsoft Teams 전용

모드를 설정하려면 사용자 지정 장치 구성 프로필에 다음 설정을 추가하세요.

|**이름**|**설명**|**OMA-URI**|**형식**|**값**|
|:--- |:--- |:--- |:--- |:--- |
|**Teams 앱 ID**|앱 이름|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|문자열| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 앱 모드**|Teams 모드|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|정수| 0 또는 1 또는 2|
