---
title: Surface Pro X 배포, 관리 및 서비스
description: 이 문서에서는 Surface Pro X의 배포, 관리 및 서비스에 대한 주요 고려 사항에 대한 개요를 제공합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: f0fed17dade345bf3f7dc9619eab7981dcb30cb0
ms.sourcegitcommit: 6d531906c36da51cb4032a220d70182e686114a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2021
ms.locfileid: "11721278"
---
# <a name="deploying-managing--servicing-surface-pro-x"></a>Surface Pro X 배포, 관리 및 서비스

## <a name="introduction"></a>소개

고성능 상용 요구 사항을 처리하도록 제작된 Surface Pro X는 동급에서 가장 강력한 프로세서인 Microsoft SQ1 및 Microsoft SQ1 ARM 칩셋을 통합하여 새로운 지평을 마련했습니다.

3GHz CPU와 2.1 테라플롭 GPU로 구동되는 Surface Pro X는 완전한 Windows 환경을 제공합니다. 15시간의 배터리 사용 시간이 내장된 기가비트 LTE와 터치, 펜, 태블릿 및 노트북의 다양성으로 금융, 법률 및 의료 분야의 모바일 일선 근로자 및 전문가 또는 연장된 배터리 사용 시간 및 지속적인 연결 기능을 요구하는 모든 역할에 이상적입니다.

Surface Pro X는 Microsoft 365, Intune 및 Windows Autopilot과 함께 사용될 때 최고의 성능을 발휘하며, 최신 클라우드 기반 환경을 위해 거의 독점적으로 설계되었습니다. 이 문서에서는 어떻게 Surface Pro X를 배포, 관리 및 서비스하는지 설명하고 이를 위한 주요 고려 사항을 간략하게 설명합니다.

## <a name="deploying-surface-pro-x"></a>Surface Pro X 배포

최상의 환경을 위해 Microsoft 클라우드 솔루션 공급자의 도움을 받아 Windows Autopilot을 사용하여 Surface Pro X를 프로비저닝하거나 Autopilot 배포 프로필 밀 관련 기능을 사용하여 자체 프로비저닝합니다. 자세한 내용은 다음을 참고하십시오.

- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md)
- [Windows Autopilot 개요](/windows/deployment/windows-autopilot/windows-autopilot)

Autopilot 배포에는 다음과 같은 몇 가지 장점이 있습니다. 공장에서 프로비전된 운영 체제를 사용하여 제로 터치 배포를 간소화하고 엔터프라이즈용 Microsoft 365 앱(Office Pro Plus라고도 함)의 사전 설치를 포함할 수 있습니다.

최신 관리, 보안 및 생산성 솔루션을 이미 사용하는 조직은 Surface Pro X의 고유한 성능 기능의 이점을 잘 활용할 수 있는 위치에 있습니다. 현대화된 비즈니스 앱, Microsoft Store(UWP) 앱 또는 원격 데스크톱 솔루션을 사용하는 고객 또한 혜택을 얻을 수 있습니다.

## <a name="image-based-deployment-considerations"></a>이미지 기반 배포 고려 사항

Microsoft Deployment Toolkit(MDT) 및 Microsoft Endpoint Configuration Manager(이전의 System Center Configuration Manager)는 현재 운영 체제 배포를 위해 Surface Pro X를 지원하지 않습니다. 이미지 기반 배포에 의존하는 고객은 Surface Pro 7+을 고려하는 동시에 최신 배포 솔루션으로 전환할 적절한 시기를 계속 고려해야 합니다. 

## <a name="managing-surface-pro-x-devices"></a>Surface Pro X 디바이스 관리

### <a name="intune"></a>Intune

