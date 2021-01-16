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
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271145"
---
# 배터리 제한 설정

배터리 제한 옵션은 Surface 디바이스 배터리가 충전되는 방법을 변경하고 수명을 연장하는 UEFI 설정입니다. 이 설정은 디바이스가 계속해서 전원에 연결된 경우(예: 디바이스가 키오스크 솔루션에 통합된 경우)에 권장됩니다.  

## 배터리 제한 작동 방식

디바이스를 배터리 제한으로 설정하면 디바이스 배터리를 충전하기 위한 프로토콜이 변경됩니다. 배터리 한도를 사용하도록 설정하면 배터리 충전이 최대 용량의 50%로 제한됩니다. Windows에서 보고되는 요금 수준에는 이 제한이 반영됩니다. 따라서 배터리가 최대 50%까지 충전되어 이 제한을 초과하여 충전되지 않는 것으로 나타났습니다. 장치가 50% 충전을 초과하는 동안 배터리 제한을 사용하도록 설정하면 배터리 아이콘에 장치가 연결되어 있지만 장치가 최대 충전 용량의 50%에 도달할 때까지 전원이 방전된 것으로 표시됩니다.  

## 지원되는 디바이스

배터리 제한 UEFI 설정은 Surface Pro 7+, Surface Pro 7 및 Surface Laptop 3을 비롯한 최신 Surface 디바이스에 기본으로 제공합니다. 이전 디바이스에는 Windows 업데이트 또는 Surface 지원 사이트의 MSI 드라이버 및 펌웨어 패키지를 통해 사용할 수 있는 [Surface UEFI](manage-surface-driver-and-firmware-updates.md)펌웨어 [업데이트가 필요합니다.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface) 지원되는 각 장치에 필요한 특정 Surface UEFI 버전에 대해 장시간 연결해야 하는 Surface 디바이스에 대해 ["배터리 제한"을](https://support.microsoft.com/help/4464941) 사용하도록 설정하세요. 

## Surface UEFI에서 배터리 제한 사용(Surface Pro 4 이상)

Surface UEFI 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면**전원 + Vol Up).** 부팅 **구성을 선택한**다음 **** 고급 옵션에서 배터리 **제한** 모드를 으로 **전환합니다.**  

![배터리 제한 고급 옵션](images/enable-bl.png) 

## Surface Go 및 Surface Go 2에서 배터리 제한 사용
Surface UEFI로 부팅하여 Surface 배터리 제한 설정을 구성할 수 있습니다(디바이스를 끄면**전원 + Vol Up).** 부팅 **구성을 선택한**다음 **키오스크**모드에서 슬라이더를 오른쪽으로 이동하여 배터리 제한을 사용으로 **설정합니다.**  

![Surface Go의 키오스크 모드 배터리 제한](images/go-batterylimit.png) 

## Surface UEFI에서 배터리 제한 사용(Surface Pro 3)

Surface UEFI 배터리 제한 설정은 Surface UEFI로 부팅하여 구성할 수 있습니다(디바이스를 켜면**전원 + Vol Up).** **키오스크**모드를 선택하고 배터리 **제한을**선택한 다음 사용을 **선택합니다.**

![고급 옵션 스크린샷](images/enable-bl-sp3.png) 

![고급 옵션](images/enable-bl-sp3-2.png) 

## Surface Enterprise Management Mode(SEMM) 또는 Surface Pro 3 펌웨어 PowerShell 스크립트를 사용하여 배터리 제한 사용

Surface UEFI 배터리 제한은 다음 방법을 통해 구성에 사용할 수 있습니다.

- Surface Pro 4 이상 
    - [Microsoft Surface UEFI 구성기](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - IT용 Surface 도구의 [Surface](https://www.microsoft.com/download/details.aspx?id=46703) UEFI 관리자 Powershell 스크립트(SEMM_Powershell.zip)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Microsoft Surface UEFI 구성기 사용

배터리 제한 모드를 구성하려면 SEMM(Surface Pro **4 이상)의** 고급 설정 구성 페이지에서 키오스크 오버라이드 설정을 설정하십시오. ****

![고급 설정 스크린샷](images/semm-bl.png)

### Surface UEFI 관리자 PowerShell 스크립트 사용

배터리 제한 기능은 다음 설정을 통해 제어됩니다.  

`407 = Battery Profile`

**설명:** 배터리 사용 패턴에 대한 활성 관리 스키마

**기본값:**  `0` 

배터리 `1` 제한을 사용하도록 설정하려면 이 설정을 설정하십시오.

### Surface Pro 3 펌웨어 도구 사용

배터리 제한 기능은 다음 설정을 통해 제어됩니다.  

**이름:** BatteryLimitEnable

**설명:** BatteryLimit

**현재 값:**  `0` 

**기본값:** `0`

**제안된 값:** `0` 

배터리 `1` 제한을 사용하도록 설정하려면 이 설정을 설정하십시오.

>[!NOTE]
>이 설정을 구성하려면 [ 다음을 ](https://www.microsoft.com/download/details.aspx?id=46703)SP3_Firmware_Powershell_Scripts.zip. 

