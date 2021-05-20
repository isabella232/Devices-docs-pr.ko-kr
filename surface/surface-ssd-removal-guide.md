---
title: 호환되는 Surface 디바이스에서 SSD 제거
description: 자격을 갖춘 IT 기술자를 위한 이 문서에서는 Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X 및 Surface Laptop Go에서 SDSD 제거 및 교체에 권장되는 모범 사례에 대해 설명하고 있습니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576908"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>호환되는 Surface 디바이스에서 SSD 제거 모범 사례

> [!IMPORTANT]
> 이 문서는 엔터프라이즈 조직의 적격 IT 기술자가 사용하기 위한 것입니다. 다음 호환되는 Surface 디바이스에서 SSD를 제거하고 교체할 때 적격 IT 기술자가 사용하기 위한 권장 모범 사례에 대해 설명하고 있습니다. 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop 이동
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> 장치를 열고 장치 구성 요소를 교체하면 감전, 장치 손상, 화재 및 개인 상해 위험 및 기타 위험을 초래할 수 있습니다.  이러한 활동을 진행할 때는 항상 주의해야 합니다. 에 대한 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에서 식별된 안전 예방 Enterprise. "rSSD 제거 가이드 for Enterprise"에 지정된 안전 예방조치 및 절차를 따를 수 없는 경우 전문 지원을 받을 것을 Enterprise.

## <a name="prerequisites"></a>필수 구성 요소

> [!IMPORTANT]
> 이 문서에서는 "rSSD 제거 가이드 for Enterprise"에 설명된 일반 안전 주의 및 안전 정책 및 절차를 이해하고 있는 것으로 가정합니다.

## <a name="prepare-for-ssd-removal"></a>SSD 제거 준비 

### <a name="install-the-latest-updates"></a>최신 업데이트 설치 

시작하기 전에 버전에 최신 Windows 설치해야 합니다.

1.  시작 **설정**보안 & 로 이동하고 업데이트  >  ****  >  **** **확인을 선택합니다.**
2. 사용 가능한 모든 업데이트를 설치합니다.
3. 장치에 액세스하는 데 필요한 암호를 확인합니다.  
 
## <a name="manage-bitlocker"></a>BitLocker 관리 

