---
title: MDM 공급자 설정 관리(Surface Hub)
description: Microsoft Surface Hub는 IT 관리자가 MDM(모바일 디바이스 관리) 솔루션을 사용하여 이러한 디바이스의 정책 및 비즈니스 응용 프로그램을 관리하도록 도와주는 엔터프라이즈 관리 솔루션을 제공합니다.
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: 모바일 디바이스 관리, MDM, 관리 정책
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: e126799fe023d97468e58c01b003ce4b605f2db7
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497791"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>MDM 공급자를 사용하여 Surface Hub 관리

Surface Hub 통해 IT 관리자는 Microsoft Intune 같은 MDM(모바일 디바이스 관리) 공급자를 사용하여 설정 및 정책을 관리할 수 있습니다. Surface Hub 관리 서버와 통신할 수 있는 기본 제공 관리 구성 요소가 있습니다. 디바이스에 추가 클라이언트를 설치할 필요가 없습니다.

## <a name="enrolling-surface-hub-into-mdm-management"></a>MDM 관리에 Surface Hub 등록 

수동 또는 자동 등록을 통해 Surface를 Microsoft Intune 또는 다른 MDM 공급자에 등록할 수 있습니다.

### <a name="manual-enrollment"></a>수동 등록

1. **설정** 앱을 열고 로컬 관리자로 로그인합니다. **Surface Hub** > **관리**를 선택한 다음 **+ 디바이스 관리를** 선택합니다.
2. MDM 공급자에 사용할 계정으로 로그인하라는 메시지가 표시됩니다. 인증 후 디바이스는 MDM 공급자에 자동으로 등록됩니다.

> [!TIP]
> Intune 사용 중이고 서버 주소가 검색되지 않으면 **manage.microsoft.com** 입력합니다.
   
> [!NOTE]
> MDM 등록은 인증에 제공된 계정 세부 정보를 사용합니다. 계정에는 Windows 디바이스와 Intune 라이선스(또는 타사 MDM 공급자에 구성된 동등한 등록 권한)를 등록할 수 있는 권한이 있어야 합니다.

### <a name="auto-enrollment--azure-ad-affiliated"></a>자동 등록 - Azure AD 관련

초기 설정 프로세스 중에 자동 등록을 사용하도록 설정된 Intune AD(Azure Active Directory) 테넌트와 Surface Hub 연결하면 디바이스가 자동으로 Intune 등록됩니다. 자세한 내용은 [Windows 디바이스에 대한 Intune 등록 방법을 참조하세요](/intune/enrollment/windows-enrollment-methods). Surface Hub가 Intune에서 "호환 장치"가 되려면 Azure AD에 연결과 Intune 자동 등록이 필요합니다. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Intune 사용하여 Surface Hub Windows 10 Team 설정 관리

Intune 및 기타 MDM 공급자의 정책 설정 관리의 기본 구성 요소는 XML 기반 OMA-DM(Open Mobile Alliance-Device Management) 프로토콜입니다. Windows AccountManagement CSP, DeviceStatus CSP, WiFi-CSP 등의 이름으로 사용 가능한 여러 CSP(구성 서비스 공급자) 중 하나를 통해 OMA-DM XML을 구현합니다. 전체 목록은 [Microsoft Surface Hub 지원되는 CSP를](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) 참조하세요.

