---
title: 첫 실행 프로그램(Surface Hub)
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
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: af6f6cc71a94d075341637499fe98f8206157e49
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576578"
---
# <a name="first-run-program-surface-hub"></a>첫 실행 프로그램(Surface Hub)


"첫 실행"이란 용어는 처음으로 Microsoft Surface Hub의 전원을 켤 때 수행하는 일련의 단계를 가리키며, OOBE("첫 실행 경험")와 의미가 같습니다. 이 섹션에서 프로세스를 안내합니다.

지금까지 이전 단계를 모두 완료했어야 합니다.

-   [Surface Hub에 대한 환경 준비](prepare-your-environment-for-surface-hub.md)
-   [물리적으로 Surface Hub 디바이스 설치](physically-install-your-surface-hub-device.md)및
-   [설치 워크시트](setup-worksheet-surface-hub.md)

완료했다고 가정하면 첫 실행은 간단하고 빠르게 진행되어야 합니다.
일반적인 절차는 다음 6단계로 이루어집니다.

1.  [안녕하세요 페이지](#first-page)
2.  [자동 설치 페이지](#set-up-for-you)
3.  [디바이스 계정 페이지](#device-account)
4.  [이 디바이스 이름 지정 페이지](#name-this-device)
5.  [이 디바이스에 대한 관리자 설정 페이지](#setup-admins)
6.  [Surface Hub 업데이트](#update-surface-hub)

각 섹션에는 변경 내용이 있을 때 사용할 수 있는 경로에 대한 정보도 포함되어 있습니다. 예를 들어 대부분의 Surface Hub는 유선 네트워크 연결을 사용하지만 일부는 무선을 사용하여 설치됩니다. 해당하는 경우 세부 정보가 제공됩니다.

>[!NOTE]
>시작하기 전에 Surface Hub와 함께 제공된 별도 키보드가 설치되고 준비되어 있어야 합니다. 자세한 내용은 Surface Hub 설치 가이드를 참조하세요.

 

## <a name="hi-there-page"></a><a href="" id="first-page"></a>안녕하세요 페이지


처음으로 Surface Hub 전원을 켤 때 표시되는 첫 번째 화면입니다. 여기서 장치에 대한 지역화 정보를 입력합니다.

>[!NOTE]
>또한 프로비저닝 패키지를 배포하는 선택적 프로세스를 시작합니다. 이 작업을 수행 중이면 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.

 언어를 선택하면 초기 설치 옵션이 표시됩니다.

![ICD 옵션 검사 목록을 보여 주는 이미지입니다.](images/setuplocale.png)

### <a name="details"></a>세부 정보

표시된 기본값이 올바르면 **다음**을 클릭하여 계속할 수 있습니다. 그렇지 않으면 해당 상자에 데이터를 입력해야 합니다.

-   **국가/지역:** Surface Hub를 사용할 국가 또는 지역을 선택합니다.
-   **앱 언어:** 앱과 기능은 이 언어와 언어 형식으로 표시됩니다.
-   **키보드 레이아웃:** 디바이스와 함께 사용할 화상 및 실제 키보드의 키보드 레이아웃을 선택합니다.
-   **표준 시간대:** Surface Hub를 사용할 표준 시간대를 선택합니다.

### <a name="what-happens"></a>발생하는 동작

>[!NOTE]
> 이 페이지의 설정을 입력한 후에는 디바이스를 초기화하지 않는 한 이 화면으로 돌아올 수 없습니다([디바이스 초기화](device-reset-surface-hub.md) 참조). 계속하기 전에 설정이 제대로 구성되었는지 확인합니다.

 

설정을 적용하면 디바이스가 유선 네트워크 연결을 확인합니다. 연결이 정상이면 [자동 설치 페이지](#set-up-for-you)가 표시됩니다. 유선 연결에 문제가 있으면 디바이스에서 [네트워크 설정 페이지](#network-setup)가 표시됩니다.

유선 연결을 찾을 수 없는 경우 디바이스가 무선 연결을 설치하려고 하며 [네트워크 설정 페이지](#network-setup)가 표시됩니다.

## <a name="network-setup-page"></a><a href="" id="network-setup"></a>네트워크 설정 페이지


디바이스가 네트워크 또는 인터넷에 연결하는 데 사용할 수 있는 유선 연결을 검색하지 못하면 이 페이지가 표시됩니다. 여기서 무선 네트워크에 연결하거나 네트워크 연결 설정을 건너뛸 수 있습니다.

![네트워크 설정 페이지를 보여 주는 이미지입니다.](images/setupnetworksetup-1.png)

### <a name="details"></a>세부 정보

이 화면은 디바이스가 유선 네트워크를 검색하지 못한 경우에만 표시됩니다. 이 화면이 표시되는 경우 다음 세 가지 옵션이 있습니다.

-   표시된 무선 네트워크 중 하나를 선택할 수 있습니다. 네트워크가 보호된 경우 로그인 페이지로 이동됩니다. 자세한 내용은 [무선 네트워크 설정](#wireless) 을 참조하세요.
-   네트워크 연결을 건너뛰려면 **이 단계 건너뛰기** 를 클릭합니다. [자동 설치 페이지](#set-up-for-you)로 이동됩니다.
    >[!NOTE]
    >건너뛸 경우 디바이스에 네트워크 연결이 없으며 시스템 업데이트, 메일 및 일정 동기화 등 네트워크 연결이 필요한 기능은 Surface Hub에서 작동하지 않습니다. 나중에 무선 네트워크에 연결할 수 있습니다(무선 설정 [관리 참조).](wireless-network-management-for-surface-hub.md)

     

-   이 화면이 표시되는 동안 네트워크 케이블을 연결할 수 있습니다. 디바이스가 연결을 검색하고 화면에 **다음** 이 추가됩니다. 유선 연결 만들기를 계속하려면 **다음** 을 클릭합니다.

### <a name="what-happens"></a>발생하는 동작

시작 시 디바이스에 유선 연결이 있고 네트워크 또는 인터넷 연결을 설정할 수 있는 경우에는 이 페이지가 표시되지 않습니다. 무선 연결에 디바이스를 연결하려는 경우 첫 실행 시 이더넷 케이블이 연결되지 않았는지 확인합니다. 이 화면으로 이동됩니다. 지금 설정하는 항목에 관계없이 나중에 [설정을 사용](wireless-network-management-for-surface-hub.md) 하여 다른 연결을 설정할 수 있습니다.

이 페이지에서 보안 무선 네트워크에 연결하려는 경우 선택한 네트워크를 클릭하고 연결하는 데 필요한 정보(암호 또는 계정 자격 증명)를 제공합니다. [무선 네트워크 설정](#wireless)을 참조하세요.

## <a name="wireless-network-setup"></a><a href="" id="wireless"></a>무선 네트워크 설정


이 페이지는 보호된 무선 네트워크를 선택한 경우에 표시됩니다.

![무선 네트워크 설정 페이지를 보여 주는 이미지입니다.](images/setupnetworksetup-3.png)

### <a name="details"></a>세부 정보

-   **사용자 이름:** 선택한 무선 네트워크에 대한 사용자 이름을 입력합니다.
-   **암호:** 네트워크 암호입니다.

### <a name="what-happens"></a>발생하는 동작

디바이스가 지정된 네트워크에 연결하려고 합니다. 성공하면 [자동 설치 페이지](#set-up-for-you)로 이동됩니다.

## <a name="network-proxy-setup"></a><a href="" id="proxy"></a>네트워크 프록시 설정


이 페이지는 디바이스가 연결이 제한된 유선 연결을 검색하는 경우에 표시됩니다. 다음 세 가지 옵션이 있습니다.

-   제한된 유선 연결 대신 사용할 무선 네트워크를 선택할 수 있습니다.

-   **이 단계 건너뛰기**를 선택하여 네트워크 연결을 건너뛸 수 있습니다. [자동 설치 페이지](#set-up-for-you)로 이동됩니다.

    > [!NOTE]
    > 건너뛸 경우 디바이스에 네트워크 연결이 없으며 메일 및 일정 동기화 등 네트워크 연결이 필요한 기능은 Surface Hub에서 작동하지 않습니다. 나중에 무선 네트워크에 연결할 수 있습니다(무선 설정 [관리 참조).](wireless-network-management-for-surface-hub.md)

-   네트워크 프록시를 사용하는 방법을 지정할 수 있는 **프록시 설정 입력** 을 선택할 수 있습니다. 다음 화면으로 이동됩니다.

    ![네트워크 프록시 페이지를 보여 주는 이미지입니다.](images/setupnetworksetup-2.png)

    이전 화면에서 **프록시 설정 입력** 을 클릭한 경우에 표시되는 화면입니다.

    ![프록시 서버 설정 세부 정보를 보여 주는 이미지입니다.](images/setupnetworksetup-4.png)

### <a name="details"></a>세부 정보

네트워크 연결을 설정하려면 스크립트 이름이나 프록시 서버 및 포트 정보 중 하나를 채워야 합니다.

-   **프록시 스크립트:** 프록시 스크립트의 주소를 제공합니다.
-   **프록시 서버 및 포트:** 프록시 서버 주소와 포트를 제공할 수 있습니다.

### <a name="what-happens"></a>발생하는 동작

**다음**을 클릭하면 디바이스가 프록시 서버에 연결하려고 합니다. 성공하면 [자동 설치 페이지](#set-up-for-you)로 이동됩니다.

**이 단계 건너뛰기**를 선택하여 네트워크 연결을 건너뛸 수 있습니다. [자동 설치 페이지](#set-up-for-you)로 이동됩니다.

>[!NOTE]
>건너뛸 경우 디바이스에 네트워크 연결이 없으며 메일 및 일정 동기화 등 네트워크 연결이 필요한 기능은 Surface Hub에서 작동하지 않습니다. 나중에 무선 네트워크에 연결할 수 있습니다(무선 설정 [관리 참조).](wireless-network-management-for-surface-hub.md)

 

## <a name="set-up-for-you-page"></a><a href="" id="set-up-for-you"></a>자동 설치 페이지


이 화면은 정보 제공 목적으로만 사용되며, 기본적으로 사용되는 권장 설정을 보여 줍니다.

![자동 설치 페이지를 보여 주는 이미지입니다.](images/setupsetupforyou.png)

### <a name="details"></a>세부 정보

이 화면을 읽고 기본적으로 사용되는 서비스를 확인해야 합니다. 필요한 경우 설정 앱을 사용하여 모두 변경할 수 있지만 변경할 경우의 결과에 대해 주의해야 합니다. 자세한 내용은 [Surface Hub 소개](intro-to-surface-hub.md) 를 참조하세요.

설정 검토를 마쳤으면 **다음** 을 클릭하여 계속합니다.

### <a name="what-happens"></a>발생하는 동작

페이지에 표시된 설정은 이미 지정되었으며, 첫 실행이 완료될 때까지 변경할 수 없습니다.

## <a name="device-account-page"></a><a href="" id="device-account"></a>디바이스 계정 페이지


이 페이지에서 Surface Hub는 이전에 구성된 디바이스 계정의 자격 증명을 묻는 메시지를 표시합니다. ([디바이스 계정 만들기 및 테스트](create-and-test-a-device-account-surface-hub.md) 참조). Surface Hub는 계정의 다양한 속성을 검색하려고 하며, 실패할 경우 다른 페이지에서 추가 정보를 요청할 수도 있습니다.

>[!NOTE]
>첫 실행 중에 발생할 수 있는 특정 오류는 이 섹션에서 설명하지 않습니다. 오류에 대한 자세한 내용은 [Surface Hub 문제 해결](troubleshoot-surface-hub.md) 을 참조하세요.


![디바이스 계정 정보 입력 페이지를 보여 주는 이미지입니다.](images/setupdeviceacct.png)

### <a name="details"></a>세부 정보

첫 번째 입력 필드에서 **UPN(사용자 계정 이름)** 또는 **도메인\\사용자 이름**을 계정 식별자로 사용합니다. 환경과 일치하는 형식을 사용하고 암호를 입력합니다.


|                      환경                      | 디바이스 계정의 필수 형식 |
|-------------------------------------------------------|------------------------------------|
|         디바이스 계정이 온라인에만 호스트됩니다.         |        username@domain.com         |
|        디바이스 계정이 온-프레미스에만 호스트됩니다.         |          도메인\사용자 이름           |
| 디바이스 계정이 온라인 및 온-프레미스에 호스트됩니다(하이브리드). |          도메인\사용자 이름           |

디바이스 계정 설정을 건너뛰려면 **디바이스 계정 설정 건너뛰기**를 클릭합니다. 그러나 디바이스 계정을 설정하지 않으면 디바이스가 인프라에 완벽하게 통합되지 않습니다. 예를 들어 사용자가 다음을 수행할 수 없습니다.

-   시작 화면에서 모임 일정 확인
-   시작 화면에서 모임 시작
-   OneNote에서 화이트보드를 메일로 보내기
-   모임에 비즈니스용 Skype 사용

지금 설정을 건너뛰는 경우 나중에 설정 앱을 사용하여 디바이스 계정을 추가할 수 있습니다.

**디바이스 계정 설정 건너뛰기**를 클릭하면 디바이스에 디바이스 계정이 없을 경우 발생하는 동작을 보여 주는 대화 상자가 디바이스에서 표시됩니다. **예, 건너뛰겠습니다.** 를 선택하면 [이 디바이스 이름 지정 페이지](#name-this-device)로 이동됩니다.

![디바이스 계정 만들기를 건너뛰고 싶은지 확인하기 위해 메시지가 표시되는 이미지입니다.](images/setupskipdeviceacct.png)

### <a name="what-happens"></a>발생하는 동작

디바이스는 디바이스 계정의 UPN이나 도메인\\사용자 이름 및 암호를 사용하여 다음을 수행합니다.

-   계정이 AD(Active Directory)에 있는지 또는 Azure AD(Azure Active Directory)에 있는지를 확인합니다.

    -   UPN을 입력한 경우 디바이스는 Azure AD에서 계정을 찾습니다.
    -   도메인\\사용자 이름을 입력한 경우 디바이스는 AD에서 계정을 찾습니다.
-   계정의 사서함에 대한 Microsoft Exchange 서버를 찾습니다.
-   계정의 SIP(Session Initiation Protocol) 주소를 찾습니다.
-   계정의 표시 이름 및 별칭 특성을 끌어옵니다.

## <a name="exchange-server-page"></a><a href="" id="exchange-server"></a>Exchange 서버 페이지


이 페이지는 문제가 있는 경우에만 표시됩니다. 일반적으로 이는 제공한 디바이스 계정이 AD(Active Directory) 또는 Azure AD(Azure Active Directory)에 있지만 계정의 Exchange 서버가 검색되지 않았음을 의미합니다.

![Exchange 서버 페이지를 보여 주는 이미지입니다.](images/setupexchangeserver-01.png)

### <a name="details"></a>세부 정보

디바이스 계정의 사서함이 호스트된 Exchange 서버의 이름을 입력합니다.

이 단계를 건너뛰려면 **Exchange 서비스 설정 건너뛰기** 를 클릭합니다. 건너뛰면 사용자가 다음 작업을 수행할 수 없게 됩니다.

-   시작 화면에서 모임 일정 확인
-   시작 화면에서 모임 시작
-   OneNote에서 화이트보드를 메일로 보내기

설치 종속성에 대한 자세한 내용은 [Surface Hub 소개](intro-to-surface-hub.md) 를 참조하세요.

나중에 설정 앱을 사용하여 디바이스 계정에 Exchange 서비스를 사용하도록 설정할 수 있습니다.

**Exchange 서비스 설정 건너뛰기**를 클릭하면 발생하는 동작을 보여 주는 대화 상자가 디바이스에서 표시됩니다. **예, 건너뛰겠습니다.** 를 선택하면 Exchange 서비스가 설정되지 않습니다.

![Exchange 서비스 설정을 건너뛸 때 표시되는 확인 메시지를 보여 주는 이미지입니다.](images/setupexchangeserver-02.png)

### <a name="what-happens"></a>발생하는 동작

Surface Hub는 여기에 입력한 Exchange 서버에서 디바이스 계정의 유효성을 검사하려고 합니다. Exchange 서버에 연결하고 유효성을 검사할 수 있는 경우 첫 실행이 진행됩니다.

Exchange 서비스 설정을 건너뛰도록 선택하면 Surface Hub가 Exchange 서버 찾기를 중지하고 Exchange 서비스(메일 및 일정)가 사용되지 않습니다.

## <a name="exchange-policies-page"></a><a href="" id="exchange-policies"></a>Exchange 정책 페이지


이 페이지는 다음과 같은 경우에 표시됩니다.

-   디바이스 계정에서 PasswordEnabled 정책이 1로 설정된 EAS(Exchange Active Sync) 정책을 사용하는 경우
-   Exchange 연결이 없는 경우
-   Exchange에서 오류를 나타내는 상태 코드를 반환하는 경우 (예: 계정이 너무 많은 디바이스에 프로비전된 경우)
-   Exchange 지원 프로토콜이 Surface Hub에서 지원되지 않는 경우
-   Exchange에서 잘못된 XML을 반환하는 경우

![Exchange 정책 페이지를 보여 주는 이미지입니다.](images/setupexchangepolicies.png)

### <a name="details"></a>세부 정보

이 페이지는 정보 제공 목적으로만 사용되므로 입력이 필요하지 않습니다. 그러나 건너뛰거나 오류가 발생한 유효성 검사를 다시 시도하는 두 가지 진행 옵션이 있습니다. 가장 적합한 옵션을 결정하기 전에 다음 **발생하는 동작** 섹션을 읽어보세요. 옵션 중 하나를 클릭하기 전에 다른 곳에서 문제를 해결할 수도 있습니다.

-   **지원되지 않는 정책을 계속 사용하려면 여기를 클릭하세요.**: 첫 실행을 계속하려면 클릭합니다. Surface Hub는 Exchange 서비스를 사용하거나 동기화할 수 없습니다.
-   **다시 시도**: Exchange 서버의 정책을 다시 확인합니다.

### <a name="what-happens"></a>발생하는 동작

Surface Hub는 디바이스 계정의 EAS 정책에 PasswordEnabled 정책이 0(False)으로 설정되었는지 여부를 확인합니다. 설정되지 않은 경우 메일 및 일정을 동기화할 수 없으며 Surface Hub에서 Exchange 서비스를 사용할 수 없습니다. PC에서 Exchange 관리 도구를 사용하여 디바이스 계정에 PasswordEnabled 정책이 0으로 설정되었는지 확인할 수 있습니다. 설정되지 않은 경우 여기서 계정을 다시 구성하고 **다시 시도** 를 클릭할 수 있습니다.

정책이 이미 올바르게 구성된 경우 디바이스가 네트워크 또는 인터넷에 제대로 연결되었는지 확인하고, 이 페이지는 Surface Hub가 Exchange 서버에 연결할 수 없는 경우에도 표시되므로 Exchange 서버에 연결할 수 있는지 확인합니다.

Exchange에 연결할 수 없는 다른 가능한 이유는 인증서 기반 인증 때문입니다. 인증서 문제 때문에 이 페이지가 표시될 수도 있습니다. 디바이스에서 0x80072F0D 또는 0X800C0019 오류 코드를 표시하는 경우 인증서가 필요합니다. 프로비전은 첫 실행 프로세스의 첫 페이지에서 수행되기 때문에 **지원되지 않는 정책을 계속 사용하려면 여기를 클릭하세요.** 를 클릭하여 Exchange 서비스를 사용하지 않도록 설정한 다음 설정 앱을 통해 올바른 인증서를 설치해야 합니다.

이 확인을 건너뛰도록 선택하면 Surface Hub가 Exchange 서버 찾기 및 EAS 정책 유효성 검사를 중지하고 Exchange 서비스가 사용되지 않습니다. 설치 종속성에 대한 자세한 내용은 [Surface Hub 소개](intro-to-surface-hub.md) 를 참조하세요.

## <a name="name-this-device-page"></a><a href="" id="name-this-device"></a>이 디바이스 이름 지정 페이지


이 페이지에는 Surface Hub를 식별하는 데 사용할 두 개의 이름을 제공하라는 메시지가 표시됩니다.

![이 디바이스 이름 지정 페이지를 보여 주는 이미지입니다.](images/setupnamedevice.png)

### <a name="details"></a>세부 정보

표시된 기본값이 올바르면 **다음** 을 클릭하여 계속합니다. 그렇지 않으면 텍스트 상자 중 하나 또는 둘 다에 데이터를 입력합니다.

-   **이름:** 사용자가 Surface Hub에 무선으로 연결하려고 할 때 표시되는 이름입니다.
-   **디바이스 이름:** 화면에 설명된 대로 임의의 고유 이름으로 설정할 수 있습니다.

두 이름이 모두 길이 요구 사항 이내이고 제한된 문자를 사용하지 않는 한, **다음** 을 클릭하면 다음 페이지인 [이 디바이스에 대한 관리자 설정](#setup-admins)으로 이동됩니다.

### <a name="what-happens"></a>발생하는 동작

Surface Hub에는 두 개의 디바이스 이름이 필요하며, 기본적으로 다음과 같이 설정됩니다.

-   **이름:** 기본적으로 디바이스 계정의 표시 이름으로 설정됩니다.
-   **디바이스 이름:** 기본적으로 디바이스 계정의 별칭으로 설정됩니다.

나중에 이름 중 하나를 변경할 수 있지만 다음에 유의하세요.

-   사용자가 무선으로 연결하려고 할 때 Surface Hub 간에 구분할 수 있도록 이름은 인식 가능하고 서로 달라야 합니다.
-   디바이스를 도메인에 가입하려는 경우 디바이스 이름은 계정의 Active Directory 도메인에 있는 다른 디바이스의 이름과 달라야 합니다. 디바이스가 도메인에 가입된 다른 디바이스와 동일한 이름을 사용하는 경우에는 도메인에 가입할 수 없습니다.

>[!NOTE]
>[인프라를 통해 Miracast](miracast-over-infrastructure.md)를 사용하려는 경우 디바이스 이름을 DNS을 통해 검색할 수 있어야 합니다. Surface Hub가 동적 DNS를 통해 자동으로 등록하도록 하거나 수동으로 Surface Hub의 디바이스 이름에 대한 A 또는 AAAA 레코드를 만들어 검색할 수 있습니다.

## <a name="set-up-admins-for-this-device-page"></a><a href="" id="setup-admins"></a>이 디바이스에 대한 관리자 설정 페이지


이 페이지에서는 디바이스를 로컬로 관리하기 위해 관리자 계정을 설정하려는 방법에 대한 몇 가지 옵션 중에서 선택합니다.

각 Surface Hub를 사용할 수 있는 인증된 직원 수에 제한이 없으므로 세션 간에 변경되지 않도록 설정이 잠깁니다. 관리자만 디바이스의 설정을 구성할 수 있으며, 이 페이지에서 해당 권한을 가진 관리자 유형을 선택합니다.

>[!NOTE]
>이 페이지는 주로 디바이스의 UI에서 디바이스를 구성할 수 있는 사용자, 즉 실제로 디바이스를 방문하고, 로그인하고, 설정 앱을 열고, 설정을 변경할 수 있는 사용자를 확인하는 데 사용됩니다.

 

![이 디바이스에 대한 관리자 설정 페이지를 보여 주는 이미지입니다.](images/setupsetupadmins.png)

### <a name="details"></a>세부 정보

사용 가능한 다음 세 가지 옵션 중 하나를 선택합니다.

-   **Microsoft Azure Active Directory 사용**
-   **Active Directory 도메인 서비스 사용**
-   **로컬 관리자 사용**

### <a name="what-happens"></a>발생하는 동작

옵션을 선택할 때 발생하는 동작입니다.

-   **Microsoft Azure Active Directory 사용**

    이 옵션을 클릭하면 디바이스를 Azure AD에 가입할 수 있습니다. **다음**을 클릭하면 디바이스가 일부 설정을 적용하기 위해 다시 시작되고, [Microsoft Azure Active Directory 사용](#use-microsoft-azure) 페이지로 이동된 다음 Azure AD에 가입할 수 있는 자격 증명을 입력하라는 메시지가 표시됩니다. 가입된 조직의 Azure 전역 관리자 역할 구성원은 앱 앱을 설정 있습니다. 허용되는 특정 사용자는 Azure AD 구독 및 Azure AD 조직의 설정을 구성한 방식에 따라 달라집니다.
    
    > [!IMPORTANT]
    > 디바이스를 Azure AD에 가입하기 전에 설정 앱을 사용하여 Surface Hub를 관리하도록 할 수 있는 사용자 구성을 통해 테넌트에서 자동 [Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) 등록이 사용하도록 설정되어 있는지 확인합니다. 그런 다음 Intune 정책을 사용하여 Surface Hub에서 전역이 아닌 [관리자를](surface-hub-2s-nonglobal-admin.md) 구성할 수 있습니다.

-   **Active Directory 도메인 서비스 사용**

    장치를 AD에 가입하려면 이 옵션을 클릭합니다. **다음**을 클릭하면 [Active Directory 도메인 서비스 사용](#use-active-directory) 페이지로 이동되며 지정된 도메인에 가입할 수 있는 자격 증명을 입력하라는 메시지가 표시됩니다. 가입 후에 가입된 도메인에서 보안 그룹을 선택할 수 있으며, 해당 보안 그룹의 사용자는 설정 앱을 사용할 수 있습니다.

-   **로컬 관리자 사용**

    이 관리자는 디렉터리 서비스에서 백업되지 않으므로 디바이스가 Azure AD 또는 AD에 액세스할 수 없는 경우에만 이 옵션을 선택하는 것이 좋습니다. [로컬 관리자 사용](#use-a-local-admin) 페이지에서 관리자의 사용자 이름 및 암호를 만든 후 설정 앱을 열 때마다 동일한 자격 증명을 다시 입력해야 합니다.

    로컬 관리자가 로그인하려면 Surface Hub에 실제로 액세스할 수 있어야 합니다.

>[!NOTE]
>이 프로세스를 마친 후에는 디바이스를 초기화하지 않는 한 디바이스의 관리 옵션을 변경할 수 없습니다.

 

### <a name="use-microsoft-azure-active-directory"></a><a href="" id="use-microsoft-azure"></a>Microsoft Azure Active Directory 사용

Surface Hub를 Azure AD(Azure Active Directory)에 가입하는 경우 이 **다음에 발생하는 동작** 페이지가 표시됩니다. 페이지를 읽고 **다음** 을 클릭하여 **로그인 페이지**로 이동합니다.

Azure AD에 가입하면 다음 두 가지 주요 이점이 있습니다.

1.  조직의 일부 직원이 관리자로 디바이스에 액세스할 수 있으며, 설정 앱을 시작하고 디바이스를 구성할 수 있습니다. 관리자 권한이 있는 사용자는 Azure AD 구독에서 정의됩니다.

2.  Azure AD가 MDM(모바일 디바이스 관리) 솔루션에 연결된 경우 정책 및 구성을 적용할 수 있도록 디바이스가 해당 MDM 솔루션에 등록됩니다.

    ![Surface Hub를 Azure Active Directory에 연결할 때의 메시지를 보여 주는 이미지입니다.](images/setupjoiningazuread-1.png)

### <a name="details"></a>세부 정보

다음 입력이 필요합니다.

-   **사용자의 UPN:** Azure AD에 가입할 수 있는 계정의 UPN(사용자 계정 이름)입니다.
-   **암호:** Azure AD에 가입하는 데 사용하는 계정의 암호입니다.

![계정 로그인 정보를 보여 주는 이미지입니다.](images/setupjoiningazuread-2.png)

이 시점까지 Azure AD 계정에 대한 유효한 자격 증명이 없을 경우 디바이스에서 로컬 관리자 계정을 만들지 계속할 수 있습니다. **대신 로컬 계정으로 Windows를 설정**을 클릭합니다.

![관리자 계정 설정 페이지를 보여 주는 이미지입니다.](images/setupjoiningazuread-3.png)

### <a name="what-happens"></a>발생하는 동작

유효한 Azure AD 계정 자격 증명을 입력하면 디바이스가 연결된 Azure AD 조직에 가입하려고 합니다. 성공하면 디바이스가 해당 조직의 직원을 디바이스의 로컬 관리자로 프로비전합니다. Azure AD 테넌트가 구성된 경우에는 디바이스가 MDM에도 등록됩니다.

### <a name="use-active-directory-domain-services"></a><a href="" id="use-active-directory"></a>Active Directory 도메인 서비스 사용

이 페이지에는 Surface Hub가 보안 그룹을 디바이스 관리자로 프로비전할 수 있도록 도메인 가입을 위한 자격 증명을 묻는 메시지가 표시됩니다.

디바이스가 도메인에 가입되고 나면 가입한 도메인의 보안 그룹을 지정해야 합니다. 이 보안 그룹은 Surface Hub에서 관리자로 프로비전되며, 보안 그룹의 모든 사용자가 해당 도메인 자격 증명을 입력하여 설정에 액세스할 수 있습니다.

![도메인 가입 페이지를 사용한 관리자 설정을 보여 주는 이미지입니다.](images/setupdomainjoin.png)

### <a name="details"></a>세부 정보

다음 입력이 필요합니다.

-   **도메인:** 가입하려는 도메인의 FQDN(정규화된 도메인 이름)입니다. 이 도메인의 보안 그룹을 사용하여 디바이스를 관리할 수 있습니다.
-   **사용자 이름:** 지정된 도메인에 가입할 수 있는 권한이 있는 계정의 사용자 이름입니다. 
-   **암호:** 계정의 암호입니다.

자격 증명이 확인된 후 보안 그룹 이름을 입력하라는 메시지가 표시됩니다. 이 입력은 필수입니다.

![보안 그룹 입력 페이지를 보여 주는 이미지입니다.](images/setupsecuritygroup-1.png)

### <a name="what-happens"></a>발생하는 동작

제공된 도메인, [Active Directory 도메인 서비스 사용 페이지](#use-active-directory) 의 계정 자격 증명 및 [이 디바이스 이름 지정](#name-this-device) 페이지의 디바이스 이름을 사용하여 Surface Hub가 도메인에 가입하려고 합니다. 가입에 성공하면 첫 실행이 계속되고 보안 그룹을 묻는 메시지가 표시됩니다. 가입에 실패하면 첫 실행이 중지되고 제공한 정보를 변경하라는 메시지가 표시됩니다.

가입에 성공하면 **보안 그룹 입력** 페이지가 표시됩니다. 이 페이지에서 **선택** 단추를 클릭하면 디바이스가 도메인에서 지정된 보안 그룹을 검색합니다. 찾으면 그룹이 확인됩니다. **마침** 을 클릭하여 첫 실행 프로세스를 완료합니다.

>[!NOTE]
>Surface Hub를 도메인에 가입한 후에는 디바이스를 초기화하지 않고 가입 취소할 수 없습니다.

 

### <a name="use-a-local-admin"></a>로컬 관리자 사용

Azure AD(Azure Active Directory) 또는 AD(Active Directory)를 사용하여 Surface Hub를 관리하지 않으려는 경우 로컬 관리자 계정을 만들어야 합니다.

![로컬 관리자의 관리자 계정 설정을 보여 주는 이미지입니다.](images/setuplocaladmin.png)

### <a name="details"></a>세부 정보

다음 입력이 필요합니다.

-   **사용자 이름:** 이 Surface Hub에 대해 만들 로컬 관리자 계정의 사용자 이름입니다.
-   **암호:** 디바이스 계정의 암호입니다.
-   **암호 다시 입력:** 이전 상자와 동일한 암호를 입력하여 확인합니다.

### <a name="what-happens"></a>발생하는 동작

이 페이지는 여기에 입력된 자격 증명을 사용하여 새 관리자 계정을 만들려고 합니다. 성공하면 첫 실행이 종료됩니다. 실패하면 다른 자격 증명을 입력하라는 메시지가 표시됩니다.

## <a name="update-the-surface-hub"></a><a href="" id="update-surface-hub"></a>Surface Hub 업데이트


>[!IMPORTANT]
>업데이트를 수행하기 전에 키의 백업이 있는지 확인하기 위해 [BitLocker 키 저장](save-bitlocker-key-surface-hub.md)을 읽어야 합니다.

 

최신 기능과 수정 사항을 가져오려면 앞의 첫 실행 단계를 모두 완료하는 즉시 Surface Hub를 업데이트해야 합니다.

1.  장치가 업데이트 서버에 액세스할 수 Windows 확인합니다. 
2.  설정을 열고 **업데이트 및 보안**, **Windows 업데이트**, **업데이트 확인**을 차례로 클릭합니다.
3.  업데이트를 사용할 수 있으면 다운로드됩니다. 다운로드가 완료된 후 **지금 업데이트** 단추를 클릭하여 업데이트를 설치합니다.
4.  업데이트가 설치된 후 화면의 지시를 따릅니다. 디바이스를 다시 시작해야 할 수도 있습니다.

 

 





