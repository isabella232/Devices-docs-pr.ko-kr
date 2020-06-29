---
title: Microsoft Surface Hub에 대한 환경 준비
description: 이 섹션에서는 Microsoft Surface Hub의 모든 기능을 사용할 수 있도록 환경을 준비하는 데 필요한 단계를 간략히 설명합니다.
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: 환경 준비, Surface Hub의 기능, 디바이스 계정 만들기 및 테스트, 네트워크 가용성 확인
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0ee406df6d3022f04a80f4ce253bd76f6473f1c8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836647"
---
# Microsoft Surface Hub에 대한 환경 준비


이 섹션에는 설정 종속성 및 설정 프로세스에 대한 개요가 포함되어 있습니다. 이 섹션의 정보를 검토하면 사용자 환경을 준비하고 Surface Hub를 설정하는 데 필요한 정보를 수집할 수 있습니다.


## 인프라 종속성 검토
이러한 종속성을 검토하여 Surface Hub 기능이 IT 인프라에서 작동하게 합니다.

| 종속성        | 목적           |
|-------------|------------------|
| Active Directory 또는 Azure AD(Azure Active Directory) | <p>Surface Hub는 Active Directory 또는 Azure AD 계정(**디바이스 계정**이라고 함)을 사용하여 비즈니스용 Skype와 Exchange 서비스에 액세스합니다. Surface Hub는 디바이스 계정 자격 증명의 유효성을 검사하고 디바이스 계정의 표시 이름, 별칭, Exchange 서버, SIP(Session Initiation Protocol) 주소 등의 정보에 액세스하기 위해 Active Directory 도메인 컨트롤러 또는 Azure AD 테넌트에 연결할 수 있어야 합니다.</p>또한 권한 부여된 사용자 그룹이 Surface Hub에 대한 설정을 구성할 수 있도록 Surface Hub를 도메인에 가입시키거나 Azure AD에 연결할 수 있습니다. |
| Exchange(Exchange 2013 이상 또는 Exchange Online) 및 Exchange ActiveSync | <p>Exchange를 통해 메일 및 일정 기능을 사용할 수 있으며, 디바이스 사용자가 Surface Hub에 모임 요청을 보내 원터치 모임 참가를 사용하도록 설정할 수도 있습니다.</p>ActiveSync는 디바이스 계정의 일정 및 메일을 Surface Hub에 동기화하는 데 사용됩니다. 디바이스가 ActiveSync를 사용할 수 없는 경우 시작 화면에 모임이 표시되지 않으며, 모임 참가 및 화이트보드를 메일로 보내기를 사용할 수 없습니다. |
| 비즈니스용 Skype(Lync Server 2013 이상 또는 비즈니스용 Skype Online)  | 비즈니스용 Skype는 화상 통화, 인스턴트 메시징, 화면 공유 등의 다양한 회의 기능에 사용됩니다.|
| MDM (모바일 디바이스 관리) 솔루션 (Microsoft Intune, Microsoft Endpoint Configuration Manager 또는 지원 되는 타사 MDM 공급자) | 원격으로 설정을 적용하고 앱을 설치하며 한 번에 여러 디바이스에 설정을 적용하고 앱을 설치하려면 MDM 솔루션을 설정하고 해당 솔루션에 디바이스를 등록해야 합니다. 자세한 정보는 [MDM 공급자 설정 관리](manage-settings-with-mdm-for-surface-hub.md)를 참조하세요. |
| Microsoft Operations Management Suite(OMS)   | OMS는 Surface Hub 디바이스의 상태를 모니터링하는 데 사용됩니다. 자세한 정보는 [Surface Hub 모니터링](monitor-surface-hub.md)을 참조하세요. |
| 네트워크 및 인터넷 액세스   | 제대로 작동하려면 Surface Hub가 유선 또는 무선 네트워크에 액세스할 수 있어야 합니다. 전반적으로 유선 연결을 사용하는 것이 좋습니다. 802.1X 인증은 유선 및 무선 연결에서 모두 지원됩니다.</br></br></br>**802.1X 인증:** Windows 10 버전 1703에서 유무선 연결에 대한 802.1X 인증은 Surface Hub에서 기본적으로 활성화됩니다. 조직에서 802.1X 인증을 사용하지 않는 경우 필요한 구성은 없으며 Surface Hub는 계속해서 정상적으로 작동합니다. 802.1X 인증을 사용하는 경우 Surface Hub에 인증서가 설치되어 있는지 확인해야 합니다. MDM에서 [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp)를 사용하여 Surface Hub에 인증서를 제공하거나 [프로비저닝 패키지를 만들고](provisioning-packages-for-surface-hub.md) 첫 번째 실행 시 또는 설정 앱을 통해 설치할 수 있습니다. Surface Hub에 인증서를 적용하면 802.1X 인증이 자동으로 작동되기 시작합니다.</br>**참고:** Surface Hub에서 802.1X 유선 인증 사용에 대한 자세한 내용은 [802.1x 유선 인증 사용](enable-8021x-wired-authentication.md)을 참조하십시오.</br></br>**동적 IP:** 고정 IP를 사용하도록 Surface Hub를 구성할 수 없습니다. DHCP를 사용하여 IP 주소를 할당해야 합니다.</br></br>**프록시 서버:** 토폴로지에서 인터넷 서비스에 연결하기 위해 프록시 서버에 연결해야 하는 경우 첫 번째 실행 중이나 설정에서 구성할 수 있습니다. 프록시 자격 증명은 Surface Hub 세션 전반에 걸쳐 저장되며 한 번만 설정하면 됩니다. |

