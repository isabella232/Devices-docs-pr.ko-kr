---
title: Surface 시스템 SKU 참조
description: 모든 Surface 디바이스에 대한 시스템 모델 및 시스템 SKU 이름 참조를 참조합니다.
keywords: uefi, 구성, 펌웨어, 보안, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/27/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 0fe13750e7e8c8188b52726c114a6b3668434d39
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304831"
---
# Surface 시스템 SKU 참조

이 문서에서는 Windows Autopilot에 Surface 디바이스를 등록하거나 PowerShell 또는 WMI를 사용하여 특정 장치의 컴퓨터 상태를 확인하는 등 다양한 IT 작업에 사용할 수 있는 참조를 제공합니다.

시스템 모델 및 시스템 SKU는 Surface 디바이스의 UEFI 계층에 있는 SMBIOS(시스템 관리 BIOS) 테이블에 저장되는 변수입니다. Surface Pro 및 Surface Pro with LTE Advanced와 같이 시스템 모델 이름이 동일한 디바이스를 차별화해야 할 때마다 시스템 SKU 이름을 사용 합니다.

| Device   | 시스템 모델 | System SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE 북미                                  | Surface 3        | Surface_3_NAG                    |
| 북미 외의 Surface 3 LTE 및 일본 Y!mobile | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Commercial | 시스템 이동 | Surface_Go_1825_Commercial |
| Surface Go 소비자                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 소비자                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| surface 노트북                                               | surface 노트북   | Surface_Laptop                   |
| Surface 노트북 2 소비자                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| SQ2 프로세서가 있는 Surface Pro X                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13인치 Intel | Surface 노트북 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15인치 Intel | Surface 노트북 3 | Surface_Laptop_3_1872      |
| Surface 노트북 3 15인치 AMD   | Surface 노트북 3 | Surface_Laptop_3_1873      | 
| Surface 노트북 이동  | Surface 노트북 이동 | Surface_Laptop_Go_1943      | 

## 예 

**PowerShell을 사용하여 SKU 검색**  
다음 PowerShell 명령을 사용하여 시스템 SKU 정보를 끌어오면 됩니다.

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**시스템 정보를 사용하여 SKU 검색**  
또한 시스템 정보에서 장치에 대한 시스템 SKU 및 시스템 모델을 **찾을 수 있습니다.** 이렇게 하려면 다음 단계를 따르세요.

1. **시작을**선택한 다음 검색 상자에 **MSInfo32를** 입력합니다.  
1. 시스템 **정보를 선택합니다.**

**작업 순서 WMI 조건에서 SKU 사용**  
MDT(Microsoft Deployment Toolkit) 또는 Microsoft Endpoint Configuration Manager의 시스템 SKU 정보를 작업 순서 WMI 조건의 일부로 사용할 수 있습니다.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

## 자세히 알아보기

- [WMI 참조](https://docs.microsoft.com/windows/win32/wmisdk/wmi-reference)
- [Windows Autopilot용 Surface 등록 지원](surface-autopilot-registration-support.md)
