---
title: Surface Hub의 최신 인증
description: 이 페이지는 레거시 기본 인증과 달리 Surface Hub에서 최신 인증을 사용하는 방법을 설명하고 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206282"
---
# Surface Hub의 최신 인증

클라우드 기반 계정의 최신 인증 지원이 [Windows 10 Team 2020 업데이트에 완전히 통합되었습니다.](surface-hub-2020-update.md) 2020 업데이트를 설치한 후 레거시 기본 인증에서 마이그레이션하고 Microsoft Azure 및 Exchange Online의 최신 보안 향상 기능을 사용할 수 있습니다. 2020 업데이트를 통해 Surface Hub는 EWS(Exchange 웹 서비스) 프로토콜 및 장치 계정 동기화를 위해 Exchange Online을 지원하는 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원합니다.

새 클라우드 기반 계정의 경우 Surface Hub는 단순히 새 형식을 사용하여 장치 계정을 만드는 것 이상으로 추가 구성 없이도 최신 인증을 사용하여 Exchange [Online에 alias@contoso.com.](mailto:alias@contoso.com) 최신 인증에 지원되지 않는 레거시 형식인 Contoso\alias를 사용하지 않습니다. 자세한 내용은 Surface Hub 2S 장치 계정 [만들기를 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

> [!NOTE]
> Surface Hub는 On-premises 계정에 대한 최신 인증을 지원하지 않습니다. 계정은 클라우드에서 만들어야 합니다.