Microsoft Intune 및 기타 MDM 공급자는 CSP를 사용하여 구성 프로필 내에서 정책 설정을 구성할 수 있는 UI를 제공합니다. Intune 기본 제공 프로필인 **디바이스 제한(Windows 10 Team)에 Surface Hub** CSP를 사용하여 근접 범위 내에서 근처로 이동할 때마다 Surface Hub "깨어나지 않도록" 방지하는 등의 기본 설정을 구성할 수 있습니다. Intune 기본 제공 프로필 외부에서 허브 설정 및 기능을 관리하려면 [아래와](#create-custom-configuration-profile) 같이 사용자 지정 프로필을 사용해야 합니다. 

요약하자면, Intune 내에서 정책 설정을 구성하고 관리하는 옵션은 다음과 같습니다. 
 
- **디바이스 제한 프로필을 만듭니다.** Intune 기본 제공 프로필을 사용하고 Intune UI에서 직접 설정을 구성합니다. [디바이스 제한 프로필 만들기](#create-device-restriction-profile)를 참조하세요.
- **디바이스 구성 프로필을 만듭니다.**  Microsoft Defender 또는 보안 인증서와 같은 특정 기능 또는 기술에 초점을 맞춘 템플릿을 선택합니다. [디바이스 구성 프로필 만들기](#create-device-configuration-profile)를 참조하세요.
- **사용자 지정 구성 프로필을 만듭니다.**  [Microsoft Surface Hub 지원되는 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)에서 OMA URI(Uniform Resource Identifier)를 사용하여 관리 범위를 확장합니다. [사용자 지정 구성 프로필 만들기](#create-custom-configuration-profile)를 참조하세요.

> [!NOTE]
> 등록된 Surface Hub 디바이스를 포함하는 디바이스 그룹에 프로필을 할당해야 합니다.

## <a name="create-device-restriction-profile"></a>디바이스 제한 프로필 만들기

1. [**Microsoft Endpoint Manager 관리 센터에**](https://endpoint.microsoft.com/) 로그인하고 **DevicesConfiguration****** >  프로필 **만들기 프로필을** > **+** 선택합니다.
2. **플랫폼** 아래에서 **Windows 10 이상을** 선택합니다. >
3. ******프로필 유형에서** **템플릿을** 선택한 다음 **, 디바이스 제한(Windows 10 Team)을** 선택합니다.
4. **만들기**를 선택하고 이름을 추가한 다음 다음을 선택합니다 **.**
6. 이제 앱 및 환경, Azure 운영 인사이트, 유지 관리, 세션 및 무선 프로젝션 범주에서 Surface Hub 대한 미리 설정된 디바이스 제한 설정을 찾아 선택할 수 있습니다. 다음 그림에 표시된 예제는 화면, 절전 모드 및 세션 다시 시작에 대한 4시간 유지 관리 기간 및 15분의 시간 제한을 지정합니다.

     ![Intune 디바이스 제한 프로필을 사용하여 Surface Hub 설정을 구성합니다.](images/sh-device-restrictions.png)

프로필을 만들고 관리하는 방법에 대한 자세한 내용은 [Microsoft Intune 정책을 사용하여 디바이스 기능 제한을](/mem/intune/configuration/device-restrictions-configure#create-the-profile) 참조하세요.
 
Surface Hub 기능 및 설정을 관리하는 방법에 대한 자세한 내용은 [Intune 사용하여 Surface Hub 기능을 허용하거나 제한하는 Windows 10 Team 설정을](/mem/intune/configuration/device-restrictions-windows-10-teams) 참조하세요.
 

## <a name="create-device-configuration-profile"></a>디바이스 구성 프로필 만들기

1. [**Microsoft Endpoint Manager 관리 센터에**](https://endpoint.microsoft.com/) 로그인하고 **DevicesConfiguration****** >  프로필 **+ 프로필 만들기**를  >  선택합니다.
2. **플랫폼** 아래에서 **Windows 10 이상을** 선택합니다. >
3. **프로필 유형**에서 **템플릿을** 선택하고 Surface Hub 지원되는 다음 템플릿 중에서 선택합니다.

    - [이전 섹션에서](#create-device-restriction-profile) 설명한 대로 디바이스 제한(Windows 10 Team)입니다.
    - 엔드포인트용 Microsoft Defender(Windows 10 Desktop)
    - PKCS 인증서
    - PKCS 가져온 인증서
    - SCEP 인증서
    - 신뢰할 수 있는 인증서

## <a name="create-custom-configuration-profile"></a>사용자 지정 구성 프로필 만들기

[Microsoft Surface Hub 지원되는 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)에서 OMA URI를 사용하여 [사용자 지정 프로필을 만들어](/mem/intune/configuration/custom-settings-configure) 관리 범위를 확장할 수 있습니다. CSP의 각 설정에는 Intune 사용자 지정 구성 프로필을 사용하여 설정할 수 있는 해당 OMA-URI가 있습니다. Surface Hub 지원하는 CSP에 대한 자세한 내용은 다음 리소스를 참조할 수 있습니다. 

- [구성 서비스 공급자 참조](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub에서 지원되는 정책 CSP](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)의 설정을 사용하여 디바이스 계정을 관리하는 것은 현재 Intune 사용할 수 없으며 타사 MDM 공급자를 사용해야 합니다.

CSP 기반 정책 설정을 구현하려면 먼저 OMA URI를 생성한 다음 Intune 사용자 지정 구성 프로필에 추가합니다.

### <a name="generate-oma-uri-for-target-setting"></a>대상 설정에 대한 OMA URI 생성
 
모든 설정에 대한 OMA URI를 생성하려면 다음을 수행합니다.

1. [CSP 설명서에서 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)의 루트 노드를 식별합니다. 일반적으로 **./Vendor/MSFT/NameOfCSP**와 같습니다. 
    - **예제:** [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) 의 루트 노드는 **./Vendor/MSFT/SurfaceHub**입니다.
2. 사용할 설정의 노드 경로를 확인합니다. 
    - **예제:** 무선 프로젝션을 사용하도록 설정하는 설정의 노드 경로는 **InBoxApps/WirelessProjection/Enabled**입니다.
3. 루트 노드에 노드 경로를 추가하여 OMA URI를 생성합니다. 
    - **예제:** 무선 프로젝션을 사용하도록 설정하는 설정의 OMA URI는 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled입니다.**
4. 데이터 형식은 CSP 설명서에서도 설명됩니다. 가장 일반적인 데이터 형식은 다음과 같습니다.
    - char(문자열)
    - int(정수)
    - bool(부울)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>사용자 지정 구성 프로필에 OMA URI 추가

1. Endpoint Manager **DevicesConfiguration****** >  **profilesCreate** >  프로필을 선택합니다.
2. 플랫폼에서 **Windows 10 이상을 선택합니다.** 프로필에서 **사용자 지정**을 선택한 다음 만들기를 선택합니다 **.**
3. 이름 및 선택적 설명을 추가한 다음 다음을 선택합니다 **.**
4. **구성 설정** > **OMA-URI 설정** 아래에서 **추가**를 선택합니다.

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams 및 비즈니스용 Skype 설정

이 섹션에서는 Intune 또는 다른 MDM 공급자를 통해 관리할 수 있는 Teams 및 비즈니스용 Skype 설정을 강조 표시합니다. 여기에는 다음이 포함됩니다.

- [QoS(서비스 품질)](#quality-of-service-settings)
- [Teams 관련 기능 관리](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>서비스 품질 설정

Surface Hub 최적의 비디오 및 오디오 품질을 보장하려면 다음 QoS 설정을 디바이스에 추가합니다. 

| 이름                 | 설명           | OMA-URI                                                                 | 형식    | 값                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| 오디오 포트          | 오디오 포트 범위      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | 문자열  | 50000-50019                    |
| 오디오 DSCP           | 오디오 포트 표시   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | 정수 | 46                             |
| 비디오 포트          | 비디오 포트 범위      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | 문자열  | 50020-50039                    |
| 비디오 DSCP           | 비디오 포트 표시   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | 정수 | 34                             |
| 공유 포트        | 공유 포트 범위    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | 문자열  | 50040-50059                    |
| DSCP 공유         | 공유 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | 정수 | 18                             |

> [!NOTE]
> 표에는 기본 포트 범위가 표시됩니다. 관리자는 비즈니스용 Skype 및 Teams 제어판에서 포트 범위를 변경할 수 있습니다.

### <a name="manage-teams-specific-features"></a>Teams 관련 기능 관리

사용자 지정 구성 프로필을 만들어 Teams 조정된 모임, 근접 참가 및 기타 기능을 관리할 수 있습니다. 자세한 내용은 [Surface Hub Microsoft Teams 구성 관리를](/microsoftteams/rooms/surface-hub-manage-config) 참조하세요.

### <a name="changing-default-app-for-meetings--calls"></a>모임 & 통화에 대한 기본 앱 변경

Surface Hub 대한 모임 & 통화의 기본 앱은 Windows 10 Team 2020 업데이트(즉, Windows 10 20H2 Team Edition)를 설치하는 방법에 따라 달라집니다. Surface Hub Windows 10 20H2로 다시 이미지화하면 Microsoft Teams 기본값으로 설정되며 비즈니스용 Skype 사용할 수 없습니다(모드 1). 이전 OS 버전에서 허브를 업그레이드하는 경우 Teams 기본값으로 이미 구성하지 않은 경우 Teams 기능을 사용할 수 있는(모드 0) 비즈니스용 Skype 기본값으로 유지됩니다. 

기본 설치를 변경하려면 [사용자 지정 프로필을](/mem/intune/configuration/custom-settings-configure) 사용하여 다음과 같이 Teams 모임 모드를 설정합니다.  

- 모드 0 - 예약된 모임을 위한 Microsoft Teams 기능이 있는 비즈니스용 Skype
- 모드 1 - Microsoft Teams 전용입니다.

| 이름 | 설명 | OMA-URI | 형식 | 값 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 앱 ID**|앱 이름|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|문자열| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 앱 모드**|Teams 모드|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|정수| 0 또는 1|


