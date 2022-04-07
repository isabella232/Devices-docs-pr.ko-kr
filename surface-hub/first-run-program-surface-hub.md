---
title: Surface Hub 처음으로 설정
description: '\ 0034;첫 실행\ 0034;이란 용어는 처음으로 Microsoft Surface Hub의 전원을 켤 때 수행하는 일련의 단계를 가리키며, OOBE(\ 0034;첫 실행 경험\ 0034;)와 의미가 같습니다. 이 섹션에서 프로세스를 안내합니다.'
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: 첫 실행, Surface Hub, 첫 실행 경험, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: medium
ms.openlocfilehash: 551867ccbb041fe292d9ec60f38bb89acfbc764e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472448"
---
# <a name="first-time-setup-for-surface-hub"></a>Surface Hub 처음으로 설정

Surface Hub 처음 시작하면 디바이스가 자동으로 처음 설치 모드로 전환되어 계정 구성 및 관련 설정을 안내합니다.

> [!TIP]
> [프로비전 패키지를](#use-provisioning-packages) 사용하여 전체 설치 프로세스를 자동화하여 여러 Surface Hub에서 일관된 환경을 보장할 수 있습니다.

## <a name="get-started"></a>시작

1. 기본적으로 Cortana 프로세스를 안내할 수 있습니다. Cortana 지원을 해제하려면 마이크 아이콘을 선택합니다.

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana 프로세스를 안내할 수 있습니다.":::

2. **지역을 선택합니다.** 자동 검색된 지역을 확인하고 **예를** 선택합니다.

    :::image type="content" source="images/hub-setup-region.png" alt-text="지역을 선택합니다.":::

3. **키보드 레이아웃을 확인합니다.** **예를** 선택합니다.

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="키보드 레이아웃을 확인합니다.":::

4. 두 번째 키보드를 추가하려면 **레이아웃 추가**를 선택합니다. 그렇지 않으면 **건너뛰기(Skip**)를 선택합니다.

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="두 번째 키보드를 추가합니다.":::

5. **네트워크에 커넥트.** 이미 이더넷 케이블을 연결한 경우 Surface Hub 자동으로 네트워크에 연결됩니다. 또는 무선 네트워크에 연결할 수 있습니다. **참고:** 로그인 요청을 공급자의 웹 사이트로 리디렉션하는 핫스팟(포로 포털)의 무선 네트워크에 연결할 수 없습니다. **다음**을 선택합니다.

    :::image type="content" source="images/hub-setup-network.png" alt-text="네트워크에 커넥트.":::

6. **Windows 10 사용권 계약에 동의합니다.** **수락**을 선택합니다.

    :::image type="content" source="images/hub-setup-license.png" alt-text="Windows 10 사용권 계약에 동의합니다.":::

7. UPN 주소(user@contoso.com) 또는 하위 수준 도메인 주소(CONTOSO\user)를 사용하여 **디바이스 계정 정보를 입력**합니다. 사용자 환경과 일치하는 형식을 사용하고 암호를 입력합니다.

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="디바이스 계정 정보를 입력합니다.":::

| 환경                                              | 디바이스 계정의 필수 형식 |
| -------------------------------------------------------- | ---------------------------------- |
| 디바이스 계정은 온라인에서만 호스팅됩니다.                     | username@contoso.com               |
| 디바이스 계정은 온-프레미스에서만 호스팅됩니다.                | CONTOSO\user                       |
| 디바이스 계정이 온라인 및 온-프레미스에 호스트됨(하이브리드) | CONTOSO\user                       |

>[!NOTE]
>디바이스 계정 설정을 건너뛸 수 있지만 디바이스가 인프라에 완전히 통합되지는 않습니다. 지금 설정을 건너뛰는 경우 나중에 설정 앱을 사용하여 디바이스 계정을 추가할 수 있습니다.

8. **암호를 입력** 하고 다음을 선택합니다 **.**

9. Surface Hub 이전 단계에서 입력한 도메인에서 Exchange 서버 및 SIP 주소 정보를 자동으로 검색합니다. 또는 필요한 경우 Exchange 서버 주소를 제공하고 **다음**을 선택합니다.

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange 서버 및 SIP 주소입니다.":::

10. **이 디바이스의 이름을 지정합니다.** 디바이스의 이름을 입력하거나 제안된 이름을 사용합니다. **다음을 선택합니다**.

    :::image type="content" source="images/hub-setup-name.png" alt-text="이 디바이스의 이름을 지정합니다.":::

- **친숙한 이름은** Surface Hub 2S의 왼쪽 아래 모서리에 표시되며 디바이스에 프로젝팅할 때 표시됩니다.
- **디바이스 이름은** Active Directory 또는 Azure Active Directory 연결된 경우 및 Intune 사용하여 디바이스를 등록할 때 디바이스를 식별합니다.

>[!IMPORTANT]
>Surface Hub Active Directory에 적용하려는 경우 디바이스 이름이 [AD의 컴퓨터 이름에 대한 표준 요구 사항을](/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names) 충족해야 합니다. 그렇지 않으면 설정이 실패합니다.

>[!NOTE]
>[인프라를 통해 Miracast](miracast-over-infrastructure.md)를 사용하려는 경우 디바이스 이름을 DNS을 통해 검색할 수 있어야 합니다. Surface Hub가 동적 DNS를 통해 자동으로 등록하도록 하거나 수동으로 Surface Hub의 디바이스 이름에 대한 A 또는 AAAA 레코드를 만들어 검색할 수 있습니다.

### <a name="configure-device-admin-accounts"></a>디바이스 관리자 계정 구성

처음 설치하는 동안에만 디바이스 관리자를 설정할 수 있습니다. 자세한 내용은 다음을 참고하십시오.

- [Surface Hub 2S 디바이스 소속](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [관리자 그룹 관리](admin-group-management-for-surface-hub.md)

1. **관리자 계정 유형을 선택합니다.** Active Directory Domain Services, Azure Active Directory 또는 로컬 관리자 옵션 중 하나를 선택합니다.

    :::image type="content" source="images/hub-setup-join.png" alt-text="관리자 계정 유형을 선택합니다.":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. 온-프레미스 환경에서 Surface Hub 사용하려는 경우 **허브를 Active Directory Domain Services** 연결할 수 있습니다.  디바이스를 Active Directory에 조인할 수 있는 권한이 있는 사용자의 자격 증명을 입력합니다.
2. Surface Hub 2S에서 설정 앱에 로그인할 수 있는 멤버가 포함된 Active Directory 보안 그룹을 선택합니다.
3. **마침**을 선택합니다. 장치가 다시 시작됩니다.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. Microsoft Intune 또는 MDM 공급자를 사용하여 클라우드에서 Surface Hub 관리하려는 경우 **Microsoft Azure Active Directory** 선택합니다.
2. 다음을 선택하고 회사 또는 학교 계정으로 로그인합니다. 리디렉션된 경우 조직의 로그인 페이지를 사용하여 인증하고 요청된 경우 추가 자격 증명을 제공합니다. 그렇지 않으면 암호를 입력하고 다음을 선택합니다 **.**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="회사 또는 학교 계정으로 로그인합니다.":::

>[!NOTE]
>설정 앱을 사용하여 Surface Hub를 관리하도록 구성하려면 디바이스를 Azure AD에 조인하기 전에 테넌트에서 자동 Intune 등록을 사용하도록 설정합니다. 그런 다음 Intune 정책을 사용하여 Surface Hub[에서 전역이 아닌 관리자를 구성할](surface-hub-2s-nonglobal-admin.md) 수 있습니다.

### <a name="local-administrator-account"></a>로컬 관리자 계정

- 로컬 관리자의 사용자 이름과 기억하기 쉬운 암호를 입력합니다. 로컬 관리자 암호를 잊어버린 경우 [디바이스를 복구](surface-hub-2s-recover-reset.md) 하고 설치 프로세스를 반복해야 합니다.  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="로컬 관리자 계정에 대한 기억하기 쉬운 암호를 입력합니다.":::

### <a name="choose-privacy-settings-for-your-device"></a>디바이스에 대한 개인 정보 설정 선택

- 사용 가능한 개인 정보 설정에서 선택하고 수락을 선택합니다 **.**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="개인 정보 설정을 선택합니다.":::

### <a name="use-provisioning-packages"></a>프로비전 패키지 사용

처음 설치 옵션을 사용자 지정하여 여러 Surface Hub에서 일관된 환경을 보장할 수 있습니다.

1. 시작하려면 [프로비저닝 패키지 만들기](provisioning-packages-for-surface-hub.md) 의 설명서를 검토하고 프로비전 패키지를 USB 썸 드라이브에 저장합니다.
2. 사용권 계약 페이지(위 설정 단계의 6단계)가 표시되면 USB 포트 중 하나에 USB 썸 드라이브를 삽입합니다.
3. 메시지가 표시되면 사용하려는 프로비저닝 패키지를 선택합니다.
4. 여러 디바이스 CSV 파일을 만든 경우 디바이스 구성을 선택할 수 있습니다.
5. 지침에 따라 처음으로 설치를 완료합니다.
