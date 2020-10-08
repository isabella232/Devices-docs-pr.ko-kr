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
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: 2bee8b58b7978923c6e60e43f9e10a85dc4bec06
ms.sourcegitcommit: 17170c03206d190851b5f8e794fcc83ebbed7b5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103904"
---
# MDM 공급자 설정 관리(Surface Hub)

Surface Hub 및 기타 Windows10 디바이스에서는 IT 관리자가 MDM(모바일 디바이스 관리) 공급자를 사용하여 설정 및 정책을 관리할 수 있습니다. 기본 제공 관리 구성 요소는 관리 서버와 통신하므로 디바이스에 추가 클라이언트를 설치할 필요가 없습니다. For more information, see [Windows 10 mobile device management](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx).

Surface Hub has been validated with Microsoft's first-party MDM providers:
- Microsoft Intune standalone
- On-premises MDM with Microsoft Endpoint Configuration Manager

You can also manage Surface Hubs using any third-party MDM provider that can communicate with Windows 10 using the MDM protocol.

## <a href="" id="enroll-into-mdm"></a>Enroll a Surface Hub into MDM
You can enroll your Surface Hubs using bulk, manual, or automatic enrollment.

### Bulk enrollment
**대량 등록을 구성하려면**
- Surface Hub는 MDM에 대한 대량 등록을 위해 [프로비저닝 CSP](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx)를 지원합니다. 자세한 내용은 [Windows10 대량 등록](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx)을 참조하세요.<br>
--OR--
- If you have an on-premises Microsoft Endpoint Configuration Manager infrastructure, see [How to bulk enroll devices with On-premises Mobile Device Management in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### Manual enrollment
**수동 등록을 구성하려면**
1. Surface Hub에서 **설정**을 엽니다.
2. 메시지가 표시되면 디바이스 관리자 자격 증명을 입력합니다.
3. **이 장치**를 선택하고 **장치 관리**로 이동합니다.
4. **장치 관리**에서 **+ 장치 관리**를 선택합니다.
5. Follow the instructions in the dialog to connect to your MDM provider.

### Automatic enrollment via Azure Active Directory join

Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory. 

First step is to set up Automatic MDM enrollment. See [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

Then, when devices are setup during First-run, pick the option to join to Azure Active Directory, see [Set up admins for this device page](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## Manage Surface Hub settings with MDM

MDM을 사용하여 일부 [Surface Hub CSP 설정](#supported-surface-hub-csp-settings) 및 일부 [Windows10 설정](#supported-windows-10-settings)을 관리할 수 있습니다. Depending on the MDM provider that you use, you may set these settings using a built-in user interface, or by deploying custom SyncML. Microsoft Intune and Microsoft Endpoint Configuration Manager provide built-in experiences to help create policy templates for Surface Hub. Refer to documentation from your MDM provider to learn how to create and deploy SyncML.

### 지원되는 Surface Hub CSP 설정

You can configure the Surface Hub settings in the following table using MDM. The table identifies if the setting is supported with Microsoft Intune, Microsoft Endpoint Configuration Manager, or SyncML.

For more information, see [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     설정                                      |                                                    SurfaceHub CSP의 노드                                                    |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                유지 관리 시간                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       예                        |                       예                       |             예             |
|              동작 센서를 사용하여 자동으로 화면 켜기               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       예                        |                       예                       |             예             |
|                      무선으로 다른 화면에 표시할 때 PIN 필요                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       예                        |                       예                       |             예             |
|                            무선 프로젝션 사용                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       예                        | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                 무선 프로젝션에 사용할 Miracast 채널                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       예                        | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|              Operations Management Suite 작업 영역에 연결               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       예                        | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                         시작 화면 배경 이미지                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       예                        | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               시작 화면에 표시되는 모임 정보                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       예                        | Yes.<br> [Use a custom setting.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager |             Yes             |
|                      무선 프로젝션의 이름                       |                                                     Properties/FriendlyName                                                      | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|                   Device account                                                 | DeviceAccount/*`<name_of_policy>`* <br> [SurfaceHub CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)를 참조하세요. |                        아니요                        |                       아니오                        |             예             |
|                               Skype 도메인 지정                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               프로젝션이 시작되면 연결 앱 자동 시작               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                                기본 볼륨 설정                                |                                                     Properties/DefaultVolume                                                     |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                                화면 시간 제한 설정                                |                                                     Properties/ScreenTimeout                                                     |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                               세션 시간 제한 설정                                |                                                    Properties/SessionTimeout                                                     |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                                절전 모드 시간 제한 설정                                 |                                                     Properties/SleepTimeout                                                      |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                   화면 유휴 상태 후 세션 다시 시작 허용                   |                                                  Properties/AllowSessionResume                                                   |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|             프록시 인증에 장치 계정 사용 허용             |                                                  Properties/AllowAutoProxyAuth                                                   |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
| 예약된 모임의 초대 대상자와 함께 로그인 대화 상자 자동 채우기 사용 안 함 |                                               Properties/DisableSignInSuggestions                                                |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|              시작 메뉴에서 "내 모임 및 파일" 기능 사용 안 함               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    예 </br>                     | 예.<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                     802.1x 유선 인증용 LanProfile 설정                     |                                                         Dot3/LanProfile                                                          | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                    802.1x 유선 인증용 EapUserData 설정                     |                                                         Dot3/EapUserData                                                         | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

### 지원되는 Windows 10 설정

Surface Hub 관련 설정과 함께 모든 Windows10 장치에 공통적인 많은 설정이 있습니다. 이러한 설정은 [구성 서비스 공급자 참조](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)에서 정의됩니다. 

다음 표에는 Surface Hub에서 유효성이 검사된 Windows10 설정의 정보가 포함됩니다. There is a table with settings for these areas: security, browser, Windows Updates, Windows Defender, remote reboot, certificates, and logs. Each table identifies if the setting is supported with Microsoft Intune, Microsoft Endpoint Configuration Manager, or SyncML.

#### Security settings

|      설정       |                                            세부 정보                                             |                                                                          CSP 참조                                                                           |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Allow Bluetooth(Bluetooth 허용)   |                      Bluetooth 주변 장치를 지원하려면 이 설정을 사용으로 유지하세요.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    예 <br>                     | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
| Bluetooth 정책 | Bluetooth 장치 이름을 설정하고 광고, 검색 및 자동 페어링을 차단하는 데 사용합니다. |                     Bluetooth/*`<name of policy>`* <br> [정책 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)를 참조하세요.                      |                    예 <br>                     | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|    카메라 허용    |                           비즈니스용 Skype의 경우 이 설정을 사용으로 유지하세요.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    예 <br>                     | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|   위치 허용   |                        지도와 같은 앱을 지원하려면 이 설정을 사용으로 유지하세요.                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   예 <br> .                    | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|  원격 분석 허용   |                    Microsoft가 Surface Hub를 개선하도록 지원하려면 이 설정을 사용으로 유지하세요.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    예 <br>                     | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|  USB 드라이브 허용  |                     Surface Hub에서 USB 드라이브를 지원하려면 이 설정을 사용으로 유지하세요.                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다. 

#### 브라우저 설정

|                          설정                          |                                                                        세부 정보                                                                        |                                                                             CSP 참조                                                                              |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         홈페이지                         |                                               Microsoft Edge에서 기본 홈페이지를 구성하는 데 사용합니다.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                       쿠키 허용                       |                    Surface Hub는 세션 종료 시 쿠키를 자동으로 삭제합니다. 세션 내에서 쿠키를 차단하는 데 사용합니다.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                   개발자 도구 허용                   |                                                   사용자가 F12 개발자 도구를 사용하지 못하게 중지하는 데 사용합니다.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                    Do Not Track 허용                     |                                                          Do Not Track 헤더를 사용하도록 설정하는 데 사용합니다.                                                          |                          [브라우저/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                       팝업 허용                       |                                                         팝업 브라우저 창을 차단하는 데 사용합니다.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|                 검색 제안 허용                  |                                                  주소 표시줄에서 검색 제안을 차단하는 데 사용합니다.                                                  |       [브라우저/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|                     Allow Windows Defender SmartScreen                     |                                                       Keep this enabled to turn on Windows Defender SmartScreen.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
| Prevent ignoring Windows Defender SmartScreen warnings for websites |     For extra security, use to stop users from ignoring Windows Defender SmartScreen warnings and block them from accessing potentially malicious websites.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Yes             |
|  Prevent ignoring Windows Defender SmartScreen warnings for files   | For extra security, use to stop users from ignoring Windows Defender SmartScreen warnings and block them from downloading unverified files from Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### Windows 업데이트 설정

|                      설정                      |                                                                                                           세부 정보                                                                                                            |                                                                    CSP 참조                                                                    |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Use Current Branch or Current Branch for Business |                                                       비즈니스용 Windows 업데이트를 구성하는 데 사용합니다. [Windows 업데이트](manage-windows-updates-for-surface-hub.md)를 참조하세요.                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               기능 업데이트 지연               |                                                                                                          위의 내용을 참조하세요.                                                                                                          | [Update/DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               품질 업데이트 지연               |                                                                                                          위의 내용을 참조하세요.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               기능 업데이트 일시 중지               |                                                                                                          위의 내용을 참조하세요.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               품질 업데이트 일시 중지               |                                                                                                          위의 내용을 참조하세요.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|           WSUS를 사용하도록 장치 구성            |                                            Windows 업데이트 대신 WSUS에 Surface Hub를 연결하는 데 사용합니다. [Windows 업데이트](manage-windows-updates-for-surface-hub.md)를 참조하세요.                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|               배달 최적화               | 피어 투 피어 콘텐츠 공유를 사용하여 업데이트 중에 대역폭 문제를 줄입니다. 자세한 내용은 [Windows10 업데이트에 맞게 업데이트 배달 최적화 구성](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization)을 참조하세요. |         DeliveryOptimization/*`<name of policy>`* <br> [정책 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)를 참조하세요.          | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### Windows Defender 설정

|      설정      |                                              세부 정보                                               |                                                     CSP 참조                                                      |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Defender policies(Defender 정책) |            예약된 검사 시간을 포함하여 다양한 Defender 설정을 구성하는 데 사용합니다.            | Defender/*`<name of policy>`* <br> [정책 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)를 참조하세요. | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
|  Defender status  | Use to initiate a Defender scan, force a Security intelligence update, query any threats detected. |                   [Defender CSP](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Yes                        |                       예                       |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### 원격 다시 시작

|                       설정                        |                                                          세부 정보                                                          |                                                             CSP 참조                                                             |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Reboot the device immediately(즉시 디바이스 다시 시작)             | OMS와 함께 지원 비용을 최소화하는 데 사용합니다. [Microsoft Surface Hub 모니터링](monitor-surface-hub.md)을 참조하세요. |        ./Vendor/MSFT/Reboot/RebootNow <br> [CSP 재부팅](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)을 참조하세요.        |                       예                        |                       아니오                        |             예             |
|    Reboot the device at a scheduled date and time(예약된 날짜 및 시간에 디바이스 다시 시작)    |                                                        위의 내용을 참조하세요.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> [다시 시작 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)를 참조하세요.     | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |
| 매일 예약된 날짜 및 시간에 장치 다시 시작 |                                                        위의 내용을 참조하세요.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> [다시 시작 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)를 참조하세요. | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### 인증서 설치

|             설정             |                           세부 정보                            |                                           CSP 참조                                            |                                                         지원 여부:<br>Intune                                                          |                                                                  지원 여부:<br>Configuration Manager                                                                  | 지원 여부:<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Install trusted CA certificates(신뢰할 수 있는 CA 인증서 설치) | 신뢰할 수 있는 루트 및 중간 CA 인증서를 배포하는 데 사용합니다. | [RootCATrustedCertificates CSP](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | 예. <br> [Intune 인증서 프로필 구성](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)을 참조하세요. | Yes. <br> See [How to create certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Yes             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### 로그 수집

|     설정      |                      세부 정보                       |                                     CSP 참조                                      | 지원 여부:<br>Intune | 지원 여부:<br>Configuration Manager | 지원 여부:<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Collect ETW logs | Surface Hub에서 ETW 로그를 원격으로 수집하는 데 사용합니다. | [DiagnosticLog CSP](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            아니요             |                    아니오                    |             예             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### 네트워크 QoS(서비스 품질) 정책 설정

|        설정         |                                                            세부 정보                                                             |                                                    CSP 참조                                                     |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Set Network QoS Policy | 네트워크 트래픽에서 작업 집합을 수행하기 위해 QoS 정책을 설정하는 데 사용합니다. Skype 네트워크 패킷의 우선 순위를 정하는 데 유용합니다. | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### 네트워크 프록시 설정

|      설정      |                               세부 정보                               |                                                CSP 참조                                                 |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Set Network proxy | 이더넷과 Wi-Fi 연결을 위한 프록시 서버를 구성하는 데 사용됩니다. | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비전 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

#### 시작 메뉴 구성

|       설정        |                                                                       세부 정보                                                                        |                                                        CSP 참조                                                         |            지원 여부:<br>Intune             |    지원 여부:<br>Configuration Manager     | 지원 여부:<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Configure Start menu | 시작 메뉴에 표시될 앱을 구성하는 데 사용됩니다. 자세한 내용은 [Surface Hub 시작 메뉴 구성](surface-hub-start-menu.md)을 참조하세요. | [정책 CSP: 시작/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | 예 <br> [사용자 지정 정책을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-intune) | 예<br> [사용자 지정 설정을 사용합니다.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             예             |

\*Windows 구성 디자이너 프로비저닝 패키지를 통해 SyncML에서 지원되는 설정을 구성할 수도 있습니다.

### Generate OMA URIs for settings 
You need to use a setting's OMA URI to create a custom policy in Intune, or a custom setting in Microsoft Endpoint Configuration Manager.

**To generate the OMA URI for any setting in the CSP documentation**
1. CSP 설명서에서 CSP의 루트 노드를 확인합니다. 일반적으로 다음과 같이 표시됩니다. `./Vendor/MSFT/<name of CSP>` <br>
*예를 들어 [SurfaceHub CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)의 루트 노드는 `./Vendor/MSFT/SurfaceHub`입니다.*
2. 사용할 설정의 노드 경로를 확인합니다. <br>
*예를 들어 무선 프로젝션을 사용하도록 설정하는 설정의 노드 경로는 `InBoxApps/WirelessProjection/Enabled`입니다.*
3. 루트 노드에 노드 경로를 추가하여 OMA URI를 생성합니다. <br>
*예를 들어 무선 프로젝션을 사용하도록 설정하는 설정의 OMA URI는 `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`입니다.*

데이터 형식은 CSP 설명서에서도 설명됩니다. 가장 일반적인 데이터 형식은 다음과 같습니다.
- char(문자열)
- int(정수)
- bool(부울)


## 예: Microsoft Intune을 사용하여 Surface Hub 설정 관리

Microsoft Intune을 사용하여 Surface Hub 설정을 관리할 수 있습니다. 사용자 지정 설정은 [Microsoft Intune에서 사용자 지정 디바이스 설정을 구성하는 방법](https://docs.microsoft.com/intune/custom-settings-configure)의 지침을 따르세요. For **Platform**, select **Windows 10 and later**, and in **Profile type**, select **Device restrictions (Windows 10 Team)**.



## Example: Manage Surface Hub settings with Microsoft Endpoint Configuration Manager
Configuration Manager supports managing modern devices that do not require the Configuration Manager client to manage them, including Surface Hub. If you already use Configuration Manager to manage other devices in your organization, you can continue to use the Configuration Manager console as your single location for managing Surface Hubs.

> [!NOTE]
> These instructions are based on the current branch of Configuration Manager.

**To create a configuration item for Surface Hub settings**

1. Configuration Manager 콘솔의 **자산 및 호환성** 작업 영역에서 **개요** > **준수 설정** > **구성 항목**을 클릭합니다.
2. **홈** 탭의 **만들기** 그룹에서 **구성 항목 만들기**를 클릭합니다.
3. 구성 항목 만들기 마법사의 **일반** 페이지에서 구성 항목의 이름과 선택적 설명을 지정합니다.
4. **Configuration Manager 클라이언트를 사용하지 않고 관리되는 장치에 대한 설정**에서 **Windows 8.1 및 Windows 10**을 선택하고 **다음**을 클릭합니다.

    ![UI의 예](images/configmgr-create.png)
5. **지원되는 플랫폼** 페이지에서 **Windows 10**을 확장하고 **모든 Windows 10 Team 이상**을 선택합니다. 다른 Windows 플랫폼의 선택을 취소하고 **다음**을 클릭합니다.

    ![플랫폼 선택](images/configmgr-platform.png)
7. **장치 설정** 페이지의 **장치 설정 그룹**에서 **Windows10 Team**을 선택합니다.


8. **Windows10 Team** 페이지에서 필요한 설정을 구성합니다.

    ![Windows 10 Team](images/configmgr-team.png)
9. Windows 10 Team 페이지에서 사용할 수 없는 설정을 관리하려면 사용자 지정 설정을 만들어야 합니다. **장치 설정** 페이지에서 **기본 설정 그룹에 없는 추가 설정 구성** 확인란을 선택합니다.

    ![추가 설정](images/configmgr-additional.png)
10. **추가 설정** 페이지에서 **추가**를 클릭합니다.
11. **설정 찾아보기** 대화 상자에서 **설정 만들기**를 클릭합니다.
12. **설정 만들기** 대화 상자의 **일반** 탭에서 사용자 지정 설정의 이름과 선택적 설명을 지정합니다.
13. **설정 유형**에서 **OMA URI**를 선택합니다.
14. 양식을 완료하여 새 설정을 만들고 **확인**을 클릭합니다.

    ![OMA URI 설정](images/configmgr-oma-uri.png)
15. **설정 찾아보기** 대화 상자의 **사용 가능한 설정**에서 직접 만든 새 설정을 선택하고 **선택**을 클릭합니다.
16. **규칙 만들기** 대화 상자에서 양식을 완료하여 설정에 대한 규칙을 지정하고 **확인**을 클릭합니다.
17. 구성 항목에 추가할 각 사용자 지정 설정에 대해 9~15단계를 반복합니다.
18. 작업을 마쳤으면 **설정 찾아보기** 대화 상자에서 **닫기**를 클릭합니다.
19. 마법사를 완료합니다. <br> You can view the new configuration item in the **Configuration Items** node of the **Assets and Compliance** workspace.

For more information, see [Create configuration items for Windows 8.1 and Windows 10 devices managed without the Microsoft Endpoint Configuration Manager client](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client).

## Related topics

[Microsoft Surface Hub 관리](manage-surface-hub.md)











