---
title: Surface Hub 2S 장치 계정 만들기
description: 이 페이지에서는 Surface Hub 2S 장치 계정을 만드는 절차에 대해 설명합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 76ac960be2ab30a30b4e29618f350a13a284f52a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312024"
---
# <span data-ttu-id="35844-104">Surface Hub 2S 장치 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="35844-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="35844-105">Surface Hub 장치 계정(회의실 사서함)을 만들면 Surface Hub 2S에서 모임 요청을 수신, 승인 또는 거절하고 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="35844-106">OOBE(첫 실행 경험) 설치 중에 디바이스 계정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="35844-107">필요한 경우 나중에 변경할 수 있습니다(OOBE 설치를 거치지 않고).</span><span class="sxs-lookup"><span data-stu-id="35844-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="35844-108">다음의 경우 Microsoft 365 관리 센터에서 계정을 만들 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35844-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="35844-109">**관리 센터를 통해 계정을 만드시다.**</span><span class="sxs-lookup"><span data-stu-id="35844-109">**Create account via Admin center**.</span></span> <span data-ttu-id="35844-110">최소 요구 사항을 충족하기 위해 [Microsoft 365](https://admin.microsoft.com/AdminPortal)관리 센터에서 계정에 필요한 모든 것을 직접 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="35844-111">화이트보드 앱에서 직접 화이트보드를 공유하는 기능과 같은 일부 기능을 사용하려면 PowerShell을 사용하여 ActiveSync를 구성해야 합니다. 이 페이지에서 전자 메일 앱을 사용하는 것이 필요한 경우 [ActiveSync](#enable-activesync-if-use-of-email-app-is-required) 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35844-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="35844-112">**PowerShell을 통해 계정을 만드시다.**</span><span class="sxs-lookup"><span data-stu-id="35844-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="35844-113">PowerShell 스크립트를 사용하여 여러 장치 계정을 쉽게 만들 수 있으며 다음을 비롯한 특정 기능을 신속하게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="35844-114">모든 Surface Hub 디바이스 계정에 대한 일정 처리</span><span class="sxs-lookup"><span data-stu-id="35844-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="35844-115">요청의 사용자 지정 자동 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="35844-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="35844-116">다른 사용자나 다른 프로세스에 의해 기본 ActiveSync 사서함 정책이 이미 수정된 경우 새 ActiveSync 사서함 정책을 만들고 할당해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="35844-117">아래에서 계정 확인 스크립트를 실행하여 계정 설정을 [확인할 수](#account-verification-script) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="35844-118">Surface Hub 장치 계정은 타사 FIP(페더러티 ID 공급자)를 지원하지 않습니다. 표준 Active Directory 또는 Azure Active Directory 계정이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="35844-119">관리 센터를 통해 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="35844-119">Create account via admin center</span></span>

1. <span data-ttu-id="35844-120">Microsoft 365 관리 센터에서 리소스로 \*\*\*\* **이동하여** 장비 및 & 룸을 선택한 다음 + **리소스 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="35844-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="35844-121">장치 계정의 이름과 전자 메일 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="35844-122">나머지 설정은 기본 상태로 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-122">Leave remaining settings unchanged in the default state.</span></span>

   ![이름 및 전자 메일 주소 제공](images/sh2-account2.png)

   ![나머지 설정은 기본 상태로 변경되지 않은 상태로 두기](images/sh2-account3.png)

3. <span data-ttu-id="35844-125">디바이스 계정의 암호를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="35844-125">Set the password for the device account.</span></span> <span data-ttu-id="35844-126">암호를 설정하려면 **사용자를** 선택한 다음 **활성 사용자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="35844-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="35844-127">이제 새로 만든 사용자를 검색하여 암호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="35844-128">이 사용자가 **처음 로그인할** 때 암호를 변경하도록 옵션을 **선택하지 않도록 합니다.**</span><span class="sxs-lookup"><span data-stu-id="35844-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![디바이스 계정의 암호 설정](images/sh2-account4.png)

4. <span data-ttu-id="35844-130">Office 365 라이선스가 있는 방을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="35844-131">Microsoft Teams 및 비즈니스용 Skype 계정을 자동으로 사용할 수 있는 Office 365 **회의실** 라이선스를 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![Office 365 라이선스 할당](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="35844-133">비즈니스용 Skype를 사용하는 경우 PowerShell을 통해 설치를 완료해야 합니다. 비즈니스용 Skype 일정: [이](#set-calendar-auto-processing-skype-for-business-only) 계정에 대한 일정 자동 처리 설정</span><span class="sxs-lookup"><span data-stu-id="35844-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <span data-ttu-id="35844-134">PowerShell을 통해 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="35844-134">Create account via PowerShell</span></span>

 <span data-ttu-id="35844-135">PowerShell을 사용하여 Surface Hub에서 작업을 빠르게 자동화하는 데 반드시 PowerShell 전문 지식이 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="35844-136">이 페이지에서 적절한 스크립트를 사용하려면 먼저 설치 선행 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <span data-ttu-id="35844-137">PowerShell을 사용하여 Surface Hub를 관리하기 위한 선행 구성</span><span class="sxs-lookup"><span data-stu-id="35844-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="35844-138">관리자 권한(관리자**권한으로**실행)으로 PowerShell을 시작하고 시스템이 PowerShell 스크립트를 실행하도록 구성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="35844-139">자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="35844-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="35844-140">[Azure PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="35844-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <span data-ttu-id="35844-141">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="35844-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="35844-142">사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="35844-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="35844-143">일정 자동 처리 설정(비즈니스용 Skype만 해당)</span><span class="sxs-lookup"><span data-stu-id="35844-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="35844-144">전자 메일 앱 사용이 필요한 경우 ActiveSync 사용</span><span class="sxs-lookup"><span data-stu-id="35844-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="35844-145">기본 ActiveSync 정책은 변경되지 않은 경우 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="35844-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="35844-146">그렇지 않으면 새 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-146">Otherwise createStupid a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <span data-ttu-id="35844-147">Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="35844-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="35844-148">라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="35844-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="35844-149">사용 가능한 라이선스 확인</span><span class="sxs-lookup"><span data-stu-id="35844-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <span data-ttu-id="35844-150">계정 확인 스크립트</span><span class="sxs-lookup"><span data-stu-id="35844-150">Account verification script</span></span>

<span data-ttu-id="35844-151">장치 계정을 만들고 나면 다음 확인 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="35844-152">이 스크립트는 이전에 만든 장치 계정의 유효성을 검사하고 요약 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="35844-153">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35844-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="35844-154">특정 설정의 세부 정보는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35844-154">Details of specific settings will not be shown.</span></span>

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

## <span data-ttu-id="35844-155">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="35844-155">Learn more</span></span>

- [<span data-ttu-id="35844-156">PowerShell을 사용하여 Surface Hub 2S 온-프레미스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="35844-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)