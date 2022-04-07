---
title: 디바이스 계정 만들기 및 테스트(Surface Hub)
description: 이 항목에서는 Microsoft Surface Hub가 Microsoft Exchange 및 Skype와 통신하는 데 사용하는 디바이스 계정을 만들고 테스트하는 방법을 소개합니다.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 디바이스 계정 만들기 및 테스트, 디바이스 계정, Surface Hub 및 Microsoft Exchange, Surface Hub 및 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: c925cb952c7fd04a86d824dfba99a373c07b313e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472627"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>디바이스 계정 만들기 및 테스트(Surface Hub)

Surface Hub 디바이스 계정(리소스 계정/회의실 사서함이라고도 함)을 만들면 Surface Hub 모임 요청을 수신, 승인 또는 거절하고 모임에 참가할 수 있습니다.

디바이스 계정이 Surface Hub 프로비전되면 사용자는 회의실을 초대하는 것과 동일한 방식으로 이 계정을 모임 초대에 추가할 수 있습니다. 

[OOBE(기본 제공 환경) 설정](first-run-program-surface-hub.md) 중에 디바이스 계정을 구성할 수 있습니다. 필요한 경우 나중에 **설정** > **Surface Hub** >  **Accounts**에서 변경할 수도 있습니다.

## <a name="configuration-overview"></a>구성 개요

이 표에서는 디바이스 계정을 만들 때 필요한 주요 단계와 구성 결정에 대해 설명합니다.
 
| 단계 | 설명                     |  목적                             |
|------|---------------------------------|--------------------------------------|
| 1    | 로그온이 가능한 회의실 사서함 만들기(Exchange Online 또는 Exchange Server 2016 이상) | 이 유형의 사서함을 사용하면 디바이스에서 모임 일정을 유지하고, 모임 요청을 받고, 메일을 보낼 수 있습니다. Surface Hub 사용하려면 로그온을 사용하도록 설정해야 합니다. |
| 2    | 사서함 속성 구성 | Surface Hub에서 최상의 모임 환경을 실현하려면 정확한 속성을 사용하여 사서함을 구성해야 합니다. 사서함 속성에 대한 자세한 내용은 [Microsoft Exchange 속성(Surface Hub)](exchange-properties-for-surface-hub-device-accounts.md)을 참조하세요. |
| 3    | EWS(Exchange Web Services)를 사용하도록 설정하고 MFA(다단계 인증)를 사용하지 않도록 설정했는지 확인합니다. | Surface Hub EWS를 사용하여 일정을 동기화합니다. 기본적으로 사용자 환경에서 EWS를 허용하지 않는 경우 허브 사서함을 명시적으로 사용하도록 설정해야 합니다. Surface Hub 사용자 상호 작용 없이 백그라운드에서 Exchange 로그인하므로 MFA와 같은 대화형 프롬프트에 응답할 수 없습니다. 만든 디바이스 계정은 이러한 인증 요구 사항에서 제외해야 합니다. 그렇지 않으면 Surface Hub가 메일과 일정을 동기화할 수 없습니다. |
| 4    | Teams 또는 비즈니스용 Skype 계정을 사용하도록 설정(비즈니스용 Skype 서버 2015 이상) | 화상 통화 및 화면 공유와 같은 회의 기능을 사용하려면 비즈니스용 Skype 또는 Teams 사용하도록 설정해야 합니다. Teams 사용하도록 설정하는 라이선스에 대한 자세한 내용은 [Teams 미팅룸 라이선스](/MicrosoftTeams/rooms/rooms-licensing) 및 [Teams 서비스 설명을](/office365/servicedescriptions/teams-service-description) 참조하세요. Surface Hub Teams 및 SfB 애플리케이션은 디바이스 정보가 필요한 [Azure AD 조건부 액세스 정책](/azure/active-directory/conditional-access/concept-conditional-access-policies)(예: 규정 준수)과 호환되지 않습니다. 만든 디바이스 계정은 이러한 CA 정책에서 제외해야 합니다. 그렇지 않으면 Surface Hub 회의 기능을 사용할 수 없습니다. |
| 5    | (선택 사항) 암호 만료 사용 안 함 | 관리를 간소화하기 위해 디바이스 계정에 대한 암호 만료를 끄고 Surface Hub가 디바이스 계정의 암호를 자동으로 순환하게 할 수 있습니다. 암호 관리에 대한 자세한 내용은 [암호 관리(Surface Hub)](password-management-for-surface-hub-device-accounts.md)를 참조하세요.  |

> [!NOTE]  
> Surface Hub 디바이스 계정은 타사 IDP(페더레이션 ID 공급자)를 지원하지 않으며 Active Directory 또는 Azure Active Directory 통해 인증해야 합니다.

## <a name="detailed-configuration-steps"></a>세부 구성 단계 

디바이스 계정 설정 단계는 환경에 따라 다를 수 있습니다. 아래 표에서 배포 시나리오를 선택하여 적절한 단계를 찾고, 계정이 프로비전되면 Surface Hub를 구성하기 위한 "사용할 서식" 열을 적어둡니다.

| 조직 배포             |  설명                  |        Surface Hub 설정 중에 사용할 형식
|---------------------------------|--------------------------------------|
| [온라인 배포(Microsoft 365)](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |조직의 환경은 전적으로 Microsoft 365 배포됩니다. | username@domain.com |
| [하이브리드 배포(Exchange 온-프레미스)](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | 조직에는 온-프레미스 및 Microsoft Teams 온라인으로 호스트되는 Exchange Server 다양한 서비스가 있습니다. | username@domain.com Exchange [하이브리드 최신 인증](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)을 사용하도록 설정하면 DOMAIN\username이 사용됩니다. |
| [하이브리드 배포(Exchange Online)](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | 조직에는 온-프레미스 및 Exchange Online 호스트되는 비즈니스용 Skype 서버 다양한 서비스가 있습니다. | SfB에서 [하이브리드 최신 인증](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) 을 사용하는 경우 username@domain.com, 그렇지 않으면 DOMAIN\username |
| [온-프레미스 배포(단일 포리스트)](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버 단일 포리스트 환경에서 호스트되는 제어하는 서버가 있습니다.  | 도메인\사용자 이름 |
| [온-프레미스 배포(다중 포리스트)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버 다중 포리스트 환경에서 호스트되는 제어하는 서버가 있습니다. | ACCOUNTFOREST\username |

온라인 배포의 경우 M365 [관리 센터에서 직접 Microsoft 365 관리자가 사용할 수 있는 배포 마법사도 있습니다](https://admin.microsoft.com/Adminportal/Home#/modernonboarding/surfacehubsetupguide). 이 마법사를 사용하면 새 디바이스 계정을 만들거나 기존 리소스 계정의 유효성을 검사하여 호환 가능한 Surface Hub 디바이스 계정으로 전환할 수 있습니다.
