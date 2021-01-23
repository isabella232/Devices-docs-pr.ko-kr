---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션
description: Surface Hub 2의 Windows 10 Team에서 Windows 10 Pro 또는 Windows 10 Enterprise로 마이그레이션하는 방법
keywords: Surface Hub 데스크톱, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297641"
---
# Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션

- [문서 버전 기록](#version-history)

Surface Hub 2S는 Windows 10 Team이 설치되어 있습니다. 이 사용자 지정된 Windows 10 버전은 회의실 환경에서 공동 작업을 용이하게 합니다. 이제 Windows 10 Pro 또는 Enterprise를 실행하여 다른 PC와 매우 마찬가지로 Surface Hub 2S를 사용할 수 있습니다.

> [!IMPORTANT]
> 이 마이그레이션 프로세스를 수행하려면 이 문서에 설명된 특정 절차를 따라야 합니다. 계속하기 전에 [솔루션](#solution-components) 구성 요소 및 마이그레이션 [및 설치 워크플로를 읽어 보십시오.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Windows 10 Pro 또는 Enterprise를 설치할 때 기존 Windows 10 Team 라이선스와는 별개인 새 라이선스가 필요합니다.

별도의 PC와 다운로드 가능한 Surface UEFI 구성기 도구를 사용하여 Windows *10 Team에서 마이그레이션을* 시작하세요. 이 도구는 Surface Hub 2S에 적용하는 새 UEFI 설정이 포함된 패키지를 만듭니다.  

Surface UEFI 구성기는 Surface SEMM(엔터프라이즈 관리 모드)의 인터페이스로 작동합니다. 회사 환경의 Surface 디바이스에서 펌웨어 설정을 중앙에서 관리합니다. 자세한 내용은 Microsoft Surface 엔터프라이즈 관리 [모드를 참조하세요.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
## 솔루션 구성 요소

- Windows 10 Team을 실행하는 Surface Hub 2S 장치
- Windows 10을 실행하는 장치 분리
- SEMM 패키지를 만들기 위한 Surface UEFI 구성기 도구
- Windows 10 Pro 또는 Enterprise OS 이미지, 버전 1903 이상
- 저장소 용량이 16GB인 USB 드라이브 2개, FAT32 형식
- Surface Hub 2 MSI(Windows 10 Pro 및 Enterprise) Microsoft Windows Installer 드라이버 및 펌웨어
- 인터넷 연결
- 이미징 솔루션(선택 사항)
 
## 마이그레이션 및 설치 워크플로 요약

| 단계  | 작업                                                                                                 | 요약                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Surface Hub 2S에서 UEFI 버전을 검증합니다.](#verify-the-uefi-version-on-surface-hub-2s)                                  | UEFI 버전은 *버전 694.2938.768.0 이상이* 되어야 합니다.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어를 다운로드합니다.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | **[IT용 Surface 도구 페이지에서](https://www.microsoft.com/download/details.aspx?id=46703)** </a> 다운로드를 **선택합니다.** 그런 다음 **Surface UEFI 구성기 MSI**파일을 선택하고 다운로드하여 별도의 PC에 설치합니다. 또한 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 [펌웨어를 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=101974)</a> 5단계에서 사용하기 위해 이 패키지를 저장합니다. |
| 3 | [SEMM 인증서를 준비합니다.](#prepare-the-semm-certificate)                                                                          | Surface UEFI 구성기 실행에 필요한 인증서를 준비하거나 현재 인증서를 사용하십시오.                                                                                                                                                                                                                                                                                                      |
| 4 | [SEMM 패키지를 만들 수 있습니다.](#create-a-semm-package)                                                                               | Surface UEFI 구성을 시작하여 USB 드라이브에 SEMM 패키지를 만들 수 있습니다. 이 패키지에는 Surface Hub 2S에 적용해야 하는 구성 파일이 포함되어 있습니다. 이러한 SEMM 패키지 파일을 PC의 폴더에 복사합니다.                                                                                                                                                                                          |
| 5 | [Windows 10 이미지, SEMM 패키지 및 드라이버와 펌웨어를 사용하여 USB 플래시 드라이브를 로드합니다.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Windows 10 이미지가 포함된 USB 드라이브를 만듭니다. 이 예제에서 드라이브의 이름은 *BOOTME입니다.* Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어(2단계) 및 SEMM 패키지 파일(4단계)을 *BOOTME* 드라이브에 추가합니다.                                                                                                                                                                                                  |
| 6 | [OS 마이그레이션을 사용하도록 Surface Hub 2S의 UEFI를 업데이트합니다.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | *BOOTME* 드라이브를 사용하여 Surface Hub 2S를 UEFI 메뉴로 부팅하고 SEMM 패키지를 설치합니다.|
| 7 | [Windows 10 Pro 또는 Enterprise를 설치합니다.](#install-windows-10-pro-or-enterprise)                                        | *BOOTME* 드라이브를 사용하여 Windows 10 Pro 또는 Enterprise 버전 1903 이상을 설치합니다.                                                                                                                                                                                                                                                                                 |
| 8 | [Windows 10 Pro 및 Enterprise용 드라이버 및 펌웨어를 설치합니다.](#install-surface-hub-2-drivers-and-firmware)                                        | 장치에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 Surface Hub 2 MSI 파일에 Windows 10 Pro 및 Enterprise OS용 드라이버 및 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 펌웨어를 설치합니다.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Surface Hub 2S를 개인 생산성 장치로 구성합니다.](#configure-recommended-settings)                                        |  권장 설정 및 응용 프로그램을 사용하여 Surface Hub 2S를 개인 생산성 장치로 최적화합니다.                                                                                                                                                                                                                                                                    |

### Surface Hub 2S에서 UEFI 버전 확인

Surface Hub를 Windows 10 Team에서 Windows 10 Desktop으로 마이그레이션하기 전에 UEFI 버전 *694.2938.768.0* 이상이 필요합니다.
 
**시스템에서 UEFI 버전을 확인:**

1. Surface Hub 2S 홈 페이지에서 **** 시작을 선택한 다음 Surface 앱(모든 앱 Surface)을**니다.**  >  ****

2. Surface를 **선택하여** 디바이스의 현재 UEFI 버전을 포함하여 Surface Hub에 대한 정보를 표시합니다. 
   - UEFI 버전이 *694.2938.768.0* 이상인 경우 다음 이미지와 같이 SEMM 패키지를 만들어 OS 마이그레이션을 사용하도록 설정할 수 있습니다.

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)
 
   - UEFI 버전이 *버전 694.2938.768.0*이전인 경우 다음 방법 중 하나를 사용하여 최신 버전을 다운로드합니다.
   
#### Windows 업데이트를 통해 UEFI 업데이트

1. Surface Hub 2S에서 관리자로 **로그인합니다.**

    >[!Note]
    > 사용자 이름 또는 관리자 암호를 모르는 경우 장치를 다시 설정해야 합니다. 자세한 내용은 [Surface Hub 2S의 초기화 및 복구를 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)

1. 모든 앱 **설정**업데이트 및 보안 Windows 업데이트로 이동하여 모든  >  ****  >  ****  >  **** 업데이트를 설치합니다.
1. 디바이스를 다시 시작합니다.
1. Surface 앱을 사용하여 UEFI 버전을 검증합니다. UEFI 버전이 *694.2938.768.0* 이상이 아닌 경우 이러한 단계를 반복하거나 다음 절차에 따라 최신 UEFI 버전을 다운로드합니다.

#### BMR(메탈 복구) 이미지를 통해 UEFI 업데이트

1.  Surface 복구 [사이트로 이동하여](https://support.microsoft.com/surfacerecoveryimage) **Surface Hub 2S를 선택합니다.**
3.  허브 일련 번호를 입력합니다. 이 위치는 전원 연결 옆에 있는 허브의 뒷면에 있습니다.
4.  지시에 따라 Windows 10 Team 2020 업데이트를 설치하여 포맷된 USB 드라이브에 이미지를 다운로드합니다.
5.  업데이트 후 장치는 OOBE(첫 실행 경험) 설정으로 들어갈 수 있습니다. 설치를 완료할 필요는 없습니다. UEFI 버전이 이미 업데이트되었습니다. 대신 화면이 꺼질 때까지 전원 단추를 눌러 장치를 전원을 니다.

### Surface UEFI 구성기 및 Surface Hub 2 드라이버 및 펌웨어 다운로드

별도의 PC에서 다음 단계를 수행합니다.

1. <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">IT용 Surface 도구 페이지에서 </a> 다운로드를 **선택합니다.**  
1. Surface UEFI 구성기 MSI 파일을 선택하고 다운로드하여 별도의 PC에 설치합니다. Windows 10 Team 버전이 설치된 동안 Surface Hub 2S에서는 Surface UEFI 구성기 도구를 실행할 수 없습니다.

1. Surface [Hub 2 드라이버 및 펌웨어 Windows Installer MSI 파일을 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=101974) 새 운영 체제를 설치할 때 이 파일을 사용하게 됩니다.

### SEMM 인증서 준비

Surface UEFI 구성기 사용 전에 사용되지 않은 경우 인증서를 준비해야 합니다. 이 인증서를 사용하면 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지만 사용하여 UEFI 설정을 수정할 수 있습니다.

인증서를 사용하는 방법은 조직의 규모 또는 복잡도에 따라 다를 수 있습니다.

- 엔터프라이즈 조직은 일반적으로 표준 보안 관행에 따라 인증서를 생성하기 위해 자체 인프라를 유지 관리합니다.

- 중소기업 및 다른 기업은 파트너 공급자로부터 인증서를 받을 수 있는 경우가 종종 있습니다. 이 옵션은 IT 전문 지식이 부족하거나 전담 IT 보안 팀이 없는 조직에 권장됩니다.

- 또는 PowerShell 스크립트를 사용하여 자체 서명된 인증서를 생성할 수 있습니다. 자세한 내용은 Surface 엔터프라이즈 관리 모드 인증서 요구 [사항을 참조하세요.](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) 또는 PowerShell을 사용하여 자체 인증서를 만들 수 있습니다. 자세한 내용은 [New-SelfSignedCertificate 설명서를](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 참조하십시오.

Surface UEFI 구성기에서 만드는 SEMM 패키지는 인증서로 보호해야 합니다. 인증서는 UEFI 설정을 적용하기 전에 구성 파일의 서명을 확인합니다. 자세한 내용은 [SEMM 설명서를 참조하십시오.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
### SEMM 패키지 만들기

1. 별도의 PC에서 앞서 다운로드한 Surface UEFI 구성기 도구를 설치합니다.

1. Surface UEFI 구성기에서 시작을 **선택합니다.**

   ![Surface UEFI 구성기 시작 화면입니다.](images/shm-fig2.png)
   
1. **Surface 디바이스를 선택하고**다음을 **선택합니다.**

   ![Screenshot shows the Surface Devices option selected.](images/shm-fig3.png)
  
1. 구성 **패키지를 선택합니다.**

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. 인증서 **보호를 선택합니다.**

   ![스크린샷은 "인증서 보호 선택"을 선택하는 것입니다.](images/shm-fig5.png)

   인증서 .pfx 파일을 추가하라는 메시지가 표시됩니다.

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)
   
1. 인증서 암호를 입력하고 확인을 **선택합니다.**

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. 암호 **보호를 선택하여** Surface UEFI에 암호를 추가합니다. UEFI로 부팅할 때마다 이 암호가 필요합니다. *Surface Hub 2S에서 사용할 UEFI 암호를 설정하는 것이 좋습니다.*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)
   
1. UEFI 암호를 설정한 다음 확인을 **선택합니다.**

   > [!IMPORTANT]
   > Surface Hub를 관리하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장합니다. *이 암호가 손실된 경우 복구할 수 없습니다.*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. **Surface Hub 2S를 선택하고**다음을 **선택합니다.**

    ![Screenshot shows where to select Surface Hub 2S.](images/shm-fig10.png)
   
1. 다음을 **다시** 선택합니다.

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. Windows 10 Pro 또는 Enterprise 설치를 허용하려면 **EnableOsMigration을**켜고 다음을 **선택합니다.**

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![SCREENSHOT shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### SEMM 등록 관리

SEMM에 장치를 등록하면 디바이스를 관리하는 방법에 영향을 미치게 됩니다. 예를 들어 SEMM 패키지를 적용한 후 장치의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다(잠겨). PXE 부팅용 **IPv6과** 같은 다른 설정의 기본값도 사용할 수 없습니다.

마이그레이션을 완료한 후 UEFI 설정을 변경하려면 다른 SEMM 패키지를 적용하거나 SEMM에서 디바이스의 인센토를 해지합니다. UEFI 설정을 변경하기 위해 다른 SEMM 패키지를 적용하는 경우 새 SEMM 패키지를 빌드할 때 원본 인증서를 사용해야 합니다. UEFI 구성기 도구를 사용하여 **EnableOSMigration을** ** ** 해제합니다(원래 마이그레이션 단계와는 다름).

#### 파트너와 작업하는 경우

회사에서 Surface Hub 2 마이그레이션을 Windows 10 Pro 또는 Enterprise로 아웃소싱하는 경우 파트너가 SEMM 인증서, SEMM 패키지 및 UEFI 암호를 전송하게 할 수 있습니다. 또는 허브를 마이그레이션한 후 SEMM에서 즉시 이 허브의 인스루를 해지할 수 있습니다. 이 단계를 통해 UEFI의 로컬 관리와 디바이스를 다른 사용자로 전송할 수 있습니다. 하지만 마이그레이션 후 구성할 수 있는 UEFI 암호를 사용하는 것이 좋습니다. 자세한 내용은 [Surface UEFI 설정 관리를 참조하세요.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Windows 10 Team으로 롤백

이 문서 나중에 설명하는 마이그레이션 후 장치를 [](#to-roll-back-to-windows-10-team)Windows 10 Team으로 복원하도록 선택하는 경우 먼저 SEMM에서 허브의 선택을 해지하는 것이 좋습니다. 자세한 내용은 SEMM에서 Surface 장치 사용 안 [끄기를 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

#### USB 드라이브에 SEMM 패키지 저장

1. USB 드라이브를 PC에 연결합니다.
1. 허브 **2S를 선택하고**다음을 **선택합니다.**

   ![Screenshot shows where to select Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > SEMM 패키지를 구축하면 USB 드라이브의 모든 기존 데이터가 삭제됩니다. SEMM 패키지를 빌드하기 전에 USB 드라이브에서 필요한 파일을 제거합니다.
   
1. 빌드를 **선택합니다.**

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. 이 페이지의 스크린샷을 캡처한 다음 종료를 **선택합니다.** 이제 SEMM 패키지가 준비되었습니다. 여기에는 SEMM 패키지 *DfciUpdate.dfi와* 인증서 지문의 마지막 두 문자인 *SEMM*지문이 포함된 텍스트 파일이 포함됩니다.

   ![Screenshot shows where to select End.](images/shm-fig15.png)
   
4. 인증서 지문의 마지막 두 문자를 저장합니다. Surface Hub 2S에서 패키지를 적용할 때 SEMM을 활성화하려면 다음 문자가 필요합니다.

### Windows 10 이미지, SEMM 패키지 및 Surface Hub 2 드라이버 및 펌웨어를 사용하여 USB 플래시 드라이브 로드

다음 옵션 중 하나를 사용하여 Windows 10 Pro 또는 Enterprise 이미지(버전 *1903 이상)를* 설치할 수 있습니다.

- 현재 이미징 솔루션입니다.

- [Surface 배포 가속기.](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 이 도구를 사용하여 부팅 가능한 Windows 10 이미지를 만들 수 있습니다. 이미지에는 모든 현재 Windows 10 업데이트, 업데이트, Microsoft Office 앱 및 필요한 드라이버 및 펌웨어가 포함되어 있습니다.

- Windows 10 Pro 또는 Enterprise 이미지가 포함된 USB 플래시 드라이브입니다. 그런 다음 Surface Hub [2에 Windows 10 Pro 및 Enterprise용 드라이버](https://www.microsoft.com/download/details.aspx?id=101974) 및 펌웨어를 설치합니다.
 
다음 단계에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 SEMM 패키지 파일과 드라이버 및 펌웨어를 추가하는 방법을 보여줍니다. 다른 배포 방법을 사용하는 경우 [Surface Hub 2S의 업데이트 UEFI로](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 이동하여 이 문서의 OS 마이그레이션 섹션을 사용하도록 설정하십시오.

> [!NOTE]
> 설치를 완료한 후 기존 Windows 10 Team 라이선스와는 별개인 Windows 10 Pro 또는 Windows 10 Enterprise에 대한 유효한 라이선스가 필요합니다.

1. Windows 10 Pro 설치를 만들하려면 지침에 따라 Windows 10 다운로드에서 미디어 만들기 [도구를 다운로드합니다.](https://www.microsoft.com/software-download/windows10) Windows 10 Enterprise를 다운로드하려면 Microsoft 볼륨 라이선스 서비스 [센터로 이동해야 합니다.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

1. 새 USB 저장소 드라이브를 삽입합니다.
1. 미디어 만들기 도구를 열고 설치 **미디어 만들기를**선택한 후 다음을 **선택합니다.**

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)
   
3. 언어를 선택한 다음 **Windows 10** 및 **64비트(x64)를 선택합니다.** 그런 다음을 **선택합니다.**

   ![Screenshot shows where you select the language, O S edition, and architecture type.](images/shm-fig17.png)
   
4. **USB 플래시 드라이브를**선택하고 다음을 **선택합니다.**

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)
   
5. 다운로드가 완료되면 **마쳤습니다.**

   ![화면에서는 U S B 드라이브가 준비되어 완료 단추가 포함되어 있는 것으로 보고합니다.](images/shm-fig19.png)
   
6. Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어와 SEMM 패키지 파일을 Windows 10 이미지가 포함된 USB 플래시*드라이브(BOOTME)의*루트에 복사합니다. BOOTME USB 드라이브에는 다음이 포함되어 있습니다.

    - Windows 10 부팅 가능 이미지.
    
    - USB 드라이브의 루트에 복사된 SEMM 패키지 파일:
    
      - *DfciUpdate.dfi*.
      - SEMM 지문을 포함하는 텍스트 파일입니다. 이 예제에서는 파일이SurfaceUEFI_2020Aug25_1058.txt* .) * 자동으로 생성된 날짜-시간 스탬프는 Surface UEFI 구성기에서 파일을 만든 날짜에 해당합니다.

   - Surface Hub 2(Windows 10 Pro 및 Enterprise OS)의 드라이버 및 펌웨어(SurfaceHub2S_Win10_18362_20.082.25682.0.msi. 이 파일을 USB 드라이브의 루트에 복사합니다.

### OS 마이그레이션을 사용하도록 Surface Hub 2S에서 UEFI 업데이트

1. SURFACE Hub 2S의 USB-A 포트에 BOOTME 드라이브를 삽입합니다. 필요한 콘텐츠 목록은 이전 섹션을 참조하세요.

1. UEFI로 부팅하는 경우:

   1. Surface Hub 2S를 끄고(종료).
   1. Volume **+ 를 누르고**전원 단추를 누를 수 있습니다. UEFI **메뉴가 나타날** 때까지 볼륨 + 유지
   
      ![그리기에는 볼륨 및 전원 단추가 표시됩니다.](images/shm-fig20.png)
      
3. 장치가 다시 시작되면 앞에서 만든 UEFI 암호를 입력합니다(해당되는 경우).

   ![시스템 암호 화면](images/shm-fig22.png)
   
4. UEFI 메뉴에서 관리를 **선택합니다.** 그런 다음 **USB에서 설치를 선택합니다.**

   ![Screenshot shows where to select Management and then Install from U S B".](images/shm-fig21.png)
   
5. 다음 **이미지와 같이**지금 다시 시작을 선택합니다. 장치가 다시 시작됩니다. 창 중간에 흰색 Microsoft 로고가 표시된 다음 종료됩니다.

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. 전원 단추를 누르고 해제합니다. 빨간색 대화 상자가 나타나면 Surface 엔터프라이즈 관리 모드를 활성화할지 선택합니다.

7. 2문자 인증서 지문과 UEFI 설정 암호를 입력합니다. 그런 다음 **확인을 선택합니다.**

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > 장치에서 SEMM을 활성화하면 새 UEFI 설정 **EnableOSMigration이** 적용됩니다. 더 이상 Windows 10 Team에 액세스할 수 없습니다. 대신 다음 단계를 계속하고 Windows 10 Pro 또는 Windows 10 Enterprise를 설치해야 합니다.

   장치가 다시부팅됩니다. 화면 중간에 흰색 로고를 표시한 다음 다시 종료합니다.

### Windows 10 Pro 또는 Enterprise 설치

1. 부팅 가능한 Windows 10 Pro 또는 Enterprise 드라이브가 Surface Hub 2 USB-A 포트에 아직 없는 경우 지금 삽입합니다. 그런 다음 전원 단추를 누르고 해제합니다.

    디바이스가 시작되면 화면 중간에 흰색 로고가 표시됩니다. 그런 다음 회전하는 원이 흰색 로고 아래에 나타납니다.

3. Surface 디바이스가 USB 드라이브로 자동으로 부팅되지 않는 경우 디바이스를 끄십시오(전원 코드를 끄고 다시 연결). 전원 코드를 다시 연결한 후 디바이스가 몇 초 후에 부팅됩니다. 그런 다음 화면 중간에 흰색 로고가 표시됩니다.

    디바이스가 켜지 않은 경우 전원 단추를 누르고 해제합니다. 화면 중간에 로고가 표시될 때 흰색 로고 아래에 회전하는 원이 표시될 때까지 볼륨 단추를 누르고 있습니다.
 
   ![볼륨 및 전원 단추의 그림입니다.](images/shm-fig26.png)
   
4. OOBE(첫 실행 경험) 설치가 시작되면 지침에 따라 Windows 10 Pro 또는 Enterprise(버전 1903 이상)를 설치합니다.

### Surface Hub 2 드라이버 및 펌웨어 설치

Surface Hub 2가 최신 버전이 되도록 [Windows 10 Pro](https://www.microsoft.com/download/details.aspx?id=101974)및 Enterprise용 드라이버 및 펌웨어를 설치합니다. 그런 다음 장치를 다시 부트합니다. Surface를 한 시간 동안 켜진 후 다시 다시 시작하십시오. 두 번째 다시 시작하라는 메시지가 표시되지 않습니다. 이 일시 중지 및 추가 재부팅을 통해 펌웨어가 완전히 업데이트됩니다.
 
## 권장 설정 구성

Surface Hub 2S를 개인 생산성 장치로 구성하려면 [Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성을 참조하세요.](surface-hub-2-post-install.md)

> [!NOTE]
>이 문서에 설명된 단계에 따라 디바이스를 Windows 10 Pro 또는 Enterprise for Surface Hub 2로 성공적으로 마이그레이션할 수 없는 경우 Surface Hub 지원에 [문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Windows 10 Team으로 롤백

디바이스를 Windows 10 Team으로 복원하려면 [Surface Hub 2S에](surface-hub-2s-recover-reset.md)대한 초기화 및 복구를 참조하세요.

> [!NOTE]
> Windows 10 Team으로 롤백하기 전에 먼저 SEMM에서 Surface Hub를 열지 않는 것이 좋습니다. 자세한 내용은 SEMM에서 Surface 장치 사용 안 [끄기를 참조합니다.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## 버전 기록

다음 표에서는 이 문서의 변경 내용을 요약하여 제공합니다.

| 버전 | Date               | 설명                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 2020년 12월 14일 | "Surface Hub 2에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어"에 대한 MSI 파일을 설치하는 방법과 관련한 추가 정보를 제공합니다. 시스템의 상태에 따라 두 번째 재부팅이 필요할 수 있습니다. [](#install-surface-hub-2-drivers-and-firmware)                                                          |
| v. 1.3  | 2020년 12월 3일 | SEMM 등록 관리에 대한 [지침으로 업데이트되었습니다.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 2020년 9월 29일 | 사용 가능성 피드백을 해결 하는 기타 업데이트입니다.                                                        |
| v. 1.1  | 2020년 9월 15일 | 새 OS를 설치하기 위한 라이선스 요구 사항을 명확히 설명하는 추가 참고 사항을 소개했습니다. |
| v. 1.0  | 2020년 9월 1일  | 새 문서입니다.                                                                                           |
