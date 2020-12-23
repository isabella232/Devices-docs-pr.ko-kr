---
title: MDT 배포 중에 Surface 노트북 키보드를 사용하도록 설정하는 방법
description: MDT를 사용하여 Surface 노트북에 Windows 10을 배포하는 경우 Windows PE 환경에서 사용할 키보드 드라이버를 가져와야 합니다.
keywords: windows 10 surface, 자동화, 사용자 지정, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247310"
---
# MDT 배포 중에 Surface 노트북 키보드를 사용하도록 설정하는 방법

이 문서에서는 MDT(Microsoft Deployment Toolkit 사용하는 배포 방식에 대해 설명합니다. 이 정보를 다른 배포 방법에 적용할 수도 있습니다. 대부분의 Surface 디바이스 유형에서는 LTI(라이트 터치 설치) 중에 키보드가 작동해야 합니다. 그러나 Surface 노트북을 사용하려면 몇 가지 추가 드라이버가 필요합니다. Surface Laptop(1세대) 및 Surface Laptop 2 장치의 경우 LTI의 Windows PE(Windows 사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비해야 합니다. 이 폴더 구조에 대한 자세한 내용은 [MDT를 사용하여 Windows 10 이미지 배포: 5단계:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)드라이버 리포지토리 준비를 참조하세요.


> [!IMPORTANT]
> Windows 10 S 모드가 사전 설치된 Surface 노트북에 Windows 10 이미지를 배포하는 경우, 사전 설치한 Windows 10 S 모드로 Surface 디바이스에 Windows를 배포할 때의 문제인 KB [4032347을](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)참조합니다.

선택 프로필에 키보드 드라이버를 추가하려면 다음 단계를 수행합니다.

1. 적절한 위치에서 최신 Surface Laptop MSI 파일을 다운로드합니다.
    - [Surface 노트북(1세대) 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface 노트북 2 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Intel 프로세서 드라이버 및 펌웨어가 있는 Surface 노트북 3](https://www.microsoft.com/download/details.aspx?id=100429)

2. Surface Laptop MSI 파일의 내용을 쉽게 찾을 수 있는 폴더(예: c:\surface_laptop_drivers)에 추출합니다. 내용을 추출하기 위해 상승된 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행합니다.

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Deployment Workbench를 열고 **배포 공유** 노드 및 배포 공유를 확장한 다음 **WindowsPEX64 폴더로** 이동합니다.

   ![Deployment Workbench에서 WindowsPEX64 폴더의 위치를 표시하는 이미지](./images/surface-laptop-keyboard-1.png)

4. **WindowsPEX64** 폴더를 마우스 오른쪽 단추로 클릭하고 드라이버 **가져오기를 선택합니다.**
5. 드라이버 가져오기 마법사의 지침에 따라 드라이버 폴더를 WindowsPEX64 폴더로 가져올 수 있습니다.  

> [!NOTE]
>  다운로드한 MSI 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.  디렉터리 구조는 MSI가 릴리스된 때에 따라 SurfacePlatformInstaller(이전 MSI 파일) 또는 SurfaceUpdate(새 MSI 파일)로 시작됩니다. 

Surface 노트북(1세대)을 지원하기 위해 다음 폴더를 가져오십시오.

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

Surface Laptop 2를 지원하기 위해 다음 폴더를 가져오십시오.

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Intel 프로세서를 통해 Surface Laptop 3을 지원하기 위해 다음 폴더를 가져오십시오.

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

다음 폴더를 가져오면 Surface Laptop 3의 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- itouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
- ManagementEngine
- SurfaceAcpiNotify
- SurfaceBattery
- SurfaceDockIntegration
- SurfaceHidMini
- SurfaceHotPlug
- SurfaceIntegration
- SurfaceSerialHub
- SurfaceService
- SurfaceStorageFwUpdate


    > [!NOTE]
    >  다운로드한 MSI 패키지를 확인하여 형식 및 디렉터리 구조를 확인합니다.  디렉터리 구조는 MSI가 릴리스된 때에 따라 SurfacePlatformInstaller(이전 MSI 파일) 또는 SurfaceUpdate(새 MSI 파일)로 시작됩니다. 

    Surface 노트북(1세대)을 지원하기 위해 다음 폴더를 가져오십시오.

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Surface Laptop 2를 지원하기 위해 다음 폴더를 가져오십시오.

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    또는 "SurfaceUpdate"로 시작되는 새로운 MSI 파일의 경우 다음을 사용 합니다.

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Intel 프로세서를 통해 Surface Laptop 3을 지원하기 위해 다음 폴더를 가져오십시오.

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Intel 프로세서가 탑재된 Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다. 나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.

6. WindowsPEX64 폴더에 가져온 드라이버가 포함되어 있는지 확인합니다. 폴더는 다음과 같습니다.  

   ![Deployment Workbench의 WindowsPEX64 폴더에 새로 가져온 드라이버를 표시하는 이미지](./images/surface-laptop-keyboard-2.png)

7. WindowsPEX64 폴더를 사용하는 선택 프로필을 구성합니다. 선택 프로필은 다음과 같습니다.  

   ![선택 프로필의 일부로 선택된 WindowsPEX64 폴더를 표시하는 이미지](./images/surface-laptop-keyboard-3.png)

8. 다음과 같이 새 선택 프로필을 사용하도록 MDT 배포 공유의 Windows PE 속성을 구성합니다.  

   - 플랫폼의 **경우** **x64를 선택합니다.**
   - 선택 **프로필의 경우**새 프로필을 선택합니다.
   - 선택 **프로필의 모든 드라이버 포함을 선택합니다.**
   
   ![MDT 배포 공유의 Windows PE 속성을 표시하는 이미지](./images/surface-laptop-keyboard-4.png)

9. 선택 프로필 또는 **DriverGroup001** 변수를 사용하여 나머지 Surface 노트북 드라이버를 구성해야 합니다.  
   - Surface 노트북(1세대)의 경우 모델이 **Surface 노트북입니다.** 나머지 Surface 노트북 드라이버는 이 목록 다음 그림과 같이 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 폴더에 상주해야 합니다.
   - Surface 노트북 2의 경우 모델이 **Surface Laptop 2입니다.** 나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 2 폴더에 있습니다. 
   - Intel 프로세서가 탑재된 Surface Laptop 3의 경우 모델이 Surface Laptop 3입니다. 나머지 Surface 노트북 드라이버는 \MDT 배포 공유\첫 실행 드라이버\Windows10\X64\Surface Laptop 3 폴더에 있습니다.

   ![Deployment Workbench의 Surface Laptop 폴더에 있는 일반 Surface 노트북(1세대) 드라이버를 보여 주는 이미지](./images/surface-laptop-keyboard-5.png)

새 선택 프로필 및 관련 설정을 사용하기 위해 MDT 배포 공유를 구성한 후 [MDT를 사용하여 Windows 10 이미지 배포: 6단계:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)배포 작업 순서 만들기에 설명된대로 배포 프로세스를 계속합니다.
