---
title: Windows 10 2에서 Windows 11 Pro/Enterprise 구성 Surface Hub 구성
description: 이 문서에는 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하기 위한 권장 사항이 포함되어 있습니다.
keywords: Surface Hub, Windows 10, 데스크톱, 설치, 구성
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 0c43e2c5977321cc2153f468bea7b5f65aa00a51
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448511"
---
# <a name="configure-windows-10-or-windows-11-proenterprise-on-surface-hub-2"></a>Windows 10 2에서 Windows 11 Pro/Enterprise 구성 Surface Hub 구성

Windows 10 또는 Windows 11 Pro/Enterprise 후 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용하여 최상의 환경을 제공하도록 앱 및 설정을 구성할 수 있습니다.

이러한 단계를 수행할 때 유선 또는 무선 키보드 및 마우스를 사용하는 것이 유용할 수 있습니다.

## <a name="configure-system-settings"></a>시스템 설정 구성

1. 디바이스에서 로컬 관리자 권한이 있는 계정으로 로그인합니다.  

    - Azure AD 가입 장치에서 Azure AD 가입을 수행하는 사용자는 로컬 관리자 그룹에 자동으로 추가됩니다.  Azure AD 전역 관리자 및 Azure AD 장치 관리자도 로컬 <a href="/azure/active-directory/devices/assign-local-admin" target="_blank">관리자입니다</a>. 

    - 명령 프롬프트에 **net localgroup 관리자** 를 입력하여 로컬 관리자 권한이 있는 계정을 나열할 수 있습니다.
    
2. 사용자 이름- **SHub-Desktop**과 같은 이름을 사용하여 디바이스 이름을 변경합니다.

3. 설정을 **설정** > **** >  **시작** > 을 선택하고 동기화 설정을 **끄**십시오.**** 

    - 여기에 사용된 설정은 최상의 큰 화면 터치 환경을 사용하도록 설정되어 있으므로 다른 장치를 동기화하지 않을 수 있습니다.
    
4. 디바이스를 다시 시작합니다.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>터치 키보드 및 터치 패드 사용

1. 시작**설정** > **** > **DevicesTyping** > 을 선택하고 태블릿 모드가 아니고 키보드가 연결되지 않은 경우 터치 키보드 표시**를 켜세요**.****

2. 작업 표시줄을 누르거나 마우스 오른쪽 단추로 클릭하고 터치 키보드 표시 **단추 및** 터치 패드 표시 **단추를 선택합니다**. 

    - 터치 키보드는 직접 사용자 입력에 유용하며, 가상 터치 패드는 정확한 선택, 화면 팁 마우스로 누르기 또는 마우스 오른쪽 단추 클릭을 위한 누르기 대신 도움이 됩니다. 
    
    - 다음 예제를 참조하세요.

      ![터치 설정.](images/touch.png)

3. 터치 키보드를 QWERTY 및 부동으로 구성합니다.

    1. 터치 **키보드를** 표시하려면 작업 표시줄에서 키보드 아이콘을 선택합니다.
    
    1. 터치 키보드에서 왼쪽 위 모서리에 있는 키보드 아이콘을 선택하여 키보드 설정을 니다.
    
    1. 위쪽 행의 마지막 키보드 유형 옆에 있는 옵션을 선택하여 QWERTY를 사용하도록 설정하고 두 번째 행의 마지막 옵션을 선택하여 부동 기능을 사용하도록 설정하면 이 큰 화면에서 유용하게 사용할 수 있습니다. 다음 예를 참조하세요.

       ![키보드 설정.](images/kbd.png)
 
4. 소프트 키보드 설정을 구성합니다.

    1. 터치 키보드**에서** 설정 아이콘을 선택하거나 입력 설정을 검색하여 **여는 경우**
    
       ![소프트 키보드 설정](images/sh2-softkeyboard.png)

    1. 맞춤법 검사, 입력 및 터치 키보드의 모든 옵션을 사용하도록 설정하십시오.


다음 예제에서는 옵션을 탐색하고 선택하는 데 유용한 트랙 패드를 보여줍니다. 화면 키보드를 사용하여 다음 Microsoft Store.

