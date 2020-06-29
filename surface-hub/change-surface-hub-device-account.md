---
title: Microsoft Surface Hub 디바이스 계정 변경
description: 설정에서 디바이스 계정을 변경하면 아직 프로비전되지 않은 경우 계정을 추가하거나, 이미 프로비전된 계정의 속성을 변경할 수 있습니다.
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: 디바이스 계정 변경, 속성 변경, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836751"
---
# Microsoft Surface Hub 디바이스 계정 변경


설정에서 디바이스 계정을 변경하면 아직 프로비전되지 않은 경우 계정을 추가하거나, 이미 프로비전된 계정의 속성을 변경할 수 있습니다.

## 세부 정보


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">값</th>
<th align="left">설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>사용자 계정 이름</p></td>
<td align="left"><p>디바이스 계정의 UPN(사용자 계정 이름)입니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>암호</p></td>
<td align="left"><p>디바이스 계정의 암호입니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>도메인</p></td>
<td align="left"><p>디바이스 계정이 속하는 도메인입니다. Office 365 계정의 경우 이 필드를 제공할 필요가 없습니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>사용자 이름</p></td>
<td align="left"><p>디바이스 계정의 사용자 이름입니다. Office 365 계정의 경우 이 필드를 제공할 필요가 없습니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SIP(Session Initiation Protocol) 주소</p></td>
<td align="left"><p>디바이스 계정의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Exchange Server</p></td>
<td align="left"><p>디바이스 계정의 Exchange 서버입니다. 디바이스 계정의 사용자 이름 및 암호를 지정된 Exchange 서버에 인증할 수 있어야 합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Exchange 서비스 사용</p></td>
<td align="left"><p>선택하면 모든 Exchange 서비스를 사용할 수 있습니다(예: 시작 화면의 일정, 화이트보드를 메일로 보내기). 선택하지 않으면 모든 Exchange 서비스를 사용할 수 없으며 Exchange 서버를 제공할 필요가 없습니다.</p></td>
</tr>
</tbody>
</table>

 

## 발생하는 동작


UPN과 암호를 사용하여 AD 또는 Azure AD에서 계정의 유효성을 검사합니다. 유효성 검사에 실패할 경우 도메인과 사용자 이름을 제공해야 할 수도 있습니다.

제공된 자격 증명을 사용하여 SIP 주소를 검색하려고 합니다. SIP 주소를 찾을 수 없는 경우 비즈니스용 Skype는 UPN를 SIP 주소로 사용합니다. 계정의 SIP 주소가 아닌 경우 SIP 주소를 제공해야 합니다.

디바이스가 로그인 자격 증명과 관련된 서버를 찾을 수 없는 경우 Exchange 서버 주소를 제공해야 합니다. Microsoft Surface Hub는 Exchange 서버를 사용하여 ActiveSync에 통신하며, ActiveSync는 디바이스에서 몇 가지 주요 기능을 사용하도록 설정합니다.

## 관련 항목


[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)

 

 