Microsoft Enterprise Mobility + Security의 구성 요소인 Intune은 ID 및 액세스 제어를 위해 Azure Active Directory와 통합되며 등록된 Surface Pro X 디바이스의 세부적인 관리를 제공합니다. Intune 모바일 디바이스 관리(MDM) 정책에는 Windows 그룹 정책과 같은 이전 온-프레미스 도구에 비해 여러 가지 이점이 있습니다. 여기에는 더 빠른 디바이스 로그인 시간과 클라우드에서 전체 디바이스 관리를 가능하게 하는 보다 간소화된 정책 카탈로그가 포함됩니다. 예를 들어 eSIM 프로필을 사용하여 LTE를 관리하여 데이터 요금제를 구성하고 활성화 코드를 여러 디바이스에 배포할 수 있습니다.<br> 

Intune을 사용하는 방법에 대한 자세한 내용은 [Intune 설명서](/intune)를 참조하세요.

### <a name="co-management"></a>공동 관리

Autopilot에 배포하면 Surface Pro X 디바이스를 Azure AD 또는 Active Directory(하이브리드 Azure AD 가입)에 등록하여 Intune으로 디바이스를 관리하거나 32비트 x86 ConfigMgr 클라이언트를 설치하는 Endpoint Configuration Manager로 공동 관리할 수 있습니다.

### <a name="third-party-mdm-solutions"></a>타사 MDM 솔루션

타사 MDM 도구를 사용하여 Surface Pro X 디바이스를 관리할 수 있습니다. 자세한 내용은 MDM 공급자에게 문의하십시오.

### <a name="antivirus-software"></a>바이러스 백신 소프트웨어

Windows Defender는 Windows 10 디바이스의 지원되는 수명 동안 ARM 기반 PC에서 Windows 10을 보호하는 데 도움이 됩니다. 

일부 타사 바이러스 백신 소프트웨어는 ARM 기반 프로세서에서 실행되는 Windows 10 PC에 설치할 수 없습니다. ARM 기반 PC에서의 AV 앱 준비를 위해 타사 바이러스 백신 소프트웨어 공급자와의 협업이 계속되고 있습니다. 바이러스 백신 소프트웨어 공급자에게 문의하여 앱을 사용할 수 있는 시기를 확인하세요.

## <a name="servicing-surface-pro-x"></a>Surface Pro X 서비스

Surface Pro X는 Windows 10 버전 2004와 함께 제공되며 Windows 10 버전 1903 이상을 지원합니다. ARM 기반 디바이스로서 최신 드라이버 및 펌웨어를 유지 관리하기 위한 특정 요구 사항이 있습니다. 

Surface Pro X는 Windows 업데이트를 사용하여 가정 사용자와 소규모 비즈니스 사용자 모두가 드라이버와 펌웨어를 최신 상태로 유지하는 프로세스를 간소화하도록 설계되었습니다. 기본 설정을 사용하여 자동 업데이트를 수신합니다.  확인하려면:

1. **시작** > **설정 > 업데이트 및 보안 > Windows 업데이트** > **고급 옵션**으로 이동합니다.
2. **업데이트 설치 방법 선택**에서 **자동(권장)** 을 선택합니다.

### <a name="recommendations-for-commercial-customers"></a>상용 고객을 위한 권장 사항

- 최신 드라이버 및 펌웨어를 유지 관리하기 위해 Windows 업데이트 또는 비즈니스용 Windows 업데이트를 사용합니다. 자세한 내용은 [비즈니스용 Windows 업데이트를 사용하여 업데이트 배포](/windows/deployment/update/waas-manage-updates-wufb)를 참조하세요.
- Surface 장치에서 업데이트 배포 및 관리에 대한 자세한 내용은 [ Surface 드라이버 및 펌웨어 업데이트 관리 및 배포 ](manage-surface-driver-and-firmware-updates.md)를 참조하십시오.
- Windows Server Update Services(WSUS)는 Surface Pro X에 드라이버와 펌웨어를 제공하는 기능을 지원하지 않습니다.

## <a name="running-apps-on-surface-pro-x"></a>Surface Pro X에서 앱 실행

대부분의 앱은 제한된 예외가 있는 ARM 기반 Windows 10 PC에서 실행됩니다.

### <a name="supported-apps"></a>지원되는 앱

