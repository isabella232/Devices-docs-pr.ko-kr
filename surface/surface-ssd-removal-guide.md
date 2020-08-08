---
title: 호환 가능한 Surface 장치에서 SSD 제거
description: 한 Surface 장치에서 다른 대상으로 SSD를 전송 하는 방법을 설명 합니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918959"
---
# 호환 되는 표면 장치에서 SSD 제거에 대 한 모범 사례

> [!IMPORTANT]
> 이 문서는 엔터프라이즈 조직의 정식 IT 기술자만 사용 하기 위한 것입니다. 이는 Surface 장치에서 SSDs를 제거 하 고 교체할 때 정식 IT 기술자에 게 권장 되는 모범 사례를 설명 합니다 (이동식 SSDs 사용). 

> [!WARNING]
> 장치 열기 및 장치 구성 요소 교체는 감전, 장치 손상, 화재, 개인 부상이 위험 및 기타 위험성을 제공할 수 있습니다.  이러한 활동을 할 때는 항상 주의를 기울여야 합니다. 엔터프라이즈에 대 한 rSSD 제거 가이드에 명시 된 안전한 예방 조치 및 절차를 따릅니다. 엔터프라이즈에 대 한 rSSD 제거 가이드에 명시 된 안전 주의 사항 및 절차를 따를 수 없는 경우에는 전문가 지원을 검색 하는 것이 좋습니다. 

## 필수 구성 요소

