---
title: UI(Surface Hub)를 사용하여 디바이스 계정 만들기
description: 그래픽 사용자 인터페이스를 사용하려는 경우 Office 365 UI 또는 Exchange 관리 센터를 사용하여 Microsoft Surface Hub에 대한 디바이스 계정을 만들 수 있습니다.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: 장치 계정 만들기, Office 365 UI, Exchange 관리 센터, Microsoft 365 관리 센터, 비즈니스용 Skype, 모바일 장치 사서함 정책
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836743"
---
# UI(Surface Hub)를 사용하여 디바이스 계정 만들기


그래픽 사용자 인터페이스를 사용하려는 경우 [Office 365 UI](#create-device-acct-o365) 또는 [Exchange 관리 센터](#create-device-acct-eac)를 사용하여 Microsoft Surface Hub에 대한 디바이스 계정을 만들 수 있습니다.

## <a href="" id="create-device-acct-o365"></a>Office 365를 사용하여 디바이스 계정 만들기


1.  [Microsoft 365 관리 센터에서 계정을 만듭니다](#create-device-acct-o365-admin-ctr).
2.  [Microsoft Exchange 관리 센터에서 모바일 디바이스 사서함(ActiveSync) 정책 만들기](#create-device-acct-o365-mbx-policy)
3.  [PowerShell을 사용하여 디바이스 계정 만들기 완료](#create-device-acct-o365-complete-acct).
4.  [PowerShell을 사용하여 계정의 Exchange 속성 구성](#create-device-acct-o365-configure-exch-prop)
5.  [비즈니스용 Skype와 함께 계정을 사용하도록 설정](#create-device-acct-o365-skype-for-business)

### <a href="" id="create-device-acct-o365-admin-ctr"></a>관리 센터에서 계정 만들기

1.  방문 하 여 Office 365에 로그인https://portal.office.com
2.  Office 365 테넌트에 대한 관리자 자격 증명을 제공합니다. 이렇게 하면 Microsoft 365 관리 센터로 이동 합니다.

    ![Microsoft 365 관리 센터.](images/setupdeviceaccto365-02.png)

3. 관리 센터에서 왼쪽 패널의 **리소스로** 이동한 다음 **채팅방 & 기기**를 클릭 합니다.

    ![관리 센터의 채팅방 & 장비 옵션](images/room-equipment.png)

4. **추가**를 클릭하여 새 회의실 계정을 만듭니다. 계정에 대한 표시 이름 및 이메일 주소를 입력한 다음 **추가**를 클릭합니다.

    ![새 회의실 계정 창 만들기](images/room-add.png)

5. 활성 사용자 목록에서 방금 만든 회의실 계정을 선택합니다. 오른쪽 패널에서 계정 속성과 여러 개의 선택적 동작을 확인할 수 있습니다. Surface Hub 로그인 과정에서 암호를 변경할 수 없기 때문에 **암호 재설정**을 클릭하여 암호를 변경하고 **이 사용자가 처음 로그인할 때 암호를 변경하도록 설정**을 선택 해제합니다.

6. **할당된 라이선스** 섹션에서 **편집**을 클릭한 다음 적합한 라이선스 옆에 있는 드롭다운 화살표를 클릭하여 세부 정보를 확장합니다. 사용자 위치를 선택하고 라이선스 목록에서 **비즈니스용 Skype Online(플랜 2)** 을 전환하고 **저장**을 클릭합니다. 라이선스는 조직에 따라 다를 수 있습니다(예: 사용자의 플랜이 플랜 2 또는 플랜 3일 수 있음).

### <a href="" id="create-device-acct-o365-mbx-policy"></a>Exchange 관리 센터에서 모바일 디바이스 사서함(ActiveSync) 정책 만들기

1.  관리 센터의 왼쪽 패널에서 **관리자**를 클릭 한 다음 **Exchange**를 클릭 합니다.

    ![exchange 활성 사용자를 보여 주는 관리 센터](images/setupdeviceaccto365-08.png)

2.  이렇게 하면 Surface Hub에 대한 사서함 설정을 만들고 설정할 수 있는 Exchange 관리 센터로 이동하는 다른 탭이 브라우저에서 열립니다.

    ![Exchange 관리 센터](images/setupdeviceaccto365-09.png)

3.  모바일 디바이스 사서함 정책을 만들려면 왼쪽 패널에서 **모바일**을 클릭한 다음 **모바일 디바이스 사서함 정책**을 클릭합니다. Surface Hub에는 암호를 요구하지 않는 모바일 디바이스 사서함 정책을 가진 계정이 필요하므로 이 요구 사항에 맞는 기존 정책이 이미 있는 경우 해당 정책을 계정에 적용할 수 있습니다. 그렇지 않으면 다음 단계에 따라 Surface Hub 디바이스 계정에만 사용할 새 정책을 만듭니다.

    ![Exchange 관리 센터 - 모바일 디바이스 사서함 정책 만들기](images/setupdeviceaccto365-10.png)

4.  새 Surface Hub 모바일 디바이스 사서함 정책을 만들려면 새 정책을 추가할 정책 목록 위에 있는 컨트롤에서 **+** 단추를 클릭합니다. 이름에는 이 정책을 다른 디바이스 계정과 구분하는 데 도움이 되는 이름을 입력합니다(예: *SurfaceHubDeviceMobilePolicy*). 정책에서 디바이스의 암호 할당을 요구하지 않도록 **암호 필요**를 선택 취소된 상태로 유지하고 **저장**을 클릭합니다.

    ![새 모바일 디바이스 정책을 보여 주는 이미지.](images/setupdeviceaccto365-11.png)

5.  새 모바일 디바이스 사서함 정책을 만든 후 **Exchange 관리 센터**로 돌아가면 새 정책이 표시됩니다.

    ![Exchange 관리 센터의 새 모바일 디바이스 사서함 정책을 보여 주는 이미지](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>PowerShell을 사용하여 디바이스 계정 만들기 완료

여기서 PowerShell을 통해 일부 구성을 설정하여 계정 만들기 프로세스를 완료해야 합니다.

이러한 PowerShell 스크립트에서 사용되는 cmdlet을 실행하려면 관리자 PowerShell 콘솔에 대해 다음을 설치해야 합니다.

-   [IT 전문가를 위한 Microsoft Online Services 로그인 도우미 RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [Windows PowerShell용 Microsoft Azure Active Directory 모듈](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [비즈니스용 Skype Online, Windows PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)

Powershell에 다음 모듈을 설치 합니다.
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### 온라인 서비스에 연결

1.  관리자 권한으로 Windows PowerShell을 실행합니다.

    ![Windows PowerShell을 시작하고 관리자 권한으로 실행하는 방법을 보여 주는 이미지](images/setupdeviceaccto365-17.png)

2.  자격 증명 개체를 만들고 비즈니스용 Skype Online에 연결하는 새 세션을 만든 다음 전역 테넌트 관리자 계정을 제공하고 **확인**을 클릭합니다.

    ![Windows PowerShell 자격 증명 요청 이미지](images/setupdeviceaccto365-18.png)

3.  Microsoft Online Services에 연결하려면 다음을 실행합니다.

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-19.png)

4.  비즈니스용 Skype Online Services에 연결하려면 다음을 실행합니다.

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-20.png)

5.  마지막으로, Exchange Online Services에 연결하려면 다음을 실행합니다.

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-21.png)

6.  이제 방금 만든 비즈니스용 Skype Online 세션과 Exchange Online 세션을 가져와야 합니다. 그러면 로컬에서 사용할 수 있도록 Exchange 및 Skype 명령을 가져옵니다.

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    이 작업을 완료하는 데 시간이 좀 걸릴 수 있습니다.

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-22.png)

7.  온라인 서비스에 연결된 후 몇 개의 cmdlet을 더 실행하여 이 계정을 Surface Hub 디바이스 계정으로 구성해야 합니다.

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>PowerShell을 사용하여 계정의 Exchange 속성 구성

이제 온라인 서비스에 연결되었으므로 디바이스 계정 설정을 완료할 수 있습니다. 디바이스 계정 메일 주소를 사용하여 다음 작업을 수행합니다.

-   사서함 유형을 일반에서 회의실로 변경합니다.
-   암호를 설정하고 회의실 사서함 계정을 사용하도록 설정합니다.
-   다양한 Exchange 속성을 변경합니다.
-   사용자 계정 암호의 사용 기간 제한이 없도록 설정합니다.

1.  계정의 메일 주소를 입력하고 해당 값을 가진 변수를 만들어야 합니다.

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    값을 저장하고 사서함에서 가져오려면

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    값을 인쇄합니다.

    ```powershell
    $strEmail
    ```

    올바른 메일 주소가 표시됩니다.

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-23.png)

2. 다음 cmdlet을 실행 합니다.

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  디바이스 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선할 수 있습니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-26.png)

5.  암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다. 자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>비즈니스용 Skype와 함께 계정을 사용하도록 설정

비즈니스용 Skype와 함께 디바이스 계정을 사용하도록 설정합니다.

비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 다음 필수 조건을 충족해야 합니다.

-   O365 계획에 비즈니스용 Skype Online 독립 실행형 요금제 2 이상이 있어야 합니다. 계획이 회의 기능을 지원해야 합니다.
-   Surface Hub 용 전화 통신 서비스 공급자를 사용 하 여 엔터프라이즈 음성 (PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online 독립 실행형 요금제 3이 필요 합니다.
-   테넌트 사용자에게 Exchange 사서함이 있어야 합니다.
-   Surface Hub 계정에는 비즈니스용 Skype Online 독립 실행형 요금제 2 또는 비즈니스용 Skype Online 독립 실행형 요금제 3 라이선스가 필요 하지만, Exchange Online 라이선스는 필요 하지 않습니다.

1.  먼저 PC에서 원격 PowerShell 세션을 만듭니다.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>Exchange 관리 센터를 사용하여 디바이스 계정 만들기

>[!NOTE]
>이 메서드는 온-프레미스 Active Directory에서 동기화 하는 경우에만 작동 합니다.

Exchange 관리 센터를 사용하여 디바이스 계정을 만들 수 있습니다.

1.  [Exchange 관리 센터를 사용하여 계정 및 사서함 만들기](#create-device-acct-exch-admin-ctr)
2.  [Exchange 관리 센터에서 모바일 디바이스 사서함 정책 만들기](#create-device-acct-exch-mbx-policy)
3.  [PowerShell을 사용하여 계정 구성](#create-device-acct-exch-powershell-conf)
4.  [비즈니스용 Skype와 함께 계정을 사용하도록 설정](#create-device-acct-exch-skype-for-business)

### <a href="" id="create-device-acct-exch-admin-ctr"></a>Exchange 관리 센터를 사용하여 계정 및 사서함 만들기

1.  Exchange 관리자 자격 증명을 사용하여 Exchange 관리 센터에 로그인합니다.
2.  EAC(Exchange 관리 센터)에 있는 경우 왼쪽 패널에서 **받는 사람**으로 이동합니다.

    ![Exchange 관리 센터의 사서함을 보여 주는 이미지](images/setupdeviceacctexch-01.png)

3.  사서함 목록 위에 있는 컨트롤에서 **+** 를 선택하여 새 사서함을 만들고 **표시 이름**, **이름** 및 **사용자 로그온 이름**을 입력한 다음 **저장**을 클릭합니다.

    ![새 사서함 만들기를 보여 주는 이미지](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>Exchange 관리 센터에서 모바일 디바이스 사서함 정책 만들기

>[!NOTE]
>만든 계정에 정책을 만들고 할당 하 고 Exchange 2010를 사용 하는 경우 EMC (Exchange 관리 콘솔)을 사용 하는 경우 정책 만들기 및 정책 할당과 관련 된 해당 정보를 찾습니다.

 

1.  Exchange 관리 센터로 이동합니다.

    ![Exchange 관리 센터를 보여 주는 이미지](images/setupdeviceacctexch-03.png)

2.  모바일 디바이스 사서함 정책을 만들려면 왼쪽 패널에서 **모바일**을 클릭한 다음 **모바일 디바이스 사서함 정책**을 클릭합니다. Surface Hub에는 암호를 요구하지 않는 모바일 디바이스 사서함 정책을 가진 계정이 필요하므로 이 요구 사항에 맞는 기존 정책이 이미 있는 경우 해당 정책을 계정에 적용할 수 있습니다. 그렇지 않으면 다음 단계에 따라 Surface Hub 디바이스 계정에만 사용할 새 정책을 만듭니다.

    ![Exchange 관리 센터를 사용하여 모바일 디바이스 사서함 정책 만들기를 보여 주는 이미지](images/setupdeviceacctexch-05.png)

3.  새 모바일 디바이스 계정 사서함 정책을 만들려면 새 정책을 추가할 정책 목록 위에 있는 컨트롤에서 **+** 단추를 클릭합니다. 이름에는 이 정책을 다른 디바이스 계정과 구분하는 데 도움이 되는 이름을 입력합니다(예: *SurfaceHubDeviceMobilePolicy*). 정책이 암호로 보호되지 않아야 하므로 **암호 필요**를 선택 취소된 상태로 유지하고 **저장**을 클릭합니다.

    ![새 모바일 디바이스 사서함 정책을 보여 주는 이미지](images/setupdeviceacctexch-06.png)

4.  새 모바일 디바이스 사서함 정책을 만든 후 Exchange 관리 센터로 돌아가면 새 정책이 표시됩니다.

    ![Exchange 관리 센터의 새 모바일 디바이스 사서함 정책을 보여 주는 이미지](images/setupdeviceacctexch-07.png)

5.  PowerShell을 사용하지 않고 ActiveSync 정책을 적용하기 위해 다음을 수행할 수 있습니다.

    -   EAC에서 **받는 사람** &gt; **사서함**을 클릭하고 사서함을 선택합니다.

        ![Exchange 관리 센터를 보여 주는 이미지.](images/setupdeviceacctexch-08.png)

    -   **세부 정보** 창에서 **전화 및 음성 기능**으로 스크롤한 다음 **세부 정보 보기**를 클릭하여 **모바일 디바이스 정보** 화면을 표시합니다.

        ![사서함 세부 정보를 보여 주는 이미지.](images/setupdeviceacctexch-09.png)

    -   현재 할당된 모바일 디바이스 사서함 정책이 표시됩니다. 모바일 디바이스 사서함 정책을 변경하려면 **찾아보기**를 클릭합니다.

        ![현재 할당된 모바일 디바이스 사서함 정책을 보여 주는 이미지.](images/setupdeviceacctexch-10.png)

    -   목록에서 적절한 모바일 디바이스 사서함 정책을 선택하고 **확인**, **저장**을 차례로 클릭합니다.

        ![모바일 디바이스 사서함 정책 목록을 보여 주는 이미지.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>PowerShell을 사용하여 계정 구성

이제 온라인 서비스에 연결되었으므로 디바이스 계정 설정을 완료할 수 있습니다. 디바이스 계정 메일 주소를 사용하여 다음 작업을 수행합니다.

-   사서함 유형을 일반에서 회의실로 변경합니다.
-   다양한 Exchange 속성을 변경합니다.
-   사용자 계정 암호의 사용 기간 제한이 없도록 설정합니다.

1.  계정의 메일 주소를 입력하고 해당 값을 가진 변수를 만들어야 합니다.

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    사서함에서 가져온 값을 저장하려면

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    다음을 실행하여 값을 인쇄합니다.

    ``` syntax
    $strEmail
    ```

    올바른 메일 주소가 표시됩니다.

2.  계정을 채팅방 사서함으로 변환 해야 하므로 다음을 실행 합니다.

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  Surface Hub에서 디바이스 계정을 인증하려면 디바이스가 계정을 사용하여 ActiveSync를 통해 모임 정보를 가져오고 비즈니스용 Skype에 로그인할 수 있도록 회의실 사서함 계정을 사용하도록 설정하고 암호를 설정해야 합니다.

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  디바이스 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선할 수 있습니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  이제 AD에서 몇 가지 속성을 설정해야 합니다. 이렇게 하려면 계정 별칭이 필요합니다("@" 앞에 오는 UPN의 일부).

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  먼저 AD에서 사용자를 사용하도록 설정해야 Surface Hub에서 인증할 수 있습니다. 다음을 실행합니다.

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다. 자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>비즈니스용 Skype와 함께 계정을 사용하도록 설정

비즈니스용 Skype와 함께 디바이스 계정을 사용하도록 설정합니다.

비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 다음 필수 조건을 충족해야 합니다.

-   O365 계획에 비즈니스용 Skype Online 독립 실행형 요금제 2 이상이 있어야 합니다. 계획이 회의 기능을 지원해야 합니다.
-   Surface Hub 용 전화 통신 서비스 공급자를 사용 하 여 엔터프라이즈 음성 (PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online 독립 실행형 요금제 3이 필요 합니다.
-   테넌트 사용자에게 Exchange 사서함이 있어야 합니다.
-   Surface Hub 계정에는 비즈니스용 Skype Online 독립 실행형 요금제 2 또는 비즈니스용 Skype Online 독립 실행형 요금제 3 라이선스가 필요 하지만, Exchange Online 라이선스는 필요 하지 않습니다.

1.  먼저 PC에서 원격 PowerShell 세션을 만듭니다.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. Surface Hub 계정 등록자 풀 검색

사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. 비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





