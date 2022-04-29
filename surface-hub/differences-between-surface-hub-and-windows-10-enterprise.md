---
title: 운영 체제 필수 항목(Surface Hub)
description: 이 항목에서는 Surface Hub Windows Team 운영 체제의 고유한 측면과 Windows 10 또는 Windows 11 Enterprise 어떻게 다른지에 대해 설명합니다.
keywords: 변경 내용
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/15/2022
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 5be9c0ba3f23832d2e3d9b66a746e9f1f0772e63
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497341"
---
# <a name="operating-system-essentials-surface-hub"></a>운영 체제 필수 항목(Surface Hub)

Windows 10 Team Surface Hub 운영 체제는 Windows 10 Enterprise 시작되어 엔터프라이즈 관리, 보안 및 기타 기능에 대한 풍부한 지원을 제공합니다. 그러나 둘 간에는 중요한 차이점이 있습니다. Enterprise 버전은 PC용으로 설계되었지만 Windows 10 Team은 처음부터 큰 화면과 회의실용으로 설계되었습니다. Surface Hub 대한 보안 및 관리 요구 사항을 평가할 때 새 운영 체제로 고려하는 것이 좋습니다. 이 문서에서는 Surface Hub Windows 10 Team Windows 10 또는 Windows 11 엔터프라이즈 버전 간의 주요 차이점을 강조 표시합니다.

## <a name="convert-surface-hub-to-run-pro-or-enterprise-desktop"></a>Pro 또는 Enterprise 데스크톱을 실행하도록 Surface Hub 변환

Windows 10 또는 Windows 11 Pro/Enterprise 마이그레이션하여 Surface Hub 2S에서 OS를 변경할 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [Surface Hub 2에서 Windows 10 Pro 및 Enterprise 가용성을 발표](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107)합니다.

