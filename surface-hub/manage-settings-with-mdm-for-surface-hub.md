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
ms.openlocfilehash: 4308ce1ea8ff382dc15706e68d2d706d0fd33f5f
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576758"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>MDM 공급자를 사용하여 Surface Hub 관리

Surface Hub 통해 IT 관리자는 MDM(모바일 장치 관리) 공급자를 사용하여 설정 및 정책을 관리할 수 Microsoft Intune. Surface Hub 서버와 통신하는 기본 제공 관리 구성 요소가 있습니다. 장치에 추가 클라이언트를 설치할 필요가 없습니다.

## <a name="enrolling-surface-hub-into-mdm-management"></a>MDM Surface Hub 등록 

수동 또는 자동 등록을 Microsoft Intune 또는 기타 MDM 공급자에 Surface를 등록할 수 있습니다.

### <a name="manual-enrollment"></a>수동 등록

1. 앱 **설정** 열고 로컬 관리자로 로그인합니다. 장치 **Surface Hub**  >  **관리를 선택한** 다음 **+장치 관리를 선택합니다.**
2. MDM 공급자에 사용할 계정으로 로그인하라는 메시지가 표시됩니다. 인증 후 장치가 MDM 공급자에 자동으로 등록됩니다.

> [!TIP]
> Intune을 사용 중일 때 서버 주소가 검색되지 않는 경우 를 **manage.microsoft.com.**
   
> [!NOTE]
> MDM 등록은 인증에 제공된 계정 세부 정보를 사용 합니다. 계정에는 Intune 라이선스(또는 타사 MDM 공급자에 구성된 동등한 등록 해제)뿐만 아니라 Windows 디바이스를 등록할 수 있는 권한이 있어야 합니다.

### <a name="auto-enrollment--azure-ad-affiliated"></a>자동 등록 - Azure AD 계열사

초기 설치 프로세스 중에 Intune 자동 등록이 Surface Hub AD(Azure Active Directory) 테넌트에 가입하면 장치가 자동으로 Intune에 등록됩니다. 자세한 내용은 디바이스에 [대한 Intune 등록 Windows 참조합니다.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods) Surface Hub가 Intune에서 "호환 장치"가 되려면 Azure AD에 연결과 Intune 자동 등록이 필요합니다. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Intune을 Surface Hub Windows 10 Team 설정 관리

Intune 및 기타 MDM 공급자의 정책 설정 관리의 기본 구성 블록은 XML 기반 OMA-DM(Open Mobile Alliance-Device Management) 프로토콜입니다. Windows 10 AccountManagement CSP, DeviceStatus CSP, WiFi-CSP와 같은 이름을 사용하여 사용 가능한 여러 CSP(구성 서비스 공급자) 중 하나를 통해 OMA-DM XML을 구현합니다. 전체 목록은 에서 지원되는 [CSP를 Microsoft Surface Hub.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)

