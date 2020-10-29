---
title: Windows 10 Team 2020 업데이트의 새로운 기능
description: Surface Hub 운영 체제의 최신 업데이트 인 Windows 10 Team 2020 업데이트의 새로운 기능을 확인 하세요.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: Medium
ms.openlocfilehash: accdc8519ad90b5137e2b8f340290d9a7214e696
ms.sourcegitcommit: b4cfb718274fd632661f9112e9fd086a2ad45640
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "11143633"
---
# Windows 10 Team 2020 업데이트의 새로운 기능

Windows 10 Team 2020 업데이트는 Windows 10의 최신 기능과 함께 장치 배포 및 관리 효율성을 대폭 개선 합니다.

##  배포 및 관리 효율성

- **클라우드 장치 계정에 대 한 최신 인증**. Surface Hub는 exchange 웹 서비스 (EWS) 및 ADAL (Active Directory Authentication Library) 기반 인증을 사용 하 여 Exchange에 연결 하 고, 고객이 기본 인증을 사용 안 함 수 있도록 지원 합니다. 자세한 내용은 [Surface Hub의 최신 인증](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)을 참조 하세요.
- **20 개 이상의 새로운 MDM (모바일 디바이스 관리) 정책이 추가**되었습니다.      이러한 정책을 통해 관리자는 Microsoft Store의 앱 업데이트, 인프라를 통해 Miracast 등의 무선 투영 설정, 서비스 품질 및 802.1 x 유선 인증, 새로운 개인정보 보호/GDPR 관련 설정 등의 여러 장치 설정에 대 한 관리를 향상 시킬 수 있습니다.

##  Azure Active Directory에 가입 된 장치

- **AZURE AD 참가 디바이스에 대 한 sso (Single sign-on)** 입니다. 사용자가 Microsoft 365 자격 증명을 사용 하 여 "내 모임 및 파일"에 로그인 하면 브라우저에서 Microsoft 365 환경을 포함 하 여 앱에서 앱으로 원활 하 게 사용자 자격 증명이 전달 됩니다.
- **AZURE AD 참가 디바이스에 대 한 CA (조건부 액세스)**       IT 관리자는 해당 Azure AD 조인 된 Surface Hub에 장치 수준 보안 정책을 배포 하 여 회사 보안 및 준수 요구 사항에 따라 조직 리소스에 대 한 액세스를 제어할 수 있습니다.
- **AZURE AD에 가입 된 디바이스에 대 한 비전역 관리자 지원**.       고객은 관리자 계층 내에서 더 세부적인 관리자 집합을 선택 하 여 Surface Hub를 관리할 수 있습니다. 자세한 내용은 [관리자 그룹 관리](https://docs.microsoft.com/surface-hub/admin-group-management-for-surface-hub)를 참조하세요.


## 추가 기능


- **새로운 Microsoft Edge에 대 한 지원**. 최적화 된 호환성 성능, 보안 및 개인 정보 보호를 위해 Microsoft Edge가 다시 작성 되었습니다. 자세한 내용은 [Surface Hub의 새 Microsoft Edge 설치 및 구성을](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)참조 하세요.
- **Microsoft 팀은 기본적으로 설치**됩니다.        Microsoft 팀은 MDM을 통해 변경 하거나 구성할 수 있는 새 Surface Hub 장치에 기본 모임, 통화 및 공동 작업 앱이 포함 되어 있으며 설정 앱을 사용 하 여 Surface Hub에 직접 적용 됩니다. 자세히 알아보려면 [Microsoft 팀 배포](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)를 참조 하세요.
- **Microsoft 팀의 근접 참가에 대 한 지원**  근접 참가를 통해 사용자는 인접 한 Surface Hub를 통해 랩톱/전화기를 사용 하 여 예약 된 Microsoft 팀에서 전화를 걸거나 진행 중인 모임을 가까운 Surface Hub로 원활 하 게 전환할 수 있습니다. Windows 10 Team 2020 업데이트는 근접 참가를 구성 하기 위한 MDM (모바일 디바이스 관리) 지원을 추가 하 고 Microsoft Store를 통해 Microsoft 팀을 업데이트 하면 해당 기능이 계속 릴리스됩니다.
- **Microsoft 팀과의 공동 모임 지원**. Surface Hub와 Microsoft 팀 대화방 장치 또는 두 개의 Surface Hub 장치를 사용 하는 공간이 있는 회의실에서, 통합 된 모임을 통해 사용자는 Microsoft 팀 모임 중에 두 장치를 쉽게 활용할 수 있습니다. 한 번의 탭으로 한 장치에서 비디오 피드를 표시 하 고 다른 디바이스의 디지털 화이트 보드 또는 콘텐츠에 화면 공간을 최대화 하 여 모임에 참가할 수 있습니다. Windows 10 Team 2020 업데이트는 조정 된 모임을 구성 하기 위해 MDM (모바일 디바이스 관리) 지원을 추가 하 고 Microsoft Store를 통해 Microsoft 팀을 업데이트 하면 해당 기능이 계속 릴리스됩니다.
- **FIDO2 보안 키를 사용 하 여 암호를 덜 로그인**     합니다.     고객은 FIDO2 보안 키를 사용 하 여 사용자 이름과 비밀 번호를 입력할 필요 없이 신속 하 고 간편 하 게 Surface Hub에 로그인 할 수 있습니다. 이 기능은 모임 중에 파일, 앱 및 웹 사이트에 대 한 빠르고 원활한 인증을 제공 하는 SSO (Single Sign-On)으로 결합 됩니다. 자세한 내용은 [Surface Hub에서 passwordless 로그인 구성을](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)참조 하세요.
- **Microsoft Authenticator를 사용 하 여 암호를 더 쉽게 로그인 할 수**있습니다.  Azure AD를 사용 하는 조직의 경우 사용자가 사용자 이름과 암호에 입력할 필요 없이 Microsoft Authenticator 앱을 사용 하 여 로그인 할 수 있습니다. 또한 사용자는 UPN (사용자 계정 이름) 외에 Azure AD의 기본 전자 메일 별칭을 사용 하 여 로그인 할 수 있습니다. 자세히 알아보려면 [Microsoft Authenticator를 사용 하 여 Surface Hub에 로그인](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)을 참조 하세요.
- **Surface Hub 2S의 듀얼 펜 수동 입력**   사용자는 두 개의 Surface Hub 2 펜을 사용 하 여 Surface Hub 2S에 동시에 화이트 보드 및 공동 작업할 수 있습니다. 이중 펜 수동 입력 기능을 사용 하는 데 필요한 펌웨어 업데이트는 후속 업데이트로 해제 됩니다.

 
 
 
