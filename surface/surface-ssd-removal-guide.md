---
title: 호환되는 Surface 디바이스에서 SSD 제거
description: 적격 IT 기술자를 위한 이 문서에서는 Surface Laptop 3, Surface Pro X 및 Surface Laptop Go에서 SSD를 제거하고 교체하는 데 권장되는 모범 사례에 대해 설명하고 있습니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270633"
---
# 호환되는 Surface 디바이스에서 SSD 제거 모범 사례

> [!IMPORTANT]
> 이 문서는 엔터프라이즈 조직의 적격 IT 기술자만 사용하기 위한 것입니다. 다음 호환되는 Surface 디바이스에서 SSD를 제거하고 교체할 때 적격 IT 기술자가 사용할 수 있는 권장 모범 사례에 대해 설명하고 있습니다. 

- Surface Pro 7+
- Surface Pro X
- Surface 노트북 이동
- Surface 노트북 3

> [!WARNING]
> 장치를 열고 장치 구성 요소를 교체하면 감전, 장치 손상, 화재 및 개인 상해 위험 및 기타 위험을 초래할 수 있습니다.  이러한 활동을 진행할 때는 항상 주의해야 합니다. 엔터프라이즈용 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에 식별된 안전 예방조치 및 절차를 따르세요. "엔터프라이즈용 rSSD 제거 가이드"에 지정된 안전 예방조치 및 절차를 따를 수 없는 경우 전문 지원을 받을 것을 권장합니다.

## 필수 구성 요소

> [!IMPORTANT]
> 이 문서에서는 "엔터프라이즈용 rSSD 제거 가이드"에 설명된 일반 안전 예방조치 및 안전 정책 및 절차를 이해하고 있는 것으로 가정합니다.

## SSD 제거 준비 

### 최신 업데이트 설치 

시작하기 전에 Windows 버전에 최신 업데이트가 설치되어 있는지 확인합니다.

1.  Go to **Start**  >  **Settings**  >  **Update & Security,** and select **Check for updates.**
2. 사용 가능한 모든 업데이트를 설치합니다.
3. 장치에 액세스하는 데 필요한 암호를 확인합니다.  
 
## BitLocker 관리 

