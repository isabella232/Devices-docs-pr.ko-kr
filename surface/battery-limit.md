---
title: 배터리 제한 설정(Surface)
description: 배터리 제한은 Surface 디바이스 배터리가 충전되는 방법을 변경하고 수명을 연장하는 UEFI 설정입니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 9cf623a9a4b9d1a8d292cfa0cff25d2e57318db7
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338331"
---
# <a name="battery-limit-setting"></a>배터리 제한 설정

배터리 제한 옵션은 Surface 디바이스 배터리가 충전되는 방법을 변경하고 수명을 연장하는 UEFI 설정입니다. 이 설정은 디바이스가 계속해서 전원에 연결된 경우(예: 디바이스가 키오스크 솔루션에 통합된 경우)에 권장됩니다.  

## <a name="how-battery-limit-works"></a>배터리 제한 작동 방식

배터리 제한으로 장치를 설정하면 디바이스 배터리를 충전하기 위한 프로토콜이 변경됩니다. 배터리 한도를 사용하도록 설정하면 배터리 충전이 최대 용량의 50%로 제한됩니다. 이 설정에 보고된 Windows 이 제한이 반영됩니다. 따라서 배터리가 최대 50%까지 충전되어 이 제한을 초과하여 충전하지 않는 것으로 나타났습니다. 디바이스가 50%를 초과하는 동안 배터리 제한을 사용하도록 설정하면 배터리 아이콘에 장치가 연결되어 있지만 장치가 최대 충전 용량의 50%에 도달할 때까지 장치가 연결되어 있는 것으로 표시됩니다.  

## <a name="supported-devices"></a>지원되는 디바이스

배터리 제한 UEFI 설정은 기본적으로 다음을 포함하여 Surface 장치에 기본 제공됩니다. 

- Surface Pro 7 이상
- Surface Laptop 3 이상
- Surface Book 3
- Surface Laptop Studio
- Surface Laptop 이동
- Surface Studio 2
- Surface Laptop SE

 이전 디바이스에는 [surface UEFI](manage-surface-driver-and-firmware-updates.md) 펌웨어 업데이트가 필요하며, Windows 업데이트 또는 Surface 지원 사이트의 MSI 드라이버 및 펌웨어 패키지를 통해 사용할 [수 있습니다](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface). 지원 [되는 각 장치에 필요한 특정 Surface](https://support.microsoft.com/help/4464941) UEFI 버전에 대해 장시간 연결해야 하는 Surface 디바이스에 대해 "배터리 제한" 사용을 확인합니다.

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-4-and-later"></a>Surface UEFI(Surface Pro 4 이상에서 배터리 제한 사용)

Surface UEFI 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면 **전원 + Vol Up** ). 부팅 **구성을 선택한** 다음 고급 옵션에서 ******배터리 제한 모드** 사용을 설정으로 전환**합니다**.  

![배터리 제한 고급 옵션.](images/enable-bl.png)

## <a name="enabling-battery-limit-on-surface-go-all-generations"></a>Surface Go에서 배터리 제한 사용(모든 세대)

Surface 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면 **전원 + Vol Up** ). 부팅 **구성을 선택한** 다음 키오스크 **** 모드에서 슬라이더를 오른쪽으로 이동하여 배터리 제한을 사용으로 **설정합니다**.  

![Surface Go의 키오스크 모드 배터리 제한.](images/go-batterylimit.png)

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-3"></a>Surface UEFI에서 배터리 제한 사용(Surface Pro 3)

Surface UEFI 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면 **전원 + Vol Up** ). 키 **오스크 모드를 선택하고** **배터리 제한을** 선택한 다음 사용 을 **선택합니다**.

![고급 옵션의 스크린샷.](images/enable-bl-sp3.png)

![고급 옵션.](images/enable-bl-sp3-2.png)

## <a name="enabling-battery-limit-using-surface-enterprise-management-mode-semm-or-surface-pro-3-firmware-powershell-scripts"></a>Surface Enterprise 관리 모드(SEMM) 또는 Surface Pro 3 펌웨어 PowerShell 스크립트를 사용하여 배터리 제한 사용

Surface UEFI 배터리 제한은 다음 방법을 통해 구성에도 사용할 수 있습니다.

- Surface Pro 4 이상
  - [Microsoft Surface UEFI 구성기](surface-enterprise-management-mode.md)  
    - [IT용 Surface](https://www.microsoft.com/download/details.aspx?id=46703) 도구 다운로드의 Surface UEFI 관리자 powershell 스크립트(SEMM_Powershell.zip)

### <a name="using-microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI 구성기 사용

배터리 제한 모드를 구성하려면 SEMM(**** 설정 이상)의 고급 설정 페이지에서 키오스크 Surface Pro 4 **** 설정하세요.

![고급 설정 스크린샷.](images/semm-bl.png)

### <a name="using-surface-uefi-manager-powershell-scripts"></a>Surface UEFI 관리자 PowerShell 스크립트 사용

배터리 제한 기능은 다음 설정을 통해 제어됩니다.  

`407 = Battery Profile`

**설명**: 배터리 사용 패턴에 대한 활성 관리 체계

**기본값**:  `0`

배터리 제한을 `1` 사용하도록 설정하려면 이 설정을 설정하십시오.
