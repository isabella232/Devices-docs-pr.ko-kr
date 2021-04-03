---
title: Surface Hub의 최신 인증
description: 이 페이지에서는 레거시 기본 인증과 달리 Surface Hub에서 최신 인증을 사용하는 방법을 설명하고 있습니다.
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
ms.openlocfilehash: 3873d0ac7ffff3fa790f44b474d937772e5a0900
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474765"
---
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="59d30-104">Surface Hub의 최신 인증</span><span class="sxs-lookup"><span data-stu-id="59d30-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="59d30-105">Windows 10 Team 2020 Update는 일부 시나리오에서 허브 장치 계정의 최신 인증에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="59d30-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="59d30-106">2020 업데이트를 설치한 후 장치 계정이 Azure Active Directory를 통해 인증하고 계정의 사서함이 Exchange Online에서 호스팅되는 경우 레거시 기본 인증에서 마이그레이션하여 향상된 최신 보안 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d30-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="59d30-107">2020 업데이트를 통해 Surface Hub는 장치 계정을 Exchange Online과 동기화할 때 EWS(Exchange 웹 서비스) 프로토콜 및 ADAL(Active Directory 인증 라이브러리) 기반 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="59d30-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="59d30-108">새 클라우드 기반 계정의 경우 Surface Hub는 최신 인증을 사용하여 Exchange Online에 연결하기 위해 단순히 장치 계정을 Surface Hub에 추가하는 것 이상으로 추가 구성을 요구하지 [alias@contoso.com.](mailto:alias@contoso.com)</span><span class="sxs-lookup"><span data-stu-id="59d30-108">For new cloud-based accounts, the Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply adding the device account to the Surface Hub using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="59d30-109">최신 인증에 지원되지 않는 레거시 형식인 Contoso\alias를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59d30-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="59d30-110">자세한 내용은 장치 [계정 만들기 및 테스트를 참조하세요.](create-and-test-a-device-account-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="59d30-110">For more information, see [create and test a device account](create-and-test-a-device-account-surface-hub.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59d30-111">최신 인증은 사내 Surface Hub 계정에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59d30-111">Modern authentication is not supported for on-premises Surface Hub accounts.</span></span> <span data-ttu-id="59d30-112">계정은 인증에 Azure AD만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d30-112">The accounts must use only Azure AD for authentication.</span></span>
