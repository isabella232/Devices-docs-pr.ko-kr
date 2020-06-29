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
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836340"
---
# 디바이스 계정 만들기 및 테스트(Surface Hub)


이 항목에서는 Microsoft Surface Hub가 Microsoft Exchange 및 Skype와 통신하는 데 사용하는 디바이스 계정을 만들고 테스트하는 방법을 소개합니다.

**디바이스 계정**은 Surface Hub가 다음 작업에 사용하는 Exchange 리소스 계정입니다.

-   모임 일정 표시
-   팀 참가 또는 비즈니스용 Skype 통화
-   메일 보내기(예: 모임의 화이트보드 콘텐츠에 대한 메일 보내기)

디바이스 계정이 Surface Hub로 프로비전되면 사용자는 회의실에 초대하는 것과 같은 방식으로 이 계정을 모임 초대에 추가할 수 있습니다. 

## 구성 개요

이 표에서는 디바이스 계정을 만들 때 필요한 주요 단계와 구성 결정에 대해 설명합니다. 
 
| 단계 | 설명                     |  목적                             |
|------|---------------------------------|--------------------------------------|
| raid-1    | 로그온 가능 Exchange 리소스 사서함을 만들었음(Exchange 2013 이상 또는 Exchange Online) | 이 리소스 사서함을 통해 디바이스에서는 모임 일정을 유지 관리하고 모임 요청을 받고 메일을 보낼 수 있습니다. Surface Hub로 프로비전되려면 로그온 가능해야 합니다. |
| 2    | 사서함 속성 구성 | Surface Hub에서 최상의 모임 환경을 실현하려면 정확한 속성을 사용하여 사서함을 구성해야 합니다. 사서함 속성에 대한 자세한 내용은 [Microsoft Exchange 속성(Surface Hub)](exchange-properties-for-surface-hub-device-accounts.md)을 참조하세요. |
| 3-4    | 사서함에 호환 가능한 모바일 디바이스 사서함 정책 적용 | Surface Hub는 모바일 디바이스 사서함 정책이 아닌 MDM(모바일 디바이스 관리)을 사용하여 관리됩니다. 호환성을 위해 디바이스 계정에는 **PasswordEnabled** 설정이 False로 설정된 모바일 디바이스 사서함 정책이 있어야 합니다. 그렇지 않으면 Surface Hub가 메일과 일정을 동기화할 수 없습니다. |
| 4(tcp/ipv4)    | 비즈니스용 Skype(Lync Server 2013 이상 또는 비즈니스용 Skype Online)에서 사서함 사용 | 영상 통화, IM, 화면 공유 등의 회의 기능을 사용하려면 비즈니스용 Skype를 사용하도록 설정해야 합니다.  |
| 5mb    | (선택 사항) 허용 목록 ActiveSync 디바이스 ID | 디바이스 계정이 메일과 일정 정보를 동기화하지 못하게 하는 전역 정책이 조직에 있을 수 있습니다. 그렇다면 Surface Hub의 ActiveSync 장치 ID를 허용 해야 합니다. |
| 26    | (선택 사항) 암호 만료 사용 안 함 | 관리를 간소화하기 위해 디바이스 계정에 대한 암호 만료를 끄고 Surface Hub가 디바이스 계정의 암호를 자동으로 순환하게 할 수 있습니다. 암호 관리에 대한 자세한 내용은 [암호 관리(Surface Hub)](password-management-for-surface-hub-device-accounts.md)를 참조하세요.  |

## 세부 구성 단계 

원격 PowerShell을 사용하여 디바이스 계정을 설정하는 것이 좋습니다. 디바이스 계정을 만들고 유효성을 검사하는 데 도움이 될 수 있는 PowerShell 스크립트가 있습니다. PowerShell 스크립트 및 지침에 대한 자세한 내용은 [부록 A: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)을 참조하세요. 

PowerShell을 사용하여 디바이스 계정을 프로비전하는 자세한 단계의 경우 조직 배포에 따라 표에서 옵션을 선택합니다. 

| 조직 배포             |  설명                  |
|---------------------------------|--------------------------------------|
| [온라인 배포(Office 365)](online-deployment-surface-hub-device-accounts.md) | 조직의 환경 전체가 Office 365에 배포됩니다. |
| [온-프레미스 배포(단일 포리스트)](on-premises-deployment-surface-hub-device-accounts.md) | 조직이 제어하고 단일 포리스트 환경에서 Active Directory, Exchange 및 비즈니스용 Skype(또는 Lync)를 호스트하는 데 사용하는 서버가 조직에 있습니다. |
| [온-프레미스 배포(다중 포리스트)](on-premises-deployment-surface-hub-multi-forest.md) | 조직이 제어하고 다중 포리스트 환경에서 Active Directory, Exchange 및 비즈니스용 Skype(또는 Lync)를 호스트하는 데 사용하는 서버가 조직에 있습니다. |
| [하이브리드 배포](hybrid-deployment-surface-hub-device-accounts.md) | 온-프레미스에 호스트된 서비스와 Office 365를 통해 온라인에 호스트된 서비스가 혼합되어 있습니다. |
| [Skype 하이브리드 음성 환경으로 온라인 또는 하이브리드 배포](skype-hybrid-voice.md) | 조직에는 클라우드의 비즈니스용 Skype 홈 풀과 Exchange 서버가 있고, 비즈니스용 Skype 2015 또는 PSTN(공중 전화망)을 통해 연결된 클라우드 커넥터 버전의 온-프레미스 풀을 사용합니다. |


그래픽 UI(사용자 인터페이스)를 사용하려면 PowerShell 대신 UI를 사용하여 일부 단계를 수행할 수 있습니다. 자세한 내용은 [UI(Surface Hub)를 사용하여 디바이스 계정 만들기](create-a-device-account-using-office-365.md)를 참조하세요.

## 계정 확인 및 테스트

Surface Hub 장치 계정을 확인 및 테스트하기 위해 사용할 수 있는 방법은 [계정 확인 스크립트](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)와 [Surface Hub 하드웨어 진단 앱](https://www.microsoft.com/store/apps/9nblggh51f2g) 등 두 가지입니다. 계정을 확인 스크립트는 바탕 화면에서 PowerShell를 사용하여 이전에 생성된 장치 계정의 유효성을 검사합니다. Surface Hub 하드웨어 진단 앱은 Surface Hub에 설치되어 로그인 및 통신 오류에 대한 자세한 피드백을 제공합니다. 두 방법 모두 새로 생성된 장치 계정을 테스트할 수 있는 유용한 도구이며 최적의 계정 가용성을 보장하는 데 사용되어야 합니다.

 

 

 





