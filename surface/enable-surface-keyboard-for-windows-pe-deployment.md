---
title: MDT 배포 중 Surface 랩톱 키보드를 사용 하도록 설정 하는 방법
description: MDT를 사용 하 여 Windows 10을 Surface 노트북에 배포 하는 경우 Windows PE 환경에서 사용할 수 있도록 키보드 드라이버를 가져와야 합니다.
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
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834716"
---
# MDT 배포 중 Surface 랩톱 키보드를 사용 하도록 설정 하는 방법

이 문서에서는 MDT (Microsoft 배포 도구 키트)를 사용 하는 배포 접근 방식에 대해 설명 합니다. 다른 배포 방법론에도이 정보를 적용할 수 있습니다. 대부분의 Surface 장치 유형에 서,이 키보드는 LTI (Lite Touch 설치) 중에 작동 해야 합니다. 그러나 Surface 노트북에서는 일부 추가 드라이버를 사용 하 여 키보드를 활성화 해야 합니다. Surface 노트북 (1 Gen) 및 Surface 노트북 2 장치의 경우 LTI의 windows PE (Windows 사전 설치 환경) 단계에서 사용할 키보드 드라이버를 지정할 수 있는 폴더 구조 및 선택 프로필을 준비 해야 합니다. 이 폴더 구조에 대 한 자세한 내용은 [MDT를 사용 하 여 Windows 10 이미지 배포: 5 단계: 드라이버 리포지토리 준비](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)를 참조 하세요.

> [!NOTE]
> 현재 드라이버 충돌로 인해 동일한 Windows PE 부팅 인스턴스에서 Surface 랩톱 2 및 Surface 랩톱 3 키보드 드라이버를 추가 하는 것은 지원 되지 않습니다. 대신 별도의 인스턴스를 사용 하세요.

> [!IMPORTANT]
> Windows 10을 S 모드에 설치 되어 있는 Surface 노트북에 Windows 10 이미지를 배포 하는 경우 KB [4032347, windows를 사전 설치 된 windows 10 s 모드의 surface 장치에 배포할 때 발생](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)하는 문제를 참조 하세요.

선택 프로필에 키보드 드라이버를 추가 하려면 다음 단계를 따릅니다.

