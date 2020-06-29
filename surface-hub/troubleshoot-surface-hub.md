---
title: Microsoft Surface Hub 문제 해결
description: 설치 문제, Exchange ActiveSync 오류를 포함하여 일반적인 문제를 해결합니다.
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: 일반적인 문제, 설치 문제, Exchange ActiveSync 오류를 해결합니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834892"
---
# Microsoft Surface Hub 문제 해결


설치 문제, Exchange ActiveSync 오류를 포함하여 일반적인 문제를 해결합니다.

[Surface Hub 하드웨어 진단 도구](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab)에는 Hub의 필수 기능이 예상대로 작동하는지 확인할 수 있는 대화형 테스트가 포함되어 있습니다. 진단 도구는 하드웨어를 테스트하는 것 외에도 리소스 계정을 테스트하여 자신의 환경에 맞게 올바르게 구성되었는지 확인할 수 있습니다. 문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다. 사용 정보는 [Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun)를 참조하세요.

일반적인 문제는 원인 및 가능한 수정 사항과 함께 다음 표에 나와 있습니다. [설치 문제 해결](#setup-troubleshooting) 섹션에는 첫 실행 경험 중에 발생할 수 있는 여러 유형의 문제와 함께 디바이스 내 문제 목록이 포함되어 있습니다. [Exchange ActiveSync 오류](#exchange-activesync-errors) 섹션에는 디바이스가 Microsoft Exchange ActiveSync 서버와 동기화하려고 할 때 발생할 수 있는 일반적인 오류 목록이 포함되어 있습니다.




## 설치 문제 해결


이 섹션에는 Microsoft Surface Hub를 설치할 때 발생할 수 문제를 해결하는 데 도움이 되는 원인 및 가능한 수정 사항이 나와 있습니다.

### 디바이스 내

첫 실행 프로그램을 완료한 후 Surface Hub의 문제에 대한 가능한 수정 사항입니다.

<table>
<tr>
<th>문제</th>
<th>원인</th>
<th>가능한 수정 사항</th>
</tr>
<tr>
<td rowspan="2">
<p>자동 수락/거절 메시지가 수신되지 않습니다.</p>
</td>
<td>
<p>디바이스 계정이 메시지를 자동으로 수락/거절하도록 구성되지 않았습니다.</p>
</td>
<td>
<p>PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>를 사용합니다.</p>
</td>
</tr>
<tr>
<td>
<p>디바이스 계정이 외부 모임 요청을 처리하도록 구성되지 않았습니다.</p>
</td>
<td>
<p>PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>를 사용합니다.</p>
</td>
</tr>
<tr>
<td>
<p>시작 화면에 일정이 표시되지 않거나 “약속이 최신 상태가 아님(계정이 프로비전되지 않음)” 메시지가 표시됩니다.</p>
</td>
<td>
<p>이 Surface Hub에서 디바이스 계정이 설정되지 않았습니다.</p>
</td>
<td>
<p>설정을 통해 디바이스 계정을 프로비전합니다.</p>
</td>
</tr>
<tr>
<td>
<p>시작 화면에 일정이 표시되지 않거나 “약속이 최신 상태가 아님(과도하게 프로비전됨)” 메시지가 표시됩니다.</p>
</td>
<td>
<p>너무 많은 디바이스에서 디바이스 계정이 프로비전되었습니다.</p>
</td>
<td>
<p>프로비전된 다른 디바이스에서 디바이스 계정을 제거합니다. Exchange 관리 포털을 사용하여 이 작업을 수행할 수 있습니다.</p>
</td>
</tr>
<tr>
<td>
<p>시작 화면에 일정이 표시되지 않거나 “약속이 최신 상태가 아님(잘못된 자격 증명)” 메시지가 표시됩니다.</p>
</td>
<td>
<p>디바이스 계정의 암호가 만료되었으며 더 이상 유효하지 않습니다.</p>
</td>
<td>
<p>설정에서 계정의 암호를 업데이트합니다. <a href="password-management-for-surface-hub-device-accounts.md">암호 관리</a>를 참조하세요.</p>
</td>
</tr>
<tr>
<td>
<p>시작 화면에 일정이 표시되지 않거나 “약속이 최신 상태가 아님(계정 정책)” 메시지가 표시됩니다.</p>
</td>
<td>
<p>디바이스 계정이 잘못된 ActiveSync 정책을 사용하고 있습니다.</p>
</td>
<td>
<p>디바이스 계정에 <code>PasswordEnabled == False</code>인 ActiveSync 정책이 있는지 확인합니다.</p>
</td>
</tr>
<tr>
<td>
<p>시작 화면에 일정이 표시되지 않거나 “약속이 최신 상태가 아닐 수도 있습니다.” 메시지가 표시됩니다.</p>
</td>
<td>
<p>Exchange를 사용할 수 없습니다.</p>
</td>
<td>설정을 통해 Exchange 서비스에 디바이스 계정을 사용하도록 설정합니다. 올바른 ActiveSync 정책 집합이 있고 Exchange 서비스가 작동하는 데 필요한 인증서도 모두 설치했는지 확인해야 합니다.</td>
</tr>
<tr>
<td>
<p>비즈니스용 Skype에 로그인할 수 없습니다.</p>
</td>
<td>
<p>디바이스 계정에 SIP(Session Initiation Protocol) 주소 속성이 없습니다.</p>
</td>
<td>
<p>계정에 SIP 주소 속성이 없으며 해당 UPN(사용자 계정 이름)이 실제 SIP 주소와 일치하지 않습니다. 계정에 SIP 주소가 설정되어 있어야 하거나, 설정 앱을 사용하여 SIP 주소를 추가해야 합니다.</p>
</td>
</tr>
<tr>
<td>
<p>비즈니스용 Skype에 로그인할 수 없습니다.</p>
</td>
<td>
<p>디바이스 계정이 비즈니스용 Skype에 인증하려면 인증서가 필요합니다.</p>
</td>
<td>
<p>프로비저닝 패키지를 사용하여 해당 인증서를 설치합니다.</p>
</td>
</tr>
</table>
 

### 첫 실행

Surface Hub 첫 실행 프로그램과 관련된 문제에 대한 가능한 수정 사항입니다.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">문제</th>
<th align="left">원인</th>
<th align="left">가능한 수정 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>도메인 및 사용자 이름을 묻는 메시지가 표시될 때 계정을 찾을 수 없습니다.</p></td>
<td align="left"><p>도메인은 FQDN(정규화된 도메인 이름)이어야 합니다.</p></td>
<td align="left"><p>도메인 필드에 FQDN을 입력해야 합니다.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a>디바이스 계정 페이지, 새 계정 설정과 관련된 문제

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">문제</th>
<th align="left">원인</th>
<th align="left">가능한 수정 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Azure AD에서 제공된 계정을 찾을 수 없습니다.</p></td>
<td align="left"><p>제공된 계정의 UPN(사용자 계정 이름)에 Azure AD에서 연결할 수 없는 테넌트가 있습니다.</p></td>
<td align="left"><p>작동하는 인터넷 연결이 있고 디바이스가 Microsoft Online Services에 연결할 수 있는지 확인합니다. 계정 자격 증명을 올바르게 입력했는지 확인합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>지정된 디렉터리에 연결할 수 없습니다.</p></td>
<td align="left"><p>제공된 계정 도메인이 연결할 수 없는 도메인을 지정합니다.</p></td>
<td align="left"><p>작동하는 네트워크 연결이 있고 디바이스가 도메인 컨트롤러에 연결할 수 있는지 확인합니다. 계정 자격 증명을 올바르게 입력했는지 확인합니다. 대신 FQDN를 사용할 수도 있습니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Exchange 서버를 자동 검색할 수 없습니다.</p></td>
<td align="left"><p>Exchange 서버가 자동 검색되도록 구성되지 않았습니다.</p></td>
<td align="left"><p>디바이스 계정에 Exchange 서버 자동 검색을 사용하도록 설정하거나, 계정의 Exchange 서버 주소를 수동으로 입력합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>계정 자격 증명을 입력한 후 SIP 주소를 검색할 수 없습니다.</p></td>
<td align="left"><p>Active Directory 또는 Azure AD에 SIP 주소 항목이 없습니다.</p></td>
<td align="left"><p>비즈니스용 Skype로 계정을 사용할 수 있으며 SIP 주소가 있는지 확인합니다. 그렇지 않으면 텍스트 상자에 수동으로 SIP 주소를 입력할 수 있습니다.</p></td>
</tr>
</tbody>
</table>

 

### 디바이스 계정 페이지, 기존 계정 설정과 관련된 문제

<table>
<tr>
<th>문제</th>
<th>원인</th>
<th>오류 코드</th>
<th>가능한 수정 사항</th>
</tr>
<tr>
<td>
<p>계정이 지정된 자격 증명을 사용하여 인증할 수 없습니다.</p>
</td>
<td>
<p>계정이 AD(Active Directory)에서 사용자로 설정되지 않았거나, 인증하려면 암호가 필요하거나, 암호가 잘못되었습니다.</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>자격 증명을 올바르게 입력했는지 확인합니다. AD에서 계정을 사용자로 설정하고 암호를 추가하거나, RoomMailboxPassword를 설정합니다</p>. </td>
</tr>
<tr>
<td>
<p>Exchange 서버를 제공할 때 0x800C0019 오류가 표시됩니다.</p>
</td>
<td>
<p>디바이스 계정이 인증하려면 인증서가 필요합니다.</p>
</td>
<td>
<p>0x800C0019</p>
</td>
<td>
<p>프로비저닝 패키지를 사용하여 해당 인증서를 설치합니다.</p>
</td>
</tr>
<tr>
<td>
<p>디바이스 계정 자격 증명이 제공된 Exchange 서버에 유효하지 않습니다.</p>
</td>
<td>
<p>제공된 Exchange 서버는 디바이스 계정의 사서함이 호스트된 위치가 아닙니다.</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>디바이스 계정에 대한 올바른 Exchange 메일 서버를 제공하고 있는지 확인합니다.</p>
</td>
</tr>
<tr>
<td>
<p>Exchange 서버에 연결하는 동안 HTTP 시간이 초과되었습니다.</p>
</td>
<td></td>
<td>
<p>0x80072EE2</p>
</td>
<td></td>
</tr>
<tr>
<td>
<p>제공된 Exchange 서버를 찾을 수 없습니다.</p>
</td>
<td>
<p>제공된 Exchange 서버를 찾을 수 없습니다.</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>작동하는 네트워크 또는 인터넷 연결이 있는지, 그리고 제공한 Exchange 서버가 올바른지 확인합니다.</p>
</td>
</tr>
<tr>
<td>
<p>http는 지원되지 않습니다.</p>
</td>
<td>
<p><i>https://</i>가 아니라 <i>http://</i>를 사용하는 Exchange 서버를 제공했습니다.</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>https를 사용하는 Exchange 서버를 사용합니다.</p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p>사용자가 ActiveSync와 관련된 “이 계정에 문제가 있습니다.” 페이지로 이동됩니다.</p>
</div>
<div> </div>
</td>
<td>
<p>ActiveSync 정책 PasswordEnabled가 True(또는 1)로 설정되었습니다.</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>PasswordEnabled가 False(또는 0)로 설정된 새 ActiveSync 정책을 만들고 계정에 해당 정책을 적용합니다.</p>
</td>
</tr>
<tr>
<td>
<p>Surface Hub에 Exchange 연결이 없습니다.</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>작동하는 네트워크 또는 인터넷 연결이 있는지 확인합니다.</p>
</td>
</tr>
<tr>
<td>
<p>Exchange에서 오류를 나타내는 상태 코드를 반환하는 경우</p>
</td>
<td>
<p>없음</p>
</td>
<td>
<p>작동하는 네트워크 또는 인터넷 연결이 있는지 확인합니다.</p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a>첫 실행, 도메인 가입 페이지 문제

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">문제</th>
<th align="left">원인</th>
<th align="left">가능한 수정 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>도메인에 가입하려고 하면 계정이 지정된 자격 증명을 사용하여 인증할 수 없다는 오류가 표시됩니다.</p></td>
<td align="left"><p>제공된 자격 증명은 지정된 도메인에 가입할 수 없습니다.</p></td>
<td align="left"><p>지정된 도메인에 있는 계정의 올바른 자격 증명을 입력합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>도메인의 그룹을 지정하는 경우 도메인에서 그룹을 찾을 수 없다는 오류가 표시됩니다.</p></td>
<td align="left"><p>그룹이 제거되었거나 더 이상 존재하지 않습니다.</p></td>
<td align="left"><p>그룹이 도메인 내에 있는지 확인합니다.</p></td>
</tr>
</tbody>
</table>

 

### 첫 실행, Exchange 서버 페이지

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">문제</th>
<th align="left">원인</th>
<th align="left">가능한 수정 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>사용자가 이 페이지로 이동되며 Exchange 서버 주소를 묻는 메시지가 표시됩니다.</p></td>
<td align="left"><p>Exchange 서버가 자동 검색되도록 구성되지 않았습니다.</p></td>
<td align="left"><p>디바이스 계정에 Exchange 서버 자동 검색을 사용하도록 설정하거나, 계정의 Exchange 서버 주소를 수동으로 입력합니다.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a>첫 실행, 디바이스 내 문제

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">문제</th>
<th align="left">원인</th>
<th align="left">오류 코드</th>
<th align="left">가능한 수정 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>메일/일정을 동기화할 수 없습니다.</p></td>
<td align="left"><p>계정이 Surface Hub를 허용된 디바이스로 허용하지 않았습니다.</p></td>
<td align="left"><p>0x86000C1C</p></td>
<td align="left"><p><strong>사서함에 대 한 ActiveSyncAllowedDeviceIds 속성을 설정 하 여 Surface Hub 디바이스 ID를 허용 목록에 추가 합니다 </strong> .</p></td>
</tr>
</tbody>
</table>

 



 

## Exchange ActiveSync 오류


이 섹션에는 상태 코드, 매핑, 사용자 메시지 및 관리자가 Exchange ActiveSync 오류를 해결하기 위해 수행할 수 있는 작업이 나와 있습니다.

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">16진수 코드</th>
<th align="left">매핑</th>
<th align="left">사용자에게 친숙한 메시지</th>
<th align="left">관리자가 수행해야 하는 작업</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0x85010002</p></td>
<td align="left"><p>E_HTTP_DENIED</p></td>
<td align="left"><p>암호를 업데이트해야 합니다.</p></td>
<td align="left"><p>암호를 업데이트합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072EFD</p></td>
<td align="left"><p>WININET_E_CANNOT_CONNECT</p></td>
<td align="left"><p>지금 바로 서버에 연결할 수 없습니다. 잠시 기다린 후 다시 시도하거나, 계정 설정을 확인합니다.</p></td>
<td align="left"><p>서버 이름이 올바르고 연결 가능한지 확인합니다. 디바이스가 네트워크에 연결되었는지 확인합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C29</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (정책이 일치 하지 않음)</p></td>
<td align="left"><p>계정이 Surface Hub와 호환되지 않는 정책으로 구성되었습니다.</p></td>
<td align="left"><p>이 계정에 <strong>PasswordEnabled</strong> 정책을 사용하지 않도록 설정합니다.</p>
<p>계정에서 정책 새로 고침 간격 내에 서버 알림을 받지 못하는 경우에는 버그에 정책 오류가 발생할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C4C</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</p></td>
<td align="left"><p>계정에 너무 많은 디바이스 파트너 관계가 있습니다.</p></td>
<td align="left"><p>서버에서 파트너 관계를 하나 이상 삭제합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C0A</p></td>
<td align="left"><p>E_NEXUS_STATUS_SERVERERROR_RETRYLATER</p></td>
<td align="left"><p>지금 바로 서버에 연결할 수 없습니다.</p></td>
<td align="left"><p>서버가 다시 온라인 상태가 될 때까지 기다립니다. 문제가 계속되면 계정을 다시 프로비전합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050003</p></td>
<td align="left"><p>E_CREDENTIALS_EXPIRED(자격 증명이 만료되었으며 업데이트해야 함)</p></td>
<td align="left"><p>암호를 업데이트해야 합니다.</p></td>
<td align="left"><p>암호를 업데이트합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x8505000D</p></td>
<td align="left"><p>E_AIRSYNC_RESET_RETRY</p></td>
<td align="left"><p>지금 바로 서버에 연결할 수 없습니다. 잠시 기다리거나 계정 설정을 확인 합니다.</p></td>
<td align="left"><p>일반적으로 일시적인 오류이지만, 문제가 지속될 경우 계정과 연결된 디바이스 수를 확인하고 개수가 많으면 일부를 삭제합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C16</p></td>
<td align="left"><p>E_NEXUS_STATUS_USER_HASNOMAILBOX</p></td>
<td align="left"><p>사서함이 다른 서버로 마이그레이션되었습니다.</p></td>
<td align="left"><p>이 오류가 표시되면 안 됩니다. 문제가 계속되면 계정을 다시 프로비전합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010004</p></td>
<td align="left"><p>E_HTTP_FORBIDDEN</p></td>
<td align="left"><p>지금 바로 서버에 연결할 수 없습니다. 잠시 기다린 후 다시 시도 하거나 계정 설정을 확인 합니다.</p></td>
<td align="left"><p>서버 이름이 올바른지 확인합니다. 계정이 인증서 기반 인증을 사용하는 경우 인증서가 여전히 유효한지 확인하고, 유효하지 않으면 업데이트합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85030028</p></td>
<td align="left"><p>E_ACTIVESYNC_PASSWORD_OR_GETCERT</p></td>
<td align="left"><p>계정의 암호 또는 클라이언트 인증서가 누락 되었거나 잘못 되었습니다.</p></td>
<td align="left"><p>암호를 업데이트하거나 클라이언트 인증서를 배포합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C2A</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_POLICYREFRESH</p></td>
<td align="left"><p>계정이 Surface Hub와 호환되지 않는 정책으로 구성되었습니다.</p></td>
<td align="left"><p>이 계정에 PasswordEnabled 정책을 사용하지 않도록 설정합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050002</p></td>
<td align="left"><p>E_CREDENTIALS_UNAVAILABLE</p></td>
<td align="left"><p>암호를 업데이트해야 합니다.</p></td>
<td align="left"><p>암호를 업데이트합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE2</p></td>
<td align="left"><p>WININET_E_TIMEOUT</p></td>
<td align="left"><p>네트워크는 서버 알림을 수신 하는 데 필요한 최소 유휴 시간 제한을 지원 하지 않거나 서버가 오프 라인 상태입니다.</p></td>
<td align="left"><p>서버가 실행되고 있는지 확인합니다. NAT 설정을 확인합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85002004</p></td>
<td align="left"><p>E_FAIL_ABORT</p></td>
<td align="left"><p>이 오류는 작동 중지된 동기화를 중단하는 데 사용되며 사용자에게 표시되지 않습니다. 대화형 동기화를 강제를 적용하거나, 계정을 삭제하거나, 해당 설정을 업데이트하는 경우 진단 데이터에 표시됩니다.</p></td>
<td align="left"><p>없음</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010017</p></td>
<td align="left"><p>E_HTTP_SERVICE_UNAVAIL</p></td>
<td align="left"><p>지금 바로 서버에 연결할 수 없습니다. 잠시 기다리거나 계정 설정을 확인 합니다.</p></td>
<td align="left"><p>서버 이름이 올바른지 확인합니다. 서버가 다시 온라인 상태가 될 때까지 기다립니다. 문제가 계속되면 계정을 다시 프로비전합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C0D</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</p></td>
<td align="left"><p>지금 바로 서버에 연결할 수 없습니다. 잠시 기다리거나 계정 설정을 확인 합니다.</p></td>
<td align="left"><p>서버 이름이 올바른지 확인합니다. 서버가 다시 온라인 상태가 될 때까지 기다립니다. 문제가 계속되면 계정을 다시 프로비전합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85030027</p></td>
<td align="left"><p>E_ACTIVESYNC_GETCERT</p></td>
<td align="left"><p>Exchange 서버에 인증서가 필요합니다.</p></td>
<td align="left"><p>Surface Hub에서 적절한 EAS 인증서를 가져옵니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C2B</p></td>
<td align="left"><p>E_NEXUS_STATUS_INVALID_POLICYKEY</p></td>
<td align="left"><p>계정이 Surface Hub와 호환되지 않는 정책으로 구성되었습니다.</p></td>
<td align="left"><p>이 계정에 PasswordEnabled 정책을 사용하지 않도록 설정합니다.</p>
<p>계정에서 정책 새로 고침 간격 내에 서버 알림을 받지 못하는 경우에는 버그에 정책 오류가 발생할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010005</p></td>
<td align="left"><p>E_HTTP_NOT_FOUND</p></td>
<td align="left"><p>서버 이름이 잘못되었습니다.</p></td>
<td align="left"><p>서버 이름이 올바른지 확인합니다. 문제가 계속되면 계정을 다시 프로비전합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85010014</p></td>
<td align="left"><p>E_HTTP_SERVER_ERROR</p></td>
<td align="left"><p>서버에 연결할 수 없습니다.</p></td>
<td align="left"><p>서버 이름이 올바른지 확인합니다. 동기화를 트리거하고, 문제가 계속되면 계정을 다시 프로비전합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE7</p></td>
<td align="left"><p>WININET_E_NAME_NOT_RESOLVED</p></td>
<td align="left"><p>서버 이름 또는 주소를 확인할 수 없습니다.</p></td>
<td align="left"><p>서버 이름을 올바르게 입력했는지 확인합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x8007052F</p></td>
<td align="left"><p>ERROR_ACCOUNT_RESTRICTION</p></td>
<td align="left"><p>Exchange 서버를 자동 검색하는 동안 로그인한 사용자가 서버에 로그인할 수 없도록 하는 정책이 적용됩니다.</p></td>
<td align="left"><p>타이밍 문제입니다. 계정의 자격 증명을 다시 확인합니다. 올바른 경우 다시 프로비전합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x800C0019</p></td>
<td align="left"><p>INET_E_INVALID_CERTIFICATE</p></td>
<td align="left"><p>이 리소스에 액세스하는 데 필요한 보안 인증서가 잘못되었습니다.</p></td>
<td align="left"><p>제공된 디바이스 계정에 필요한 올바른 ActiveSync 인증서를 설치합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072F0D</p></td>
<td align="left"><p>WININET_E_INVALID_CA</p></td>
<td align="left"><p>인증 기관이 유효하지 않거나 잘못되었습니다. 인증서가 없으므로 Exchange 서버를 자동 검색할 수 없습니다.</p></td>
<td align="left"><p>제공된 디바이스 계정에 필요한 올바른 ActiveSync 인증서를 설치합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80004005</p></td>
<td align="left"><p>E_FAIL</p></td>
<td align="left"><p>제공된 도메인을 찾을 수 없습니다. Exchange 서버를 자동 검색할 수 없으며 설정에서 제공되지 않았습니다.</p></td>
<td align="left"><p>입력한 도메인이 FQDN인지, 그리고 Exchange 서버 텍스트 상자에 Exchange 서버가 입력되었는지 확인합니다.</p></td>
</tr>
</tbody>
</table>

## 고객 지원 문의

질문이 있거나 도움이 필요한 경우 [지원 요청을 만들](https://support.microsoft.com/supportforbusiness/productselection)수 있습니다.


 
## 관련 콘텐츠

- [Miracast의 Surface Hub 연결 문제 해결](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





