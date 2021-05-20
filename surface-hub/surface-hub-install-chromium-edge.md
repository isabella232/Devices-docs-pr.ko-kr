---
title: Surface Hub에 새 Microsoft Edge 설치 및 구성
description: 새 응용 프로그램을 설치하고 Microsoft Edge 구성할 Surface Hub.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576728"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>Surface Hub에 새 Microsoft Edge 설치 및 구성

Windows 10 Team 2020 업데이트는 Microsoft Edge 2S 및 Surface Hub(v1)에 대한 권장 브라우저로 Chromium(버전 8 Surface Hub 5 이상)를 기반으로 하는 새로운 Surface Hub 지원됩니다. 이 문서에서는 프로비저닝 패키지, Microsoft Intune 또는 타사 MDM(모바일 장치 관리) 공급자 중 하나를 사용하여 브라우저를 설치하는 방법을 설명합니다.

> [!IMPORTANT]
> 기본적으로 Surface Hub 디바이스는 Microsoft Edge 레거시(버전 44)로 사전 설치됩니다. After installing the [2020 Update](surface-hub-2020-update.md), it's recommended to switch to the new Microsoft Edge browser; 2021년 [3월](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) 9일에는 Microsoft Edge 레거시 지원이 종료될 예정입니다.

> [!NOTE]
> 전체 화면 모드를 종료하기 위해 화면의 위쪽에서 아래로 위로 위로 스와이프하려면 새 화면이 있는 두 손가락이 Microsoft Edge. 전체 화면 종료 작업은 길게 누르기 터치 후 표시되는 상황에 맞는 메뉴에서도 사용할 수 있습니다.


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>프로비저닝 Microsoft Edge 사용하여 설치

