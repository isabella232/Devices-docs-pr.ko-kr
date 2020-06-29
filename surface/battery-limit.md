---
title: 배터리 제한 설정 (Surface)
description: 배터리 제한은 Surface 디바이스 배터리가 충전 되는 방법을 변경 하는 UEFI 설정 이며 해당 수명 기간 연장 될 수 있습니다.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835988"
---
# 배터리 제한 설정

배터리 제한 옵션은 Surface 디바이스 배터리가 충전 되는 방법을 변경 하는 UEFI 설정으로, 해당 수명 기간을 연장 시킬 수 있습니다. 장치를 키오스크 솔루션에 통합 하는 등의 경우와 같이 장치가 전원이 계속 연결 되어 있는 경우이 설정이 권장 됩니다.  

## 배터리 제한 작동 방식

배터리 용량으로 장치를 설정 하면 디바이스 배터리 충전에 대 한 프로토콜이 변경 됩니다. 배터리 한계를 사용 하는 경우 배터리 충전량이 최대 용량을 50%로 제한 합니다. Windows에 보고 된 충전 수준에 따라이 한도가 반영 됩니다. 따라서 배터리가 최대 50%까지 충전 되어 있으며,이 한도를 초과 하 여 충전 되지 않습니다. 장치가 50% 충전을 초과 하는 동안 배터리 용량 한도를 사용 하는 경우 배터리 아이콘에 장치가 연결 되어 있지만 장치가 최대 충전 용량의 50%에 도달할 때까지 방전 됨을 표시 합니다.  

## 지원되는 디바이스
배터리 한도 UEFI 설정은 Surface Pro 7 및 Surface 노트북 3을 비롯 한 최신 Surface 장치에 기본으로 제공 됩니다. 이전 장치에는 Windows Update를 통해 또는 [Surface Support 사이트](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)의 MSI 드라이버와 펌웨어 패키지를 통해 사용할 수 있는 [surface UEFI 펌웨어 업데이트가](manage-surface-driver-and-firmware-updates.md)필요 합니다. 지원 되는 각 장치에 필요한 특정 Surface UEFI 버전에 대해 [오랜 시간 동안 연결 되어야 하는 Surface 디바이스에 대해 "배터리 한도" 사용을](https://support.microsoft.com/help/4464941) 선택 합니다. 

## Surface UEFI (Surface Pro 4 이상)에서 배터리 한도 사용

Surface uefi 배터리 제한 설정은 Surface UEFI로 부팅 하 여 구성할 수 있습니다 (장치를 켤 때**Power + 볼륨 위로** 전환). **부팅 구성을**선택한 다음 **고급 옵션**에서 **배터리 잔량 사용 모드** **를 켜기로 전환 합니다.**  

![고급 옵션 스크린샷](images/enable-bl.png) 

## Surface Go 및 Surface Go에서 배터리 한도 사용 설정 2
Surface 전지 제한 설정은 Surface UEFI로 부팅 하 여 구성할 수 있습니다 (장치를 켤 때**Power + 볼륨 위로** 전환). **부팅 구성을**선택한 다음 **키오스크 모드**아래에서 슬라이더를 오른쪽으로 이동 하 여 배터리 용량 제한을 **사용**으로 설정 합니다.  

![화면 이동의 키오스크 모드 배터리 제한 스크린샷](images/go-batterylimit.png) 

## Surface UEFI (Surface Pro 3)에서 배터리 한도 사용

Surface uefi 배터리 제한 설정은 Surface UEFI로 부팅 하 여 구성할 수 있습니다 (장치를 켤 때**Power + 볼륨 위로** 전환). **키오스크 모드**를 선택 하 고 **배터리 제한을**선택한 다음 **사용**을 선택 합니다.

![고급 옵션 스크린샷](images/enable-bl-sp3.png) 

![고급 옵션 스크린샷](images/enable-bl-sp3-2.png) 

## Surface Enterprise 관리 모드 (SEMM) 또는 Surface Pro 3 펌웨어 PowerShell 스크립트를 사용 하 여 배터리 한도 사용

Surface UEFI 배터리 제한은 다음 방법을 통해 구성할 수도 있습니다.

- Surface Pro 4 이상 
    - [Microsoft Surface UEFI 구성자](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - [IT 다운로드 Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 의 Surface UEFI Manager Powershell 스크립트 (SEMM_Powershell.zip)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Microsoft Surface UEFI 구성자 사용

배터리 제한 모드를 구성 하려면 **고급 설정** 구성 페이지의 **키오스크 무시** 설정을 Semm (Surface Pro 4 이상)으로 설정 합니다.

![고급 설정 스크린샷](images/semm-bl.png)

### Surface UEFI 관리자 PowerShell 스크립트 사용

배터리 제한 기능은 다음 설정을 통해 제어 됩니다.  

`407 = Battery Profile`

**설명**: 배터리 사용 패턴에 대 한 활성 관리 체계

**기본값**:  `0` 

`1`배터리 용량을 사용 하도록 설정 합니다.

### Surface Pro 3 펌웨어 도구 사용

배터리 제한 기능은 다음 설정을 통해 제어 됩니다.  

**이름**: BatteryLimitEnable

**설명**: BatteryLimit

**현재 값**:  `0` 

**기본 값**: `0`

**제안 된 값**: `0` 

`1`배터리 용량을 사용 하도록 설정 합니다.

>[!NOTE]
>이 설정을 구성 하려면 [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)를 사용 해야 합니다. 

