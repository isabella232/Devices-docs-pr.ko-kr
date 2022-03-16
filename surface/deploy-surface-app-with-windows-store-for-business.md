---
title: Surface 또는 비즈니스용 Microsoft Store(Surface)교육용 Microsoft Store Surface 앱 배포
description: PowerShell 및 MDT를 통해 Surface 앱을 추가하고 비즈니스용 Microsoft Store 교육용 Microsoft Store Surface 앱을 설치하는 방법을 찾아보십시오.
keywords: surface 앱, 앱, 배포, 사용자 지정
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 4/16/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: cb101ece861b19bab43b0e3356a1109389eebb2f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448361"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a>앱 및 교육을 비즈니스용 Microsoft Store Surface 앱 배포

**적용 대상**

- Surface Laptop(모든 세대)
- Surface Pro 3 이상
- Surface Laptop Go
- Surface Go(모든 세대)
- Surface Book(모든 세대)
- Surface Studio(모든 세대)
- Surface Laptop 스튜디오
- Surface Pro LTE Advanced(모델 1807)
- Surface Pro(모델 1796)
- Surface 3 LTE
- Surface 3

Surface 앱은 일련 번호Microsoft Store Surface 모델 이름, UEFI 버전 및 관련 드라이버를 비롯한 장치 정보에 빠르게 액세스할 수 있는 다양한 Surface 관련 설정 및 옵션을 제어하는 경량 앱 앱입니다.  

Windows 사용하는 고객은 자동 업데이트의 일부로 Surface 앱을 받게 됩니다. 그러나 조직에서 Surface 디바이스에 배포할 이미지를 준비하는 경우 각 개별 디바이스의 사용자에게 앱 또는 디바이스에서 앱을 다운로드하여 설치하도록 요구하는 대신 이미징 및 배포 프로세스에 Surface 앱(이전의 Surface Hub)을 포함해야 Microsoft Store 수 비즈니스용 Microsoft Store. 

> [!NOTE]
> 이 문서는 X에 적용되지 Surface Pro 않습니다. 자세한 내용은 X에서 배포[, 관리 및 Surface Pro 참조하세요.](surface-pro-arm-app-management.md)

## <a name="surface-app-overview"></a>Surface 앱 개요

Surface 앱은 앱의 무료 다운로드로 [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) 사용자는 Microsoft Store 다운로드하여 설치할 수 있지만 조직에서 비즈니스용 Microsoft Store 대신 앱을 사용하는 경우 스토어의 인벤토리에 추가하고 앱을 Windows 배포 프로세스의 일부로 포함해야 합니다. 이러한 프로세스는 이 문서 전체에서 설명됩니다. 자세한 내용은 비즈니스용 Microsoft Store 참조 [비즈니스용 Microsoft Store하세요](/microsoft-store/). 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a>Surface 계정에 Surface 비즈니스용 Microsoft Store 추가 

사용자가 회사의 비즈니스용 Microsoft Store 계정에서 앱을 설치하거나 배포하려면 먼저 원하는 앱을 사용할 수 있도록 설정하고 비즈니스 사용자에게 라이선스를 부여해야 합니다. 

