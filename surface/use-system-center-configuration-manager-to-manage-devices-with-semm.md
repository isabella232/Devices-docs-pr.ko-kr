---
title: Microsoft Endpoint Configuration Manager를 사용하여 SEMM에서 디바이스 관리
description: Endpoint Configuration Manager를 사용하여 SEMM(Microsoft Surface Enterprise 관리 모드)을 관리하는 방법을 알아보십시오.
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
ms.openlocfilehash: 9f3db9428e188aa20399d26c066507d76c90ba57
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708789"
---
# <a name="use-microsoft-endpoint-configuration-manager-to-manage-devices-with-semm"></a>Microsoft Endpoint Configuration Manager를 사용하여 SEMM에서 디바이스 관리

Microsoft Surface Enterprise SEMM(관리 모드) 기능을 사용하면 관리자가 Surface UEFI 설정의 구성을 관리하고 보호할 수 있습니다. 대부분의 조직에서 이 프로세스는 Microsoft Surface UEFI 구성 도구로 Windows 설치 관리자(.msi) 패키지를 만들어 수행됩니다. 그런 다음 이러한 패키지를 실행하거나 클라이언트 Surface 디바이스에 배포하여 SEMM에 장치를 등록하고 Surface UEFI 설정 구성을 업데이트합니다.

조직에 Microsoft Endpoint Configuration Manager Microsoft Surface UEFI 구성기 구성기 프로세스를 사용하여 SEMM을 배포하고 .msi 대신 사용할 수 있습니다. Microsoft Surface UEFI Manager는 장치에서 SEMM 관리에 필요한 어셈블리를 사용할 수 있도록 하는 간단한 설치 관리자입니다. 관리되는 클라이언트에 Microsoft Surface UEFI 관리자를 사용하여 이러한 어셈블리를 설치하면 Configuration Manager에서 응용 프로그램으로 배포된 PowerShell 스크립트를 사용하여 SEMM을 관리할 수 있습니다. 이 프로세스를 통해 SEMM 관리는 Configuration Manager 내에서 수행되어 외부 Microsoft Surface UEFI 구성 도구가 필요하지 않습니다.

> [!Note]
> 이 문서에 설명된 프로세스는 이전 버전의 Endpoint Configuration Manager 또는 다른 타사 관리 솔루션에서 작동하지만 Microsoft Surface UEFI 관리자 및 PowerShell을 통해 SEMM 관리는 Endpoint Configuration Manager의 현재 분기에서만 지원됩니다.

#### <a name="prerequisites"></a>필수 구성 요소

이 문서에 설명된 프로세스를 시작하기 전에 다음 기술 및 도구에 익숙해지십시오.

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Surface 엔터프라이즈 관리 모드(SEMM)](surface-enterprise-management-mode.md)
* [PowerShell 스크립팅](/powershell)
* [Configuration Manager를 통해 응용 프로그램 배포](/mem/configmgr/apps/deploy-use/deploy-applications)


> [!Note]
> 또한 SEMM을 보호하는 데 사용할 인증서에 액세스해야 합니다. 이 인증서의 요구 사항에 대한 자세한 내용은 Surface Enterprise 관리 모드 인증서 요구 [사항을 참조하세요.](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements)
> 
> 이 인증서는 안전한 위치에 보관하고 제대로 백업해야 합니다. 이 인증서를 분실하거나 사용할 수 없는 경우 Surface UEFI를 초기화하거나, 관리되는 Surface UEFI 설정을 변경하거나, 등록된 Surface 디바이스에서 SEMM을 제거할 수 없습니다.

#### <a name="download-microsoft-surface-uefi-manager"></a>Microsoft Surface UEFI 관리자 다운로드

Configuration Manager를 사용하여 SEMM을 관리하려면 각 클라이언트 Surface 디바이스에 Microsoft Surface UEFI 관리자를 설치해야 합니다. Microsoft Surface UEFI 관리자(SurfaceUEFIManager.msi)는 Microsoft 다운로드 센터의 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 다운로드할 수 있습니다.

