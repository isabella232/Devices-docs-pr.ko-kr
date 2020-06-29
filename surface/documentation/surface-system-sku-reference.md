---
title: Surface 시스템 SKU 참조
description: 이 항목에서는 특정 장치의 컴퓨터 상태를 빠르게 확인 하는 데 사용할 수 있는 시스템 SKU 이름에 대 한 참조를 제공 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835103"
---
# Surface System SKU 참조
이 문서는 PowerShell, WMI 및 관련 도구를 사용 하 여 특정 장치의 컴퓨터 상태를 빠르게 확인 하는 데 사용할 수 있는 시스템 SKU 이름에 대 한 참조를 제공 합니다. 

System SKU는 Surface 디바이스의 UEFI 계층에 있는 SMBIOS (시스템 관리 BIOS) 표에 저장 된 변수 (시스템 모델 및 기타)입니다.  System SKU 이름을 사용 하 여 Surface Pro 및 Surface Pro와 같은 시스템 모델 이름 (예: LTE Advanced를 사용 하는 장치)을 구분 해야 할 경우 

| **장치**| **시스템 모델** | **시스템 SKU**|
| --- | ---| --- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| &T의 Surface 3 LTE                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE 북아메리카                                  | Surface 3        | Surface_3_NAG                    |
| 북미 외부의 Surface 3 LTE 및 일본의 T-모바일 | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro LTE Advanced                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13inch                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15inch                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Go 소비자                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go 상업용                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 소비자                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 상업용                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface 노트북 2 소비자                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface 노트북 2 상업용                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## 시스템 SKU 변수 사용 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### 시스템 정보
시스템 정보에서 장치에 대 한 시스템 SKU 및 시스템 모델을 찾을 수도 있습니다. 
- MSInfo32 **시작**  >   **MSInfo32**을 클릭 합니다.  

### WMI
Microsoft 배포 도구 키트 (MDT) 또는 Microsoft 끝점 구성 관리자에서 작업 순서 WMI 조건에 시스템 SKU 변수를 사용할 수 있습니다. 예: 

    - WMI 네임 스페이스 – Root\WMI
    - WQL Query – SystemSKU = "Surface_Pro_1796" 인 MS_SystemInformation를 선택 합니다.

 
 
 


