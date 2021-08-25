---
title: Surface Hub 보안 개요
description: 이 페이지에서는 Surface Hub의 심층 방어 설계를 설명하고, Surface Hub 2S의 향상된 보안 기능, 무선 보안 보호 및 관련 기능에 관해 설명합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 01/26/2021
ms.localizationpriority: High
ms.openlocfilehash: cd0112f805b60b16c7f32099d5f5e3fde3c821fb
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911383"
---
# <a name="surface-hub-security-overview"></a>Surface Hub 보안 개요

Surface Hub Windows 10 Team 운영 체제를 실행하는 사용자 지정 플랫폼 펌웨어를 사용하여 잠긴 어플라이언스와 유사한 환경을 제공합니다. 결과로 생성되는 장치는 기존에 사용하는 "단일 사용" 보안 키오스크, “필요한 것만 실행” 철학을 취하여 현대적인 해석을 전달합니다. 다양한 공동 작업 사용자 환경을 지원하도록 만들어진 Surface Hub는 지속적으로 진화하는 보안 위협으로부터 보호됩니다.

Windows 10을 기반으로 하는 Surface Hub는 IT 관리자가 BitLocker, TPM(신뢰할 수 있는 플랫폼 모듈 2.0) 및 Windows Defender(Microsoft Defender라고도 함)를 포함한 클라우드 기반 보안을 통해 데이터 보호를 강화할 수 있도록 하는 엔터프라이즈급 최신 보안 기능을 제공합니다.

## <a name="defense-in-depth-security"></a>보안 심층 방어

보안 프로토콜은 Surface Hub가 켜진 직후에 시작됩니다. 펌웨어 수준에서부터 Surface Hub는 여러 보안 검사에 대응하여 운영 체제와 해당 구성 요소만 로드합니다. Surface Hub는 부분적 오류가 발생했을 때 시스템 전체를 보호하기 위해 독립적인 방어 하위 구성 요소를 계층화하는 심층 방어라는 전략을 사용합니다. 이 산업 관행은 잠재적인 일방적인 악용과 하위 구성 요소의 취약성을 완화하는 데 매우 효과적이라고 입증되었습니다.

최신 UEFI(통합 확장 펌웨어 인터페이스)는 내부 저장소에서 인증된 Windows 10 Team 운영 체제만 부팅하도록 Microsoft에서 정적이고 안전하게 구성되었습니다.  Surface Hub에서 실행되는 모든 코드 줄은 실행하기 전에 서명을 확인합니다. 운영 체제의 일부로 또는 Microsoft Store를 통해 설치된 Microsoft에서 서명한 응용 프로그램만 Surface Hub에서 실행할 수 있습니다. 이러한 요구 사항을 충족하지 않는 코드 또는 앱은 차단됩니다.

Surface Hub 보안 시스템은 다음을 포함합니다.

- **부팅 시 방어** 신뢰할 수 있는 Surface Hub 운영 체제 구성 요소만 로드합니다.
- **운영 체제 방어** 의도하지 않거나 악성 소프트웨어 또는 코드의 실행을 방지합니다.
- **사용자 인터페이스 방어** 최종 사용자에게 안전한 사용자 인터페이스를 제공하여 명령줄에서 실행 파일을 실행하는 것과 같은 위험할 수 있는 활동에 대한 액세스를 차단합니다.

### <a name="boot-time-defenses"></a>부팅 시 방어

SoC에는 다른 모든 코어와는 분리된 보안 프로세서가 있습니다. Surface Hub를 처음 시작하는 경우에는 다른 모든 항목을 로드하기 전에 보안 프로세서만 시작됩니다.

![보안 프로세서 보호를 보여주는 Hub 시작 부팅 단계.](images/hub-sec-1.png)

#### <a name="secure-boot"></a>보안 부팅

보안 부팅은 드라이버 및 운영 체제를 포함하여 부팅 프로세스의 구성 요소가 유효하고 알려진 서명의 데이터베이스에 대해 검증되었는지 확인하는 데 사용됩니다. Surface Hub에서 먼저 플랫폼 관련 서명의 유효성을 검사한 후에 공인 Windows Team 운영 체제를 로드할 수 있습니다. 이를 통해 정상적인 사용자 환경으로 보이는 악성 코드를 실행하는 복제되거나 수정된 시스템의 공격을 방지할 수 있습니다.  자세한 내용은 [보안 부팅 개요](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)를 참조하세요.

### <a name="operating-system-defenses"></a>운영 체제 방어

