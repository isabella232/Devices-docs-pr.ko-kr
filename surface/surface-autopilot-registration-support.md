---
title: Windows Autopilot용 Surface 등록 지원
description: 이 문서에서는 Autopilot 등록 요청을 Microsoft 지원에 제출하기 위한 요구 사항에 대해 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: b31cacad5a744dcb29fc3dd2822c656d528fcd40
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304841"
---
# Windows Autopilot용 Surface 등록 지원

이제 Microsoft 지원에서 Windows Autopilot 배포를 위해 Surface 디바이스를 등록하는 간소화된 프로세스를 사용할 수 있습니다. 2020년 9월부터 고객 및 Microsoft CSP(클라우드 솔루션 공급자)는 Microsoft 지원에 요청을 제출하여 Surface 디바이스를 등록할 수 있습니다. 이 페이지에서는 지원되는 다음과 같은 Autopilot 등록 시나리오에 대한 요구 사항을 간략하게 설명합니다.
 
- **Surface Device Autopilot Registration**. Surface 디바이스를 Windows Autopilot에 등록하기 위해 요청을 제출합니다.
- **Surface 디바이스 하드웨어 해시 요청입니다.** 고객 또는 CSP가 Microsoft Intune 또는 Microsoft 파트너 센터를 통해 디바이스를 자체 등록하는 데 사용할 수 있는 하드웨어 해시를 제공하기 위해 Microsoft 지원에 요청을 제출합니다.
- **Surface Device Autopilot Deregistration.** Windows Autopilot에서 장치 삭제 요청을 제출합니다. 일반적으로 장치 수명 종료 시나리오에 사용됩니다.

Microsoft 지원에 등록 요청을 제출하기 전에 수집해야 하는 정보에 대한 자세한 내용은 다음 표를 참조하세요. 모든 Surface 디바이스의 공식 시스템 모델 이름은 [Surface System SKU 참조를 참조합니다.](surface-system-sku-reference.md)
 
**표 1. Autopilot 등록 요청에 필요한 정보**
 

| 필수 정보                   | 설명                                                                                                                                                                                                                                                                                    | Autopilot Registration | 하드웨어 해시 요청 | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory 테넌트 ID**   | Azure Active Directory 테넌트 ID는 조직 이름 또는 도메인과 다른 GUID(Globally Unique Identifier)입니다.<br> <br>Azure Portal에 테넌트 ID 로그인을 [찾으세요.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Azure Active Directory 도메인 이름** | 최상위 도메인 이름 예를 들어 contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **소유권 증명**                 | 원래 판매 청구서 또는 송장을 PDF 형식으로 업로드하여 소유권 증명을 검증합니다. 스크린샷은 수락되지 않습니다.<br> <br>판매 청구서 또는 송장에는 다음이 포함되어야 합니다.<br>디바이스 일련 번호입니다.<br>회사 이름입니다.                                                           | Y                      | Y                     | Y                           |
| **디바이스 일련 번호**              | 각 장치 일련 번호가 새 줄에 있는 CSV 형식으로 Excel 파일을 업로드합니다.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## 지원 요청 제출

  [![Get Autopilot Registration Support for Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## 자세히 알아보기

- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md)
- [Windows Autopilot을 사용하여 Intune에 Windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 개요](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [Surface 시스템 SKU 참조](surface-system-sku-reference.md)

 
 
 

