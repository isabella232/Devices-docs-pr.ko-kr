---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: 이 문서에서는 Surface Hub 2의 Windows 10 Team에서 Windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 과정을 설명 합니다.
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/09/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 5431cb9c11fbcfadf0ef517164521c237fb6b3bb
ms.sourcegitcommit: 75940bb1ab4e08c96736923859c7dd673dcf8d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009626"
---
# Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션

## 소개

Surface Hub 2S는 회의실 환경에서 쉽게 공동 작업을 할 수 있도록 디자인 된 windows 10 팀 (windows 10의 사용자 지정 버전)을 사용 하 여 사전 설치 되어 제공 됩니다. 이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용 하기 위해 Windows 10 Pro 또는 Enterprise를 실행 하는 옵션이 있습니다. 

> [!IMPORTANT]
>일반 업그레이드 또는 마이그레이션과 달리이 프로세스는이 페이지에 설명 된 대로 규범적 절차를 따라야 합니다. 계속 하기 전에 [솔루션 구성 요소](#solution-components) 및 [마이그레이션 워크플로](#migration-workflow-summary) 를 검토 합니다.

별도의 PC 및 다운로드 가능한 도구-- **SURFACE UEFI 구성자** 를 사용 하 여 Windows 10 팀에서 마이그레이션을 시작 하 고 Surface Hub 2S에 적용 하는 새 UEFI 설정을 포함 하는 패키지를 만듭니다.  Surface UEFI Configurator는 엔터프라이즈 환경에서 Surface 장치에 대 한 펌웨어 설정을 중앙에서 관리할 수 있도록 디자인 된 Surface X관리 모드 (SEMM)로 작용 합니다. SEMM에 대해 자세히 알아보려면 [Microsoft Surface Enterprise 관리 모드 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.
 

## 솔루션 구성 요소

- Windows 10 Team 운영 체제를 실행 하는 Surface Hub 2S 장치
- Windows 10을 실행 하는 별도의 장치
- Surface UEFI 구성자 도구
- Windows 10 Pro 또는 엔터프라이즈 OS 이미지, 버전 1903 이상
- 저장 용량이 16GB 인 2 개의 USB 드라이브, FAT32 형식
- Surface Hub 2, Windows Installer의 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어. MSI 파일
- 인터넷 연결
- 이미징 솔루션 (선택 사항)

 
## 마이그레이션 워크플로 요약

| 단계  | 작업                                                                                                 | 요약                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| raid-1 | [Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | UEFI 버전이 694.2938.768.0 이상 인지 확인 합니다.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Surface UEFI 구성자 및 Surface Hub 2 드라이버 및 펌웨어 다운로드](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Surface Tools에서 [SURFACE UEFI 구성자](https://www.microsoft.com/download/details.aspx?id=46703) 을 다운로드 하 여 별도의 PC에 설치 합니다. [Surface Hub 2에서 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어를 다운로드 합니다. MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974) 을 만들고 5 단계에서 사용할 수 있도록 저장 합니다. |
| 3-4 | [SEMM 인증서 준비](#prepare-semm-certificate)                                                                          | Surface UEFI 구성자 실행에 필요한 인증서를 준비 하거나 현재 인증서를 사용 합니다.                                                                                                                                                                                                                                                                                                      |
| 4(tcp/ipv4) | [SEMM 패키지 만들기](#create-semm-package)                                                                               | Surface Hub 2S에 적용할 필수 구성 파일을 포함 하는 USB 드라이브에 SEMM 패키지를 만들기 위해 서피스 UEFI 구성자을 시작 합니다. PC의 폴더에이 SEMM 패키지 파일을 복사 합니다.                                                                                                                                                                                          |
| 5mb | [Surface Hub 2의 windows 10 Pro 및 Enterprise 용 Windows 10 이미지, SEMM 패키지, 드라이버 및 펌웨어를 포함 하는 USB 플래시 드라이브 준비](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Windows 10 이미지를 포함 하는 단일 USB 드라이브 (이 예에서는 **Bootme** )를 만듭니다. Surface Hub 2 (단계 2) 및 SEMM 패키지 파일 (4 단계)에 Windows 10 Pro 및 Enterprise 용 드라이버와 펌웨어를 **추가 합니다.**                                                                                                                                                                                                  |
| 26 | [OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI 업데이트](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | **Bootme** 드라이브를 사용 하 여 UEFI 메뉴로 부팅 Surface Hub 2S를 사용해 서, semm 패키지를 설치 합니다.|
| 7 | [Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치 합니다.](#install-windows-10-pro-or-enterprise)                                        | **Bootme** 드라이브를 사용 하 여 **Windows 10 Pro 또는 Enterprise** 버전 1903 이상을 설치 합니다.                                                                                                                                                                                                                                                                                 |
| 20cm(8 | [Surface Hub 2에 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어 설치](#install-surface-hub-2-drivers-and-firmware)                                        | 장치에 최신 업데이트와 드라이버가 모두 있는지 확인 하려면 [Surface Hub 2에 Windows 10 Pro 및 Enterprise 용 드라이버와 펌웨어를 설치 합니다. MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                  |
| 되었는지 | [Surface Hub 2S을 개인 생산성 장치로 완전히 구성](#next-steps)                                        |  추천 설정 및 응용 프로그램 집합을 사용 하 여 Surface Hub 2S의 사용을 개인 생산성 장치로 최적화 합니다.                                                                                                                                                                                                                                                                    |

### Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인

Surface Hub를 Windows 10 Team에서 Windows 10 데스크톱으로 마이그레이션하기 전에 필요한 최소 UEFI 버전은 **694.2938.768.0**입니다.
 
**시스템에서 현재 UEFI 버전을 확인 하려면 다음을 실행 합니다.**

1. Surface Hub 2S 홈 화면에서 **시작** 을 선택 하 고 **SurfaceApp** (**모든 앱**  >  **화면**)을 엽니다.

2. 장치에서 현재 버전의 UEFI를 포함 하 여 Surface Hub에 대 한 정보를 표시 하려면 **화면** 을 선택 합니다. UEFI 버전이 아래와 같이 **694.2938.768.0** 이거나 이후 버전인 경우 OS 마이그레이션을 사용 하도록 설정 하기 위해 UEFI는 semm 패키지를 만들 수 있습니다.

    ![Surface 앱을 열고 서피스 선택 &](images/shm-fig1.png)
 
3. UEFI 버전이 버전 **694.2938.768.0**보다 이전인 경우 Windows Update를 사용 하 여 현재 버전을 가져와야 합니다.

**Windows Update에서 UEFI를 업데이트 하려면 다음을 수행 합니다.**
1. Surface Hub 2S에서 **관리자로**로그인 하 고, **모든 앱**  >  **설정** >  **업데이트 및 보안**  >  **Windows** 로 이동한 다음 모든 업데이트를 업데이트 하 고 설치 하 고, 장치를 다시 시작 합니다. Surface 앱을 사용 하 여 UEFI 버전을 확인 합니다. 참고: 사용자 이름 또는 관리자 암호를 모르는 경우에는 장치를 재설정 해야 합니다. 자세한 내용은 [Surface Hub 2S 다시 설정 및 복구](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)를 참조 하세요.

2. UEFI 버전이 **694.2938.768.0** 이상에 도달할 때까지이 단계를 반복 합니다.

3. 여러 번 시도 했지만 여전히 업데이트 된 UEFI가 표시 되지 않으면 **업데이트 기록을** 확인 하 고 실패 한 펌웨어 설치의 모든 인스턴스를 찾습니다. 장치를 다시 설정 해야 할 수 있습니다 (**설정**  >  **업데이트 & 보안**  >  **재설정 장치**).

### Surface UEFI 구성자 및 Surface Hub 2 드라이버 및 펌웨어 다운로드

별도의 PC에서 다음을 수행 합니다.

- 화면 도구에서 Microsoft [SURFACE UEFI 구성자](https://www.microsoft.com/download/details.aspx?id=46703) 을 다운로드 하 여 설치 합니다. Surface UEFI Configurator는 Surface Hub 2S에서 실행할 수 없으며, Windows 10 팀이 설치 되어 있습니다.

- [Surface Hub 2 드라이버 및 펌웨어 Windows Installer를 다운로드 합니다. MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974) 을 설치 하 여 새 운영 체제를 설치할 수 있습니다.

### SEMM 인증서 준비

Surface UEFI 구성자을 처음 사용 하는 경우 인증서를 준비 해야 합니다. 이 인증서는 디바이스를 SEMM에 등록 한 후 승인 된 인증서로 만든 패키지만 UEFI 설정을 수정 하는 데 사용할 수 있도록 보장 합니다. 인증서를 획득 하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.

- 대규모 엔터프라이즈 조직은 일반적으로 표준 보안 관례에 따라 인증서를 생성 하는 고유한 인증서 인프라를 유지 관리 합니다.

- 중간 규모 기업과 다른 업체는 타사 공급자 로부터 인증서를 획득 하도록 선택할 수 있습니다. 이는 IT 전문 지식 또는 전담 IT 보안 팀이 없는 조직에 게 권장 되는 옵션입니다.

- 또는 다음 설명서에 따라 PowerShell 스크립트를 사용 하 여 자체 서명 된 인증서를 생성할 수 있습니다 ( [Surface Enterprise 관리 모드 인증서 요구 사항](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)). 또는 PowerShell을 사용 하 여 다음 설명서에 따라 고유한 인증서를 만들 수 있습니다: [New-new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).

UEFI 설정을 적용 하기 전에 구성 파일의 서명을 확인 하기 위해 SEMM 패키지를 인증서로 보호 해야 합니다. 자세히 알아보려면 [Surface Enterprise 관리 모드](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 설명서를 참조 하세요.
 
 
### SEMM 패키지 만들기

1. **SURFACE UEFI 구성자** 를 열고 **시작**을 선택 합니다.

   ![Surface UEFI 구성자 열기](images/shm-fig2.png)
   
2. **Surface 장치** 를 선택 하 고 **다음**을 선택 합니다.

   ![Surface 장치 선택](images/shm-fig3.png)
  
3. **구성 패키지**를 선택 합니다.

   ![구성 패키지 선택](images/shm-fig4.png)
  
4. **인증서 보호**를 선택 합니다.

   ![인증서 보호 선택](images/shm-fig5.png)

5. 인증서 .pfx 파일을 추가 하 라는 메시지가 표시 됩니다.

   ![인증서를 추가 하 라는 메시지가 표시 됩니다.](images/shm-fig6.png)
   
6. **인증서 암호** 를 입력 하 고 **확인을**선택 합니다.

   ![인증서 암호를 입력 하 고 확인을 선택 합니다.](images/shm-fig7.png)

7. **암호 보호** 를 선택 하 여 Surface UEFI에 암호를 추가 합니다. UEFI로 부팅할 때마다이 암호가 필요 합니다. Surface Hub 2S에서 사용 하 게 될 UEFI 암호를 설정 하는 것 **이 좋습니다** .

   ![비밀 번호 보호 클릭](images/shm-fig8.png)
   
8. **UEFI 암호** 를 설정 하 고 **확인**을 선택 합니다.

   ![UEFI 암호 입력](images/shm-fig9.png)

   > [!IMPORTANT]
   > 비밀 번호를 기록해 둡니다. 비밀 번호를 잊어버리거나 분실 한 경우에는 복구 프로세스가 없습니다. 

9. **Surface Hub 2S** 를 선택 하 고 **다음**을 선택 합니다.

   ![Surface Hub 2S 선택](images/shm-fig10.png)
   
10. **다음**을 선택합니다.

    ![다음 선택](images/shm-fig10a.png)

11. Windows 10 Pro 또는 Enterprise 설치를 허용 하려면 **Os마이그레이션이 enableon을 선택 합니다.**

    ![OS 마이그레이션 사용 선택](images/shm-fig11.png)
    
12. **Enableosmigration** **On** 으로 설정 하 고 **다음**을 선택 합니다.

    ![On으로 OS 마이그레이션 사용 설정](images/shm-fig12.png)

> [!NOTE]
> SEMM 패키지를 적용 한 후에는 모든 UEFI 설정이 장치에서 UEFI 메뉴에 회색으로 표시 (잠김)로 표시 됩니다. 이 값에는 PXE 부팅에 대 한 IPv6 같은 다른 설정의 기본값이 포함 됩니다. UEFI 설정을 수정 하려면 다른 SEMM 패키지를 적용 하거나 h m m m a m m m m에서 장치를 등록 해제 해야 합니다.

#### USB 드라이브에 SEMM 패키지 저장

1. PC에 USB 드라이브를 연결 합니다. **Hub 2S** 를 선택 하 고 **다음**을 선택 합니다.

   ![USB 선택](images/shm-fig13.png)
   
2. **빌드**를 선택 합니다.

   ![빌드 선택](images/shm-fig14.png)

3. 이 페이지의 스크린샷을 캡처한 다음 **End (종료**)를 선택 합니다. 이제 SEMM 패키지 **Dfciupdate. dfi** 및 인증서의 손도장 (thumbprint)의 마지막 두 문자인 semm 지문이 있는 텍스트 파일이 포함 되어 있습니다.

   ![종료 선택](images/shm-fig15.png)
   
4. Surface Hub 2S에 패키지를 적용할 때 SEMM을 활성화 하는 데 필요한 인증서 손도장의 마지막 2 문자를 저장 합니다.

### Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어를 포함 하는 USB 플래시 드라이브 준비

다음 옵션 중 하나를 사용 하 여 Windows 10 Pro 또는 엔터프라이즈 이미지 (버전 1903 이상)를 설치할 수 있습니다.

- 현재 이미징 솔루션.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 를 사용 하면 현재 windows 10 업데이트, Office, 선택한 다른 앱, 필요한 드라이버와 펌웨어를 모두 포함할 수 있는 부팅 가능 Windows 10 이미지를 만들 수 있습니다. 

- Windows 10 Pro 또는 엔터프라이즈 이미지가 설치 된 USB 플래시 드라이브  [와 Surface Hub 2에 windows 10 pro 및 enterprise 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치한 후
 

이 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2에서 Windows 10 Pro 및 Enterprise 용 SEMM 패키지 파일 및 드라이버와 펌웨어를 추가 하는 방법에 대해 설명 합니다. MSI 파일. 다른 배포 방법을 사용 하는 경우 [OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI를 업데이트 하](#update-uefi-on-surface-hub-2s-to-enable-os-migration)여 다음 섹션으로 진행 하세요.

> [!NOTE]
> 설치한 후에는 Windows 10 Pro 또는 Windows 10 Enterprise에 대 한 유효한 라이선스가 필요 합니다.

1. Windows 10 Pro 설치를 만들려면 **미디어 만들기** 도구 사용에 대 한 [windows 10 다운로드](https://www.microsoft.com/software-download/windows10) 페이지의 지침을 따릅니다. Windows 10 Enterprise를 다운로드 하려면 [Microsoft 볼륨 라이선스 서비스 센터로](https://www.microsoft.com/licensing/servicecenter/default.aspx)이동 합니다.

2. 새 **USB 저장소** 드라이브를 삽입 합니다. **미디어 만들기** 도구를 시작 하 고 **설치 미디어 만들기** 를 선택한 후 **다음**을 선택 합니다.

   ![설치 미디어 만들기](images/shm-fig16.png)
   
3. 언어, Windows 10 및 64 비트 (x64)를 선택 하 고 **다음**을 선택 합니다.

   ![언어, Windows 10, 64 비트 & 선택 하 고 다음을 선택 합니다.](images/shm-fig17.png)
   
4. **USB 플래시 드라이브** 를 선택 하 고 **다음**을 선택 합니다.

   ![USB 플래시 드라이브를 선택 하 고 다음을 선택 합니다.](images/shm-fig18.png)
   
5. 다운로드가 완료 되 면 **마침을**선택 합니다.

   ![마침을 선택 합니다.](images/shm-fig19.png)
   
6. Surface Hub 2에서 Windows 10 Pro 및 Enterprise 용 SEMM 패키지 파일 및 드라이버와 펌웨어를 복사 합니다. MSI가 Windows 10 이미지를 포함 하는 USB 플래시 드라이브 (**부트**)에 표시 됩니다.

    - DfciUpdate. dfi
    - SEMM 지문이 있는 텍스트 파일입니다. (이 예에서는 SurfaceUEFI_2020Aug25_1058.txt).
    - Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)의 Windows 10 Pro 및 Enterprise 용 드라이버 및 펌웨어

### OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI 업데이트

**부팅 me** 드라이브를 사용 하 여 semm 패키지 파일을 설치 하 고 UEFI를 업데이트 하 여 Surface Hub가 Windows 10 Pro 또는 Enterprise를 실행할 수 있도록 합니다. 그런 다음 **Bootme** 드라이브로 부팅 하 여 Windows 10을 설치 합니다.

1. Windows 10 Pro 및 엔터프라이즈의 Surface Hub 2에 대 한 SEMM 패키지 파일, 드라이버, 펌웨어를 포함 하는 **Bootme** 드라이브를 삽입 합니다. MSI 및 Windows 10이 Surface Hub 2S의 USB-A 포트에 파일을 설치 합니다.  

2. UEFI로 부팅 하려면 다음을 수행 합니다.

   1. Surface Hub 2S의 첫 번째 전원 끄기 (종료).
   1. **볼륨 +** 를 길게 누른 다음 **전원** 단추를 눌렀다가 놓습니다.
   1. UEFI 메뉴가 나타날 때까지 지주 **볼륨 +** 를 유지 합니다.
   
      ![UEFI 메뉴가 나타날 때까지 holdling 볼륨을 유지 합니다.](images/shm-fig20.png)
      
3. 장치가 다시 시작 되 면 앞에서 만든 UEFI 암호 (해당 하는 경우)를 입력 합니다 (권장).

   ![장치가 다시 시작 되 면 UEFI paassword를 입력 합니다.](images/shm-fig22.png)
   
4. UEFI 메뉴에서 **Management**  >  **USB에서 관리 설치**를 선택 합니다.

   ![USB에서 설치 & 관리를 선택 합니다.](images/shm-fig21.png)
   
5. 아래와 같이 **지금 다시 시작**을 선택 합니다. 장치가 재부팅 되 고 화면 가운데에 흰색 4 사각형 로고가 표시 되 고 종료 됩니다.

   ![지금 다시 시작 선택](images/shm-fig25.png)
   
6. 전원 단추를 눌렀다가 놓으면 빨간색 화면에 Surface Enterprise 관리 모드를 활성화 하 라는 메시지가 표시 됩니다. 

7. 두 문자 **인증서 손도장**( **UEFI 설정 암호** )을 입력 한 다음 **확인을**선택 합니다.

   ![2 문자 인증서 지문 입력](images/shm-fig23.png)
 
   > [!NOTE]
   > 장치에서 SEMM을 활성화 하면 새 UEFI 설정 **Enableosmigration** 적용 됩니다. 더 이상 Windows 10 팀에 액세스할 수 없으며 다음 단계로 진행 하 여 Windows 10 Pro 또는 Windows 10 Enterprise를 설치 해야 합니다. 

8. 장치가 재부팅 되 고 화면 가운데에 흰색 4 사각형 로고가 표시 된 다음 다시 종료 됩니다.

### Windows 10 Pro 또는 Enterprise 설치

1. 부팅 가능 Windows 10 Pro 또는 엔터프라이즈 드라이브가 Surface Hub 2 USB-A 포트에 없으면 지금 삽입 한 다음 전원 단추를 눌렀다가 놓습니다.

2. 장치가 시작 되 면 화면 가운데에 흰색 4 정사각형이 표시 되 고 흰색 4 사각형 로고 아래에 회전 원이 표시 됩니다.

3. 장치가 USB 드라이브로 자동으로 부팅 되지 않으면 장치 전원을 끈 다음 (전원 코드를 뽑고 다시 연결). 전원 코드를 다시 연결한 후에는 화면이 화면 가운데에 있는 흰색 4 개 정사각형 로고까지 몇 초 후에 장치가 부팅 되거나 전원 단추를 눌렀다가 놓아 장치를 다시 켤 수 있습니다. 화면 가운데에 4 사각형 로고가 표시 되 면 즉시 4도 흰색 사각형 로고 아래에 회전 하는 원이 나타날 때까지 볼륨 작게 단추를 길게 누릅니다.
 
   ![USB에서 Windows 10으로 부팅](images/shm-fig26.png)
   
4. OOBE (로그 아웃) 설정이 실행 되 면 지침에 따라 Windows 10 Pro 또는 Enterprise (버전 1903 이상)를 설치 합니다.

### Surface Hub 2 드라이버 및 펌웨어 설치

 - 장치에 최신 업데이트와 드라이버가 모두 있는지 확인 하려면 [Surface Hub 2에 Windows 10 Pro 및 Enterprise 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.
 
### 다음 단계

Surface Hub 2S을 개인 생산성 장치로 완전히 구성 하려면 [Surface hub 2에서 Windows 10 Pro 또는 Enterprise 구성을](surface-hub-2-post-install.md)참조 하세요.

> [!NOTE]
>이 문서에 설명 된 단계를 수행 하 여 Surface Hub 2 용 Windows 10 Pro 또는 Enterprise로 장치를 마이그레이션하는 데 실패 한 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.

