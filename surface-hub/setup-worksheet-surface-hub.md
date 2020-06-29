---
title: 설치 워크시트(Surface Hub)
description: 사전 설치를 마쳤으며 Microsoft Surface Hub의 처음 설치를 시작할 준비가 되었으면 이 섹션에 나열된 모든 정보가 있는지 확인합니다.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: 설치 워크시트, 사전 설치, 처음 설치
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836447"
---
# 설치 워크시트(Surface Hub)


사전 설치를 마쳤으며 Microsoft Surface Hub의 처음 설치를 시작할 준비가 되었으면 이 섹션에 나열된 모든 정보가 있는지 확인합니다.

프록시 정보 또는 도메인 자격 증명과 같은 일부 정보는 모든 Surface Hub에서 사용할 수 있지만, 구성해야 하는 각 Surface Hub에 대해 하나의 목록을 채워야 합니다. 결정한 디바이스 구성 방법에 따라 또는 조직의 인프라에 대한 사용자 환경 구성 방법에 따라 이 정보 중 일부는 필요하지 않을 수도 있습니다.

<table>
<tr>
<th>속성</th>
<th>용도</th>
<th>예제</th>
<th>실제 값</th>
</tr>
<tr>
<td>
<p>프록시 정보</p>
</td>
<td>
<p>네트워크에서 네트워크 및/또는 인터넷 액세스에 프록시를 사용하는 경우 스크립트 또는 서버/포트 정보를 제공해야 합니다.</p>
</td>
<td>
<p>프록시 스크립트: <code>http://contoso/proxy.pa</code> </br>
- 또는 - </br>
서버 및 포트 정보: 10.10.10.100, 포트 80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>무선 네트워크 자격 증명(사용자 이름 및 암호)</p>
</td>
<td>
<p>디바이스를 Wi-Fi에 연결하려는 경우 무선 네트워크에 사용자 자격 증명이 필요합니다.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>디바이스 계정 UPN 또는 도메인\사용자 이름과 디바이스 계정 암호</p>
</td>
<td>
<p>UPN(사용자 계정 이름) 또는 도메인\사용자 이름과 디바이스 계정의 암호입니다. 메일, 일정 및 비즈니스용 Skype는 호환되는 디바이스 계정에 따라 달라집니다.</p>
</td>
<td>
<p> UPN: ConfRoom15@contoso.com, #Passw0rd1 </br>
- 또는 - <br> 
도메인 및 사용자 이름: CONTOSO\ConfRoom15, #Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>디바이스 계정 Microsoft Exchange 서버</p>
</td>
<td>
<p>디바이스 계정의 Exchange 서버입니다.
메일, 일정 및 비즈니스용 Skype는 호환되는 디바이스 계정에 따라 달라집니다.
메일 및 일정이 작동하려면 디바이스 계정에 유효한 Exchange 서버가 있어야 합니다. 디바이스는 이 서버를 자동으로 찾으려고 합니다.</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>디바이스 계정 SIP(Session Initiation Protocol) 주소</p>
</td>
<td>
<p>디바이스 계정의 비즈니스용 Skype SIP 주소입니다.
메일, 일정 및 비즈니스용 Skype는 호환되는 디바이스 계정에 따라 달라집니다.
비즈니스용 Skype가 작동하려면 디바이스 계정에 유효한 SIP 주소가 있어야 합니다. 디바이스는 이 서버를 자동으로 찾으려고 합니다.</p>
</td>
<td>
<p>SIP: ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>이름</p>
</td>
<td>
<p>디바이스 이름은 사용자가 Surface Hub에 무선으로 연결하려고 할 때 표시되는 브로드캐스트 이름입니다. 이 이름은 Surface Hub 화면에 명확하게 표시됩니다.
사용자가 연결하려고 할 때 Surface Hub 간에 구분할 수 있도록 인식 가능한 고유한 이름을 선택하는 것이 좋습니다.</p>
</td>
<td>
<p>회의실 15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>디바이스 이름</p>
</td>
<td>
<p>디바이스 이름은 도메인 가입에 사용되는 이름이며, 디바이스가 MDM에 등록된 경우 MDM 공급자에 표시되는 ID입니다.
선택한 디바이스 이름은 사용자의 Active Directory 도메인에 있는 다른 디바이스의 이름과 달라야 합니다(디바이스를 도메인에 가입하려는 경우). 이름이 고유하지 않은 디바이스는 도메인에 가입할 수 없습니다.
</p>
</td>
<td>
<p>confroom15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>AZURE AD에 가입하는 경우</b></p>
</td>
</tr>
<tr>
<td>
<p>Azure AD 테넌트 사용자 자격 증명(사용자 이름 및 암호)</p>
</td>
<td>
<p>Azure AD(Azure Active Directory) 조직의 사용자가 디바이스 관리자가 되게 하려는 경우 Azure AD에 가입해야 합니다.
Azure AD에 가입하려면 유효한 사용자 자격 증명이 필요합니다.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>도메인에 가입하는 경우</b></p>
</td>
</tr>
<tr>
<td>
<p>가입할 도메인</p>
</td>
<td>
<p>선택한 보안 그룹이 디바이스 관리자가 될 수 있도록 가입해야 하는 도메인입니다.
FQDN(정규화된 도메인 이름)이 필요할 수도 있습니다.</p>
</td>
<td>
<p>contoso(짧은 이름) 또는 contoso.corp.com(FQDN)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>도메인 계정 자격 증명(사용자 이름 및 암호)</p>
</td>
<td>
<p>도메인에 가입하기에 충분한 계정 자격 증명을 제공하지 않을 경우 도메인에 가입할 수 없습니다. 가입할 도메인과 도메인에 가입할 자격 증명을 제공하고 나면 선택한 보안 그룹이 디바이스의 설정을 변경할 수 있습니다.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>관리자 보안 그룹 별칭</p>
</td>
<td>
<p>AD(Active Directory)의 보안 그룹으로, 이 보안 그룹의 모든 구성원이 디바이스의 설정을 변경할 수 있습니다.</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>로컬 관리자를 사용하는 경우</b></p>
</td>
</tr>
<tr>
<td>
<p>로컬 관리자 계정 자격 증명(사용자 이름 및 암호)</p>
</td>
<td>
<p>AD 도메인 또는 Azure AD에 가입하지 않으려는 경우 디바이스에서 로컬 관리자 계정을 만들 수 있습니다.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>인증서 또는 앱을 설치해야 하는 경우</b></p>
</td>
</tr>
<tr>
<td>
<p>USB 드라이브</p>
</td>
<td>
<p>첫 실행 전에 인증서 또는 유니버설 앱을 설치하려는 것을 알고 있다면 <a href="provisioning-packages-for-certificates-surface-hub.md">프로비저닝 패키지 만들기</a>의 단계를 따르세요. 프로비저닝 패키지는 USB 드라이브에 만들어집니다.</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





