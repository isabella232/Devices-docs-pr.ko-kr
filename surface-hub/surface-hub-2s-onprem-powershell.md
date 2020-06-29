---
title: PowerShell을 사용 하 여 Surface Hub 2S 온-프레미스 계정 구성
description: PowerShell을 사용 하 여 Surface Hub 2S 온-프레미스 계정을 구성 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836644"
---
# PowerShell을 사용 하 여 Surface Hub 2S 온-프레미스 계정 구성

## Exchange Server PowerShell에 연결

> [!IMPORTANT]
> 일부 cmdlet에 대 한 온-프레미스 Exchange 서버의 클라이언트 액세스 서비스에 대 한 FQDN (정규화 된 도메인 이름)이 필요 합니다.

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## 디바이스 계정 만들기

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## 자동 일정 처리 설정

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## 비즈니스용 Skype 개체 사용

> [!NOTE]
> 비즈니스용 Skype 등록자 풀의 FQDN을 아는 것이 중요 합니다.

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## 모바일 장치 사서함 정책

Surface Hub에서 온라인 또는 온-프레미스 환경에 연결할 수 있도록 모바일 장치 사서함 정책 (ActiveSync 정책이 라고도 함)을 만들어야 할 수 있습니다.

## Surface Hub 모바일 장치 사서함 정책 만들기

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## 추가 설정

사용자가 모임을 비즈니스용 Skype 또는 팀에 게 메일 설명 것을 염두에 두어야 하는 Surface Hub 채팅방에 대 한 정보를 추가 하는 것이 좋습니다.

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
