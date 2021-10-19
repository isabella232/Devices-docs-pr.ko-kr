---
title: Windows 10 Team 2020 업데이트의 새로운 기능
description: Surface Hub 2020 Update의 최신 업데이트에서 새로운 Windows 10 Team 확인 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/19/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3b9dbf0e4b7412967c3f2c68ddc10a6fccac8907
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101225"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Windows 10 Team 2020 업데이트의 새로운 기능

Windows 10 Team 2020 업데이트는 장치 배포 및 관리성에 대한 주요 개선 기능과 함께 최신 Windows 10 제공합니다.

## <a name="deployment-and-manageability"></a>배포 및 관리 가능성

- **클라우드 장치 계정에 대한 최신 인증**. Surface Hub EWS(Exchange 웹 서비스) 및 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원하여 Exchange 기본 인증 사용을 더는 사용하지 않습니다. 자세한 내용은 에서 [최신 인증을 Surface Hub.](surface-hub-modern-auth.md)
- MDM(모바일 장치 관리) 정책 설정이 **20개 이상 새로 추가 및 업데이트되었습니다.**  이러한 정책 설정을 통해 IT 관리자는 Microsoft Store 앱 업데이트, 인프라를 통해 무선으로 Miracast 설정, 서비스 품질 및 802.1x 유선 인증과 같은 네트워크 설정, 새로운 개인 정보/GDPR 관련 설정을 비롯한 여러 장치 설정을 더 개선할 수 있습니다. 새 CSP(구성 서비스 공급자)에는 다음이 포함됩니다. 

  - [Accounts CSP](/windows/client-management/mdm/accounts-csp) 
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp) 
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp) 

자세한 내용은 다음을 참조합니다. 
- [지원되는 CSP는 Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [MDM 공급자를 사용하여 Surface Hub 관리](manage-settings-with-mdm-for-surface-hub.md)

## <a name="azure-active-directory-joined-devices"></a>Azure Active Directory 가입된 장치

- **Azure AD 가입 장치에 대한 SSO(Single Sign-On)입니다.** 사용자가 자신의 Microsoft 365 자격 증명을 사용하여 "내 모임 및 파일"에 로그인하면 사용자 자격 증명이 앱 간 원활하게 흐르며 브라우저의 Microsoft 365 환경을 포함하게 됩니다.
- Azure AD 가입 장치에 대한 **CA(조건부 액세스)입니다.** IT 관리자는 회사 보안 및 규정 준수 요구 사항에 따라 장치 정책을 할당하여 Azure AD 가입 Surface Hub에서 조직 리소스에 대한 사용자 액세스를 제어할 수 있습니다.
- Azure AD 가입 장치에 대한 전역이 아닌 **관리자에 대한 지원**. 고객은 관리자 계층 구조 내에서 보다 세부적인 관리자 집합을 선택하여 관리자를 관리할 Surface Hub. 자세한 내용은 에서 전역이 아닌 관리자 계정 [구성을 Surface Hub.](surface-hub-2s-nonglobal-admin.md)

## <a name="browser-and-pen"></a>브라우저 및 펜

- **새 Microsoft Edge 기본적으로 설치됩니다.** Microsoft Edge 성능, 보안 및 개인 정보 보호를 위해 다시 구성했습니다. 자세한 내용은 Manage [Microsoft Edge on Surface Hub.](surface-hub-install-chromium-edge.md)
- **2S에서**이중 펜 Surface Hub.   사용자는 두 개의 Surface Hub 2 펜을 사용하여 2S에서 Surface Hub 수 있습니다. 이중 펜식 자동 작성을 사용하도록 설정하는 데 필요한 펌웨어 업데이트는 후속 업데이트와 함께 릴리스됩니다.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams 설치됩니다.**        Microsoft Teams MDM을 통해 또는 Surface Hub 앱을 사용하여 직접 구성할 수 있는 새 Surface Hub 디바이스에서 기본 모임, 통화 및 공동 작업 설정 포함되어 있습니다. 자세한 내용은[[배포](/MicrosoftTeams/teams-surface-hub)Microsoft Teams.
- **를 통해 근접 조인을 Microsoft Teams.**  근접 연결 기능을 사용하면 사용자가 자신의 랩톱/Microsoft Teams 사용하여 가까운 Surface Hub 예약된 통화를 하게 되거나 진행 중 모임을 가까운 가까운 모임으로 원활하게 전환할 수 Surface Hub. Windows 10 Team 2020 업데이트에는 근접 연결 구성을 위한 MDM(모바일 장치 관리) 지원이 추가되었습니다. 자세한 내용은 다음을 참조합니다. 

  - [Microsoft Teams 블로그 를 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833) 
  - [Surface Hub에서 Microsoft Teams 설정 관리](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **에서 조정된 모임을 Microsoft Teams.** 회의실에는 Surface Hub Microsoft Teams 회의실 장치 또는 두 개의 Surface Hub 디바이스가 있는 공간에서 협정 모임을 통해 사용자는 모임 중에 두 장치를 Microsoft Teams 있습니다. 한 번의 탭으로 사용자는 한 디바이스에서 비디오 피드를 표시하고 다른 디바이스의 디지털 화이트보드 또는 콘텐츠를 표시하여 한 디바이스에서 모임에 참가하고 화면 공간을 최대화할 수 있습니다. Windows 10 Team 2020 업데이트에는 조정된 모임을 구성하기 위한 MDM(모바일 장치 관리) 지원이 추가되어 나중에 이 기능이 Microsoft Teams 업데이트로 Microsoft Store. 자세한 내용은 [Set up Coordinated Meetings with Microsoft Teams 룸 and Surface Hub.](/MicrosoftTeams/rooms/coordinated-meetings)

## <a name="security"></a>Security

- **FIDO2 보안** 키를 사용하는 암호 없는 로그인     FIDO2 보안 키를 사용하여 고객은 사용자 이름과 암호를 입력하지 않고도 Surface Hub 쉽고 빠르게 로그인할 수 있습니다. SSO(Single Sign-On)와 결합된 이 기능은 모임 중에 파일, 앱 및 웹 사이트에 대해 빠르고 원활한 인증을 제공합니다. 자세한 내용은 에서 암호 없는 로그인 [구성을 Surface Hub.](surface-hub-2s-phone-authenticate.md)
- **를 사용하여 암호 없는 로그인이 Microsoft Authenticator.**  Azure AD를 사용하는 조직의 경우 사용자는 사용자 이름과 Microsoft Authenticator 입력하지 않고도 Microsoft Authenticator 앱을 사용하여 로그인할 수 있습니다. 또한 사용자는 UPN(사용자 계정 이름) 외에 Azure AD에서 기본 설정 전자 메일 별칭을 사용하여 로그인할 수 있습니다. 자세한 내용은 [Sign in to Surface Hub with Microsoft Authenticator.](surface-hub-authenticator-app.md)

## <a name="learn-more"></a>자세히 알아보기

- [Windows 10 Team 2020 업데이트 1이 모든 Surface Hub에 릴리스되었습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team 2020 업데이트 설치](surface-hub-2020-update.md)  
 