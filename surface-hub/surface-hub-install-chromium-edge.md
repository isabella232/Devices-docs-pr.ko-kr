---
title: Surface Hub에 새 Microsoft Edge 설치 및 구성
description: Surface Hub에 새 Microsoft Edge를 설치 하 고 구성 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: fe5f76034b5b8ae4801a8fb403d6db0ed423c144
ms.sourcegitcommit: 75940bb1ab4e08c96736923859c7dd673dcf8d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009616"
---
# Surface Hub에 새 Microsoft Edge 설치 및 구성

Windows 10 Team 2020 업데이트는 Chromium (버전 85 이상) 기반의 새 Microsoft Edge를 Surface Hub에 권장 하는 브라우저로 지원 합니다. Microsoft Intune 또는 기본 MDM (모바일 장치 관리) 공급자를 사용 하 여 원격으로 제공 되는 프로비저닝 패키지를 사용 하 여 Microsoft Edge를 수동으로 설치할 수 있습니다.

기본적으로 Surface Hub 디바이스는 Microsoft Edge 레거시 (버전 44)로 미리 설치 되어 있습니다.
 
Edge 개발자가 이미 설치 되어 있는 경우 다음 단계를 완료 합니다.

1. 버전을 모르거나 확인 하 고 싶은 경우에는 Edge 브라우저를 열고 edge://version로 이동 합니다.
2. **Surface Hub > 장치 관리**로 이동 합니다. **배포 패키지**에서 **배포 패키지 추가 또는 제거를 선택 합니다.**
3. 이전 설치 관리자를 사용 하 여 시작 메뉴에서 Microsoft Edge 개발자를 고정 한 경우 목록에서 **사용자 지정 시작 메뉴** 를 클릭 하 고 제거를 클릭 **합니다.**
4. 사용자 지정 시작 레이아웃 정책을 사용한 경우에는 [Surface Hub 시작 메뉴의 Microsoft Edge 표시](#display-microsoft-edge-in-the-surface-hub-start-menu)섹션에 설명 된 대로 최신 Edge 경로를 사용 하 여 수정 해야 합니다.
5. 이제 MicrosoftEdgeDevUninstaller kg을 프로 비전 할 수 있습니다.
6. **모든 앱**에서 Edge 개발자가 제거 되 면 먼저 "MicrosoftEdgeDevInstaller"를 제거한 다음 "MicrosoftEdgeDevUninstaller"을 제거 합니다.
7. 이는 Microsoft Edge 개발자를 제거 했습니다. 이제 표준 버전을 설치할 수 있습니다.

 
 
## Microsoft Edge 설치

### 배포 패키지를 사용 하 여 Microsoft Edge 설치

1. PC에서 USB 드라이브의 루트 폴더에 [Microsoft Edge 프로비저닝 패키지](https://aka.ms/HubEdge) (MicrosoftEdgeDevInstaller kg)를 다운로드 합니다.
2. Surface Hub에 USB 드라이브를 삽입 합니다.
3. Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.
4. **Surface Hub** > **장치 관리**로 이동합니다. **프로비저닝 패키지**에서 **프로비저닝 패키지 추가 또는 제거**를 선택합니다.
5. **패키지 추가**를 선택합니다.
6. Microsoft Edge 프로비저닝 패키지를 선택 하 고 **추가**를 선택 합니다.
7. 배포 패키지에 적용 되는 변경 내용에 대 한 요약이 표시 됩니다. **예, 추가**를 선택합니다.
8. Microsoft Edge 설치가 완료 될 때까지 기다립니다. 설치 되 면 Surface Hub 시작 메뉴로 이동 하 여 새 Microsoft Edge에 액세스 합니다.              

> [!NOTE]
> 사용 가능한 최신 버전의 Microsoft Edge가 있는 경우 자동으로 업데이트 됩니다.
 
### Intune을 사용 하 여 Microsoft Edge 설치
 
> [!NOTE]
> Surface Hub 디바이스는 Intune을 사용 하 여 등록 하 고 관리 해야 합니다. 자세한 내용은 [Microsoft Intune을 사용 하 여 Surface Hub 2S 관리](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)를 참조 하세요.
 

1. [Microsoft에서 Microsoft Edge 설치 관리자를 다운로드](https://www.microsoft.com/edge/business/download)합니다.
    - [안정적인 채널](https://docs.microsoft.com/deployedge/microsoft-edge-channels) 의 현재 버전 사용 **(버전 85)**
    - **Windows 64 비트** 선택
2. Microsoft [Edge 설치 관리자를 Microsoft Intune의 lob (기간 업무) 앱으로 추가](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)합니다.
    - Microsoft Edge 업데이트를 사용 하 여 Microsoft Edge에 대 한 자동 업데이트를 처리 하도록 선택 하는 경우 앱 **버전 무시** 설정을 **앱 정보** 창으로 구성 해야 합니다. 이 설정을 **Yes**로 전환 하면 Microsoft Intune에서 Surface Hub 장치에 설치 된 앱 버전을 적용 하지 않습니다.

 
### 모바일 장치 관리를 사용 하 여 Microsoft Edge 설치

1. [Microsoft에서 Microsoft Edge 설치 관리자를 다운로드](https://www.microsoft.com/edge/business/download)합니다.
    - [안정적인 채널](https://docs.microsoft.com/deployedge/microsoft-edge-channels) 의 현재 버전 사용 **(버전 85)**
    - **Windows 64 비트** 선택
2. 로컬 파일 공유 (\\server\share\MicrosoftEdgeEnterpriseX64.msi)와 같은 호스팅된 위치에서 Microsoft Edge 설치 관리자를 준비 합니다. Surface Hub 장치에는 호스팅된 위치에 액세스할 수 있는 권한이 있어야 합니다.
3. MDM 공급자를 통해 [EnterpriseDesktopAppManagement 구성 서비스 공급자 (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) 를 사용 하 여 Microsoft Edge를 설치 합니다.

 

## Microsoft Edge 구성

### Surface Hub에 대 한 기본 Microsoft Edge 정책
Surface Hub에 최적화 된 환경을 제공 하기 위해 Microsoft Edge는 다음 정책으로 구성 되어 있습니다.
 
> [!NOTE]
>  이러한 정책에 대 한 기본값을 유지 하는 것이 좋습니다.
 

| Microsoft Edge 정책                                                                                                    | 추천 환경                                                                                                                                                                                                                                               | 기본값 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Microsoft Edge 레거시에서 데이터 형식 및 설정을 자동으로 가져오지 않습니다. 이렇게 하면 Surface Hub의 공유 설정으로 로그인 한 사용자의 프로필을 변경 하지 않아도 됩니다.                                                                                                 | 4(tcp/ipv4)                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 마지막 브라우저 창이 닫힌 후에도 Microsoft Edge 프로세스가 백그라운드에서 계속 실행 되도록 하 여 세션 중에 웹 앱에 더욱 빠르게 액세스할 수 있도록 합니다.                                                                                                      | raid-1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 사용자가 Microsoft Edge에서 새 프로필을 만들 수 있도록 허용 하지 않습니다. 이렇게 하면 검색 및 로그인 환경이 단순해 집니다.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 한 명의 사용자만 Microsoft Edge에 로그인 할 수 있도록 합니다. 이렇게 하면 검색 및 로그인 환경이 단순해 집니다.                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 사용자가 Microsoft Edge에서 SSO (Single Sign-on)를 즐길 수 있도록 합니다. 사용자가 Surface Hub에 로그인 한 경우 해당 자격 증명을 다시 인증 하지 않아도 지원 되는 웹 사이트로 이동할 수 있습니다.  | raid-1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 관리자가 아닌 사용자가 Microsoft Edge에 새 확장을 설치 하지 못하도록 합니다. 기본적으로 설치할 확장 목록을 구성 하려면 [Extensioninstallforcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist)를 사용 합니다. | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 사용자가 처음으로 Microsoft Edge를 실행할 때 표시 되는 첫 번째 실행 환경 및 시작 화면을 숨깁니다. Surface Hub는 공유 장치 이므로 사용자 환경이 간단해 집니다.                                                                      | raid-1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | InPrivate 모드를 사용 하지 않도록 설정 합니다. 세션 종료는 이미 데이터 검색을 해제 하므로 탐색 및 로그인 환경이 간단해 집니다.                                                                                                                                          | raid-1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 새 탭 페이지에 Office 365 피드 환경을 표시 합니다. 사용자가 Surface Hub에 로그인 하면 Office 365에서 해당 파일 및 콘텐츠에 빠르게 액세스할 수 있습니다.                                                                                                        | raid-1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 사용자가 Surface Hub에 로그인 하면 조직 계정을 사용 하 여 비 이동식 프로필이 만들어집니다. 이렇게 하면 SSO (Single Sign-on) 환경이 단순해 집니다.                                                                                                 | raid-1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Microsoft Edge에서 인쇄를 사용 하지 않도록 설정 합니다. Surface Hub는 인쇄를 지원 하지 않습니다.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Microsoft Edge에서 Microsoft 서비스에 로그인 한 사용자를 사전 인증할 수 있도록 합니다. 이렇게 하면 SSO (Single Sign-on) 환경이 단순해 집니다.                                                                                                                         | raid-1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 파일을 저장할 위치를 사용자에 게 묻지 않고 파일을 다운로드 폴더에 자동으로 저장 합니다. 이렇게 하면 검색 환경이 단순해 집니다.                                                                                                                             | 0                 |

> [!IMPORTANT]
> 현재 PWAs (배포 가능한 프로그레시브 웹 앱)는 Windows 10 Team 운영 체제에서 지원 되지 않습니다.  또한 Surface Hub에서는 Microsoft Edge 정책 설정 [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) 이 지원 되지 않습니다. 

### Microsoft Edge 정책 설정 구성

Microsoft [edge 브라우저 정책을](https://docs.microsoft.com/deployedge/microsoft-edge-policies) 사용 하 여 microsoft edge에서 브라우저 설정을 구성 합니다. 이러한 정책은 다음을 사용 하 여 적용할 수 있습니다.

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Admx 수집을 지 원하는 기본 MDM (모바일 장치 관리) 공급자](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)
- [Windows 구성 디자이너에서 admx 수집을 사용 하 여 패키지를 프로 비전](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)합니다.

 
### Microsoft Edge 업데이트 구성

기본적으로 Microsoft Edge는 자동으로 업데이트 됩니다. Microsoft [edge 업데이트 정책을](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) 사용 하 여 Microsoft edge 업데이트에 대 한 설정을 구성 합니다.
Surface Hub는 다음 Microsoft Edge 업데이트 정책을 지원 하지 않는다는 점에 유의 하세요.

- **Allowsxs** – Surface Hub에서 Microsoft edge 안정화 채널은 항상 Microsoft edge 레거시를 대체 합니다.
- **Createdesktopshortcut 가기** – Surface Hub는 바탕 화면 바로 가기를 사용 하지 않습니다.

> [!NOTE]
>  Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다. [필요한 도메인 url](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 이 허용 목록에 추가 되었는지 확인 하 여 방화벽과 기타 보안 메커니즘을 통해 통신을 보장 합니다.
 
### Surface Hub 시작 메뉴에 Microsoft Edge 표시

기본 시작 메뉴 레이아웃을 사용 하는 경우 Microsoft Edge 프로비저닝 패키지를 사용 하 여 시작 메뉴를 설치 하 여 Microsoft Edge를 고정 된 앱으로 추가할 수 있습니다.
사용자 지정 된 시작 메뉴 레이아웃을 적용 하려는 경우 다음 XML을 사용 하 여 Microsoft Edge의 고정 된 타일을 추가 합니다.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

자세한 내용은 [Surface Hub 시작 메뉴 구성을](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)참조 하세요.
 
> [!NOTE]
> 새 Microsoft Edge에서는 SecondaryTiles을 사용 하 여 고정 된 웹 사이트 및 링크를 지원 하지 않습니다.

## 관련 링크

- [Microsoft Edge 설명서](https://docs.microsoft.com/microsoft-edge/).

