---
title: Surface Duo 보안 개요
description: 이 문서에서는 Surface Duo가 Android OS 및 Microsoft가 엔지니어링한 UEFI를 통해 모바일 장치에 엔터프라이즈급 보안을 제공하는 방법을 중점적으로 다루고 있습니다.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 677839038d8990aa7cb88800dabd51ace565e472
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449161"
---
# <a name="surface-duo-security-overview"></a>Surface Duo 보안 개요

Surface Duo는 장치, ID 및 데이터를 보호하는 심층 통합 하드웨어, 펌웨어 및 소프트웨어를 통해 모든 계층에서 기본 제공 보호 기능을 제공합니다. Android 10 디바이스인 Surface Duo는 OS 수준 및 Google 서비스 계층의 Android 보안 기능을 활용합니다. Android OS는 기존 OS 보안 컨트롤을 활용하여 사용자 데이터 및 시스템 리소스를 보호하고, 맬웨어로부터 장치 무결성을 보호하며, 응용 프로그램 차단 기능을 제공합니다. 또한 Google은 Android OS 보안과 결합되어 Android 사용자를 지속적으로 보호하는 데 도움이 되는 OS 위에 계층화된 다양한 서비스를 제공합니다.

- **사용자 지정 엔지니어링 UEFI.** Android 장치에서 Surface Duo에 고유한 것은 펌웨어 구성 요소를 완전하게 제어할 수 있는 Microsoft의 사용자 지정 UEFI(Unified Extensible Firmware Interface)입니다. Microsoft는 사장에서 모든 펌웨어 코드를 작성하거나 검토하여 Surface Duo에 Enterprise급 보안을 제공하므로 Microsoft는 잠재적인 펌웨어 위협에 직접 대처하고 공급망 보안 위험을 완화할 수 있습니다.
- **확인된 부팅.** 로그인 시 하드웨어 수준에서 시작하여 검증된 부팅은 실행된 코드가 신뢰할 수 있는 소스에서만 제공되도록 보장하기 위해 노력합니다. 하드웨어로 보호된 신뢰 루트에서 부팅 로더, 부팅 파티션 및 기타 확인된 파티션에 대한 전체 신뢰 체인을 설정합니다. Surface Duo가 부팅되면 각 단계는 실행을 넘기기 전에 다음 단계의 무결성과 무결성을 검증합니다.
- **앱 분리.** 응용 프로그램 샌드박스는 Android 앱을 격리하고 보호하여 악성 앱이 개인 정보에 액세스하지 못하게 합니다. 필수, 항상 사용 암호화 및 키 처리는 장치가 잘못된 손에 빠지는 경우에도 전송 중 및 미사용 데이터를 보호하는 데 도움이 됩니다. 암호화는 키 저장소 키로 보호됩니다. 이 키는 암호화 키를 컨테이너에 저장하여 장치에서 추출하기가 더 어렵습니다.
- **Google Play Protect.** 소프트웨어 계층에서 Surface Duo는 Google Play Protect 위협 감지를 사용하여 Google Play의 공용 앱, Microsoft에서 업데이트한 시스템 앱, 통신사에 의해 업데이트된 시스템 앱, 사이드로드된 앱을 비롯한 모든 응용 프로그램을 검색합니다.
- **Microsoft Defender ATP.** 이제 Intune에서 관리되는 Android 장치에서 Window 10용 엔터프라이즈급 바이러스 백신 및 맬웨어 보호 소프트웨어를 사용할 수 있습니다. 자세한 내용은 [Android용 Microsoft Defender ATP를 참조합니다](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android).

## <a name="mobile-device-management-security"></a>모바일 장치 관리 보안

Surface Duo는 조직 및 규정 준수 요구 사항에 맞게 조정할 수 있는 일관된 보호 도구, 기술 및 모범 사례 집합을 제공하는 Enterprise Mobility Management(EMM) 솔루션을 사용하여 회사 환경에서 보호됩니다. 광범위한 관리 API는 IT 부서에 데이터 누출을 방지하고 다양한 시나리오에서 규정 준수를 적용하는 데 도움이 되는 도구를 제공합니다. 다중 프로필 지원 및 장치 관리 옵션을 사용하면 회사 및 개인 데이터를 분리하여 회사 데이터를 안전하게 유지할 수 있습니다.

MDM 보안은 사용자가 이동 중 생산성을 향상하는 동시에 중요한 회사 지적 재산을 보호할 수 있도록 하는 확장된 구성 기술 집합을 토로합니다. 여기에는 환경에 따라 특정 목표를 달성할 수 있도록 설계된 앱 보호 정책, 장치 제한 정책 및 관련 기술이 포함됩니다. 비즈니스가 음식점 인출 명령 전달, 치과용 IT 서비스 관리 또는 중요한 국가 보안 정보 처리로 구성됩니다.

예를 들어 사용자가 2단계 인증과 함께 6자리 영문 핀을 입력하도록 요구하여 장치 인증을 강화할 수 있습니다. 사용자가 등록할 수 있는 장치를 제한하여 라이선스 제한을 준수하거나 "무단 사용되지 않은" 전화 또는 기타 지원되지 않는 장치 유형에 대한 액세스 권한을 부여하지 않도록 할 수 있습니다. Intune 및 기타 EMM을 사용하면 조직에서 요구에 따라 장치를 관리할 수 있습니다.

