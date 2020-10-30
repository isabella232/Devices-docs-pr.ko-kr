---
title: Microsoft Endpoint Configuration Manager를 사용 하 여 SEMM (Surface)을 사용 하 여 장치 관리
description: 끝점 구성 관리자를 사용 하 여 Microsoft Surface Enterprise 관리 모드 (SEMM)를 관리 하는 방법에 대해 알아봅니다.
keywords: 등록, 업데이트, 스크립트, 설정
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 2d31f520d8c4da54f47b2b89b58b43e2cb983f1a
ms.sourcegitcommit: 7f5b97275fe301ef700f9c77954a1054e2e8d046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145619"
---
# Microsoft Endpoint Configuration Manager를 사용하여 SEMM에서 디바이스 관리

Surface UEFI 장치의 Microsoft Surface Enterprise 관리 모드 (SEMM) 기능을 통해 관리자는 Surface UEFI 설정의 구성을 관리 하 고 보안을 유지할 수 있습니다. 대부분의 조직에서는 Microsoft Surface UEFI 구성자 도구를 사용 하 여 Windows Installer (.msi) 패키지를 만들어이 프로세스를 수행 합니다. 그런 다음 해당 패키지를 클라이언트 화면 장치에 실행 하거나 배포 하 여 디바이스를 SEMM에 등록 하 고 Surface UEFI 설정 구성을 업데이트 합니다.

Microsoft Endpoint Configuration Manager를 사용 하는 조직의 경우 Microsoft Surface UEFI Configurator 프로세스를 사용 하 여 SEMM을 배포 하 고 관리 하는 방법도 있습니다. Microsoft Surface UEFI 관리자는 디바이스에서 SEMM 관리를 사용할 수 있는 필수 어셈블리를 만드는 간단한 설치 관리자입니다. 관리 되는 클라이언트에 Microsoft Surface UEFI Manager를 사용 하 여 이러한 어셈블리를 설치 하면 PowerShell 스크립트를 사용 하 여 구성 관리자가 SEMM을 관리 하 고 응용 프로그램으로 배포할 수 있습니다. 이 프로세스를 사용 하 여 구성 관리자에서 SEMM 관리를 수행 하므로 외부 Microsoft Surface UEFI 구성자 도구가 필요 하지 않습니다.

> [!Note]
> 이 문서에서 설명 하는 프로세스는 이전 버전의 끝점 구성 관리자나 다른 타사 관리 솔루션과 함께 사용할 수 있지만, Microsoft Surface UEFI 관리자와 PowerShell의 관리는 끝점 구성 관리자의 현재 분기 에서만 지원 됩니다.

#### 필수 구성 요소

이 문서에서 설명 하는 프로세스를 시작 하기 전에 다음 기술과 도구에 대해 숙지 하세요.

