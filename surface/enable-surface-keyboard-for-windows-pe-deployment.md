---
title: MDT 배포 Surface Laptop 키보드를 사용하도록 설정하는 방법
description: MDT를 사용하여 Surface 랩톱에 Windows 10 배포하는 경우 해당 PE 환경에서 사용할 키보드 드라이버를 Windows 합니다.
keywords: windows 10 surface, 자동화, 사용자 지정, mdt
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
ms.openlocfilehash: 8707d022ae5e3d3f34c59fab88328b5720896898
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449191"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>MDT 배포 Surface Laptop 키보드를 사용하도록 설정하는 방법

이 문서에서는 MDT(Microsoft Deployment Toolkit 사용하는 배포 방식에 대해 설명합니다. 이 정보를 다른 배포 방법에 적용할 수도 있습니다. 대부분의 유형의 Surface 디바이스에서 키보드는 LTI(라이트 터치 설치) 중에 작동해야 합니다. 그러나 Surface Laptop 사용하려면 몇 가지 드라이버가 추가로 필요합니다. Surface Laptop(1세대) 및 Surface Laptop 2 장치의 경우 LTI의 Windows Windows PE(사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비해야 합니다. 이 폴더 구조에 대한 자세한 내용은 [MDT를 사용하여 Windows 10 이미지 배포: 5단계:](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository) 드라이버 리포지토리 준비를 참조하세요.

> [!TIP]
> 동일한 Windows PE 부팅 인스턴스에서 Surface Laptop 2 및 Surface Laptop 3에 키보드 드라이버를 사용하는 경우 키보드 또는 터치 패드가 WINDOWS PE에서 작동하지 않는 경우 펌웨어를 수동으로 다시 설정해야 할 수 있습니다.
>
> - 전원 단추를 30초간 누르고 있습니다. PSU(전원 공급 장치)에 연결되어 있는 경우 전원 단추를 누르고 PSU 코드 끝에 조명이 잠시 꺼지기 전에 전원 단추를 누릅니다.

> [!IMPORTANT]
> S 모드가 Surface Laptop Windows 10 있는 Windows 10 이미지를 배포하는 경우 사전 설치한 Windows S 모드로 [Surface](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues) 디바이스에 Windows 배포할 때의 문제인 KB 4032347, S 모드로 Windows 10 참조합니다. Windows 10

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>선택 프로필에 키보드 드라이버 추가

1. 적절한 위치에서 최신 Surface Laptop .msi 파일을 다운로드합니다.
    - [Surface Laptop(1세대) 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 프로세서 드라이버 및 펌웨어가 있는 Surface Laptop 3](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 프로세서 드라이버 및 펌웨어가 있는 Surface Laptop 4](https://www.microsoft.com/download/102924)
    - [Surface Laptop 드라이버 및 펌웨어가 있는 Surface Laptop 4](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=103503)

2. 파일 내용의 Surface Laptop .msi 쉽게 찾을 수 있는 폴더(예: c:\surface_laptop_drivers)에 추출합니다. 내용을 추출하기 위해 상승된 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행합니다.

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Deployment Workbench를 열고 **Deployment Shares** 노드 및 배포 공유를 확장한 다음 **WindowsPEX64 폴더로** 이동합니다.
4. **WindowsPEX64 폴더를 마우스 오른쪽 단추로** 클릭하고 **드라이버 가져오기를 선택합니다**.
5. 드라이버 가져오기 마법사의 지침에 따라 WindowsPEX64 폴더로 드라이버 폴더를 가져올 수 있습니다.

 > [!NOTE]
 > 다운로드한 .msi 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.  디렉터리 구조는 이전 .msi 파일) 또는 SurfaceUpdate(.msi 파일)로 시작되는 디렉터리 구조는 .msi 파일을 릴리스한 .msi 있습니다.

## <a name="import-drivers-for-surface-devices"></a>Surface 디바이스용 드라이버 가져오기

디바이스에 따라 다음 폴더를 Surface Laptop.  

| 장치                                | 폴더 가져오기                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 추가 정보                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Laptop 스튜디오                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol | 해당 없음 |
| Surface Pro 8                         | heci<br>ialpss2_gpio2_tgl<br>ialpss2_i2c_tgl<br>ialpss2_spi_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>msux64w10<br>netwtw08<br>surfacebattery<br>surfacehidminidriver<br>surfaceintegrationdriver<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>tbthostcontroller<br>tbthostcontrollerhsacomponent<br> |해당 없음 |
| Surface Laptop 4 및 Intel 프로세서 | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          |해당 없음                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 4 AMD 프로세서   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient |해당 없음                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 3 Intel 프로세서 | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | 다음 폴더를 가져오면 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>칩셋<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| Surface Laptop 2                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | "SurfaceUpdate"로 .msi 새 파일의 경우 다음을 사용 합니다.<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                                    |
| Surface Laptop(1세대)              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | "SurfaceUpdate"로 .msi 새 파일의 경우 다음을 사용 합니다.<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                |

  > [!TIP]
  > 다운로드한 .msi 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.  디렉터리 구조는 디렉터리가 릴리스된 .msi 따라 SurfacePlatformInstaller(이전 .msi 파일) 또는 SurfaceUpdate(.msi 파일)로 .msi 됩니다.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>가져온 드라이버를 & PE 속성을 Windows 확인

1. 다음 그림과 같이 WindowsPEX64 폴더에 가져온 드라이버가 포함되어 있는지 확인합니다.

   ![Deployment Workbench의 WindowsPEX64 폴더에 새로 가져온 드라이버를 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-2.png)
1. 다음 그림과 같이 WindowsPEX64 폴더를 사용하는 선택 프로필을 구성합니다.

   ![선택 프로필의 일부로 선택된 WindowsPEX64 폴더를 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-3.png)
1. 다음과 Windows 선택 프로필을 사용하도록 MDT 배포 공유의 기본 PE 속성을 구성합니다.
    - 플랫폼 **에서** **x64를 선택합니다**.
    - 선택 **프로필의 경우** 새 프로필을 선택합니다.
    - 선택 **프로필의 모든 드라이버 포함을 선택합니다**.

    ![MDT 배포 공유의 Windows PE 속성을 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-4.png)
4. 선택 프로필 또는 **DriverGroup001** 변수를 사용하여 나머지 Surface Laptop 드라이버를 구성해야 합니다.
    - Surface Laptop(1세대)의 경우 **모델이 Surface Laptop**. 나머지 Surface Laptop 드라이버는 다음 그림과 같이 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 폴더에 상주해야 합니다.
    - Surface Laptop 2의 경우 모델이 Surface Laptop **2입니다**. 나머지 Surface Laptop 드라이버는 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 폴더에 배치해야 합니다.
    - Intel Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다. 나머지 Surface Laptop 드라이버는 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 폴더에 있습니다.

    ![Deployment Workbench의 Surface Laptop 폴더에 있는 일반 Surface Laptop(1세대) 드라이버를 보여 주는 이미지입니다.](./images/surface-laptop-keyboard-5.png)

새 선택 프로필 및 관련 설정을 사용하기 위해 MDT 배포 공유를 구성한 후 [MDT](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)를 사용하여 Windows 10 이미지 배포: 6단계: 배포 작업 순서 만들기에 설명된 배포 프로세스를 계속합니다.