Microsoft Intune 및 기타 MDM 공급자는 CSP를 사용하여 구성 프로필 내에서 정책 설정을 구성할 수 있는 UI를 제공합니다. Intune은 기본 제공 프로필인 Surface Hub CSP(장치 제한(Windows 10 Team)를 사용하여 사용자가 근접 범위 내에서 주변을 이동할 때마다 Surface Hub "깨어나는" 것을 방지하는 등의 기본 설정을 구성할 수 있습니다. **** Intune의 기본 제공 프로필 외부에서 허브 설정 및 기능을 관리하려면 아래와 같이 사용자 지정 프로필을 [사용해야 합니다.](#create-custom-configuration-profile) 

요약하면 Intune 내에서 정책 설정을 구성하고 관리하는 옵션은 다음과 같습니다. 
 
- **장치 제한 프로필을 생성합니다.** Intune의 기본 제공 프로필을 사용하여 Intune UI에서 직접 설정을 구성합니다. 장치 [제한 프로필 만들기를 참조하세요.](#create-device-restriction-profile)
- **장치 구성 프로필을 생성합니다.**  Microsoft Defender 또는 보안 인증서와 같은 특정 기능이나 기술에 중점을 두는 템플릿을 선택합니다. 장치 [구성 프로필 만들기를 참조하세요.](#create-device-configuration-profile)
- **사용자 지정 구성 프로필을 만들 수 있습니다.**  OMA URI(OMA Uniform Resource Identifier)를 사용하여 OMA URI에서 지원되는 [모든 CSP에서](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)관리 범위를 Microsoft Surface Hub. 사용자 [지정 구성 프로필 만들기를 참조하세요.](#create-custom-configuration-profile)

> [!NOTE]
> 등록된 디바이스가 포함된 디바이스 그룹에 프로필을 할당해야 Surface Hub 합니다.

## <a name="create-device-restriction-profile"></a>장치 제한 프로필 만들기

1. Microsoft Endpoint Manager [**로그인하고**](https://endpoint.microsoft.com/)장치 구성 프로필 ****  >  ****  >  **+** **프로필 만들기 를 선택합니다.**
2. 플랫폼 **아래에서**추가 **Windows 10 이상을 선택합니다.** >
3. Under ****Profile type **,** select **Templates** and then select **Device restrictions (Windows 10 Team)**
4. **만들기를**선택하고 이름을 추가한 후 다음을 **선택합니다.**
6. 이제 앱 및 환경, Azure 운영 Surface Hub, 유지 관리, 세션 및 무선 투영 범주에 대한 미리 설정된 장치 제한 설정을 찾아 선택할 수 있습니다. 다음 그림에 표시된 예제는 4시간의 유지 관리 기간과 화면, 절전 및 세션 다시 시작에 대한 15분의 시간 제한을 지정합니다.

     ![Intune Surface Hub 프로필을 사용하여 설정 구성](images/sh-device-restrictions.png)

프로필을 만들고 관리하는 데 대한 자세한 내용은 에서 정책을 사용하여 장치 기능 [제한을 Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile)
 
Surface Hub 기능과 설정을 관리하는 방법에 대한 자세한 내용은 Surface Hub Windows 10 Team 장치 제한을 [Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>장치 구성 프로필 만들기

1. Microsoft Endpoint Manager [**로그인하고**](https://endpoint.microsoft.com/)장치 구성 프로필 ****+ 프로필  >  ****  >  **만들기 를 선택합니다.**
2. 플랫폼 **아래에서**추가 **Windows 10 이상을 선택합니다.** >
3. 프로필 **유형에서** **템플릿을** 선택하고 지원되는 다음 템플릿 중 Surface Hub.

    - 이전 섹션에 설명된 Windows 10 Team(장치 제한 [사항)](#create-device-restriction-profile)
    - 끝점용 Microsoft Defender(Windows 10 데스크톱)
    - PKCS 인증서
    - PKCS에서 가져온 인증서
    - SCEP 인증서
    - 신뢰할 수 있는 인증서

## <a name="create-custom-configuration-profile"></a>사용자 지정 구성 프로필 만들기

에서 지원되는 모든 [](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) [CSP의](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)OMA URI를 사용하여 사용자 지정 프로필을 만들어 관리 범위를 확장할 Microsoft Surface Hub. CSP의 각 설정에는 Intune에서 사용자 지정 구성 프로필을 사용하여 설정할 수 있는 해당 OMA-URI가 있습니다. 지원되는 CSP에 대한 자세한 Surface Hub 다음 리소스를 참조할 수 있습니다. 

- [구성 서비스 공급자 참조](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub에서 지원되는 정책 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> [SurfaceHub CSP의](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) 설정을 사용하여 디바이스 계정을 관리하는 것은 현재 Intune에서 가능하지 않습니다. 타사 MDM 공급자를 사용할 필요는 없습니다.

CSP 기반 정책 설정을 구현하려면 먼저 OMA URI를 생성한 다음 Intune의 사용자 지정 구성 프로필에 추가합니다.

### <a name="generate-oma-uri-for-target-setting"></a>대상 설정에 대한 OMA URI 생성
 
모든 설정에 대한 OMA URI를 생성하는 경우:

1. [CSP 설명서에서](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)CSP의 루트 노드를 식별합니다. 일반적으로 이 모양은 **./Vendor/MSFT/ 입니다. <name of CSP> ** 
    - **예제:** [SurfaceHub CSP의](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) 루트 노드는 **./Vendor/MSFT/SurfaceHub입니다.**
2. 사용할 설정의 노드 경로를 확인합니다. 
    - **예제:** 무선 투영을 사용하도록 설정하는 설정의 노드 경로는 **InBoxApps/WirelessProjection/Enabled입니다.**
3. 루트 노드에 노드 경로를 추가하여 OMA URI를 생성합니다. 
    - **예제:** 무선 투영을 사용하도록 설정하는 설정의 OMA URI는 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled입니다.**
4. 데이터 형식은 CSP 설명서에서도 설명됩니다. 가장 일반적인 데이터 형식은 다음과 같습니다.
    - char(문자열)
    - int(정수)
    - bool(부울)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>사용자 지정 구성 프로필에 OMA URI 추가

1. 다음 Endpoint Manager 장치 **구성**  >  **프로필**  >  **프로필 만들기 를 선택합니다.**
2. 플랫폼에서 추가 **Windows 10 선택합니다.** 프로필에서 사용자 지정 **을**선택한 다음 만들기를 **선택합니다.**
3. 이름과 선택적 설명을 추가하고 다음을 **선택합니다.**
4. 구성 **설정**  >  **OMA-URI**설정 추가를 **선택합니다.**

  
## <a name="manage-specific-surface-hub-features"></a>특정 Surface Hub 관리

이 섹션에서는 Intune 또는 기타 MDM 공급자를 통해 관리할 수 있는 기능에 대한 정보를 중시합니다. 여기에는 다음이 포함됩니다.

- [QoS(서비스 품질)](#quality-of-service-settings)
- [Microsoft Teams 및 비즈니스용 Skype](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>서비스 품질 설정

비디오 및 오디오 품질을 최적화하려면 Surface Hub 다음 QoS 설정을 장치에 추가합니다. 

| 이름 | 설명 | OMA-URI | 형식 | 값 |
|:------ |:------------- |:--------- |:------ |:------- |
|**오디오 포트**| 오디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | 문자열  | 3478-3479 |
|**오디오 DSCP**| 오디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | 정수 | 46 |
|**비디오 포트**| 비디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | 문자열  | 3480 |
|**비디오 DSCP**| 비디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | 정수 | 34 |
|**공유 포트**| 공유 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | 문자열  | 3481 |
|**DSCP 공유**| 포트 표시 공유 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | 정수 | 18 |
|**P2P 오디오 포트**| 오디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | 문자열  | 50000-50019 |
|**P2P 오디오 DSCP**| 오디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | 정수 | 46 |
|**P2P 비디오 포트**| 비디오 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | 문자열  | 50020-50039 |
|**P2P 비디오 DSCP**| 비디오 포트 표시 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | 정수 | 34 |
|**P2P 공유 포트**| 공유 포트 범위 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | 문자열  | 50040-50059 |
|**P2P 공유 DSCP**| 포트 표시 공유 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | 정수 | 18 |


#### <a name="skype-for-business-qos-settings"></a>비즈니스용 Skype QoS 설정

| 이름                 | 설명           | OMA-URI                                                                    | 형식    | 값                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| 오디오 포트          | 오디오 포트 범위      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | 문자열  | 50000-50019                    |
| 오디오 DSCP           | 오디오 포트 표시   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | 정수 | 46                             |
| 오디오 미디어 원본   | Skype 앱 이름        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | 문자열  | Microsoft.PPISkype.Windows.exe |
| 비디오 포트          | 비디오 포트 범위      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | 문자열  | 50020-50039                    |
| 비디오 DSCP           | 비디오 포트 표시   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | 정수 | 34                             |
| 비디오 미디어 원본   | Skype 앱 이름        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | 문자열  | Microsoft.PPISkype.Windows.exe |
| 포트 공유        | 공유 포트 범위    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | 문자열  | 50040-50059                    |
| DSCP 공유         | 포트 표시 공유 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | 정수 | 18                             |
| 미디어 원본 공유 | Skype 앱 이름        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | 문자열  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 두 표 모두 기본 포트 범위를 보여줍니다. 관리자는 비즈니스용 Skype 및 Teams 제어판에서 포트 범위를 변경할 수 있습니다.

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams 및 비즈니스용 Skype 설정

사용자 지정 구성 프로필을 만들어 조정된 모임Teams 근접 참가 및 기타 기능을 관리할 수 있습니다. 자세한 내용은 [Manage Microsoft Teams configuration on Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

#### <a name="changing-default-business-communications-platform"></a>기본 비즈니스 통신 플랫폼 변경

Surface Hub 기본 비즈니스 통신 플랫폼은 Windows 10 Team 2020 Update(20H2라고도 Windows 10)를 설치하는 방법에 따라 다릅니다. 20H2로 Surface Hub 이미지를 Windows 10 경우 Microsoft Teams 사용 가능한 비즈니스용 Skype(모드 1)로 설정됩니다. 이전 OS 버전에서 허브를 업그레이드하는 경우 비즈니스용 Skype 기본으로 유지되는 것이고, Teams 기능을 사용할 수 있습니다(모드 0). 기본값으로 Teams. 

기본 설치를 변경하려면 다음과 같이 앱 [모드를](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) Teams 사용자 지정 프로필을 사용하세요.  

- 모드 0 - 예약된 모임을 위한 Microsoft Teams 기능이 있는 비즈니스용 Skype
- 모드 1 - 예약된 모임을 위한 비즈니스용 Skype 기능이 있는 Microsoft Teams
- 모드 2 - Microsoft Teams 전용

| 이름 | 설명 | OMA-URI | 형식 | 값 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 앱 ID**|앱 이름|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|문자열| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 앱 모드**|Teams 모드|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|정수| 0 또는 1 또는 2|










