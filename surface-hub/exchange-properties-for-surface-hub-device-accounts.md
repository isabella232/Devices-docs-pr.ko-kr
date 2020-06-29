---
title: Microsoft Exchange 속성(Surface Hub)
description: Microsoft Surface Hub에서 최상의 모임 환경을 사용하려면 디바이스 계정의 일부 Microsoft Exchange 속성을 특정 값으로 설정해야 합니다.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Microsoft Exchange 속성, 디바이스 계정, Surface Hub, Windows PowerShell cmdlet
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836239"
---
# <span data-ttu-id="2ef4c-104">Microsoft Exchange 속성(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="2ef4c-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="2ef4c-105">Microsoft Surface Hub에서 최상의 모임 환경을 사용하려면 디바이스 계정의 일부 Microsoft Exchange 속성을 특정 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="2ef4c-106">다음 표에는 PowerShell cmdlet 매개 변수, 해당 용도 및 설정해야 하는 값에 따라 다양한 Exchange 속성이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2ef4c-107">속성</span><span class="sxs-lookup"><span data-stu-id="2ef4c-107">Property</span></span></th>
<th align="left"><span data-ttu-id="2ef4c-108">설명</span><span class="sxs-lookup"><span data-stu-id="2ef4c-108">Description</span></span></th>
<th align="left"><span data-ttu-id="2ef4c-109">값</span><span class="sxs-lookup"><span data-stu-id="2ef4c-109">Value</span></span></th>
<th align="left"><span data-ttu-id="2ef4c-110">영향</span><span class="sxs-lookup"><span data-stu-id="2ef4c-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2ef4c-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="2ef4c-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-112">AutomateProcessing 매개 변수는 사서함에서 일정 처리를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="2ef4c-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-114">Surface Hub는 가용성에 따라 모임 요청을 자동으로 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2ef4c-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="2ef4c-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-116">AddOrganizerToSubject 매개 변수는 모임 이끌이의 이름을 모임 요청의 제목으로 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-117">$False</span><span class="sxs-lookup"><span data-stu-id="2ef4c-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-118">시작 화면에 모임 이끌이가 두 번 표시되지 않습니다(이끌이와 모임 제목 둘 다로 표시 안 함).</span><span class="sxs-lookup"><span data-stu-id="2ef4c-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2ef4c-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="2ef4c-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-120">AllowConflicts 매개 변수는 충돌하는 모임 요청을 허용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-121">$False</span><span class="sxs-lookup"><span data-stu-id="2ef4c-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-122">Surface Hub는 다른 모임 시간과 충돌하는 모임 요청을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2ef4c-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="2ef4c-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-124">DeleteComments 매개 변수는 들어오는 모임 요청의 메시지 본문에서 텍스트를 제거할지 또는 유지할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-125">$False</span><span class="sxs-lookup"><span data-stu-id="2ef4c-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-126">모임의 메시지 본문을 유지하고 모임 중에 필요한 경우 Surface Hub에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2ef4c-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="2ef4c-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-128">DeleteSubject 매개 변수는 들어오는 모임 요청의 제목을 제거할지 또는 유지할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-129">$False</span><span class="sxs-lookup"><span data-stu-id="2ef4c-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-130">Surface Hub에서 모임 요청 제목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2ef4c-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="2ef4c-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-132">RemovePrivateProperty 매개 변수는 들어오는 모임 요청에 대한 비공개 플래그를 지울지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-133">$False</span><span class="sxs-lookup"><span data-stu-id="2ef4c-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-134">비공개 모임 제목은 시작 화면에 비공개로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2ef4c-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="2ef4c-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-136">AddAdditionalResponse 매개 변수는 모임 요청에 응답할 때 리소스 사서함에서 추가 정보를 보낼지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-137">$True</span><span class="sxs-lookup"><span data-stu-id="2ef4c-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-138">모임 요청에 응답을 보내는 경우 응답으로 사용자 지정 텍스트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2ef4c-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="2ef4c-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-140">AdditionalResponse 매개 변수는 모임 요청에 대한 응답에 포함할 추가 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="2ef4c-141">참고 </strong> AddAdditionalResponse가 $True으로 설정 되지 않은 경우이 텍스트는 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="2ef4c-142">사용자 선택 - 추가 응답을 사용하여 Surface Hub를 사용하거나 리소스를 가리키는 방법을 사용자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2ef4c-143">응답 메시지를 더 추가하여 모임에서 Surface Hub를 사용하는 방법을 소개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ef4c-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





