---
title: Windows 10 Team 2020 업데이트의 새로운 기능
description: Surface Hub 운영 체제의 최신 업데이트 Windows 10 Team 2020 업데이트의 새로운 내용을 확인하세요.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
ms.openlocfilehash: 995766eb216051de270a387c15c96ee42dd008a3
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497961"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Windows 10 Team 2020 업데이트의 새로운 기능

Surface Hub 새로운 기능과 기능을 제공하는 정기 업데이트의 이점을 제공합니다. Windows 10 Team 2020 업데이트(20H2)와 이후 업데이트 1 & 업데이트 2는 최신 Windows 기능과 함께 디바이스 배포 및 관리 효율성이 크게 향상되었습니다.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 Team 2020 업데이트 2 

### <a name="gcc-high-support"></a>높은 지원 GCC

이 업데이트([KB5010415](https://support.microsoft.com/help/5010415) 또는 후속 Windows CU)를 설치한 후 Surface Hub는 GCC High 환경에서 지원됩니다. 이때 Teams 룸 클라이언트가 GCC High 테넌트에 성공적으로 연결하려면 [추가 단계 ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) 가 필요합니다.

### <a name="support-for-surface-hub-2-smart-camera"></a>Surface Hub 2 스마트 카메라 지원

AI 기반 Surface Hub 2 스마트 카메라는 하이브리드 팀에 최적화되어 원격 참가자가 Surface Hub 콘텐츠와 상호 작용하는 동시에 회의실의 다른 모든 사용자를 볼 수 있습니다.  자세한 내용은 [Surface Hub 2 스마트 카메라 설치 및 관리를 참조하세요](surface-hub-2-smart-camera.md). 

### <a name="support-for-progressive-web-apps-pwas"></a>PWA(프로그레시브 Web Apps) 지원

관리자는 프로비저닝 팩을 적용하는 MDM(모바일 디바이스 관리 공급자)을 사용하여 Surface Hubs에 PWA를 원격으로 설치할 수 있습니다. 자세한 내용은 [Surface Hub 프로그레시브 Web Apps 설치를](install-pwa-surface-hub.md) 참조하세요. 

### <a name="ease-of-access-updates"></a>접근성 업데이트

사용자는 다른 버전의 Windows 10 또는 Windows 11 것처럼 Surface Hub 세션 중에 접근성 설정을 조정하고 앱을 닫을 수 있습니다. 

- **접근성.** 사용자는 로그인하지 않고 표시, 텍스트 커서, 돋보기, 고대비, 내레이터, 선택 자막 및 키보드 설정을 조정할 수 있습니다. 
- **앱에 익숙한 UI**입니다. 사용자는 앱의 오른쪽 위 모서리에 있는 닫기 단추를 선택하여 Surface Hub 앱을 닫을 수 있습니다. 이렇게 하면 앱을 Surface Hub 표시의 아래쪽으로 끌어서 닫을 필요가 없습니다. (참고: 이 기능은 2022년 3월로 예정된 다음 Edge 업데이트의 일부로 Edge 브라우저에서 사용할 수 있습니다.) 

자세한 내용은 [Surface Hub 접근성 설정 조정을](accessibility-surface-hub.md) 참조하세요.

### <a name="administrator-updates"></a>관리자 업데이트

- **이벤트 뷰어**. 관리자는 설정 앱에서 직접 Windows 이벤트 뷰어 액세스할 수 있습니다. 
- **새 MDM(모바일 디바이스 관리) 정책 설정**입니다. 새 CSP(구성 서비스 공급자)에는 다음이 포함됩니다.

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

자세한 내용은 [Surface Hub 전역이 아닌 관리자 계정 구성을 참조](surface-hub-2s-nonglobal-admin.md)하세요.


## <a name="windows-10-team-2020-update-1"></a>Windows 10 Team 2020 업데이트 1

### <a name="support-for-new-teams-rooms-application"></a>새 Teams 룸 애플리케이션 지원

이 업데이트([KB5005101](https://support.microsoft.com/help/5005101) 또는 후속 Windows CU)를 설치한 후 Surface Hubs는 Windows 업데이트 통해 새 [Teams 룸 클라이언트](surface-hub-teams-rooms.md)로 자동 업그레이드를 지원합니다.

### <a name="support-for-new-whiteboard-application"></a>새 Whiteboard 애플리케이션 지원

이 업데이트를 설치한 후 Surface Hubs는 Microsoft Store 업데이트를 통해 새 [Whiteboard 앱](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226)으로 자동 업그레이드(사용 가능한 경우)를 지원합니다.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>기본적으로 설치된 새 Microsoft Edge 브라우저

이 업데이트를 설치한 후 Surface Hubs는 Microsoft Edge 레거시 브라우저를 새 Chromium 기반 Edge 브라우저로 자동으로 바꿉니다.  자세한 내용은 [Surface Hub Microsoft Edge 관리를](surface-hub-install-chromium-edge.md) 참조하세요. 이 업데이트 또는 후속 Windows CU를 설치한 후 Windows 10 Team Edge 레거시를 더 이상 사용할 수 없습니다.


## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 Team 2020 업데이트(20H2)

### <a name="deployment-and-manageability"></a>배포 및 관리 효율성

- **클라우드 디바이스 계정에 대한 최신 인증입니다**. Surface Hub Exchange 웹 서비스(EWS) 및 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원하여 Exchange 연결하여 고객이 기본 인증 사용을 더 이상 사용하지 못하게 합니다. 자세한 내용은 [Surface Hub 최신 인증을](surface-hub-modern-auth.md) 참조하세요.
- **20개 이상의 새 MDM 정책 설정 및 업데이트된 MDM 정책 설정**  이러한 정책 설정은 IT 관리자가 Microsoft Store 앱 업데이트, 인프라를 통한 Miracast 같은 무선 프로젝션 설정, 서비스 품질 및 802.1x 유선 인증과 같은 네트워크 설정, 새로운 개인 정보/GDPR 관련 설정을 포함하여 여러 디바이스 설정에 대한 향상된 제어를 제공합니다. 새 CSP는 다음과 같습니다.

  - [Accounts CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

자세한 내용은 다음을 참조하세요.

- [Microsoft Surface Hub 지원되는 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [MDM 공급자를 사용하여 Surface Hub 관리](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>조인된 디바이스 Azure Active Directory

- **Azure AD 조인된 디바이스에 대한 SSO(Single Sign-On)** 입니다. 사용자가 Microsoft 365 자격 증명을 사용하여 **내 모임 및 파일에** 로그인하면 브라우저의 Microsoft 365 환경을 포함하여 앱에서 앱으로 자격 증명이 원활하게 전달됩니다.
- **Azure AD 조인된 디바이스에 대한 CA(조건부 액세스)** 입니다. IT 관리자는 회사 보안 및 규정 준수 요구 사항에 따라 디바이스 정책을 할당하여 Azure AD 가입된 Surface Hubs에서 조직 리소스에 대한 사용자 액세스를 제어할 수 있습니다.
- **Azure AD 조인된 디바이스에 대한 전역이 아닌 관리자를 지원합니다**. 고객은 관리자 계층 구조 내에서 보다 세분화된 관리자 집합을 선택하여 Surface Hub 관리할 수 있습니다. 자세한 내용은 [Surface Hub 전역이 아닌 관리자 계정 구성을 참조](surface-hub-2s-nonglobal-admin.md)하세요.

### <a name="inking-improvements"></a>수동 입력 개선 사항

- **Surface Hub 2S에서 이중 펜 수동 입력 지원**  화이트보드를 사용하고 Surface Hub 2S에서 2개의 Surface Hub 2펜으로 나란히 공동 작업합니다. Windows 10 Team 2020으로 업그레이드한 후 설치된 시스템 하드웨어 업데이트는 이 시나리오에 대한 펌웨어 지원을 추가합니다.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams 기본적으로 설치됩니다**. Microsoft Teams 새 Surface Hub 디바이스에서 모임, 통화 및 공동 작업을 위한 기본 앱으로, MDM을 통해 또는 설정 앱을 사용하여 Surface Hub 직접 변경하거나 구성할 수 있습니다. 자세한 내용은 [Microsoft Teams 배포](/MicrosoftTeams/teams-surface-hub)를 참조하세요.
- **Microsoft Teams 사용한 근접 조인 지원**  근접 조인을 사용하면 사용자가 노트북이나 휴대폰을 사용하여 인근 Surface Hub 예약된 Microsoft Teams 통화를 할 수 있습니다.  또한 사용자가 진행 중인 모임을 인근 Surface Hub 전환할 수 있습니다. Windows 10 Team 2020 업데이트는 근접 조인을 구성하는 MDM(모바일 장치 관리) 지원을 추가합니다. 자세한 내용은 다음을 참조하세요.

  - [Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Surface Hub에서 Microsoft Teams 설정 관리](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Microsoft Teams 조정된 모임에 대한 지원** Surface Hub Microsoft Teams 회의실 장치 또는 두 개의 Surface Hub 장치가 있는 공간을 갖춘 회의실에서 조정된 모임을 통해 사용자는 Microsoft Teams 모임 중에 두 장치를 빠르게 활용할 수 있습니다. 사용자는 한 장치에서 비디오 피드를 표시하고 다른 장치에는 디지털 화이트보드 또는 콘텐츠를 표시하여 한 번의 탭으로 화면 공간을 최대화하여 두 장치에서 모임에 참가할 수 있습니다. Windows 10 Team 2020 업데이트는 MDM(Mobile 장치 관리) 지원을 추가하여 조정된 모임을 구성하며, 이 기능은 이후 Microsoft Store 통해 Microsoft Teams 업데이트로 릴리스됩니다. 자세한 내용은 [Microsoft Teams 룸 및 Surface Hub 사용하여 조정된 모임 설정을](/MicrosoftTeams/rooms/coordinated-meetings) 참조하세요.

### <a name="security"></a>보안

- **FIDO2 보안 키를 사용하는 암호 없는 로그인** FIDO2 보안 키를 사용하면 사용자는 사용자 이름과 암호를 입력하지 않고도 Surface Hub 빠르게 로그인할 수 있습니다. SSO(Single Sign-On)와 결합된 이 기능은 모임 중에 파일, 앱 및 웹 사이트에 빠르고 원활한 인증을 제공합니다. 자세한 내용은 [Surface Hub 암호 없는 로그인 구성을](surface-hub-2s-phone-authenticate.md) 참조하세요.
- **Microsoft Authenticator 사용하여 암호 없는 로그인을 개선**했습니다.  Azure AD 사용하는 조직의 경우 사용자는 Microsoft Authenticator 앱으로 로그인할 수 있습니다. 또한 사용자는 Azure AD 기본 설정 전자 메일 별칭 또는 UPN(사용자 계정 이름)으로 로그인할 수 있습니다. 자세한 내용은 [Microsoft Authenticator 사용하여 Surface Hub 로그인을](surface-hub-authenticator-app.md) 참조하세요.

## <a name="learn-more"></a>세부 정보

- [모든 Surface Hub에 릴리스된 Windows 10 Team 2020 업데이트 1](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [2020년 Windows 10 Team 업데이트 사용 가능 10월 27일](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Windows 10 Team 2020 업데이트 설치](surface-hub-2020-update.md)