![트랙 패드 사용.](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>키보드 Bluetooth 마우스 구성(선택 사항)

커넥트 디바이스를 기본 Windows 입력 또는 정밀도 작업으로 사용하는 경우 키보드와 마우스를 사용합니다.

사용자 Surface Hub PC <a href="https://aka.ms/mm" target="_blank"> 근처에 있는 경우 테두리 없이 마우스</a>를 사용하여 PC와 PC 간에 원활하게 Surface Hub 수 있습니다. 자세한 내용은 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Garage: Mouse without Borders에서 Microsoft 다운로드를 참조하세요. </a>

## <a name="example-of-taskbar-layout"></a>작업 표시줄 레이아웃의 예

Windows 10 또는 Windows 11 Pro/Enterprise에 대해 Surface Hub 2를 설정/구성하기 위한 아래 단계를 완료한 후 각 응용 프로그램의 빠른 원터치 실행을 위해 가장 많이 사용하는 응용 프로그램을 작업 표시줄에 고정하는 것이 좋습니다. 다음은 작업 표시줄이 어떻게 표시될 수 있는지의 예입니다.

 ![작업 표시줄 레이아웃](images/taskblyt.png)
### <a name="update-installed-apps"></a>설치된 앱 업데이트

설치된 모든 스토어 앱을 업데이트하는 경우:

1. 앱 Microsoft Store 열고 오른쪽 위 모서리에서 더 많은 **** 타원 보기를 선택합니다.
2. 다운로드 **및 업데이트를 선택합니다.**
3. 업데이트 **다운로드 선택**

### <a name="scan-for-and-install-all-windows-updates"></a>모든 업데이트 검색 Windows 설치

마이그레이션 후 설치할 수 있는 서비스 및 기능 업데이트가 있을 수 있습니다. 

- **** >  설정**Update & 보안** > 업데이트 **확인을 선택합니다**.
- 업데이트가 있는 경우 업데이트를 설치하고 다시 시작한 후 다음 알림이 표시될 때까지 프로세스를 반복합니다.

> [!div class="mx-imgBorder"]
> ![Windows 업데이트 '최신 정보' 알림입니다.](images/wustatus.png)


## <a name="onedrive-for-business"></a>비즈니스용 OneDrive

이 <a href="/onedrive/onedrive" target="_blank"> 비즈니스용 OneDrive</a> 사용하여 모든 작업 장치 간에 도구, 로그 및 기타 파일을 쉽게 공유할 수 있습니다.

- OneDrive 데스크톱 및 Intune에서 관리하는 모바일 장치 간에 작업 Surface Hub 공유할 수 있습니다. 모든 장치에서 파일을 편집할 수 있으며 모든 네트워크 연결 장치가 변경 내용으로 업데이트됩니다.

- Surface Hub SSD(128GB)의 크기를 고려하여 OneDrive 데스크톱 장치에서 Surface Hub 구성하는 경우 기본 구성은 파일을 온라인에서 유지하고 파일을 사용할 때 파일을 다운로드하는 것입니다.

필요한 OneDrive 파일만 다운로드하도록 구성하려면 필요할 때 파일 관리 파일 설정을 공간 **** 절약 및 파일 다운로드로 **설정하십시오**. 자세한 내용은 2013 <a href="/onedrive/files-on-demand-windows" target="_blank"> 에서 쿼리 및 요구 시 파일 관리 상태 Windows</a>.

![OneDrive 설정](images/onedrive.png)

> [!NOTE]
> 이러한 단계를 반복하여 개인 설정을 구성할 수도 OneDrive 드라이브 공간을 절약하고 필요할 때만 파일을 다운로드해야 합니다.

## <a name="sharepoint-and-teams"></a>SharePoint Teams

SharePoint 및 Teams 채널 파일은 데스크톱 장치(예: 랩톱 및 Surface Hub)에 로컬로 동기화할 수도 OneDrive 동기화 있습니다.

내부 회사 파일을 로컬 드라이브에 동기화하려면 OneDrive 동기화:

1. 사이트 SharePoint 이동하여 로컬 장치에서 보거나 편집하는 데 관심이 있는 파일의 최상위 문서 디렉터리로 이동합니다.

2. 창의 리본 **메뉴** 위쪽에 있는 동기화 단추를 SharePoint 선택합니다.

3. 팝업**에서 열**기에서 선택합니다 **. 이 사이트가** 팝업 창을 Microsoft OneDrive.

4. 작업 표시줄의 SharePoint 오른쪽에 있는 OneDrive 아이콘을 선택하여 로컬 드라이브와 동기화하고 있는지를 확인할 수 있습니다.

5. 파일을 온라인에서 유지하고 파일을 사용할 때만 다운로드할 수 있는 구성이 설정되어 있는지 확인:

    1. 파일 탐색기를 니다.
    
    2. 으로 이동하여 사용자 SharePoint 마우스 오른쪽 단추로 클릭합니다(예: **Contoso \ \<SharePoint Document Folder Name\>**).
    
    3. 공간 **비우기 를 선택합니다**.
    
    4. 상태 열에는 파일 및 폴더의 상태가 표시됩니다. 자세한 내용은 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 클라이언트와 SharePoint 파일 동기화를 OneDrive 동기화 참조하세요</a>.
    
6. Teams 채널 파일은 버전 기록 및 로컬 SharePoint 동기화를 포함하여 동일한 SharePoint 문서 기능과 함께 SharePoint 사이트에 저장됩니다. 채널 Teams 동기화하려면

    1. 관심 있는 Teams 채널로 이동하고 맨 위에 있는 파일 **탭**을 선택합니다. 그런 다음 동기화 **를 선택합니다**. 파일이 동기화를 시작하고 Desktop **\ Contoso \ 의 파일 탐색기에서 표시됩니다 \<name of the Teams Channel\>**.
    
    2. SharePoint 사이트를 동기화하는 데 사용한 절차와 동일한 절차를 사용하여 파일을 클라우드에 보관하고 파일을 사용할 때만 다운로드하고, Teams 채널 이름의 파일 탐색기를 탭하고 마우스 오른쪽 단추로 클릭한 다음 공간 비우기를 선택하여 파일을 다운로드**합니다.**

## <a name="surface-hub-pen-settings"></a>Surface Hub 펜 설정

**펜 Bluetooth Surface Hub 페어링**

펜을 페어링하여 펜 펌웨어를 최신으로 유지하고, 펜 바로 가기를 설정하고, Bluetooth 장치 설정 페이지 또는 Surface 앱에서 배터리 충전 정보를 얻습니다.

1. 시작**설정** > **** >  **선택합니다**.

2. 사용자 **또는 Bluetooth 추가를 선택합니다**.

3. 선택 **Bluetooth**.

4. 펜 tail 단추를 제거하고 흔들어 배터리 연결을 끊습니다.

5. 캡을 다시 넣은 다음 페어링 LED가 깜박일 때까지 캡을 누르고 있습니다.

6. 설정 Surface Hub Bluetooth 2 펜을 Surface Hub **선택합니다**.

7. 페어링 작업을 완료합니다. 

8. 페어링에 성공하지 못하면 펜을 다시 페어링해 하세요. 그래도 문제가 해결되지 않는 경우 펜이 화이트보드 응용 프로그램에서 작동하는지 확인하여 배터리가 충전되어 있는지 테스트할 수 있습니다. 그렇지 않은 경우 배터리를 교체하고 펜을 다시 페어링합니다.  필요한 경우 장치를 다시 시작한 다음 다시 시도하십시오.

**펜 바로 가기 설정** Surface Hub 펜에 "tail click"이라고도 하는 바로 가기 단추가 있습니다. 바로 가기를 구성하려면 앞에서 설명한 대로 펜을 먼저 페어링해야 합니다.

1. 펜을 검색하고 **펜 & Windows Ink 선택합니다**.

2. 페이지 아래쪽에서 다음과 같이 대화 상자를 여는 펜 바로 가기를 선택합니다.

   ![펜 바로 가기](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>카메라 구성

디바이스의 위쪽 또는 한 쪽에 카메라를 탑재할 수 있습니다. 카트 대신 데스크톱 독립 실행형 또는 허브 근처에 있는 허브를 사용하는 경우 카메라 각도를 최적화하기 위해 위치에 카메라를 탑재합니다. 카메라가 자동 회전하지 않습니다. 따라서 카메라를 수동으로 회전하려면 2mm 16진수 키가 필요합니다. 

카메라를 사이 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 드 마운트하고 카메라를 수동으로 회전하는 방법에 대한 자세한 내용은 2S 카메라 Surface Hub 방향을 참조하세요</a>.

## <a name="windows-hello-configuration"></a>Windows Hello 구성

Surface Hub 또는 Windows 10 Windows 11 Pro/Enterprise 2S를 사용하면 Win32 데스크톱 응용 프로그램의 전체 제품군과 생체 인식 Windows Hello 있습니다. Surface Hub 2 지문 판독기 액세서리를 장치의 모든 USB-C 포트에 연결할 수 있습니다. 

Surface Hub 2 지문 판독기를 주문하거나 기술 사양을 보기 위해서는 (surface-hub-2-essential-add-ons.md" target="_blank">Essential 추가 기능을 Windows 10 Pro 및 Enterprise Surface Hub 2</a>에서 참조합니다. 

지문 판독기를 삽입한 후 시작설정**** > **** > **AccountsSign-in** >  **옵션** > Windows Hello **Fingerprint**를 선택하여 지문을 등록합니다.

얼굴 Windows Hello 인증된 디바이스를 사용합니다. 2S Surface Hub 안면 인식을 지원하지 Windows Hello 않습니다.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>작업 표시줄에서 잠금 화면 바로 가기 아이콘 사용

작업 표시줄에 아이콘을 추가하면 Windows-L 바로 가기 키와 유사한 원터치 화면 잠금을 사용할 수 있습니다. 

1.  바탕 화면을 탭하고 누르거나 마우스 오른쪽 단추로 클릭하고 **** NewShortcutBrowseDesktopOKNext**** > **** > **** > **** >  > **를 선택합니다**.

1.  내 **PC** 잠금과 같은 바로 가기 이름을 입력한 다음 마친을 **선택합니다**.

1.  바탕 화면에서 새로 만든 바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 속성을 **선택합니다**. 바로 가**기 탭**의 대상 필드에 **Rundll32.exe User32.dll,LockWorkStation을 입력합니다.** ****

1.  아이콘 **변경 단추를** 선택하고 아이콘을 **C:\Windows\System32\imageres.dll** 사용할 아이콘을 선택합니다. 

    다음 예제를 참조하세요.

    ![아이콘을 선택 합니다.](images/lock.png)
    
1.  확인 **을 선택하여** 바로 가기를 저장합니다.

1.  바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 작업 표시줄에 고정 **을 선택합니다**.

1. 잠금 바로 가기를 작업 표시줄에 고정한 후 바탕 화면에서 삭제할 수 있습니다.

## <a name="applications"></a>응용 프로그램


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

설치하려면 Microsoft Whiteboard.

 - 작업 **Windows Ink 작업 영역** 오른쪽 아래에서 선택 아이콘을 선택하고 화이트보드를 **다운로드합니다**.
 
   ![Ink 작업 영역](images/ink.png) 

또는 다음 창에서 화이트보드를 설치할 Microsoft Store.

1. 앱 Microsoft Store 열고 **화이트보드를 검색합니다**.

2. 여러 **장치에서 로그인** 하고 사용 하여 감사합니다.를 선택하십시오.

3. 화이트보드를 작업 표시줄에 고정합니다.

### <a name="surface-app"></a>Surface 앱

1. 이 Microsoft Store Surface를 검색**합니다**.

2. 필터**에서 사용 가능을** 모든 장치**로 설정**

3. Surface 앱을 **설치** 합니다. 나열된 첫 번째 앱입니다. 앱을 설치하려면 MSA를 스토어에 연결해야 할 수 있습니다.

4. Surface 앱을 **작업** 표시줄에 고정합니다.

### <a name="snip--sketch"></a>캡처 및 스케치

1. 스케치 앱을 **& Snip** 앱을 열고 작업 표시줄에 고정합니다.

2. 오른쪽 위 모서리에서 타원을 선택한 다음 **설정.**

3. 이 **설정** 클립**보드에 자동** **복사, 스**니프 저장 및 여러 창(선택 사항)**을 니다**.

### <a name="microsoft-office"></a>Microsoft Office

1. <a href="https://portal.office.com/account#installs" target="_blank"> Office 포털을 열</a>고 원하는 응용 프로그램을 설치합니다.

2. 원하는 Office 응용 프로그램을 작업 표시줄에 고정합니다.

3. 설치 Outlook OST를 설정하여 지난 Outlook 캐시만 저장해야 합니다. 이렇게 하면 디스크 사용량 및 설정 시간이 크게 줄어듭니다.

    - 파일**계** > **정 설정** 선택하고 계정을 선택합니다.
    
    - 변경**을 선택하고** 캐시된 Exchange 모드에 **** 대한 슬라이더를 14일로 설정하십시오.

### <a name="microsoft-teams"></a>Microsoft Teams

1. 를 다운로드하여 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams</a>.

2. 응용 프로그램을 자동으로 시작하도록 설정을 구성합니다(선택 사항).

3. 작업 Teams 고정합니다.

4. 방해가 Teams 않도록 디바이스에서 알림 메시지를 줄이는 것이 좋습니다(선택 사항).

   ![Teams 알림입니다.](images/teams.png)

### <a name="connect-app"></a>커넥트 앱

> [!IMPORTANT]
> Windows 10 버전 2004 이상에서는 커넥트 사용하는 무선 투영용 Miracast 앱이 기본적으로 설치되지 않지만 선택적 기능으로 사용할 수 있습니다. 2004 이상 버전의 Windows 설치(또는 업데이트)한 경우 설정에서 이 PC에 투영 화면에 다음이 표시될 수 있습니다.

![Project PC에 연결합니다.](images/sh2-project.png) 


1. "이 PC에 투영" 설정 페이지에서 앱을 설치하려면 선택 **** >  적 기능 **추가** 기능을 선택한 다음 무선 디스플레이 앱을 **설치**합니다.

2. 일부 **Windows 및 Android** 장치에서 확인이 된다고 말하면 이 PC에 프로젝트할 수 있습니다. 아래에서 다음을 선택하십시오.

    - **장치가 회사** 네트워크에 없는 경우 모든 곳에서 사용할 수 있습니다.
    - 그렇지 않은 경우 보안 네트워크 **의 모든 곳에서 사용 가능을 선택하세요**.
    
3. 이 **PC에 프로젝트 요청에서** 처음만 **선택하십시오**.

4. 페 **어링을 위해 PIN 필요에서** 사용 안 을 **선택 합니다**.

5. 그런 다음 앱을 시작하고 작업 표시줄에 고정하기 위해 **앱을 커넥트.**

6. 앱을  열 수 있습니다. 앱이 열려 있는 동안 작업 표시줄에서 커넥트 앱 아이콘을 마우스 오른쪽 단추로 클릭하고 작업 표시줄에 고정**을 선택합니다**.

7. 그런 다음 앱 커넥트 닫습니다. **Project 한** 번 이상 실행하지 않으면 이 PC에 대한 앱이 작동하지 않을 수 있습니다.

회사 네트워크에 없는 경우 권장되는 구성:

![설정.](images/project1.png)

회사 네트워크에서 권장되는 구성:

![설정 사용할 수 있습니다.](images/project2.png)

### <a name="your-phone"></a>사용자 휴대폰

**사용자 휴대폰 앱은** 기본적으로 앱에 Windows 10. 이 저장소가 없는 경우 스토어의 스토어에서 설치할 Windows 있습니다.

앱을 설정하는 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 방법에 대한 자세한 내용은 PC와 휴대폰 간에 사용자 휴대폰 Windows 10 설정하는 방법을 참조하세요</a>. 또한 앱에서 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 앱의 일반적인 문제를 사용자 휴대폰 방법을 Windows 10</a>.

###  <a name="fancy-zones"></a>멋진 영역


**멋진 영역**은 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"></a> PowerToys 도구 모음의 GitHub. 디스플레이에서 고정 레이아웃("영역")을 정의한 다음 각 영역에서 실행할 앱을 선택할 수 있도록 하여 Surface Hub 2의 화면 공간 활용에 좋은 방법입니다. 


PowerToys [Wiki](https://github.com/microsoft/PowerToys/wiki)에는 [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)를 포함하여 각 도구를 사용 및 사용자 지정하는 방법에 대한 지침이 있습니다. 높은 수준에서 – 설치한 PowerToys 사용자 지정 레이아웃을 선택하거나 만든 다음 Shift 키를 아래로 끌어서 키보드 키를 사용하여 실행 중인 앱을 특정 영역으로 이동할 수 있습니다. 이 Bluetooth 또는 USB 키보드와 마우스를 사용하면 도움이 되거나 화면 터치 키보드와 터치 패드를 사용할 수 있습니다.

**전원 토이 팁**
- 앱의 PowerToys 업데이트에 대한 전자 메일 알림을 GitHub 페이지 맨 위에 있는 "등록" 단추를 [클릭합니다](https://github.com/microsoft/PowerToys/releases).
- 설치 PowerToys 설치되면 업데이트 Windows 다운로드 설정을 구성하여 최신 업데이트를 다운로드하고 설치할 PowerToys 수 있습니다.****
- PowerToys 설정으로 이동하려면 작업 표시줄에서 앱 실행 카라트 를 **** 선택한 다음 메뉴가 나타날 때까지 마우스 오른쪽 단추를 클릭하거나 PowerToys 아이콘을 누르고 있습니다. "설정"를 선택합니다.
- 설정 페이지의 PowerToys 자동으로 업데이트 다운로드**를 켜**십시오.
- 업데이트가 릴리스된 경우 업데이트 설치 Windows 옵션을 제공하도록 알림이 표시됩니다.


### <a name="edge-chromium-browser"></a>Edge Chromium 브라우저

브라우저에서 새 에지 Chromium <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">다운로드하여 설치합니다</a>.


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub 하드웨어 진단 도구

Surface Hub <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> 하드웨어 진단</a> 도구를 무료로 사용할 수 Microsoft Store. 이 도구는 사용자가 최상의 Surface Hub 수 있도록 디자인되어 있습니다. 펌웨어가 최신 버전인지와 올바르게 구성된지 확인하는 테스트가 포함되어 있습니다. 대화형 테스트를 통해 필수 기능이 예상대로 작동하고 있는지 확인할 수 있습니다. 문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다. 링크를 클릭하여 웹 응용 Microsoft Store 설치한 다음 응용 프로그램을 작업 표시줄에 고정합니다.

## <a name="additional-settings"></a>추가 설정

### <a name="pen-tail-select-to-launch-whiteboard"></a>펜 tail을 선택하여 화이트보드 시작

1. 펜을 **검색**하고 **펜 & Windows Ink 선택합니다**.

2. 페이지 아래쪽의 펜 바로 가**기 설정에서** 한 번만 **선택을 Microsoft Whiteboard****.** 

### <a name="power-management"></a>전원 관리

2에서 Windows 10 또는 Windows 11 Pro/Enterprise 최상의 환경을 얻을 수 있는 몇 가지 전원 Surface Hub 있습니다. 여기에는 화면 및 PC 시간 제한과 기본 제공 Doppler(휴먼 현재 상태 감지), 화면 보호기 및 암호 보호와 상호 작용하는 방법, 랩톱/데스크톱 사용자를 위한 그룹 정책 전원 설정을 전달하는 방법에 대한 적절한 방법도 포함됩니다.

Windows 10 Windows 11 Pro/Enterprise Surface Hub 터치, 마우스 및 키보드 동작뿐만 아니라 기본 제공 Doppler(휴먼 점유 감지)로 화면이 절전되지 않습니다. 휴먼 점유 검색은 기본적으로 사용하도록 설정되어 있지만, 원하는 경우 초기 마이그레이션의 일부로 Surface UEFI 구성 도구에서 장치 옵션을 전환하거나 이후 UEFI 구성 패키지를 구축 및 적용하여 UEFI에서 사용하지 않도록 설정할 수 있습니다. 

**전원 관리: 화면 및 PC 절전 설정**

1. 시작**설정** > **** >  **절** > 전 & **선택합니다**.

2. 전원 모드 슬라이더를 최상의 성능**으로 설정**

3. 화면 및 절전 모드 값을 기본 설정으로 구성하고 움직임이 감지될 때 디바이스를 깨우는 Doppler 현재 상태 검색을 고려합니다. 따라서 모범 사례로 화면이 2시간 후에 꺼지기로 설정하고 **PC** 에서 4시간 후에 꺼지 **기로 설정하는 것이 좋습니다.**

**전원 관리: 화면 보호기**

1. 잠금 화면 **및** 잠금 화면 **설정을 검색합니다**.

2. 화면 **시간 제한 설정 및** **화면 보호기** 설정을 기본 설정으로 구성합니다. 권장되는 기본값은:

   - 화면 보호기에서 (없음) 또는 선택한 화면 보호기입니다.
   - 15분까지 기다립니다.
   - 다시 시작 시 로그온 화면을 표시합니다.


**전원 관리: 그룹 정책**

다음 절차를 수행하기 전에 IT 부서에 승인을 요청하여 전역 전원 관리 정책에서 Surface Hub 2S 장치를 제외합니다. 일부 전원 관리 설정은 현재 상태 검색 기능을 사용하지 않도록 설정할 수 있습니다.

1. 소프트웨어 센터 **를 검색한** 후 을 .

2. 옵션을 **선택합니다**.

3. 전원 관리를 **확장하고**  IT 부서에서 이 컴퓨터에 전원 설정을 **적용하지 않습니다.를 선택합니다**.

   ![소프트웨어 설정.](images/soft-cntr.png)

### <a name="storage-sense"></a>저장소 센스

Surface Hub 2에는 로컬 저장소용 128GB SSD가 있으므로 일반 사용 중에 저장소 저장 방법을 사용하는 것이 좋습니다.  센스를 Storage:

1.  시스템 설정 **아래에** 있는 저장소 설정을 **검색합니다**.

2.  이 **설정** 저장소 센스 켜기 **** 를 선택하여 **Storage 를 니다**.

3.  센스를 Storage **켜기.**

4.  **센스 Storage 구성**을 선택하거나 지금 실행하고 제한된 드라이브 공간으로 인해 파일을 가능한 한 많이 온라인으로 유지하도록 설정을 구성합니다.

권장 설정:

- 센스 Storage = 매일 실행합니다.
- 앱에서 사용하지 않는 임시 파일 삭제 = 최소 14일마다 삭제
- 30일 넘게 다운로드한 경우 내 다운로드 폴더에서 파일을 삭제합니다.
- OneDrive: = 30일 이상 열지 않은 경우 콘텐츠가 온라인 전용이 됩니다.

### <a name="tablet-mode"></a>태블릿 모드

접근성 요구에 필요한 경우 태블릿 모드를  켜야 합니다.


### <a name="sound-settings"></a>소리 설정

1. 소리 설정을 **검색하고** 이 페이지를 여십시오.

2. 오른쪽 **의 소리 제어** 판을 선택하고 소리 탭 **을** 선택합니다.

3. 프로그램 **이벤트에서** **장치** 커넥트 **장치 연결 끊기를** 없음으로 **설정합니다**.

### <a name="silence-notifications"></a>침묵 알림

1. 포커 **스 도우미를 검색** 하고 이 페이지를 여십시오.

2. 알람 **만 선택합니다**. 이렇게 하면 상수 알림 플라이아웃이 방지됩니다.

### <a name="disk-cleanup"></a>디스크 정리

1. 디스크 정리 **를 검색하고** 이 앱을 여는 경우

2. 삭제할 **파일에서** 삭제할 파일을 선택합니다. 

3. 또한 **시스템 파일 정리를 선택합니다**.

## <a name="complete-and-verify"></a>완료 및 확인

1. 모든 앱 업데이트를 Windows 설치합니다.

2. 그룹 정책을 업데이트합니다.

   1. 승강된 명령 프롬프트에 **gpupdate /force /boot /wait:0을 입력합니다**.
   
3. 디바이스를 다시 시작합니다.

4. 작업 표시줄 앱을 검증합니다.

   - 커넥트 앱
   - 잠금 아이콘
   - 캡처 및 스케치
   - Teams(해당하는 경우)
   - Office 앱(해당하는 경우)
   - Surface 앱
   - 화이트보드
    
5. 현재 상태 검색을 검증합니다.

   - 현재 상태 검색은 시스템 트레이의 녹색 아이콘입니다.
    
6. 앱에서 이 PC에 대한 투영이 활성화되어 있는지 커넥트 확인합니다. 이 PC **Project 구성**한 후 커넥트 앱을 한 번 이상 실행합니다. 나중에 커넥트 앱을 실행하기 위해 앱을 실행하지 Surface Hub.

7. 전원 및 절전 설정을 확인합니다.

    - 화면 보호기: 15분, (없음), Mystify 또는 Blank; 암호 요구 확인란이 선택되어 있도록 합니다.
    - 화면: **2시간 후 꺼집니다**.
    - PC:  **4시간 후에 꺼집니다**.
    
8. 작동 Windows Hello 확인

9. 설정 동기화가 사용되지 않도록 설정되어 있는지 확인합니다.

10. 시작 앱을 검증합니다.

> [!TIP]
> Windows 10 설치 및 구성한 후 Surface Hub 2S는 다른 디바이스 또는 다른 장치와 Windows 10 Windows 11 있습니다.

## <a name="related-topics"></a>관련 항목

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Windows 10 2에서 Windows 10 Windows 11 Pro/Enterprise/Surface Hub 마이그레이션</a>
