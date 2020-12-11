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
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6b5dac9f418207293e3b9b386d59fd26762feb72
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206302"
---
# Intune으로 Surface Hub 2S 관리하기

## Intune으로 Surface Hub 2S 등록하기

Surface Hub 2S에서는 IT 관리자가 MDM(모바일 장치 관리) 공급자를 사용하여 설정 및 정책을 관리할 수 있습니다. Surface Hub 2S에는 관리 서버와 통신하는 기본 제공 관리 구성 요소가 있어서 장치에 추가 클라이언트를 설치할 필요가 없습니다.

### 수동 등록

1. Surface **** Hub 2S에서 설정 앱을 열고 로컬 관리자로 로그인합니다. **Surface Hub** > **장치 관리**를 선택한 다음 **+** 를 선택하여 추가합니다.
2. Intune에 사용할 계정으로 로그인하라는 메시지가 표시됩니다. 인증 후 장치는 자동으로 Intune에 등록됩니다.

   ![Intune으로 Surface Hub 2S 등록하기](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> 인증에 사용되는 계정은 Intune 등록 계정이 되어야 하며 Intune에 대한 라이선스가 있어야 합니다.

### 자동 등록 - Azure Active Directory 연결

초기 설정 프로세스 중에 Intune 자동 등록이 설정된 Azure AD 테넌트로 Surface Hub를 연결하는 경우 장치가 자동으로 Intune에 등록됩니다. 자세한 내용은 [Windows 장치에 대한 Intune 등록 방법](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)을 참조하세요. Surface Hub가 Intune에서 "호환 장치"가 되려면 Azure AD에 연결과 Intune 자동 등록이 필요합니다. 

## Intune을 사용하여 Windows 10 Team 설정 관리

1. Microsoft **Endpoint Manager에 로그인하고** **장치 구성**  >  **프로필 만들기**  >  **프로필을 선택합니다.** 
2. 플랫폼에서 **Windows 10 이상**장치 ****  >  **제한(Windows 10 Team)을** 선택한 다음 만들기를 **선택합니다.** 
3. 이제 Surface Hub 및 Surface Hub 2S에 대한 미리 설정한 장치 제한 설정을 찾아 선택할 수 있습니다.

 ![Surface Hub 2S에 대한 장치 제한을 설정합니다.](images/sh2-set-intune3.png) <br>

이러한 설정은 앱 및 환경, Azure 운영 인사이트, 유지 관리, 세션 및 무선 투영 범주에 걸쳐 있습니다.  

## 지원되는 CSP(구성 서비스 공급자)

Intune 콘솔을 통해 직접 사용할 수 있는 정책 외에도 레지스트리 키 또는 파일에 매핑되는 다양한 CSP(구성 서비스 공급자)가 있습니다. 

Microsoft는 일반적으로 각 새 버전의 Windows 10 운영 체제와 함께 새 CSP를 제공합니다. [Windows 10 Team 2020 업데이트에는](surface-hub-2020-update.md) Surface Hub 및 Surface Hub 2S에 대한 20개 이상의 신규 및 업데이트된 장치 관리 정책이 포함되어 있습니다. 이러한 MDM 정책을 통해 IT 관리자는 Microsoft Store의 앱 업데이트, 인프라를 통해 Miracast와 같은 무선 투영 설정, 네트워크 설정(예: 서비스 품질 및 802.1x 유선 인증) 및 새로운 개인 정보/GDPR 관련 설정을 제어할 수 있습니다.

자세한 내용은 다음 리소스를 참조하세요. 

- [구성 서비스 공급자 참조](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Microsoft Surface Hub에서 지원되는 정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Surface Hub Team 2020 업데이트의 새로운](surface-hub-2020-update-whats-new.md)

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

## Microsoft Teams 설정

Intune을 사용하여 다양한 Microsoft Teams 설정을 구성할 수 있습니다.

### 모드

Surface Hub 2S는 Microsoft Teams와 비즈니스용 Skype를 모두 지원하는 모드 0에서 Microsoft Teams와 함께 설치됩니다. 모드는 아래 설명과 같이 기능합니다.

- 모드 0 - 예약된 모임을 위한 Microsoft Teams 기능이 있는 비즈니스용 Skype
- 모드 1 - 예약된 모임을 위한 비즈니스용 Skype 기능이 있는 Microsoft Teams
- 모드 2 - Microsoft Teams 전용

모드를 조정하려면 사용자 지정 장치 구성 프로필에 다음 [설정을 추가합니다.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| 이름 | 설명 | OMA-URI | 형식 | 값 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 앱 ID**|앱 이름|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|문자열| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 앱 모드**|Teams 모드|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|정수| 0 또는 1 또는 2|

### 조정된 모임 및 근접 참가

Teams 협정 모임 및 근접 참가 기능은 Intune 프로필을 통해 배포된 [XML](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) 파일을 통해 구성할 수 있습니다.
