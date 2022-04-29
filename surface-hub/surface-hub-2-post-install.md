---
title: Windows 10/11 Pro 구성하거나 Surface Hub 2에서 Enterprise
description: 이 문서에는 개인 설정된 대형 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하기 위한 권장 사항이 포함되어 있습니다.
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
ms.openlocfilehash: 2b645ef580eda85a91bf282c8772c42c09cbb67d
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497771"
---
# <a name="configure-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>Windows 10/11 Pro 구성하거나 Surface Hub 2에서 Enterprise

Windows 10/11 Pro 또는 Enterprise 마이그레이션한 후 이 맞춤형 대형 화면 터치 및 펜 컴퓨터를 사용하여 최상의 환경을 보장하도록 앱 및 설정을 구성할 수 있습니다.

이러한 단계를 수행할 때 유선 또는 무선 키보드와 마우스를 사용하는 것이 유용할 수 있습니다.

## <a name="configure-system-settings"></a>시스템 설정 구성

1. 디바이스에서 로컬 관리자 권한이 있는 계정으로 로그인합니다.  

    - Azure AD 조인된 디바이스에서 Azure AD 조인을 수행하는 사용자는 로컬 관리자 그룹에 자동으로 추가됩니다.  Azure AD 전역 관리자 및 Azure AD 디바이스 관리자도 로컬 관리자입니다<a href="/azure/active-directory/devices/assign-local-admin" target="_blank"></a>. 

    - 명령 프롬프트에서 **net localgroup 관리자** 를 입력하여 로컬 관리자 권한이 있는 계정을 나열할 수 있습니다.
    
2. 이름(예: **username-SHub-Desktop**)을 사용하여 디바이스 이름을 바꿉니다.

3. **시작** > **설정** > **AccountsSync** >  설정을 선택하고 **동기화 설정을** 해제**합니다**. 

    - 여기서 사용되는 설정은 최상의 대형 화면 터치 환경을 사용하도록 설정되므로 다른 디바이스를 동기화하지 않을 수 있습니다.
    
4. 디바이스를 다시 시작합니다.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>터치 키보드 및 터치 패드 사용

1. **시작** > **설정** > **DevicesTyping을** >  선택하고 **태블릿 모드가 아니고 키보드가 연결되어 있지 않은 경우 터치 키보드 표시**를 켭니다.****

2. 작업 표시줄을 길게 누르거나 마우스 오른쪽 단추로 클릭하고 **터치 키보드 표시 단추** 와 **터치 패드 표시 단추를** 선택합니다. 

    - 터치 키보드는 직접 사용자 입력에 유용하며, 가상 터치 패드는 정확한 선택, 화면 팁 가리키기 또는 마우스 오른쪽 단추를 길게 누르는 대신 도움이 됩니다. 
    
    - 다음 예제를 참조하세요.

      ![터치 설정.](images/touch.png)

3. 터치 키보드를 QWERTY 및 부동으로 구성합니다.

    1. 작업 표시줄에서 **키보드** 아이콘을 선택하여 터치 키보드를 표시합니다.
    
    1. 터치 키보드의 왼쪽 위 모서리에 있는 키보드 아이콘을 선택하여 키보드 설정을 엽니다.
    
    1. 위쪽 행에서 마지막 키보드 유형 옆을 선택하여 QWERTY를 사용하도록 설정하고 두 번째 행의 마지막 옵션을 선택하여 부동 소수를 사용하도록 설정합니다. 이 큰 화면에서 유용합니다. 다음 예를 참조하세요.

       ![키보드 설정.](images/kbd.png)
 
4. 소프트 키보드 설정을 구성합니다.

    1. 터치 키보드에서 **설정** 아이콘을 선택하거나 **입력 설정을** 검색하여 엽니다.
    
       ![소프트 키보드 설정.](images/sh2-softkeyboard.png)

    1. 맞춤법, 입력 및 터치 키보드에서 모든 옵션을 사용하도록 설정합니다.


