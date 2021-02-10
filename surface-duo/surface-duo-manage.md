---
title: Surface Duo 관리 개요
description: 이 문서에서는 상업적 환경에서 Surface Duo를 관리하기 위한 옵션을 중시합니다.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/23/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 19ef3f5d20b22997aa339a462a34b84da27fb922
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326231"
---
# Surface Duo 관리 개요

상용 고객은 직원 또는 회사 소유 장치를 관리하는지 여부에 관계 없이 일관된 클라우드 기반 장치 관리 기능을 제공하는 다양한 EMM(Enterprise Mobility Management) 솔루션을 사용하여 Surface Duo를 관리할 수 있습니다.

통합 콘솔인 Microsoft Endpoint Manager 및 Microsoft Intune과 같은 extensible 구성 요소를 사용하는 [Microsoft EMM을](https://androidenterprisepartners.withgoogle.com/provider/#!/75) 통해 Duo 관리 Duo를 관리할 수 있습니다. 또는 Google의 Android 에코시스템에서 모든 EMM 공급자를 사용할 수 있습니다. 경우에 따라 타사 EMM 솔루션은 환경에 따라 유용할 수 있는 특정 시나리오를 충족하기 위해 추가 지원을 제공합니다.

 EMM 솔루션을 비교하기 위해 [Android Enterprise Solutions 디렉터리를 참조하세요.](https://androidenterprisepartners.withgoogle.com/emm/)
Intune을 사용하여 끝점 관리자를 사용하면 최신 모바일 장치 관리 정책과 이전 기술(예: intune)을 사용하여 Duo를 관리할 Exchange ActiveSync. 이미 Exchange ActiveSync 설정을 사용하여 모바일 장치를 관리하는 경우 전자 메일 장치 구성 프로필을 사용하여 Intune을 사용하여 Duo 장치에 해당 설정을 적용할 수 있습니다.  자세한 내용은 Intune을 사용하여 장치에 전자 [메일 설정 추가를 참조하세요.](https://docs.microsoft.com/mem/intune/configuration/email-settings-configure)

Intune에서 장치를 관리하는 기본 수단인 프로필은 조직의 요구에 맞게 사용자 지정할 수 있는 기본 설정을 제공합니다. 

## 개인 소유의 Surface Duo 장치 관리
| 솔루션                                          | 기능                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | 자세히 알아보기                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 장치 등록이 없는 앱 보호 정책 | 응용 프로그램 내에서 조직의 데이터를 관리하고 보호할 수 있습니다.<br>장치 등록 없이 경량 관리 솔루션인 앱 보호 정책을 배포합니다.<br>이제 Adobe Acrobat, 서비스 시작 및 확대/축소와 같은 Microsoft Office 및 타사 앱을 비롯한 앱 보호 정책을 사용하여 점점 더 많은 앱을 관리할 수 있습니다. 전체 목록은 Microsoft [Intune으로](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps)보호되는 앱을 참조하세요. | - [앱 보호 정책 개요](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)<br>- [Microsoft Intune의 Android](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)앱 보호 정책 설정<br>- [Intune 앱 래핑](https://docs.microsoft.com/mem/intune/developer/app-wrapper-prepare-android)도구를 사용하여 앱 보호 정책에 대한 Android 앱을 준비합니다. |
| Android Enterprise 작업 프로필                   | BYOD 배포를 대상으로 하는 작업 프로필은 조직에서 개인 앱 및 데이터에 대한 장치를 사용하지 못하도록 제한하지 않고 데이터, 앱 및 보안 정책을 완전하게 제어할 수 있도록 Duo에 별도의 공간을 제공합니다.                                                                                                                                                                                                                                                  | - [Surface Duo에 대한 Android 엔터프라이즈 작업 프로필을 구성합니다.](surface-duo-config-work-profile.md)                                                                                                                                                                                                                                                                                                               |


## 회사 소유의 Surface Duo 장치 관리

| 솔루션                                  | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | 자세히 알아보기                                                                                                                                                                                                                                                                                                      |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 회사 프로필이 있는 회사 소유 장치 | 업무를 위해 제공한 회사 소유의 단일 사용자 장치에서 개인 사용을 사용하도록 설정하고자 하는 조직을 대상으로 합니다. 조직에서 작업 프로필을 관리하는 것보다 더 세부적으로 제어할 수 있도록 설계되지만 전체 장치 관리 또는 전용 장치 관리를 사용하여 장치를 완전히 잠그는 것은 원하지 않습니다.<br>Android OS로 격리된 작업 및 개인 프로필 앱 데이터는 관리자에게 더 많은 장치 수준 제어를 제공하여 Android 엔터프라이즈 작업 프로필과 다릅니다.<br>IT 관리자는 작업 프로필에서 작업 계정, 응용 프로그램 및 데이터를 보고 제어하고 구성할 수 있으며 최종 사용자는 관리자가 개인 프로필의 데이터 및 응용 프로그램을 볼 수 없음을 보장합니다. | - [회사 프로필을 사용하여 Android Enterprise 회사 소유 장치에 대한 공개 미리 보기를 발표하는 Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-announcing-public-preview-for-android-enterprise/ba-p/1524325)                                                                    |
| Android Enterprise 완전 관리          | 단일 사용자와 연결된 회사 소유 디바이스에 대한 포괄적인 장치 및 앱 관리 기능을 개인용이 아닌 업무 전용으로 활용합니다.<br> <br>전체 장치 관리를 통해 IT는 장치 데이터 및 보안을 완전하게 제어할 수 있으며 Android의 전체 앱 관리 기능 제품군에 액세스할 수 있습니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.<br><br>- 장치에서 최소 암호 요구 사항을 설정할 수 있습니다.<br>- 원격으로 장치 지우기 및 잠금<br>- 앱 사용 권한 요청에 대한 기본 응답을 설정합니다.<br>- Microsoft 시작 프로그램을 통해 최종 사용자 환경 사용자 지정<br><br>또한 원격으로 앱을 설치 및 제거하는 기능을 포함하여 디바이스의 앱에 대한 모든 제어가 있습니다.                                 | - [Android Enterprise 완전히 관리되는 장치의 Intune 등록을 설정합니다.](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-enroll) |
| 전용 장치 관리               | 이 엔터프라이즈 배포 시나리오는 운송, 교통 및 공장 층과 같은 특정 사용 사례에 배포된 장치를 대상으로 합니다. 앱을 하나 또는 두 개로 제한하고 사용자가 설정을 변경하지 못하도록 해야 하는 잠긴 환경을 위해 사용합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                           | - [Android Enterprise 전용 장치의 Intune 등록 설정](https://docs.microsoft.com/mem/intune/enrollment/android-kiosk-enroll)                                                                                                                                                               |

 
## 자세히 알아보기
- [Ignite 세션: 엔터프라이즈에서 Surface Duo를 사용하여 생산성 배포, 관리 및 사용](https://youtu.be/DOsBMNFmdfw)
- [Microsoft Intune을 사용하여 장치 관리](https://docs.microsoft.com/mem/intune/remote-actions/device-management)
- [Intune 배포 계획, 디자인 및 구현 가이드](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [Intune으로 Android 장치 등록](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)
