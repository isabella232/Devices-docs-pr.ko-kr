---
title: 사용자 Microsoft Edge 관리 Surface Hub
description: 이 문서에서는 브라우저 설정을 Microsoft Edge 기본 정책 설정 및 도구에 대해 설명합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 80e861fd575324db21be458f7b82cd5fdb538b50
ms.sourcegitcommit: 68b6e86919d6e29155bf9386d05279866e1157e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "12100716"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>사용자 Microsoft Edge 관리 Surface Hub

브라우저 [Microsoft Edge 사용하여](/deployedge/microsoft-edge-policies) 다음 방법을 Microsoft Edge 브라우저 설정을 구성합니다.

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [ADMX Ingestion을 지원하는 선호하는 MDM(모바일 장치 관리) 공급자](/deployedge/configure-edge-with-mdm)
- [ADMX 구성 디자이너에서 ADMX Windows 프로비저닝](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> 전체 화면 모드를 종료하기 위해 화면의 위쪽에서 아래로 위로 위로 스와이프하려면 새 화면이 있는 두 손가락이 Microsoft Edge. 전체 화면 종료 작업은 길게 누르기 터치 후 표시되는 상황에 맞는 메뉴에서도 사용할 수 있습니다.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Microsoft Edge 대한 기본 Surface Hub

Microsoft Edge 최적화된 환경을 제공하기 위해 다음 정책 설정으로 미리 Surface Hub.


> [!TIP]
> 이러한 정책 설정의 기본값을 유지하는 것이 좋습니다.

| 정책 설정                                                                                                   | 권장 환경                                                                                                                                                                                                                                               | 기본값 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 데이터타입 및 설정을 데이터 스타일에서 자동으로 가져오지 Microsoft Edge 레거시. 이렇게 하여 로그인한 사용자의 프로필을 공유 설정으로 변경하지 Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 마지막 Microsoft Edge 창을 닫은 후에도 앱 프로세스가 백그라운드에서 계속 실행되어 세션 중에 웹앱에 더 빠르게 액세스할 수 있도록 합니다.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 사용자가 새 프로필을 만들 수 있도록 허용하지 Microsoft Edge. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 한 사용자만 로그인할 수 Microsoft Edge. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | 사용자가 단일 SSO(Single Sign-On)를 Microsoft Edge. 사용자가 로그인한 Surface Hub 자격 증명은 다시 인증하지 않고도 지원되는 웹 사이트로 흐를 수 있습니다.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 관리자가 아닌 사용자가 새 확장을 설치하지 못하도록 Microsoft Edge. 기본적으로 설치할 확장 목록을 구성하기 위해 [ExtensionInstallForcelist 를 사용하세요.](/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 사용자가 처음 실행 환경을 실행할 때 일반적으로 표시되는 첫 번째 실행 환경과 시작 화면을 Microsoft Edge 숨겨야 합니다. 공유 Surface Hub 장치이기 때문에 사용자 환경이 간소화됩니다.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | InPrivate 모드를 사용하지 않도록 설정합니다. 세션 종료는 이미 검색 데이터를 지우기 때문에 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 새 탭 Office 365 피드 환경을 보여줍니다. 사용자가 로그인되어 Surface Hub 파일 및 콘텐츠에 빠르게 액세스할 수 Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 사용자가 조직에 로그인하면 Surface Hub 계정을 사용하여 이동식이 아닌 프로필이 만들어집니다. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | 인쇄할 수 Microsoft Edge. Surface Hub 인쇄를 지원하지 않습니다.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 사용자가 Microsoft Edge 로그인한 사용자를 사전 인증할 수 있도록 Microsoft 서비스. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 사용자에게 파일을 저장할 위치를 묻지 않고 파일을 다운로드 폴더에 자동으로 저장합니다. 이렇게 하면 검색 환경이 간소화됩니다.                                                                                                                             | 0                 |

> [!IMPORTANT]
> 배포 가능한 PW(점진적 웹앱)는 현재 배포 가능한 운영 체제에서 Windows 10 Team 않습니다.  또한 웹 응용 Microsoft Edge 정책 설정 [WebAppInstallForceList가](/deployedge/microsoft-edge-policies#webappinstallforcelist) 지원되지 Surface Hub.

### <a name="configure-microsoft-edge-updates"></a>업데이트 Microsoft Edge 구성

기본적으로 Microsoft Edge 자동으로 업데이트됩니다. 업데이트 [Microsoft Edge 사용하여](/deployedge/microsoft-edge-update-policies) 업데이트 정책에 대한 설정을 Microsoft Edge 업데이트. 이 Surface Hub 데스크톱 바로 가기를 사용하지 않는 경우 **CreateDesktopShortcut** 정책 Surface Hub 지원하지 않습니다.

> [!TIP]
> Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다. 방화벽 [및](/deployedge/microsoft-edge-security-endpoints) 기타 보안 메커니즘을 통한 통신을 보장하기 위해 필요한 도메인 URL을 허용 목록에 추가합니다.

## <a name="related-links"></a>관련 링크

- [Microsoft Edge 설명서](/microsoft-edge/)