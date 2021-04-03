---
title: Windows 10 Team 2020 업데이트 설치
description: Surface Hub 운영 체제 Windows 10 Team 2020 업데이트의 최신 업데이트를 다운로드합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470416"
---
# <a name="install-windows-10-team-2020-update"></a>Windows 10 Team 2020 업데이트 설치 

Windows 10 버전 20H2를 기반으로 하는 새로운 Surface Hub 운영 체제인 **Windows 10 Team 2020 Update를**이제 Surface Hub 2S 및 원래 Surface Hub(v1)에서 사용할 수 있습니다. 

- 참조: [알려진 문제: Windows 10 Team 2020 업데이트](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>배포

다음 방법 중 하나를 사용하여 Windows 2020 Update를 얻을 수 있습니다.

- **비즈니스용 Windows 업데이트**.
- **BMR(Bare metal recovery) 이미지**. 장치를 Azure Active Directory에 가입하거나 장치가 인터넷에서 업데이트를 수신하도록 허용하지 않는 고객에게 권장되는 옵션입니다. 시작하려면 [Surface에 대한 복구 이미지 다운로드를 참조합니다.](https://support.microsoft.com/surfacerecoveryimage)
- **Windows 업데이트.** 가용성은 다음 표에 설명된 지역/국가에 따라 다릅니다.

| 단계 | 국가/지역                         | 시작          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, 오스트레일리아, 캐나다, 벨기에, 멕시코 | 2020년 10월  |
| 2     | 영국, 일본, 스위스, 이탈리아          | 2020년 11월 |
| 3     | 독일, 네덜란드                   | 2021년 2월 말 |
| 4     | Global                                 | 2021년 3월 초 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Windows 10 Team Edition 버전 1703으로 Surface Hub 서비스 

[Windows 10 Team Edition 버전 1703에](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) 대한 전체 서비스 지원은 2021년 3월 16일까지 계속될 예정입니다.

### <a name="2s-devices"></a>2S 장치 

모든 지역의 고객은 Surface Hub 2S의 초기화 및 복구에 설명된 Windows 업데이트, 비즈니스용 Windows 업데이트를 통해 또는 BMR(메탈 복구) 이미지를 사용하여 Surface [Hub 2S 장치를 2020](surface-hub-2s-recover-reset.md)업데이트로 업데이트할 수 있습니다.

### <a name="v1-devices"></a>V1 장치 

모든 지역의 고객은 Windows 업데이트, 비즈니스용 Windows 업데이트 또는 Surface Hub 복구 도구를 사용하여 Surface Hub v1 장치를 2020 업데이트로 업데이트할 [수 있습니다.](surface-hub-recovery-tool.md) 대기 업데이트를 수신하려면 KB5000749를 설치해야 합니다. 자세한 내용은 [Surface IT Pro 블로그를 참조하세요.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371)
 
## <a name="whats-new"></a>새로운 What's new

Windows 10 Team 2020 Update는 최신 Windows 10 기능과 함께 장치 배포 및 관리성을 대대적으로 개선합니다. 자세한 내용은 [Windows 10 Team 2020 Update의 새로운 내용을 참조합니다.](surface-hub-2020-update-whats-new.md)
 
## <a name="before-you-begin"></a>시작하기 전에

Windows 10 Team 2020 업데이트를 설치하기 전에 장치와 연결된 BitLocker 키를 저장해야 합니다. 

**BitLocker 키를 수동으로 저장하려면**

1. Surface Hub에 USB 드라이브를 삽입합니다.
2. Surface Hub에서 설정을 **열고** 메시지가 표시될 때 관리자 자격 증명을 입력합니다.
3. Update & Security Recovery **로**  >  **이동합니다.**
4. **BitLocker에서**저장을 **선택합니다.** BitLocker 키는 USB 드라이브의 텍스트 파일에 저장됩니다.

자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md)

## <a name="learn-more"></a>자세히 알아보기

- [Windows 10 Team 2020 업데이트의 새로운 기능](surface-hub-2020-update-whats-new.md)
- [Windows 10 Team 출시 업데이트](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