* [Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [Surface 엔터프라이즈 관리 모드(SEMM)](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [PowerShell 스크립트](https://technet.microsoft.com/scriptcenter/dd742419)
* [System Center Configuration Manager 응용 프로그램 배포](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* 인증서 관리

> [!Note]
> 또한, 사용 하려는 인증서에 대 한 액세스 권한이 필요 합니다 (SEMM). 이 인증서에 대 한 요구 사항에 대 한 자세한 내용은 [Surface 엔터프라이즈 관리 모드 인증서 요구 사항을](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)참조 하세요.
> 
> 이 인증서는 안전한 위치에 보관 하 고 제대로 백업 하는 것이 중요 합니다. 이 인증서가 손실 되거나 사용할 수 없게 되 면 Surface UEFI를 다시 설정 하거나, 관리 되는 표면 UEFI 설정을 변경 하거나, 등록 된 Surface 장치에서 SEMM을 제거 하는 것이 불가능 합니다.

#### Microsoft Surface UEFI 관리자 다운로드

Configuration Manager에서 SEMM을 관리 하려면 각 클라이언트 화면 장치에 Microsoft Surface UEFI 관리자를 설치 해야 합니다. Microsoft 다운로드 센터의 [IT 페이지에 대 한 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 MICROSOFT Surface UEFI 관리자 (SurfaceUEFIManager.msi)를 다운로드할 수 있습니다.

#### Configuration Manager에 대 한 SEMM 스크립트 다운로드

Microsoft Surface UEFI 관리자가 클라이언트 화면 장치에 설치 된 후에는 PowerShell 스크립트를 사용 하 여 배포 및 관리 됩니다. 다운로드 센터에서 [Semm 관리 스크립트](https://www.microsoft.com/download/details.aspx?id=46703) 의 샘플을 다운로드할 수 있습니다.

## Microsoft Surface UEFI 관리자 배포

Microsoft Surface UEFI 관리자의 배포는 일반적인 응용 프로그램 배포입니다. Microsoft Surface UEFI 관리자 설치 관리자 파일은 [표준 자동 옵션](https://msdn.microsoft.com/library/windows/desktop/aa367988)을 사용 하 여 설치할 수 있는 표준 Windows installer 파일입니다.

Microsoft Surface UEFI 관리자를 설치 하는 명령은 다음과 같습니다.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

Microsoft Surface UEFI 관리자를 제거 하는 명령은 다음과 같습니다.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

새 응용 프로그램을 만들고 Surface 장치를 포함 하는 컬렉션에 배포 하려면 다음 단계를 수행 합니다.

1. **시작** 화면이 나 **시작** 메뉴에서 Configuration Manager 콘솔을 엽니다.
2. 창의 왼쪽 아래 모서리에 있는 **소프트웨어 라이브러리** 를 선택 합니다.
3. 소프트웨어 라이브러리의 **응용 프로그램 관리** 노드를 확장 한 다음 **응용 프로그램**을 선택 합니다.
4. 창 위쪽의 **홈** 탭에서 **응용 프로그램 만들기** 단추를 선택 합니다. 그러면 응용 프로그램 만들기 마법사가 시작 됩니다.
5. 응용 프로그램 만들기 마법사는 일련의 단계를 제공 합니다.

   * **일반** – **이 응용 프로그램에 대 한 정보를 자동으로 설치 파일에서 검색** 옵션이 기본적으로 선택 되어 있습니다. **형식** 필드에서 **Windows Installer (.msi 파일)** 도 기본적으로 선택 되어 있습니다. **찾아보기를** 선택 하 여 이동 하 고 **SurfaceUEFIManagerSetup.msi**를 선택한 후 **다음**을 선택 합니다.
   
      > [!Note]
      > SurfaceUEFIManagerSetup.msi의 위치는 네트워크 공유에 있어야 하며 다른 파일을 포함 하지 않는 폴더에 위치 해야 합니다. 로컬 파일 위치를 사용할 수 없습니다.

   * **정보 가져오기** -응용 프로그램 만들기 마법사가 .msi 파일을 구문 분석 하 고 **응용 프로그램 이름** 및 **제품 코드**를 읽습니다. 그림 1에 나와 있는 것 처럼, SurfaceUEFIManagerSetup.msi는 라인 **컨텐트 파일**아래에 유일한 파일로 나열 되어야 합니다. 계속 하려면 **다음** 을 선택 합니다.

      ![Surface UEFI 관리자 설정의 정보는 자동으로 구문 분석 됩니다.](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *그림 1. Microsoft Surface UEFI Manager 설치 프로그램의 정보가 자동으로 구문 분석 됩니다.*

   * **일반 정보** -응용 프로그램의 이름 및 게시자 및 버전에 대 한 정보를 수정 하거나이 페이지에서 메모를 추가할 수 있습니다. Microsoft Surface UEFI 관리자의 설치 명령이 설치 프로그램 필드에 표시 됩니다. 시스템 설치의 기본 설치 동작을 통해 사용자가 Surface device에 로그온 되어 있지 않은 경우에도 Microsoft Surface UEFI 관리자가 SEMM에 필요한 어셈블리를 설치할 수 있습니다. 계속 하려면 **다음** 을 선택 합니다.
   * **요약** - **정보 가져오기** 단계에서 구문 분석 되 고 **일반 정보** 단계의 선택 내용이이 페이지에 표시 됩니다. 선택을 확인 하 고 응용 프로그램을 만들려면 **다음** 을 선택 합니다.
   * **진행률** -응용 프로그램을 가져와 소프트웨어 라이브러리에 추가할 때 진행률 표시줄과 상태를 표시 합니다.
   * **완료** – 응용 프로그램 만들기 프로세스가 완료 되 면 성공적인 응용 프로그램 만들기에 대 한 확인이 표시 됩니다. **닫기를** 선택 하 여 응용 프로그램 만들기 마법사를 완료 합니다.

구성 관리자에서 응용 프로그램을 만든 후 배포 지점에 배포 하 고 Surface 장치를 포함 하 여 컬렉션에 배포할 수 있습니다. 이 응용 프로그램은 Surface device에서 설치 하거나 사용 하지 않습니다. 이는 SEMM에 필요한 어셈블리만 PowerShell 스크립트를 사용 하 여 사용 하도록 하는 데만 제공 됩니다.

SEMM로 관리 되지 않는 장치에 Microsoft Surface UEFI 관리자 어셈블리를 설치 하지 않으려는 경우 Microsoft Surface UEFI 관리자를 SEMM 구성 관리자 스크립트의 종속성으로 구성할 수 있습니다. 이 시나리오는이 문서의 뒷부분에 나오는 [SEMM 구성 관리자 스크립트](#deploy-semm-configuration-manager-scripts) 섹션에 설명 되어 있습니다.

## SEMM 구성 관리자 스크립트 만들기 또는 수정

장치에 필요한 어셈블리가 설치 된 후에는 SEMM에 디바이스를 등록 하 고 Surface UEFI를 구성 하는 프로세스는 PowerShell 스크립트를 사용 하 여 수행 하 고 구성 관리자를 사용 하 여 스크립트 응용 프로그램으로 배포 됩니다. 이러한 스크립트는 조직과 환경의 필요에 맞게 수정할 수 있습니다. 예를 들어 다양 한 부서나 역할에 관리 되는 Surface 디바이스에 대 한 여러 구성을 만들 수 있습니다. 이 문서의 시작 부분에 있는 [필수 구성 요소](#prerequisites) 섹션의 링크에서 semm 및 Configuration Manager 스크립트의 샘플을 다운로드할 수 있습니다.

구성 관리자를 사용 하 여 SEMM 배포를 수행 하는 데 필요한 두 가지 주요 스크립트는 다음과 같습니다.

* **ConfigureSEMM.ps1** –이 스크립트를 사용 하 여 surface device에 대해 지정 된 설정을 적용 하 고, 디바이스를 semm에 등록 하 고, 디바이스의 등록을 식별 하는 데 사용 되는 레지스트리 키를 semm로 설정 합니다.
* **ResetSEMM.ps1** –이 스크립트를 사용 하 여 surface DEVICE에서 semm을 초기화 하 고, semm에서 등록을 취소 하 고, surface UEFI 설정에 대 한 컨트롤을 제거 합니다.

예제 스크립트에는 Surface UEFI 설정을 설정 하는 방법과 이러한 설정에 대 한 사용 권한을 제어 하는 방법에 대 한 예제가 포함 되어 있습니다. 이러한 설정을 수정 하 여 Surface UEFI를 보호 하 고 환경의 필요에 따라 Surface UEFI 설정을 설정할 수 있습니다. 이 문서의 다음 섹션에서는 ConfigureSEMM.ps1 스크립트에 대해 설명 하 고 요구 사항에 맞게 스크립트에 대해 수행 해야 하는 수정 사항을 알아봅니다.

> [!NOTE]
> SEMM 구성 관리자 스크립트와 내보낸 SEMM 인증서 파일 (.pfx)은 다른 파일이 없는 동일한 폴더에 배치 해야 Configuration Manager에 추가 됩니다.

### 인증서 및 패키지 이름 지정

수정 해야 하는 스크립트의 첫 번째 영역은 SEMM 인증서를 지정 하 고 로드 하는 부분으로, SurfaceUEFIManager 버전 및 SEMM 구성 패키지 및 SEMM 설정 패키지의 이름을 표시 합니다. 인증서 이름 및 SurfaceUEFIManager 버전은 ConfigureSEMM.ps1 스크립트의 56 ~ 73 줄에 지정 되어 있습니다.

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

**$CertName** 변수의 **FabrikamSEMMSample** 값을 58 줄의 semm 인증서 파일 이름으로 바꿉니다. 이 스크립트는 스크립트가 있는 폴더에 작업 디렉터리 (명명 된 Config)를 만든 다음이 작업 디렉토리에 인증서 파일을 복사 합니다.

소유자 패키지 및 재설정 패키지도 구성 디렉터리에 만들어지고,이 스크립트에서 생성 된 Surface UEFI 설정 및 사용 권한에 대 한 구성을 유지 합니다.

73 줄에서 **$password** 변수의 값을 **1234** 에서 인증서 파일의 암호로 바꿉니다. 암호가 필요 하지 않은 경우 **1234** 텍스트를 삭제 합니다.

> [!Note]
> 인증서 손도장의 마지막 두 문자는 디바이스를 SEMM에 등록 하는 데 필요 합니다. 이 스크립트는 사용자에 게 이러한 자리 숫자를 표시 하 여, 시스템을 다시 부팅 하기 전에 사용자 또는 기술자에 게 해당 숫자를 기록 하 여 장치를 SEMM에 등록할 수 있도록 합니다. 이 스크립트는 150-155 줄에 있는 다음 코드를 사용 하 여이를 수행 합니다.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

인증서 파일 (.pfx)에 대 한 액세스 권한이 있는 관리자는 CertMgr에서 .pfx 파일을 열어 언제 든 지 지문을 읽을 수 있습니다. CertMgr를 사용 하 여 지문을 보려면 다음 프로세스를 따르세요.

1. .Pfx 파일을 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.
2. 탐색 창에서 폴더를 확장 합니다.
3. **인증서**를 선택 합니다.
4. 기본 창에서 인증서를 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.
5. **세부 정보** 탭을 선택 합니다.
6. **표시** 드롭다운 메뉴에서 **모두** 또는 **속성만** 선택 해야 합니다.
7. 필드 **지문을**선택 합니다.

> [!NOTE]
> 구성 관리자가 제거 작업을 사용 하 여 디바이스에서 SEMM을 제거 하도록 설정 하려면 ResetSEMM.ps1 스크립트의이 섹션에 SEMM 인증서 이름과 암호를 입력 해야 합니다.

### 사용 권한 구성

Surface UEFI에 대 한 구성을 지정할 스크립트의 첫 번째 영역은 **사용 권한 구성** 영역입니다. 이 지역은 sample 스크립트의 210 줄에서 시작 하 여 **사용 권한을 구성** 하 고 계속 해 서 247 줄까지 유지 합니다. 다음 코드 조각에서는 먼저 모든 Surface UEFI 설정에 대 한 사용 권한을 설정 하 여 해당 사용자가 SEMM에 의해서만 수정할 수 있도록 하 고, 로컬 사용자가 Surface UEFI 암호, TPM, 프론트 및 후면 카메라를 수정할 수 있도록 하는 명시적 권한을 추가 합니다.

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

각 **$uefiV 2** 변수는 이름 또는 ID를 설정 하 여 Surface UEFI 설정을 식별 하 고 다음 값 중 하나로 사용 권한을 구성 합니다.

* **$ownerOnly** –이 설정을 수정할 수 있는 권한은 semm에만 부여 됩니다.
* **$ownerAndLocalUser** –이 설정을 수정할 수 있는 권한은 물론, Surface UEFI에 대 한 로컬 사용자 부팅 및 semm에 부여 됩니다.

이 문서의 [설정 이름 및 id](#settings-names-and-ids) 섹션에서 Surface UEFI에 대해 사용 가능한 설정 이름 및 id에 대 한 정보를 확인할 수 있습니다.

### 설정 구성

Surface UEFI에 대 한 구성을 지정할 스크립트의 두 번째 영역은 각 설정을 사용할지 여부를 구성 하는 ConfigureSEMM.ps1 스크립트의 설정 영역을 **구성** 하는 데 사용 됩니다. 샘플 스크립트에는 모든 설정을 기본값으로 설정 하는 지침이 포함 되어 있습니다. 그런 다음 스크립트는 PXE 부팅에 IPv6을 사용 하지 않도록 설정 하 고 Surface UEFI 관리자 암호를 변경 하지 않고 유지 하는 명시적인 지침을 제공 합니다. 이 지역은 샘플 스크립트의 291 줄에서 335 줄에 있는 **# 설정 설명 구성** 으로 시작 하 여 찾을 수 있습니다. 지역이 다음과 같이 표시 됩니다.

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

스크립트의 **사용 권한 구성** 섹션에 설정 된 권한과 마찬가지로, 각 표면 UEFI 설정의 구성은 **$uefiV 2** 변수를 정의 하 여 수행 됩니다. **$UefiV 2** 변수를 정의 하는 각 줄에 대해 Surface UEFI 설정은 설정 이름 또는 ID로 식별 되 고, 구성 된 값은 **Enabled** 또는 **Disabled**로 설정 됩니다.

Surface uefi 설정의 구성을 변경 하지 않으려는 경우, 예를 들어 모든 Surface UEFI 설정을 기본값으로 다시 설정 하는 작업으로 Surface UEFI 관리자 암호가 지워지지 않도록 하려면 **ClearConfiguredValue ()** 를 사용 하 여이 설정이 변경 되지 않도록 할 수 있습니다. 예제 스크립트에서이는 줄 323에서 설정 ID ( **501**)로 샘플 스크립트에서 식별 된 Surface UEFI 관리자 암호의 지우기를 방지 하는 데 사용 됩니다.

이 문서의 뒷부분에 나오는 [설정 이름 및 id](#settings-names-and-ids) 섹션에서 Surface UEFI에 대해 사용 가능한 설정 이름 및 id에 대 한 정보를 확인할 수 있습니다.

### 설정 레지스트리 키

구성 관리자의 등록 된 시스템을 식별 하기 위해 ConfigureSEMM.ps1 스크립트는 SEMM 구성 스크립트를 사용 하 여 등록 된 시스템을 식별 하는 데 사용할 수 있는 레지스트리 키를 작성 합니다. 이러한 키는 다음 위치에서 찾을 수 있습니다.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

380-477 줄에 있는 다음 코드 단편은 이러한 레지스트리 키를 작성 하는 데 사용 됩니다.

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### 설정 이름 및 Id

Surface uefi 설정 또는 Surface UEFI 설정에 대 한 사용 권한을 구성 하려면 각 설정을 해당 설정 이름 또는 설정 ID 중에서 참조 해야 합니다. Surface UEFI에 대 한 새로운 업데이트 각각에 대해 새 설정이 추가 될 수 있습니다. Surface 장치에서 사용할 수 있는 설정의 전체 목록 (설정 이름 및 설정 Id)을 가져오는 가장 좋은 방법은 [IT 다운로드에 대 한 Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 에서 SEMM_Powershell.zip의 ShowSettingsOptions.ps1 스크립트를 사용 하는 것입니다. 

ShowSettingsOptions.ps1를 실행 하는 컴퓨터에는 Microsoft Surface UEFI 관리자가 설치 되어 있어야 하지만, 스크립트에는 Surface device가 필요 하지 않습니다.


## SEMM 구성 관리자 스크립트 배포

클라이언트 장치에서 스크립트를 구성 하 고 사용할 준비가 되 면 다음 단계는 이러한 스크립트를 구성 관리자의 응용 프로그램으로 추가 하는 것입니다. 구성 관리자를 열기 전에 다음 파일이 다른 파일을 포함 하지 않는 공유 폴더에 있는지 확인 합니다.

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* SEMM 인증서 (예: SEMMCertificate. .pfx)

SEMM 구성 관리자 스크립트는 구성 관리자에 스크립트 응용 프로그램으로 추가 됩니다. ConfigureSEMM.ps1를 사용 하 여 SEMM을 설치 하는 명령은 다음과 같습니다.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

ResetSEMM.ps1를 사용 하 여 SEMM을 제거 하는 명령은 다음과 같습니다.

`Powershell.exe -file ".\ResetSEMM.ps1"`

구성 관리자에 SEMM 구성 관리자 스크립트를 응용 프로그램으로 추가 하려면 다음 프로세스를 사용 합니다.

1. 이 문서의 앞부분에 있는 [Microsoft SURFACE UEFI Manager 배포](#deploy-microsoft-surface-uefi-manager) 섹션의 1 ~ 5 단계를 사용 하 여 응용 프로그램 만들기 마법사를 시작 합니다.

2. 아래와 같이 응용 프로그램 만들기 마법사를 진행 합니다.

   - **일반** - **응용 프로그램 정보를 수동으로 지정**을 선택 하 고 **다음**을 선택 합니다.

   - **일반 정보** –이 페이지에서 응용 프로그램의 이름 (예: semm)과 publisher, 버전 또는 메모와 같은 기타 원하는 정보를 입력 합니다. 계속 하려면 **다음** 을 선택 합니다.

   - **Application Catalog** –이 페이지의 필드에 기본값을 적용할 수 있습니다. **다음**을 선택합니다.

   - **배포 유형** – **추가** 를 선택 하 여 배포 유형 만들기 마법사를 시작 합니다.

   - 다음과 같이 배포 형식 만들기 마법사의 단계를 진행 합니다.

     * **일반** - **형식** 드롭다운 메뉴에서 **스크립트 설치 관리자** 를 선택 합니다. **수동으로 배포 유형 정보 지정** 옵션이 자동으로 선택 됩니다. 계속 하려면 **다음** 을 선택 합니다.
     * **일반 정보** -배포 유형의 이름 (예: Semm 구성 스크립트)을 입력 하 고 **다음** 을 선택 하 여 계속 합니다.
     * **콘텐츠** – **콘텐츠 위치** 필드 옆에 있는 **찾아보기를** 선택한 다음 semm 구성 관리자 스크립트가 있는 폴더를 선택 합니다. **설치 프로그램** 필드에이 문서의 앞부분에 있는 [설치 명령을](#deploy-semm-configuration-manager-scripts) 입력 합니다. **프로그램 제거** 필드에이 문서의 앞부분에 있는 [제거 명령](#deploy-semm-configuration-manager-scripts) (그림 2에 표시 됨)을 입력 합니다. 다음 **을 선택 하** 여 다음 페이지로 이동 합니다.
    
     ![SEMM 구성 관리자 스크립트를 설치 및 제거 명령으로 설정 합니다.](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *그림 2. SEMM 구성 관리자 스크립트를 설치 및 제거 명령으로 설정 합니다.*

     * **감지 메서드** – Semm 구성 관리자 스크립트 레지스트리 키 검색 규칙을 추가 하려면 **절 추가** 를 선택 합니다. 그림 3과 같이 **검색 규칙** 창이 표시 됩니다. 다음 설정을 사용합니다.

       - **설정 유형** 드롭다운 메뉴에서 **레지스트리** 를 선택 합니다.
       - **하이브** 드롭다운 메뉴에서 **HKEY_LOCAL_MACHINE** 를 선택 합니다.
       - **키** 필드에 **SOFTWARE\Microsoft\Surface\SEMM** 를 입력 합니다.
       - **값** 필드에 **CertName** 를 입력 합니다.
       - **데이터 형식** 드롭다운 메뉴에서 **문자열** 을 선택 합니다.
       - 이 **앱의 현재 상태를 표시 하려면이 레지스트리 설정을 다음 규칙에 맞아야 합니다 .를 선택 합니다** .
       - **값** 필드에서 스크립트의 58 줄에 입력 한 인증서의 이름을 입력 합니다.
       - **확인** 을 선택 하 여 **검색 규칙** 창을 닫습니다.

     ![레지스트리 키를 사용 하 여 SEMM에 등록 된 장치 식별](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *그림 3. 레지스트리 키를 사용 하 여 SEMM에 등록 된 장치 식별*

     * 다음 **을 선택 하** 여 다음 페이지로 이동 합니다.
     
     * **사용자 환경** - **설치 동작** 드롭다운 메뉴에서 **시스템에 대 한 설치** 를 선택 합니다. 사용자가 인증서 지문 자체를 기록 하 고 입력 하도록 하려면 **사용자가 로그온 할 때만**로그온 요구 사항을 설정 된 상태로 둡니다. 관리자가 사용자에 대 한 지문을 입력 하 고 사용자가 지문을 볼 필요가 없도록 하려면 **로그온 요구 사항** 드롭다운 메뉴에서 **사용자가 로그온 되었는지 여부** 를 선택 합니다.

     * **요구 사항** – ConfigureSEMM.ps1 스크립트는 장치가 Surface device가 자동으로 확인 된 후 semm을 사용 하도록 설정 합니다. 그러나 SEMM을 사용 하 여 관리 하지 않는 장치를 사용 하 여이 스크립트 응용 프로그램을 컬렉션에 배포 하려는 경우 여기에 요구 사항을 추가 하 여이 응용 프로그램이 관리 하려는 Surface 장치 또는 디바이스 에서만 실행 되도록 할 수 있습니다. **Next (다음** )를 선택 하 여 계속 합니다.
     
     * **종속성** – **추가** 를 선택 하 여 **종속성 추가** 창을 엽니다.

       * **추가** 를 선택 하 여 **필요한 응용 프로그램 지정** 창을 엽니다.

          - **종속성 그룹 이름** 필드에 semm 종속성의 이름을 입력 합니다 (예: *semm 어셈블리*).

          - **사용할 수 있는 응용 프로그램** 및 MSI 배포 유형 목록에서 **Microsoft Surface UEFI 관리자** 를 선택한 다음 **확인** 을 선택 하 여 **필요한 응용 프로그램 지정** 창을 닫습니다.
          
         *   Configuration Manager 스크립트를 사용 하 여 SEMM을 설정 하려고 할 때 장치에 Microsoft Surface UEFI 관리자가 자동으로 설치 되도록 하려면 **자동 설치** 확인란을 선택 합니다. **확인** 을 선택 하 여 **종속성 추가** 창을 닫습니다.

     * 계속 하려면 **다음** 을 선택 합니다.
     
     * **요약** -배포 형식 만들기 마법사에서 입력 한 정보가이 페이지에 표시 됩니다. 선택을 확인 하려면 **다음** 을 선택 합니다.
     
     * **진행률** – semm 스크립트 응용 프로그램에 대 한 배포 유형을 추가 하는 진행률 표시줄과 상태가이 페이지에 표시 됩니다.
     
     * **완료** – 프로세스가 완료 되 면 배포 유형 만들기에 대 한 확인이 표시 됩니다. **닫기를** 선택 하 여 배포 유형 만들기 마법사를 완료 합니다.

   - **요약** -응용 프로그램 만들기 마법사에서 입력 한 정보가 표시 됩니다. **다음** 을 선택 하 여 응용 프로그램을 만듭니다.

   - **진행률** – 응용 프로그램이 소프트웨어 라이브러리에 추가 되는 진행률 표시줄과 상태가이 페이지에 표시 됩니다.

   - **완료** – 응용 프로그램 만들기 프로세스가 완료 되 면 성공적인 응용 프로그램 만들기에 대 한 확인이 표시 됩니다. **닫기를** 선택 하 여 응용 프로그램 만들기 마법사를 완료 합니다.

구성 관리자의 소프트웨어 라이브러리에서 스크립트 응용 프로그램을 사용할 수 있게 되 면 장치 또는 컬렉션에 준비한 스크립트를 사용 하 여 SEMM을 배포 하 고 배포할 수 있습니다. Microsoft Surface UEFI 관리자 어셈블리를 자동으로 설치 되는 종속성으로 구성한 경우에는 한 번에 SEMM을 배포할 수 있습니다. 어셈블리를 종속성으로 구성 하지 않은 경우 SEMM을 설정 하기 전에 관리 하려는 장치에 설치 되어 있어야 합니다.

이 스크립트 응용 프로그램을 사용 하 고 최종 사용자에 게 표시 되는 구성으로 SEMM을 배포 하면 PowerShell 스크립트가 시작 되 고 PowerShell 창에 해당 인증서의 지문이 표시 됩니다. 장치를 다시 부팅 한 후 Surface UEFI에서 메시지가 표시 되 면 사용자가이 지문을 기록 하 여 입력 하도록 할 수 있습니다.

또는 자동으로 다시 부팅 하 고 사용자에 게 표시 되지 않는 설치 하도록 응용 프로그램 설치를 구성할 수 있습니다. 이 시나리오에서 기술자는 다시 부팅 하면 각 장치에 지문을 입력 해야 합니다. 인증서 파일에 대 한 액세스 권한이 있는 모든 기술자는 CertMgr를 사용 하 여 인증서를 보고 지문을 읽을 수 있습니다. CertMgr를 사용 하 여 지문을 보는 방법에 대 한 지침은이 문서의 [SEMM Configuration Manager 스크립트 만들기 또는 수정](#create-or-modify-the-semm-configuration-manager-scripts) 섹션을 참고 하세요.

이 스크립트를 사용 하 여 구성 관리자로 배포 된 장치에서 SEMM을 제거 하는 것은 구성 관리자로 응용 프로그램을 제거 하는 것 만큼 간단 합니다. 이 작업은 ResetSEMM.ps1 스크립트를 시작 하 고 SEMM 배포 중에 사용 된 것과 동일한 인증서 파일을 사용 하 여 장치를 올바르게 등록 취소 합니다.

> [!NOTE]
> 장치를 등록을 해제 해야 하는 경우에만 다시 설정 패키지를 만드는 것이 좋습니다. 이러한 재설정 패키지는 일반적으로 하나의 디바이스에 대해서만 유효 하며 일련 번호로 식별 됩니다. 그러나이 인증서를 사용 하 여 SEMM에 등록 된 모든 장치에서 작동 하는 범용 재설정 패키지를 만들 수 있습니다.
> 
> 유니버설 재설정 패키지는 디바이스를 등록 하는 데 사용한 인증서의 경우에 따라 신중 하 게 보호 하는 것이 좋습니다 (SEMM). 인증서 자체와 마찬가지로,이 범용 재설정 패키지를 사용 하 여 조직의 Surface 디바이스를 SEMM에서 등록을 해제 합니다.
> 
> 다시 설정 패키지를 설치할 때 지원 되는 최저 값 (LSV)은 값 1로 다시 설정 됩니다. 기존 구성 패키지를 사용 하 여 디바이스를 reenroll 수 있습니다. 장치가 소유권을 가져오기 전에 인증서 지문을 입력 하 라는 메시지가 표시 됩니다.
> 
> 이러한 이유로 SEMM의 디바이스 reenrollment 해당 장치에 새 패키지를 만들고 설치 해야 합니다. 이 작업은 새 등록 이므로 SEMM로 등록 된 디바이스의 구성은 변경 되지 않으므로, 소유권을 가져오기 전에 장치에서 인증서 지문을 확인 하 라는 메시지가 표시 됩니다.
