---
title: Windows Autopilot용 Surface 등록 지원
description: 이 문서에서는 Autopilot 등록 요청을 Microsoft 지원에 제출하기 위한 요구 사항에 대해 설명하고 있습니다.
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 77881fae189af1ad3773f5fad192a28746e2d983
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449421"
---
# <a name="surface-registration-support-for-windows-autopilot"></a>Windows Autopilot용 Surface 등록 지원

이제 Microsoft 지원에서 Autopilot 배포를 위해 Surface Windows 등록하는 간소화된 프로세스를 사용할 수 있습니다. 2020년 9월부터 고객과 Microsoft CSP(클라우드 솔루션 공급자)는 Microsoft 지원에 요청을 제출하여 Surface 디바이스를 등록할 수 있습니다. 이 페이지에서는 지원되는 다음과 같은 Autopilot 등록 시나리오에 대한 요구 사항을 간략하게 설명합니다.
 
- **Surface 디바이스 Autopilot Registration**. Surface 디바이스를 Autopilot에 등록하기 위한 Windows 제출합니다.
- **Surface 디바이스 하드웨어 해시 요청.** 고객 또는 CSP가 사용자 또는 Microsoft 파트너 센터를 통해 장치를 자체 등록하는 데 사용할 수 있는 하드웨어 해시를 제공하기 위해 Microsoft Microsoft Intune 제출합니다.
- **Surface 디바이스 Autopilot Deregistration.** 디바이스 종료 시나리오에서 일반적으로 Windows Autopilot에서 장치를 삭제하기 위한 요청을 제출합니다.

Microsoft 지원에 등록 요청을 제출하기 전에 수집해야 하는 정보에 대한 자세한 내용은 다음 표를 참조하세요. 모든 Surface 디바이스의 공식 시스템 모델 이름에 대한 자세한 내용은 [Surface System SKU 참조를 참조합니다](surface-system-sku-reference.md).
 
**표 1. Autopilot 등록 요청에 필요한 정보**
 

| 필수 정보                   | 설명                                                                                                                                                                                                                                                                                    | Autopilot 등록 | 하드웨어 해시 요청 | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory 테넌트 ID**   | Azure Active Directory 테넌트 ID는 조직 이름 또는 도메인과 다른 GUID(Globally Unique Identifier)입니다.<br> <br>테넌트 ID를 찾으면 여기에서 Azure Portal에 로그인 [합니다](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | Y                      | N                     | Y                           |
| **Azure Active Directory 도메인 이름** | 최상위 도메인 이름 예를 들어 contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **소유권 증명**                 | 원래 판매 청구서 또는 송장을 PDF 형식으로 업로드하여 소유권 증명을 검증합니다. 스크린샷은 수락되지 않습니다.<br> <br>판매 청구서 또는 송장에는 다음이 포함되어야 합니다.<br>디바이스 일련 번호입니다.<br>회사 이름입니다.                                                           | Y                      | Y                     | Y                           |
| **장치 일련 번호**              | 업로드 Excel 줄에 각 장치 일련 번호를 사용하여 CSV 형식으로 파일을 저장합니다.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## <a name="submit-support-requests"></a>지원 요청 제출

  [![Get Surface에 대한 Autopilot 등록 지원입니다.](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <a name="learn-more"></a>세부 정보

- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md)
- [Windows Autopilot을 사용하여 Intune에 Windows 장치 등록](/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 개요](/mem/autopilot/windows-autopilot)
- [Surface 시스템 SKU 참조](surface-system-sku-reference.md)

 
 
 

