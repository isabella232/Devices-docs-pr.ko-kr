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
ms.openlocfilehash: 9d2214453c8cb4c8d03f526dd4ac83264d2a16ad
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676382"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>디바이스 계정 만들기 및 테스트(Surface Hub)

Surface Hub 계정(리소스 계정/회의실 사서함)을 만들면 Surface Hub 요청을 수신, 승인 또는 거절하고 모임에 참가할 수 있습니다.

장치 계정이 Surface Hub 회의실을 초대하는 방법과 동일한 방식으로 모임 초대에 이 계정을 추가할 수 있습니다. 

[OOBE(첫](first-run-program-surface-hub.md)실행 경험) 설치 중에 디바이스 계정을 구성할 수 있습니다. 필요한 경우 나중에 계정 에서 **** 변경할  >  **설정 Surface Hub**  >  **있습니다.**

## <a name="configuration-overview"></a>구성 개요

이 표에서는 디바이스 계정을 만들 때 필요한 주요 단계와 구성 결정에 대해 설명합니다.
 
| 단계 | 설명                     |  목적                             |
|------|---------------------------------|--------------------------------------|
| 1    | 로그온 가능 방 사서함 만들기(Exchange Online 또는 Exchange Server 2016 이상) | 이 유형의 사서함을 사용하면 장치가 모임 일정을 유지 관리하고, 모임 요청을 받고, 메일을 보낼 수 있습니다. 로그온할 수 있는 사용자와 함께 사용하려면 로그온이 Surface Hub. |
| 2    | 사서함 속성 구성 | Surface Hub에서 최상의 모임 환경을 실현하려면 정확한 속성을 사용하여 사서함을 구성해야 합니다. 사서함 속성에 대한 자세한 내용은 [Microsoft Exchange 속성(Surface Hub)](exchange-properties-for-surface-hub-device-accounts.md)을 참조하세요. |
| 3    | EWS(Exchange)를 사용하도록 설정하고 MFA(다단계 인증)를 사용하지 않도록 설정해야 합니다. | 이 Surface Hub EWS를 사용하여 일정을 동기화합니다. 환경에서 기본적으로 EWS를 허용하지 않는 경우 허브 사서함에서 EWS를 명시적으로 사용하도록 설정해야 합니다. 사용자가 Surface Hub 없이 백그라운드에서 Exchange 로그인할 때 MFA와 같은 대화형 프롬프트에 응답할 수 없습니다. 만든 디바이스 계정은 이러한 인증 요구 사항에서 제외해야 합니다. 그렇지 않으면 Surface Hub가 메일과 일정을 동기화할 수 없습니다. |
| 4    | Teams 또는 비즈니스용 Skype(비즈니스용 Skype 서버 2015 이상)에 대해 계정을 사용하도록 설정 | 비즈니스용 Skype 또는 Teams 화상 통화 및 화면 공유와 같은 회의 기능을 사용하도록 설정해야 합니다. 라이선스를 사용하도록 설정하는 라이선스에 대한 자세한 [](/MicrosoftTeams/rooms/rooms-licensing) 내용은 Teams 라이선스 및 Teams 미팅룸 [설명을 Teams 참조하세요.](/office365/servicedescriptions/teams-service-description) 앱의 Teams SfB 응용 Surface Hub 장치 정보(예: 규정 준수)가 필요한 [Azure AD 조건부](/azure/active-directory/conditional-access/concept-conditional-access-policies) 액세스 정책과 호환되지 않습니다. 만든 디바이스 계정은 이러한 CA 정책에서 제외해야 합니다. 그렇지 Surface Hub 회의 기능을 사용할 수 없습니다. |
| 5    | (선택 사항) 암호 만료 사용 안 함 | 관리를 간소화하기 위해 디바이스 계정에 대한 암호 만료를 끄고 Surface Hub가 디바이스 계정의 암호를 자동으로 순환하게 할 수 있습니다. 암호 관리에 대한 자세한 내용은 [암호 관리(Surface Hub)](password-management-for-surface-hub-device-accounts.md)를 참조하세요.  |
| 6    | (선택 사항) ActiveSync를 Exchange 정책 구성 | 특정 온-프레미스 Exchange Server & Active Directory 배포에서는 ActiveSync를 사용하여 장치 계정 메일 및 일정 정보를 동기화합니다. 구성할 정책에 대한 자세한 내용은 계정 에 [대한 ActiveSync Surface Hub 참조하세요.](apply-activesync-policies-for-surface-hub-device-accounts.md) |

> [!NOTE]  
> Surface Hub 계정은 타사 ID 공급자(IdP)를 지원하지 않습니다. Active Directory 또는 인증을 통해 인증해야 Azure Active Directory.

## <a name="detailed-configuration-steps"></a>세부 구성 단계 

원격 장치를 사용하여 Surface Hub 계정을 설정하는 것이 Windows PowerShell. Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1리소스 계정을 만들거나 기존 리소스 계정의 유효성을 검사하여 호환되는 장치 계정으로 전환하는 데 도움이 되는 Surface Hub 스크립트를 제공합니다. 원하는 경우 아래 표에서 옵션을 선택하고 조직 배포에 따라 자세한 PowerShell 단계를 따를 수 있습니다.

| 조직 배포             |  설명                  |        설치 중에 사용할 Surface Hub 형식
|---------------------------------|--------------------------------------|
| [온라인 배포(Microsoft 365 또는 Office 365)](/MicrosoftTeams/rooms/with-office-365) |조직의 환경은 전적으로 조직 또는 Microsoft 365 Office 365. | username@domain.com |
| [하이브리드 배포(Exchange 배포)](/MicrosoftTeams/rooms/with-exchange-on-premises) | 조직에는 서비스가 혼합되어 있으며, Exchange Server 온라인에서 Microsoft Teams 있습니다. | username@domain.com 도메인에서 [하이브리드](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) 최신 인증을 사용할 수 Exchange 도메인\사용자 이름 |
| [하이브리드 배포(Exchange Online)](/MicrosoftTeams/rooms/with-exchange-online) | 조직에는 서비스가 혼합되어 있으며, 비즈니스용 Skype 서버 호스트된 Exchange Online. | username@domain.com 하이브리드 [최신](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) 인증이 SfB에서 활성화되어 있는 경우 도메인\사용자 이름입니다. 그렇지 않은 경우 |
| [온-프레미스 배포(단일 포리스트)](/MicrosoftTeams/rooms/with-skype-for-business-server-2015) | 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버 제어하는 서버가 있습니다.  | 도메인\사용자 이름 |
| [온-프레미스 배포(다중 포리스트)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 조직에는 Active Directory, Exchange 및 비즈니스용 Skype 서버 제어하는 서버가 있습니다. | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>계정 확인 및 테스트

Surface Hub 장치 계정의 유효성을 검사하고 테스트하는 데 사용할 수 [](https://go.microsoft.com/fwlink/?linkid=870105) 있는 두 가지 방법은SkypeRoomProvisioningScript.ps1및 Surface Hub [있습니다.](https://www.microsoft.com/store/apps/9nblggh51f2g) 계정 프로비전 스크립트는 PC에서 PowerShell을 사용하여 이전에 만든 디바이스 계정의 유효성을 검사할 수 있습니다. Surface Hub 하드웨어 진단 앱은 Surface Hub에 설치되어 로그인 및 통신 오류에 대한 자세한 피드백을 제공합니다. 두 방법 모두 새로 생성된 장치 계정을 테스트할 수 있는 유용한 도구이며 최적의 계정 가용성을 보장하는 데 사용되어야 합니다.