다음 예제에서는 옵션을 탐색하고 선택하는 데 유용한 트랙 패드를 보여줍니다. 화상 키보드는 Microsoft Store 검색하는 데 사용됩니다.

![트랙 패드 사용.](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Bluetooth 키보드 및 마우스 구성(선택 사항)

장치를 기본 Windows 디바이스로 사용하거나 입력 또는 정밀도 작업에 자주 사용하는 경우 키보드와 마우스를 커넥트.

Surface Hub 장치가 PC 근처에 있는 경우 테두리</a>가 없는 마우스를 사용하여 <a href="https://aka.ms/mm" target="_blank"> Surface Hub PC 간에 원활하게 이동할 수 있습니다. 자세한 내용은 차고: 테두리가 없는 마우스에서 Microsoft 다운로드를 참조 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 하세요. </a>

## <a name="example-of-taskbar-layout"></a>작업 표시줄 레이아웃의 예

아래 단계를 완료하여 Windows 10/11 Pro 또는 Enterprise 대한 Surface Hub 2를 설정/구성한 후 가장 많이 사용되는 애플리케이션을 작업 표시줄에 고정하여 각 애플리케이션의 빠른 원터치 시작을 수행하는 것이 좋습니다. 다음은 작업 표시줄의 모양에 대한 예입니다.

 ![작업 표시줄 레이아웃입니다.](images/taskblyt.png)
### <a name="update-installed-apps"></a>설치된 앱 업데이트

설치된 모든 스토어 앱을 업데이트하려면 다음을 수행합니다.

1. Microsoft Store 앱을 열고 오른쪽 위 모서리에서 줄임표 **더 보기**를 선택합니다.
2. **다운로드 및 업데이트를 선택합니다.**
3. **업데이트 가져오기** 선택

### <a name="scan-for-and-install-all-windows-updates"></a>모든 Windows 업데이트 검색 및 설치

마이그레이션 후 설치할 수 있는 서비스 및 기능 업데이트가 있을 수 있습니다. 

- **설정** > **& 보안 > 업데이트 확인**으로 이동하고 **업데이트 확인을** 선택합니다.
- 업데이트가 있는 경우 다음 알림이 표시될 때까지 업데이트를 설치하고 다시 부팅한 다음 프로세스를 반복합니다.

> [!div class="mx-imgBorder"]
> !['최신 상태' 알림을 Windows 업데이트.](images/wustatus.png)


## <a name="onedrive-for-business"></a>비즈니스용 OneDrive

비즈니스용 OneDrive</a> 사용하여 <a href="/onedrive/onedrive" target="_blank"> 모든 작업 디바이스 간에 도구, 로그 및 기타 파일을 쉽게 공유할 수 있습니다.

- OneDrive 랩톱, Surface Hub Desktop 및 Intune 관리형 모바일 장치 간에 작업 파일을 공유할 수 있습니다. 모든 디바이스에서 파일을 편집할 수 있으며 모든 네트워크에 연결된 디바이스는 변경 내용으로 업데이트됩니다.

- Surface Hub SSD(128GB)의 크기를 고려하여 Surface Hub Desktop 디바이스에서 OneDrive 구성하는 경우 기본 구성은 파일을 온라인 상태로 유지하고 파일을 사용할 때 다운로드하는 것입니다.

필요한 경우에만 파일을 다운로드하도록 OneDrive 구성하려면 파일 **주문형** 설정을 설정하여 **공간을 절약하고 파일을 사용할 때 다운로드합니다**. 자세한 내용은 <a href="/onedrive/files-on-demand-windows" target="_blank"> Windows</a> 요청 시 파일 상태 쿼리 및 설정을 참조하세요.

![OneDrive 설정입니다.](images/onedrive.png)

> [!NOTE]
> 이러한 단계를 반복하여 개인 OneDrive 구성할 수도 있지만 드라이브 공간을 절약하고 필요에 따라 파일만 다운로드해야 합니다.

## <a name="sharepoint-and-teams"></a>SharePoint 및 Teams

SharePoint 및 Teams 채널 파일은 OneDrive 동기화 엔진을 사용하여 랩톱 및 Surface Hub와 같은 데스크톱 디바이스에 로컬로 동기화할 수도 있습니다.

OneDrive 동기화 앱을 사용하여 로컬 드라이브에 내부 회사 파일을 동기화하려면 다음을 수행합니다.

1. SharePoint 사이트로 이동하여 로컬 디바이스에서 보거나 편집하려는 파일에 대한 최상위 문서 디렉터리로 이동합니다.

2. SharePoint 리본의 맨 위에 있는 **동기화** 단추를 선택합니다.

3. 팝업에서 **열기**를 선택합니다 **. 이 사이트에서 Microsoft OneDrive 열려고 합니다**.

4. 작업 표시줄의 오른쪽 아래에 있는 OneDrive 아이콘을 선택하여 SharePoint 파일이 로컬 드라이브와 동기화되는지 확인합니다.

5. 파일을 온라인 상태로 유지하고 파일을 사용할 때만 다운로드하도록 구성이 설정되어 있는지 확인합니다.

    1. 파일 탐색기를 엽니다.
    
    2. SharePoint 이름으로 이동하여 마우스 오른쪽 단추로 클릭합니다(예: **Contoso \ \<SharePoint Document Folder Name\>**.
    
    3. **공간 확보를** 선택합니다.
    
    4. 상태 열에는 파일 및 폴더의 상태가 표시됩니다. 자세한 내용은 OneDrive 동기화 클라이언트와 SharePoint 파일 동기화를 참조 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 하세요</a>.
    
6. Teams 채널 파일은 버전 기록 및 로컬 데스크톱 디바이스에 동기화를 포함하여 동일한 SharePoint 문서 기능을 사용하여 SharePoint 사이트에 저장됩니다. Teams 채널 파일을 동기화하려면 다음을 수행합니다.

    1. 관심 있는 Teams 채널로 이동하고 맨 위에 있는 **파일** 탭을 선택합니다. 그런 다음 **동기화**를 선택합니다. 파일 동기화를 시작하고 **Desktop \ Contoso \ \<name of the Teams Channel\>** 파일 탐색기 표시됩니다.
    
    2. SharePoint 사이트를 동기화하는 데 사용한 것과 동일한 절차를 사용하여 파일을 클라우드에 유지하고 사용할 때만 다운로드합니다. Teams 채널 이름에서 파일 탐색기 길게 누르거나 마우스 오른쪽 단추로 클릭한 다음 **공간을 확보**하도록 선택합니다.

## <a name="surface-hub-pen-settings"></a>펜 설정 Surface Hub

**Bluetooth Surface Hub 펜 페어링**

펜을 페어링하여 펜 펌웨어를 최신 상태로 유지하고, 펜 바로 가기를 설정하고, Bluetooth 장치 설정 페이지 또는 Surface 앱에서 배터리 충전 정보를 가져옵니다.

1. **시작** > **설정** > **예정을** 선택합니다.

2. **Bluetooth 또는 기타 디바이스 추가를** 선택합니다.

3. **Bluetooth** 선택합니다.

4. 펜 테일 단추를 제거하고 흔들면 배터리 연결이 끊어집니다.

5. 캡을 다시 켜고 페어링 LED가 깜박일 때까지 캡을 길게 누릅니다.

6. Surface Hub Bluetooth 설정에서 **Surface Hub 2펜을** 선택합니다.

7. 페어링 작업을 완료합니다. 

8. 페어링에 성공하지 못한 경우 펜을 다시 페어링해 보세요. 이것이 작동하지 않는 경우 화이트보드 애플리케이션에서 펜이 작동하는지 확인하여 배터리가 충전되었는지 테스트할 수 있습니다. 그렇지 않은 경우 배터리를 교체하고 펜을 다시 페어링해 보세요.  필요한 경우 디바이스를 다시 시작한 다음 다시 시도합니다.

**펜 바로 가기 설정** Surface Hub 펜에는 "꼬리 클릭"이라고도 하는 바로 가기 단추가 있습니다. 바로 가기를 구성하려면 앞에서 설명한 대로 먼저 펜을 페어링해야 합니다.

1. 펜을 검색하고 **펜 & Windows Ink 설정을** 선택합니다.

2. 페이지 아래쪽에서 다음과 같이 대화 상자를 여는 펜 바로 가기를 선택합니다.

   ![펜 바로 가기입니다.](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>카메라 구성

디바이스의 위쪽 또는 양쪽에 카메라를 탑재할 수 있습니다. 카트 대신 데스크톱 스탠드로 허브를 사용하거나 허브 근처에 있는 경우 카메라를 위치에 탑재하여 카메라 각도를 최적화합니다. 카메라가 자동으로 회전하지 않으므로 카메라를 수동으로 회전하려면 2mm 16진수 키가 있어야 합니다. 

카메라를 사이드 마운트하고 카메라를 수동으로 회전하는 방법에 대한 자세한 내용은 Surface Hub 2S 카메라 렌즈 방향을 참조 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 하세요</a>.

## <a name="windows-hello-configuration"></a>Windows Hello 구성

Windows 10/11 Pro 또는 Enterprise 실행하는 Surface Hub 2S는 Win32 데스크톱 애플리케이션의 전체 제품군과 생체 인식 Windows Hello 옵션을 허용합니다. Surface Hub 2 지문 판독기 액세서리는 디바이스의 모든 USB-C 포트에 연결할 수 있습니다. 

Surface Hub 2 지문 판독기를 주문하거나 기술 사양을 보려면 (surface-hub-2-essential-add-ons.md" target="_blank">Windows 10 Pro 대한 필수 추가 기능 및 Surface Hub 2</a>의 Enterprise 참조하세요. 

지문 판독기를 삽입한 후 **시작** > **설정** > **AccountsSign-in** >  **옵션** > **Windows Hello 지문**을 선택하여 지문을 등록합니다.

얼굴 인식을 위해 Windows Hello 인증된 디바이스를 사용합니다. Surface Hub 2S 카메라는 Windows Hello 얼굴 인식을 지원하지 않습니다.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>작업 표시줄에서 잠금 화면 바로 가기 아이콘 사용

Windows-L 바로 가기 키와 유사한 원터치 화면 잠금을 사용하도록 설정하는 아이콘을 작업 표시줄에 추가하려면 다음을 수행합니다. 

1.  바탕 화면을 길게 누르거나 마우스 오른쪽 단추로 클릭하고 **NewShortcutBrowseDesktopOKNext** > **** > **** > **** > **** > 를 선택합니다.****

1.  **내 PC 잠금**과 같은 바로 가기의 이름을 입력한 다음 **마침**을 선택합니다.

1.  바탕 화면에서 새로 만든 바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 **속성을 선택합니다.** **바로 가기** 탭의 **대상** 필드에 다음을 입력합니다. **Rundll32.exe User32.dll,LockWorkStation**

1.  **아이콘 변경** 단추를 선택하고 **C:\Windows\System32\imageres.dll** 찾아 사용할 아이콘을 선택합니다. 

    다음 예제를 참조하세요.

    ![아이콘을 선택합니다.](images/lock.png)
    
1.  **확인을** 선택하여 바로 가기를 저장합니다.

1.  마우스 오른쪽 단추로 클릭하거나 탭하고 바로 가기를 누른 상태로 **작업 표시줄에 고정을** 선택합니다.

1. 작업 표시줄에 잠금 바로 가기를 고정한 후 바탕 화면에서 삭제할 수 있습니다.

## <a name="applications"></a>응용 프로그램


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

Microsoft Whiteboard 설치하려면 다음을 수행합니다.

 - 작업 표시줄의 오른쪽 아래에 있는 **Windows Ink 작업 영역** 아이콘을 선택하고 **화이트보드**를 다운로드합니다.
 
   ![잉크 작업 영역입니다.](images/ink.png) 

또는 Microsoft Store Whiteboard를 설치할 수 있습니다.

1. Microsoft Store 앱을 열고 **화이트보드**를 검색합니다.

2. 디바이스에서 로그인하고 사용하려면 **[아니요** ]를 선택합니다.

3. 작업 표시줄에 화이트보드를 고정합니다.

### <a name="surface-app"></a>Surface 앱

1. Microsoft Store Surface를 검색**합니다**.

2. 필터에서 **사용 가능한** 디바이스를 **모든 디바이스**로 설정합니다.

3. **Surface** 앱을 설치합니다. 첫 번째 앱이 나열되어야 합니다. 앱을 설치하려면 MSA를 스토어에 연결해야 할 수 있습니다.

4. **Surface** 앱을 작업 표시줄에 고정합니다.

### <a name="snip--sketch"></a>캡처 및 스케치

1. **Snip & 스케치** 앱을 열고 작업 표시줄에 고정합니다.

2. 오른쪽 위 모서리에서 줄임표를 선택한 다음 **설정** 선택합니다.

3. **설정** **클립보드에 자동 복사**, **코드 조각 저장** 및 **여러 창**(선택 사항)을 켭니다.

### <a name="microsoft-office"></a>Microsoft Office

1. Office 포털</a>을 <a href="https://portal.office.com/account#installs" target="_blank"> 열고 원하는 애플리케이션을 설치합니다.

2. 원하는 Office 애플리케이션을 작업 표시줄에 고정합니다.

3. Outlook 설치된 경우 마지막 2주 캐시만 저장하도록 Outlook OST를 설정해야 합니다. 이렇게 하면 디스크 사용량 및 설정 시간이 크게 줄어듭니다.

    - **FileAccount** >  **설정** 선택하고 계정을 선택합니다.
    
    - **변경을** 선택하고 **캐시된 Exchange 모드 사용에** 대한 슬라이더를 14일로 설정합니다.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Microsoft Teams </a>다운로드하여 설치 <a href="https://teams.microsoft.com/downloads" target="_blank"> 합니다.

2. 자동 시작 애플리케이션에 대한 설정을 구성합니다(선택 사항).

3. 작업 표시줄에 Teams 고정합니다.

4. 주의 분산을 방지하기 위해 디바이스에서 Teams 알림을 줄이는 것이 좋습니다(선택 사항).

   ![알림을 Teams.](images/teams.png)

### <a name="connect-app"></a>커넥트 앱

> [!IMPORTANT]
> Windows 10 버전 2004 이상에서는 Miracast 사용하는 무선 프로젝션용 커넥트 앱이 기본적으로 설치되지 않지만 선택적 기능으로 사용할 수 있습니다. Windows 버전 2004 이상을 설치(또는 업데이트)한 경우 설정에서 이 PC로 프로젝션 화면에 다음이 표시될 수 있습니다.

![이 PC에 Project.](images/sh2-project.png) 


1. "이 PC에 프로젝션" 설정 페이지에서 앱을 설치하려면 **선택적 기능을** >  선택하고 **기능을 추가한** 다음 **무선 디스플레이** 앱을 설치합니다.

2. **일부 Windows 및 Android 디바이스는 정상이라고 말할 때 이 PC에 프로젝션할 수 있습니다**.

    - 디바이스가 회사 네트워크에 없는 경우 **어디서나 사용할 수** 있습니다.
    - 그렇지 않으면 **보안 네트워크의 모든 위치에서 사용 가능**을 선택합니다.
    
3. **이 PC에 프로젝션하도록 요청**에서 **처음만** 선택합니다.

4. **페어링에 PIN 필요**에서 **[안 ]** 을 선택합니다.

5. 그런 다음 앱을 시작하고 작업 표시줄에 고정하려면 **커넥트** 검색합니다.

6. 앱을 엽니다. 앱이 열려 있는 동안 작업 표시줄에서 커넥트 앱 아이콘을 마우스 오른쪽 단추**로 클릭하고 작업 표시줄에 고정을** 선택합니다.

7. 그런 다음 커넥트 앱을 닫습니다. **앱이** 한 번 이상 실행되지 않는 한 이 PC에 대한 Project 작동하지 않을 수 있습니다.

회사 네트워크에 없는 경우 권장 구성:

![집에서 설정.](images/project1.png)

회사 네트워크에서 권장되는 구성:

![직장에서 설정.](images/project2.png)

### <a name="your-phone"></a>사용자 휴대폰

**전화** 앱은 기본적으로 Windows 10 설치됩니다. 없는 경우 Windows 스토어에서 설치할 수도 있습니다.

앱 설정에 대한 자세한 내용은 Windows 10 전화 설정하고 PC와 휴대폰</a> 간에 데이터를 동기화하는 방법을 참조 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 하세요. 또한 Windows 10</a> 전화 앱의 일반적인 문제를 해결하는 방법을 참조 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 하세요.

###  <a name="fancy-zones"></a>팬시 존


**팬시 존은** GitHub PowerToys</a> 도구 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> 컬렉션의 일부입니다. 디스플레이에서 고정 레이아웃("영역")을 정의한 다음 각 영역에서 실행할 앱을 선택할 수 있는 기능을 제공하여 Surface Hub 2에서 화면 공간을 활용하는 좋은 방법입니다. 


[PowerToys wiki](https://github.com/microsoft/PowerToys/wiki)에는 [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)를 포함하여 각 도구를 사용하고 사용자 지정하는 방법에 대한 지침이 있습니다. 높은 수준 – PowerToys 설치한 후 사용자 지정 레이아웃을 선택하거나 만든 다음, 시프트 키를 누른 채 키보드 키를 끌어서 실행 중인 앱을 특정 영역으로 이동할 수 있습니다. Bluetooth 또는 USB 키보드와 마우스를 사용하면 도움이 되거나 화상 터치 키보드와 터치 패드를 사용할 수 있습니다.

**파워 토이 팁**
- GitHub PowerToys 릴리스 업데이트에 대한 이메일 알림을 받으려면 [페이지](https://github.com/microsoft/PowerToys/releases) 맨 위에 있는 "등록" 단추를 클릭합니다.
- PowerToys 설치되면 Windows 알림을 받거나 PowerToys 설정을 구성하여 최신 업데이트를 다운로드하고 설치할 수 **있습니다**.
- PowerToys 설정으로 이동하려면 작업 표시줄에서 캐럿 **실행 앱을** 선택한 다음 메뉴가 나타날 때까지 마우스 오른쪽 단추로 클릭하거나 길게 누르고 PowerToys 아이콘을 누릅니다. "설정"를 선택합니다.
- PowerToys 설정 페이지 아래쪽에서 **업데이트 다운로드를 자동으로** 설정합니다.
- 업데이트가 릴리스되면 업데이트를 설치할 시기를 알려주는 Windows 알림이 표시됩니다.


### <a name="edge-chromium-browser"></a>Edge Chromium 브라우저

새 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium 브라우저를 다운로드하고 설치합니다</a>.


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub 하드웨어 진단 도구

<a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Microsoft Store 무료로 사용할 수 있는 Surface Hub 하드웨어 진단 도구</a>입니다. 이 도구는 Surface Hub 최상의 성능을 발휘할 수 있도록 설계되었습니다. 여기에는 펌웨어가 최신 상태이고 올바르게 구성되었는지 확인하는 테스트가 포함되어 있습니다. 대화형 테스트를 사용하면 필수 기능이 예상대로 작동하는지 확인할 수 있습니다. 문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다. 링크를 클릭하여 Microsoft Store 설치한 다음 애플리케이션을 작업 표시줄에 고정합니다.

## <a name="additional-settings"></a>추가 설정

### <a name="pen-tail-select-to-launch-whiteboard"></a>화이트보드를 시작하는 펜 테일 선택

1. **펜**을 검색하고 **펜 & Windows Ink 설정을** 선택합니다.

2. 페이지 아래쪽의 **펜 바로 가기** 아래에서 **선택 항목을 한 번** 설정하여 **Microsoft Whiteboard**. 

### <a name="power-management"></a>전원 관리

Surface Hub 2에서 Windows 10/11 Pro 또는 Enterprise 사용하여 최상의 환경을 제공하는 데 사용할 수 있는 몇 가지 전원 설정이 있습니다. 여기에는 화면 및 PC 시간 제한 및 기본 제공 사용자 현재 상태 감지(Doppler), 화면 보호기 및 암호 보호와 상호 작용하는 방법, 그리고 적절한 경우 랩톱/데스크톱 사용자를 위한 그룹 정책 전원 설정을 바이패스하는 방법이 포함됩니다.

Surface Hub 2의 Windows 10/11 Pro 또는 Enterprise 터치, 마우스 및 키보드 동작뿐만 아니라 기본 제공 인간 점유 감지(Doppler)로 화면이 절전 모드로 전환되지 않도록 합니다. 인간 점유 감지는 기본적으로 사용하도록 설정되어 있지만 원하는 경우 초기 마이그레이션의 일부로 Surface UEFI 구성 도구에서 디바이스 옵션을 토글하거나 이후 UEFI 구성 패키지를 빌드하고 적용하여 UEFI에서 사용하지 않도록 설정할 수 있습니다. 

**전원 관리: 화면 및 PC 절전 모드 설정**

1. **시작** > **설정** > **SystemPower** >  **& 절전 모드**를 선택합니다.

2. 전원 모드 슬라이더를 **최상의 성능**으로 설정합니다.

3. 화면 및 절전 모드 값을 기본 설정으로 구성하고 이동이 감지될 때 디바이스를 절전 모드 해제하는 Doppler 현재 상태 감지를 고려합니다. 따라서 **2시간 후에**는 화면을 끄고 PC는 **4시간 후에 끄**도록 설정하는 것이 좋습니다.

**전원 관리: 화면 보호기**

1. **잠금 화면을** 검색하고 **잠금 화면 설정을** 엽니다.

2. **화면 시간 제한 설정** 및 **화면 보호기 설정을** 기본 설정으로 구성합니다. 권장되는 기본값은 다음과 같습니다.

   - 화면 보호기를 (없음) 또는 선택한 화면 보호기로 이동합니다.
   - 대기 시간은 15분입니다.
   - 다시 시작되면 로그온 화면을 표시합니다.


**전원 관리: 그룹 정책**

다음 절차를 수행하기 전에 IT 부서에 승인을 확인하여 글로벌 전원 관리 정책에서 Surface Hub 2S 디바이스를 제외합니다. 일부 전원 관리 설정은 현재 상태 검색 기능을 사용하지 않도록 설정할 수 있습니다.

1. **소프트웨어 센터를** 검색하여 엽니다.

2. **옵션을** 선택합니다.

3. **전원 관리를** 확장하고 **IT 부서의 전원 설정을 이 컴퓨터에 적용하지 않음을** 선택합니다.

   ![소프트웨어 설정.](images/soft-cntr.png)

### <a name="storage-sense"></a>저장소 센스

Surface Hub 2에는 로컬 스토리지용 128GB SSD가 있으므로 정상적인 사용 중에 스토리지 저장 측정값의 사용을 고려해야 합니다.  Storage Sense를 구성하려면 다음을 수행합니다.

1.  시스템 설정에서 찾을 **수 있는 스토리지** 설정을 검색 **합니다**.

2.  **설정** 스토리지 **센스 켜기를** 선택하여 **Storage** 설정 페이지를 엽니다.

3.  Storage 감각을 **켜**십시오.

4.  **Storage 센스 구성을 선택하거나 지금 실행하고** 가능한 한 온라인 상태로 유지하도록 설정을 구성합니다(제한된 드라이브 공간으로 인해).

권장 설정:

- Storage Sense = 매일 실행합니다.
- 내 앱에서 사용하지 않는 임시 파일 삭제 = 14일마다(이상)
- 다운로드 폴더에 있는 파일이 30일 이상 있는 경우 파일을 삭제합니다.
- OneDrive: 콘텐츠는 30일 이상 열리지 않으면 온라인 전용이 됩니다.

### <a name="tablet-mode"></a>태블릿 모드

접근성 요구 사항이 필요한 경우 태블릿 모드를 켭니다.


### <a name="sound-settings"></a>소리 설정

1. **소리 설정을** 검색하고 이 페이지를 엽니다.

2. 오른쪽에서 **소리 제어판** 선택하고 **소리** 탭을 선택합니다.

3. **프로그램 이벤트에서** **디바이스 커넥트** 및 **디바이스 연결 끊기를** **없음**으로 설정합니다.

### <a name="silence-notifications"></a>무음 알림

1. **포커스 지원을** 검색하고 이 페이지를 엽니다.

2. **알람만** 선택합니다. 이렇게 하면 일정한 알림 플라이아웃이 방지됩니다.

### <a name="disk-cleanup"></a>디스크 정리

1. **디스크 정리**를 검색하고 이 앱을 엽니다.

2. **삭제할 파일 아래에서 삭제**할 파일을 선택합니다. 

3. **시스템 파일 정리**도 선택합니다.

## <a name="complete-and-verify"></a>완료 및 확인

1. 모든 Windows 업데이트를 검색하고 설치합니다.

2. 그룹 정책 업데이트합니다.

   1. 관리자 권한 명령 프롬프트에서 **gpupdate /force /boot /wait:0**을 입력합니다.
   
3. 디바이스를 다시 시작합니다.

4. 작업 표시줄 앱을 확인합니다.

   - 커넥트 앱
   - 잠금 아이콘
   - 캡처 및 스케치
   - Teams(해당하는 경우)
   - Office 앱(해당하는 경우)
   - Surface 앱
   - 화이트보드
    
5. 현재 상태 검색을 확인합니다.

   - 현재 상태 감지는 시스템 트레이에 녹색 아이콘이 됩니다.
    
6. 커넥트 앱에서 이 PC에 프로젝션을 사용하도록 설정되어 있는지 확인합니다. **이 PC 설정에 대한 Project** 구성한 후 커넥트 앱을 한 번 이상 실행합니다. (이후에 커넥트 앱은 Surface Hub 프로젝션하기 위해 실행될 필요가 없습니다.)

7. 전원 및 절전 모드 설정을 확인합니다.

    - 화면 보호기: 15분, (없음), Mystify 또는 Blank로 설정; 암호를 요구하는 확인란이 선택되어 있는지 확인합니다.
    - 화면: **2시간 후 꺼집니다**.
    - PC:  **4시간 후에 끄십시오**.
    
8. Windows Hello 작동하는지 확인합니다.

9. 동기화 설정을 사용할 수 없는지 확인합니다.

10. 시작 앱을 확인합니다.

> [!TIP]
> Windows 10 설치하고 구성한 후에는 다른 Windows 10 또는 Windows 11 디바이스와 마찬가지로 Surface Hub 2S를 관리할 수 있습니다.

## <a name="related-topics"></a>관련 항목

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Windows 10/11 Pro 마이그레이션하거나 Surface Hub 2에서 Enterprise</a>
