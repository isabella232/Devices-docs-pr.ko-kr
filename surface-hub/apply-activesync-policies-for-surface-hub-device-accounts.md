---
title: 디바이스 계정에 ActiveSync 정책 적용(Surface Hub)
description: Microsoft Surface Hub의 디바이스 계정은 ActiveSync를 사용하여 메일과 일정을 동기화합니다. 이렇게 하면 사용자가 Surface Hub에서 예약된 모임에 참가하고 시작할 수 있으며, 모임 중에 작성한 모든 화이트보드를 메일로 보낼 수 있습니다.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, ActiveSync 정책
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474735"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="8b762-105">디바이스 계정에 ActiveSync 정책 적용(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="8b762-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="8b762-106">Active Directory 장치 **계정(도메인\사용자** 이름 형식으로 허브에 프로비전) 및 온-프레미스 Exchange 서비스를 사용하는 Surface Hub는 ActiveSync를 사용하여 메일 및 일정을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-106">Surface Hubs using Active Directory device accounts (provisioned on the Hub in **domain\username** format) and on-premises Exchange services make use of ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="8b762-107">이렇게 하면 사용자가 Surface Hub에서 예약된 모임에 참가하고 시작할 수 있으며, 모임 중에 작성한 모든 화이트보드를 메일로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="8b762-108">이러한 기능이 작동하려면 조직에 대한 ActiveSync 정책을 다음과 같이 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="8b762-109">Surface Hub의 디바이스 계정이 사용하는 리소스 사서함의 동기화를 차단하는 전역 정책이 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="8b762-110">이러한 차단 정책이 있는 경우 Surface Hub를 허용된 장치로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="8b762-111">**PasswordEnabled** 설정이 False로 설정된 모바일 디바이스 사서함 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="8b762-112">기타 모바일 디바이스 사서함 정책 설정은 Surface Hub와 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="8b762-113">DeviceID 허용</span><span class="sxs-lookup"><span data-stu-id="8b762-113">Allowing the DeviceID</span></span>

<span data-ttu-id="8b762-114">조직에 Surface Hub에서 프로비전된 디바이스 계정의 동기화를 차단하는 전역 정책이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="8b762-115">이 속성을 구성하려면 [ActiveSync에 디바이스 ID 허용](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b762-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="8b762-116">PasswordEnabled 설정</span><span class="sxs-lookup"><span data-stu-id="8b762-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="8b762-117">디바이스 계정에 **PasswordEnabled** 특성이 False 또는 0으로 설정된 ActiveSync 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b762-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="8b762-118">이 속성을 구성하려면 [Microsoft Surface Hub 호환 Exchange ActiveSync 정책 만들기](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b762-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