## <a name="app-protection-policies"></a>앱 보호 정책

APP(앱 보호 정책)은 조직의 데이터를 안전하게 유지하거나 관리되는 앱에 포함되도록 하는 규칙입니다. 정책은 사용자가 "회사" 데이터에 액세스하거나 이동하려고 할 때 적용되는 규칙 또는 사용자가 앱 내부에 있을 때 금지되거나 모니터링되는 작업 집합일 수 있습니다. 관리되는 앱은 앱 보호 정책이 적용된 앱으로, Intune에서 관리할 수 있습니다.

앱 보호 정책을 사용하면 응용 프로그램 내에서 조직의 데이터를 관리하고 보호할 수 있습니다. 앱 및 앱과 같은 Microsoft Office 앱은 Intune MAM에서 관리할 수 있습니다. 공개적으로 사용할 수 [Microsoft Intune 보호된](/mem/intune/apps/apps-supported-intune-apps) 앱의 공식 목록을 참조하세요.

## <a name="security-considerations-for-managing-surface-duo"></a>Surface Duo 관리에 대한 보안 고려 사항

모바일 장치 관리 솔루션에서 사용할 수 있는 정책 설정 수가 늘어나면 조직에서 특정 요구에 맞게 보호 수준을 조정할 수 있습니다. 조직에서 Surface Duo(또는 다른 Android 장치)에 대한 보안 설정의 우선 순위를 지정하는 데 도움을 주기 위해 Intune은 몇 가지 고유한 구성 시나리오로 Enterprise [Android](/mem/intune/enrollment/android-configuration-framework) Enterprise 보안 구성 프레임워크를 도입하여 작업 프로필 및 완전히 관리되는 시나리오에 대한 지침을 제공합니다.

| 보안 수준                                                                                                       | 대상                                                                                                                                                                      | 요약                                                                                                                                                                                     | 설정 정보                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 작업 프로필 기본 보안 - 수준 1                                                                                | 직장 또는 학교 데이터에 액세스할 수 있는 개인 장치.                                                                                                                             | 암호 요구 사항을 소개하고, 작업 및 개인 데이터를 분리하고, Android 장치 의회의 유효성을 검사합니다.                                                                               | [작업 프로필 수준 1 설정](/mem/intune/enrollment/android-work-profile-security-settings) |
| 작업 프로필 높은 보안 - 수준 3<br>프레임워크 규칙으로 인해 이 수준은 수준 1의 다음 수준입니다.<br>  | 고유하게 위험이 높은 사용자 또는 그룹이 사용하는 장치입니다. 예를 들어 무단 공개로 인해 상당한 재료 손실을 유발하는 매우 중요한 데이터를 처리하는 사용자가 있습니다. | 모바일 위협 방어 또는 Microsoft Defender ATP를 도입하고, 최소 Android 버전을 8.0으로 설정하고, 보다 강력한 암호 정책을 제정하며, 작업 및 개인 분리를 추가로 제한합니다. | [작업 프로필 수준 3 설정](/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| 완전히 관리되는 기본 보안 -수준 1                                                                                | 엔터프라이즈 장치에 대한 최소 보안 구성으로, 직장 또는 학교 데이터에 액세스하는 대부분의 모바일 사용자에게 해당합니다.                                                          | 암호 요구 사항을 도입하고, 최소 Android 버전을 8.0으로 설정하고, 특정 장치 제한을 적용합니다.                                                                          | [완전히 관리되는 수준 1 설정](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| 완전히 관리되는 향상된 보안 수준 2                                                                              | 사용자가 중요한 정보 또는 기밀 정보에 액세스하는 장치.                                                                                                                | 더 강력한 암호 정책을 제정하고 사용자/계정 기능을 사용하지 않도록 합니다.                                                                                                                   | [완전히 관리되는 수준 2 설정](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| 완전히 관리되는 높은 보안 수준 3                                                                                  | 고유하게 위험이 높은 사용자 또는 그룹이 사용하는 장치입니다. 예를 들어 무단 공개로 인해 상당한 재료 손실을 유발하는 매우 중요한 데이터를 처리하는 사용자가 있습니다. | 최소 Android 버전을 10.0으로 증가하고, 모바일 위협 방어 또는 Microsoft Defender ATP를 도입하고, 추가 장치 제한을 적용합니다.                                     | [완전히 관리되는 수준 3 설정](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |

 다른 프레임워크와 함께, 보안이 위협 환경, 위험 요소 및 사용 가능성에 미치는 영향을 평가해야 하기에 해당하는 수준의 설정을 조직의 요구에 따라 조정해야 할 수 있습니다.

## <a name="learn-more"></a>세부 정보

- [Android Enterprise 보안 구성 프레임워크](/mem/intune/enrollment/android-configuration-framework)
- [앱 보호 정책 개요](/mem/intune/apps/app-protection-policy)
- [Android 앱 보호 정책 Microsoft Intune](/mem/intune/apps/app-protection-policy-settings-android)
- [등록 제한 설정](/mem/intune/enrollment/enrollment-restrictions-set)
- [Android Enterprise 보안 백서](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