> [!IMPORTANT]
> 이 문서에서는 [엔터프라이즈의 Rssd 제거 가이드](https://www.microsoft.com/download/100440)에 설명 된 일반 안전 주의 사항 및 안전 정책 및 절차를 이해 하 고 있는 것으로 가정 합니다.

## SSD 제거 준비 

### 최신 업데이트 설치 

시작 하기 전에 Windows 버전에 최신 업데이트가 있는지 확인 합니다.

1.  **시작**  >  **설정**  >  **업데이트 & 보안** 으로 이동 하 고 **업데이트 확인**을 선택 합니다. 사용 가능한 모든 업데이트를 설치 합니다.  

2.  장치에 액세스 하는 데 필요한 암호가 있는지 확인 합니다.  
 
## Bitlocker 관리 

> [!NOTE]
> 이 섹션에는 하드 드라이브에 대해 BitLocker 암호화를 사용 하도록 설정한 조직에 대 한 권장 사항이 포함 되어 있습니다. 자세한 내용은 [BitLocker 복구 가이드](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)를 참조 하세요. 

### SSD 제거 및 바꾸기 중에 BitLocker 암호화를 사용 하지 않도록 설정

SSD 제거 및 바꾸기 전에 장치를 암호화 하지 않으면 다음 단계에 따라 BitLocker를 해제 합니다.

1.  **설정**에서 **bitlocker** 를 입력 하 고 **bitlocker 관리**를 선택 합니다. 
2.  **Bitlocker 해제**를 선택 합니다. 
3.  장치 전원을 차단 합니다. 

### SSD 제거 및 교체 중에 BitLocker 암호화가 사용 하도록 설정 된 경우

장치를 SSD 제거 및 바꾸기 전에 암호화 된 경우 다음 단계에 따라 BitLocker 복구 키를 생성 하 고 USB 저장소에 저장 합니다.

1.  **설정** 으로 이동 하 여 **Bitlocker**를 입력 합니다.
2. **Bitlocker**  > **생성 bitlocker 복구 키**관리를 선택 합니다.
2.  USB 드라이브를 삽입 합니다. 
3.  복구 키를 USB 저장소에 저장 합니다.  
4.  USB 드라이브를 제거 합니다.  
5.  장치 전원을 차단 합니다. 

## SSD 제거 및 바꾸기 

1.  [엔터프라이즈에 대 한 Rssd 제거 가이드](https://www.microsoft.com/download/100440)의 지침에 따라 SSD를 제거 합니다. 
2. 원본 SSD를 새 장치에 배치 하 고 새 장치를 유선 인터넷 연결에 연결 합니다.
2.  새 장치를 켭니다. 장치는 시작 하는 동안 펌웨어 업데이트를 거쳐야 할 수 있습니다.  
 
## SSD 제거 및 바꾸기 이후

### 암호화 되지 않은 SSDs 관리 

전송 하는 동안 SSD를 암호화 되지 않은 상태로 유지 하려면 다음을 수행 합니다. 

1.  **Sign-In Options**  >  왼쪽의 키 아이콘으로 표시 되는 로그인 옵션**암호로** 이동 합니다.  
2.  비밀 번호를 입력 하 고 해당 하는 경우 2 단계 인증 완료 대기 중에 로그인 합니다 (해당 하는 경우).
3.  완전히 로그인 한 후에는 **Start**  >  **계정**  >  **로그**시작으로 이동 합니다.  
4.  암호를 사용 하 여 다시 로그인 하 고 메시지가 표시 되 면 Windows Hello 및 PIN을 설정 합니다. 
    - 장치에서 SSD 제거 및 교체를 용이 하 게 하기 위해 bitlocker를 사용 하지 않도록 설정 된 경우, 교체 후 bitlocker를 사용 하도록 설정 **하려면 bitlocker**  >  **bitlocker**  >  **다시 시작**bitlocker 관리를 참조 하세요.  
6.  **Sdt** 를 실행 하 여 전체 장치 기능을 확인 합니다.  
7.  **설정**활성화로 이동 하 여 Windows 정품 인증을 확인  >  **Activation**합니다.  오류 메시지가 나타나면 **문제 해결**을 선택 합니다. 
8.  **Office 앱**을 열고 **파일**계정으로 이동한 다음 오류 메시지를 확인 하 여 office 계정을 확인  >  **Account** 합니다.  

### 암호화 된 SSDs 관리 

> [!NOTE]
> USB 드라이브에 저장 된 BitLocker 복구 키를 읽으려면 두 번째 장치가 필요 합니다. 

전송 하는 동안 SSD를 암호화 된 상태로 유지 하는 경우 다음을 수행 합니다.

1.  Bitlocker 복구 키가 포함 된 USB 드라이브를 두 번째 장치에 삽입 합니다. 
2.  Bitlocker 복구 키를 포함 하는 .txt 파일을 엽니다. 
3.  Bitlocker 복구 키를 원래 SSD를 포함 하는 새 장치에 수동으로 입력 합니다.  
4.  BitLocker 복구 키를 입력 한 후 **Sign-In Options**  >  왼쪽에 있는 열쇠 아이콘으로 표시 되는 로그인 옵션**암호로** 이동 합니다.  
5.  비밀 번호 입력 및 로그인, 2 단계 인증 완료 보류 중 (해당 하는 경우) 
6.  완전히 로그인 한 후에는 **Start**  >  **계정**  >  **로그**시작으로 이동 합니다.  
7.  암호를 사용 하 여 다시 로그인 하 고 Windows Hello를 설정 하 고 PIN을 추가 합니다. 
8.  장치가 SSD 제거 및 교체를 용이 하 게 하기 위해 bitlocker를 사용 하지 않도록 설정 되어 있는 경우, 교환 후 bitlocker를 사용 하도록 **설정**하려면 bitlocker로 bitlocker  >  **Bitlocker**  >  **Manage Bitlocker**  >  **다시 시작**bitlocker를 관리 하세요 .를 선택 합니다.  
9.  **Sdt** 를 실행 하 여 전체 장치 기능을 확인 합니다.  
10. **설정**활성화로 이동 하 여 Windows 정품 인증을 확인  >  **Activation**합니다.  오류 메시지가 나타나면 **문제 해결**을 선택 합니다.
11. Office 계정을 확인 하려면 **office 앱**을 연 다음 **파일**계정으로 이동 하 여  >  **Account** 오류 메시지를 확인 합니다.

## 추가 정보 

자세한 내용은 다음 문서를 참조하세요.

- [엔터프라이즈 용 rSSD 제거 가이드](https://www.microsoft.com/download/100440)
- [BitLocker 복구 가이드](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

그래도 문제가 해결되지 않을 경우 [Microsoft 커뮤니티](https://answers.microsoft.com/)를 참조 하세요.