1. 아직 수행하지 않은 경우 새 계정을 [비즈니스용 Microsoft Store.](https://www.microsoft.com/business-store) 

2. 포털에 로그인합니다. 

3. 오프라인 라이선싱 사용: **** >  그림 1에 **표시된 설정** 관리를 클릭한 다음 **** 스토어에서 쇼핑하는 사용자에 대해 오프라인 사용이 허가된 앱 표시 확인란을 선택합니다. 앱 라이선싱 모델에 비즈니스용 Microsoft Store 대한 자세한 내용은 비즈니스용 Microsoft Store [및 Education의 앱을 참조하세요](/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![오프라인 라이선스 앱 표시 확인란](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *그림 1. 오프라인으로 사용할 수 있도록 앱 사용*

4. Surface 앱을 앱 계정에 비즈니스용 Microsoft Store 추가합니다.

    * **스토어에서 Surface 앱 검색** 
    
    * Surface 앱이 검색 결과에 표시된 후 앱 아이콘을 클릭합니다.
    
    * 그림 2에 표시된 같이 선택(**온라인** 또는 오프라인 **** 선택)이 표시됩니다.
    
      > [!div class="mx-imgBorder"]
      > ![오프라인 라이선싱 모드를 선택하고 인벤토리에 앱을 추가합니다.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *그림 2. 오프라인 라이선싱 모드를 선택하고 인벤토리에 앱 추가*
    
    * 오프라인 **을 클릭하여** 오프라인 라이선싱 모드를 선택합니다.
    
    * 앱 **다운로드를 클릭하여** 앱 인벤토리에 비즈니스용 Microsoft Store 추가합니다. 그림 3과 같이 관리 도구를 사용하여 오프라인 앱을 배포하거나 개인 저장소의 회사의 인벤토리 페이지에서 다운로드할 수 있습니다.를 확인하라는 대화 상자가 표시됩니다.
    
      > [!div class="mx-imgBorder"]
      > ![오프라인 사용이 허가된 앱의 인정 창입니다.](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *그림 3. 오프라인 사용이 허가된* 앱의 인정
      
    * **확인**을 클릭합니다.

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a>앱 계정에서 Surface 비즈니스용 Microsoft Store 다운로드
오프라인 모드에서 비즈니스용 Microsoft Store 계정에 앱을 추가한 후 앱을 다운로드하여 배포 공유에 AppxBundle로 추가할 수 있습니다.

1. 에서 비즈니스용 Microsoft Store 계정에 로그온합니다https://businessstore.microsoft.com.

2. Manage **->Apps & 클릭합니다**. 이 문서의 계정에 Surface 앱 추가 섹션에서 추가한 Surface 앱을 포함하여 모든 회사의 앱 목록이 비즈니스용 Microsoft Store [표시됩니다](#add-surface-app-to-a-microsoft-store-for-business-account).

3. 동작**에서** 타원(**...**)을 클릭한 다음 Surface 앱에 **** 오프라인으로 사용하기 위해 다운로드를 클릭합니다.

4. 그림 4에 표시된 **** 같이 선택한 **** 앱에 대해 사용 가능한 선택에서 원하는 플랫폼 및 아키텍처 옵션을 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![AppxBundle 패키지의 예입니다.](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *그림 4. 앱에 대한 AppxBundle 패키지 다운로드*
    
5. 다운로드 **를 클릭합니다**. AppxBundle 패키지가 다운로드됩니다. 다운로드한 파일의 경로는 이 문서의 부분에 필요하기 때문에 유의해야 합니다.

6. 인코딩된 **** 라이선스 또는 인코딩되지 않은 라이선스 **옵션을** 클릭합니다. 인코딩된 라이선스 옵션을 Microsoft Endpoint Configuration Manager 또는 구성 디자이너를 사용하여 Windows 패키지를 만들 때 사용합니다. MDT(Microsoft Deployment Toolkit)를 포함하여 이미징을 기반으로 하는 배포 솔루션 또는 DISM(배포 이미지 서비스 및 관리) 또는 배포 솔루션을 사용하는 경우 인코딩되지 않은 라이선스 옵션을 선택합니다.

7. 생성 **을** 클릭하여 앱에 대한 라이선스를 생성하고 다운로드합니다. 라이선스 파일의 경로는 이 문서의 부분에 필요하기 때문에 유의해야 합니다.

>[!NOTE]
>Surface 앱과 같이 오프라인으로 사용하기 위해 앱을 다운로드할 때 필수 프레임워크로 레이블이 붙은 페이지 아래쪽에 섹션이 표시 **될 수 있습니다**. 대상 컴퓨터에는 앱이 실행될 수 있도록 프레임워크가 설치되어 있어야 합니다. 따라서 아키텍처에 필요한 각 프레임워크(x86 또는 x64)에 대한 다운로드 프로세스를 반복하고 이 문서의 틀에서 설명하는 Windows 배포의 일부로 포함해야 할 수 있습니다.

그림 5는 Surface 앱에 필요한 프레임워크를 보여줍니다.

> [!div class="mx-imgBorder"]
> ![Surface 앱에 필요한 프레임워크입니다.](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*그림 5. Surface 앱에 필요한 프레임워크*

>[!NOTE]
>Surface 앱의 버전 번호와 필수 프레임워크는 앱이 업데이트될 때 변경됩니다. Surface 앱의 최신 버전과 각 프레임워크를 비즈니스용 Microsoft Store. 항상 Surface 앱 및 권장 프레임워크 버전을 사용하여 비즈니스용 Microsoft Store. 더 이상 사용되지 않은 프레임워크 또는 잘못된 버전을 사용할 경우 오류나 응용 프로그램 충돌이 발생할 수 있습니다.

Surface 앱에 필요한 프레임워크를 다운로드하려면 다음 단계를 따르세요.

1. download( **다운로드** ) 단추 **를 클릭합니다Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. 이렇게 하여 Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe를 다운로드합니다. 지정된 폴더에 대한 Appx 파일입니다.

2. download( **다운로드** ) 단추 **를 클릭합니다Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. 그러면 Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe를 다운로드합니다. 지정된 폴더에 대한 Appx 파일입니다.

>[!NOTE]
>Surface 디바이스에는 각 프레임워크의 64비트(x64) 버전만 필요합니다. Surface 디바이스는 네이티브 64비트 UEFI 장치로, 32비트 프레임워크가 필요한 32비트(x86) Windows 호환되지 않습니다. 

## <a name="install-surface-app-on-your-computer-with-powershell"></a>PowerShell을 통해 컴퓨터에 Surface 앱 설치
다음 절차에서는 Surface 앱을 컴퓨터에 프로비전하고 이후에 컴퓨터에서 만든 모든 사용자 계정에 사용할 수 있도록 합니다.

1. 이 문서의 비즈니스용 Microsoft Store 계정에서 [Surface](#download-surface-app-from-a-microsoft-store-for-business-account) 앱을 다운로드하는 방법 섹션에 설명된 절차에 따라 Surface app AppxBundle 및 라이선스 파일을 다운로드합니다. 

2. 관리자 권한 PowerShell 세션을 시작합니다.

    >[!NOTE]
    >관리자 권한으로 PowerShell을 실행하지 않는 경우 세션에 앱을 설치하는 데 필요한 권한이 없습니다.
    
3. 관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    여기서 `<DownloadPath>` 은 앱 계정에서 AppxBundle 및 라이선스 파일을 다운로드한 비즈니스용 Microsoft Store 있습니다.

    예를 들어 파일을 c:\Temp에 다운로드한 경우 실행한 명령은 다음과 같습니다.
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. 이제 Surface 앱을 현재 Windows 컴퓨터에서 사용할 수 있습니다. 

   Surface 앱이 프로비전된 컴퓨터에서 작동하기 전에 이 문서 앞부분에서 설명한 프레임워크도 프로비전해야 합니다. 이러한 프레임워크를 프로비전하기 위해 Surface 앱을 프로비전하는 데 사용한 상승된 PowerShell 세션에서 다음 절차를 사용합니다.

5. 관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. 관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a>MDT를 통해 Surface 앱 설치
다음 절차에서는 MDT를 사용하여 배포 시 Surface 앱의 설치를 자동화합니다. 응용 프로그램은 배포 중 MDT에서 자동으로 프로비전되어 기존 이미지로 이 프로세스를 사용할 수 있습니다. 이 프로세스는 Surface 디바이스에 Windows 배포의 일부로 Surface 앱을 배포하는 Windows 권장되는 프로세스입니다.

1. 이 문서의 앞부분에서 설명한 절차 [에](#download-surface-app-from-a-microsoft-store-for-business-account) 따라 Surface app AppxBundle 및 라이선스 파일을 다운로드합니다. 

2. MDT Deployment Workbench에서 새 응용 프로그램 마법사를 사용하여 다운로드한 파일을 원본 파일이 있는 새 **응용 프로그램으로 가져올 수 있습니다**.

3. 새 **응용 프로그램** 마법사의 명령 세부 정보 페이지에서 기본 작업 디렉터리를 지정하고 **** **명령**에 대해 다음과 같이 AppxBundle의 파일 이름을 지정합니다.

   * 명령:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * 작업 디렉터리: %DEPLOYROOT%\Applications\SurfaceApp

Surface 앱이 대상 컴퓨터에서 작동하려면 이 문서 앞부분에서 설명한 프레임워크도 필요하게 됩니다. 다음 절차에 따라 Surface 앱에 필요한 프레임워크를 MDT로 가져오고 종속성으로 구성합니다.

1. 이 문서의 앞부분에서 설명한 절차를 사용하여 프레임워크 파일을 다운로드합니다. 각 프레임워크를 별도의 폴더에 저장합니다.

2. MDT Deployment Workbench에서 새 응용 프로그램 마법사를 사용하여 다운로드한 파일을 원본 파일이 있는 새 **응용 프로그램으로 가져올 수 있습니다**.

3. 명령 **세부 정보 페이지의** 명령 필드 및 기본 작업 디렉터리에 다운로드한 각 응용 프로그램의 파일 이름을 입력 **** 합니다.

Surface 앱의 종속성으로 프레임워크를 구성하기 위해 다음 프로세스를 사용하세요.

1. MDT Deployment Workbench에서 Surface 앱의 속성을  열 수 있습니다.

2. 종 **속성 탭을 클릭** 한 다음 추가를 **클릭합니다**.

3. 새 응용 프로그램 마법사에서 제공한 이름을 사용하여 각 프레임워크의 확인란을 선택합니다.

가져온 후 Surface 앱을 배포 마법사의 응용 프로그램 단계에서 Windows 있습니다.**** 다음 프로세스에 따라 배포 작업 순서에서 응용 프로그램을 지정하여 응용 프로그램을 자동으로 설치할 수도 있습니다.

1. MDT Deployment Workbench에서 배포 작업 순서를 엽니다.

2. 배포의 **State Restore**(상태 복원) 섹션에서 새로운 **Install Application**(응용 프로그램 설치) 작업을 추가합니다.

3. 단일 **응용 프로그램 설치를** 선택하고 **설치할 응용** 프로그램으로 Surface **App을 지정합니다**.

앱 배포에 앱을 Windows 대한 자세한 내용은 MDT를 사용하여 배포 준비[를 참조하세요](/windows/deployment/deploy-windows-mdt/prepare-for-windows-deployment-with-mdt).