#### <a name="download-semm-scripts-for-configuration-manager"></a>Configuration Manager용 SEMM 스크립트 다운로드

Microsoft Surface UEFI 관리자를 클라이언트 Surface 디바이스에 설치한 후 PowerShell 스크립트를 사용하여 SEMM을 배포하고 관리할 수 있습니다. SURFACE Tools for IT에서 앱을 다운로드하여 [SEMM](https://www.microsoft.com/download/details.aspx?id=46703) SEMM_PowerShell.zip 샘플을 다운로드합니다.

## <a name="deploy-microsoft-surface-uefi-manager"></a>Microsoft Surface UEFI 관리자 배포

Microsoft Surface UEFI 관리자의 배포는 일반적인 응용 프로그램 배포입니다. Microsoft Surface UEFI 관리자 설치 관리자 파일은 표준 Windows 옵션으로 설치할 수 있는 표준 설치 관리자 [파일입니다.](https://msdn.microsoft.com/library/windows/desktop/aa367988)

Microsoft Surface UEFI 관리자를 설치하는 명령은 다음과 같습니다.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

Microsoft Surface UEFI 관리자를 제거하는 명령은 다음과 같습니다.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

새 응용 프로그램을 만들고 Surface 디바이스가 포함된 컬렉션에 배포하기 위해 다음 단계를 수행합니다.

1. 시작 화면 또는 **** 시작 메뉴에서 Configuration Manager **콘솔을 갑니다.**
2. 창의 **왼쪽** 아래 모서리에 있는 소프트웨어 라이브러리를 선택합니다.
3. 소프트웨어 **라이브러리의 응용** 프로그램 관리 노드를 확장한 다음 응용 프로그램 을 **선택합니다.**
4. 창 **위쪽의** 홈 **** 탭에서 응용 프로그램 만들기 단추를 선택합니다. 그러면 응용 프로그램 만들기 마법사가 시작됩니다.
5. 응용 프로그램 만들기 마법사에서는 다음 일련의 단계를 제공합니다.

   * **일반** – **설치 파일에서** 이 응용 프로그램에 대한 정보 자동 검색 옵션이 기본적으로 선택되어 있습니다. 유형 **필드에서** Windows **설치 관리자(.msi 파일)도** 기본적으로 선택되어 있습니다. **찾아보기를** 선택하여 으로 이동한SurfaceUEFIManagerSetup.msi를 선택한 후 다음 **을 ** **선택합니다.**
   
      > [!Note]
      > 네트워크 SurfaceUEFIManagerSetup.msi 다른 파일이 없는 폴더에 있어야 합니다. 로컬 파일 위치를 사용할 수 없습니다.

   * **정보 가져오기** – 응용 프로그램 만들기 마법사가 응용 프로그램 **** .msi 구문 분석하고 응용 프로그램 이름 및 제품 **코드를 읽습니다.** SurfaceUEFIManagerSetup.msi 내용은 그림 1과 같이 콘텐츠 **** 파일 줄에서 유일한 파일로 나열해야 합니다. 계속하려면 **다음을** 선택합니다.

      ![Surface UEFI 관리자 설정의 정보가 자동으로 구문 분석됩니다.](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *그림 1. Microsoft Surface UEFI 관리자 설치의 정보가 자동으로 구문 분석됩니다.*

   * **일반 정보** – 응용 프로그램의 이름과 게시자 및 버전에 대한 정보를 수정하거나 이 페이지에 설명을 추가할 수 있습니다. Microsoft Surface UEFI 관리자의 설치 명령이 설치 프로그램 필드에 표시됩니다. 시스템에 설치의 기본 설치 동작은 사용자가 Surface 디바이스에 로그온되어 있지 않은 경우에도 Microsoft Surface UEFI 관리자가 SEMM에 필요한 어셈블리를 설치할 수 있도록 합니다. 계속하려면 **다음을** 선택합니다.
   * **요약** - 정보 가져오기 단계에서 구문 분석된 정보와 일반 **** 정보 단계의 선택 영역이 이 페이지에 표시됩니다. **** **다음을** 선택하여 선택을 확인하고 응용 프로그램을 만들 수 있습니다.
   * **진행률** - 응용 프로그램을 가져와 소프트웨어 라이브러리에 추가할 때 진행률 표시줄과 상태를 표시됩니다.
   * **완료** - 응용 프로그램 만들기 프로세스가 완료되면 응용 프로그램을 성공적으로 만들 수 있는지 확인이 표시됩니다. 닫기 **를** 선택하여 응용 프로그램 만들기 마법사를 완료합니다.

Configuration Manager에서 응용 프로그램을 만든 후 배포 지점에 배포하고 Surface 디바이스를 포함한 컬렉션에 배포할 수 있습니다. 이 응용 프로그램은 Surface 디바이스에 SEMM을 설치하거나 사용하도록 설정하지 않습니다. PowerShell 스크립트를 사용하여 SEMM을 사용하도록 설정하는 데 필요한 어셈블리만 제공합니다.

SEMM으로 관리되지 않는 장치에 Microsoft Surface UEFI 관리자 어셈블리를 설치하지 않을 경우 Microsoft Surface UEFI 관리자를 SEMM 구성 관리자 스크립트의 종속성으로 구성할 수 있습니다. 이 시나리오는 이 문서 의 부분에 있는 [SEMM 구성](#deploy-semm-configuration-manager-scripts) 관리자 스크립트 배포 섹션에 설명되어 있습니다.

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a>SEMM Configuration Manager 스크립트 만들기 또는 수정

디바이스에 필요한 어셈블리를 설치한 후 SeMM에 장치를 등록하고 Surface UEFI를 구성하는 프로세스는 PowerShell 스크립트를 사용하여 수행되고 Configuration Manager를 사용하여 스크립트 응용 프로그램으로 배포됩니다. 이러한 스크립트는 조직 및 환경의 요구에 맞게 수정할 수 있습니다. 예를 들어 여러 부서나 역할에서 관리되는 Surface 디바이스에 대해 여러 구성을 만들 수 있습니다. 이 문서의 시작 부분의 [Prerequisites](#prerequisites) 섹션에 있는 링크에서 SEMM 및 Configuration Manager용 스크립트 샘플을 다운로드할 수 있습니다.

Configuration Manager를 사용하여 SEMM 배포를 수행하기 위해 필요한 두 가지 기본 스크립트가 있습니다.

* **ConfigureSEMM.ps1** – 원하는 Surface UEFI 설정을 사용하여 Surface 디바이스에 지정된 설정을 적용하고, SEMM에 장치를 등록하고, SEMM에서 디바이스 등록을 식별하는 데 사용되는 레지스트리 키를 설정하기 위해 이 스크립트를 사용하여 Surface 디바이스에 대한 구성 패키지를 만들 수 있습니다.
* **ResetSEMM.ps1** – 이 스크립트를 사용하여 Surface 디바이스에서 SEMM을 초기화합니다. 이 스크립트를 사용하여 SEMM에서 SEMM을 제거하고 Surface UEFI 설정에 대한 컨트롤을 제거합니다.

샘플 스크립트에는 Surface UEFI 설정을 설정하는 방법과 이러한 설정에 대한 사용 권한을 제어하는 방법의 예가 포함되어 있습니다. 이러한 설정을 수정하여 Surface UEFI를 보호하고 환경의 요구에 따라 Surface UEFI 설정을 설정할 수 있습니다. 이 문서의 다음 섹션에서는 ConfigureSEMM.ps1 스크립트를 설명하고 요구 사항에 맞게 스크립트에 필요한 수정 사항을 살펴보십시오.

> [!NOTE]
> SEMM Configuration Manager 스크립트와 내보낼 SEMM 인증서 파일(.pfx)은 Configuration Manager에 추가되기 전에 다른 파일이 없는 동일한 폴더에 배치해야 합니다.

### <a name="specify-certificate-and-package-names"></a>인증서 및 패키지 이름 지정

수정해야 하는 스크립트의 첫 번째 영역은 SEMM 인증서를 지정하고 로드하는 부분으로, SurfaceUEFIManager 버전과 SEMM 구성 패키지 및 SEMM 재설정 패키지의 이름을 나타냅니다. 인증서 이름 및 SurfaceUEFIManager 버전은 스크립트의 56줄에서 73줄에 ConfigureSEMM.ps1 지정됩니다.

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

$certName 변수의 **FabrikamSEMMSample.pfx** 값을 줄 58에 있는 SEMM 인증서 파일의 이름으로 바니다. **** 스크립트는 스크립트가 있는 폴더에 작업 디렉터리(Config)를 만든 다음 인증서 파일을 이 작업 디렉터리에 복사합니다.

소유자 패키지 및 재설정 패키지도 Config 디렉터리에 만들어지며 스크립트에서 생성된 Surface UEFI 설정 및 사용 권한에 대한 구성을 보유합니다.

줄 73에서 $password 변수의 **** 값을 **1234에서** 인증서 파일의 암호로 바니다. 암호가 필요하지 않은 경우 **1234** 텍스트를 삭제합니다.

> [!Note]
> SEMM에서 장치를 등록하려면 인증서 지문의 마지막 두 문자가 필요합니다. 이 스크립트는 사용자에게 이러한 숫자를 표시하여 시스템 재부팅 전에 이러한 숫자를 기록할 수 있도록 하여 SEMM에 장치를 등록합니다. 스크립트는 이 작업을 수행하기 위해 150-155 줄에 있는 다음 코드를 사용 합니다.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

인증서 파일(.pfx)에 액세스할 수 있는 관리자는 CertMgr에서 .pfx 파일을 열면 지문을 읽을 수 있습니다. CertMgr로 지문을 보시다가 다음 프로세스를 수행하십시오.

1. .pfx 파일을 마우스 오른쪽 단추로 클릭한 다음 열기 **를 선택합니다.**
2. 탐색 창에서 폴더를 확장합니다.
3. 인증서를 **선택합니다.**
4. 주 창에서 인증서를 마우스 오른쪽 단추로 클릭한 다음 열기 를 **선택합니다.**
5. 세부 **정보 탭을** 선택합니다.
6. **모두** 또는 **속성만** 표시 **** 드롭다운 메뉴에서 선택해야 합니다.
7. 지문 **필드를 선택합니다.**

> [!NOTE]
> Configuration Manager가 제거 작업을 통해 장치에서 SEMM을 제거할 수 있도록 ResetSEMM.ps1 스크립트의 이 섹션에도 SEMM 인증서 이름과 암호를 입력해야 합니다.

### <a name="configure-permissions"></a>사용 권한 구성

Surface UEFI에 대한 구성을 지정할 스크립트의 첫 번째 영역은 사용 권한 구성 **영역입니다.** 이 영역은 #Configure **Permissions** 주석이 있는 샘플 스크립트의 줄 210에서 시작하여 247줄로 계속됩니다. 다음 코드 조각은 먼저 SEMM에서만 수정할 수 있도록 모든 Surface UEFI 설정에 대한 사용 권한을 설정한 다음 로컬 사용자가 Surface UEFI 암호, TPM 및 전면 및 후면 카메라를 수정할 수 있도록 명시적 권한을 추가합니다.

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

각 **$uefiV 2** 변수는 이름 또는 ID를 설정하여 Surface UEFI 설정을 식별한 다음 다음 값 중 하나에 대한 사용 권한을 구성합니다.

* **$ownerOnly** – 이 설정을 수정할 수 있는 권한은 SEMM에만 부여됩니다.
* **$ownerAndLocalUser** – 이 설정을 수정할 수 있는 권한은 SeMM뿐만 아니라 Surface UEFI로 부팅되는 로컬 사용자에게 부여됩니다.

Surface UEFI에 사용할 수 있는 설정 이름 및 ID에 대한 정보는 이 문서의 설정 및 [ID 섹션에서](#settings-names-and-ids) 찾을 수 있습니다.

### <a name="configure-settings"></a>설정 구성

Surface UEFI에 대한 구성을 지정할 스크립트의 두 **** 번째 영역은 각 설정을 사용할지 여부를 구성하는 ConfigureSEMM.ps1 스크립트의 구성 설정 영역입니다. 샘플 스크립트에는 모든 설정을 기본값으로 설정하는 지침이 포함되어 있습니다. 그런 다음 이 스크립트는 PXE 부팅에 대해 IPv6을 사용하지 않도록 설정하고 Surface UEFI 관리자 암호를 변경하지 않는 명시적 지침을 제공합니다. 샘플 스크립트에서 줄 **291에서** 335까지의 #설정 설명 구성으로 시작되는 이 지역을 찾을 수 있습니다. 영역이 다음과 같이 표시됩니다.

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

스크립트의 **사용** 권한 구성 섹션에 설정된 사용 권한과 마찬가지로 각 Surface UEFI 설정의 구성은 $uefiV 2 변수를 **정의하여** 수행됩니다. **$uefiV 2** 변수를 정의하는 각 줄에 대해 Surface UEFI 설정은 이름 또는 ID를 설정하여 식별하고 구성된 값은 **Enabled** 또는 **Disabled로 설정됩니다.**

예를 들어 모든 Surface UEFI 설정을 기본값으로 다시 설정하여 Surface UEFI 관리자 암호가 지워지지 않도록 하는 등 Surface UEFI 설정의 구성을 변경하지 않을 경우 **ClearConfiguredValue()를** 사용하여 이 설정이 변경되지 않도록 적용할 수 있습니다. 샘플 스크립트에서는 323 줄에서 설정 ID인 **501**으로 샘플 스크립트에서 식별된 Surface UEFI 관리자 암호를 지우지 못하게 하는 데 사용됩니다.

Surface UEFI에 사용할 수 있는 설정 이름 및 ID에 대한 자세한 내용은 이 문서 의 부분에 있는 설정 및 [ID 섹션에서](#settings-names-and-ids) 찾을 수 있습니다.

### <a name="settings-registry-key"></a>설정 레지스트리 키

Configuration Manager에 등록된 시스템을 식별하기 위해 ConfigureSEMM.ps1 스크립트는 등록된 시스템을 SEMM 구성 스크립트와 함께 설치한 것으로 식별하는 데 사용할 수 있는 레지스트리 키를 작성합니다. 이러한 키는 다음 위치에서 찾을 수 있습니다.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

380-477 줄에 있는 다음 코드 조각을 사용하여 이러한 레지스트리 키를 작성합니다.

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

### <a name="settings-names-and-ids"></a>설정 및 ID

Surface UEFI 설정에 대한 Surface UEFI 설정 또는 사용 권한을 구성하려면 각 설정을 해당 설정 이름 또는 설정 ID로 참조해야 합니다. Surface UEFI에 대한 새 업데이트가 있을 때마다 새 설정이 추가될 수 있습니다. IT ShowSettingsOptions.ps1 도구의 SEMM_Powershell.zip 스크립트를 [실행하면](https://www.microsoft.com/download/details.aspx?id=46703)사용 가능한 설정에 대한 세부 정보가 제공됩니다. 실행되는 ShowSettingsOptions.ps1 Microsoft Surface UEFI Manager가 설치되어 있어야 하지만 스크립트에 Surface 디바이스가 필요하지 않습니다.


## <a name="deploy-semm-configuration-manager-scripts"></a>SEMM Configuration Manager 스크립트 배포

스크립트가 클라이언트 장치에서 SEMM을 구성하고 사용하도록 설정할 준비가 된 후 다음 단계는 Configuration Manager에서 이러한 스크립트를 응용 프로그램으로 추가하는 것입니다. Configuration Manager를 열기 전에 다음 파일이 다른 파일을 포함하지 않는 공유 폴더에 포함되어야 합니다.

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* SEMM 인증서(예: SEMMCertificate.pfx)

SEMM Configuration Manager 스크립트는 Configuration Manager에 스크립트 응용 프로그램으로 추가됩니다. 다음 명령과 함께 SEMM을 ConfigureSEMM.ps1 명령은 다음과 같습니다.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

다음 명령을 사용하여 SEMM을 ResetSEMM.ps1 명령은 다음과 같습니다.

`Powershell.exe -file ".\ResetSEMM.ps1"`

CONFIGURATION Manager에 SEMM Configuration Manager 스크립트를 응용 프로그램으로 추가하려면 다음 프로세스를 사용 합니다.

1. 이 문서 앞부분의 [Microsoft Surface UEFI](#deploy-microsoft-surface-uefi-manager) 관리자 배포 섹션에서 1~5단계를 사용하여 응용 프로그램 만들기 마법사를 시작하십시오.

2. 다음과 같이 응용 프로그램 만들기 마법사를 진행합니다.

   - **일반** – **수동으로 응용 프로그램 정보 지정을 선택하고**다음 을 **선택합니다.**

   - **일반 정보** – 응용 프로그램의 이름(예: SEMM) 및 이 페이지의 게시자, 버전 또는 설명과 같은 기타 정보를 입력합니다. 계속하려면 **다음을** 선택합니다.

   - **응용 프로그램 카탈로그** - 이 페이지의 필드를 기본값으로 남겨 두면 됩니다. **다음**을 선택합니다.

   - **배포 유형** – **추가를** 선택하여 배포 유형 만들기 마법사를 시작하십시오.

   - 다음과 같이 배포 유형 만들기 마법사의 단계를 진행합니다.

     * **일반** – 유형 **드롭다운 메뉴에서** **스크립트** 설치 관리자를 선택합니다. 배포 **유형 정보 수동** 지정 옵션이 자동으로 선택됩니다. 계속하려면 **다음을** 선택합니다.
     * **일반 정보** – 배포 유형의 이름(예: SEMM 구성 스크립트)을 입력한 후 다음을 **선택하여** 계속합니다.
     * **콘텐츠** – **콘텐츠** 위치 **** 필드 옆에 있는 찾아보기를 선택한 다음 SEMM 구성 관리자 스크립트가 있는 폴더를 선택합니다. 설치 **프로그램 필드에** 이 [](#deploy-semm-configuration-manager-scripts) 문서 앞부분에 있는 설치 명령을 입력합니다. 프로그램 **제거 필드에** 이 문서의 [](#deploy-semm-configuration-manager-scripts) 앞부분에 있는 제거 명령을 입력합니다(그림 2에 표시). **다음을** 선택하여 다음 페이지로 이동합니다.
    
     ![SEMM Configuration Manager 스크립트를 설치 및 제거 명령으로 설정](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *그림 2. SEMM Configuration Manager 스크립트를 설치 및 제거 명령으로 설정*

     * **검색 방법** – **절 추가를** 선택하여 SEMM Configuration Manager 스크립트 레지스트리 키 검색 규칙을 추가합니다. 그림 **3과 같이** 검색 규칙 창이 표시됩니다. 다음 설정을 사용합니다.

       - 설정 **유형 드롭다운** **메뉴에서** 레지스트리를 선택합니다.
       - Hive **HKEY_LOCAL_MACHINE** 메뉴에서 **** 선택을 선택합니다.
       - 키 **필드에 SOFTWARE\Microsoft\Surface\SEMM을** **입력합니다.**
       - 값 **필드에 CertName을** **입력합니다.**
       - 데이터 **형식 드롭다운** **메뉴에서 문자열을** 선택합니다.
       - 이 레지스트리 설정은 다음 규칙을 충족해야 이 응용 프로그램 단추가 **존재할 수 있습니다.를** 선택합니다.
       - 값 필드에 스크립트의 줄 58에 입력한 인증서의 이름을 **입력합니다.**
       - **확인을** 선택하여 검색 규칙 **창을 닫습니다.**

     ![레지스트리 키를 사용하여 SEMM에 등록된 장치 식별](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *그림 3. 레지스트리 키를 사용하여 SEMM에 등록된 장치 식별*

     * **다음을** 선택하여 다음 페이지로 이동합니다.
     
     * **사용자 환경** – 설치 동작 **** **드롭다운** 메뉴에서 시스템에 설치를 선택합니다. 사용자가 직접 인증서 지문을 기록하고 입력하도록 하려는 경우 로그온 요구 사항을 사용자가 로그온한 경우만으로 **설정해야 합니다.** 관리자가 사용자의 지문을 입력하도록 하고 사용자에게 지문을 볼 필요가 없는 경우 **** 로그온 요구 사항 드롭다운 **** 메뉴에서 사용자가 로그온되어 있는지 여부를 선택합니다.

     * **요구** 사항 – ConfigureSEMM.ps1 스크립트는 SEMM을 사용하도록 설정하기 전에 디바이스가 Surface 장치임이 자동으로 확인됩니다. 그러나 이 스크립트 응용 프로그램을 SEMM을 사용하여 관리해야 하는 디바이스가 아니라 다른 디바이스가 있는 컬렉션에 배포하려는 경우 여기에 요구 사항을 추가하여 이 응용 프로그램이 SEMM을 사용하여 관리하려는 Surface 디바이스 또는 디바이스에서만 실행되도록 할 수 있습니다. 계속하려면 **다음을** 선택합니다.
     
     * **종속성** – **추가를** 선택하여 종속성 추가 **창을 열** 수 있습니다.

       * 추가를 선택하여 필수 응용 프로그램 **지정 창을 열** 수 있습니다. ****

          - 종속성 그룹 이름 필드에 SEMM **** 종속성의 이름을 입력합니다(예: *SEMM 어셈블리).*

          - 사용 가능한 응용 프로그램 및 MSI 배포 유형 목록에서 Microsoft Surface **** **UEFI 관리자를** 선택한 다음 확인을 선택하여 필수 응용 프로그램 지정 **창을 닫습니다.** ****
          
         *   Configuration **** Manager 스크립트를 사용하여 SEMM을 사용하도록 설정하려고 할 때 장치에 Microsoft Surface UEFI Manager를 자동으로 설치하려면 자동 설치 확인란을 선택된 것으로 유지하십시오. 확인을 **선택하여** 종속성 추가 **창을 닫습니다.**

     * 계속하려면 **다음을** 선택합니다.
     
     * **요약** - 배포 유형 만들기 마법사 전체에 입력한 정보가 이 페이지에 표시됩니다. **선택을** 확인하려면 다음을 선택합니다.
     
     * **진행률** - SEMM 스크립트 응용 프로그램에 대한 배포 유형이 추가될 때 진행률 표시줄 및 상태가 이 페이지에 표시됩니다.
     
     * **완료** - 프로세스가 완료되면 배포 유형 만들기 확인이 표시됩니다. 닫기 **를** 선택하여 배포 유형 만들기 마법사를 완료합니다.

   - **요약** - 응용 프로그램 만들기 마법사 전체에 입력한 정보가 표시됩니다. **다음을** 선택하여 응용 프로그램을 만들 수 있습니다.

   - **진행률** - 응용 프로그램이 소프트웨어 라이브러리에 추가될 때 진행률 표시줄 및 상태가 이 페이지에 표시됩니다.

   - **완료** - 응용 프로그램 만들기 프로세스가 완료되면 응용 프로그램을 성공적으로 만들 수 있는지 확인이 표시됩니다. 닫기 **를** 선택하여 응용 프로그램 만들기 마법사를 완료합니다.

Configuration Manager의 소프트웨어 라이브러리에서 스크립트 응용 프로그램을 사용할 수 있는 후 장치 또는 컬렉션에 준비한 스크립트를 사용하여 SEMM을 배포하고 배포할 수 있습니다. Microsoft Surface UEFI 관리자 어셈블리를 자동으로 설치되는 종속성으로 구성한 경우 한 단계로 SEMM을 배포할 수 있습니다. 어셈블리를 종속성으로 구성하지 않은 경우 SEMM을 사용하도록 설정하기 전에 관리하려는 장치에 어셈블리를 설치해야 합니다.

이 스크립트 응용 프로그램을 사용하여 최종 사용자에게 표시되는 구성을 사용하여 SEMM을 배포하면 PowerShell 스크립트가 시작되고 인증서의 지문이 PowerShell 창에 표시됩니다. 장치를 다시 시작한 후 Surface UEFI에서 메시지가 표시될 때 사용자가 이 지문을 기록하고 입력하게 할 수 있습니다.

또는 응용 프로그램 설치를 구성하여 자동으로 다시 시작하고 사용자에게 기본으로 설치하도록 구성할 수 있습니다. 이 시나리오에서는 기술자가 재부팅할 때 각 디바이스에 지문을 입력해야 합니다. 인증서 파일에 액세스할 수 있는 모든 기술자는 CertMgr로 인증서를 확인하여 지문을 읽을 수 있습니다. CertMgr로 지문을 보는 지침은 이 문서의 [SEMM 구성](#create-or-modify-the-semm-configuration-manager-scripts) 관리자 스크립트 만들기 또는 수정 섹션에 있습니다.

Configuration Manager를 사용하여 배포된 장치에서 이러한 스크립트를 사용하여 SEMM을 제거하는 것은 Configuration Manager를 사용하여 응용 프로그램을 제거하는 것만큼 쉽습니다. 이 작업은 ResetSEMM.ps1 스크립트를 시작하고 SEMM 배포 중에 사용된 동일한 인증서 파일을 사용하여 디바이스의 등록을 올바르게 해지합니다.

> [!NOTE]
> 디바이스를 초기화해야 하는 경우 초기화 패키지를 만드는 것이 좋습니다. 이러한 재설정 패키지는 일반적으로 일련 번호로 식별된 하나의 장치에만 유효합니다. 그러나 이 인증서를 사용하여 SEMM에 등록된 모든 장치에 사용할 수 있는 유니버설 재설정 패키지를 만들 수 있습니다.
> 
> SEMM에 장치를 등록하는 데 사용한 인증서만큼 범용 초기화 패키지를 신중하게 보호하는 것이 좋습니다. 인증서 자체와 마찬가지로 이 유니버설 초기화 패키지를 사용하여 SEMM에서 조직의 Surface 디바이스를 등록을 끄는 데 사용할 수 있습니다.
> 
> 초기화 패키지를 설치하면 LSV(최저 지원 값)가 값 1로 다시 설정됩니다. 기존 구성 패키지를 사용하여 디바이스를 다시 설치할 수 있습니다. 소유권을 찍기 전에 디바이스에서 인증서 지문을 묻는 메시지가 표시됩니다.
> 
> 이러한 이유로 SEMM에서 장치를 다시 설치하려면 해당 장치에 새 패키지를 만들어 설치해야 합니다. 이 작업은 이미 SEMM에 등록된 디바이스의 구성이 변경되지 않은 새 등록이기 때문에 소유권이 적용되기 전에 디바이스에서 인증서 지문을 묻는 메시지가 표시됩니다.