또한 Surface Hub에 다음과 같이 열린 포트가 필요합니다.
- HTTPS: 443
- HTTP: 80
- NTP: 123

비즈니스용 Skype와 함께 Surface Hub를 사용 하는 경우에는 추가 포트를 열어야 합니다. 아래 지침을 따르세요.
- 비즈니스용 Skype Online을 사용 하는 경우 [Office 365 Ip url 및 ip 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)를 참조 하세요.
- 비즈니스용 Skype 서버를 사용 하는 경우 비즈니스용 [Skype server: 포트 및 내부 서버용 프로토콜](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols)을 참조 하세요. 
- 비즈니스용 Skype Online 및 비즈니스용 Skype Server를 사용 하는 경우 [Office 365 Ip url 및 ip 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) 및 [비즈니스용 Skype server: 포트 및 내부 서버용 프로토콜에 대해](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)문서화 된 모든 포트가 열려 있어야 합니다.

Microsoft는 Surface Hub 환경을 향상시키기 위해 진단 데이터를 수집합니다. 허용 목록에 이러한 사이트 추가:
- 진단 데이터 클라이언트 끝점: `https://vortex.data.microsoft.com/`
- 진단 데이터 설정 끝점: `https://settings.data.microsoft.com/`

### 프록시 구성

조직에서 네트워크의 컴퓨터가 인터넷에 연결하지 못하게 제한하면 비즈니스용 Microsoft Store를 사용하기 위해 장치에 사용 가능한 일련의 URL을 제공해야 합니다. 일부 비즈니스용 Store 기능에는 Microsoft Store 앱 및 Microsoft Store 서비스가 사용됩니다. 비즈니스용 Store를 사용하여 앱을 구입, 설치 또는 업데이트하는 장치에서는 이들 URL에 액세스할 수 있어야 합니다. 프록시 서버를 사용하여 트래픽을 차단하면 구성에서 이들 URL을 허용해야 합니다.

- login.live.com
- login.windows.net
- account.live.com
- clientconfig.passport.net
- windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com(Windows 10, 버전 1607 이전)
- www.msftconnecttest.com/connecttest.txt (Windows 10, 버전 1607부터 www.msftncsi.com 대체)


## 다른 관리자와 작업

Surface Hub는 몇 가지 서로 다른 제품 및 서비스와 상호작용합니다. 조직의 규모에 따라 여러 사용자가 사용자 환경의 여러 다른 제품을 지원할 수 있습니다. Surface Hub 배포를 계획하고 준비할 때 Exchange, Active Directory(또는 Azure Active Directory), MDM(모바일 디바이스 관리) 및 네트워크 리소스를 관리하는 직원을 포함해야 합니다. 


