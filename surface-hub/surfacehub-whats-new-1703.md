---
title: Surface Hub에 대한 Windows 10 버전 1703의 새로운 기능
description: Windows 10 버전 1703(크리에이터스 업데이트)는 Microsoft Surface Hub에 새로운 기능을 제공합니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 01ee3530f7d9db9947d4be6395660170cfb30142
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448711"
---
# <a name="whats-new-in-windows-10-version-1703-for-microsoft-surface-hub"></a>Microsoft Surface Hub에 대한 Windows 10 버전 1703의 새로운 기능은 무엇인가요?

Surface Hub 엔지니어 Jordan Marchese가 소개하는 Microsoft Surface Hub의 현재 Windows 10 버전 1703(크리에이터스 업데이트)를 시청하세요. 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

Windows 10, 버전 1703(크리에이터스 업데이트라고도 함)은 Microsoft Surface Hub에 다음과 같은 변경 내용을 도입하였습니다.

## <a name="new-settings"></a>새로운 설정

MDM(모바일 디바이스 관리) 및 CSP(구성 서비스 공급자)에 설정이 추가되어 Surface Hub 관리 기능을 확장하였습니다. [새 설정에 추가된 내용](manage-settings-with-mdm-for-surface-hub.md):

- InBoxApps/SkypeForBusiness/DomainName
- InBoxApps/Connect/AutoLaunch
- Properties/DefaultVolume
- Properties/ScreenTimeout
- Properties/SessionTimeout
- Properties/SleepTimeout
- Properties/AllowSessionResume
- Properties/AllowAutoProxyAuth
- Properties/DisableSigninSuggestions
- Properties/DoNotShowMyMeetingsAndFiles
- System/AllowStorageCard

추가 설정은 새 [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) 및 [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp)를 기반으로 합니다.
</br>

## <a name="provisioning-wizard"></a>프로비전 마법사

사용하기 쉬운 마법사로 여러 Surface Hub 디바이스에 적용할 수 있는 프로비저닝 패키지를 신속하게 만들 수 있으며 Azure Active Directory에 대한 대량 가입이 포함됩니다. [Surface Hub 프로비저닝 패키지를 만드는 방법을 알아보세요.](provisioning-packages-for-certificates-surface-hub.md)

![디바이스 프로비전 Surface Hub 단계](images/wcd-wizard.png)
    
## <a name="miracast-on-your-existing-wireless-network-or-lan"></a>기존 무선 네트워크 또는 LAN의 Miracast 

Microsoft는 직접 무선 링크가 아니라 [로컬 네트워크를 통해 Miracast 스트림을 보낼 수 있는](miracast-over-infrastructure.md) 기능을 확장했습니다. 
    
## <a name="end-session"></a>세션 종료

**완료**가 이제 **세션 종료**로 변경되었습니다. [세션 종료를 사용하는 방법을 알아보세요.](finishing-your-surface-hub-meeting.md) 

![세션 종료.](images/end-session.png)



 

 