> [!NOTE]
> 이 섹션에는 하드 디스크에 대해 BitLocker 암호화를 사용하도록 설정한 조직에 대한 권장 사항이 포함되어 있습니다. 자세한 내용은 [BitLocker 복구 가이드를 참조하세요.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### SSD 제거 및 교체 중에 BitLocker 암호화를 사용하지 않도록 설정한 경우

SSD 제거 및 교체 전에 디바이스를 암호화 해제할 수 있는 경우 다음 단계에 따라 BitLocker를 끄세요.

1.  **설정에서** **BitLocker를 입력한** 다음 **BitLocker 관리를 선택합니다.** 
2.  **BitLocker 끄기를 선택합니다.** 
3.  디바이스 전원을 니다. 

### SSD 제거 및 교체 중에 BitLocker 암호화를 사용하도록 설정한 경우

SSD 제거 및 교체 전에 장치가 암호화된 경우 다음 단계에 따라 BitLocker 복구 키를 생성하고 USB 저장소에 저장합니다.

1.  **설정에서** **BitLocker를 입력합니다.**
2. Select **Manage BitLocker**  > **Generate BitLocker Recovery Key.**
2.  USB 드라이브를 삽입합니다. 
4.  복구 키를 USB 저장소에 저장합니다.  
5.  USB 드라이브를 제거합니다.  
6.  디바이스 전원을 니다. 

## SSD 제거 및 바꾸기 

1.  엔터프라이즈용 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에 포함된 장치에 대한 적절한 지침을 사용하여 SSD를 제거합니다. 
2.  원래 SSD를 새 장치에 저장하고 새 장치를 유선 인터넷 연결에 연결합니다.
3.  새 디바이스에서 전원을 니다. 디바이스가 시작 중에 펌웨어 업데이트를 거치게 될 수 있습니다.  
 
## SSD 제거 및 교체 후

### 암호화되지 않은 SDD 관리 

전송 중에 SSD가 암호화되지 않은 경우 다음 단계를 수행합니다. 

1.  Go to **Sign-In Options**  >  **Password** (represented by the key icon on the left side.  
2.  암호를 입력하고 2단계 인증 완료 대기(해당하는 경우)에 로그인합니다.
3.  완전히 로그인한 후 계정 로그인 ****  >  ****  >  **시작으로 이동하세요.**  
4.  암호를 사용하여 다시 로그인하고 메시지가 표시될 때 Windows Hello 및 PIN을 설정하세요. 
    - 장치가 SSD 제거 및 교체를 용이하게 하기 위해 BitLocker를 사용하지 않도록 설정한 경우 대체 후 BitLocker를 사용하도록 설정하려면 **BitLocker**  >  **관리 BitLocker**다시 시작  >  **BitLocker로 이동하십시오.**  
6.  Microsoft [Surface Diagnostic](surface-diagnostic-toolkit-for-business-intro.md) Toolkit(비즈니스용 SDT)를 실행하여 전체 장치 기능을 확인합니다.  
7.  설정 정품 인증으로 이동하여 Windows 정품 **인증을**  >  **확인합니다.**  오류 메시지가 표시되어 있는 경우 문제 해결을 **선택합니다.** 
8.  Office 앱을 열고 **파일**계정으로 **** 이동한 다음 오류 메시지를 확인하여 Office  >  **** 계정을 검사합니다.  

### 암호화된 SDD 관리 

> [!NOTE]
> USB 드라이브에 저장된 BitLocker 복구 키를 읽으기 위해 두 번째 장치가 필요합니다. 

SSD가 전송 중에 암호화된 경우 다음 단계를 수행합니다.

1.  BitLocker 복구 키가 포함된 USB 드라이브를 두 번째 장치에 삽입합니다. 
2.  Bitlocker 복구 키가 포함된 .txt 파일을 씁니다. 
3.  원래 SSD가 포함된 새 디바이스에서 BitLocker 복구 키를 수동으로 입력합니다.  
4.  BitLocker 복구 키를 성공적으로 입력한 후 로그인 **** 옵션 암호(왼쪽의 키 아이콘으로  >  **** 표시)로 이동하십시오.  
5.  암호를 입력하고 로그인하고 2단계 인증 완료를 보류 중입니다(해당하는 경우).
6.  완전히 로그인한 후 계정 로그인 ****  >  ****  >  **시작으로 이동하세요.**  
7.  암호를 사용하여 다시 로그인한 다음 Windows Hello를 설정하고 PIN을 추가합니다. 
8.  장치가 SSD 제거 및 교체를 용이하게 하기 위해 BitLocker를 사용하지 않도록 설정한 경우, **** 교체 후 BitLocker를 사용하도록 설정하려면  >  **BitLocker**관리  >  **BitLocker**다시 시작  >  **BitLocker로**이동합니다.  
9.  **[SDT를 실행하여](surface-diagnostic-toolkit-for-business-intro.md)** 전체 장치 기능을 확인합니다.  
10. Windows 정품 인증을 확인하려면 설정 **활성화를**  >  **선택합니다.**  오류 메시지가 표시되어 있는 경우 문제 해결을 **선택합니다.**
11. Office 계정의 상태를 확인하려면 **Office 앱을**연 다음 **** 파일 계정으로 이동하여 오류 메시지를  >  **** 검사합니다.

## 자세히 알아보기

- [엔터프라이즈용 rSSD 제거 가이드](https://www.microsoft.com/download/100440)
- [BitLocker 복구 가이드](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

그래도 문제가 해결되지 않을 경우 Microsoft [커뮤니티로 이동](https://answers.microsoft.com/)