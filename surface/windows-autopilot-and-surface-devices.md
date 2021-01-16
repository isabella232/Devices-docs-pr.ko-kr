---
title: Windows Autopilot 및 Surface 디바이스
ms.reviewer: ''
manager: laurawi
description: Surface 디바이스에 대한 Windows Autopilot 배포 옵션에 대해 설명합니다.
keywords: autopilot, windows 10, surface, deployment
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
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271104"
---
# Windows Autopilot 및 Surface 디바이스

Windows Autopilot은 Windows 10의 클라우드 기반 배포 기술입니다. Windows Autopilot을 사용하여 제로 터치 프로세스에서 바로 원격으로 디바이스를 배포하고 구성할 수 있습니다.

일반적으로 IT pros는 이미 완벽하게 양호한 OS가 이미 설치된 디바이스에 배포될 이미지를 구축하고 사용자 지정하는 데 많은 시간을 소비합니다. Windows Autopilot은 Windows 장치를 설정하고 구성하는 기술 모음을 사용하여 새로운 제로 터치 배포 접근 방식을 도입했습니다. 이를 통해 IT 부서는 관리할 인프라와 간편하고 간단한 프로세스를 통해 이미지를 구성/사용자 지정할 수 있습니다. 사용자의 관점에서 볼 때 Surface를 생산적인 상태로 설정하는 데 몇 가지 간단한 단계만 수행하면 됩니다. 실제로 최종 사용자에게 필요한 유일한 상호 작용은 네트워크에 연결하고 자격 증명을 확인하는 것입니다. 그 이후의 모든 것은 완전히 자동화됩니다.

Windows Autopilot을 사용하면 다음을 할 수 있습니다.

- 장치를 Azure AD(Azure Active Directory)에 자동으로 가입합니다.
- Microsoft Intune과 같은 MDM 서비스에 장치를 자동 등록합니다(Azure AD Premium 구독 필요).
- 관리자 계정 생성을 제한하십시오. Autopilot은 Windows에 로그인하는 첫 번째 사용자가 표준 사용자로 입력하도록 하는 유일한 방법입니다.
- 디바이스 프로필을 기반으로 구성 그룹에 장치를 만들고 자동으로 할당합니다.
- 조직 요구 사항을 충족하기 위해 OOBE(Out of Box Experience) 콘텐츠 및 브랜더를 사용자 지정합니다.
- Intune을 사용하여 전체 장치 구성을 사용하도록 설정
- 원격으로 장치를 초기화하거나 다시 시작합니다.

## 작동 방식

Windows Autopilot 등록 장치는 처음 시작할 때 하드웨어 해시라고 하는 고유한 장치 서명을 통해 인터넷을 통해 *식별됩니다.* Azure AD(Azure Active Directory) 및 모바일 장치 관리와 같은 최신 관리 솔루션을 사용하여 자동으로 등록되고 구성됩니다.

Windows Autopilot을 사용할 수 있는 Surface 파트너에서 구매 시 Surface 디바이스를 등록할 수 있습니다. 이러한 파트너는 사용자에게 직접 새 장치를 배송할 수 있습니다. 장치를 처음 켜면 디바이스가 자동으로 등록되고 구성됩니다. 이 프로세스는 배포 중에 다시imaging을 제거하여 장치 관리 및 배포의 새로운 Agile 방법을 구현할 수 있도록 합니다.

## 최신 관리

Autopilot은 Autopilot을 통해 배포하도록 특별히 설계된 Surface Pro 7+, Surface Laptop 3, Surface Pro 7 및 Surface Pro X를 비롯한 Surface 디바이스에 권장되는 배포 옵션입니다.

 Microsoft 클라우드 솔루션 공급자의 도움을 통해 Surface 디바이스를 등록하는 것이 가장 좋은 방법입니다. 이 단계를 통해 Intune에서 직접 Surface에서 UEFI 펌웨어 설정을 관리할 수 있습니다. 인증서 관리를 위해 디바이스를 물리적으로 터치할 필요가 없습니다. 자세한 [내용은 Surface UEFI 설정의 Intune](surface-manage-dfci-guide.md) 관리를 참조하세요.

## Windows 버전 고려 사항

구매 시 Surface 파트너의 등록을 포함하여 Windows Autopilot을 통해 Surface 디바이스를 광범위하게 배포하려면 Windows 10 버전 1709(가을 크리에이터스 업데이트) 이상이 필요합니다.

이러한 Windows 버전은 대규모 배포에 필요한 Windows Autopilot 디바이스를 고유하게 식별하는 4,000비트 해시 값을 지원합니다. Surface Pro 7+, Surface Pro X 및 Surface Laptop 3을 비롯한 모든 새 Surface 디바이스는 Windows 10 버전 1903 이상과 함께 출시됩니다.

## 수리 또는 교체가 필요한 Surface 디바이스의 Exchange 환경

Microsoft는 모든 Surface에서 Autopilot 등록을 자동으로 확인하고 고객의 테넌트에서 디바이스의 등록을 다시 등록을 해지합니다.  Microsoft는 대체 장치를 고객에게 다시 배송하면 대체 장치가 Windows Autopilot에 등록되도록 합니다. 이 서비스는 모든 장치 교환 서비스 주문 시 Microsoft와 직접 사용할 수 있습니다.

> [!NOTE]
> 고객이 파트너를 사용하여 디바이스를 반환하는 경우 파트너는 디바이스 등록을 등록을 후 Windows Autopilot에 등록하는 등 Exchange 프로세스를 관리할 책임이 있습니다.

## Microsoft 지원 등록

고객과 Microsoft 클라우드 솔루션 공급자(CSP)는 Microsoft 지원에 요청을 제출하여 Surface 디바이스를 등록할 수 있습니다. 자세한 내용은 [Windows Autopilot에 대한 Surface 등록 지원을 참조합니다.](surface-autopilot-registration-support.md)

## Windows Autopilot에 사용할 수 있는 Surface 파트너

Surface 파트너를 선택하면 구매 시 Windows Autopilot에서 Surface 디바이스를 등록할 수 있습니다. 등록된 장치를 사용자에게 직접 배송할 수도 있습니다. Windows Autopilot, Azure AD 및 모바일 장치 관리를 사용하여 제로 터치 프로세스를 통해 장치를 완전히 구성할 수 있습니다.

Windows Autopilot을 사용할 수 있는 Surface 파트너는 다음과 같습니다.

| 미국 파트너 | 글로벌 파트너 | 미국 배포자 |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [또한](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [연결](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [인사이트](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [베틀](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [인그램](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [SHI](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI 연결](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [보호된 트러스트](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## 자세히 알아보기

Windows Autopilot에 대한 자세한 내용은 다음을 참조하세요.
- [Windows Autopilot 개요](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Windows Autopilot용 Surface 등록 지원](surface-autopilot-registration-support.md)