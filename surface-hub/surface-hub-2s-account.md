---
title: Surface Hub 2S 장치 계정 만들기
description: 이 페이지에서는 Surface Hub 2S 디바이스 계정을 만드는 절차에 대해 설명 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836380"
---
# Surface Hub 2S 장치 계정 만들기

Surface Hub 디바이스 계정 (회의실 사서함이 라고도 함)을 만들면 Surface Hub 2S에서 모임 요청을 받아서 승인 하거나 거절 하 고 Microsoft 팀 또는 비즈니스용 Skype를 사용 하 여 모임에 참가할 수 있습니다. OOBE (고급 경험) 설정 중 디바이스 계정을 구성 합니다. 필요한 경우 OOBE 설치를 거치지 않고 나중에 변경할 수 있습니다.

기본적으로 사용 되지 않는 표준 채팅방 사서함과 달리, Surface Hub 2S 디바이스 계정을 사용 하 여 Microsoft 팀과 비즈니스용 Skype에 로그인 해야 합니다. Surface Hub 2S는 Exchange ActiveSync를 사용 하며,이는 디바이스 계정에 대 한 ActiveSync 사서함 정책이 필요 합니다. Exchange Online과 함께 제공 되는 기본 ActiveSync 사서함 정책을 적용 합니다.

Microsoft 365 관리 센터를 사용 하거나 PowerShell을 사용 하 여 계정을 만듭니다. Exchange Online PowerShell을 사용 하 여 다음과 같은 특정 기능을 구성할 수 있습니다.

- 모든 Surface Hub 디바이스 계정에 대 한 일정 처리.
- 일정 요청에 대 한 사용자 지정 자동 회신
- 기본 ActiveSync 사서함 정책이 다른 사용자에 의해 이미 수정 된 경우에는 새 ActiveSync 사서함 정책을 만들어 할당 해야 할 수 있습니다.

> [!NOTE]  
> Surface Hub 디바이스 계정은 타사 페더레이션 Id 공급자 (FIPs)를 지원 하지 않으며 표준 Active Directory 또는 Azure Active Directory 계정 이어야 합니다.

## Microsoft 365 관리 센터를 사용 하 여 계정 만들기

1. Microsoft 365 관리 센터에서 **리소스로** 이동 하 여 **채팅방 & 장비** 를 선택한 다음 **+ Room**을 선택 합니다.

2. 디바이스 계정의 이름 및 전자 메일 주소를 입력 합니다. 나머지 설정은 기본 상태에서 변경 되지 않은 상태로 둡니다.

   ![이름 및 전자 메일 주소 제공](images/sh2-account2.png)

   ![나머지 설정을 기본 상태의 변경 되지 않은 상태로 유지](images/sh2-account3.png)

3. 장치 계정에 대 한 암호를 설정 합니다. 암호를 설정 하려면 **사용자** 를 선택한 다음 **활성 사용자**를 선택 합니다. 이제 새로 만든 사용자를 검색 하 여 암호를 설정 합니다. **이 사용자가 처음 로그인 할 때 암호를 변경 하도록** 하는 옵션을 선택 **하지** 않았는지 확인 합니다.

   ![장치 계정에 대 한 암호 설정](images/sh2-account4.png)

4. Office 365 라이선스를 사용 하 여 채팅방을 할당 합니다. 비즈니스용 Skype Online 및 Microsoft 팀에 대 한 계정을 자동으로 사용 하도록 설정 하는 새로운 옵션인 Office 365 **모임 채팅방** 라이선스를 할당 하는 것이 좋습니다.

   ![Office 365 라이선스 할당](images/sh2-account5.png)

### PowerShell을 통해 설치 마무리

- **비즈니스용 Skype:** 비즈니스용 Skype 전용 (온-프레미스 또는 온라인)의 경우 **CsMeetingRoom** 를 실행 하 여 비즈니스용 skype 개체를 사용 하도록 설정 하 여 오디오 및 로비 저장에 대 한 회의실 메시지 표시와 같은 기능을 사용 하도록 설정할 수 있습니다.

- **Microsoft 팀 및 비즈니스용 Skype 달력:** 이 계정에 대 한 [**일정 자동 처리**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) 를 설정 합니다.

## PowerShell을 사용 하 여 계정 만들기

Microsoft 관리 센터 포털을 사용 하는 대신 PowerShell을 사용 하 여 계정을 만들 수 있습니다.

### Exchange Online PowerShell에 연결

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### 새 회의실 사서함 만들기

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### 일정 자동 처리 설정

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### 라이선스 할당

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결

### 사전 요구 조건 설치

- [Visual c + + 2017 재배포 가능 패키지](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [비즈니스용 Skype Online PowerShell 모듈](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
