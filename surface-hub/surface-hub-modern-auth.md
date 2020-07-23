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
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893155"
---
# <span data-ttu-id="a931c-104">Surface Hub의 최신 인증</span><span class="sxs-lookup"><span data-stu-id="a931c-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="a931c-105">클라우드 기반 계정에 대 한 최신 인증 지원은 Windows 10 Team 2020 업데이트에서 완벽 하 게 통합 되어 레거시 기본 인증에서 마이그레이션하고 Microsoft Azure 및 Exchange Online의 최신 보안 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a931c-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="a931c-106">2020 업데이트를 사용 하는 Surface Hub는 exchange Online for Device 계정 동기화를 사용 하도록 설정 하는 웹 서비스 (EWS) 프로토콜 및 ADAL (Active Directory Authentication Library) 기반 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a931c-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="a931c-107">새로운 클라우드 기반 계정의 경우 Surface Hub는 자동으로 최신 인증을 사용 하 여 [alias@contoso.com](mailto:alias@contoso.com)형식으로 디바이스 계정을 만드는 것 외에 추가 구성을 요구 하지 않고 Exchange Online에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a931c-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="a931c-108">최신 인증에 지원 되지 않는 레거시 형식-Contoso\alias를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a931c-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="a931c-109">자세한 내용은 [Surface Hub 2S 디바이스 계정 만들기](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a931c-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="a931c-110">Surface Hub는 온-프레미스 계정에 대 한 최신 인증을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a931c-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="a931c-111">계정은 클라우드에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a931c-111">The accounts must be created in the cloud.</span></span>