1. 적절 한 위치에서 최신 Surface 랩톱 MSI 파일을 다운로드 합니다.
    - [Surface 노트북 (1 Gen) 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface 노트북 2 드라이버 및 펌웨어](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Intel 프로세서 드라이버 및 펌웨어가 있는 Surface 노트북 3](https://www.microsoft.com/download/details.aspx?id=100429)

2. Surface 랩톱 MSI 파일의 내용을 쉽게 찾을 수 있는 폴더에 추출 합니다 (예: c:\ surface_laptop_drivers). 콘텐츠를 추출 하려면 관리자 명령 프롬프트 창을 열고 다음 예제에서 명령을 실행 합니다.

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 배포 워크 벤치를 열고 **배포 공유** 노드 및 배포 공유를 확장 한 다음 **WindowsPEX64** 폴더로 이동 합니다.

   ![배포 워크 벤치에서 WindowsPEX64 폴더의 위치를 표시 하는 이미지](./images/surface-laptop-keyboard-1.png)

4. **WindowsPEX64** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **드라이버 가져오기를**선택 합니다.
5. 드라이버 가져오기 마법사의 지침에 따라 드라이버 폴더를 WindowsPEX64 폴더로 가져옵니다.  

> [!NOTE]
>  다운로드 한 MSI 패키지를 확인 하 여 형식 및 디렉터리 구조를 확인 합니다.  디렉터리 구조는 MSI가 해제 된 시점에 따라 SurfacePlatformInstaller (오래 된 MSI 파일) 또는 SurfaceUpdate (최신 MSI 파일)로 시작 됩니다. 

Surface 노트북 (1 Gen)을 지원 하려면 다음 폴더를 가져옵니다.

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

Surface 노트북 2를 지원 하려면 다음 폴더를 가져옵니다.

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Intel 프로세서를 사용 하는 Surface 노트북 3을 지원 하려면 다음 폴더를 가져옵니다.

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

다음 폴더를 가져오면 Surface 노트북 3 용 PE에서 전체 키보드, 트랙 패드 및 터치 기능을 사용할 수 있습니다.

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
    >  다운로드 한 MSI 패키지를 확인 하 여 형식 및 디렉터리 구조를 확인 합니다.  디렉터리 구조는 MSI가 해제 된 시점에 따라 SurfacePlatformInstaller (오래 된 MSI 파일) 또는 SurfaceUpdate (최신 MSI 파일)로 시작 됩니다. 

    Surface 노트북 (1 Gen)을 지원 하려면 다음 폴더를 가져옵니다.

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Surface 노트북 2를 지원 하려면 다음 폴더를 가져옵니다.

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    또는 "SurfaceUpdate"로 시작 하는 최신 MSI 파일에 대해 다음을 사용 합니다.

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Intel 프로세서를 사용 하는 Surface 노트북 3을 지원 하려면 다음 폴더를 가져옵니다.

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Intel 프로세서를 사용 하는 Surface 노트북 3의 모델은 Surface 노트북 3입니다. 남아 있는 Surface 노트북 드라이버는 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 노트북 3 폴더에 있습니다.

6. 이제 WindowsPEX64 폴더에 가져온 드라이버가 포함 되어 있는지 확인 합니다. 폴더는 다음과 유사 합니다.  

   ![배포 워크 벤치의 WindowsPEX64 폴더에 새로 가져온 드라이버를 표시 하는 이미지](./images/surface-laptop-keyboard-2.png)

7. WindowsPEX64 폴더를 사용 하는 선택 프로필을 구성 합니다. 선택 프로필은 다음과 유사 합니다.  

   ![선택 프로필의 일부로 선택 된 WindowsPEX64 폴더를 표시 하는 이미지](./images/surface-laptop-keyboard-3.png)

8. 다음과 같이 새 선택 프로필을 사용 하도록 MDT 배포 공유의 Windows PE 속성을 구성 합니다.  

   - **플랫폼용**으로 **x64**를 선택 합니다.
   - **선택 프로필**의 경우 새 프로필을 선택 합니다.
   - **선택 프로필에서 모든 드라이버 포함을**선택 합니다.
   
   ![MDT 배포 공유의 Windows PE 속성을 보여 주는 이미지](./images/surface-laptop-keyboard-4.png)

9. 선택 프로필 또는 **DriverGroup001** 변수를 사용 하 여 남아 있는 Surface 노트북 드라이버를 구성 했는지 확인 합니다.  
   - Surface 노트북 (1 Gen)의 모델은 **Surface 노트북**입니다. 남아 있는 Surface 노트북 드라이버는이 목록 뒤에 나오는 그림과 같이 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 랩톱 폴더에 상주해 야 합니다.
   - Surface 노트북 2의 경우 모델은 **Surface 노트북 2**입니다. 남아 있는 Surface 노트북 드라이버는 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 노트북 2 폴더에 상주해 야 합니다. 
   - Intel 프로세서를 사용 하는 Surface 노트북 3의 모델은 Surface 노트북 3입니다. 남아 있는 Surface 노트북 드라이버는 \MDT 배포 Share\Out-of-Box Drivers\Windows10\X64\Surface 노트북 3 폴더에 있습니다.

   ![배포 워크 벤치의 Surface 랩톱 폴더에 있는 일반 Surface 노트북 (첫번째 Gen) 드라이버를 표시 하는 이미지](./images/surface-laptop-keyboard-5.png)

새 선택 프로필 및 관련 설정을 사용 하도록 MDT 배포 공유를 구성한 후에는 [mdt를 사용 하 여 Windows 10 이미지 배포: 6 단계: 배포 작업 순서 만들기](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)에 설명 된 대로 배포 프로세스를 계속 합니다.
