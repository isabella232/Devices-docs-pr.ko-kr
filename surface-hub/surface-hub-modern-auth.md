---
title: Surface Hub의 최신 인증
description: 이 페이지에서는 레거시 기본 인증과 대조적으로 Surface Hub의 최신 인증 사용에 대해 설명 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004470"
---
# Surface Hub의 최신 인증

클라우드 기반 계정에 대 한 최신 인증 지원은 [Windows 참가자 프로그램](https://insider.windows.com/)에서 사용할 수 있는 preview 빌드를 사용 하 여 예정 된 Windows 10 팀 2020 업데이트에 완벽 하 게 통합 되어 있습니다. [Preview 빌드를 설치한](surface-hub-install-2020preview.md)후에는 레거시 기본 인증에서 마이그레이션하고 Microsoft Azure 및 Exchange Online의 최신 보안 기능을 활용할 수 있습니다. 2020 업데이트를 사용 하는 Surface Hub는 exchange Online for Device 계정 동기화를 사용 하도록 설정 하는 웹 서비스 (EWS) 프로토콜 및 ADAL (Active Directory Authentication Library) 기반 인증을 지원 합니다.

새로운 클라우드 기반 계정의 경우 Surface Hub는 자동으로 최신 인증을 사용 하 여 [alias@contoso.com](mailto:alias@contoso.com)형식으로 디바이스 계정을 만드는 것 외에 추가 구성을 요구 하지 않고 Exchange Online에 연결 합니다. 최신 인증에 지원 되지 않는 레거시 형식-Contoso\alias를 사용 하지 마세요. 자세한 내용은 [Surface Hub 2S 디바이스 계정 만들기](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)를 참조 하세요.

> [!NOTE]
> Surface Hub는 온-프레미스 계정에 대 한 최신 인증을 지원 하지 않습니다. 계정은 클라우드에서 만들어야 합니다.

