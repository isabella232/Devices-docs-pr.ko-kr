---
title: Surface Hub 2S 장치 계정 만들기
description: 이 페이지에서는 Surface Hub 2S 디바이스 계정을 만드는 절차에 대해 설명합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385226"
---
# <a name="create-surface-hub-2s-device-account"></a>Surface Hub 2S 장치 계정 만들기

Surface Hub 장치 계정(회의실 사서함)을 만들면 Surface Hub 2S에서 모임 요청을 수신, 승인 또는 거절하고 모임에 참가할 수 있습니다. OOBE(첫 실행 경험) 설정 중에 장치 계정을 구성합니다. 필요한 경우 나중에 변경할 수 있습니다(OOBE 설정을 거치지 않고).

다음의 경우 Microsoft 365 관리 센터에서 계정을 만들 수 Windows PowerShell. 

- **관리 센터를 통해 계정을 생성합니다.** 최소 요구 사항을 충족하기 위해 [Microsoft 365](https://admin.microsoft.com/AdminPortal)관리 센터에서 계정에 필요한 모든 것을 직접 구성할 수 있습니다. 화이트보드 앱에서 직접 화이트보드를 공유하는 기능과 같은 일부 기능을 사용하려면 PowerShell을 사용하여 ActiveSync를 구성해야 합니다. 이 페이지에서 전자 메일 앱의 사용이 필요한 경우 [ActiveSync](#enable-activesync-if-use-of-email-app-is-required) 사용을 참조하세요.

- **PowerShell을 통해 계정을 생성합니다.** PowerShell 스크립트를 사용하여 여러 장치 계정을 쉽게 만들 수 있으며 다음을 비롯한 특정 기능을 신속하게 구성할 수 있습니다.
    - 모든 Surface Hub 디바이스 계정에 대한 일정 처리
    - 요청의 사용자 지정 자동 응답입니다.
    - 다른 사용자나 다른 프로세스에 의해 기본 ActiveSync 사서함 정책이 이미 수정된 경우 새 ActiveSync 사서함 정책을 만들고 할당해야 할 수 있습니다.

> [!TIP]
> 아래에서 계정 확인 스크립트를 실행하여 [계정 설정을 확인할 수](#account-verification-script) 있습니다.

> [!NOTE]  
> Surface Hub 장치 계정은 타사 FIP(페더티된 ID 공급자)를 지원하지 않습니다. 표준 Active Directory 또는 Azure Active Directory 계정이 되어야 합니다.

## <a name="create-account-via-admin-center"></a>관리 센터를 통해 계정 만들기

1. Microsoft 365 관리 센터에서 리소스로 **이동하여** 회의실 & **장비로 이동한** 다음 + 리소스 추가를 **선택합니다.**

2. 장치 계정의 이름과 전자 메일 주소를 제공합니다. 나머지 설정은 기본 상태로 변경되지 않습니다.

   ![이름 및 전자 메일 주소 제공](images/sh2-account2.png)

   ![나머지 설정은 기본 상태로 변경되지 않은 상태로 유지](images/sh2-account3.png)

3. 디바이스 계정의 암호를 설정하세요. 암호를 설정하려면 **사용자를** 선택한 다음 활성 사용자 **를 선택합니다.** 이제 새로 만든 사용자를 검색하여 암호를 설정합니다. 사용자가 처음 **로그인할** 때 암호를 변경하도록 옵션을 **선택하지 않도록 합니다.**

   ![디바이스 계정의 암호 설정](images/sh2-account4.png)

4. Office 365 라이선스가 있는 방을 할당합니다. Microsoft Teams 및 비즈니스용 Skype에 대한 계정을 자동으로 설정하는 Office 365 **회의실** 라이선스를 할당하는 것이 좋습니다.

   ![Office 365 라이선스 할당](images/sh2-account5.png)


> [!NOTE]  
> If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account. 

## <a name="create-account-via-powershell"></a>PowerShell을 통해 계정 만들기

 PowerShell을 사용하여 Surface Hub에서 작업을 빠르게 자동화하는 데 반드시 PowerShell 전문 지식이 필요하지는 않습니다. 이 페이지에서 적절한 스크립트를 사용하려면 먼저 설치 선행 작업을 완료해야 합니다.

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a>PowerShell을 사용하여 Surface Hub를 관리하기 위한 선행 구성 

1. 관리자 권한(관리자 권한으로 실행)을 사용하여 PowerShell을 시작하고 시스템이 PowerShell 스크립트를 실행하도록 구성되어 있는지 확인**** 자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?) 
2. [Azure PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/powershell/azure/install-az-ps)


### <a name="connect-to-exchange-online-powershell"></a>Exchange Online PowerShell에 연결

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a>사서함 만들기

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a>일정 자동 처리 설정(비즈니스용 Skype만 해당)

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a>전자 메일 앱 사용이 필요한 경우 ActiveSync 사용

 기본 ActiveSync 정책은 변경되지 않은 경우 작동됩니다. 그렇지 않으면 새 정책을 만들고 할당합니다.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a>Azure AD에 연결

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a>라이선스 할당

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a>사용 가능한 라이선스 확인

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a>계정 확인 스크립트

장치 계정을 만들고 나면 다음 확인 스크립트를 실행할 수 있습니다. 이 스크립트는 이전에 만든 디바이스 계정의 유효성을 검사하고 요약 보고서를 생성합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

특정 설정의 세부 정보는 표시되지 않습니다.

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## <a name="learn-more"></a>자세히 알아보기

- [PowerShell을 사용하여 Surface Hub 2S 온-프레미스 계정 만들기](surface-hub-2s-onprem-powershell.md)