---
title: Windows 10/11 Pro 마이그레이션하거나 Surface Hub 2에서 Enterprise
description: Surface Hub 2의 Windows 10 Team Windows 10 Pro 또는 Windows 10 Enterprise 마이그레이션하는 방법입니다.
keywords: Surface Hub Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 7b221b6f8b4a7753a10dd974da47ce58af41d006
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497761"
---
# <a name="migrate-to-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>Windows 10/11 Pro 마이그레이션하거나 Surface Hub 2에서 Enterprise

- [아티클 버전 기록](#version-history)

Surface Hub 2S에는 Windows 10 Team 설치되어 있습니다. 이 사용자 지정된 버전의 Windows 10 회의실 환경에서 공동 작업을 용이하게 합니다. 이제 Windows 10/11 Pro 실행하거나 Enterprise 다른 PC와 마찬가지로 Surface Hub 2S를 사용할 수 있습니다.

> [!IMPORTANT]
> 이 마이그레이션 프로세스를 수행하려면 이 문서에 설명된 특정 절차를 따라야 합니다. 계속하기 전에 [솔루션 구성 요소와](#solution-components) [마이그레이션 및 설치 워크플로](#migration-and-installation-workflow-summary)를 읽습니다.

> [!NOTE]
> Surface Hub 2S에 Windows 10/11 Pro 또는 Enterprise 설치하는 경우 디바이스와 함께 제공되는 기존 Windows 10 Team 라이선스와 다른 새 라이선스가 필요합니다.

별도의 PC 및 다운로드 가능한 *Surface UEFI 구성기* 도구를 사용하여 Windows 10 Team 마이그레이션을 시작합니다. 이 도구는 Surface Hub 2S에 적용하는 새 UEFI 설정이 포함된 패키지를 만듭니다.  

Surface UEFI 구성기는 SURFACE ENTERPRISE 관리 모드(SEMM)에 대한 인터페이스로 작동합니다. 회사 환경의 Surface 디바이스에서 펌웨어 설정을 중앙 집중식으로 관리할 수 있습니다. 자세한 내용은 [Microsoft Surface Enterprise 관리 모드](/surface/surface-enterprise-management-mode)를 참조하세요.

## <a name="solution-components"></a>솔루션 구성 요소

- Windows 10 Team 실행 중인 Surface Hub 2S 디바이스
- Windows 10 실행하는 별도의 디바이스
- SEMM 패키지를 만드는 Surface UEFI 구성기 도구
- Windows 10/11 Pro 또는 Enterprise OS 이미지, 버전 20H2 이상
- 16GB 스토리지, FAT32 형식의 USB 드라이브 2개
- Surface Hub 2 Microsoft Windows Installer(MSI) 파일의 Windows 10 Pro 및 Enterprise 드라이버 및 펌웨어
- 인터넷 연결
- 이미징 솔루션(선택 사항)

## <a name="migration-and-installation-workflow-summary"></a>마이그레이션 및 설치 워크플로 요약

| 단계  | 작업                                                                                                 | 요약                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Surface Hub 2S에서 UEFI 버전을 확인합니다](#verify-the-uefi-version-on-surface-hub-2s).                                  | UEFI 버전은 *버전 694.2938.768.0* 이상이어야 합니다.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Surface UEFI 구성기 및 Surface Hub 2개 드라이버 및 펌웨어를 다운로드합니다.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | **[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703)** 페이지에서</a> **다운로드**를 선택합니다. 그런 다음 **Surface UEFI 구성기 MSI 파일을** 선택하고 다운로드한 다음 별도의 PC에 설치합니다. 또한 [Surface Hub 2 MSI 파일에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 다운로드합니다.</a> 5단계에서 사용할 이 패키지를 저장합니다. |
| 3 | [SEMM 인증서를 준비합니다.](#prepare-the-semm-certificate)                                                                          | Surface UEFI 구성기를 실행하거나 현재 인증서를 사용하는 데 필요한 인증서를 준비합니다.                                                                                                                                                                                                                                                                                                      |
| 4 | [SEMM 패키지를 만듭니다.](#create-a-semm-package)                                                                               | Surface UEFI 구성기를 시작하여 USB 드라이브에 SEMM 패키지를 만듭니다. 이 패키지에는 Surface Hub 2S에 적용해야 하는 구성 파일이 포함됩니다. 이러한 SEMM 패키지 파일을 PC의 폴더에 복사합니다.                                                                                                                                                                                          |
| 5 | [Windows 10 이미지, SEMM 패키지, 드라이버 및 펌웨어를 사용하여 USB 플래시 드라이브를 로드합니다.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Windows 10 이미지를 포함하는 USB 드라이브를 만듭니다. 이 예제에서 드라이브의 이름은 *BOOTME*입니다. Surface Hub 2단계에서 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어를 추가하고 SEMM 패키지 파일(4단계부터)을 *BOOTME* 드라이브에 추가합니다.                                                                                                                                                                                                  |
| 6 | [OS 마이그레이션을 사용하도록 설정하려면 Surface Hub 2S에서 UEFI를 업데이트합니다.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | *BOOTME* 드라이브를 사용하여 Surface Hub 2S를 UEFI 메뉴로 부팅하고 SEMM 패키지를 설치합니다.|
| 7 | [Windows 10 Pro 설치하거나 Enterprise.](#install-windows-1011-pro-or-enterprise)                                        | *BOOTME* 드라이브를 사용하여 Windows 10 Pro 또는 Enterprise 버전 *20H2* 이상을 설치합니다.                                                                                                                                                                                                                                                                                 |
| 8 | [Windows 10 Pro 및 Enterprise 위한 드라이버 및 펌웨어를 설치합니다.](#install-surface-hub-2-drivers-and-firmware)                                        | 디바이스에 모든 최신 업데이트 및 드라이버가 있는지 확인하려면 Windows 10 Pro용 드라이버 및 펌웨어를 설치<a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">하고 SURFACE HUB 2개의 MSI 파일에 OS를 Enterprise.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Surface Hub 2S를 개인 생산성 디바이스로 구성합니다.](#configure-recommended-settings)                                        |  권장 설정 및 애플리케이션을 사용하도록 설정하여 개인 생산성 디바이스로 Surface Hub 2S를 최적화합니다.                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>Surface Hub 2S에서 UEFI 버전 확인

Windows 10 Team Windows 10 Desktop으로 Surface Hub 마이그레이션하기 전에 UEFI 버전 *694.2938.768.0* 이상이 필요합니다.

**시스템에서 UEFI 버전을 확인하려면 다음을 수행합니다.**

1. Surface Hub 2S 홈페이지에서 **시작을** 선택한 다음 Surface 앱(**All** **AppsSurface** > )을 엽니다.

2. **Surface를** 선택하여 디바이스의 현재 UEFI 버전을 포함하여 Surface Hub 대한 정보를 표시합니다.
   - UEFI 버전이 *694.2938.768.0* 이상인 경우 다음 이미지와 같이 SEMM 패키지를 만들어 OS 마이그레이션을 사용하도록 설정할 수 있습니다.

    ![스크린샷은 Surface 앱의 "Surface" 페이지를 보여줍니다.](images/shm-fig1.png)

   - UEFI 버전이 *버전 694.2938.768.0*보다 이전인 경우 다음 방법 중 하나를 사용하여 최신 버전을 가져옵니다.

#### <a name="update-uefi-via-windows-update"></a>Windows 업데이트 통해 UEFI 업데이트

1. Surface Hub 2S에서 **관리자**로 로그인합니다.

    >[!Note]
    > 사용자 이름 또는 관리자 암호를 모르는 경우 디바이스를 다시 설정해야 합니다. 자세한 내용은 [Surface Hub 2S에 대한 다시 설정 및 복구](/surface-hub/surface-hub-2s-recover-reset)를 참조하세요.

1. **모든 앱** > **설정** > **업데이트 및 보안** > **Windows 업데이트**으로 이동하여 모든 업데이트를 설치합니다.
1. 디바이스를 다시 시작합니다.
1. Surface 앱을 사용하여 UEFI 버전을 확인합니다. UEFI 버전이 *694.2938.768.0* 이상이 아닌 경우 다음 단계를 반복하거나 다음 절차를 사용하여 최신 UEFI 버전을 가져옵니다.

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>BMR(완전 복구) 이미지를 통해 UEFI 업데이트

1. [Surface 복구 사이트](https://support.microsoft.com/surfacerecoveryimage)로 이동하여 **Surface Hub 2S**를 선택합니다.
3. 허브 일련 번호를 입력합니다. 전원 연결 옆에 있는 허브의 뒷면에 있습니다.
4. 지침에 따라 Windows 10 Team 2020 업데이트를 설치하여 포맷된 USB 드라이브에 이미지를 다운로드합니다.
5. 업데이트 후 디바이스는 OOBE(기본 제공 환경) 설정에 들어갑니다. 설치를 완료할 필요가 없습니다. UEFI 버전이 이미 업데이트되었습니다. 대신 화면이 꺼될 때까지 전원 단추를 눌러 디바이스의 전원을 끕니다.

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>Surface UEFI 구성기 및 Surface Hub 2개 드라이버 및 펌웨어 다운로드

별도의 PC에서 다음 단계를 수행합니다.

1. <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> IT용 Surface 도구 페이지에서</a> **다운로드**를 선택합니다.  
1. Surface UEFI 구성기 MSI 파일을 선택하고 다운로드한 후 별도의 PC에 설치합니다. Surface UEFI 구성기 도구는 Windows 10 Team 버전이 설치된 동안 Surface Hub 2S에서 실행할 수 없습니다.

1. [Surface Hub 2개 드라이버 및 펌웨어 Windows 설치 관리자 MSI 파일을 다운로드](https://www.microsoft.com/download/details.aspx?id=101974)합니다. 새 운영 체제를 설치할 때 이 파일을 사용합니다.

### <a name="prepare-the-semm-certificate"></a>SEMM 인증서 준비

이전에 Surface UEFI 구성기를 사용하지 않은 경우 인증서를 준비해야 합니다. 이 인증서는 디바이스가 SEMM에 등록된 후에 승인된 인증서로 만든 패키지를 사용하여 UEFI 설정을 수정할 수 있도록 합니다.

인증서를 가져오는 방법은 조직의 크기 또는 복잡성에 따라 달라집니다.

- Enterprise 조직은 일반적으로 표준 보안 관행에 따라 인증서를 생성하기 위해 자체 인프라를 유지 관리합니다.

- 중간 규모 기업 및 기타 기업은 종종 파트너 공급자로부터 인증서를 받기로 선택합니다. 이 옵션은 IT 전문 지식이 많지 않거나 전담 IT 보안 팀이 없는 조직에 권장됩니다.

- 또는 PowerShell 스크립트를 사용하여 자체 서명된 인증서를 생성할 수 있습니다. 자세한 내용은 [Surface Enterprise 관리 모드 인증서 요구 사항을 참조하세요](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). 또는 PowerShell을 사용하여 고유한 인증서를 만들 수 있습니다. 자세한 내용은 [자체 서명된 인증서](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) 설명서를 참조하세요.

Surface UEFI Configurator가 만드는 SEMM 패키지는 인증서로 보호되어야 합니다. 인증서는 UEFI 설정을 적용하기 전에 구성 파일의 서명을 확인합니다. 자세한 내용은 [SEMM](/surface/surface-enterprise-management-mode) 설명서를 참조하세요.

### <a name="create-a-semm-package"></a>SEMM 패키지 만들기

1. 별도의 PC에서 이전에 다운로드한 Surface UEFI 구성기 도구를 설치합니다.

1. Surface UEFI 구성기를 열고 **시작을** 선택합니다.

   ![Surface UEFI 구성기 시작 화면](images/shm-fig2.png)

1. **Surface 디바이스****를 선택한 다음** 다음을 선택합니다.

   ![스크린샷은 선택된 Surface Devices 옵션을 보여줍니다.](images/shm-fig3.png)
  
1. **구성 패키지를** 선택합니다.

   ![스크린샷은 선택된 "구성 패키지 선택"을 보여줍니다.](images/shm-fig4.png)
  
1. **인증서 보호를** 선택합니다.

   ![스크린샷은 "인증서 보호 선택"을 선택하는 것이었습니다.](images/shm-fig5.png)

   인증서 .pfx 파일을 추가하라는 메시지가 표시됩니다.

   ![스크린샷은 인증서 파일을 추가할 위치를 보여줍니다.](images/shm-fig6.png)

1. 인증서 암호를 입력한 다음 **확인을** 선택합니다.

   ![스크린샷은 인증서 암호를 입력하고 확인하는 필드를 보여줍니다.](images/shm-fig7.png)

1. **암호 보호를** 선택하여 Surface UEFI에 암호를 추가합니다. UEFI로 부팅할 때마다 이 암호가 필요합니다. *Surface Hub 2S에서 사용할 UEFI 암호를 설정하는 것이 좋습니다.*

   ![스크린샷은 암호 보호를 선택할 위치를 보여줍니다.](images/shm-fig8.png)

1. UEFI 암호를 설정한 다음 **확인을** 선택합니다.

   > [!IMPORTANT]
   > Surface Hub 관리하는 IT 관리자가 액세스할 수 있는 안전한 위치에 암호를 저장합니다. *이 암호가 손실되면 복구할 수 없습니다.*

   ![스크린샷은 UEFI 암호를 설정하는 위치를 보여줍니다.](images/shm-fig9.png)

1. **Surface Hub 2S**를 선택한 다음, **다음**을 선택합니다.

    ![스크린샷은 Surface Hub 2S를 선택할 위치를 보여줍니다.](images/shm-fig10.png)

1. **다음을** 다시 선택합니다.

    ![스크린샷은 "구성 요소 선택" 아래에서 다음을 선택하는 방법을 보여줍니다.](images/shm-fig10a.png)

1. Windows 10/11 Pro 또는 Enterprise 설치할 수 있도록 하려면 **EnableOsMigration**을 켜고 **다음**을 선택합니다.

    ![스크린샷은 O S 마이그레이션 사용을 선택할 위치를 보여 줍니다.](images/shm-fig11.png)

    ![스크린샷은 OS 마이그레이션을 사용하도록 설정하는 위치를 보여줍니다.](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>SEMM 등록 관리

SEMM에 디바이스를 등록하면 디바이스를 관리하는 방법에 영향을 줍니다. 예를 들어 SEMM 패키지를 적용한 후에는 디바이스의 UEFI 메뉴에서 모든 UEFI 설정을 사용할 수 없습니다(잠김). **PXE 부팅용 IPv6**과 같은 다른 설정의 기본값도 사용할 수 없습니다.

마이그레이션을 완료한 후 UEFI 설정을 변경하려면 다른 SEMM 패키지를 적용하거나 SEMM에서 디바이스 등록을 취소합니다. 다른 SEMM 패키지를 적용하여 UEFI 설정을 변경하는 경우 새 SEMM 패키지를 빌드할 때 원래 인증서를 사용해야 합니다. UEFI 구성기 도구를 사용하고 **EnableOSMigration***을 해제*합니다(원래 마이그레이션 단계에서와 같이 *켜*지지 않음).

#### <a name="if-you-work-with-partners"></a>파트너와 함께 작업하는 경우

회사에서 Windows 10/11 Pro 또는 Enterprise Surface Hub 2 마이그레이션을 아웃소싱하는 경우 파트너가 SEMM 인증서, SEMM 패키지 및 UEFI 암호를 사용자에게 전송하도록 할 수 있습니다. 또는 허브를 마이그레이션한 후 SEMM에서 즉시 등록을 취소할 수 있습니다. 이 단계를 통해 UEFI를 로컬로 관리하고 디바이스를 다른 당사자에게 전송할 수 있습니다. 그러나 마이그레이션 후에 구성할 수 있는 UEFI 암호를 사용하는 것이 좋습니다. 자세한 내용은 [Surface UEFI 설정 관리를 참조하세요](/surface/manage-surface-uefi-settings).

#### <a name="to-roll-back-to-windows-10-team"></a>Windows 10 Team 롤백하려면

[이 문서의 뒷부분에 설명된 대로](#to-roll-back-to-windows-10-team) 마이그레이션 후 Windows 10 Team 디바이스를 복원하도록 선택하는 경우 먼저 SEMM에서 허브 등록을 취소하는 것이 좋습니다. 자세한 내용은 [SEMM에서 Surface 디바이스 등록 취소](/surface/unenroll-surface-devices-from-semm)를 참조하세요.

>[!WARNING]
>SEMM에서 디바이스 등록을 취소하고 Surface UEFI 설정의 사용자 제어를 복원하려면 SEMM에 디바이스를 등록하는 데 사용된 SEMM 인증서가 있어야 합니다. 이 인증서가 손실되거나 손상되면 SEMM에서 등록을 취소할 수 없습니다. 그에 따라 SEMM 인증서를 백업하고 보호합니다.

#### <a name="save-the-semm-package-to-a-usb-drive"></a>USB 드라이브에 SEMM 패키지 저장

1. USB 드라이브를 PC에 커넥트.
1. **허브 2S**를 선택한 다음, **다음**을 선택합니다.

   ![스크린샷은 허브 2S를 선택할 위치를 보여줍니다.](images/shm-fig13.png)

   > [!WARNING]
   > SEMM 패키지가 빌드되면 USB 드라이브의 모든 기존 데이터가 지워집니다. SEMM 패키지를 빌드하기 전에 USB 드라이브에서 필요한 파일을 제거합니다.

1. **빌드**를 선택합니다.

   ![스크린샷은 빌드를 선택할 위치를 보여줍니다.](images/shm-fig14.png)

1. 이 페이지의 스크린샷을 캡처한 다음 **종료**를 선택합니다. 이제 SEMM 패키지가 준비되었습니다. 여기에는 SEMM 패키지 *DfciUpdate.dfi* 와 인증서 지문의 마지막 두 문자인 SEMM *지문*이 포함된 텍스트 파일이 포함되어 있습니다.

   ![스크린샷은 끝을 선택할 위치를 보여줍니다.](images/shm-fig15.png)

4. 인증서 지문의 마지막 두 문자를 저장합니다. Surface Hub 2S에서 패키지를 적용할 때 SEMM을 활성화하려면 이러한 문자가 필요합니다.

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>Windows 10 이미지, SEMM 패키지 및 Surface Hub 2개 드라이버 및 펌웨어를 사용하여 USB 플래시 드라이브 로드

다음 옵션 중 하나를 사용하여 Windows 10/11 Pro 또는 Enterprise 이미지(버전 *20H2* 이상)를 설치할 수 있습니다.

- 현재 이미징 솔루션입니다.

- [Surface 배포 가속기](/surface/microsoft-surface-deployment-accelerator). 이 도구를 사용하여 부팅 가능한 Windows 10 이미지를 만듭니다. 이미지에는 모든 현재 Windows 10 업데이트, Microsoft Office, 기타 앱 및 필요한 드라이버 및 펌웨어가 포함될 수 있습니다.

- Windows 10/11 Pro 또는 Enterprise 이미지를 포함하는 USB 플래시 드라이브입니다. 이 옵션은 OOBE(기본 제공 환경) 설정 후까지 사용할 수 있는 Wi-Fi 없습니다. 설치가 완료되면 디바이스에 [Windows 10 Pro 및 Enterprise 필요한 Surface Hub 2개의 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치합니다.

다음 단계에서는 설치 미디어에서 USB 플래시 드라이브를 만든 다음 SURFACE HUB 2 MSI 파일에서 WINDOWS 10 PRO 및 Enterprise OS용 드라이버 및 펌웨어와 SEMM 패키지 파일을 추가하는 방법을 보여  있습니다. 다른 배포 방법을 사용하는 경우 [Surface Hub 2S의 업데이트 UEFI로 이동하여 이 문서의 OS 마이그레이션 섹션을 사용하도록 설정합니다](#update-uefi-on-surface-hub-2s-to-enable-os-migration).

> [!NOTE]
> 설치를 완료한 후에는 기존 Windows 10 Team 라이선스와 별개인 Windows 10 Pro 또는 Windows 10 Enterprise 유효한 라이선스가 필요합니다.

1. Windows 10 Pro 설치를 만들려면 지침에 따라 [다운로드 Windows 10](https://www.microsoft.com/software-download/windows10) 미디어 만들기 도구를 다운로드합니다. Windows 10 Enterprise 다운로드하려면 [Microsoft 볼륨 라이선싱 서비스 센터로](https://www.microsoft.com/licensing/servicecenter/default.aspx) 이동합니다.

1. 새 USB 스토리지 드라이브를 삽입합니다.
1. 미디어 만들기 도구를 열고 **설치 미디어 만들기****를 선택한 다음** 다음을 선택합니다.

   ![스크린샷은 설치 미디어를 만드는 옵션을 보여줍니다.](images/shm-fig16.png)

3. 언어를 선택한 다음 **, Windows 10** 및 **64비트(x64)를** 선택합니다. 그런 다음 **다음**을 선택합니다.

   ![언어, O S 버전 및 아키텍처 유형을 선택하는 위치를 보여주는 스크린샷.](images/shm-fig17.png)

4. **USB 플래시 드라이브를** 선택한 다음, **다음**을 선택합니다.

   ![스크린샷은 U S B 플래시 드라이브를 선택할 수 있는 위치를 보여줍니다.](images/shm-fig18.png)

5. 다운로드가 완료되면 **마침**을 선택합니다.

   ![화면은 U S B 드라이브가 준비되었으며 마침 단추가 포함되어 있음을 보고합니다.](images/shm-fig19.png)

6. SURFACE HUB 2(MSI 파일)의 WINDOWS 10 PRO 및 Enterprise OS용 SEMM 패키지 파일과 드라이버 및 펌웨어를 Windows 10 이미지가 포함된 *USB 플래시 드라이브(BOOTME*)의 루트에 복사합니다. BOOTME USB 드라이브에는 다음이 포함됩니다.

    - Windows 10 부팅 가능한 이미지입니다.

    - USB 드라이브의 루트에 복사된 SEMM 패키지 파일:

      - *DfciUpdate.dfi*.
      - SEMM 지문이 포함된 텍스트 파일입니다. (이 예제에서는 파일이 *SurfaceUEFI_2020Aug25_1058.txt*.) 자동으로 생성된 날짜-타임스탬프는 Surface UEFI 구성기를 사용하여 파일을 만든 날짜에 해당합니다.

   - Surface Hub 2(SurfaceHub2S_Win10_18362_20.082.25682.0.msi)의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어입니다. 이 파일을 USB 드라이브의 루트에 복사합니다.

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>OS 마이그레이션을 사용하도록 Surface Hub 2S에서 UEFI 업데이트

1. SURFACE HUB 2S의 USB-A 포트에 BOOTME 드라이브를 삽입합니다. 필요한 콘텐츠 목록은 이전 섹션을 참조하세요.

1. UEFI로 부팅하려면:

   1. Surface Hub 2S를 해제(종료)합니다.
   1. **볼륨 +** 를 길게 누른 다음 전원 단추를 누르고 놓습니다. UEFI 메뉴가 나타날 때까지 **볼륨 +** 를 계속 유지합니다.

      ![드로잉은 볼륨 및 전원 단추를 보여 줍니다.](images/shm-fig20.png)

3. 디바이스가 다시 시작되면 해당되는 경우 이전에 만든 UEFI 암호를 입력합니다(권장).

   ![시스템 암호 화면.](images/shm-fig22.png)

4. UEFI 메뉴에서 **관리를** 선택합니다. 그런 다음  **, USB에서 설치를** 선택합니다.

   ![스크린샷은 관리를 선택한 다음 "U S B에서 설치"를 선택할 위치를 보여줍니다.](images/shm-fig21.png)

5. 다음 이미지와 같이 **지금 다시 시작을** 선택합니다. 장치가 다시 시작됩니다. 창 중간에 흰색 Microsoft 로고가 표시되고 종료됩니다.

   ![스크린샷은 다시 시작하라는 메시지를 보여줍니다.](images/shm-fig25.png)

6. 전원 단추를 누르고 놓습니다. 표시되는 빨간색 대화 상자에서 Surface Enterprise 관리 모드를 활성화하도록 선택합니다.

7. 두 문자 인증서 지문과 UEFI 설정 암호를 입력합니다. 그런 다음 **확인을** 선택합니다.

   ![스크린샷은 두 문자 인증서 지문 및 UEFI 설정 암호를 입력하는 확인 활성화 대화 상자를 보여줍니다.](images/shm-fig23.png)

   > [!NOTE]
   > 디바이스에서 SEMM을 활성화하면 새 UEFI 설정 **EnableOSMigration** 이 적용됩니다. 더 이상 Windows 10 Team 액세스할 수 없습니다. 대신 다음 단계를 계속 진행하여 Windows 10 Pro 또는 Windows 10 Enterprise 설치해야 합니다.

   디바이스가 다시 부팅됩니다. 화면 중간에 흰색 로고가 표시되고 다시 종료됩니다.

### <a name="install-windows-1011-pro-or-enterprise"></a>Windows 10/11 Pro 설치 또는 Enterprise

1. 부팅 가능한 Windows 10/11 Pro 또는 Enterprise 드라이브가 Surface Hub 2 USB-A 포트에 아직 없는 경우 지금 삽입합니다. 그런 다음 전원 단추를 누르고 놓습니다.

    디바이스가 시작되면 화면 중간에 흰색 로고가 표시됩니다. 그런 다음 흰색 로고 아래에 회전하는 원이 나타납니다.

3. Surface 디바이스가 USB 드라이브로 자동으로 부팅되지 않는 경우 디바이스의 전원을 끕니다(전원 코드를 분리한 다음 다시 연결). 전원 코드를 다시 연결한 후 몇 초 후에 디바이스가 부팅됩니다. 그러면 화면 중간에 흰색 로고가 표시됩니다.

    디바이스가 켜지지 않으면 전원 단추를 누르고 놓습니다. 화면 중간에 로고가 표시된 직후, 흰색 로고 아래에 회전하는 원이 표시될 때까지 볼륨 아래쪽 단추를 길게 누릅니다.

   ![볼륨 및 전원 단추의 그림입니다.](images/shm-fig26.png)

4. OOBE(기본 제공 환경) 설정이 시작되면 지침에 따라 Windows 10/11 Pro 또는 Enterprise(버전 *20H2* 이상)를 설치합니다.

### <a name="install-surface-hub-2-drivers-and-firmware"></a>Surface Hub 2개 드라이버 및 펌웨어 설치

Surface Hub 2가 최신 상태인지 확인하려면 [Windows 10 Pro 및 Enterprise 위한 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=101974)를 설치합니다. 그런 다음 디바이스를 다시 부팅합니다. Surface가 1시간 동안 켜져 있는 상태로 유지한 다음 다시 부팅합니다. 두 번째 다시 부팅하라는 메시지가 표시되지 않습니다. 이 일시 중지 및 추가 재부팅은 펌웨어가 완전히 업데이트되었는지 확인합니다.

## <a name="configure-recommended-settings"></a>권장 설정 구성

Surface Hub 2S를 개인 생산성 디바이스로 구성하려면 [Windows 10/11 Pro 구성 또는 Surface Hub 2의 Enterprise](surface-hub-2-post-install.md) 참조하세요.

> [!NOTE]
>이 문서에 설명된 단계에 따라 디바이스를 Windows 10/11 Pro 또는 Surface Hub 2용 Enterprise 마이그레이션할 수 없는 경우 [Surface Hub 지원에](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support) 문의하세요.

## <a name="to-roll-back-to-windows-10-team"></a>Windows 10 Team 롤백하려면

디바이스를 Windows 10 Team 복원하려면 Surface Hub [2S에 대한 다시 설정 및 복구](surface-hub-2s-recover-reset.md)를 참조하세요.

> [!NOTE]
> Windows 10 Team 롤백하기 전에 먼저 SEMM에서 Surface Hub 등록을 취소하는 것이 좋습니다. 자세한 내용은 [SEMM에서 Surface 디바이스 등록 취소](/surface/unenroll-surface-devices-from-semm)를 참조하세요.

## <a name="version-history"></a>버전 기록

다음 표에서는 이 문서의 변경 내용을 요약합니다.

| 버전 | 날짜               | 설명                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| V. 1.5  | 2021년 12월 1일  | Windows 11 대한 지원을 표시하도록 업데이트됨
| V. 1.4  | 2020년 12월 14일 | "Surface Hub 2의 Windows 10 Pro 및 Enterprise OS용 드라이버 및 펌웨어"에 대한 MSI 파일을 설치하는 방법에 대한 [추가 정보를](#install-surface-hub-2-drivers-and-firmware) 제공하며, 시스템 상태에 따라 두 번째 재부팅이 필요할 수 있습니다.                                                          |
| V. 1.3  | 2020년 12월 3일 | [SEMM 등록 관리에](#manage-semm-enrollment) 대한 지침으로 업데이트되었습니다.                                                       |
| V. 1.2  | 2020년 9월 29일 | 유용성 피드백을 처리하는 기타 업데이트입니다.                                                        |
| V. 1.1  | 2020년 9월 15일 | 새 OS를 설치하기 위한 라이선스 요구 사항을 명확히 하는 추가 참고 사항을 소개했습니다. |
| V. 1.0  | 2020년 9월 1일  | 새 문서입니다.                                                                                           |
