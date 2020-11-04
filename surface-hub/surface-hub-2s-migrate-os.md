---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: 이 문서에서는 Surface Hub 2의 Windows 10 팀에서 windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 방법에 대해 설명 합니다.
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 713bd2e76f144b4dca7c0fad5c584b06ea12b0b5
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154141"
---
# Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션

Surface Hub 2S는 Windows 10 팀에 사전 설치 되어 제공 됩니다. 이 사용자 지정 버전의 Windows 10은 회의실 환경에서 공동 작업을 용이 하 게 하기 위해 설계 되었습니다. 이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용 하기 위해 Windows 10 Pro 또는 Enterprise를 실행 하는 옵션이 있습니다. 

> [!IMPORTANT]
>일반 업그레이드 또는 마이그레이션과 달리이 프로세스는이 문서에 설명 된 대로 규범적 절차를 따라야 합니다. 계속 하기 전에 [솔루션 구성 요소](#solution-components) 및 [마이그레이션 및 설치 워크플로](#migration-and-installation-workflow-summary) 를 검토 하세요.


> [!NOTE]
> Windows 10 Pro 또는 Enterprise를 설치 하는 경우 기존 Windows 10 팀 라이선스와 별개인 새로운 라이선스가 필요 합니다. 


별도의 PC 및 다운로드 가능한 도구 *SURFACE UEFI 구성자*를 사용 하 여 Windows 10 팀에서 마이그레이션을 시작 합니다. 이 도구를 사용 하 여 Surface Hub 2S에 적용 하는 새 UEFI 설정을 포함 하는 패키지를 만듭니다.  

Surface UEFI 구성자는 Surface 엔터프라이즈 관리 모드 (SEMM)의 인터페이스로 작동 합니다. 기업 환경에서 Surface 장치에 대 한 펌웨어 설정을 중앙에서 관리할 수 있도록 설계 되었습니다. 자세한 내용은 [Microsoft SEMM 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.
 

## 솔루션 구성 요소

- Windows 10 Team 운영 체제를 실행 하는 Surface Hub 2S 장치
- Windows 10을 실행 하는 별도의 장치
- SEMM 패키지를 만들기 위한 Surface UEFI 구성자 도구
- Windows 10 Pro 또는 엔터프라이즈 OS 이미지, 버전 1903 이상
- 16gb의 저장소, FAT32 형식으로 된 2 개의 USB 드라이브
- Surface Hub 2 용 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어는 MSI (Microsoft Windows Installer) 파일입니다.
- 인터넷 연결
- 이미징 솔루션 (선택 사항)

 
## 마이그레이션 및 설치 워크플로 요약

| 단계  | 작업                                                                                                 | 요약                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| raid-1 | [Surface Hub의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인 2S.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | UEFI 버전이 694.2938.768.0 이상 인지 확인 합니다.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Surface UEFI 구성자 및 Surface Hub 2 드라이버와 펌웨어를 다운로드 합니다.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | [**IT에 대 한 Surface Tools**](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 **다운로드**를 선택 합니다. 그런 다음 Surface UEFI 구성자를 선택 하 여 다운로드 **합니다. MSI 파일** 을 만들고 별도의 PC에 설치 합니다. [Surface Hub 2 MSI 파일에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 다운로드 합니다. 5 단계에서 사용할 수 있도록 저장 합니다. |
| 3-4 | [SEMM 인증서를 준비 합니다.](#prepare-the-semm-certificate)                                                                          | Surface UEFI 구성자을 실행 하는 데 필요한 인증서를 준비 합니다. 또는 현재 인증서를 사용 합니다.                                                                                                                                                                                                                                                                                                      |
| 4(tcp/ipv4) | [SEMM 패키지를 만듭니다.](#create-a-semm-package)                                                                               | Surface Hub 2S에 적용 해야 하는 구성 파일을 포함 하는 USB 드라이브에 SEMM 패키지를 만들기 위해 서피스 UEFI 구성자 시작 PC의 폴더에이 SEMM 패키지 파일을 복사 합니다.                                                                                                                                                                                          |
| 5mb | [Windows 10 용 이미지, SEMM 패키지, Surface Hub 2의 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어가 포함 된 USB 플래시 드라이브를 준비 합니다.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Windows 10 이미지를 포함 하는 단일 USB 드라이브를 만듭니다. 이 예제에서 드라이브는 *Bootme*로 지정 됩니다. Surface Hub 2 (단계 2) 및 SEMM 패키지 파일 (4 단계)에 Windows 10 Pro 및 Enterprise OS 용 드라이버와 펌웨어를 *추가 합니다.*                                                                                                                                                                                                  |
| 26 | [Surface Hub 2S에서 UEFI를 업데이트 하 여 OS 마이그레이션을 사용 하도록 설정 합니다.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | *Bootme* 드라이브를 사용 하 여 UEFI 메뉴로 부팅 Surface Hub 2S를 사용해 서 semm 패키지를 설치 합니다.|
| 7 | [Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치 합니다.](#install-windows-10-pro-or-enterprise)                                        | *Bootme* 드라이브를 사용 하 여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치 합니다.                                                                                                                                                                                                                                                                                 |
| 20cm(8 | [Surface Hub 2에 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어를 설치 합니다.](#install-surface-hub-2-drivers-and-firmware)                                        | 장치에 최신 업데이트와 드라이버가 모두 포함 되도록 하려면 [Surface Hub 2 MSI 파일에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.                                                                                                                                                                                                                                                                                  |
| 되었는지 | [Surface Hub 2S을 개인 생산성 장치로 완전히 구성 합니다.](#configure-recommended-settings)                                        |  Surface Hub 2S을 개인 생산성 장치로 최적화 하는 데 권장 설정 및 응용 프로그램을 사용 하도록 설정 합니다.                                                                                                                                                                                                                                                                    |

### Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족 하는지 확인

Windows 10 Team에서 Windows 10 Desktop으로 Surface Hub를 마이그레이션하기 전에 적어도 *694.2938.768.0*인 UEFI 버전이 필요 합니다.
 
시스템에서 UEFI 버전을 확인 하려면 다음을 수행 합니다.

1. Surface Hub 2S 홈 페이지에서 **시작**을 선택 하 고 Surface app (**모든 앱**  >  **화면**)을 엽니다.

2. 디바이스의 현재 UEFI 버전을 포함 하 여 Surface Hub에 대 한 정보를 표시 하려면 **화면** 을 선택 합니다. 
   - UEFI 버전이 *694.2938.768.0* 이상 이면 다음 이미지와 같이 OS 마이그레이션을 사용 하도록 설정 하는 semm 패키지를 만들 수 있습니다.

       ![Surface 앱의 Surface 페이지를 보여 주는 스크린샷](images/shm-fig1.png)
 
   - UEFI 버전이 *694.2938.768.0*보다 이전인 경우 Windows Update를 사용 하 여 현재 버전을 가져옵니다.

Windows Update를 사용 하 여 UEFI를 업데이트 하려면 다음을 실행 합니다.

1. Surface Hub 2S에 **관리자로**로그인 합니다. 
    >[!Note]
    > 사용자 이름 또는 관리자 암호를 모르는 경우에는 장치를 다시 설정 해야 합니다. 자세한 내용은 [Surface Hub 2S 다시 설정 및 복구](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)를 참조 하세요.

1. **모든 앱**  >  **설정**  >  **업데이트 및 보안**  >  **Windows 업데이트로**이동한 다음 모든 업데이트를 설치 합니다. 
1. 디바이스를 다시 시작합니다. 
1. Surface 앱을 사용 하 여 UEFI 버전을 확인 합니다. 
2. UEFI 버전이 *694.2938.768.0* 이상에 도달할 때까지이 단계를 반복 합니다.
3. 여러 번 시도한 후에 업데이트 된 UEFI가 표시 되지 않으면 **업데이트 기록을** 확인 하 고 실패 한 펌웨어 설치의 모든 인스턴스를 찾습니다. 장치를 다시 설정 해야 할 수 있습니다 (**설정**  >  **업데이트 & 보안**  >  **재설정 장치**).

### Surface UEFI 구성자 및 Surface Hub 2 드라이버 및 펌웨어 다운로드

별도의 PC에서 다음을 수행 합니다.

1. [IT에 대 한 Surface Tools 페이지](https://www.microsoft.com/download/details.aspx?id=46703)에서 **다운로드**를 선택 합니다.  
1. Surface UEFI 구성자 MSI 파일을 선택 하 여 다운로드 하 고 별도의 PC에 설치 합니다. Windows 10 Team edition이 설치 되어 있는 동안 surface Hub 2S에서 Surface UEFI 구성자 도구를 실행할 수 없습니다.

1. [Surface Hub 2 드라이버 및 펌웨어 Windows INSTALLER MSI 파일](https://www.microsoft.com/download/details.aspx?id=101974)을 다운로드 합니다. 새 운영 체제를 설치할 때이 파일을 사용 합니다.

### SEMM 인증서 준비

이전에 Surface UEFI 구성자을 사용 하지 않은 경우에는 인증서를 준비 해야 합니다. 이 인증서는 디바이스를 SEMM에 등록 한 후에는 승인 된 인증서로 만든 패키지를 사용 하는 경우에만 UEFI 설정을 수정할 수 있도록 보장 합니다. 

인증서를 얻는 방법은 조직의 규모 또는 복잡도에 따라 달라 집니다.

- 일반적으로 엔터프라이즈 조직은 표준 보안 관례에 따라 인증서를 생성 하는 고유한 인프라를 유지 관리 합니다.

- 중간 규모 기업과 다른 사용자가 파트너 공급자 로부터 인증서를 받을 수 있습니다. 이 옵션은 IT 전문 지식이 부족 하거나 전담 IT 보안 팀을 보유 하 고 있지 않은 조직에 권장 됩니다.

- 또는 PowerShell 스크립트를 사용 하 여 자체 서명 된 인증서를 생성할 수 있습니다. 자세한 내용은 [Surface Enterprise 관리 모드 인증서 요구 사항을](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)참조 하세요. 또는 PowerShell을 사용 하 여 고유한 인증서를 만들 수 있습니다. 자세한 내용은 [새로운 new-selfsignedcertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 설명서를 참조 하세요.

Surface UEFI 구성자가 생성 하는 SEMM 패키지는 인증서를 사용 하 여 보호 해야 합니다. 이 인증서는 UEFI 설정을 적용할 수 있기 전에 구성 파일의 서명을 확인 합니다. 자세한 내용은 [Semm 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.
 
 
### SEMM 패키지 만들기

1. 별도의 PC에서 이전에 다운로드 한 Surface UEFI 구성자 도구를 설치 합니다. 

2. Surface UEFI 구성자를 연 다음 **시작**을 선택 합니다.

   ![Surface UEFI 구성자를 엽니다.](images/shm-fig2.png)
   
3. **Surface 장치**를 선택 하 고 **다음**을 선택 합니다.

   ![Surface 장치를 선택 합니다.](images/shm-fig3.png)
  
4. **구성 패키지**를 선택 합니다.

   ![구성 패키지를 선택 합니다.](images/shm-fig4.png)
  
5. **인증서 보호**를 선택 합니다.

   ![인증서 보호를 선택 합니다.](images/shm-fig5.png)

   인증서 .pfx 파일을 추가 하 라는 메시지가 표시 됩니다.

   ![인증서를 추가 합니다.](images/shm-fig6.png)
   
7. 인증서 암호를 입력 한 다음 **확인**을 선택 합니다.

   ![인증서 암호를 입력 하 고 확인을 선택 합니다.](images/shm-fig7.png)

8. **암호 보호** 를 선택 하 여 Surface UEFI에 암호를 추가 합니다. UEFI로 부팅할 때마다이 암호가 필요 합니다. Surface Hub 2S에서 사용할 UEFI 암호를 설정 하는 *것이 좋습니다* .

   ![비밀 번호 보호를 선택 합니다.](images/shm-fig8.png)
   
9. UEFI 암호를 설정한 다음 **확인**을 선택 합니다.

   > [!IMPORTANT]
   > Surface Hub를 관리 하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장 합니다. 암호가 손실 된 경우에는 복구할 수 없습니다. 

   ![UEFI 암호를 입력 합니다.](images/shm-fig9.png)

10. **Surface Hub 2S**를 선택 하 고 **다음**을 선택 합니다.

    ![Surface Hub 2S를 선택 합니다.](images/shm-fig10.png)
   
11. **다음**을 선택합니다.

    ![다음을 선택합니다.](images/shm-fig10a.png)

12. Windows 10 Pro 또는 Enterprise 설치를 허용 하려면 **Enableosmigration**을 설정 하 고 **다음**을 선택 합니다.

    ![O S 마이그레이션 사용을 선택 합니다.](images/shm-fig11.png)
    
    ![OS 마이그레이션 사용을 On으로 설정 합니다.](images/shm-fig12.png)

> [!NOTE]
> SEMM 패키지를 적용 한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다 (잠금). **PXE 부팅에 대 한 IPv6 등의** 다른 설정에 대 한 기본값도 사용할 수 없습니다. 
>
>마이그레이션을 완료 한 후 UEFI 설정을 변경 하려면 다른 SEMM 패키지를 적용 하거나 h m m m m m m m m m m m m m m m a m에서 다른 SEMM 패키지를 적용 하 여 UEFI 설정을 변경 하는 경우 새 SEMM 패키지를 빌드할 때 원래 인증서를 사용 해야 합니다. UEFI 구성자 도구를 사용 하 고 기본 마이그레이션 단계와 같이 **Enableosmigration** 을 해제 (켜져 있지 않음) 합니다.

#### USB 드라이브에 SEMM 패키지 저장

1. PC에 USB 드라이브를 연결 합니다. 
1. **Hub 2S**를 선택 하 고 **다음**을 선택 합니다.

   ![USB 선택](images/shm-fig13.png)

   > [!WARNING]
   > USB 드라이브의 모든 기존 데이터는 SEMM 패키지가 빌드될 때 지워집니다. SEMM 패키지를 작성 하기 전에 저장 하려는 USB 드라이브에서 파일을 제거 합니다.
   
2. **빌드**를 선택 합니다.

   ![빌드를 선택 합니다.](images/shm-fig14.png)

3. 이 페이지의 스크린샷을 캡처한 다음 **End (종료**)를 선택 합니다. 이제 SEMM 패키지가 준비 되었습니다. 여기에는 semm 패키지 *Dfciupdate. dfi* 와 인증서의 손도장 (thumbprint)의 마지막 두 문자를 포함 하는 텍스트 파일이 포함 되어 있습니다.

   ![종료를 선택 합니다.](images/shm-fig15.png)
   
4. 인증서 지문의 마지막 두 문자를 저장 합니다. Surface Hub 2S에 패키지를 적용 하는 경우 SEMM을 활성화 하려면 이러한 문자가 필요 합니다.

### Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어가 포함 된 USB 플래시 드라이브 준비

다음 옵션 중 하나를 사용 하 여 Windows 10 Pro 또는 엔터프라이즈 이미지 (버전 1903 이상)를 설치할 수 있습니다.

- 현재 이미징 솔루션.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator). 이 도구를 사용 하 여 부팅 가능한 Windows 10 이미지를 만듭니다. 이미지에는 현재 Windows 10 업데이트, Office, 선택한 다른 앱, 필요한 드라이버 및 펌웨어가 모두 포함 될 수 있습니다. 

- Windows 10 Pro 또는 엔터프라이즈 이미지를 포함 하는 USB 플래시 드라이브 그런 다음 [Surface Hub 2에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.
 
다음 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS 용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가 하는 방법에 대해 설명 합니다. 다른 배포 방법을 사용 하는 경우이 문서의 [OS 마이그레이션 기능을 사용 하도록 설정 하는 Surface Hub 2S의 UEFI 업데이트](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 섹션으로 이동 합니다.

> [!NOTE]
> 설치를 완료 한 후에는 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대 한 유효한 라이선스가 필요 합니다.

1. Windows 10 Pro 설치를 만들려면 [**windows 10 다운로드**](https://www.microsoft.com/software-download/windows10) 페이지에서 지침에 따라 미디어 만들기 도구를 다운로드 합니다. Windows 10 Enterprise를 다운로드 하려면 [Microsoft 볼륨 라이선스 서비스 센터로](https://www.microsoft.com/licensing/servicecenter/default.aspx)이동 합니다.

2. 새 USB 저장소 드라이브를 삽입 합니다. 
1. 미디어 만들기 도구를 열고 **설치 미디어 만들기**를 선택한 후 **다음**을 선택 합니다.

   ![설치 미디어를 만듭니다.](images/shm-fig16.png)
   
3. 언어를 선택한 다음 **Windows 10** 및 **64 비트 (x64)** 를 선택 합니다. 그런 후 **다음**을 선택 합니다.

   ![언어를 선택 하 고 Windows 10 및 64 비트를 선택 합니다. 그런 후 다음을 선택 합니다.](images/shm-fig17.png)
   
4. **USB 플래시 드라이브**를 선택 하 고 **다음**을 선택 합니다.

   ![U B 플래시 드라이브를 선택 하 고 다음을 선택 합니다.](images/shm-fig18.png)
   
5. 다운로드가 완료 되 면 **마침을**선택 합니다.

   ![마침을 선택 합니다.](images/shm-fig19.png)
   
6. Windows 10 이미지를 포함 하는 USB 플래시 드라이브 (*부트*)의 루트에 Surface Hub 2 (MSI 파일)의 semm 패키지 파일과 드라이버 및 펌웨어를 복사 합니다. BOOTME USB 드라이브에는 다음이 포함 됩니다.

    - Windows 10 부팅 가능 이미지
    
    - SEMM 패키지 파일 (USB 드라이브의 루트에 복사 됨).
    
      - *Dfciupdate. dfi*.
      - SEMM 지문을 포함 하는 텍스트 파일입니다. (이 예제에서는 파일을 *SurfaceUEFI_2020Aug25_1058.txt*.) 자동으로 생성 된 날짜 시간 스탬프는 Surface UEFI Configurator를 사용 하 여 파일을 만든 날짜에 해당 합니다.

   - Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)의 Windows 10 Pro 및 Enterprise OS 용 드라이버 및 펌웨어. 이 파일을 USB 드라이브의 루트에 복사 합니다.

### OS 마이그레이션을 사용 하도록 Surface Hub 2S에서 UEFI 업데이트

1. BOOTME 드라이브를 USB-A Surface Hub 2S의 포트에 넣습니다. 필수 파일 목록은 이전 섹션을 참조 하세요.

2. UEFI로 부팅 하려면 다음을 수행 합니다.

   1. Surface Hub 2S를 끄거나 종료 합니다.
   1. **볼륨 +** 를 길게 누른 다음 전원 단추를 눌렀다가 놓습니다.
   1. UEFI 메뉴가 나타날 때까지 지주 **볼륨 +** 를 유지 합니다.
   
      ![UEFI 메뉴가 나타날 때까지 볼륨 단추를 길게 누릅니다.](images/shm-fig20.png)
      
3. 장치가 다시 시작 되 면 앞에서 만든 UEFI 암호 (해당 하는 경우)를 입력 합니다 (권장).

   ![UEFI 암호를 입력 합니다.](images/shm-fig22.png)
   
4. UEFI 메뉴에서 **Management**  >  **USB에서 관리 설치**를 선택 합니다.

   ![관리 및 U S B에서 설치를 선택 합니다.](images/shm-fig21.png)
   
5. 다음 이미지가 표시 된 대로 **지금 다시 시작**을 선택 합니다. 장치가 재부팅 됩니다. 창 가운데에 흰색 Microsoft 로고가 표시 되 고 종료 됩니다.

   ![지금 다시 시작을 선택 합니다.](images/shm-fig25.png)
   
6. 전원 단추를 눌렀다가 놓습니다. 표시 되는 빨간색 창에서 Surface Enterprise 관리 모드를 활성화 합니다. 

7. 2 자로 된 인증서 손도장과 UEFI 설정 암호를 입력 합니다. 그런 다음 **확인을**선택 합니다.

   ![2 자로 된 인증서 손도장과 UEFI 설정 암호를 입력 합니다.](images/shm-fig23.png)
 
   > [!NOTE]
   > 장치에서 SEMM을 활성화 하면 새 UEFI 설정 **Enableosmigration** 적용 됩니다. 더 이상 Windows 10 팀에 액세스할 수 없게 됩니다. 대신 다음 단계를 계속 하 고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치 해야 합니다. 

   장치가 재부팅 됩니다. 화면 중간에 흰색 로고를 표시 한 다음 다시 종료 합니다.

### Windows 10 Pro 또는 Enterprise 설치

1. 부팅 가능 Windows 10 Pro 또는 엔터프라이즈 드라이브가 Surface Hub 2 USB-A 포트에 없는 경우 지금 삽입 합니다. 그런 다음 전원 단추를 눌렀다가 놓습니다. 

    장치가 시작 되 면 화면 가운데에 흰색 로고가 표시 됩니다. 그런 다음 흰색 로고 아래에 회전 하는 원이 표시 됩니다.

3. 장치가 자동으로 USB 드라이브로 부팅 되지 않으면 장치 전원을 끈 다음 (전원 코드를 뽑은 다음 다시 연결). 전원 코드를 다시 연결 하면 몇 초 후에 장치가 부팅 됩니다. 그러면 화면 가운데에 흰색 로고가 표시 됩니다. 

    장치가 켜지 지 않으면 전원 단추를 눌렀다가 놓습니다. 화면 가운데에 로고가 표시 되 면 즉시 흰색 로고 아래에 회전 하는 원이 나타날 때까지 볼륨 단추를 길게 누릅니다.
 
   ![U S B 드라이브에서 Windows 10으로 부팅 합니다.](images/shm-fig26.png)
   
4. OOBE (처음 실행 경험) 설정이 시작 되 면 지침에 따라 Windows 10 Pro 또는 Enterprise (버전 1903 이상)를 설치 합니다.

### Surface Hub 2 드라이버 및 펌웨어 설치

장치에 최신 업데이트와 드라이버가 모두 있는지 확인 하려면 [Surface Hub 2에 Windows 10 Pro 및 ENTERPRISE OS 용 드라이버와 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치 합니다.
 
## 권장 설정 구성

Surface Hub 2S을 개인 생산성 장치로 완전히 구성 하려면 [Surface hub 2에서 Windows 10 Pro 또는 Enterprise 구성을](surface-hub-2-post-install.md)참조 하세요.

> [!NOTE]
>이 문서에서 설명 하는 단계가 Surface Hub 2 용 Windows 10 Pro 또는 Enterprise로 장치를 성공적으로 마이그레이션하지 못하는 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.

## Windows 10 팀으로 롤백

장치를 Windows 10 팀으로 복원 하려는 경우 [Surface Hub 2S 다시 설정 및 복구](surface-hub-2s-recover-reset.md)를 참조 하세요.

## 버전 기록

다음 표에는이 문서의 변경 내용이 요약 되어 있습니다.

| 버전 | Date               | 설명                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| variant. 1.2  | 2020 년 9 월 29 일 | 사용성 피드백을 처리 하는 기타 업데이트.                                                        |
| variant. 1.1  | 2020 년 9 월 15 일 | 새 OS 설치에 대 한 라이선스 요구 사항을 명확 하 게 설명 하는 추가 메모를 배치 했습니다. |
| variant. 1.0  | 2020 년 9 월 1 일  | 새 문서.                                                                                           |
