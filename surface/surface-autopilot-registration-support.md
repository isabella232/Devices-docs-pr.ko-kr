---
title: Windows Autopilot에 대 한 Surface Registration 지원
description: 이 문서에서는 Microsoft 지원에 Autopilot 등록 요청을 제출 하기 위한 요구 사항을 설명 합니다.
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
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016482"
---
# Windows Autopilot에 대 한 Surface Registration 지원

이제 Microsoft 지원에서 Windows Autopilot 배포에 대 한 Surface 디바이스를 등록 하는 간단한 프로세스가 제공 됩니다. 2020 년 9 월부터 고객 및 Microsoft Csp (클라우드 솔루션 공급자)는 Microsoft 지원에 요청을 제출 하 여 Surface 디바이스를 등록할 수 있습니다. 이 페이지에서는 다음과 같이 지원 되는 Autopilot 등록 시나리오에 대 한 요구 사항을 간략하게 설명 합니다.
 

- **Surface Device Autopilot 등록**. Surface 디바이스 등록 요청을 Windows Autopilot에 제출 합니다.
- **Surface 디바이스 하드웨어 해시 요청입니다.** 고객 또는 Csp가 Microsoft Intune 또는 Microsoft 파트너 센터를 통해 자체 등록 디바이스에 사용할 수 있는 하드웨어 해시를 제공 하기 위해 Microsoft Support에 요청을 제출 합니다.
- **Surface 디바이스 Autopilot 등록 취소.** Windows Autopilot에서 장치 삭제 요청을 제출 합니다. 일반적으로 장치 종료 시나리오에서 사용 됩니다.

Microsoft 지원에 등록 요청을 제출 하기 전에 수집 해야 하는 정보에 대 한 자세한 내용은 다음 표를 참조 하세요.
 
**표 1. Autopilot 등록 요청에 필요한 정보**
 

| 필수 정보                   | 설명                                                                                                                                                                                                                                                                                    | Autopilot 등록 | 하드웨어 해시 요청 | Autopilot<br>취소 |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory 테 넌 트 ID**   | Azure Active Directory 테 넌 트 ID가 조직 이름 또는 도메인과는 다른 전역 고유 식별자 (GUID)입니다.<br> <br>테 넌 트 ID를 찾으려면 [여기](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)에서 Azure 포털에 로그인 합니다. | 예                      | N                     | 예                           |
| **Azure Active Directory 도메인 이름** | 최상위 수준의 도메인 이름 예를 contoso.com.                                                                                                                                                                                                                                          | 예                      | N                     | 예                           |
| **소유권 증명**                 | 원본 판매 증서 또는 송장을 PDF 형식으로 업로드 하 여 소유권 증명을 확인 합니다. 스크린샷이 허용 되지 않습니다.<br> <br>할인 증서 또는 송장에는 다음이 포함 되어야 합니다.<br>장치 일련 번호.<br>회사 이름입니다.                                                           | 예                      | Y                     | 예                           |
| **장치 일련 번호**              | 각 장치 일련 번호를 새 줄에 포함 하 여 CSV 형식으로 Excel 파일을 업로드 합니다.                                                                                                                                                                                                                  | 예                      | Y                     | 예                           |

 

## 지원 요청 제출

  [![Get Autopilot 등록 지원 화면](images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## 자세히 알아보기

- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md)
- [Windows Autopilot을 사용하여 Intune에 Windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 개요](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

