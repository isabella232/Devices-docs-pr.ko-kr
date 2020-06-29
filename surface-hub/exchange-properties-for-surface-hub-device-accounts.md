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
# Microsoft Exchange 속성(Surface Hub)


Microsoft Surface Hub에서 최상의 모임 환경을 사용하려면 디바이스 계정의 일부 Microsoft Exchange 속성을 특정 값으로 설정해야 합니다. 다음 표에는 PowerShell cmdlet 매개 변수, 해당 용도 및 설정해야 하는 값에 따라 다양한 Exchange 속성이 나와 있습니다.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">속성</th>
<th align="left">설명</th>
<th align="left">값</th>
<th align="left">영향</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>AutomateProcessing 매개 변수는 사서함에서 일정 처리를 사용하거나 사용하지 않도록 설정합니다.</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>Surface Hub는 가용성에 따라 모임 요청을 자동으로 수락하거나 거부할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>AddOrganizerToSubject 매개 변수는 모임 이끌이의 이름을 모임 요청의 제목으로 사용할지 여부를 지정합니다.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>시작 화면에 모임 이끌이가 두 번 표시되지 않습니다(이끌이와 모임 제목 둘 다로 표시 안 함).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>AllowConflicts 매개 변수는 충돌하는 모임 요청을 허용할지 여부를 지정합니다.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Surface Hub는 다른 모임 시간과 충돌하는 모임 요청을 거부합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>DeleteComments 매개 변수는 들어오는 모임 요청의 메시지 본문에서 텍스트를 제거할지 또는 유지할지를 지정합니다.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>모임의 메시지 본문을 유지하고 모임 중에 필요한 경우 Surface Hub에서 검색할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>DeleteSubject 매개 변수는 들어오는 모임 요청의 제목을 제거할지 또는 유지할지를 지정합니다.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Surface Hub에서 모임 요청 제목을 표시할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>RemovePrivateProperty 매개 변수는 들어오는 모임 요청에 대한 비공개 플래그를 지울지 여부를 지정합니다.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>비공개 모임 제목은 시작 화면에 비공개로 표시됩니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>AddAdditionalResponse 매개 변수는 모임 요청에 응답할 때 리소스 사서함에서 추가 정보를 보낼지 여부를 지정합니다.</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>모임 요청에 응답을 보내는 경우 응답으로 사용자 지정 텍스트가 제공됩니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>AdditionalResponse 매개 변수는 모임 요청에 대한 응답에 포함할 추가 정보를 지정합니다.</p>
<div class="alert">
<strong>참고 </strong> AddAdditionalResponse가 $True으로 설정 되지 않은 경우이 텍스트는 전송 되지 않습니다.
</div>
<div>
 
</div></td>
<td align="left"><p>사용자 선택 - 추가 응답을 사용하여 Surface Hub를 사용하거나 리소스를 가리키는 방법을 사용자에게 알릴 수 있습니다.</p></td>
<td align="left"><p>응답 메시지를 더 추가하여 모임에서 Surface Hub를 사용하는 방법을 소개할 수 있습니다.</p></td>
</tr>
</tbody>
</table>

 

 

 