- 대부분의 x86 Win32 앱은 Surface Pro X에서 실행됩니다.
- 네이티브 ARM64 및 Microsoft Store UWP 앱은 배터리 사용 시간을 최적화하면서 ARM 기반 프로세서의 최대 기본 속도를 활용하는 탁월한 사용자 환경을 제공합니다.
- ARM 기반 프로세서에서 실행되는 Windows 10 PC용으로 설계된 드라이버를 사용하는 앱입니다.

> [!NOTE]
> Windows 참가자 프로그램을 통해 미리 보기에서 64 비트 에뮬레이션을 사용하면 Surface Pro X에서 64 비트(x64) 앱을 실행할 수 있습니다.

### <a name="fasttrack-app-assure"></a>FastTrack App Assure 

App Assure 프로그램은 LOB, ISV 및 ARM 기반 Windoes 10을 대상으로하는 Microsoft 자사 앱을 사용하는 상용 고객에게 제공됩니다. 상용 고객이 ARM에서 Windows 10을 사용할 때 앱 호환성 문제가 발생하는 경우, Microsoft는 추가 비용없이 문제를 해결하고 앱 수정을 지원하기 위하여 개발자 리소스를 제공합니다. 자세히 알아보려면 [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure)를 방문하세요.

Surface Pro X에서 앱을 실행하는 방법에 대한 자세한 내용은 다음을 참조하십시오.

