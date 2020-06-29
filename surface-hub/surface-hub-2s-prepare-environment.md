---
title: Surface Hub 2S에 대한 환경 준비
description: Surface Hub 2S 환경을 준비 하기 위해 수행 해야 하는 작업에 대해 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 38f02b885a0ac2789ffc82f1ab38dc57fea5e841
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835343"
---
# Surface Hub 2S에 대한 환경 준비

## Office 365 준비

Exchange Online, 비즈니스용 Skype Online, Microsoft 팀 또는 Microsoft 화이트 보드를 사용 하 고 Intune을 사용 하 여 Surface Hub 2S를 관리 하려는 경우 먼저 [끝점에 대 한 Office 365 요구 사항을](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)검토 합니다.

Office 365 끝점은 모든 추가 패킷 수준 검사 또는 처리를 우회 하 여 모든 신뢰할 수 있는 Office 365 네트워크 요청을 방화벽을 통해 직접 보내는 방법으로 네트워크를 최적화 하는 데 도움이 됩니다. 이 기능은 대기 시간과 해당 경계 용량 요구 사항을 줄입니다.

Microsoft는 필요한 포트, Url, IP 주소를 변경할 수 있는 새로운 기능과 기능을 사용 하 여 Office 365 서비스를 정기적으로 업데이트 합니다. 변경 사항을 평가, 구성, 최신 상태로 유지 하려면 [Office 365 IP 주소 및 URL 웹 서비스](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)에 가입 합니다.

## 디바이스 소속

디바이스 소속을 사용 하 여 Surface Hub 2S의 설정 앱에 대 한 사용자 액세스를 관리할 수 있습니다.
Surface Hub 2S에서 실행 되는 Windows 10 Team Edition 운영 체제를 사용 하 여 권한 있는 사용자만 설정 앱을 사용 하 여 설정을 조정할 수 있습니다. 소속을 선택 하면 기능 가용성에 영향을 줄 수 있으므로, 사용자가 의도 한 대로 기능에 액세스할 수 있도록 적절 하 게 계획 합니다.

> [!NOTE]
> 초기 OOBE (첫 실행 경험) 설정 중에만 디바이스 소속을 설정할 수 있습니다. 디바이스 소속을 다시 설정 해야 하는 경우 OOBE 설치 프로그램을 반복 해야 합니다.

## 소속 없음

각 Surface Hub 2S에서 다른 로컬 관리자 계정을 사용 하 여 작업 그룹에서 Surface Hub 2S 하는 것과는 관계가 없습니다. 회원 가입을 선택 하지 않은 경우에는 [BitLocker 키를 USB 엄지 드라이브에](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)로컬로 저장 해야 합니다. Intune을 사용 하 여 디바이스를 등록할 수 있습니다. 그러나 로컬 관리자만 OOBE 중에 구성 된 계정 자격 증명을 사용 하 여 설정 앱에 액세스할 수 있습니다. 설정 앱에서 관리자 계정 암호를 변경할 수 있습니다.

## Active Directory Domain Services

온-프레미스 Active Directory 도메인 서비스를 사용 하 여 Surface Hub 2S을 구입한 경우에는 도메인의 보안 그룹을 사용 하 여 설정 앱에 대 한 액세스 권한을 관리 해야 합니다. 이렇게 하면 모든 보안 그룹 구성원에 게 Surface Hub 2S 설정을 변경할 수 있는 권한이 있는지 확인할 수 있습니다. 또한 다음을 참고 하세요.

- 온-프레미스 Active Directory 도메인 서비스를 사용 하는 Surface Hub 2S의 경우 BitLocker 키를 Active Directory 스키마에 저장할 수 있습니다. 자세한 내용은 [BitLocker에 맞게 조직 준비: 계획 및 정책을](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)참조 하세요. 
- 조직의 신뢰할 수 있는 루트 Ca가 Surface Hub 2S의 동일한 컨테이너에 푸시되는 데,이는 프로비저닝 패키지를 사용 하 여 가져올 필요가 없다는 의미입니다.
- 계속 해 서 Intune을 사용 하 여 디바이스를 등록 하 여 Surface Hub 2S의 설정을 중앙에서 관리할 수 있습니다.

## Azure Active Directory

Azure Active Directory (Azure AD)를 사용 하 여 Surface Hub 2S을 계열사로 선택한 경우 전역 관리자 보안 그룹의 모든 사용자가 Surface Hub 2S에서 설정 앱에 로그인 할 수 있습니다. 현재는 Surface Hub 2S의 설정 앱에 로그인 하기 위해 다른 그룹을 위임할 수 없습니다.

조직에 Intune 자동 등록을 사용 하도록 설정한 경우 Surface Hub 2S는 Intune을 사용 하 여 자동으로 등록 됩니다. 디바이스의 BitLocker 키는 Azure AD에 자동으로 저장 됩니다. Affiliating Surface Hub를 Azure AD와 함께 사용 하는 경우 single sign-on 및 간단한 인증이 작동 하지 않습니다.