1. PC에서 USB [드라이브의 루트](https://aka.ms/HubEdge) 폴더에 Microsoft Edge 프로비저닝 패키지(MicrosoftEdgeInstaller.ppkg)를 다운로드합니다.
2. USB 드라이브를 연결에 Surface Hub.
3. 다음 Surface Hub **열고** 설정 관리자 자격 증명을 입력합니다.
4. **Surface Hub** > **장치 관리**로 이동합니다. **프로비저닝 패키지**에서 **프로비저닝 패키지 추가 또는 제거**를 선택합니다.
5. **패키지 추가**를 선택합니다.
6. 프로비저닝 Microsoft Edge 선택하고 추가 를 **선택합니다.**
7. 프로비저닝 패키지가 적용되는 변경 내용을 요약하여 볼 수 있습니다. **예, 추가**를 선택합니다.
8. 설치가 Microsoft Edge 때까지 기다렸다가 설치되면 시작 메뉴로 Surface Hub 메뉴로 이동하여 새 Microsoft Edge.              

> [!NOTE]
> 사용할 수 있는 최신 버전의 Microsoft Edge 자동으로 업데이트됩니다.
 
## <a name="install-microsoft-edge-using-intune"></a>Intune을 Microsoft Edge 설치
 
> [!NOTE]
> 이 설치 방법을 사용하려면 Surface Hub 장치를 등록하고 Intune을 사용하여 관리해야 합니다. 자세한 내용은 [MDM을 사용하여 Surface Hub 2S 관리를 참조하세요.](manage-settings-with-mdm-for-surface-hub.md)
 

1. [설치 Microsoft Edge 다운로드합니다.](https://www.microsoft.com/edge/business/download)
    - 안정 채널에서 현재 버전 [](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **사용(버전 85)**
    - **64비트** Windows 선택
2. 에 Microsoft Edge 설치 관리자를 업무용 [앱으로 Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - 앱에 대한 자동 Microsoft Edge 업데이트 처리하기로 선택한 Microsoft Edge 앱 버전 무시 설정 **** 앱 정보 창을 **구성해야** 합니다. 이 설정을 **예로**전환하면 Microsoft Intune 장치에 설치된 앱 버전이 Surface Hub 않습니다.

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>타사 Microsoft Edge 사용하여 설치

1. [Microsoft에서 Microsoft Edge 설치 관리자를 다운로드합니다.](https://www.microsoft.com/edge/business/download)
    - 안정 채널에서 현재 버전 [](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **사용(버전 85)**
    - **64비트** Windows 선택
2. 로컬 Microsoft Edge 공유(예: 로컬 파일 공유)에 설치 관리자를 \\server\share\MicrosoftEdgeEnterpriseX64.msi. 장치 Surface Hub 호스트된 위치에 액세스할 수 있는 권한이 있어야 합니다.
3. MDM 공급자를 통해 [EnterpriseDesktopAppManagement CSP(구성](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) 서비스 공급자)를 사용하여 Microsoft Edge.

## <a name="configure-microsoft-edge"></a>Microsoft Edge 구성

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>Microsoft Edge 대한 기본 Surface Hub

Microsoft Edge 최적화된 환경을 제공하기 위해 다음 정책 설정으로 미리 Surface Hub.
 
> [!TIP]
> 이러한 정책 설정의 기본값을 유지하는 것이 좋습니다.
 

| 정책 설정                                                                                                   | 권장 환경                                                                                                                                                                                                                                               | 기본값 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 데이터타입 및 설정을 데이터 스타일에서 자동으로 가져오지 Microsoft Edge 레거시. 이렇게 하여 로그인한 사용자의 프로필을 공유 설정으로 변경하지 Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 마지막 Microsoft Edge 창을 닫은 후에도 앱 프로세스가 백그라운드에서 계속 실행되어 세션 중에 웹앱에 더 빠르게 액세스할 수 있도록 합니다.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 사용자가 새 프로필을 만들 수 있도록 허용하지 Microsoft Edge. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 한 사용자만 로그인할 수 Microsoft Edge. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 사용자가 단일 SSO(Single Sign-On)를 Microsoft Edge. 사용자가 로그인한 Surface Hub 자격 증명은 다시 인증하지 않고도 지원되는 웹 사이트로 흐를 수 있습니다.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 관리자가 아닌 사용자가 새 확장을 설치하지 못하도록 Microsoft Edge. 기본적으로 설치할 확장 목록을 구성하기 위해 [ExtensionInstallForcelist 를 사용하세요.](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 사용자가 처음 실행 환경을 실행할 때 일반적으로 표시되는 첫 번째 실행 환경과 시작 화면을 Microsoft Edge 숨겨야 합니다. 공유 Surface Hub 장치이기 때문에 사용자 환경이 간소화됩니다.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | InPrivate 모드를 사용하지 않도록 설정합니다. 세션 종료는 이미 검색 데이터를 지우기 때문에 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 새 탭 Office 365 피드 환경을 보여줍니다. 사용자가 로그인되어 Surface Hub 파일 및 콘텐츠에 빠르게 액세스할 수 Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 사용자가 조직에 로그인하면 Surface Hub 계정을 사용하여 이동식이 아닌 프로필이 만들어집니다. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 인쇄할 수 Microsoft Edge. Surface Hub 인쇄를 지원하지 않습니다.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 사용자가 Microsoft Edge 로그인한 사용자를 사전 인증할 수 있도록 Microsoft 서비스. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 사용자에게 파일을 저장할 위치를 묻지 않고 파일을 다운로드 폴더에 자동으로 저장합니다. 이렇게 하면 검색 환경이 간소화됩니다.                                                                                                                             | 0                 |

> [!IMPORTANT]
> 배포 가능한 PW(점진적 웹앱)는 현재 배포 가능한 운영 체제에서 Windows 10 Team 않습니다.  또한 웹 응용 Microsoft Edge 정책 설정 [WebAppInstallForceList가](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) 지원되지 Surface Hub. 

### <a name="configure-microsoft-edge-policy-settings"></a>정책 Microsoft Edge 구성

브라우저 [Microsoft Edge 정책을 사용하여](https://docs.microsoft.com/deployedge/microsoft-edge-policies) 브라우저 설정 구성을 Microsoft Edge. 이러한 정책은 다음을 사용하여 적용할 수 있습니다.

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).
- [ADMX Ingestion을 지원하는 선호하는 MDM(모바일](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)장치 관리) 공급자 또는
- [구성 디자이너에서 ADMX ingestion을 Windows 프로비저닝합니다.](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### <a name="configure-microsoft-edge-updates"></a>업데이트 Microsoft Edge 구성

기본적으로 Microsoft Edge 자동으로 업데이트됩니다. 업데이트 [Microsoft Edge 사용하여](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) 업데이트 정책에 대한 설정을 Microsoft Edge 업데이트.
이 Surface Hub 업데이트 정책을 지원하지 Microsoft Edge 않습니다.

- **Allowsxs** – Surface Hub Microsoft Edge 안정 채널이 항상 Microsoft Edge 레거시.
- **CreateDesktopShortcut** – Surface Hub 바로 가기를 사용하지 않습니다.

> [!TIP]
>  Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다. 방화벽 및 기타 보안 메커니즘을 통한 통신을 보장하기 위해 필요한 도메인 [URL을](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 허용 목록에 추가해야 합니다.

## <a name="related-links"></a>관련 링크

- [Microsoft Edge 설명서](https://docs.microsoft.com/microsoft-edge/)

