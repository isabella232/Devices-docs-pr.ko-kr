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
ms.date: 07/23/2020
ms.localizationpriority: Medium
ms.openlocfilehash: a031fd7fd861e5d45194ec1a8c391621a2bcb71a
ms.sourcegitcommit: 5fa5efefd510ce6f435d7142fb2f2cc08b520da9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078748"
---
# Intune으로 Surface Hub 2S 관리하기

## Intune으로 Surface Hub 2S 등록하기

Surface Hub 2S에서는 IT 관리자가 MDM(모바일 장치 관리) 공급자를 사용하여 설정 및 정책을 관리할 수 있습니다. Surface Hub 2S에는 관리 서버와 통신하는 기본 제공 관리 구성 요소가 있어서 장치에 추가 클라이언트를 설치할 필요가 없습니다.

### 수동 등록

1. Surface Hub 2S에서 **설정** 앱을 열고 로컬 관리자로 로그인 합니다. **Surface Hub** > **장치 관리**를 선택한 다음 **+** 를 선택하여 추가합니다.
2. Intune에서 사용할 계정으로 로그인 하 라는 메시지가 표시 됩니다. 인증 후 장치는 자동으로 Intune에 등록됩니다.

   ![Intune으로 Surface Hub 2S 등록하기](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> 인증에 사용 되는 계정은 Intune 등록 계정이 며 Intune에 대해 사용이 허가 되어야 합니다.

### 자동 등록 - Azure Active Directory 연결

초기 설정 프로세스 중에 Intune 자동 등록이 설정된 Azure AD 테넌트로 Surface Hub를 연결하는 경우 장치가 자동으로 Intune에 등록됩니다. 자세한 내용은 [Windows 장치에 대한 Intune 등록 방법](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)을 참조하세요. Surface Hub가 Intune에서 "호환 장치"가 되려면 Azure AD에 연결과 Intune 자동 등록이 필요합니다. 

## Intune을 사용 하 여 Windows 10 팀 설정 관리

1. **Microsoft Endpoint Manager**에 로그인 하 고 **장치**  >  **구성 프로필**을 선택 하 여  >  **프로필을 만듭니다**. 
2. **플랫폼**에서 **windows 10 이상**  >  **장치 제한 (windows 10 팀)** 을 선택 하 고 **만들기**를 선택 합니다. 
3. 이제 Surface Hub 및 Surface Hub 2S에 대해 미리 설정 된 장치 제한 설정을 찾아 선택할 수 있습니다.

 ![Surface Hub 2S에 대한 장치 제한을 설정합니다.](images/sh2-set-intune3.png) <br>

이러한 설정에는 앱과 환경, Azure operational insights, 유지 관리, 세션, 무선 프로젝션이 범주로 분류 됩니다.  

## 지원 되는 Csp (구성 서비스 공급자)

Intune 콘솔을 통해 직접 사용할 수 있는 정책 외에도 레지스트리 키 또는 파일에 매핑되는 다양 한 Csp (구성 서비스 공급자)가 있습니다. 

Microsoft는 일반적으로 새 Windows 10 운영 체제 버전 마다 새로운 Csp를 제공 합니다. Windows 참가자 프로그램을 통해 미리 보기에서 사용할 수 있는 [windows 10 Team 2020 업데이트](surface-hub-install-2020preview.md)에는 surface Hub 및 Surface hub 2S에 대 한 20 개 이상의 새로운 장치 관리 정책 및 업데이트 됨이 포함 되어 있습니다. 이러한 MDM 정책을 통해 관리자는 Microsoft Store, 인프라를 통해 Miracast, 802.1 x 유선 인증, 새로운 개인 정보/GDPR 관련 설정 등의 무선 프로젝션 설정에서 앱 업데이트를 더욱 효율적으로 제어할 수 있습니다.

자세한 내용은 다음 리소스를 참조하세요. 

- [구성 서비스 공급자 참조](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Microsoft Surface Hub에서 지원되는 정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)

## QoS(서비스 품질) 설정

Surface Hub 2S에서 최적의 비디오 및 오디오 품질을 보장하려면 장치에 다음 QoS 설정을 추가하세요. 

### Microsoft Teams QoS 설정 

| 이름 | 설명 | OMA-URI | 형식 | 값 |
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

| 이름 | 설명 | OMA-URI | 형식 | 값 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 앱 ID**|앱 이름|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|문자열| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 앱 모드**|Teams 모드|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|정수| 0 또는 1 또는 2|
