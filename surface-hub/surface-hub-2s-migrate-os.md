---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: 이 문서에서는 Surface Hub 2의 Windows 10 Team에서 Windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 방법을 설명합니다.
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 01c5c8a5c6b9f7ed657829fe792fc9eecd1facb5
ms.sourcegitcommit: 5d02cca9ca8c0a252798c2fc0a89dbda81911c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195403"
---
# Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션

Surface Hub 2S는 Windows 10 Team과 함께 사전 설치됩니다. 이 사용자 지정된 Windows 10 버전은 회의실 환경에서 공동 작업을 용이하게 하도록 설계되었습니다. 이제 다른 PC와 마찬가지로 Surface Hub 2S를 사용하기 위해 Windows 10 Pro 또는 Enterprise를 실행하는 옵션이 제공됩니다. 

> [!IMPORTANT]
>일반적인 업그레이드 또는 마이그레이션과 달리 이 프로세스에서는 이 문서에 설명된 징계 절차를 따라야 합니다. 계속하기 [전에 솔루션](#solution-components) 구성 요소 및 마이그레이션 및 [설치](#migration-and-installation-workflow-summary) 워크플로를 검토합니다.


> [!NOTE]
> Windows 10 Pro 또는 Enterprise를 설치할 때 기존 Windows 10 Team 라이선스와는 별개인 새 라이선스가 필요합니다. 


별도의 PC 및 다운로드 가능한 도구 Surface UEFI 구성 도구를 사용하여 Windows 10 Team에서 *마이그레이션을 시작하세요.* 이 도구를 사용하여 Surface Hub 2S에 적용하는 새 UEFI 설정이 포함된 패키지를 만들 수 있습니다.  

Surface UEFI 구성기는 Surface SEMM(엔터프라이즈 관리 모드)에 대한 인터페이스로 작동합니다. 회사 환경의 Surface 디바이스에서 펌웨어 설정을 중앙에서 쉽게 관리하도록 설계되었습니다. 자세한 내용은 Microsoft <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 설명서를 참조하세요.</a>
 

## 솔루션 구성 요소

- Windows 10 Team 운영 체제를 실행하는 Surface Hub 2S 장치
- Windows 10을 실행하는 장치 분리
- SEMM 패키지를 만들기 위한 Surface UEFI 구성기 도구
- Windows 10 Pro 또는 Enterprise OS 이미지, 버전 1903 이상
- 16GB의 저장소가 있는 USB 드라이브 2개, FAT32 형식
- Surface Hub 2(MSI) 파일의 Windows 10 Pro 및 엔터프라이즈 OS용 Microsoft Windows Installer 및 펌웨어
- 인터넷 연결
- 이미징 솔루션(선택 사항)

 
## 마이그레이션 및 설치 워크플로 요약

| 단계  | 작업                                                                                                 | 요약                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족하는지 확인합니다.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | UEFI 버전이 694.2938.768.0 이상인지 확인                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어를 다운로드합니다.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **IT용 Surface 도구 페이지에서** </a> 다운로드를 **선택합니다.** 그런 다음 **Surface UEFI 구성 프로그램을 선택하고 다운로드합니다. MSI 파일을** 설치하고 별도 PC에 설치합니다. Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 다운로드합니다.</a> 5단계에서 사용하기 위해 저장합니다. |
| 3 | [SEMM 인증서를 준비합니다.](#prepare-the-semm-certificate)                                                                          | Surface UEFI 구성기 실행에 필요한 인증서를 준비합니다. 또는 현재 인증서를 사용 합니다.                                                                                                                                                                                                                                                                                                      |
| 4 | [SEMM 패키지를 생성합니다.](#create-a-semm-package)                                                                               | Surface Hub 2S에서 적용해야 하는 구성 파일이 포함된 USB 드라이브에 SEMM 패키지를 만들 수 있는 Surface UEFI 구성을 시작하십시오. 이러한 SEMM 패키지 파일을 PC의 폴더에 복사합니다.                                                                                                                                                                                          |
| 5 | [Surface Hub 2에서 Windows 10 Pro 및 Enterprise OS용 Windows 10 이미지, SEMM 패키지 및 드라이버 및 펌웨어가 포함된 USB 플래시 드라이브를 준비합니다.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Windows 10 이미지가 포함된 단일 USB 드라이브를 만듭니다. 이 예제에서 드라이브의 이름은 *BOOTME입니다.* Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어(2단계) 및 SEMM 패키지 파일(4단계)을 *BOOTME* 드라이브에 추가합니다.                                                                                                                                                                                                  |
| 6 | [SURFACE Hub 2S에서 UEFI를 업데이트하여 OS 마이그레이션을 사용하도록 합니다.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | *BOOTME* 드라이브를 사용하여 Surface Hub 2S를 UEFI 메뉴로 부팅하고 SEMM 패키지를 설치합니다.|
| 7 | [Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.](#install-windows-10-pro-or-enterprise)                                        | *BOOTME* 드라이브를 사용하여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.                                                                                                                                                                                                                                                                                 |
| 8 | [Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 설치합니다.](#install-surface-hub-2-drivers-and-firmware)                                        | 장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 설치합니다.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Surface Hub 2S를 개인 생산성 장치로 완전히 구성합니다.](#configure-recommended-settings)                                        |  Surface Hub 2S를 개인 생산성 장치로 최적화하려면 권장 설정 및 응용 프로그램을 사용하도록 설정하세요.                                                                                                                                                                                                                                                                    |

### Surface Hub 2S의 UEFI 버전이 최소 요구 사항을 충족하는지 확인

Surface Hub를 Windows 10 Team에서 Windows 10 Desktop으로 마이그레이션하기 전에 *694.2938.768.0*이상인 UEFI 버전이 필요합니다.
 
**시스템에서 UEFI 버전을 확인:**

1. Surface Hub 2S 홈 페이지에서 **Start**시작을 선택한 다음 Surface 앱(모든 앱 Surface)을**니다.**  >  **Surface**

2. Surface를 **선택하여** 디바이스의 현재 UEFI 버전을 포함하여 Surface Hub에 대한 정보를 표시합니다. 
   - UEFI 버전이 *694.2938.768.0* 이상인 경우 다음 이미지와 같이 SEMM 패키지를 만들어 OS 마이그레이션을 사용하도록 설정할 수 있습니다.

       ![Screenshot showing the Your Surface page in the Surface app.](images/shm-fig1.png)
 
   - UEFI 버전이 버전 694.2938.768.0 이전인 경우 Window 10 Team 2020 Update BMR(Update Bare Metal Recovery) 이미지를 설치하거나 Windows 업데이트를 사용하여 현재 버전을 얻어야 합니다.
   
**Windows 업데이트를 통해 UEFI를 업데이트하는 방법:**

1. Surface Hub 2S에서 관리자로 **로그인합니다.** 
    >[!Note]
    > 사용자 이름 또는 관리자 암호를 모르는 경우 장치를 다시 설정해야 합니다. 자세한 내용은 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Surface Hub 2S의 초기화 및 복구를 참조하세요.</a>

1. 모든 앱 **설정**업데이트 및 보안 Windows 업데이트로 이동한 다음 모든  >  **Settings**  >  **Update and Security**  >  **Windows Update**업데이트를 설치합니다. 
1. 디바이스를 다시 시작합니다. 
1. Surface 앱을 사용하여 UEFI 버전을 검증합니다. 
1. 이제 UEFI 버전이 아직 버전 694.2938.768.0 이상이 아닌 경우 위의 단계를 반복하거나 Windows 10 Team 2020 BMR(Update Bare Metal Recovery) 이미지를 설치하여 최신 UEFI를 얻을 수 있습니다.

**BMR(Bare Metal Recovery) 이미지를 통해 UEFI를 업데이트하는 경우:**

1.  Surface 복구 [사이트로 이동하여](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S 선택**
3.  허브 일련 번호를 입력합니다(전원 연결 옆의 허브 뒷면에 위치).
4.  지시에 따라 Windows 10 Team 2020 업데이트를 설치하여 포맷된 USB 드라이브에 이미지를 다운로드합니다.
5.  업데이트가 완료된 후 장치가 OOBE를 처음 설치하면 OOBE를 완료할 필요가 없습니다. UEFI 버전이 업데이트됩니다. 대신 화면이 꺼질 때까지 전원 단추를 눌러 장치를 전원을 니다. 

### Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어 다운로드

별도의 PC에서:

1. <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">IT용 Surface 도구 페이지에서 </a> 다운로드를 **선택합니다.**  
1. Surface UEFI 구성기 MSI 파일을 선택하고 다운로드하여 별도의 PC에 설치합니다. Windows 10 Team 버전이 설치된 동안에는 Surface Hub 2S에서 Surface UEFI 구성기 도구를 실행할 수 없습니다.

1. Surface <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Hub 2 드라이버 및 펌웨어 Windows Installer MSI 파일을 </a> 다운로드합니다. 새 운영 체제를 설치할 때 이 파일을 사용하게 됩니다.

### SEMM 인증서 준비

Surface UEFI 구성기 사용 전에 사용되지 않은 경우 인증서를 준비해야 합니다. 이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지를 사용하여만 UEFI 설정을 수정할 수 있도록 합니다. 

인증서를 사용하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.

- 엔터프라이즈 조직은 일반적으로 표준 보안 관행에 따라 인증서를 생성하기 위해 자체 인프라를 유지 관리합니다.

- 중소기업 및 다른 기업은 파트너 공급자로부터 인증서를 받을 수 있습니다. 이 옵션은 충분한 IT 전문 지식이나 전담 IT 보안 팀이 없는 조직에 권장됩니다.

- 또는 PowerShell 스크립트를 사용하여 자체 서명된 인증서를 생성할 수 있습니다. 자세한 내용은 Surface 엔터프라이즈 관리 모드 인증서 요구 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> 사항을 </a> 참조하세요. 또는 PowerShell을 사용하여 자체 인증서를 만들 수 있습니다. 자세한 내용은 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate 설명서를 </a> 참조하십시오.

Surface UEFI 구성기에서 만드는 SEMM 패키지는 인증서로 보호해야 합니다. 인증서는 UEFI 설정을 적용하기 전에 구성 파일의 서명을 확인합니다. 자세한 내용은 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 설명서를 </a> 참조하십시오.
 
 
### SEMM 패키지 만들기

1. 별도의 PC에서 앞서 다운로드한 Surface UEFI 구성기 도구를 설치합니다. 

2. Surface UEFI 구성기에서 시작을 **선택합니다.**

   ![Surface UEFI 구성기 열기](images/shm-fig2.png)
   
3. **Surface 디바이스를 선택하고**다음을 **선택합니다.**

   ![Surface 디바이스를 선택합니다.](images/shm-fig3.png)
  
4. 구성 **패키지를 선택합니다.**

   ![구성 패키지를 선택합니다.](images/shm-fig4.png)
  
5. 인증서 **보호를 선택합니다.**

   ![인증서 보호를 선택합니다.](images/shm-fig5.png)

   인증서 .pfx 파일을 추가하라는 메시지가 표시됩니다.

   ![인증서를 추가합니다.](images/shm-fig6.png)
   
7. 인증서 암호를 입력하고 확인을 **선택합니다.**

   ![인증서 암호를 입력하고 확인을 선택합니다.](images/shm-fig7.png)

8. Surface **Password Protection** UEFI에 암호를 추가하려면 암호 보호를 선택합니다. UEFI로 부팅할 때마다 이 암호가 필요합니다. Surface *strongly recommend* Hub 2S에서 사용할 UEFI 암호를 설정하는 것이 좋습니다.

   ![암호 보호를 선택합니다.](images/shm-fig8.png)
   
9. UEFI 암호를 설정한 다음 확인을 **선택합니다.**

   > [!IMPORTANT]
   > Surface Hub를 관리하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장합니다. 암호가 손실된 경우 복구할 수 없습니다. 

   ![UEFI 암호를 입력합니다.](images/shm-fig9.png)

10. **Surface Hub 2S를 선택하고**다음을 **선택합니다.**

    ![Surface Hub 2S를 선택합니다.](images/shm-fig10.png)
   
11. **다음**을 선택합니다.

    ![다음을 선택합니다.](images/shm-fig10a.png)

12. Windows 10 Pro 또는 Enterprise 설치를 허용하려면 **EnableOsMigration을**켜고 다음을 **선택합니다.**

    ![O S 마이그레이션 사용을 선택합니다.](images/shm-fig11.png)
    
    ![OS 마이그레이션 사용 설정](images/shm-fig12.png)

### SEMM 등록 관리

SEMM에 장치를 등록하면 디바이스를 관리하는 방법에 영향을 미치게 됩니다. 예를 들어 SEMM 패키지를 적용한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다(잠겨). PXE 부팅용 **IPv6과** 같은 다른 설정의 기본값도 사용할 수 없습니다. 

마이그레이션을 완료한 후 UEFI 설정을 변경하려면 다른 SEMM 패키지를 적용하거나 SEMM에서 디바이스의 인센토를 해지합니다. UEFI 설정을 변경하기 위해 다른 SEMM 패키지를 적용하는 경우 새 SEMM 패키지를 빌드할 때 원본 인증서를 사용해야 합니다. UEFI 구성기 도구를 사용하여 **EnableOSMigration을** 해제합니다(원래 마이그레이션 단계에 표시된 것 아님).

#### 파트너와 작업

회사에서 Surface Hub 2의 Windows 10 Pro 또는 Enterprise로의 마이그레이션을 아웃소싱하는 경우 파트너가 SEMM 인증서, SEMM 패키지 및 UEFI 암호를 전송하게 할 수 있습니다.  또는 허브를 마이그레이션한 후 SEMM에서 즉시 등록을 등록을 해지하면 UEFI의 로컬 관리 및 디바이스를 다른 사용자로 전송할 수 있습니다. 하지만 마이그레이션 후 구성할 수 있는 UEFI 암호를 사용하는 것이 좋습니다. 자세한 내용은 [Surface UEFI 설정 관리를 참조하세요.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Windows 10 Team으로 롤백

마이그레이션 후 아래 설명에 따라 디바이스를 Windows 10 Team으로 복원하도록 선택한 경우 먼저 SEMM에서 허브의 사용을 철회하는 것이 좋습니다. [as described below](#roll-back-to-windows-10-team) 자세한 내용은 [SEMM에서 Surface 디바이스의 사용 안을 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)


#### USB 드라이브에 SEMM 패키지 저장

1. USB 드라이브를 PC에 연결합니다. 
1. 허브 **2S를 선택하고**다음을 **선택합니다.**

   ![USB 선택](images/shm-fig13.png)

   > [!WARNING]
   > SEMM 패키지를 구축하면 USB 드라이브의 모든 기존 데이터가 삭제됩니다. SEMM 패키지를 구축하기 전에 저장할 USB 드라이브에서 파일을 제거합니다.
   
2. 빌드를 **선택합니다.**

   ![빌드를 선택합니다.](images/shm-fig14.png)

3. 이 페이지의 스크린샷을 캡처한 다음 종료를 **선택합니다.** 이제 SEMM 패키지가 준비되었습니다. 여기에는 SEMM 패키지 *DfciUpdate.dfi* 및 SEMM 지문(인증서 지문의 마지막 두 문자)이 포함된 텍스트 파일이 포함됩니다.

   ![끝을 선택합니다.](images/shm-fig15.png)
   
4. 인증서 지문의 마지막 두 문자를 저장합니다. Surface Hub 2S에서 패키지를 적용할 때 SEMM을 활성화하려면 다음 문자가 필요합니다.

### Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어가 포함된 USB 플래시 드라이브 준비

다음 옵션 중 하나를 사용하여 Windows 10 Pro 또는 Enterprise 이미지(버전 1903 이상)를 설치할 수 있습니다.

- 현재 이미징 솔루션입니다.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Surface 배포 </a> 가속기. 이 도구를 사용하여 부팅 가능한 Windows 10 이미지를 만들 수 있습니다. 이미지에는 모든 현재 Windows 10 업데이트, Office, 선택한 기타 앱 및 필요한 드라이버 및 펌웨어가 포함되어 있습니다. 

- Windows 10 Pro 또는 Enterprise 이미지가 포함된 USB 플래시 드라이브입니다. 그런 다음 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 </a> 설치합니다.
 
다음 절차에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가하는 방법에 대해 설명합니다. 다른 배포 방법을 사용하는 경우 Surface [Hub 2S의 업데이트 UEFI로](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 이동하여 이 문서의 OS 마이그레이션 섹션을 사용하도록 설정하십시오.

> [!NOTE]
> 설치를 완료한 후 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대한 유효한 라이선스가 필요합니다.

1. Windows 10 Pro 설치를 만들 경우 Windows 10 다운로드 페이지에서 지침에 따라 미디어 만들기 도구를 <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> </a> 다운로드합니다. Windows 10 Enterprise를 다운로드하려면 Microsoft 볼륨 라이선스 서비스 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> 센터로 이동해야 </a> 합니다.

2. 새 USB 저장소 드라이브를 삽입합니다. 
1. 미디어 만들기 도구를 열고 설치 **미디어 만들기를**선택한 후 다음을 **선택합니다.**

   ![설치 미디어를 만드시다.](images/shm-fig16.png)
   
3. 언어를 선택한 다음 **Windows 10** 및 **64비트(x64)를 선택합니다.** 그런 다음을 **선택합니다.**

   ![언어를 선택하고 Windows 10 및 64비트를 선택합니다. 그런 다음을 선택합니다.](images/shm-fig17.png)
   
4. USB **플래시 드라이브를**선택하고 다음을 **선택합니다.**

   ![U S B 플래시 드라이브를 선택하고 다음을 선택합니다.](images/shm-fig18.png)
   
5. 다운로드가 완료되면 **마쳤습니다.**

   ![완료를 선택합니다.](images/shm-fig19.png)
   
6. Surface Hub 2의 Windows 10 Pro 및 Enterprise OS(MSI 파일)에 대한 SEMM 패키지 파일 및 드라이버 및 펌웨어를 Windows 10 이미지가 포함된 USB 플래시*드라이브(BOOTME)의*루트에 복사합니다. BOOTME USB 드라이브에는 다음이 포함되어 있습니다.

    - Windows 10 부팅 가능 이미지.
    
    - SEMM 패키지 파일(USB 드라이브의 루트에 복사)
    
      - *DfciUpdate.dfi*.
      - SEMM 지문을 포함하는 텍스트 파일입니다. 이 예제에서는 파일이SurfaceUEFI_2020Aug25_1058.txt* .) * 자동으로 생성된 날짜 타임스탬프는 Surface UEFI 구성기에서 파일을 만든 날짜에 해당합니다.

   - Surface Hub 2(Windows 10 Pro 및 Enterprise OS)의 드라이버 및 펌웨어(SurfaceHub2S_Win10_18362_20.082.25682.0.msi. 이 파일을 USB 드라이브의 루트에 복사합니다.

### OS 마이그레이션을 사용하도록 Surface Hub 2S에서 UEFI 업데이트

1. Surface Hub 2S의 USB-A 포트에 BOOTME 드라이브를 삽입합니다. 필수 파일 목록은 이전 섹션을 참조하세요.

2. UEFI로 부팅하는 경우:

   1. Surface Hub 2S를 끄고(종료).
   1. Volume **+ 를 누르고**전원 단추를 누를 수 있습니다.
   1. UEFI **메뉴가 나타날** 때까지 볼륨 + 유지
   
      ![UEFI 메뉴가 나타날 때까지 볼륨 업 단추를 누르고 있습니다.](images/shm-fig20.png)
      
3. 장치를 다시 시작하면 앞에서 만든 UEFI 암호를 입력합니다(해당하는 경우 권장).

   ![UEFI 암호를 입력합니다.](images/shm-fig22.png)
   
4. UEFI 메뉴에서 **USB에서 관리**  >  **설치를 선택합니다.**

   ![관리 및 US B에서 설치를 선택합니다.](images/shm-fig21.png)
   
5. 다음 **이미지와 같이**지금 다시 시작을 선택합니다. 장치가 다시부팅됩니다. 창 중간에 흰색 Microsoft 로고를 표시한 다음 종료합니다.

   ![지금 다시 시작을 선택합니다.](images/shm-fig25.png)
   
6. 전원 단추를 누르고 해제합니다. 빨간색 창이 나타나면 Surface 엔터프라이즈 관리 모드를 활성화합니다. 

7. 2문자 인증서 지문과 UEFI 설정 암호를 입력합니다. 그런 다음 **확인을 선택합니다.**

   ![2문자 인증서 지문과 UEFI 설정 암호를 입력합니다.](images/shm-fig23.png)
 
   > [!NOTE]
   > 장치에서 SEMM을 활성화하면 새 UEFI 설정 **EnableOSMigration이** 적용됩니다. 더 이상 Windows 10 Team에 액세스할 수 없습니다. 대신 다음 단계를 계속하고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치해야 합니다. 

   장치가 다시부팅됩니다. 화면 중간에 흰색 로고를 표시한 다음 다시 종료합니다.

### Windows 10 Pro 또는 Enterprise 설치

1. 부팅 가능한 Windows 10 Pro 또는 Enterprise 드라이브가 Surface Hub 2 USB-A 포트에 아직 없는 경우 지금 삽입합니다. 그런 다음 전원 단추를 누르고 해제합니다. 

    디바이스가 시작되면 화면 중간에 흰색 로고가 표시됩니다. 그런 다음 흰색 로고 아래에 회전하는 원이 표시됩니다.

3. 장치가 자동으로 USB 드라이브로 부팅되지 않는 경우 디바이스를 끄세요(전원 코드를 끄고 다시 연결). 전원 코드를 다시 연결한 후 디바이스가 몇 초 후에 부팅됩니다. 그런 다음 화면 중간에 흰색 로고가 표시됩니다. 

    디바이스가 켜지 않은 경우 전원 단추를 누르고 해제합니다. 화면 중간에 로고가 표시되고 나면 흰색 로고 아래에 회전하는 원이 표시될 때까지 볼륨 단추를 누르고 있습니다.
 
   ![U.S B 드라이브에서 Windows 10으로 부팅합니다.](images/shm-fig26.png)
   
4. OOBE(첫 실행 경험) 설치가 시작되면 지침에 따라 Windows 10 Pro 또는 Enterprise(버전 1903 이상)를 설치합니다.

### Surface Hub 2 드라이버 및 펌웨어 설치

장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 </a> 설치합니다.
 
## 권장 설정 구성

Surface Hub 2S를 개인 생산성 장치로 완전히 구성하려면 <a href="surface-hub-2-post-install.md" target="_blank"> Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성을 </a> 참조하세요.

> [!NOTE]
>이 문서에 설명된 단계가 Surface Hub 2용 Windows 10 Pro 또는 Enterprise로 성공적으로 마이그레이션되지 않는 경우 Surface Hub 지원에 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> </a> 문의하세요.

## Windows 10 Team으로 롤백

디바이스를 Windows 10 Team으로 복원하려면 Surface Hub 2S에 대한 초기화 및 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 복구를 </a> 참조하세요.

> [!NOTE]
> Windows 10 Team으로 롤백하기 전에 SEMM에서 허브를 먼저 사용인증을 해지하는 것이 좋습니다. 자세한 내용은 [SEMM에서 Surface 디바이스의 사용 안을 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## 버전 기록

다음 표에서는 이 문서의 변경 내용을 요약하여 제공합니다.

| 버전 | Date               | 설명                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.3  | 2020년 12월 3일 | SEMM 등록 관리에 대한 지침으로 업데이트되었습니다.                                                        |
| v. 1.2  | 2020년 9월 29일 | 사용 가능성 피드백을 해결 하는 기타 업데이트입니다.                                                        |
| v. 1.1  | 2020년 9월 15일 | 새 OS를 설치하기 위한 라이선스 요구 사항을 명확히 설명하는 추가 참고 사항이 도입되었습니다. |
| v. 1.0  | 2020년 9월 1일  | 새 문서입니다.                                                                                           |
