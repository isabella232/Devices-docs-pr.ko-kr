---
title: Windows Autopilot 및 Surface 디바이스
ms.reviewer: ''
manager: laurawi
description: Surface 디바이스에 Windows Autopilot 배포 옵션에 대해 설명합니다.
keywords: autopilot, Windows 10, Windows 11, surface, deployment
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ca2dab5483ecb7ae11a102c56308742e348156bb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448531"
---
# <a name="windows-autopilot-and-surface-devices"></a>Windows Autopilot 및 Surface 디바이스

Windows Autopilot은 Windows 10 클라우드 기반 배포 Windows 11. Autopilot을 Windows 제로 터치 프로세스에서 바로 장치를 원격으로 배포하고 구성할 수 있습니다.

일반적으로 IT 프로는 이미 완전히 좋은 OS가 이미 설치된 디바이스에 배포될 이미지를 구축하고 사용자 지정하는 데 많은 시간을 소비합니다. Windows Autopilot은 여러 기술 모음을 사용하여 새로운 제로 터치 배포 접근 방식을 도입하고 Windows 합니다. 이를 통해 IT 부서는 관리할 인프라가 거의 또는 없는 이미지와 쉽고 간단한 프로세스를 구성/사용자 지정할 수 있습니다. 사용자의 관점에서 보면 Surface를 생산성 상태로 설정하는 데 몇 가지 간단한 단계만 수행하면 됩니다. 실제로 최종 사용자에게 필요한 유일한 상호 작용은 네트워크에 연결하고 자격 증명을 확인하는 것입니다. 그 이후의 모든 것은 완전히 자동화됩니다.

Windows Autopilot을 사용하여 다음을 할 수 있습니다.

- 디바이스를 Azure AD(Azure Active Directory 자동으로 연결합니다.
- 장치와 같은 MDM 서비스에 장치를 Microsoft Intune(Azure AD Premium 등록해야 합니다.
- 관리자 계정 생성을 제한하십시오. Autopilot은 로그인하는 첫 번째 사용자가 표준 사용자로 Windows 유일한 방법입니다.
- 디바이스 프로필을 기반으로 구성 그룹에 장치를 만들고 자동으로 할당합니다.
- 조직 요구 사항을 충족하기 위해 OOBE(Out of Box Experience) 콘텐츠 및 브랜더링을 사용자 지정합니다.
- Intune을 사용하여 전체 장치 구성을 사용하도록 설정
- 원격으로 장치를 초기화하거나 다시 시작합니다.

## <a name="how-it-works"></a>작동 방식

Windows Autopilot 등록 장치는 처음 시작할 때 하드웨어 해시라고 하는 고유한 장치 서명을 통해 인터넷을 통해 *식별됩니다*. Azure AD(Azure AD) 및 모바일 장치 관리와 같은 최신 관리 Azure Active Directory 자동으로 등록되고 구성됩니다.

Autopilot을 사용할 수 있는 Surface 파트너로부터 구매 시 Surface 디바이스를 등록할 Windows 있습니다. 이러한 파트너는 사용자에게 직접 새 장치를 배송할 수 있습니다. 장치를 처음 켜면 장치가 자동으로 등록되고 구성됩니다. 이 프로세스는 배포 중에 다시 구현되지 않습니다. 이를 통해 장치 관리 및 배포의 새로운 agile 방법을 구현할 수 있습니다.

## <a name="modern-management"></a>최신 관리

Autopilot은 Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Pro 7+, Surface Laptop 4 및 Surface Pro X를 비롯한 Surface 디바이스에 권장되는 배포 옵션입니다. 이 옵션은 Autopilot을 통해 배포하도록 특별히 디자인되었습니다.

 Surface 디바이스를 등록하는 것이 가장 Microsoft 클라우드 솔루션 공급자. 이 단계를 통해 Intune에서 직접 Surface에서 UEFI 펌웨어 설정을 관리할 수 있습니다. 인증서 관리를 위해 디바이스를 물리적으로 터치할 필요가 없습니다. 자세한 [내용은 Surface UEFI 설정의 Intune](surface-manage-dfci-guide.md) 관리를 참조하세요.

## <a name="windows-version-considerations"></a>Windows 고려 사항

구매 시 Surface 파트너의 등록을 포함하여 Windows Autopilot을 통해 Surface 디바이스를 광범위하게 배포하려면 Windows 10 버전 1709(Fall Creators Update) 이상이 필요합니다.

이러한 Windows 버전은 대규모 배포에 필요한 Windows Autopilot의 장치를 고유하게 식별하는 4,000비트(4k) 해시 값을 지원합니다.

## <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Exchange 교체가 필요한 Surface 디바이스에서 환경 제공

Microsoft는 Autopilot 등록을 위해 모든 Surface를 자동으로 확인하고 고객의 테넌트에서 디바이스의 등록을 다시 등록합니다.  Microsoft는 대체 장치를 고객에게 다시 Windows Autopilot에 등록합니다. 이 서비스는 Microsoft와 직접 모든 장치 교환 서비스 주문 시 사용할 수 있습니다.

> [!NOTE]
> 고객이 파트너를 사용하여 디바이스를 반환하는 경우 파트너는 Autopilot에 장치 등록을 등록 및 등록하는 등 교환 프로세스를 Windows 담당합니다.

## <a name="microsoft-support-registration"></a>Microsoft 지원 등록

고객 및 Microsoft CSP(클라우드 솔루션 공급자)는 Microsoft 지원에 요청을 제출하여 Surface 디바이스를 등록할 수 있습니다. 자세한 내용은 [Autopilot에 대한 Surface 등록 Windows 참조합니다](surface-autopilot-registration-support.md).

## <a name="surface-partners-enabled-for-windows-autopilot"></a>Autopilot에서 사용할 수 Windows Surface 파트너

Surface 파트너가 구매 시 Windows Autopilot에서 Surface 디바이스를 등록할 수 있습니다를 선택합니다. 등록된 장치를 사용자에게 직접 배송할 수도 있습니다. Autopilot, Azure AD 및 모바일 장치 관리를 사용하여 Windows 제로 터치 프로세스를 통해 장치를 구성할 수 있습니다.

Autopilot에서 사용할 수 있는 surface 파트너는 Windows 있습니다.

| 미국 파트너 | 글로벌 파트너 | 미국 배포자 |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [또한](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  [연결](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [인사이트](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [베틀](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [인그램](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [SHI](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI 커넥트](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [보호된 트러스트](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## <a name="learn-more"></a>세부 정보

Autopilot에 대한 Windows 자세한 내용은 다음을 참조하세요.

- [Windows Autopilot 개요](/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 요구 사항](/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Windows Autopilot용 Surface 등록 지원](surface-autopilot-registration-support.md)