운영 체제가 Microsoft와 Surface Hub에서 만든 것으로 확인되면 장치가 부팅 프로세스를 성공적으로 완료하고 실행 코드를 자세히 조사합니다. 운영 체제 보안에 대한 이 접은 방식으로 모든 실행 파일에 대한 코드 서명을 식별하여 제한 사항을 통과하는 기능만 런타임으로 로드하도록 할 수 있습니다. 이 코드 서명 방법을 사용하여 운영 체제에서 작성자를 확인하고, 장치에서 실행되기 전에 코드가 변경되지 않았음을 확인할 수 있습니다.

Surface Hub는 Windows Application Control(이전까지의 Device Guard)에서 UMCI(사용자 모드 코드 무결성)라는 코드 서명 기능을 사용합니다. 정책 설정은 다음 요구 사항 중 하나를 충족하는 앱만 허용하도록 구성되어 있습니다.

- [공식적으로 인증된](https://docs.microsoft.com/windows/uwp/publish/the-app-certification-process) 유니버설 Windows 플랫폼(Microsoft Store) 앱.
- 고유한 Microsoft 프로덕션 루트 CA(인증 기관)로 서명된 앱(해당 인증서에 대한 액세스 권한이 부여된 Microsoft 직원만 서명할 수 있음).
- 고유한 Surface Hub 프로덕션 루트 C로 서명된 앱.

구성 파일은 타사에서 제한을 제거하거나 수정할 수 없도록 설계된 Microsoft 프로덕션 루트 CA를 사용하여 서명됩니다. 이 시점의 다른 모든 실행 파일은 운영 체제 런타임 수준에서 간단히 차단되며 처리 능력에는 액세스할 수 없습니다. 이 공격 표면 축소는 다음과 같은 보호를 제공합니다.

- 레거시 문서 모드 없음
- 레거시 스크립트 엔진 없음
- VML(Vector Markup Language) 없음
- 브라우저 도우미 개체 없음
- ActiveX 컨트롤 없음

Surface Hub는 UMCI를 통해 서명되지 않거나 잘못 서명된 코드를 차단하는 것 외에도 Windows Application Control을 사용하여 명령 프롬프트, PowerShell 및 작업 관리자와 같은 Windows 구성 요소를 차단합니다. 이러한 보호책은 안전한 컴퓨팅 어플라이언스로 Surface Hub의 주요 설계 기능을 반영합니다. 자세한 내용은 다음을 참조하십시오.

- [Application Control 개요](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender Application Control 및 코드 무결성의 가상화 기반 보호](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

### <a name="user-interface-defenses"></a>사용자 인터페이스 방어

부팅 시 방어 및 운영 체제 잠금 보호책은 기초 보안을 제공하지만, 사용자 인터페이스는 위험을 더 줄이기 위해 설계된 추가 계층을 제공합니다. 드라이버를 통해 악성 코드가 장치에 도달하는 것을 방지하기 위해 Surface Hub는 PnP(plug and play) 장치용 고급 드라이버를 다운로드하지 않습니다. USB 플래시 드라이브 또는 인증된 Surface Hub 주변 기기(스피커, 마이크, 카메라)와 같은 기본 드라이버를 활용하는 장치는 예상대로 작동하지만, 프린터와 같은 고급 시스템은 제대로 작동하지 않습니다.

사용자 인터페이스 방어는 또한 UI를 단순화하여 악성 소프트웨어 또는 코드가 실행되지 않도록 방지합니다. 다음 Surface Hub UI 요소는 코드 서명으로 제공되는 핵심 보안을 계층화합니다.

- **파일 탐색기** Surface Hub에는 사용자를 시스템이나 프로그램 파일에 노출하지 않고도 음악, 비디오, 문서, 그림, 다운로드 폴더에 빠르게 액세스할 수 있는 사용자 지정 파일 탐색기가 있습니다. 로컬 하드 드라이브의 다른 위치는 파일 탐색기를 통해 사용할 수 없습니다. 또한, .exe, .msi 설치 파일 등의 여러 파일 형식은 악성 실행 파일에 대해 다른 보안 계층을 제공할 수 없습니다.

- **시작 및 모든 앱** Surface Hub의 시작 및 모든 앱 구성 요소는 Application Control를 통해 차단되는 명령 프롬프트, PowerShell 또는 기타 Windows 구성 요소에 대한 액세스를 노출하지 않습니다. 또한, 일반적으로 Surface Hub에 대한 검색 상자에서 PC에 액세스하는 Windows 실행 기능은 꺼져 있습니다.

## <a name="security-enhancements-in-surface-hub-2s"></a>Surface Hub 2S 보안 강화

Surface Hub와 Surface Hub 2S 모두 같은 운영 체제 소프트웨어를 실행하지만, Surface Hub 2S의 고유한 일부 기능은 IT 관리자가 다음과 같은 작업을 수행할 수 있도록 추가 관리 및 보안 기능을 제공합니다.

- SEMM으로 UEFI 설정 관리하기
- 부트 가능한 USB를 사용하여 Hub 복구하기
- 암호 순환으로 장치 계정 강화하기

### <a name="manage-uefi-settings-with-semm"></a>SEMM으로 UEFI 설정 관리하기

UEFI는 기본 하드웨어 플랫폼 부분과 운영 체제 간의 인터페이스입니다. Surface Hub에서 사용자 지정 UEFI 구현을 사용하면 이러한 설정을 세밀하게 제어하고, Microsoft 이외의 엔터티가 장치의 UEFI 설정을 변경하거나 이동식 드라이브로 부팅하여 운영 체제를 수정하거나 변경할 수 없습니다.

개략적으로 공장 프로비전 프로세스가 진행되는 동안 Surface Hub UEFI는 보안 부팅을 사용할 수 있도록 미리 구성되어 있으며, UEFI 메뉴에 대한 액세스가 잠겨 있고 바로 가기 키가 제거된 내부 SSD(Solid-State Drive)로만 부팅하도록 설정됩니다. 이렇게 하면 UEFI 액세스를 봉인하고, 장치가 Surface Hub에 설치된 Windows Team 운영 체제로만 부팅할 수 있습니다.

SEMM(Microsoft Surface Enterprise 관리 모드)를 통해 관리되는 경우 IT 관리자는 조직 전체에서 Hub 장치에 UEFI 설정을 배포할 수 있습니다. 여기에는 기본 제공 하드웨어 구성 요소를 사용하거나 사용하지 않도록 설정하고, 권한이 없는 사용자가 UEFI 설정을 변경하지 못하도록 보호하고, 부팅 설정을 조정하는 기능이 포함됩니다.

![Surface Hub UEFI 설정.](images/hub-sec-2.png)

관리자는 다운로드 가능한 [Microsoft Surface UEFI 구성기](https://www.microsoft.com/download/details.aspx?id=46703)를 사용하여 SEMM과 등록된 Surface Hub 2S 장치를 구현할 수 있습니다. 자세한 내용은 [SEMM 및 UEFI를 사용하여 Surface Hub 2S 보호 및 관리하기](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)를 참조하세요.
인증서를 사용하여 허가되지 않은 변조 또는 제거로부터 구성을 보호하는 SEMM을 통해 다음 구성 요소를 관리할 수 있습니다.

- 유선 LAN
- 카메라
- Bluetooth
- Wi-Fi
- 점유 센서
- PXE 부팅용 IPv6
- 대체 부팅
- 부팅 순서 잠금
- USB 부팅
- UEFI 프런트 페이지 인터페이스
    - 장치
    - Boot
    - 날짜/시간

    
### <a name="recover-hub-with-bootable-usb"></a>부트 가능한 USB를 사용하여 Hub 복구하기

Surface Hub 2S를 사용하면 관리자는 복구 이미지를 사용하여 20분 이내에 장치를 공장 설정으로 다시 설치할 수 있습니다. 일반적으로 Surface Hub가 더 이상 작동하지 않는 경우에만 이 작업을 수행해야 합니다. 복구는 Bitlocker 키를 분실하거나 더 이상 설정 앱에 대한 관리자 자격 증명을 보유하고 있지 않은 경우에도 유용합니다.

### <a name="harden-device-account-with-password-rotation"></a>암호 순환으로 장치 계정 강화하기

Surface Hub는 "룸 계정"이라는 장치 계정을 사용하여 Exchange, Microsoft Teams 및 기타 서비스를 인증합니다. 암호 순환을 사용하도록 설정하면 Hub 2S는 자동으로 7일마다 대문자, 소문자, 숫자 및 특수 문자를 조합하여 15~32문자로 구성된 새 암호를 생성합니다. 사용자가 암호를 알고 있는 것이 아니기 때문에 장치 계정 암호 순환은 사용자 오류와 사회 공학적 보안 공격에 관련된 위험을 효과적으로 완화합니다.

## <a name="windows-10-enterprise-grade-security"></a>Windows 10 엔터프라이즈급 보안

Surface Hub는 이 문서에서 다루는 Surface Hub 관련 구성 및 기능 외에도 Windows 10의 표준 보안 기능을 사용합니다. 확인할 수 있습니다.

- **BitLocker** Surface Hub SSD는 BitLocker를 장착하여 장치의 데이터를 보호합니다. 해당 구성은 업계 표준을 따릅니다. 자세한 내용은 [BitLocker 개요](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)를 참조하세요.
- **Windows Defender** Windows Defender 맬웨어 방지 엔진은 Surface Hub에서 지속적으로 실행되며, Surface Hub에서 발견되는 위협을 자동으로 해결합니다. Windows Defender 엔진은 자동으로 업데이트를 받으며, IT 관리자용 원격 관리 도구를 통해 관리할 수 있습니다. Windows Defender 엔진은 심층 방어 접근 방식을 완벽하게 보여 주는 예제입니다. 맬웨어가 핵심 코드 신호 기반 보안 솔루션을 찾는 방법을 찾을 수 있는 경우 여기에서 발견됩니다. 자세한 내용은 [Windows Defender Application Control 및 코드 무결성의 가상화 기반 보호](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)를 참조하세요.
- **플러그 앤 플레이 드라이버.** 드라이버를 통해 악성 코드가 장치에 도달하는 것을 방지하기 위해 Surface Hub는 PnP 장치용 고급 드라이버를 다운로드하지 않습니다. 이를 통해 USB 플래시 드라이브와 같은 기본 드라이버를 활용하는 장치는 프린터와 같은 고급 시스템을 차단하면서 예상대로 작동할 수 있습니다.
- **신뢰할 수 있는 플랫폼 모듈 2.0** Surface Hub에는 암호화 키 및 해시를 생성하고 저장하기 위한 산업 표준 dTPM(개별 신뢰할 수 있는 플랫폼 모듈)이 있습니다. dTPM은 부팅 단계, BitLocker 마스터 키, 암호가 없는 sign-on 키 등을 확인하는 데 사용되는 키를 보호합니다. dTPM은 [FIPS 140-2 수준 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation) 인증, 미국 정부 컴퓨터 보안 표준을 충족하고, 전 세계에서 사용하는 [공통 평가 기준](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria) 인증을 준수합니다.

## <a name="wireless-security-for-surface-hub"></a>Surface Hub에 대한 무선 보안

Surface Hub는 Wi-Fi Direct/Miracast 기술과 관련된 802.11, WPA2(Wi-Fi Protected Access) 및 WPS(Wireless Protected Setup) 표준을 사용합니다. 디바이스는 WPS만 지원하므로(WPA2 PSK(미리 공유한 키) 또는 WPA2 엔터프라이즈는 지원하지 않음) 기존에 802.11 암호화와 관련된 문제가 설계상 간단해집니다.

Miracast는 Wi-Fi Direct 프로토콜이 지원하는 Wi-Fi 디스플레이 표준의 일부입니다. 이러한 표준은 화면 공유 및 공동 작업을 위해 최신 모바일 디바이스에서 지원됩니다

Wi-Fi Direct 또는 Wi-Fi "P2P"(피어 투 피어)는 Wi-Fi Alliance가 "애드혹" 네트워크용으로 발표한 표준입니다. 이 표준은 지원되는 디바이스가 일반적인 Wi-Fi 액세스 지점 또는 인터넷 연결 없이 직접 통신하고 네트워크 그룹을 만들도록 허용합니다.

Wi-Fi Direct에 대한 보안은 WPA2가 WPS 표준을 사용하여 제공합니다. 숫자 핀, 물리적 또는 가상 누름 단추 또는 근거리 통신을 사용하는 대역 외 메시지를 사용하여 장치를 인증할 수 있습니다. Surface Hub는 기본적으로 누름 단추와 PIN 메서드를 모두 지원합니다. 자세한 내용은 [Surface Hub가 Wi-Fi Direct 보안 문제를 해결하는 방법](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)을 참조하세요.

## <a name="learn-more"></a>자세히 알아보기

- [보안 부팅 개요](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

- [BitLocker 개요](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

- [Application Control 개요](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [SEMM 및 UEFI를 사용하여 Surface Hub 2S 보호 및 관리](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)

- [Surface Hub가 Wi-Fi Direct 보안 문제를 해결하는 방법](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)

- [Windows Defender Application Control 및 코드 무결성의 가상화 기반 보호](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

- [IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703)

- [FIPS 140-2 수준 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)

- [공통 평가 기준 인증](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)
