---
title: Skype 하이브리드 음성 환경으로 온라인 또는 하이브리드 배포(Surface Hub)
description: 이 항목에서는 클라우드 커넥터 버전 또는 비즈니스용 Skype 2015 풀을 통한 온-프레미스 PSTN 연결을 사용하여 비즈니스용 Skype 클라우드 PBX를 활성화하는 방법에 대해 설명합니다.
keywords: 하이브리드 배포, Skype 하이브리드 음성
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836431"
---
# Skype 하이브리드 음성 환경으로 온라인 또는 하이브리드 배포(Surface Hub)

이 항목에서는 클라우드 커넥터 버전 또는 비즈니스용 Skype 2015 풀을 통한 온-프레미스 PSTN(공중 전화망) 연결을 사용하여 비즈니스용 Skype 클라우드 PBX를 활성화하는 방법에 대해 설명합니다. 이 옵션에서는 클라우드에 있는 비즈니스용 Skype 홈 풀과 Exchange 서버는 비즈니스용 Skype 2015 또는 클라우드 커넥터 버전을 실행하는 온-프레미스 풀을 통해 PSTN으로 연결됩니다. [다른 클라우드 PBX 옵션](https://technet.microsoft.com/library/mt612869.aspx)에 대해 자세히 알아보세요.  

하이브리드 음성 옵션 중 하나를 사용하여 비즈니스용 Skype 클라우드 PBX를 배포한 경우 Surface Hub용 회의실 계정을 사용하도록 설정하려면 다음 단계를 수행합니다. 먼저 일반 사용자 계정을 만들고 모든 하이브리드 음성 옵션 및 전화 번호를 할당한 다음, 회의실 계정으로 계정 변환을 고려해야 합니다. 이 순서대로 수행하지 않으면 하이브리드 전화 번호를 할당할 수 없습니다.  

>[!WARNING]
>하이브리드 음성을 구성하기 전에 계정을 만드는 경우 (Enable-CSMeetingRoom 명령을 실행하면) 필요한 하이브리드 음성 매개 변수를 구성할 수 없게 됩니다. 이전에 구성된 계정에 대한 하이브리드 음성 매개 변수를 구성하거나 전화 번호를 다시 구성하려면 E5 또는 E3 + 클라우드 PBX 추가 기능 라이선스를 삭제한 후 3단계부터 시작하여 다음 단계를 수행합니다.

1. Surface Hub용 새 사용자 계정을 만듭니다. 이 예제에서는 <strong> surfacehub2@adatum.com </strong> 를 사용 합니다. 계정은 로컬 Active Directory에서 만들고 클라우드와 동기화 하거나 클라우드에서 직접 만들 수 있습니다. 

    ![새 개체 사용자](images/new-user-hybrid-voice.png)

2. **암호 사용 기간 제한 없음**을 선택합니다. Surface Hub 디바이스에 중요합니다.

   ![암호 사용 기간 제한 없음](images/new-user-password-hybrid-voice.png)

3. Office 365에서 **E5** 라이선스 또는 **E3 및 클라우드 PBX** 추가 기능을 회의실 사용자 계정에 추가합니다. 하이브리드 음성을 작동하는 데 필요합니다.

   ![제품 라이선스 추가](images/product-license-hybrid-voice.png)

4. 회의실 사용자 계정이 비즈니스용 Skype Online에 표시될 때까지 15분 정도 기다립니다.

5. 비즈니스용 Skype Online에서 회의실 사용자 계정을 만든 후 비즈니스용 Skype 원격 PowerShell에서 하이브리드 음성을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. Surface Hub에서 테스트 전화를 걸어 하이브리드 음성 통화 흐름을 확인합니다.

7. PC에서 원격 PowerShell 세션을 시작하고 다음 cmdlet을 실행하여 Exchange에 연결합니다.

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. 세션을 설정한 후 회의실 사용자 계정을 **RoomMailboxAccount**로 사용하려면 다음 cmdlet을 실행하여 회의실 사용자 계정을 수정합니다. 이렇게 하면 계정이 Surface Hub에 인증할 수 있습니다.

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. 사서함을 설정한 후 새 Exchange ActiveSync 정책을 만들거나 호환되는 기존 정책을 사용해야 합니다.

   Surface Hub는 **PasswordEnabled** 속성이 **False**로 설정된 ActiveSync 정책이 있는 장치 계정하고만 호환됩니다. 제대로 설정하지 않으면 Surface Hub의 Exchange 서비스(메일, 일정 및 모임 참가)를 사용할 수 없습니다.
    
   호환되는 정책을 아직 만들지 않은 경우 “Surface Hubs”라는 정책을 만드는 다음 cmdlet을 사용합니다. 정책을 만든 후 다른 장치 계정에 동일한 정책을 적용할 수 있습니다.

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   호환되는 정책이 만들어지면 장치 계정에 정책을 적용해야 합니다. 그러나 정책은 사용자 계정에만 적용할 수 있고 리소스 사서함에는 적용할 수 없습니다. 다음 cmdlet을 실행하여 사서함을 사용자 유형으로 변환하고 정책을 적용한 다음 사서함으로 다시 변환해야 합니다. 계정을 다시 사용하도록 설정하고 암호도 다시 설정해야 할 수 있습니다.
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. 장치 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선해야 합니다. [Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md)에서 설정할 수 있는 속성을 확인할 수 있습니다. 다음 cmdlet은 Exchange 속성을 설정하는 예를 제공합니다.

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. 비즈니스용 Skype Online에서 사서함을 모임 장치로 사용하도록 설정합니다. 계정을 모임 장치로 사용할 수 있도록 하는 다음 cmdlet을 실행 합니다. 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    이 cmdlet을 실행하면 다음 이미지와 같이 사용자에게 회의실에 있는지 묻는 메시지가 표시됩니다. **예**를 선택하는 경우 마이크와 스피커가 음소거됩니다.

    ![](images/adjust-room-audio.png)


    
현재 하이브리드 음성을 포함한 회의실 계정이 완전히 구성됩니다. Skype 온-프레미스를 사용하면 설명, 위치 등과 같은 온-프레미스에 대한 추가 특성 구성할 수 있습니다. Skype 온라인에 회의실을 만드는 경우 이러한 매개 변수를 온라인 설정할 수 있습니다. 

다음 이미지에서 디바이스에 표시되는 방식을 확인할 수 있습니다.


![](images/select-room-hybrid-voice.png)
