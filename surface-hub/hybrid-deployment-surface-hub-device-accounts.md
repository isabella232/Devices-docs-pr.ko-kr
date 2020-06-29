---
title: 하이브리드 배포(Surface Hub)
description: 하이브리드 배포에서 Microsoft Surface Hub에 대한 디바이스 계정을 설정하려면 특별한 처리가 필요합니다.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: 하이브리드 배포, Surface Hub용 디바이스 계정, Exchange에서 호스트하는 온-프레미스, Exchange에서 호스트하는 온라인
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836204"
---
# 하이브리드 배포(Surface Hub)

하이브리드 배포에서 Microsoft Surface Hub에 대한 디바이스 계정을 설정하려면 특별한 처리가 필요합니다. 온-프레미스에 호스트된 서비스와 온라인에 호스트된 서비스가 혼합되어 있는 하이브리드 배포를 사용하는 경우 각 서버가 호스트된 위치에 따라 구성이 달라집니다. 이 항목에서는 [온-프레미스에 호스트된 Exchange](#exchange-on-premises), [온라인에 호스트된 Exchange](#exchange-online), 비즈니스용 Skype 온-프레미스, 비즈니스용 Skype Online 및 비즈니스용 Skype 하이브리드 Skype에 대한 하이브리드 배포를 설명합니다. 이 배포 유형에는 너무 많은 변형이 있으므로 모든 변형에 대한 자세한 지침을 제공할 수는 없습니다. 다음 프로세스는 대부분의 구성에 적용됩니다. 프로세스가 설치에 부적합한 경우 다른 배포 옵션에 대해 이 문서에 설명된 것과 동일한 최종 결과를 얻기 위해 PowerShell([부록: PowerShell ](appendix-a-powershell-scripts-for-surface-hub.md)참조)을 사용하는 것이 좋습니다. 그런 다음 제공된 PowerShell 스크립트를 사용하여 Surface Hub 설치를 확인해야 합니다. [계정 확인 스크립트](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)를 참조하세요.

> [!NOTE]
> Exchange 하이브리드 환경에서 [exchange 온-프레미스](#exchange-on-premises)에 대 한 단계를 따릅니다. Exchange 개체를 Office 365으로 이동 하려면 [MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet을 사용 합니다.

## 온-프레미스 Exchange

온-프레미스 Exchange를 사용하는 경우 이 절차를 사용합니다.

1. 이 절차에서는 AD 관리 도구를 사용하여 온-프레미스 도메인 계정의 메일 주소를 추가합니다. 이 계정은 Office 365와 동기화됩니다.

- **Active Directory 사용자 및 컴퓨터** AD 도구에서 Surface Hub 계정을 만들 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**, **사용자**를 차례로 클릭합니다.
- **전체 이름** 상자에 이전 cmdlet의 표시 이름을 입력하고 **사용자 로그온 이름** 상자에 별칭을 입력합니다. **다음**을 클릭합니다.<p>

![Active Directory에서 새 사용자를 만들기 위한 새 개체 상자.](images/hybriddeployment-01a.png)

- 이 계정의 암호를 입력합니다. 확인을 위해 다시 입력해야 합니다. **암호 사용 기간 제한 없음** 확인란만 선택되었는지 확인합니다.

> **중요** Surface Hub의 비즈니스용 Skype를 사용하려면 **암호 사용 기간 제한 없음**을 선택해야 합니다. 도메인 규칙에서 사용 기간 제한이 없는 암호를 차단할 수도 있습니다. 이 경우 각 Surface Hub 디바이스 계정에 대한 예외를 만들어야 합니다.

![암호 대화 상자를 표시하는 이미지](images/hybriddeployment-02a.png)

-   **마침** 을 클릭하여 계정을 만듭니다.

![새 사용자에 대한 계정 이름, 로그온 이름 및 암호 옵션을 보여 주는 이미지](images/hybriddeployment-03a.png)

2. 원격 사서함을 사용하도록 설정합니다.

관리자 권한으로 온-프레미스 Exchange 관리 셸을 열고 이 cmdlet을 실행합니다.

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> 이 cmdlet을 실행하기 위한 온-프레미스 Exchange 환경이 없는 경우 계정의 Active Directory 개체에 직접 동일한 변경을 수행할 수 있습니다.
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. 계정을 만든 후 디렉터리 동기화를 실행합니다. 완료 되 면 Microsoft 365 관리 센터의 사용자 페이지로 이동 하 여 이전 단계에서 만든 계정이 온라인에 병합 되었는지 확인 합니다.

4. Microsoft Exchange Online에 연결하고 Office 365에서 계정의 몇 가지 속성을 설정합니다.

PC에서 원격 PowerShell 세션을 시작하고 Microsoft Exchange에 연결합니다. 관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.

다음 단계는 Office 365 테넌트에서 실행됩니다.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용합니다.

사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.

Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다. 제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.

호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다. 정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

호환 되는 정책을 사용 하는 경우에는 해당 정책을 디바이스 계정에 적용 해야 합니다. 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. Exchange 속성을 설정합니다.

디바이스 계정에서 Exchange 속성을 설정하여 모임 환경을 개선할 수 있습니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. Azure AD에 연결합니다.

먼저 PowerShell 버전 2용 Azure AD 모듈을 설치해야 합니다. 관리자 권한 PowerShell 프롬프트에서 다음 명령을 실행 합니다.

```PowerShell
Install-Module -Name AzureAD
```

일부 계정 설정을 적용하려면 Azure AD에 연결해야 합니다. 이 cmdlet을 실행하여 연결할 수 있습니다.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Office 365 라이선스를 할당합니다.

디바이스 계정에 유효한 Office 365(O365) 라이선스가 있어야 합니다. 그렇지 않으면 Exchange와 비즈니스용 Skype가 작동하지 않습니다. 라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 이에 따라 계정에 사용할 수 있는 라이선스 SKU가 결정됩니다.

`Get-AzureADSubscribedSku`를 사용하여 O365 테넌트에 사용 가능한 SKU 목록을 검색할 수 있습니다.

SKU 목록을 표시한 후에는 `$License.SkuId` 변수에 원하는 SkuId를 할당해야 합니다.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

다음으로 [비즈니스용 Skype Online](#skype-for-business-online), [비즈니스용 Skype 온-프레미스](#skype-for-business-on-premises) 또는 [비즈니스용 Skype 하이브리드](#skype-for-business-hybrid)에서 디바이스 계정을 사용하도록 설정합니다.

### 비즈니스용 Skype Online

비즈니스용 Skype Online을 사용하려면 테넌트 사용자에게 Exchange 사서함이 있어야 합니다(테넌트에 Exchange 사서함이 하나 이상 있어야 함). 다음 표에서 필요한 계획 또는 추가 서비스에 대해 설명합니다.

| Skype 공간 시스템 시나리오 | Office 365 Premium, 엔터프라이즈 용 Microsoft 365 앱 또는 비즈니스용 Skype 독립 실행형 요금제 2를 사용 하는 경우 다음이 필요 합니다. | 엔터프라이즈 기반 요금제를 사용하는 경우 다음이 필요합니다. | 비즈니스용 Skype 서버 2015 (온-프레미스 또는 하이브리드)이 있는 경우 다음이 필요 합니다. |
| --- | --- | --- | --- |
| 예약된 모임에 참가 | 비즈니스용 Skype 독립 실행형 요금제 1 | E1, 3, 4, 또는 5 | 비즈니스용 Skype 서버 Standard CAL |
| 임시 회의 시작 | 비즈니스용 Skype 독립 실행형 요금제 2 | E1, 3, 4, 또는 5 | 비즈니스용 Skype 서버 Standard CAL 또는 Enterprise CAL |
| 임시 회의를 시작하고 회의에서 해당 번호에 전화 걸기 | 비즈니스용 Skype 독립 실행형 요금제 2, 오디오 회의</br></br>**참고** PSTN 소비 청구는 선택 사항입니다. | E1 또는 E3 (오디오 회의) 또는 E5| 비즈니스용 Skype 서버 Standard CAL 또는 Enterprise CAL |
| 회의실에 전화 번호를 제공하고 회의실에서 전화를 걸거나 받고 또는 전화 번호를 사용하여 전화 접속 회의 참석 | 전화 시스템 및 PSTN 음성 통화 요금제를 사용 하는 비즈니스용 Skype 독립 실행형 요금제 2 | 전화 시스템 및 PSTN 음성 통화 요금제 또는 E5와 E1 또는 E3 | 비즈니스용 Skype 서버 Standard CAL 또는 Plus CAL |

다음 표에서 Office 365 요금제 및 비즈니스용 Skype 옵션을 나열합니다.

| O365 요금제 | 비즈니스용 Skype | 전화 시스템 | 오디오 회의 | 통화 요금제 |
| --- | --- | --- | --- | --- |
| O365 Business Essentials | 포함 |  |  |  |
| O365 Business Premium | 포함 |  |  |  |
| E1 | 포함 | 추가 기능 | 추가 기능 | 추가 기능 (전화 시스템 추가 기능 필요) |
| E3 | 포함 | 추가 기능 | 추가 기능 | 추가 기능 (전화 시스템 추가 기능 필요) |
| E5 | 포함 | 포함 | 포함 | 추가 기능  |

1. 먼저 PC와 비즈니스용 Skype Online 환경 간의 원격 PowerShell 세션을 만듭니다.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. 비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. Surface Hub 계정에 비즈니스용 Skype 라이선스를 할당합니다.

 비즈니스용 Skype Online에서 Surface Hub 계정을 사용하도록 설정하는 이전 단계를 완료했으면 Surface Hub에 라이선스를 할당해야 합니다. O365 관리 포털을 사용 하 여 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스를 장치에 할당 합니다.

- 테넌트 관리자로 로그인하고 O365 관리 포털을 연 다음 관리자 앱을 클릭합니다.

- **사용자 및 그룹** 을 클릭한 다음 **사용자 추가, 암호 재설정 등**을 클릭합니다.

- Surface Hub 계정을 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.

- **라이선스**를 클릭합니다.

- 라이선스 **할당**에서 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 비즈니스용 Skype (계획 1) 또는 비즈니스용 Skype (요금제 2)를 선택 합니다. Surface Hub에서 엔터프라이즈 음성을 사용 하려면 요금제 2 라이선스를 사용 해야 합니다.

- **저장**을 클릭합니다.

> [!NOTE]
> Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하여 이러한 라이선스 중 하나를 할당하는 데 필요한 cmdlet을 실행할 수도 있지만 여기서는 설명하지 않습니다.

유효성 검사를 위해 비즈니스용 Skype 클라이언트(PC, Android 등)를 사용하여 이 계정에 로그인할 수 있어야 합니다.

### 비즈니스용 Skype 온-프레미스

이 cmdlet을 실행하려면 Skype 프런트 엔드 중 하나에 연결해야 합니다. Skype PowerShell을 열고 다음을 실행합니다.

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### 비즈니스용 Skype 하이브리드

조직에서 [비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결](https://technet.microsoft.com/library/jj205403.aspx)을 설정한 경우에는 계정을 만들기 위한 지침이 표준 Surface Hub 배포와 약간 다릅니다.

Surface Hub에는 `meetingroom` 유형의 Skype 계정이 필요하지만 일반 사용자는 Skype에서 사용자 유형 계정을 사용합니다. 사용자가 로컬 Skype 서버에 있을 수도 있고 Office 365에서 호스트될 수도 있는 하이브리드에 대해 Skype 서버를 설정한 경우 Surface Hub 계정을 만들려고 하면 몇 가지 문제가 발생할 수 있습니다.

비즈니스용 Skype Server 2015 하이브리드 환경에서는 Active Directory 도메인 서비스에서 사용자 계정을 만들 수 있도록 온-프레미스 배포에서 비즈니스용 Skype Online에서 원하는 사용자를 먼저 만들어야 합니다. 그런 다음 사용자를 비즈니스용 Skype Online으로 이동할 수 있습니다. 온-프레미스에서 온라인으로 사용자 계정을 이동 하는 작업은 [csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet을 통해 수행 됩니다. Csmeetingroom 개체를 이동 하려면 [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet을 사용 합니다.

> [!NOTE]
> CsMeetingRoom cmdlet을 사용 하려면 [비즈니스용 Skype server 2015에는 5 월 2017 누적 업데이트 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) 또는 [Lync Server 2013의 7 2017 월 누적 업데이트 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)에 설치 되어 있어야 합니다.


## Exchange Online

Exchange Online을 사용하는 경우 이 절차를 사용합니다.

1. Office 365에서 메일 계정을 만듭니다.

PC에서 원격 PowerShell 세션을 시작하고 Exchange에 연결합니다. 관련 cmdlet을 실행할 수 있는 권한이 설정되었는지 확인합니다.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. 사서함을 설정 합니다.

세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 회의실 사서함의 설정을 변경합니다. 이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.

기존 리소스 사서함을 변경하는 경우

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

새 리소스 사서함을 만드는 경우

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. Exchange ActiveSync 정책을 만듭니다.

사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.

Surface Hub는 **PasswordEnabled** 속성이 False로 설정된 ActiveSync 정책이 있는 디바이스 계정하고만 호환됩니다. 이 기능이 제대로 설정 되어 있지 않으면 Surface Hub의 Exchange 서비스 (메일, 일정, 모임 참가)가 사용 되지 않습니다.

호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다. 정책을 만든 후 다른 디바이스 계정에 동일한 정책을 적용할 수 있습니다.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

호환 되는 정책을 사용 하는 경우에는 해당 정책을 디바이스 계정에 적용 해야 합니다. 그러나 정책은 사용자 계정에만 적용할 수 있고 리소스 사서함에는 적용할 수 없습니다. 사서함을 사용자 유형으로 변환하고 정책을 적용한 다음 사서함으로 다시 변환합니다. 다시 사용하도록 설정하고 암호도 다시 설정해야 할 수 있습니다.

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. Exchange 속성을 설정합니다.

디바이스 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선해야 합니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. 온-프레미스 도메인 계정에 대 한 전자 메일 주소를 추가 합니다.

이 절차에서는 AD 관리 도구를 사용하여 온-프레미스 도메인 계정의 메일 주소를 추가합니다.

- **Active Directory 사용자 및 컴퓨터** AD 도구에서 Surface Hub 계정을 만들 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**, **사용자**를 차례로 클릭합니다.
- **전체 이름** 상자에 이전 cmdlet의 표시 이름을 입력하고 **사용자 로그온 이름** 상자에 별칭을 입력합니다. **다음**을 클릭합니다.

![Active Directory에서 새 사용자를 만들기 위한 새 개체 상자](images/hybriddeployment-01a.png)

- 이 계정의 암호를 입력합니다. 확인을 위해 다시 입력해야 합니다. **암호 사용 기간 제한 없음** 확인란만 선택되었는지 확인합니다.

> [!IMPORTANT]
> **암호 사용 기간 제한 없음** 선택은 Surface Hub의 비즈니스용 Skype에 대 한 요구 사항입니다. 도메인 규칙에서 사용 기간 제한이 없는 암호를 차단할 수도 있습니다. 이 경우 각 Surface Hub 디바이스 계정에 대한 예외를 만들어야 합니다.

![암호 대화 상자를 표시하는 이미지](images/hybriddeployment-02a.png)

- **마침** 을 클릭하여 계정을 만듭니다.

![새 사용자에 대한 계정 이름, 로그온 이름 및 암호 옵션을 보여 주는 이미지](images/hybriddeployment-03a.png)

6. 디렉터리 동기화를 실행합니다.

계정을 만든 후 디렉터리 동기화를 실행합니다. 완료되면 사용자 페이지로 이동한 다음 이전 단계에서 만든 두 계정이 병합되었는지 확인합니다.

7. Azure AD에 연결합니다.

먼저 PowerShell 버전 2용 Azure AD 모듈을 설치해야 합니다. 관리자 권한 PowerShell 프롬프트에서 다음 명령을 실행 합니다.

```PowerShell
Install-Module -Name AzureAD
```

일부 계정 설정을 적용하려면 Azure AD에 연결해야 합니다. 이 cmdlet을 실행 하 여 연결할 수 있습니다.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Office 365 라이선스를 할당합니다.

디바이스 계정에 유효한 Office 365(O365) 라이선스가 있어야 합니다. 그렇지 않으면 Exchange와 비즈니스용 Skype가 작동하지 않습니다. 라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 이에 따라 계정에 사용할 수 있는 라이선스 SKU가 결정됩니다.

다음으로 `Get-AzureADSubscribedSku`를 사용하여 O365 테넌트에 사용 가능한 SKU 목록을 검색할 수 있습니다.

SKU 목록을 표시한 후에는 `$License.SkuId` 변수에 원하는 SkuId를 할당해야 합니다.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

다음으로 [비즈니스용 Skype Online](#skype-for-business-online), [비즈니스용 Skype 온-프레미스](#skype-for-business-on-premises) 또는 [비즈니스용 Skype 하이브리드](#skype-for-business-hybrid)에서 디바이스 계정을 사용하도록 설정합니다.

### 비즈니스용 Skype Online

비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 [비즈니스용 Skype Online의 필수 조건](#skype-for-business-online)을 충족해야 합니다.

1. 먼저 PC와 비즈니스용 Skype Online 환경 간의 원격 PowerShell 세션을 만듭니다.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. 비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. Surface Hub 계정에 비즈니스용 Skype 라이선스 할당

비즈니스용 Skype Online에서 Surface Hub 계정을 사용하도록 설정하는 이전 단계를 완료했으면 Surface Hub에 라이선스를 할당해야 합니다. O365 관리 포털을 사용 하 여 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스를 장치에 할당 합니다.

- 테넌트 관리자로 로그인하고 O365 관리 포털을 연 다음 관리자 앱을 클릭합니다.

- **사용자 및 그룹** 을 클릭한 다음 **사용자 추가, 암호 다시 설정 등**을 클릭합니다.

- Surface Hub 계정을 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.

- **라이선스**를 클릭합니다.

- 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 **라이선스 할당**에서 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 선택합니다. Surface Hub에서 엔터프라이즈 음성을 사용하려는 경우 계획 3 라이선스를 사용해야 합니다.

- **저장**을 클릭합니다.

> [!NOTE]
> Windows PowerShell용 Microsoft Azure Active Directory 모듈을 사용하여 이러한 라이선스 중 하나를 할당하는 데 필요한 cmdlet을 실행할 수도 있지만 여기서는 설명하지 않습니다.

유효성 검사를 위해 비즈니스용 Skype 클라이언트(PC, Android 등)를 사용하여 이 계정에 로그인할 수 있어야 합니다.

### 비즈니스용 Skype 온-프레미스

이 cmdlet을 실행하려면 Skype 프런트 엔드 중 하나에 연결해야 합니다. Skype PowerShell을 열고 다음을 실행합니다.

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### 비즈니스용 Skype 하이브리드

조직에서 [비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결](https://technet.microsoft.com/library/jj205403.aspx)을 설정한 경우에는 계정을 만들기 위한 지침이 표준 Surface Hub 배포와 약간 다릅니다.

Surface Hub에는 *meetingroom* 유형의 Skype 계정이 필요하지만 일반 사용자는 Skype에서 *사용자* 유형 계정을 사용합니다. 사용자가 로컬 Skype 서버에 있을 수도 있고 Office 365에서 호스트될 수도 있는 하이브리드에 대해 Skype 서버를 설정한 경우 Surface Hub 계정을 만들려고 하면 몇 가지 문제가 발생할 수 있습니다.

비즈니스용 Skype Server 2015 하이브리드 환경에서는 Active Directory 도메인 서비스에서 사용자 계정을 만들 수 있도록 온-프레미스 배포에서 비즈니스용 Skype Online에서 원하는 사용자를 먼저 만들어야 합니다. 그런 다음 사용자를 비즈니스용 Skype Online으로 이동할 수 있습니다. 온-프레미스에서 온라인으로 사용자 계정을 이동 하는 작업은 [csuser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet을 통해 수행 됩니다. Csmeetingroom 개체를 이동 하려면 [move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet을 사용 합니다.

> [!NOTE]
> CsMeetingRoom cmdlet을 사용 하려면 [비즈니스용 Skype server 2015에는 5 월 2017 누적 업데이트 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) 또는 [Lync Server 2013의 7 2017 월 누적 업데이트 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)에 설치 되어 있어야 합니다.
