---
title: Windows Autopilot 및 Surface 디바이스
ms.reviewer: ''
manager: laurawi
description: Surface 장치에 대 한 Windows Autopilot 배포 옵션에 대해 알아보세요.
keywords: autopilot, windows 10, surface, 배포
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834620"
---
# Windows Autopilot 및 Surface 디바이스

Windows Autopilot는 Windows 10의 클라우드 기반 배포 기술입니다. Windows Autopilot를 사용 하 여 상자를 바로 사용할 수 있는 0-터치식 프로세스에서 장치를 원격으로 배포 하 고 구성 합니다.

Windows Autopilot에서 등록 된 디바이스는 *하드웨어 해시*라고 하는 고유한 장치 서명을 통해 처음 시작 될 때 인터넷을 통해 식별 됩니다. Azure AD (azure Active Directory) 및 모바일 장치 관리와 같은 최신 관리 솔루션을 사용 하 여 자동으로 등록 하 고 구성 합니다.

Windows Autopilot에 대해 사용 하도록 설정 된 Surface 파트너에서 구매할 때 Surface 장치를 등록할 수 있습니다. 이러한 파트너는 사용자에 게 직접 새 장치를 제공할 수 있습니다. 디바이스는 처음 켤 때 자동으로 등록 되 고 구성 됩니다. 이 프로세스는 배포 중에 reimaging를 제거 하 여 장치 관리 및 배포의 새로운 agile 메서드를 구현할 수 있도록 합니다.

## 최신 관리

Autopilot는 Autopilot를 통해 배포용으로 설계 된 surface Pro 7, Surface 랩톱 3 및 surface Pro X를 포함 하 여 Surface 디바이스에 권장 되는 배포 옵션입니다.

 Microsoft 클라우드 솔루션 공급자의 도움말을 사용 하 여 Surface 디바이스를 등록 하는 것이 좋습니다. 이 단계에서는 Intune에서 직접 UEFI 펌웨어 설정을 관리할 수 있습니다. 이를 통해 인증서 관리를 위해 디바이스를 물리적으로 터치 해야 할 필요가 없어집니다. 자세한 내용은 [SURFACE UEFI 설정의 Intune management을](surface-manage-dfci-guide.md) 참조 하세요.

## Windows 버전 고려 사항

구매할 때 Surface 파트너의 등록을 포함 하 여 Windows Autopilot를 통해 Surface 디바이스를 광범위 하 게 배포 하는 경우 Windows 10 버전 1709 (낙하 생성기 업데이트) 이상이 필요 합니다.

이러한 Windows 버전에서는 확장 시 배포에 필요한 Windows Autopilot 장치를 고유 하 게 식별 하는 4000 바이트 (4k) 해시 값을 지원 합니다. Surface Pro 7, Surface Pro X, Surface 노트북 3을 비롯 한 모든 새 Surface 장치는 Windows 10 버전 1903 이상에 제공 됩니다.

## 복구 또는 교체 필요에 따라 Surface 디바이스의 Exchange 환경

Microsoft는 Autopilot 등록을 위해 모든 화면을 자동으로 확인 하 고 고객의 테 넌 트에서 장치를 등록 합니다.  Microsoft는 대체 장치가 고객에 게 다시 배송 되 면 대체 장치를 Windows Autopilot에 등록할 수 있도록 합니다. 이 서비스는 모든 장치 교환 서비스에서 Microsoft와 직접 주문할 수 있습니다.

> [!NOTE]
> 고객이 파트너를 사용 하 여 디바이스를 반환 하는 경우 파트너는 deregistering 및 Windows Autopilot에 등록 하는 장치를 포함 하 여 exchange 프로세스를 관리 해야 합니다.

## Windows Autopilot에 대해 사용 하도록 설정 된 Surface 파트너

Surface 파트너 선택은 Windows Autopilot에서 구매할 때 사용자에 게 Surface 디바이스를 등록할 수 있습니다. 또한 등록 된 디바이스를 사용자에 게 직접 제공할 수 있습니다. 장치는 Windows Autopilot, Azure AD 및 모바일 장치 관리를 사용 하 여 0 터치 프로세스를 통해 완전히 구성할 수 있습니다.

Windows Autopilot으로 설정 되는 Surface 파트너는 다음과 같습니다.

| 미국 파트너 | 글로벌 파트너 | 미국 대리점 |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [수도](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [연결](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [정보](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [이 진 영문법](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [SHI](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [고 대 인 acenter](https://www.computacenter.com/uk) |    |
| * [보려면](https://www.functiononeit.com/#empower)  |   |  |
| * [보호 된 신뢰](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## 자세히 알아보기

Windows Autopilot에 대 한 자세한 내용은 다음을 참조 하세요.
- [Windows Autopilot 개요](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 요구 사항](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)