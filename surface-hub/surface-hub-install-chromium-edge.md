---
title: Surface Hub에 새 Microsoft Edge 설치 및 구성
description: Surface Hub에서 새 Microsoft Edge를 설치하고 구성합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/08/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 74ae47e80447f89753110c52a49daf649478dd50
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319172"
---
# Surface Hub에 새 Microsoft Edge 설치 및 구성

Windows 10 Team 2020 업데이트는 Surface Hub 2S 및 Surface Hub(v1)에 권장되는 브라우저로 Chromium(버전 85 이상)을 기반으로 하는 새로운 Microsoft Edge를 지원합니다. 이 문서에서는 프로비저닝 패키지, Microsoft Intune 또는 타사 MDM(모바일 장치 관리) 공급자의 세 가지 방법 중 하나를 사용하여 브라우저를 설치하는 방법을 설명합니다.

> [!IMPORTANT]
> 기본적으로 Surface Hub 장치는 Microsoft Edge 레거시(버전 44)로 사전 설치됩니다. [2020 업데이트를](surface-hub-2020-update.md)설치한 후 새 Microsoft Edge 브라우저로 전환하는 것이 좋습니다. [레거시 Microsoft Edge에](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) 대한 지원은 2021년 3월 9일로 종료됩니다.

## 프로비저닝 패키지를 사용하여 Microsoft Edge 설치

