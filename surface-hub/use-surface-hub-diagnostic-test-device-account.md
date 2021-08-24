---
title: Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트
description: Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: 접근성 설정, 설정 앱, 접근성
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 0a9914f5c07a33306cc8a3ef87de85df47a05a20
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911436"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a>Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트

## <a name="introduction"></a>소개

> [!NOTE]
> 하드웨어 설정 도구의 "계정 Surface Hub" 섹션은 정보를 수집하지 않습니다. 입력으로 입력된 전자 메일 및 암호는 사용자 환경에서 직접만 사용되고 수집되거나 다른 누구에게도 전송되지 않습니다. 로그인 정보는 응용 프로그램이 닫히거나 응용 프로그램에서 현재 세션을 종료할 때까지만 Surface Hub.

> [!IMPORTANT]
> * 이 응용 프로그램을 실행하려면 관리자 권한이 필요하지 않습니다.
> * Microsoft에서 서비스 호출을 열기 전에 진단 결과를 로컬 관리자와 논의해야 합니다.

### <a name="surface-hub-hardware-diagnostic"></a>Surface Hub 하드웨어 진단

기본적으로 Surface Hub [](https://www.microsoft.com/store/apps/9nblggh51f2g) 하드웨어 진단 응용 프로그램은 이전 버전의 Surface Hub 설치되지 않습니다. 응용 프로그램은 응용 프로그램에서 무료로 Microsoft Store. 응용 프로그램을 설치하려면 관리자 권한이 필요합니다.

   ![하드웨어 진단 스크린샷.](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a>하드웨어 Surface Hub 도구 정보

Surface Hub 하드웨어 진단 도구는 탐색하기 쉬운 도구로, 사용자가 장치 내에서 여러 하드웨어 구성 요소를 테스트할 Surface Hub 있습니다. 또한 이 도구는 장치 계정을 테스트하고 Surface Hub 수 있습니다. 이 문서에서는 하드웨어 진단 도구 내에서 계정 설정 테스트하는 Surface Hub 설명합니다.

> [!NOTE]
> 테스트가 Surface Hub 전에 디바이스 계정이 만들어야 합니다. Surface Hub 관리자 가이드에서는 온라인(Office365) 또는 하이브리드 장치 계정을 만드는 데 도움이 되는 지침과 PowerShell 스크립트를 제공합니다. 자세한 내용은 가이드의 [](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) 장치 계정 만들기 및 테스트(Surface Hub) 항목으로 이동하세요.

### <a name="device-account-testing-process"></a>디바이스 계정 테스트 프로세스

1. 모든 **앱으로 이동한**다음 하드웨어 Surface Hub 응용 프로그램을 찾습니다.

    ![모든 앱의 스크린샷.](images/02-all-apps.png)

1. 응용 프로그램이 시작되면 시작 **페이지에서는** 허브를 테스트하는 이유를 문서화하는 텍스트 창을 제공합니다. 이 메모는 테스트가 끝날 때 진단 결과와 함께 USB에 저장할 수 있습니다. 메모 입력을 마친 후 계속 **단추를** 선택합니다.

    >[!NOTE]
    >진단 결과를 저장하는 경우 기본 경로를 변경하거나 하위 경로를 선택하지 않습니다. 파일은 나중에 파일 탐색기 앱을 통해 복사할 수 있습니다.

    ![환영 스크린샷.](images/03-welcome.png)

1. 다음 화면에서는 모든 구성 요소 또는 일부를 테스트하는 Surface Hub 있습니다. 장치 계정 테스트를 시작하려면 테스트 결과 **아이콘을** 선택합니다.

    ![테스트 옵션 스크린샷.](images/04-test-results-1.png)

    ![테스트 결과 스크린샷.](images/05-test-results-2.png)

1. 계정 **설정.**  

    ![계정 계정의 설정.](images/06-account-settings.png)

    계정 설정 디바이스 계정을 테스트하는 데 사용됩니다.

    ![Screenshot of Account 설정 Details.](images/07-account-settings-details.png)

1. 디바이스 계정의 전자 메일 주소를 입력합니다. 암호는 선택 사항이지만 권장됩니다. 계속할 준비가 **되면** 계정 테스트 단추를 선택합니다.

    ![테스트 계정의 스크린샷.](images/08-test-account.png)

1. 테스트가 완료되면 네 가지 테스트 영역에 대한 결과를 검토합니다. 각 항목 옆에 있는 Plus 또는 Minus 기호를 선택하여 각 섹션을 확장하거나 축소할 수 있습니다.

    **네트워크**

    ![네트워크 스크린샷.](images/09-network.png)

    **환경**

    ![환경 스크린샷.](images/10-environment.png)

    **인증서**

    ![인증서 스크린샷.](images/11-certificates.png)

    **트러스트 모델**

    ![트러스트 모델 스크린샷.](images/12-trust-model.png)

## <a name="appendix"></a>부록

### <a name="field-messages-and-resolution"></a>필드 메시지 및 확인

#### <a name="network"></a>네트워크

필드 |성공 |실패 |설명 |참조
|------|------|------|------|------|
인터넷 연결 |디바이스에 인터넷 연결이 있습니다. |장치가 인터넷에 연결되지 않습니다. |프록시 연결을 비롯한 인터넷 연결 확인 |
HTTP 버전 |1.1 |1.0 |HTTP 1.0이 발견된 경우 WU 및 스토어에서 문제가 발생하게 됩니다. |
직접 인터넷 연결 |장치에 프록시가 구성되어 있는 장치에 프록시가 구성되지 않은 경우 |해당 없음 |정보. 장치가 프록시 뒤에 있나요? |
프록시 주소 | | |구성된 경우 프록시 주소를 반환합니다. |
프록시 인증 |프록시에는 인증이 필요하지 않습니다. |프록시를 사용하려면 프록시 인증 필요 |사용자가 Edge에서 이미 열려 있는 세션을 이미 있으며 프록시를 통해 인증한 경우 가극적일 수 있습니다. |
프록시 인증 유형 | | |프록시 인증을 사용하는 경우 프록시에서 보급하는 인증 방법을 반환합니다.  |

#### <a name="environment"></a>환경

필드 |성공 |실패 |설명 |참조
|------|------|------|------|------|
SIP 도메인 | | |정보.  |
Skype 환경 |비즈니스용 Skype Online, 비즈니스용 Skype OnPrem, 비즈니스 하이브리드용 Skype |정보. |검색된 환경 유형 참고: 암호를 입력한 경우 하이브리드만 검색할 수 있습니다.
LyncDiscover FQDN | | |정보. LyncDiscover DNS 결과 표시 |
LyncDiscover URI | | |정보. 환경에서 LyncDiscover를 수행하는 데 사용되는 URL을 표시됩니다.|
LyncDiscover |연결 성공 |연결이 실패했습니다. |LyncDiscover 웹 서비스의 응답입니다. |
SIP 풀 호스트 이름 | | |정보. LyncDiscover에서 검색된 SIP 풀 이름 표시 |

#### <a name="certificates-in-premises-hybrid-only"></a>인증서(프레미스 하이브리드에만 해당)

LyncDiscover 인증서

필드 |성공 |실패 |설명 |참조
|------|------|------|------|------|
LyncDiscover Cert CN | | |정보. LD 인증 일반 이름 표시 |
LyncDiscover Cert CA | | |정보. LD Cert CA 표시 |
LyncDiscover Cert Root CA | | |정보. 사용 가능한 경우 LD Cert Root CA를 표시됩니다. |
LD 트러스트 상태 |인증서가 신뢰할 수 있습니다. |인증서를 신뢰할 수 없습니다. 루트 CA를 추가하십시오. |로컬 인증서 저장소에 대해 인증서를 검증합니다. 컴퓨터는 인증서를 신뢰하는 경우 양수입니다.|[PowerShell을 비즈니스용 Skype 인증서 다운로드 및 배포](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [프로비저닝 패키지에 Surface Hub 지원되는 항목](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP 풀 인증

필드 |성공 |실패 |설명 |참조
|------|------|------|------|------|
SIP 풀 Cert CN | | |(콘텐츠) |
SIP 풀 Cert CA | | |(콘텐츠) |
SIP 풀 트러스트 상태 |인증서가 신뢰할 수 있습니다. |인증서를 신뢰할 수 없습니다. 루트 CA를 추가하십시오. |로컬 인증서 저장소에 대해 인증서를 확인하고 장치가 인증서를 신뢰하는 경우 양의 인증서를 반환합니다. |
SIP 풀 인증 루트 CA | | |정보. SIP 풀 인증 루트 CA(사용 가능한 경우)를 표시합니다. |

#### <a name="trust-model-on-premises-hybrid-only"></a>트러스트 모델(사내 하이브리드에만 해당)

필드 |성공 |실패 |설명 |참조
|------|------|------|------|------|
트러스트 모델 상태 |신뢰 모델 문제가 검색되지 않습니다. |SIP 도메인과 서버 도메인이 서로 다르면 다음 도메인을 추가하십시오. |신뢰 모델 문제의 LD FQDN/ LD 서버 이름/ 풀 서버 이름을 검사합니다. 
Domain Name(s) | | |SFB에서 연결할 수 있는 도메인 목록을 반환합니다. |