- [Windows 10 ARM 기반 PC 지원 FAQ](https://support.microsoft.com/help/4521606)
- [ARM의 Windows 10 설명서](/windows/arm)

## <a name="virtual-desktops-vdi"></a>가상 데스크톱(VDI)

Windows Virtual Desktop을 사용하면 모든 위치에서 모든 컴퓨팅 디바이스 또는 플랫폼에서 Windows 데스크톱, 애플리케이션 및 데이터에 액세스할 수 있습니다. 자세한 내용은 [Windows Virtual Desktop 사이트](https://aka.ms/wvd)를 참조하십시오. 

## <a name="browsing-with-surface-pro-x"></a>Surface Pro X로 브라우징

인기 있는 브라우저가 Surface Pro X에서 실행됩니다.

- 기본 제공 Edge, Firefox, Chrome, Internet Explorer 모두 Surface Pro X에서 실행됩니다.
- Chromium 기반 Firefox 및 Microsoft Edge가 기본적으로 실행되므로 ARM 기반 프로세서의 Windows 10 PC에서 향상된 성능을 제공합니다.

## <a name="installing-and-using-microsoft-office"></a>Microsoft Office 설치 및 사용

- ARM 기반 프로세서의 Windows 10 PC에서 최상의 환경을 위해 Office 365를 사용하십시오.
- Office 365 “간편 실행”은 ARM 기반 프로세서의 Windows 10 PC에서 실행되도록 최적화된 Outlook, Word, Excel, PowerPoint를 설치합니다.
- Microsoft Teams는 Surface Pro X에서 잘 실행됩니다.
- Office 2019와 같은 Office의 "영구 버전"의 경우 32비트 버전을 설치합니다.

## <a name="vpn"></a>VPN

특정 타사 VPN이 ARM 기반 프로세서에서 Windows 10 PC를 지원하는지 확인하려면 VPN 공급자에게 문의하십시오.

## <a name="feature-summary"></a>기능 요약

다음 표는 ARM 기반 Windows 10이 설치된 Surface Pro X에서 선별된 주요 기능의 가용성을 보여줍니다.


**배포**

| 기능                                                           | 예/아니오 | 참고                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | 예 |                                                                                                                                   |
| 네트워크 부팅 지원(PXE)                                    | 아니오  |                                                                                                                                   |
| Windows 구성 디자이너                                    | 아니오  | Surface Pro X에 권장하지 않습니다.                                                                                                |
| WinPE                                                             | 예 | Surface Pro X에 권장하지 않습니다. Microsoft는 Surface Pro X에서 WinPE를 지원하기 위해 필수 .ISO 및 드라이버를 제공하지 않습니다. |
| Endpoint Configuration Manager: 운영 체제 배포(OSD) | 아니오  | Surface Pro X에서 지원되지 않습니다.                                                                                                   |
| MDT                                                               | 아니오  | Surface Pro X에서 지원되지 않습니다.                                                                                                   |

 
 
 **Management**
 

| 기능                                       | 예/아니오     | 참고                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| Intune                                        | 예     | eSIM 프로필이 제공되는 LTE를 관리합니다.                                                        |
| Windows Autopilot                             | 예     |                                                                                       |
| Azure AD(공동 관리)                      | 예     | Surface Pro X를 Azure AD 또는 Active Directory(하이브리드 Azure AD 가입)에 가입시키는 기능. |
| Endpoint Configuration Manager                | 예     |                                                                                       |
| AC 복원 시 전원 켜기                      | 예     |                                                                                       |
| 비즈니스용 Surface 진단 도구 키트(SDT) | 예     |                                                                                       |
| Surface 자산 태그 도구                        | 예     |                                                                                       |
| Surface 엔터프라이즈 관리 모드(SEMM)     | 부분 | 펌웨어 수준에서 Surface Pro X에서 하드웨어를 비활성화할 수 있는 옵션이 없습니다.                 |
| Surface UEFI 구성기                     | 아니오      | 하드웨어를 비활성화하는 옵션이 없습니다. 펌웨어 수준에서 Surface Pro X에서.                |
| Surface UEFI 관리자                          | 부분 | 펌웨어 수준에서 Surface Pro X에서 하드웨어를 비활성화할 수 있는 옵션이 없습니다.                 |

 

**보안**
 

 기능                                       | 예/아니오     | 참고                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BitLocker                                     | 예     |                                                       |
| Windows Defender                              | 예     |                                                                                       |
| 타사 바이러스 백신에 대한 지원             | 메모 참고| 일부 타사 바이러스 백신 소프트웨어는 ARM 기반 프로세서에서 실행되는 Windows 10 PC에 설치할 수 없습니다. ARM 기반 PC에서의 AV 앱 준비를 위해 타사 바이러스 백신 소프트웨어 공급자와의 협업이 계속되고 있습니다. 바이러스 백신 소프트웨어 공급자에게 문의하여 앱을 사용할 수 있는 시기를 확인하세요. |
| 보안 부팅               | 예     |                                                                                       |
| Windows Information Protection                      | 예     |                                                                                       |
| Surface 데이터 지우개(SDE)     | 예     |                                                                                       |




## <a name="faq"></a>FAQ

### <a name="can-i-deploy-surface-pro-x-with-mdt-or-endpoint-configuration-manager"></a>MDT 또는 Endpoint Configuration Manager로 Surface Pro X를 배포할 수 있습니까?

MDT(Microsoft 배포 도구 키트) 및 Microsoft Endpoint Configuration Manager는 현재 운영 체제 배포를 위해 Surface Pro X를 지원하지 않습니다. 이미지 기반 배포에 의존하는 고객은 Surface Pro 7+을 고려하는 동시에 클라우드로 전환할 적절한 시기를 계속 평가해야 합니다.

### <a name="how-can-i-deploy-surface-pro-x"></a>Surface Pro X를 배포하는 방법은 무엇입니까?

Windows Autopilot을 사용하여 Surface Pro X를 배포합니다.

### <a name="is-a-bmr-available"></a>BMR을 사용할 수 있나요?

예, [Surface 복구 이미지 다운로드](https://support.microsoft.com/surfacerecoveryimage)를 참조하세요..

### <a name="is-intune-required-to-manage-surface-pro-x"></a>Surface Pro X를 관리하려면 Intune이 필요합니까?

Intune을 사용하는 것이 좋지만 꼭 그래야 하는 것은 아닙니다. Autopilot에 배포하면 Surface Pro X 디바이스를 Azure AD 또는 Active Directory(하이브리드 Azure AD 가입)에 등록하여 Intune으로 디바이스를 관리하거나 32비트 x86 ConfigMgr 클라이언트를 설치하는 Endpoint Configuration Manager로 공동 관리할 수 있습니다.
