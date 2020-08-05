---
title: 시스템 SKU 참조 (Surface)
description: 시스템 모델 및 시스템 SKU 이름에 대 한 참조를 참조 하세요.
keywords: uefi, 구성, 펌웨어, 보안, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/04/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 3eb177e976bd99ec245996db8cb22eab639f63cc
ms.sourcegitcommit: c0676329f894135388b6d52f85ee8ac9507a836e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905675"
---
# 시스템 SKU 참조

이 문서는 PowerShell 또는 WMI를 사용 하 여 특정 장치의 컴퓨터 상태를 빠르게 확인 하는 데 사용할 수 있는 시스템 모델 및 시스템 SKU 이름에 대 한 참조를 제공 합니다.

시스템 모델 및 시스템 SKU는 Surface 디바이스의 UEFI 계층에 있는 SMBIOS (시스템 관리 BIOS) 표에 저장 된 변수입니다. System SKU 이름을 사용 하 여 Surface Pro 및 Surface Pro와 같은 시스템 모델 이름 (예: LTE Advanced를 사용 하는 장치)을 구분 해야 할 경우

| 장치   | 시스템 모델 | 시스템 SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| &T의 Surface 3 LTE                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE 북아메리카                                  | Surface 3        | Surface_3_NAG                    |
| 표면 3 LTE 북미 및 Y 외부: 일본의 모바일 | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13 "                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15 "                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE 상업용 | 시스템 이동 | Surface_Go_1825_Commercial |
| Surface Go 소비자                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go 상업용                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 소비자                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 상업용                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| surface 노트북                                               | surface 노트북   | Surface_Laptop                   |
| Surface 노트북 2 소비자                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface 노트북 2 상업용                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface 랩탑을 3 13 "Intel | Surface 노트북 3 | Surface_Laptop_3_1867:1868 |
| Surface 랩탑을 3 15 "Intel | Surface 노트북 3 | Surface_Laptop_3_1872      |
| Surface 랩탑 3 15 "AMD   | Surface 노트북 3 | Surface_Laptop_3_1873      | 

## 예 

**PowerShell을 사용 하 여 SKU 검색**  
다음 PowerShell 명령을 사용 하 여 시스템 SKU 정보를 가져옵니다.

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**시스템 정보를 사용 하 여 SKU 검색**  
**시스템 정보**에서 장치에 대 한 시스템 SKU 및 시스템 모델을 찾을 수도 있습니다. 이렇게 하려면 다음 단계를 따르세요.

1. **시작**을 선택 하 고 검색 상자에 **MSInfo32** 를 입력 합니다.  
1. **시스템 정보**를 선택 합니다.

**작업 순서 WMI 조건에서 SKU 사용**  
작업 순서 WMI 조건의 일부로 MDT (Microsoft Deployment Toolkit) 또는 Microsoft Endpoint Configuration Manager의 시스템 SKU 정보를 사용할 수 있습니다.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
