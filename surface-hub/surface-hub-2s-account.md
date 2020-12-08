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
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196731"
---
# Surface Hub 2S 장치 계정 만들기

Surface Hub 장치 계정(회의실 사서함)을 만들면 Surface Hub 2S에서 Microsoft Teams 또는 비즈니스용 Skype를 사용하여 모임 요청을 수신, 승인 또는 거절하고 모임에 참가할 수 있습니다. OOBE(첫 실행 경험) 설치 중에 디바이스 계정을 구성합니다. 필요한 경우 나중에 변경할 수 있습니다(OOBE 설치를 거치지 않고).

기본적으로 사용하지 않도록 설정되어 있는 표준 채팅방 사서함과 달리 Surface Hub 2S 장치 계정이 Microsoft Teams 및 비즈니스용 Skype에 로그인하도록 설정해야 합니다. Surface Hub 2S는 디바이스 Exchange ActiveSync ActiveSync 사서함 정책이 필요한 2016을 사용합니다. Exchange Online과 함께 제공된 기본 ActiveSync 사서함 정책을 적용합니다.

Microsoft 365 관리 센터 또는 PowerShell을 사용하여 계정을 만들 수 있습니다. Exchange Online PowerShell을 사용하여 다음을 비롯한 특정 기능을 구성할 수 있습니다.

- 모든 Surface Hub 디바이스 계정에 대한 일정 처리
- 요청의 사용자 지정 자동 응답입니다.
- 다른 사용자나 다른 프로세스에 의해 기본 ActiveSync 사서함 정책이 이미 수정된 경우 새 ActiveSync 사서함 정책을 만들고 할당해야 할 수 있습니다.

> [!NOTE]  
> Surface Hub 장치 계정은 타사 FIP(페더러티 ID 공급자)를 지원하지 않습니다. 표준 Active Directory 또는 Azure Active Directory 계정이 되어야 합니다.

## Microsoft 365 관리 센터를 사용하여 계정 만들기

1. Microsoft 365 관리 센터에서 리소스로 **이동하여** 장비 및 & **룸을** 선택한 다음 **+ 회의실을 선택합니다.**

2. 장치 계정의 이름과 전자 메일 주소를 제공합니다. 나머지 설정은 기본 상태로 변경되지 않습니다.

   ![이름 및 전자 메일 주소 제공](images/sh2-account2.png)

   ![나머지 설정은 기본 상태로 변경되지 않은 상태로 두기](images/sh2-account3.png)

3. 디바이스 계정의 암호를 설정하십시오. 암호를 설정하려면 **사용자를** 선택한 다음 **활성 사용자를 선택합니다.** 이제 새로 만든 사용자를 검색하여 암호를 설정합니다. 이 사용자가 **처음 로그인할** 때 암호를 변경하도록 옵션을 선택하지 **않도록 합니다.**

   ![디바이스 계정의 암호 설정](images/sh2-account4.png)

4. Office 365 라이선스가 있는 방을 할당합니다. 비즈니스용 Skype Online 및 Microsoft Teams에 대해 계정을 자동으로 활성화하는 새로운 옵션인 Office 365 **회의실** 라이선스를 할당하는 것이 좋습니다.

   ![Office 365 라이선스 할당](images/sh2-account5.png)

### PowerShell을 통해 설정 완료

- **Microsoft Teams 및 비즈니스용 Skype 일정:** 이 [**계정에 대한 일정 자동 처리를**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) 설정하십시오.

## PowerShell을 사용하여 계정 만들기

Microsoft Admin Center 포털을 사용하는 대신 PowerShell을 사용하여 계정을 만들 수 있습니다.

### Exchange Online PowerShell에 연결

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### 사서함 만들기

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### 일정 자동 처리 설정

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### 전자 메일 앱 사용이 필요한 경우 ActiveSync 사용

 기본 ActiveSync 정책은 인치되지 않은 경우 작동됩니다. 그렇지 않으면 새 정책을 만들고 할당합니다.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### Azure AD에 연결

```powershell
Connect-AzureAD
```

### 라이선스 할당

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### 사용 가능한 라이선스 확인

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```