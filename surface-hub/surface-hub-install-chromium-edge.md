---
title: Surface Hub에서 Microsoft Edge 관리
description: 이 문서에서는 브라우저 설정을 구성하는 기본 Microsoft Edge 정책 설정 및 도구에 대해 설명합니다.
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
ms.openlocfilehash: b652b990ce798d807ff2a27e87d212d01f3c23a2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497731"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Surface Hub에서 Microsoft Edge 관리

[Microsoft Edge 브라우저 정책을](/deployedge/microsoft-edge-policies) 사용하여 다음 방법 중 어떤 방법을 통해 Microsoft Edge 브라우저 설정을 구성합니다.

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [ADMX 수집을 지원하는 선호하는 MDM(모바일 장치 관리) 공급자](/deployedge/configure-edge-with-mdm)
- [Windows 구성 디자이너에서 ADMX 수집을 사용하여 패키지 프로비전](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> 화면 위쪽에서 아래로 살짝 밀어 전체 화면 모드를 종료하려면 새 Microsoft Edge 두 손가락이 필요합니다. 종료 전체 화면 작업은 길게 누른 후 표시되는 상황에 맞는 메뉴에서도 사용할 수 있습니다.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Surface Hub 대한 기본 Microsoft Edge 정책

Microsoft Edge Surface Hub 최적화된 환경을 제공하기 위해 다음 정책 설정으로 미리 구성됩니다.


> [!TIP]
> 이러한 정책 설정의 기본값을 유지하는 것이 좋습니다.

| 정책 설정                                                                                                   | 권장 환경                                                                                                                                                                                                                                               | 기본값 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Microsoft Edge 레거시 데이터 형식 및 설정을 자동으로 가져오지 마세요. 이렇게 하면 Surface Hub 공유 설정을 사용하여 로그인한 사용자의 프로필을 변경할 수 없습니다.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Microsoft Edge 프로세스가 마지막 브라우저 창을 닫은 후에도 백그라운드에서 계속 실행되도록 허용하여 세션 중에 웹앱에 더 빠르게 액세스할 수 있습니다.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 사용자가 Microsoft Edge 새 프로필을 만들 수 없습니다. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 한 명의 사용자만 Microsoft Edge 로그인할 수 있습니다. 이렇게 하면 검색 및 로그인 환경이 간소화됩니다.                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | 사용자가 Microsoft Edge SSO(Single Sign-On)를 즐길 수 있습니다. 사용자가 Surface Hub 로그인하면 자격 증명이 다시 인증할 필요 없이 지원되는 웹 사이트로 흐를 수 있습니다.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 관리자가 아닌 사용자가 Microsoft Edge 새 확장을 설치하지 못하도록 합니다. 기본적으로 설치할 확장 목록을 구성하려면 [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)를 사용합니다. | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 사용자가 처음으로 Microsoft Edge 실행할 때 일반적으로 표시되는 첫 번째 실행 환경 및 시작 화면을 숨깁니다. Surface Hub 공유 디바이스이므로 사용자 환경이 간소화됩니다.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | InPrivate 모드를 사용하지 않도록 설정합니다. 세션 종료는 이미 검색 데이터를 지우기 때문에 검색 및 로그인 환경을 간소화합니다.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 새 탭 페이지의 Office 365 피드 환경을 표시합니다. 사용자가 Surface Hub 로그인하면 Office 365 파일 및 콘텐츠에 빠르게 액세스할 수 있습니다.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 사용자가 Surface Hub 로그인하면 조직 계정을 사용하여 이동식이 아닌 프로필이 만들어집니다. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Microsoft Edge 인쇄를 사용하지 않도록 설정합니다. Surface Hub 인쇄를 지원하지 않습니다.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Microsoft Edge Microsoft 서비스 로그인한 사용자를 사전에 인증할 수 있습니다. 이렇게 하면 SSO(Single Sign-On) 환경이 간소화됩니다.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 사용자에게 파일을 저장할 위치를 묻는 대신 다운로드 폴더에 파일을 자동으로 저장합니다. 이렇게 하면 검색 환경이 간소화됩니다.                                                                                                                             | 0                 |

> [!TIP]
> 배포 가능한 PWA(프로그레시브 웹앱)는 이제 Windows 10 Team 운영 체제에서 지원됩니다. 자세한 내용은 [Surface Hub 프로그레시브 Web Apps 설치를](install-pwa-surface-hub.md) 참조하세요. 

### <a name="configure-microsoft-edge-updates"></a>Microsoft Edge 업데이트 구성

기본적으로 Microsoft Edge 자동으로 업데이트됩니다. [Microsoft Edge 업데이트 정책을](/deployedge/microsoft-edge-update-policies) 사용하여 Microsoft Edge 업데이트 대한 설정을 구성합니다. Surface Hub 바탕 화면 바로 가기를 사용하지 않으므로 Surface Hub **CreateDesktopShortcut** 정책 설정을 지원하지 않습니다.

> [!TIP]
> Microsoft Edge 기능을 지원하려면 인터넷에 연결되어 있어야 합니다. 방화벽 및 기타 보안 메커니즘을 통한 통신을 보장하기 위해 [필요한 도메인 URL](/deployedge/microsoft-edge-security-endpoints) 을 허용 목록에 추가합니다.

## <a name="related-links"></a>관련 링크

- [Microsoft Edge 설명서](/microsoft-edge/)