---
title: Intune을 사용하여 Surface Hub 2S에 앱 배포
description: Intune을 사용 하 여 앱을 Surface Hub 2S에 배포 하는 방법에 대해 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835687"
---
# Intune을 사용하여 Surface Hub 2S에 앱 배포

팀 또는 조직의 요구에 맞게 추가 앱을 설치할 수 있습니다.

## 개발자 지침

- Surface Hub에서는 [UWP(유니버설 Windows 플랫폼) 앱](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)만 실행합니다. [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter)를 사용하여 만든 앱은 Surface Hub에서 실행되지 않습니다.
- 앱은 [유니버설 장치 패밀리](https://msdn.microsoft.com/library/windows/apps/dn894631) 또는 Windows Team 장치 패밀리를 대상으로 해야 합니다.
- Surface Hub [는 비즈니스용 Microsoft Store](https://businessstore.microsoft.com/store)의 [오프 라인 라이선스가 있는 앱](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 만 지원 합니다.
- 기본적으로 앱은 설치할 스토어 서명되어야 합니다. 테스트 및 개발 중에 디바이스를 개발자 모드로 전환하여 개발자 서명된 UWP 앱을 실행할 수도 있습니다.
- Microsoft Store에서 앱을 개발 하 고 제출할 때 디바이스 패밀리 가용성 및 조직 라이선스 옵션을 설정 하 여 Surface Hub에서 앱을 실행할 수 있는지 확인 합니다.
- Surface Hub에 앱을 설치 하려면 관리자 자격 증명이 필요 합니다. 회의실 및 다른 공유 공간에 사용 하도록 설계 된 Surface Hub는 일반 사용자가 앱을 다운로드 하 고 설치 하기 위해 Microsoft Store에 액세스할 수 없도록 합니다.

## 배포 지침

Intune을 사용 하 여 UWP (유니버설 Windows 플랫폼) 앱을 Surface Hub 2S에 배포 하 고 장치에 대 한 앱 배포 속도를 지정할 수 있습니다.

1. 앱을 배포 하려면 조직에 MDM을 사용 하도록 설정 합니다. Intune 포털에서 MDM 기관으로 **Intune** (권장)을 선택 합니다. <br>

    ![MDM 기관 선택](images/sh2-set-intune5.png)

2. Intune에서 비즈니스용 Microsoft 스토어를 사용 하도록 설정 합니다. Intune을 열고 **Client apps**  >  **Microsoft Store for Business 용** 클라이언트 앱을 선택 합니다. <br>

    ![비즈니스용 스토어 사용](images/sh2-deploy-apps-sync.png)

3. Intune에서 **비즈니스용 Microsoft 스토어** 를 열고 **설정**  >  **배포**  >  **관리 도구**를 선택 합니다. 관리 도구로 **Microsoft Intune** 을 선택 합니다. <br>

    ![Intune을 관리 도구로 추가](images/sh2-set-intune8.png)

4. 비즈니스용 Microsoft Store에서 **설정**  >  **상점**  >  **쇼핑 환경을**선택 하 고 **오프 라인 앱 표시**를 선택 합니다. 오프 라인 앱은 Intune으로 동기화 하 고 장치에 중앙에서 배포할 수 있는 앱을 참조 합니다.
5. 오프 라인 쇼핑을 사용 하도록 설정한 후에는 Intune으로 동기화 하 고 디바이스 라이선스로 배포할 수 있는 앱에 대 한 오프 라인 라이선스를 얻을 수 있습니다.
6. **Intune**  >  **클라이언트 앱**  >  **for 비즈니스용 Microsoft Store**에서 **동기화**를 선택 합니다.
7. 클라이언트 앱 페이지에서 앱 목록에서 앱을 검색 합니다. 앱을 원하는 장치 그룹 또는 그룹에 할당 합니다. **과제**  >  **추가 그룹**을 선택 합니다. <br>

![* 그룹에 앱 할당 *](images/sh2-assign-group.png) <br>

8. 할당 유형에 **서 필수**를 선택 합니다. <br>

![* 그룹에 앱 할당 *](images/sh2-add-group.png) <br>

9. 선택한 그룹에 대해 **장치 라이선스** 를 선택한 다음 **확인** 을 선택 하 고 할당을 저장 합니다. <br>
 
![* 그룹에 앱 할당 *](images/sh2-apps-assign.png)