- [Surface Hub 2에서 Windows 10 또는 Windows 11 Pro 또는 Enterprise 마이그레이션](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>사용자 인터페이스

### <a name="shell-os-user-interface"></a>셸(OS 사용자 인터페이스)

Surface Hub의 셸은 처음부터 큰 화면과 터치에 최적화되도록 설계되었습니다. Windows 10 또는 Windows 11 Enterprise 동일한 셸을 사용하지 않습니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- Windows 10 또는 Windows 11 Enterprise 셸의 컨트롤과 관련된 설정 Surface Hub 적용되지 않습니다.

### <a name="lock-screen-and-screensaver"></a>잠금 화면 및 화면 보호기

Surface Hub에는 잠금 화면이나 화면 보호기가 없지만 시작 화면이라는 유사한 기능이 있습니다. 시작 화면에는 디바이스 계정 일정의 예약된 모임이 표시되며, Surface Hub의 인기 앱인 비즈니스용 Skype, 화이트보드 및 연결에 손쉽게 액세스할 수 있습니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 잠금 화면, 화면 시간 제한 및 화면 보호기에 대한 설정은 Surface Hub에서 적용되지 않습니다.

### <a name="user-sign-in"></a>사용자 로그인

Surface Hub는 회의실 등의 공용 공간에서 사용하도록 설계되었습니다. Windows PC와 달리 누구든지 로그인하지 않고 Surface Hub를 사용할 수 있습니다. 이 공동 기능을 사용하도록 설정하기 위해 Surface Hub Windows 10 또는 Windows 11 Enterprise 수행하는 것과 동일한 방식으로 Windows 로그인을 지원하지 않습니다(예: OS에 사용자 로그인 및 OS 전체에서 해당 자격 증명 사용). 대신, 항상 Surface Hub에 자동 로그인한 낮은 권한의 로컬 사용자가 있습니다. 관리자(예: 관리자가 로그인할 때 OS에 로그인하지 않은 경우)를 포함하여 추가 사용자를 로그인하는 것은 지원되지 않습니다.

사용자는 Surface Hub에 로그인할 수 있지만 OS에 로그인하지는 않습니다. 예를 들어 사용자가 앱 또는 내 모임 및 파일에 로그인하면 사용자는 OS가 아니라 앱 또는 서비스에만 로그인됩니다. 결과적으로 로그인한 사용자는 클라우드에 저장된 클라우드 파일과 개인 모임을 검색할 수 있으며 **세션 종료**가 활성화되면 이러한 자격 증명이 삭제됩니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 일반적으로 Surface Hub는 보안을 강화하기 위해 사용자 액세스 제어 대신 잠금 기능을 사용합니다. 암호 요구 사항, 대화형 로그온, 사용자 계정 및 액세스 제어와 관련된 정책은 Surface Hub에서 적용되지 않습니다.

### <a name="saving-and-browsing-files"></a>파일 저장 및 검색

사용자는 Surface Hub에서 제한된 디렉터리 집합에 액세스할 수 있습니다.
- 음악
- 비디오
- 문서
- 사진
- 다운로드

사용자가 **세션 종료**를 누르면 이러한 디렉터리에 로컬로 저장된 파일이 삭제됩니다. 모임 중에 만든 콘텐츠를 저장하려면 USB 드라이브 또는 OneDrive에 파일을 저장해야 합니다.

*영향을 줄 수 있는 조직 정책:* - 액세스 권한 및 파일 및 폴더의 소유권과 관련된 정책은 Surface Hub 적용되지 않습니다. 사용자는 시스템 디렉터리 및 네트워크 폴더에서 파일을 찾거나 저장할 수 없습니다.

## <a name="applications"></a>응용 프로그램

### <a name="default-applications"></a>기본 응용 프로그램

몇 가지 예외를 제외하고 Surface Hub 기본 유니버설 Windows 플랫폼(UWP) 앱은 Windows 10 또는 Windows 11 PC에서도 사용할 수 있습니다.

Surface Hub에 미리 설치된 UWP 앱:

- 알람 및 시계
- 계산기
- 연결
- Excel Mobile
- 피드백 허브
- 파일 탐색기
- 시작
- 지도
- Microsoft Edge
- Microsoft Power BI
- Microsoft Teams
- Microsoft Whiteboard
- OneDrive
- 사진
- PowerPoint Mobile
- 설정
- 스토어
- 팁
- Word Mobile

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- Windows 10 또는 Windows 11 Enterprise 대한 지침을 사용하여 Surface Hub 기본 앱의 기능 및 네트워크 요구 사항을 확인합니다.

### <a name="installing-apps-drivers-and-services"></a>앱, 드라이버 및 서비스 설치

어플라이언스와 유사한 디바이스 특성을 유지하기 위해 Surface Hub는 UWP(유니버설 Windows 플랫폼) 앱의 설치만 지원하고 클래식 Win32 앱, 서비스 및 드라이버 설치는 지원하지 않습니다. 또한 관리자만 UWP 앱 설치에 액세스할 수 있습니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 의도하지 않은 사용을 방지하기 위해 직원은 관리자가 설치한 앱만 사용할 수 있습니다. Surface Hub는 대부분의 기존 PC 관리 및 모니터링 도구에 필요한 Win32 에이전트 설치를 지원하지 않습니다.

## <a name="security-and-lockdown"></a>보안 및 잠금

Surface Hub 회의실과 같은 공동 공간에서 사용할 수 있도록 사용자 지정 OS는 Windows 10 또는 Windows 11 사용할 수 있는 많은 보안 및 잠금 기능을 구현합니다. 자세한 내용은 [Surface Hub 보안 개요](surface-hub-security.md)를 참조하세요.

Surface Hub 다음과 같은 Windows 보안 기능을 구현합니다.

- [보안 부팅](/windows-hardware/design/device-experiences/oem-secure-boot)
- [Windows Defender Application Control 및 코드 무결성의 가상화 기반 보호](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [AppLocker를 사용하는 응용 프로그램 제한 정책](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)
- [BitLocker 드라이브 암호화](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [TPM(신뢰할 수 있는 플랫폼 모듈)](/windows/security/information-protection/tpm/trusted-platform-module-top-node)
- [Windows Microsoft Defender 바이러스 백신](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)
- 설정 앱 액세스를 위한 [UAC(사용자 계정 컨트롤)](/windows/security/identity-protection/user-account-control/user-account-control-overview)

추가 보안을 제공하는 Surface Hub 기능은 다음과 같습니다.

- 사용자 지정 UEFI 펌웨어
- 사용자 지정 셸 및 시작 메뉴에서 디바이스가 회의 기능으로 제한됨
- 사용자 지정 파일 탐색기에서 내 문서 아래의 파일 및 폴더에 대한 액세스 권한만 부여됨
- 사용자 지정 설정 앱에서 관리자만 디바이스 설정을 수정할 수 있음
- 고급 플러그 앤 플레이 드라이버를 다운로드할 수 없음

*이러한 차이가 영향을 줄 수 있는 조직 정책:*

- Surface Hub에 대한 보안 평가를 수행하는 경우 이러한 기능을 고려하세요.

## <a name="management"></a>관리

### <a name="device-settings"></a>디바이스 설정

설정 앱을 통해 디바이스 설정을 구성할 수 있습니다. 설정 앱은 Surface Hub 맞게 사용자 지정되지만 Windows 10 또는 Windows 11 Desktop의 많은 친숙한 설정도 포함합니다. 설정 앱을 열 때 관리자 자격 증명을 확인하기 위해 UAC(사용자 계정 컨트롤) 프롬프트가 표시되지만 관리자가 로그인되지는 않습니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 직원은 Surface Hub를 회의에 사용할 수 있지만 디바이스 설정을 수정할 수는 없습니다. 잠금 기능 외에도 이러한 제한은 직원이 디바이스를 회의 기능에만 사용하도록 합니다.

### <a name="administrative-features"></a>관리 기능

Windows 10 또는 Windows 11 Enterprise 관리 기능(예: Microsoft 관리 콘솔, 실행, 명령 프롬프트, PowerShell, 레지스트리 편집기 및 작업 관리자)은 Surface Hub 지원되지 않습니다. 설정 앱에는 Surface Hub에서 로컬로 사용할 수 있는 모든 관리 기능이 포함되어 있습니다.

#### <a name="event-viewer"></a>이벤트 뷰어

Windows 10 Team 2020 업데이트 2는 Windows 10 Pro 또는 Windows 10 Enterprise 설치된 [이벤트 뷰어](/host-integration-server/core/windows-event-viewer1) 동일한 Windows 이벤트 뷰어 대한 지원을 추가합니다. 

**이벤트 뷰어를 열려면 다음을 수행합니다.**

1. 관리자 자격 증명을 사용하여 **설정** 앱에 로그인합니다.
2. **SecurityLogs** >  **& 업데이트를** 선택하고 이벤트 뷰어 아래에서 **열기**를 선택합니다. 

자세한 내용은 [Windows 이벤트 뷰어](/host-integration-server/core/windows-event-viewer1) 참조하세요.

### <a name="remote-management-and-monitoring"></a>원격 관리 및 모니터링

Surface Hub [Azure Monitor](/azure/azure-monitor/)를 통한 [Microsoft Intune](/mem/intune/) 및 모니터링과 같은 MDM(모바일 디바이스 관리) 솔루션을 통한 원격 관리를 지원합니다. 

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- Surface Hub는 System Center Operations Manager 등 대부분의 기존 PC 관리 및 모니터링 도구에 필요한 Win32 에이전트 설치를 지원하지 않습니다.

### <a name="group-policy"></a>그룹 정책

Surface Hub 감사를 포함하여 Windows 그룹 정책 지원하지 않습니다. 대신 MDM을 사용하여 Surface Hub에 정책을 적용합니다. MDM에 대한 자세한 내용은 [MDM 공급자를 사용하여 설정 관리](manage-settings-with-mdm-for-surface-hub.md)를 참조하세요.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 그룹 정책 대신 MDM을 사용하여 Surface Hub를 관리합니다.

### <a name="remote-assistance"></a>원격 지원

Surface Hub는 원격 지원을 지원하지 않습니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 원격 지원과 관련된 정책은 Surface Hub에서 적용되지 않습니다.

## <a name="network"></a>네트워크

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>도메인 가입 및 Azure AD(Azure Active Directory) 가입 

Surface Hub는 도메인 가입 및 Azure AD 가입을 사용하여 주로 디렉터리 백업 관리자 그룹을 제공합니다. 하이브리드 조인은 지원되지 않습니다. 사용자는 도메인 계정으로 로그인할 수 없습니다. 자세한 내용은 [관리자 그룹 관리](admin-group-management-for-surface-hub.md)를 참조하세요.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- Surface Hub 도메인에 가입된 경우 그룹 정책 설정이 적용되지 않습니다. 도메인 멤버 자격과 관련된 정책 설정은 Surface Hub 적용되지 않습니다.

### <a name="accessing-domain-resources"></a>도메인 리소스에 액세스

사용자는 Microsoft Edge에 로그인하여 인트라넷 사이트 및 온라인 리소스(예: Office 365)에 액세스할 수 있습니다. Surface Hub가 디바이스 계정을 사용하여 구성된 경우 시스템은 이 계정을 사용하여 Exchange 및 비즈니스용 Skype에 액세스합니다. 그러나 Surface Hub는 파일 공유 및 프린터와 같은 도메인 리소스에 대한 액세스를 지원하지 않습니다.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- 도메인 개체 액세스와 관련된 정책은 Surface Hub에서 적용되지 않습니다.

### <a name="diagnostic-data"></a>진단 데이터

Surface Hub OS는 Windows 연결된 사용자 환경 및 원격 분석 구성 요소를 사용하여 진단 데이터를 수집하고 전송합니다. 자세한 내용은 [조직에서 Windows 진단 데이터 구성](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)을 참조하세요.

*이러한 차이가 영향을 줄 수 있는 조직 정책:* 

- Windows 10 또는 Windows 11 Enterprise 것과 동일한 방식으로 Surface Hub 대한 진단 데이터 수준을 구성합니다.
