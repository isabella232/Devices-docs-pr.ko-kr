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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834884"
---
# Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트

## 소개

> [!NOTE]
> Surface Hub 하드웨어 진단 도구의 "계정 설정" 섹션에서 정보를 수집 하지 않습니다. 입력으로 입력 된 전자 메일 및 암호는 사용자 환경 에서만 사용할 수 있으며, 수집 하거나 다른 사람에 게 전송 되지 않습니다. 로그인 정보는 응용 프로그램이 닫히거나 Surface Hub의 현재 세션을 종료할 때까지 유지 됩니다.

> [!IMPORTANT]
> * 이 응용 프로그램을 실행 하는 데 관리자 권한이 필요 하지 않습니다.
> * Microsoft에서 서비스 통화를 열기 전에 진단 결과를 로컬 관리자와 논의 해야 합니다.

### Surface Hub 하드웨어 진단

[Surface Hub 하드웨어 진단](https://www.microsoft.com/store/apps/9nblggh51f2g) 응용 프로그램은 기본적으로 이전 버전의 surface hub 시스템에 설치 되어 있지 않습니다. Microsoft Store에서 응용 프로그램을 무료로 이용할 수 있습니다. 응용 프로그램을 설치 하려면 관리자 권한이 필요 합니다.

   ![하드웨어 진단 스크린샷](images/01-diagnostic.png)

## Surface Hub 하드웨어 진단 도구 정보

Surface Hub 하드웨어 진단 도구는 사용자가 Surface Hub 장치 내의 많은 하드웨어 구성 요소를 테스트할 수 있는 탐색 하기 쉬운 도구입니다. 이 도구는 Surface Hub 디바이스 계정도 테스트 하 고 확인할 수도 있습니다. 이 문서에서는 Surface Hub 하드웨어 진단 도구 내에서 계정 설정 테스트를 사용 하는 방법에 대해 설명 합니다.

> [!NOTE]
> Surface Hub에 대 한 디바이스 계정은 테스트를 완료 하기 전에 만들어야 합니다. Surface Hub 관리자 가이드는 온-프레미스, 온라인 (Office365) 또는 하이브리드 디바이스 계정을 만드는 데 도움이 되는 지침 및 PowerShell 스크립트를 제공 합니다. 자세한 내용은 가이드의 [디바이스 계정 만들기 및 테스트 (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) 항목을 참조 하세요.

### 디바이스 계정 테스트 프로세스

1. **모든 앱**으로 이동한 다음 Surface Hub 하드웨어 진단 응용 프로그램을 찾습니다.

    ![모든 앱 스크린샷](images/02-all-apps.png)

1. 응용 프로그램이 시작 되 면 **시작** 페이지에서 허브를 테스트 하는 이유를 설명 하는 텍스트 창을 제공 합니다. 이 노트는 테스트를 끝맺을 때 진단 결과와 함께 USB에 저장 될 수 있습니다. 메모를 모두 입력 했으면 **계속** 단추를 선택 합니다.

    ![시작 스크린샷](images/03-welcome.png)

1. 다음 화면에는 Surface Hub 구성 요소의 전체 또는 일부를 테스트 하는 옵션이 있습니다. 장치 계정 테스트를 시작 하려면 **테스트 결과** 아이콘을 선택 합니다.

    ![테스트 결과 스크린샷](images/04-test-results-1.png)

    ![테스트 결과 스크린샷](images/05-test-results-2.png)

1. **계정 설정을**선택 합니다.  

    ![계정 설정 스크린샷](images/06-account-settings.png)

    계정 설정 화면은 장치 계정을 테스트 하는 데 사용 됩니다.

    ![계정 설정 세부 정보 스크린샷](images/07-account-settings-details.png)

1. 장치 계정의 전자 메일 주소를 입력 합니다. 비밀 번호는 선택 사항 이지만 권장 되는 방법입니다. 계속할 준비가 되 면 **테스트 계정** 단추를 선택 합니다.

    ![테스트 계정 스크린샷](images/08-test-account.png)

1. 테스트가 완료 되 면 4 개의 테스트 영역에 대 한 결과를 검토 합니다. 각 항목 옆에 있는 더하기 또는 빼기 기호를 선택 하 여 각 구역을 확장 하거나 축소할 수 있습니다.

    **네트워크**

    ![네트워크 스크린샷](images/09-network.png)

    **환경**

    ![환경 스크린샷](images/10-environment.png)

    **인증서**

    ![인증서 스크린샷](images/11-certificates.png)

    **신뢰 모델**

    ![신뢰 모델 스크린샷](images/12-trust-model.png)

## 부록

### 필드 메시지 및 해결 방법

#### 네트워크

필드 |성공 |실패 |설명 |참고자료
|------|------|------|------|------|
인터넷 연결 |장치에 인터넷 연결이 있습니다. |장치에 인터넷이 연결 되어 있지 않습니다. |프록시 연결을 포함 하 여 인터넷 연결을 확인 합니다. |
HTTP 버전 |1.1 |1.0 |HTTP 1.0이 발견 되 면 WU 및 스토어에서 문제가 발생 합니다. |
직접 인터넷 연결 |디바이스에 프록시 구성 디바이스에 프록시가 구성 되어 있지 않음 |해당 없음 |나타낼. 디바이스가 프록시 뒤에 있습니까? |
프록시 주소 | | |구성 된 경우 프록시 주소를 반환 합니다. |
프록시 인증 |프록시에는 인증이 필요 하지 않습니다. |프록시에 프록시 인증이 필요 합니다. |사용자가 Edge에서 열려 있는 세션을 이미 사용 중이 고 프록시를 통해 인증 된 경우 결과가 가양성 일 수 있습니다. |
프록시 인증 형식 | | |프록시 인증을 사용 하는 경우 프록시에서 알린 인증 방법을 반환 합니다.  |

#### 환경

필드 |성공 |실패 |설명 |참고자료
|------|------|------|------|------|
SIP 도메인 | | |나타낼.  |
Skype 환경 |비즈니스용 skype Online, 비즈니스용 Skype OnPrem, 비즈니스용 Skype 하이브리드 |나타낼. |검색 된 환경 유형입니다. 참고: 하이브리드은 암호를 입력 한 경우에만 검색할 수 있습니다.
LyncDiscover 검색 | | |나타낼. DNS 결과를 표시 하는 ldisc |
LyncDiscover 검색 | | |나타낼. 환경에서 LyncDiscover을 수행 하는 데 사용 되는 URL을 표시 합니다.|
LyncDiscover |연결 성공 |연결 실패 |웹 서비스에서 받은 응답입니다. |
SIP 풀 호스트 이름 | | |나타낼. LyncDiscover에서 검색 된 SIP 풀 이름 표시 |

#### 인증서 (온-프레미스 하이브리드에만 해당)

인증서 검색

필드 |성공 |실패 |설명 |참고자료
|------|------|------|------|------|
인증서 CN 검색 | | |나타낼. LD cert 일반 이름 표시 |
인증서 CA를 확인 하는 ldisc | | |나타낼. LD Cert CA를 표시 합니다. |
인증서 루트 CA를 확인 하는 LyncDiscover | | |나타낼. 사용 가능한 경우 LD Cert 루트 CA를 표시 합니다. |
LD 개 신뢰 상태 |인증서를 신뢰할 수 있습니다. |인증서를 신뢰할 수 없습니다. 루트 CA를 추가 하세요. |로컬 인증서 저장소에 대해 인증서를 확인 합니다. 컴퓨터에서 인증서를 신뢰 하는 경우 양수를 반환 합니다.|[PowerShell을 사용 하 여 비즈니스용 Skype 인증서 다운로드 및 배포](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Surface Hub 프로비저닝 패키지에 지원 되는 항목](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP 풀 인증

필드 |성공 |실패 |설명 |참고자료
|------|------|------|------|------|
SIP 풀 Cert CN | | |콘텐츠의 |
SIP 풀 Cert CA | | |콘텐츠의 |
SIP 풀 신뢰 상태 |인증서를 신뢰할 수 있습니다. |인증서를 신뢰할 수 없습니다. 루트 CA를 추가 하세요. |로컬 인증서 저장소에 대해 인증서를 확인 하 고 장치가 인증서를 신뢰 하는 경우 양수를 반환 합니다. |
SIP 풀 인증서 루트 CA | | |방법. 가능한 경우 SIP 풀 인증서 루트 CA를 표시 합니다. |

#### 신뢰 모델 (온-프레미스 하이브리드에만 해당)

필드 |성공 |실패 |설명 |참고자료
|------|------|------|------|------|
신뢰 모델 상태 |신뢰 모델 문제가 감지 되지 않았습니다. |SIP 도메인 및 서버 도메인이 다름 다음 도메인을 추가 하세요. |보안 모델 문제에 대 한 LD FQDN/LD 서버 이름/풀 서버 이름을 확인 합니다. 
도메인 이름 | | |SFB에 연결 하기 위해 추가 해야 하는 도메인 목록을 반환 합니다. |
