---
title: MDT 배포 중에 Surface Laptop 키보드를 사용하도록 설정하는 방법
description: MDT를 사용하여 Surface 랩톱에 Windows 10 배포하는 경우 Windows PE 환경에서 사용할 키보드 드라이버를 가져와야 합니다.
keywords: windows 10 Surface, 자동화, 사용자 지정, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 01/05/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
ms.openlocfilehash: d207d0843e23f68713597c12a529ab5574fa695e
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497921"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>MDT 배포 중에 Surface Laptop 키보드를 사용하도록 설정하는 방법

이 문서에서는 MDT(Microsoft Deployment Toolkit)를 사용하는 배포 방법을 설명합니다. 다른 배포 방법론에도 이 정보를 적용할 수 있습니다. 대부분의 Surface 장치 유형에서는 LTI(라이트 터치 설치) 중에 키보드가 작동해야 합니다. 그러나 Surface Laptop 키보드를 사용하도록 설정하려면 몇 가지 추가 드라이버가 필요합니다. Surface Laptop(1세대) 및 Surface Laptop 2 디바이스의 경우 LTI의 Windows PE(사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비해야 Windows 합니다. 이 폴더 구조에 대한 자세한 내용은 [MDT를 사용하여 Windows 10 이미지 배포: 5단계: 드라이버 리포지토리 준비](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)를 참조하세요.

> [!TIP]
> 동일한 Windows PE 부팅 인스턴스에서 Surface Laptop 2 및 Surface Laptop 3에 키보드 드라이버를 사용하는 경우 키보드 또는 터치 패드가 Windows PE에서 작동하지 않는 경우 펌웨어를 수동으로 다시 설정해야 할 수 있습니다.
>
> - 전원 단추를 30초 동안 길게 누릅니다. PSU(전원 공급 장치)에 연결된 경우 전원 단추를 길게 누르면 PSU 코드 끝에 있는 표시등이 잠시 꺼진 후 다시 켜집니다.

> [!IMPORTANT]
> S 모드에서 Windows 10 미리 설치된 Surface Laptop Windows 10 이미지를 배포하는 경우 S 모드에서 [사전 설치된 Windows 10 사용하여 Surface 디바이스에 Windows 배포할 때 발생하는 KB 4032347, 문제를](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues) 참조하세요.

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>선택 프로필에 키보드 드라이버 추가

1. 적절한 위치에서 최신 Surface Laptop .msi 파일을 다운로드합니다.
    - [Surface Laptop(1세대) 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=57515)
    - [인텔 프로세서 드라이버 및 펌웨어를 사용하는 Surface Laptop 3](https://www.microsoft.com/download/details.aspx?id=100429)
    - [인텔 프로세서 드라이버 및 펌웨어를 사용하는 Surface Laptop 4](https://www.microsoft.com/download/102924)
    - [AMD 프로세서 드라이버 및 펌웨어가 있는 Surface Laptop 4](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=103503)

2. 쉽게 찾을 수 있는 폴더(예: c:\surface_laptop_drivers)에 Surface Laptop .msi 파일의 내용을 추출합니다. 콘텐츠를 추출하려면 관리자 권한 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행합니다.

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Deployment Workbench를 열고 **배포 공유** 노드 및 배포 공유를 확장한 다음 **WindowsPEX64** 폴더로 이동합니다.
4. **WindowsPEX64** 폴더를 마우스 오른쪽 단추로 클릭하고 **드라이버 가져오기**를 선택합니다.
5. 드라이버 가져오기 마법사의 지침에 따라 드라이버 폴더를 WindowsPEX64 폴더로 가져옵니다.

 > [!NOTE]
 > 다운로드한 .msi 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.  디렉터리 구조는 .msi 파일이 릴리스된 시기에 따라 SurfacePlatformInstaller(이전 .msi 파일) 또는 SurfaceUpdate(최신 .msi 파일)로 시작합니다.

## <a name="import-drivers-for-surface-devices"></a>Surface 디바이스용 드라이버 가져오기

Surface Laptop 디바이스에 적절하게 다음 폴더를 가져옵니다.

| 장치                                    | 폴더 가져오기                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 추가 정보                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Laptop 스튜디오**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | 해당 없음                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Pro 8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealarmacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | 해당 없음                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **인텔 프로세서를 사용하는 Surface Laptop 4** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | 해당 없음                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **AMD 프로세서를 Surface Laptop 4**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient | 해당 없음                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **인텔 프로세서를 사용하는 Surface Laptop 3** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | 다음 폴더를 가져오면 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>Itouch<br>칩셋<br>칩셋LPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | "SurfaceUpdate"로 시작하는 최신 .msi 파일의 경우 다음을 사용합니다.<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop(1세대)**              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | **"SurfaceUpdate"** 로 시작하는 최신 .msi 파일의 경우 다음을 사용합니다.<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > 다운로드한 .msi 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.  디렉터리 구조는 .msi 해제된 시기에 따라 SurfacePlatformInstaller(이전 .msi 파일) 또는 SurfaceUpdate(최신 .msi 파일)로 시작합니다.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>가져온 드라이버 확인 & Windows PE 속성 구성

1. 다음 그림과 같이 WindowsPEX64 폴더에 가져온 드라이버가 포함되어 있는지 확인합니다.

   ![Deployment Workbench의 WindowsPEX64 폴더에 새로 가져온 드라이버를 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-2.png)
1. 다음 그림과 같이 WindowsPEX64 폴더를 사용하는 선택 프로필을 구성합니다.

   ![선택 프로필의 일부로 선택한 WindowsPEX64 폴더를 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-3.png)
1. 다음과 같이 새 선택 프로필을 사용하도록 MDT 배포 공유의 Windows PE 속성을 구성합니다.
    - **플랫폼**의 경우 **x64를** 선택합니다.
    - **선택 프로필**의 경우 새 프로필을 선택합니다.
    - **선택 프로필에서 모든 드라이버 포함을** 선택합니다.

    ![MDT 배포 공유의 Windows PE 속성을 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-4.png)
4. 선택 프로필 또는 **DriverGroup001** 변수를 사용하여 나머지 Surface Laptop 드라이버를 구성했는지 확인합니다.
    - Surface Laptop(1세대)의 경우 모델이 **Surface Laptop**. 나머지 Surface Laptop 드라이버는 다음 그림과 같이 \MDT 배포 공유\기본 제공 드라이버\Windows10\X64\Surface Laptop 폴더에 있어야 합니다.
    - Surface Laptop 2의 경우 모델은 **Surface Laptop 2**입니다. 나머지 Surface Laptop 드라이버는 \MDT 배포 공유\기본 제공 드라이버\Windows10\X64\Surface Laptop 2 폴더에 있어야 합니다.
    - 인텔 프로세서를 사용하는 Surface Laptop 3의 경우 모델은 Surface Laptop 3입니다. 나머지 Surface Laptop 드라이버는 \MDT 배포 공유\기본 제공 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.

    ![Deployment Workbench의 Surface Laptop 폴더에 있는 일반 Surface Laptop(1세대) 드라이버를 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-5.png)

새 선택 프로필 및 관련 설정을 사용하도록 MDT 배포 공유를 구성한 후 [MDT: 6단계: 배포 작업 순서를 사용하여 Windows 10 이미지 배포에](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence) 설명된 대로 배포 프로세스를 계속 진행합니다.