> [!NOTE]
> 이 섹션에는 하드 디스크에 대한 암호화를 사용하도록 BitLocker 조직에 대한 권장 사항이 포함되어 있습니다. 자세한 내용은 BitLocker [복구 가이드를 참조하세요.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>SSD BitLocker 교체 중에 암호화를 사용하지 않도록 설정한 경우

SSD를 제거하고 교체하기 전에 디바이스를 암호화 해제할 수 있는 경우 다음 단계에 따라 장치를 BitLocker.

1.  에서 **설정**를 **입력하고 BitLocker** 를 입력한 다음 관리 **BitLocker.** 
2.  에서 **끄기 를 BitLocker.** 
3.  디바이스 전원을 니다. 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>SSD를 BitLocker 교체하는 동안 암호화를 사용할 수 있는 경우

SSD 제거 및 교체 전에 장치가 암호화된 경우 다음 단계에 따라 BitLocker 복구 키를 생성하고 USB 저장소에 저장합니다.

1.  에서 **설정**를 **BitLocker.**
2. Manage **BitLocker**  > **Generate BitLocker Recovery Key 를 선택합니다.**
2.  USB 드라이브를 삽입합니다. 
4.  복구 키를 USB 저장소에 저장합니다.  
5.  USB 드라이브를 제거합니다.  
6.  디바이스 전원을 니다. 

## <a name="remove-and-replace-ssd"></a>SSD 제거 및 바꾸기 

1.  에 대한 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에 포함된 장치에 적절한 지침을 사용하여 SSD를 Enterprise. 
2.  원래 SSD를 새 장치에 추가하고 새 장치를 유선 인터넷 연결에 연결합니다.
3.  새 디바이스에서 전원을 니다. 디바이스가 시작 중에 펌웨어 업데이트를 거치게 될 수 있습니다.  
 
## <a name="after-ssd-removal-and-replacement"></a>SSD 제거 및 교체 후

### <a name="manage-unencrypted-ssds"></a>암호화되지 않은 SDS 관리 

전송 중에 SSD가 암호화되지 않은 경우 다음 단계를 수행합니다. 

1.  로그인 **옵션**암호(왼쪽의 키 아이콘으로  >  **** 표시)로 이동하세요.  
2.  암호를 입력하고 2단계 인증 완료 보류 중으로 로그인합니다(해당하는 경우).
3.  완전히 로그인한 후 계정 시작 ****  >  ****  >  **로그인으로 이동하세요.**  
4.  메시지가 표시될 때 암호를 사용하여 Windows Hello 및 PIN을 설정하여 다시 로그인합니다. 
    - SSD 제거 및 교체를 BitLocker 위해 장치가 사용되지 않도록 설정되어 있으며 교체 후 BitLocker 사용하려면 **** manage  >  **BitLocker Manage BitLocker**Resume BitLocker  >  **.**  
6.  Microsoft [Surface Diagnostic Toolkit(비즈니스용](surface-diagnostic-toolkit-for-business-intro.md) SDT)를 실행하여 전체 장치 기능을 확인합니다.  
7.  정품 인증으로 Windows 정품 **인증을**설정  >  **확인합니다.**  오류 메시지가 표시되어 있는 경우 문제 해결 을 **선택합니다.** 
8.  Office 앱 을 열고 **** Office 계정으로 이동한 **** 다음 오류 메시지를  >  **** 검사합니다.  

### <a name="managing-encrypted-ssds"></a>암호화된 SDS 관리 

> [!NOTE]
> USB 드라이브에 저장된 복구 BitLocker 읽기 위해 두 번째 장치가 필요합니다. 

전송 중에 SSD가 암호화된 경우 다음 단계를 수행합니다.

1.  두 번째 장치에 BitLocker 복구 키가 포함된 USB 드라이브를 삽입합니다. 
2.  Bitlocker .txt 포함된 파일 파일을 열 수 있습니다. 
3.  원래 SSD가 BitLocker 디바이스에서 복구 키를 수동으로 입력합니다.  
4.  BitLocker 복구 키를 성공적으로 입력한 후 로그인 옵션 **** 암호(왼쪽의 키 아이콘으로 표시)로  >  **** 이동하세요.  
5.  암호를 입력하고 로그인하고 2단계 인증 완료를 보류하고 있습니다(해당하는 경우).
6.  완전히 로그인한 후 계정 시작 ****  >  ****  >  **로그인으로 이동하세요.**  
7.  암호를 사용하여 다시 로그인한 다음 Hello를 Windows PIN을 추가합니다. 
8.  SSD 제거 및 BitLocker 쉽게 사용할 수 있도록 장치를 사용하지 않도록 설정한 경우 교체 후 BitLocker 사용하려면 설정 ****  >  **BitLocker**  >  **Manage BitLocker**Resume BitLocker  >  **.**  
9.  **[SDT를 실행하여](surface-diagnostic-toolkit-for-business-intro.md)** 전체 장치 기능을 확인합니다.  
10. 정품 인증을 Windows **활성화를 설정**  >  **선택합니다.**  오류 메시지가 표시되어 있는 경우 문제 해결 을 **선택합니다.**
11. Office 계정의 상태를 확인하려면 Office 앱 을 열고 파일 **** **계정으로**이동하여 오류 메시지를  >  **** 검사합니다.

## <a name="learn-more"></a>자세히 알아보기

- [rSSD Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker 복구 가이드](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

그래도 문제가 해결되지 않을 경우 [으로 이동하여 Microsoft Community.](https://answers.microsoft.com/)