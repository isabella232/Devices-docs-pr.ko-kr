---
title: 2020 2020 Windows 10 Team 새로운 소식
description: Surface Hub 2020 Update의 최신 업데이트에서 새로운 Windows 10 Team 확인해 보아야 합니다.
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
ms.openlocfilehash: c44ec68a39158910c841375aeda0a6d6bf11635f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448271"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>2020 2020 Windows 10 Team 새로운 소식

Surface Hub 기능을 제공하는 주기적인 업데이트의 이점을 제공합니다. 2020 업데이트(20H2)Windows 10 Team 업데이트 및 이후 업데이트 1 & 업데이트 2는 장치 배포 및 관리성이 최신 Windows 10 향상되었습니다.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 Team 2020 업데이트 2 

### <a name="gcc-high-support"></a>GCC 높은 지원

이 업데이트([KB5010415](https://support.microsoft.com/help/5010415) 또는 후속 Windows CU)를 설치한 후 Surface Hub는 고급 환경에서 GCC 지원됩니다. 현재, Teams 룸 클라이언트 [ ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) 가 높은 테넌트에 연결하려면 추가 GCC 필요합니다.

### <a name="ease-of-access-updates"></a>접근성 업데이트

사용자는 다른 버전의 앱처럼 Surface Hub 세션 중에 접근성 설정을 조정하고 앱을 닫을 Windows 10. 

- **접근성**. 사용자는 로그인하지 않고도 디스플레이, 텍스트 커서, 돋보기, 높은 대비, 내레이터, 선택 자막 및 키보드 설정을 조정할 수 있습니다. 
- **앱에 대한 친숙한 UI입니다**. 사용자는 앱의 오른쪽 Surface Hub 닫기 단추를 선택하여 앱에서 앱을 닫을 수 있습니다. 이렇게 하여 앱을 앱 표시의 아래쪽으로 끌어서 닫을 Surface Hub 없습니다. (참고: 이 기능은 2022년 3월에 예정된 다음 에지 업데이트의 일부로 에지 브라우저에서 사용할 수 있습니다.) 

자세한 내용은 [Access의 접근](accessibility-surface-hub.md)성 설정 조정을 Surface Hub.

### <a name="administrator-updates"></a>관리자 업데이트

- **이벤트 뷰어**. 관리자는 Windows 앱에서 직접 이벤트 뷰어에 액세스할 설정 있습니다. 
- **새 MDM(모바일 장치 관리) 정책 설정입니다**. 새 CSP(구성 서비스 공급자)에는 다음이 포함됩니다.

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

자세한 내용은 [Configure non global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="windows-10-team-2020-update-1"></a>Windows 10 Team 2020 업데이트 1

### <a name="support-for-new-teams-rooms-application"></a>새 응용 프로그램 Teams 룸 지원

이 업데이트([KB5005101](https://support.microsoft.com/help/5005101) 또는 후속 Windows CU)를 설치한 후 Surface Hub는 Teams 룸 업데이트를 통해 새 Windows 클라이언트로 자동 업그레이드 [](surface-hub-teams-rooms.md) 할 수 있습니다.

### <a name="support-for-new-whiteboard-application"></a>새 화이트보드 응용 프로그램 지원

이 업데이트를 설치한 후 Surface Hub는 업데이트 업데이트를 통해 새 [Whiteboard](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) 앱에 대한 자동 업그레이드(사용 가능한 경우)Microsoft Store 지원됩니다.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>새 Microsoft Edge 브라우저가 기본적으로 설치됩니다.

이 업데이트를 설치하고 나면 Surface Hub는 자동으로 Microsoft Edge 레거시 브라우저를 새 Chromium 에지 브라우저로 대체합니다.  자세한 내용은 Manage [Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md). Edge 레거시는 이 업데이트를 설치하거나 Windows 10 Team 후속 CU에서 더 이상 사용할 Windows 없습니다.


## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 Team 2020 업데이트(20H2)

### <a name="deployment-and-manageability"></a>배포 및 관리 가능성

- **클라우드 장치 계정에 대한 최신 인증.** Surface Hub EWS(Exchange 웹 서비스) 및 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원하여 Exchange 기본 인증 사용을 더는 사용하지 않습니다. 자세한 내용은 최신 인증[을 Surface Hub](surface-hub-modern-auth.md).
- **새로 추가 및 업데이트된 MDM 정책 설정이 20개 이상 있습니다**.  이러한 정책 설정을 통해 IT 관리자는 Microsoft Store 앱 업데이트, 인프라를 사용하는 무선 투영 설정Miracast 서비스 품질 및 802.1x 유선 인증과 같은 네트워크 설정, 새로운 개인 정보/GDPR 관련 설정을 비롯한 여러 장치 설정에 대한 제어 권한을 향상합니다. 새 CSP는 다음과 같습니다.

  - [Accounts CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

자세한 내용은 다음을 참조합니다.

- [CSP는 Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [MDM 공급자를 사용하여 Surface Hub 관리](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory 장치

- **Azure AD 가입 장치에 대한 SSO(Single Sign-On)입니다**. 사용자가 내 모임에 Microsoft 365 자격 증명으로 로그인하고 자격 증명 **** 이 앱에서 앱으로 원활하게 흐르며 브라우저의 Microsoft 365 환경을 포함하면 됩니다.
- **Azure AD 가입 장치에 대한 CA(조건부 액세스)입니다**. IT 관리자는 회사 보안 및 규정 준수 요구 사항에 따라 장치 정책을 할당하여 Azure AD 가입 Surface Hub에서 조직 리소스에 대한 사용자 액세스를 제어할 수 있습니다.
- **Azure AD 가입 장치에 대한 전역이 아닌 관리자에 대한 지원.** 고객은 관리자 계층 구조 내에서 보다 세부적인 관리자 집합을 선택하여 관리자를 관리할 Surface Hub. 자세한 내용은 [Configure non global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

### <a name="inking-improvements"></a>향상된 Inking

- **2S에서** 이중 펜 Surface Hub 지원  화이트보드를 사용하여 2S에서 Surface Hub 2개의 펜과 Surface Hub 공동 작업을 할 수 있습니다. Windows 10 Team 2020으로 업그레이드한 후 설치된 모든 시스템 하드웨어 업데이트는 이 시나리오에 대한 펌웨어 지원을 추가합니다.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams 설치됩니다**. Microsoft Teams MDM을 통해 또는 Surface Hub 앱을 사용하여 직접 구성할 수 있는 새 Surface Hub 디바이스에서 모임, 통화 및 공동 작업을 위한 기본 설정 포함되어 있습니다. 자세한 내용은 [Deploy Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **와일드 조**인 및 Microsoft Teams.  근접 연결은 사용자가 랩톱 또는 휴대폰을 사용하여 Microsoft Teams 예약된 통화를 Surface Hub 수 있습니다.  또한 진행 중 모임을 가까운 모임으로 전환할 수 Surface Hub. Windows 10 Team 2020 업데이트에는 근접 연결 구성을 위한 MDM(모바일 장치 관리) 지원이 추가되었습니다. 자세한 내용은 다음을 참조합니다.

  - [Microsoft Teams 블로그를 참조하세요](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Surface Hub에서 Microsoft Teams 설정 관리](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **모임과 함께 조정된 모임을 Microsoft Teams**. Surface Hub Microsoft Teams 회의실 장치 또는 두 개의 Surface Hub 디바이스가 있는 회의실에서는 조정된 모임을 통해 사용자가 모임 중에 두 장치를 Microsoft Teams 있습니다. 사용자는 한 디바이스에서 비디오 피드를 표시하고 다른 디바이스의 디지털 화이트보드 또는 콘텐츠를 표시하여 한 디바이스에서 한 번의 탭으로 모임에 참가하고 화면 공간을 최대화할 수 있습니다. Windows 10 Team 2020 업데이트에는 조정된 모임을 구성하기 위한 MDM(모바일 장치 관리) 지원이 추가되어 나중에 이 기능이 Microsoft Teams 업데이트로 Microsoft Store. 자세한 내용은 [Set up Coordinated Meetings with Microsoft Teams 룸 and Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### <a name="security"></a>보안

- **FIDO2 보안 키를 사용하는 암호 없는 로그인** FIDO2 보안 키를 사용하여 사용자는 사용자 이름과 암호를 입력하지 않고도 Surface Hub 로그인할 수 있습니다. SSO(Single Sign-On)와 결합된 이 기능은 모임 중에 파일, 앱 및 웹 사이트에 빠르고 원활한 인증을 제공합니다. 자세한 내용은 [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **보안 기능을 사용하는** 암호 없는 로그인이 Microsoft Authenticator.  Azure AD를 사용하는 조직의 경우 사용자는 앱 앱으로 Microsoft Authenticator 있습니다. 또한 사용자는 AZURE AD에서 기본 설정 전자 메일 별칭과 UPN(사용자 계정 이름)을 사용하여 로그인할 수 있습니다. 자세한 내용은 Sign [in to Surface Hub with Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>세부 정보

- [Windows 10 Team 2020 업데이트 1이 모든 Surface Hub에 릴리스되었습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team 2020 업데이트 10월 27일 사용 가능](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Windows 10 Team 2020 업데이트 설치](surface-hub-2020-update.md)