## 디바이스 계정 만들기 및 확인

디바이스 계정은 Surface Hub에서 회의 일정을 표시하고, 비즈니스용 Skype에 참여하며, 메일을 보내고 선택한 경우 Exchange 인증에 사용하는 Exchange 리소스 계정입니다. 자세한 내용은 [디바이스 계정 만들기 및 테스트](create-and-test-a-device-account-surface-hub.md)를 참조하세요.

장치 계정을 만든 후 올바르게 설치되어 있는지 확인하려면 Surface Hub 디바이스 계정 유효성 검사 PowerShell 스크립트를 실행합니다. 자세한 내용은 이 가이드의 뒷부분에 나오는 [Surface Hub용 PowerShell 스크립트](appendix-a-powershell-scripts-for-surface-hub.md)를 참조하세요. 

 

## 첫 실행 프로그램 준비 
[첫 실행 프로그램](first-run-program-surface-hub.md)을 시작하기 전에 몇 가지 항목을 고려해야 합니다.  

### 프로비저닝 패키지 만들기(옵션)
프로비저닝 패키지를 사용하여 인증서를 추가하고 설정을 사용자 지정하며 앱을 설치할 수 있습니다. 자세한 내용은 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md) 를 참조하세요. [첫 실행 시 프로비저닝 패키지를 설치](first-run-program-surface-hub.md#first-page)할 수 있습니다.

### 관리자 그룹 설정
디바이스에서 설정 앱을 사용하여 각 Surface Hub를 개별적으로 구성할 수 있습니다. 권한이 없는 사용자가 설정을 변경하지 못하도록 설정 앱에서는 관리자 자격 증명을 사용하여 앱을 열어야 합니다. 관리자 그룹을 설정하고 관리하는 방법에 대한 자세한 내용은 [관리자 그룹 관리](admin-group-management-for-surface-hub.md) 를 참조하세요. [첫 실행 시 디바이스의 관리자를 설정](first-run-program-surface-hub.md#setup-admins)합니다.

### Surface Hub 설정 워크시트를 검토하고 완료(옵션)
Surface Hub의 첫 실행 프로그램을 진행할 때 몇 가지 정보를 제공해야 합니다. 설정 워크시트에는 해당 정보가 개요되어 있으며 첫 실행 프로그램을 진행할 때 필요한 환경별 정보 목록을 제공합니다. 자세한 정보는 [설정 워크시트](setup-worksheet-surface-hub.md)를 참조하세요.


## 이 섹션의 내용

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">항목</th>
<th align="left">설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">디바이스 계정 만들기 및 테스트</a></p></td>
<td align="left"><p>이 항목에서는 Surface Hub가 Skype와 통신하는 데 사용하는 디바이스 계정을 만들고 테스트하는 방법을 소개합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">프로비저닝 패키지 만들기</a></p></td>
<td align="left"><p>Windows 10의 경우 프로비저닝 패키지를 통해 레지스트리 또는 CSP(콘텐츠 서비스 플랫폼)를 사용하는 설정을 구성할 수 있습니다. 프로비전을 사용하여 첫 실행 중에 인증서를 추가할 수도 있습니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">관리자 그룹 관리</a></p></td>
<td align="left"><p>디바이스에서 설정 앱을 열어 각 Surface Hub를 개별적으로 구성할 수 있습니다. 그러나 관리자가 아닌 사용자가 설정을 변경하는 것을 방지하기 위해 설정 앱을 열고 설정을 변경하려면 관리자 자격 증명이 필요합니다.</p>
<p>설정 앱을 열려면 로컬 관리자 자격 증명이 필요합니다.</p></td>
</tr>
</tbody>
</table>

## 자세한 정보

- [블로그 게시물: Surface Hub 및 비즈니스용 Skype 신뢰할 수 있는 도메인 목록](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [블로그 게시물: 다중 도메인 환경의 Surface Hub](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [블로그 게시물: Surface Hub용 프록시 구성](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 





