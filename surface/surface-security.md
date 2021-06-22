---
title: Surface 보안 개요
description: 이 문서에서는 Surface 디바이스 보안에 대한 개요를 제공합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/04/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 67ba96129d69cafaa7a1b24ce3dde98767b676ef
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614131"
---
# <a name="surface-security-overview"></a>Surface 보안 개요

보안 연구의 최근 발전은 OS 및 연결된 서비스에 더 많은 보호가 구축되면 공격자는 펌웨어가 최상위 대상으로 등장하는 다른 악용을 찾고 있습니다.

오늘날 장치 펌웨어 관리는 불일치한 환경으로, 종종 펌웨어를 모니터링하기 어렵고 유지 관리하기 복잡해하는 타사 공급자와 관련이 있습니다. 궁극적으로 이는 하드웨어 제조업체가 위협에 대응하여 시기적박한 업데이트를 검색하고 푸시하는 기능을 제한할 수 있습니다.

Microsoft Surface는 2015년 이후 하드웨어 디자인, 사내 펌웨어 개발 및 장치 업데이트 및 관리에 대한 전체적인 접근 방식을 통해 펌웨어 보호 및 장치 보안에 대한 통합된 접근 방식을 사용하고 있습니다.

Surface의 경우 UEFI(Unified Extensible Firmware Interface) 1은 사장에서 유지 관리되고, Windows 업데이트를 통해 정기적으로 업데이트되고, Windows <sup> [](#references) Autopilot을 통해 관리를 위해 원활하게 배포되어 장치를 부팅하기 전에 위험을 최소화하고 펌웨어 수준에서 제어를 </sup> 최대화합니다. Microsoft는 UEFI에서 관리되는 UEFI의 Open Source Project [Mu를](https://microsoft.github.io/mu/) 통해 GitHub 완전하게 Microsoft Endpoint Manager.

## <a name="microsoft-designed-and-built-components"></a>Microsoft에서 디자인 및 구축한 구성 요소

칩에서 클라우드로의 모든 Surface 계층은 Microsoft에서 개발 및 유지 관리하여 언제 어디서나 궁극적인 제어, 사전 보호 및 안심하고 안심할 수 있도록 합니다. Surface 디바이스는 Microsoft에서 제공하는 가장 강력한 보안 프로토콜을 함께 제공하며, IT 복잡성을 줄여 사용자가 업무에 집중할 수 있도록 하는 간소화된 관리를 지원합니다.

Surface는 독립적인 방어 하위 구성 요소의 계층을 활용하여 심층 방어 접근 방식을 통해 보안을 강화합니다. 칩에서 클라우드로 또는 고급 위협을 방지, 감지, 조사 및 대응하기 위해 작동하는 AI 기반의 Microsoft Defender에 대한 신뢰 루트를 보장하는 UEFI 또는 Microsoft에서 기본 제공되는 것이 bolt-on보다 더 나은 위치를 적용합니다.

| 기능                         | 설명                                                                                                                                                                                                                                                                                                                         | 자세히 알아보기                                                                                                                                                                   |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft Built UEFI            | 장치를 구성하고 디바이스를 부팅하는 Windows 10<br>장치 및 디바이스의 초기 부팅을 Windows 10 운영 체제에 펌웨어 런타임 서비스를 제공합니다. 를 통해 SEMM의 프레미스 관리 및 DFCI 클라우드 기반 관리를 통해 장치의 하드웨어를 훨씬 더 Microsoft Endpoint Manager | [Surface UEFI 설정 관리](manage-surface-uefi-settings.md)                                                                        |
| 실제 TPM 2.0                | 신뢰할 수 있는 플랫폼 모듈 - 통합된 암호화 키를 통해 하드웨어를 보호하도록 설계된 전용 마이크로컨트롤러입니다.<br>키 암호화 및 저장(BitLocker, Windows Hello, AD 자격 증명,)<br>PCR - 이전 구성의 변경 내용을 감지하기 위해 측정 및 관련 메트릭을 보호하는 플랫폼 구성 등록  | [TPM(신뢰할 수 있는 플랫폼 모듈) 기술 개요](/windows/security/information-protection/tpm/trusted-platform-module-overview)                 |
| 비즈니스용 Windows Hello      | PC 및 모바일 장치에서 암호를 강력한 2단계 인증으로 대체합니다. 이 생체 인식 인증은 장치에 연결하고 생체 인식 또는 PIN을 사용하는 새로운 유형의 사용자 자격 증명으로 구성됩니다.                                                                                                                   | [비즈니스 Windows Hello 작동 방식 - Microsoft 365 보안](/windows/security/identity-protection/hello-for-business/hello-how-it-works) |
| 통합 암호화           | BitLocker에서 통합 암호화를 사용하여 데이터를 보호하고 암호화할 수 있으며, Windows Hello TPM 및 UEFI와 함께 암호 없는 로그인을 사용하도록 설정할 수 있습니다.                                                                                                                                                                 | [BitLocker(Windows 10) - Microsoft 365 보안](/windows/security/information-protection/bitlocker/bitlocker-overview)                     |
| 엔드포인트용 Microsoft Defender | 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 하도록 설계된 엔터프라이즈 끝점 보안 플랫폼을 제공합니다.                                                                                                                                                                               | [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)                 |

## <a name="factory-level-security-protocols-and-inspection"></a>공장 수준 보안 프로토콜 및 검사

펌웨어에서 운영 체제 및 최종 어셈블리 전에 하드웨어의 모든 구성 요소까지 Surface 장치는 물리적으로 보안이 유지된 개발 및 제조 시설의 공급망 공격으로부터 안전합니다.

정의상, 보안 공급망은 품질, 성능 및 운영 목표를 충족하는 완성된 제품을 제공합니다. 간단히 말하면, 보안 공급망은 모든 구성 요소가 정품이며 무단 또는 악의적인 조작이나 사보타지가 없는지 보장합니다. Microsoft는 UEFI 펌웨어에서 운영 체제까지 모든 것이 Microsoft에서 직접 오는 보안이 유지되는 공장에서 장치를 제조합니다. 타사 BIOS 공급업체는 관련이 없습니다. 이는 Surface 제품에 대한 공급망 공격으로부터 보호하는 방법의 강력한 부분입니다. 디바이스에 필요하지 않은 시스템 관리 모드 SMM 기능을 포함하여 사용되지 않는 코드를 제거하여 UEFI의 공격 Surface를 줄입니다.

외부 인터넷 기반 공격, 침입 및 기타 위협으로부터 시설을 보호하려면 다음을 비롯한 주요 영역에 대한 지속적인 투자가 필요합니다.

- 최종 어셈블리 위치에서 모든 구성 요소의 엄격한 검사 및 테스트
- 공장에서 높은 수준의 물리적 보안을 유지 관리합니다.
- Microsoft에서 개발한 펌웨어& 드라이버 및 OS만 사용
- Microsoft 리셀러에게 Surface 디바이스를 안전한 배송 및 신뢰할 수 있는 배송업체로 전달합니다.

출하 시 비즈니스용Surface 업데이트는 Windows 통해 보호됩니다.

## <a name="advanced-windows-security-features"></a>고급 Windows 보안 기능

권한 공격의 에스컬레이터는 악의적인 배우의 가장 좋은 친구로, 종종 메모리에 저장된 중요한 정보를 대상으로 합니다. 이러한 종류의 공격은 사소한 사용자 모드 손상을 OS 및 장치의 전체 손상으로 전환할 수 있습니다. 이러한 종류의 공격에 대처하기 위해 Microsoft는 VBS(가상화 기반 보안) 및 하이퍼바이스로 보호되는 코드 무결성(HVCI, 일반적으로 메모리 무결성이라고도 칭)을 개발했습니다. VBS 및 HVCI는 가상화와 같은 하드웨어 기능을 사용하여 격리된 환경에서 중요한 보안 작업을 수행하여 일반 및 정교한 맬웨어로부터 더 나은 보호를 제공합니다.

Surface는 기본 제공 및 Windows 강화된 하드웨어 보안 기능을 기본 제공 및 설정하는 고객에게 더 강력한 보안을 제공했습니다.

## <a name="virtualization-based-security"></a>가상화 기반 보안

가상화 기반 보안 또는 VBS는 하드웨어 가상화 기능을 사용하여 일반 운영 체제에서 보안 메모리 지역을 만들고 격리합니다. Windows "가상 보안 모드"를 사용하여 다양한 보안 솔루션을 호스팅하여 운영 체제의 취약성으로부터 보호를 크게 강화하고 악의적인 악용을 사용하여 보호를 막을 수 있습니다.

### <a name="hypervisor-enforced-code-integrity-hvci"></a>Hypervisor-Enforced 코드 무결성(HVCI)

HVCI는 VBS를 사용하여 코드 무결성 정책 적용을 크게 강화합니다. 커널 모드 코드 무결성은 시작되기 전에 모든 커널 모드 드라이버 및 이진 파일을 확인하고, 시스템 메모리에 부호 없는 드라이버 또는 시스템 파일이 로드되지 않도록 합니다. 다음 다이어그램과 같이 HVCI는 격리된 실행 환경에서 실행되고 커널 서명 정책에 따라 커널 코드의 무결성을 검증합니다.

다음 Surface 디바이스에서 VBS와 HVCI를 모두 사용할 수 있습니다.

- Surface Laptop 4
- Surface Pro 7+
- Surface Book 3,
- Surface Laptop 이동,
- Surface Pro X

## <a name="secure-boot-and-boot-guard"></a>보안 부팅 및 부팅 보호

Surface 디바이스의 신뢰 루트는 서명 및 측정을 확인하여 다음 부팅 단계를 계속 진행하기 전에 각 단계가 안전하고 인증되도록 합니다. UEFI 및 TPM 2.0에서 사용하는 보안 부팅은 Surface 디바이스에서 코드 서명, 측정 및 올바르게 구현된 코드만 실행할 수 있도록 합니다.

그림 2에 표시된 것 처럼 펌웨어의 무결성은 각 단계에서 전원 단추를 눌러 운영 체제를 실행하는지 검사합니다.

 > [!div class="mx-imgBorder"]
 > ![그림 1. Surface 디바이스의 보안 부팅 ](images/secboot.png)
  *그림 1. Surface 디바이스용 보안 부팅*

| 단계  | 보안 부팅 단계                                                                                                                                                                                                                                      |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | TPM에서 제공하는 신뢰 루트에서 전원 단추를 누를 때마다 보안이 인스턴스화됩니다. 장치를 처음 전원으로 들이면 시스템에서 일련의 보안 검사를 실행하여 장치 펌웨어가 변조되거나 손상되지 않은지 확인합니다. |
| **2** | 전원이 설정될 때 SoC는 칩세트 공급업체 키를 사용하여 ACM(Authenticated Code Module)(Intel 기반 디바이스)을 사용하여 마이크로코드 로드의 유효성을 검사하고 시작됩니다.                                                                              |
| **3** | ACM은 로드하기 전에 UEFI 코드를 측정하고 TPM의 플랫폼 구성 레지스터[PCR]에서 알려진 측정값과 비교하여 UEFI 코드가 변경되지 않은지 확인합니다.                                                                |
| **4** | UEFI 실행을 허용하기 전에 Boot Guard는 UEFI가 Surface OEM 키로 서명되어 있는지 검사합니다. 처음에 확인된 UEFI 모듈은 다이어그램에 표시된 SEC 보안 및 PEI 사전 EFI 섹션입니다.                                                |
| **5** | PEI 섹션은 로드되는 드라이버 실행 환경인 DXE 모듈에서 Surface 서명을 검사합니다. DXE 모듈에는 부팅 장치 선택 단계가 포함됩니다.                                                                          |
| **6** | 부팅 장치가 선택되면 UEFI는 부팅 장치를 읽고 실행을 허용하기 전에 OS 부팅 로더의 서명을 확인합니다.                                                                                                             |
| **7** | 그러면 OS가 OS를 구성하는 주 구성 요소에서 서명을 검사합니다.

### <a name="malware-protection"></a>맬웨어 보호

악성 소프트웨어 공격으로부터 장치를 보호하기 위해 Surface를 사용하면 보안 부팅을 통해 인증 버전의 Windows 10 시작하고 펌웨어가 출고 시와 같은 정품으로 정품이 되도록 할 수 있습니다.

Surface 디바이스의 SoC에는 다른 모든 코어와 분리된 보안 프로세서가 있습니다. Surface 디바이스를 처음 시작하면 보안 프로세서만 시작된 후 다른 것을 로드할 수 있습니다. 보안 부팅은 드라이버 및 운영 체제를 포함하여 부팅 프로세스의 구성 요소가 유효하고 알려진 서명의 데이터베이스에 대해 검증되었는지 확인하는 데 사용됩니다. 이를 통해 정상적인 사용자 환경으로 보이는 악성 코드를 실행하는 복제되거나 수정된 시스템의 공격을 방지할 수 있습니다. 자세한 내용은 [보안 부팅 개요](/windows-hardware/design/device-experiences/oem-secure-boot)를 참조하세요.

운영 체제가 Microsoft에서 시작된 것으로 확인되고 Surface 디바이스가 부팅 프로세스를 성공적으로 완료하면 장치는 실행 코드를 확인합니다. 운영 체제 보안에 대한 이 접은 방식으로 모든 실행 파일에 대한 코드 서명을 식별하여 제한 사항을 통과하는 기능만 런타임으로 로드하도록 할 수 있습니다. 이 코드 서명 방법을 사용하여 운영 체제에서 작성자를 확인하고, 장치에서 실행되기 전에 코드가 변경되지 않았음을 확인할 수 있습니다.

## <a name="drtm-protection-in-amd-devices"></a>AMD 장치의 DRTM 보호

AMD 프로세서가 포함된 Surface 디바이스는 동일한 방식으로 보안 부팅을 구현합니다. Surface Laptop 4와 AMD Ryzen Microsoft Surface Edition 프로세서는 DRTM(Dynamic Root of Trust Measurements)을 사용하여 초기 전원 설정으로부터 펌웨어를 보호합니다. DRTM은 모든 COUS를 제어하여 측정된 경로를 따라 실행을 강요하고, 다양한 단계에서 신뢰를 다시 구축하여 시스템 펌웨어/소프트웨어의 무결성을 검증합니다. 초기에 이 신뢰할 수 있는 상태로 전환하면 부팅 단계에서 잠재적인 공격에 대한 보호가 추가됩니다.

DRTM은 TSME(Total System Memory Encryption)를 사용하여 측정을 암호화하여 측정을 보호합니다. 시스템 재설정을 제외하고는 지우지 못하면 TSME가 설정됩니다. 각 재설정에 대한 새 암호화 키는 보안을 위해 단일 사용 암호화를 보장합니다.

SMM(시스템 관리 모드)에 대한 런타임 호출은 가장 높은 수준에서 실행됩니다. SMM 코드에 문제가 있는 경우 위험할 수 있습니다. SURFACE LAPTOP 4에서는 SMI(시스템 관리 인터럽트)를 가로채 시스템을 보호하고 SMM 코드 실행을 더 낮은 수준(사용자)으로 디스패치하여 코드 및 데이터에 대한 잘못된 액세스로부터 시스템을 보호합니다. SMM 보호는 하드웨어 보호를 사용하여 액세스할 수 있는 코드, 데이터 및 시스템 리소스를 제한하여 부주의하거나 악의적인 인시던트에 대한 보호를 강화합니다.

Surface Laptop 4에서 AMD Ryzen은 강력한 펌웨어 업데이트 지원 외에 [NIST 800-193](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-193.pdf)플랫폼 펌웨어 복구 지침을 지원합니다. 부팅 펌웨어에 대한 복원력 업데이트 메커니즘은 부팅 시퀀스가 부팅 중에 펌웨어의 손상된 복사본을 감지하는 경우 펌웨어의 백업 복사본에 자동 복구를 제공하는 A-B 복구 메커니즘을 사용합니다.

DRTM 및 SMM에 대한 자세한 내용은 Windows Defender System Guard가 보안 및 보호를 Windows 10 - Windows [방법을 | Microsoft Docs](/windows/security/threat-protection/windows-defender-system-guard/how-hardware-based-root-of-trust-helps-protect-windows)

## <a name="remote-device-management-control"></a>원격 장치 관리 제어

IT 관리자는 모든 디바이스를 물리적으로 터치하지 않고도 Surface 디바이스를 원격으로 관리할 수 있습니다. Microsoft Endpoint Manager 및 Windows Autopilot을 사용하면 Azure 클라우드에서 Surface 디바이스를 완전히 원격으로 관리하여 시작할 때 완전히 구성된 디바이스를 사용자에게 제공합니다. 초기화 및 사용 중지 기능을 통해 IT는 새 원격 사용자에 대해 장치를 쉽게 재배포하고 도난당한 장치를 지우는 데 사용할 수 있습니다. 이를 통해 Surface 디바이스를 손실하거나 도난당하는 경우 신속하고 안전한 응답 기능을 통해 모든 회사 데이터를 원격으로 제거하고 Surface를 완전히 새로운 장치로 다시 구성할 수 있습니다.

| 기능                                        | 설명                                                                                                                                                                                                                                                                                                                                                                                                        | 자세히 알아보기                                                                                                                                                                                                                                                              |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DCFI(장치 펌웨어 구성 인터페이스) | 제로 터치 장치 프로비전을 통해 클라우드 규모의 원격 펌웨어 관리를 제공합니다. Microsoft의 자체 UEFI는 더 강력한 DCFI 구현을 허용하여 조직에서 하드웨어 요소를 사용하지 않도록 설정하고 Intune을 사용하여 UEFI를 원격으로 잠글 수 있도록 합니다. ¹                                                                                                                                                                          | [Surface UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)<br> <br>[Surface UEFI 설정 관리](manage-surface-uefi-settings.md)                                          |
| SEMM(Surface Enterprise 관리 모드)      | 중앙 집중식 엔터프라이즈에서 UEFI 펌웨어 설정에 대한 중앙 집중식 연결(On-premises, hybrid 및 cloud environments)을 지원합니다.¹                                                                                                                                                                                                                                                                                           | [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)                                                                                                                                                       |
| 비즈니스용 Windows 업데이트                    | IT 관리자는 이러한 시스템을 Windows 10 업데이트 서비스에 직접 연결하여 조직의 Windows 10 장치를 최신 보안 방어, Windows 기능 및 Surface 펌웨어로 항상 최신 Windows 있습니다. 그룹 정책 또는 MDM 솔루션(예: Microsoft Intune)을 사용하여 Surface 디바이스의 업데이트 방법과 Windows 제어하는 비즈니스용 업데이트 설정을 구성할 수 있습니다. | [비즈니스용 Windows 업데이트](/windows/deployment/update/waas-manage-updates-wufb)<br> <br>[Surface 드라이버 및 펌웨어 업데이트 관리 및 배포](manage-surface-driver-and-firmware-updates.md) |

## <a name="references"></a>참조

1. Surface Go 및 Surface Go 2는 타사 UEFI를 사용하며 DFCI를 지원하지 않습니다. DFCI는 현재 Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 및 Surface Pro X에 사용할 수 있습니다. 

## <a name="learn-more"></a>자세히 알아보기

- [새 Surface PC를 사용하면 기본적으로 VBS(가상화 기반 보안)를 통해 고객이 더 많은 작업을 안전하게 할 수 있습니다.](https://www.microsoft.com/security/blog/2021/01/11/new-surface-pcs-enable-virtualization-based-security-vbs-by-default-to-empower-customers-to-do-more-securely/)
- [Surface 펌웨어 보호의 중요한 역할을 강조하는 연구](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/study-highlights-critical-role-of-surface-firmware-protection/ba-p/2245244)
- [Microsoft Surface 및 2016을 통해 보안 및 규정 Microsoft 365](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/enhancing-security-and-compliance-with-microsoft-surface-and/ba-p/2283062)
- [Surface UEFI 설정 관리](manage-surface-uefi-settings.md)
- [Surface UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)
- [Project Mu](https://microsoft.github.io/mu/)