1. PC에서 Microsoft Edge 프로비저닝 패키지(MicrosoftEdgeInstaller.ppkg)를 USB 드라이브의 루트 폴더에 다운로드합니다. [](https://aka.ms/HubEdge)
2. Usb 드라이브를 Surface Hub에 삽입합니다.
3. Surface Hub에서 설정을 **열고** 메시지가 표시될 때 관리자 자격 증명을 입력합니다.
4. **Surface Hub** > **장치 관리**로 이동합니다. **프로비저닝 패키지**에서 **프로비저닝 패키지 추가 또는 제거**를 선택합니다.
5. **패키지 추가**를 선택합니다.
6. Microsoft Edge 프로비저닝 패키지를 선택하고 추가를 **선택합니다.**
7. 프로비저닝 패키지가 적용되는 변경 내용을 요약하여 볼 수 있습니다. **예, 추가**를 선택합니다.
8. Microsoft Edge 설치가 완료될 때까지 기다릴 수 있습니다. 설치되면 Surface Hub 시작 메뉴로 이동하여 새 Microsoft Edge에 액세스합니다.              

> [!NOTE]
> 사용 가능한 최신 버전의 Microsoft Edge가 있는 경우 자동으로 업데이트됩니다.
 
## Intune을 사용하여 Microsoft Edge 설치
 
> [!NOTE]
> Surface Hub 디바이스는 Intune을 사용하여 등록하고 관리해야 합니다. 자세한 내용은 [Microsoft Intune을 사용하여 Surface Hub 2S 관리를 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [Microsoft Edge 설치 관리자를 다운로드합니다.](https://www.microsoft.com/edge/business/download)
    - 안정 채널에서 현재 버전 [](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **사용(버전 85)**
    - **Windows 64비트 선택**
2. [Microsoft Intune에 Microsoft Edge](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)설치 관리자를 업무 앱으로 추가합니다.
    - Microsoft Edge 업데이트를 사용하여 Microsoft Edge에 대한 자동 업데이트를 처리하도록 선택한 경우 앱 정보 창을 무시 앱 버전 **설정을** **구성해야** 합니다. 이 설정을 **예로**전환하면 Microsoft Intune이 Surface Hub 장치에 설치된 앱 버전을 적용하지 않습니다.

## 타사 MDM 공급자를 사용하여 Microsoft Edge 설치

1. [Microsoft에서 Microsoft Edge 설치 관리자를 다운로드합니다.](https://www.microsoft.com/edge/business/download)
    - 안정 채널에서 현재 버전 [](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **사용(버전 85)**
    - **Windows 64비트 선택**
2. 로컬 파일 공유(예: 로컬 파일 공유)에 Microsoft Edge 설치 관리자를 \\server\share\MicrosoftEdgeEnterpriseX64.msi. Surface Hub 장치에 호스트된 위치에 액세스할 수 있는 권한이 있어야 합니다.
3. MDM [공급자를 통해 EnterpriseDesktopAppManagement CSP(구성](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) 서비스 공급자)를 사용하여 Microsoft Edge를 설치합니다.

## Microsoft Edge 구성

### Surface Hub에 대한 기본 Microsoft Edge 정책

Microsoft Edge는 Surface Hub에 최적화된 환경을 제공하기 위해 다음과 같은 정책 설정으로 미리 구성됩니다.
 
> [!TIP]
> 이러한 정책 설정의 기본값을 유지하는 것이 좋습니다.
 

| 정책 설정                                                                                                   | 권장 환경                                                                                                                                                                                                                                               | 기본값 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Microsoft Edge 레거시에서 데이터타입 및 설정을 자동으로 가져오지 않습니다. 이렇게 하여 Surface Hub의 공유 설정으로 로그인한 사용자의 프로필을 변경하지 않습니다.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 마지막 브라우저 창이 닫힌 후에도 Microsoft Edge 프로세스가 백그라운드에서 계속 실행되어 세션 중에 웹앱에 더 빠르게 액세스할 수 있도록 합니다.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 사용자가 Microsoft Edge에서 새 프로필을 만들 수 있도록 허용하지 않습니다. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 한 사용자만 Microsoft Edge에 로그인할 수 있습니다. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 사용자가 Microsoft Edge에서 SSO(Single Sign-On)를 사용할 수 있습니다. 사용자가 Surface Hub에 로그인하면 자격 증명이 다시 인증되지 않고도 지원되는 웹 사이트로 흐를 수 있습니다.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 관리자가 아닌 사용자가 Microsoft Edge에 새 확장을 설치할 수 없습니다. 기본적으로 설치할 확장 목록을 구성하기 위해 [ExtensionInstallForcelist를 사용하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 사용자가 처음으로 Microsoft Edge를 실행할 때 일반적으로 표시되는 첫 실행 환경 및 시작 화면을 숨길 수 있습니다. Surface Hub는 공유 장치이기 때문에 사용자 환경이 간소화됩니다.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | InPrivate 모드를 사용하지 않도록 설정합니다. 세션 종료는 이미 검색 데이터를 지우기 때문에 검색 및 로그인 환경을 간소화합니다.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 새 탭 페이지에 Office 365 피드 환경을 보여줍니다. 사용자가 Surface Hub에 로그인하면 Office 365에서 파일 및 콘텐츠에 빠르게 액세스할 수 있습니다.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 사용자가 Surface Hub에 로그인하면 이동식이 아닌 프로필이 조직 계정을 사용하여 만들어집니다. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Microsoft Edge에서 인쇄를 사용하지 않습니다. Surface Hub는 인쇄를 지원하지 않습니다.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Microsoft Edge에서 Microsoft 서비스를 사용하여 로그인한 사용자를 사전 인증할 수 있도록 합니다. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 파일을 저장할 위치를 묻는 대신 파일을 다운로드 폴더에 자동으로 저장합니다. 이렇게 하면 검색 환경이 간소화됩니다.                                                                                                                             | 0                 |

> [!IMPORTANT]
> 배포 가능한 PW(점진적 웹앱)는 현재 Windows 10 Team 운영 체제에서 지원되지 않습니다.  또한 Microsoft Edge 정책 설정 [WebAppInstallForceList는](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) Surface Hub에서 지원되지 않습니다. 

### Microsoft Edge 정책 설정 구성

[Microsoft Edge 브라우저 정책을 사용하여](https://docs.microsoft.com/deployedge/microsoft-edge-policies) Microsoft Edge에서 브라우저 설정을 구성합니다. 이러한 정책은 다음을 사용하여 적용할 수 있습니다.

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- ADMX 정보 유무를 지원하는 [선호하는 MDM(모바일](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)장치 관리) 공급자 또는
- [Windows 구성 디자이너에서 ADMX Ingestion을 사용하여 패키지 프로비저닝](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Microsoft Edge 업데이트 구성

기본적으로 Microsoft Edge는 자동으로 업데이트됩니다. [Microsoft Edge 업데이트 정책을 사용하여](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) Microsoft Edge 업데이트에 대한 설정을 구성합니다.
Surface Hub는 다음 Microsoft Edge 업데이트 정책을 지원하지 않습니다.

- **Allowsxs** – Surface Hub에서 Microsoft Edge 안정 채널은 항상 Microsoft Edge 레거시를 대체합니다.
- **CreateDesktopShortcut** – Surface Hub는 데스크톱 바로 가기를 사용하지 않습니다.

> [!NOTE]
>  Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다. 방화벽 및 기타 보안 메커니즘을 통한 통신을 보장하기 위해 필요한 도메인 [URL을](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 허용 목록에 추가해야 합니다.
 
### Surface Hub 시작 메뉴에 Microsoft Edge 표시

기본 시작 메뉴 레이아웃을 사용하는 경우 Microsoft Edge 프로비저닝 패키지가 있는 시작 메뉴를 설치하여 Microsoft Edge를 고정된 앱으로 추가할 수 있습니다.
사용자 지정된 시작 메뉴 레이아웃을 적용하려는 경우 다음 XML을 사용하여 Microsoft Edge에 고정된 타일을 추가합니다.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

자세한 내용은 Surface Hub 시작 [메뉴를 참조하세요.](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)
 
> [!NOTE]
> 새 Microsoft Edge는 고정된 웹 사이트를 지원하지 않습니다.

## 관련 링크

- [Microsoft Edge 설명서.](https://docs.microsoft.com/microsoft-edge/)

