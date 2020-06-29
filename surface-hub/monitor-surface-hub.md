---
title: Microsoft Surface Hub 모니터링
description: Microsoft Surface Hub 디바이스 모니터링은 Microsoft OMS(Operations Management Suite)를 통해 사용하도록 설정할 수 있습니다.
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 모니터링, Microsoft Operations Management Suite, OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836180"
---
# Microsoft Surface Hub 모니터링

Microsoft Surface Hub 디바이스 모니터링은 Microsoft OMS(Operations Management Suite)를 통해 사용하도록 설정할 수 있습니다. [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138)는 Surface Hub를 포함하여 전체 IT 인프라의 관리 및 보호를 도와주는 Microsoft IT 관리 솔루션입니다.


Surface Hub는 Log Analytics 솔루션으로 제공되며 이를 통해 모든 Surface Hub에서 사용 및 안정성 데이터를 수집하고 확인할 수 있습니다. Surface Hub 솔루션을 사용하여 다음을 수행할 수 있습니다.
- Surface Hub를 인벤토리에 포함합니다.
- Skype 모임, 유선 및 무선 보호, Surface Hub의 앱에 대한 사용 및 안정성 데이터 스냅숏을 봅니다.
- Surface Hub에서 소프트웨어 또는 하드웨어 문제를 보고할 경우 빠르게 응답하기 위한 사용자 지정 경고를 만듭니다.

## Operations Management Suite에 Surface Hub 추가

1. **OMS(Operations Management Suite)에 로그인합니다**. Microsoft 계정이나 회사 또는 학교 계정을 사용하여 작업 영역을 만들 수 있습니다. 회사에서 이미 Azure AD(Azure Active Directory)를 사용 중일 경우 OMS에 로그인할 때 회사 또는 학교 계정을 사용합니다. 회사 또는 학교 계정을 사용하면 OMS에서 사용 권한을 관리할 때 Azure AD의 ID를 사용할 수 있습니다.
2. **새 OMS 작업 영역을 만듭니다**. 작업 영역의 이름을 입력하고, 작업 영역 지역을 선택하고, 이 작업 영역과 연결할 메일 주소를 입력합니다. **만들기**를 선택합니다.
3. **Azure 구독을 작업 영역에 연결합니다**. 조직에 기존 Azure 구독이 있는 경우 이를 작업 영역에 연결할 수 있습니다. 조직의 Azure 관리자에게 액세스 권한을 요청해야 할 수 있습니다.

    > [!NOTE] 
    > 조직에 Azure 구독이 없다면 새 구독을 만들거나 목록에서 기본 OMS Azure 구독을 선택합니다. 작업 영역이 열립니다.

4. **Surface Hub 솔루션을 추가합니다**. 솔루션 갤러리의 갤러리에서 **Surface Hub** 타일을 선택하고 솔루션 세부 정보 페이지에서 **추가**를 선택합니다. 이제 솔루션이 작업 영역에 표시됩니다.

## Surface Hub 대시보드 사용
OMS 작업 영역의 **개요** 페이지에서 Surface Hub 타일을 클릭하면 Surface Hub 대시보드가 표시됩니다. 대시보드를 사용하여 Surface Hub에서 사용 및 안정성 데이터 스냅숏을 확인할 수 있습니다. 대시보드에서 각 보기를 클릭하여 세부 데이터를 확인하고 원하는 대로 쿼리를 수정하고 경고를 만들 수 있습니다.

> [!NOTE]
> 이러한 보기는 대부분 지난 30일 간의 데이터를 표시하지만 구독의 데이터 보존 정책이 적용되지 않습니다.

**활성 Surface Hub**

이 보기를 사용하여 모든 Surface Hub의 인벤토리를 가져올 수 있습니다. OMS에 연결되면 각 Surface Hub가 주기적으로 "하트비트" 이벤트를 서버에 보냅니다. 이 보기는 지난 24시간 내에 하트비트를 보고한 Surface Hub를 표시합니다.

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**무선 프로젝션**

이 보기를 사용하여 지난 30일 동안의 무선 프로젝트에 대한 사용 및 안정성 데이터를 확인할 수 있습니다. 그래프에는 조직의 구성원이 이 기능을 사용 중인지 나타내는 모든 Surface Hub에 대한 총 무선 연결 수가 표시됩니다. 이 수가 작은 경우에는 조직의 구성원이 Surface Hub에 무선으로 연결하는 방법을 알아볼 수 있도록 교육을 제공해야 함을 제한하는 것일 수 있습니다.
 
또한 그래프에는 성공한 연결과 실패한 연결의 분석이 표시됩니다. 실패한 연결 수가 큰 경우에는 디바이스가 Miracast를 통해 무선 프로젝션을 제대로 지원하지 않는 것일 수 있습니다. 최고 성능을 위해 디바이스에서 WDI Wi-Fi 드라이버와 WDDM 2.0 그래픽 드라이버를 실행하는 것이 좋습니다. 세부 정보 보기를 사용하여 무선 프로젝션 문제가 특정 디바이스에서 공통적인지 알아보세요.
 
연결에 실패할 경우 사용자가 Windows 노트북이나 휴대폰을 사용 중이면 다음을 수행할 수도 있습니다.
- **설정** > **장치** > **연결된 장치**에서 연결된 장치를 제거하고 다시 연결합니다.
- 디바이스를 다시 부팅합니다.
 
**유선 프로젝션**

이 보기를 사용하여 지난 30일 동안의 유선 프로젝트에 대한 사용 및 안정성 데이터를 확인할 수 있습니다. 그래프에 표시된 실패한 연결 수가 클 경우 오디오-비디오 파이프라인에 연결 문제가 있을 수 있습니다. 예를 들어 HDMI 리피터나 공간 중심 제어 패널을 사용할 경우 이를 다시 시작해야 할 수 있습니다.
 
**응용 프로그램 사용**

이 보기를 사용하여 지난 30일 동안 Surface Hub에 있는 앱의 사용 데이터를 확인할 수 있습니다. 비즈니스용 Skype를 제외하고 데이터는 Surface Hub에서 앱이 시작될 때 발생합니다. 이 보기를 통해 조직에서 어떤 Surface Hub 앱이 가장 중요한지 이해할 수 있습니다. 환경에 새 기간 업무 앱을 배포할 경우 이를 통해 앱이 사용되는 빈도를 이해할 수도 있습니다.
 
**응용 프로그램 크래시**

이 보기를 사용하여 지난 30일 동안 Surface Hub에 있는 앱의 안정성 데이터를 확인할 수 있습니다. 데이터는 Surface Hub에서 앱 작동이 중단될 때 발생합니다. 이 보기를 통해 제대로 작동하지 않는 Windows 제공 및 기간 업무 앱을 검색하고 이를 앱 개발자에게 알릴 수 있습니다.
 
**샘플 쿼리**

이 보기를 사용하여 권장 쿼리 집합에 따라 사용자 지정 경고를 만들 수 있습니다. Surface Hub에서 소프트웨어 또는 하드웨어 문제를 보고할 경우 경고를 통해 빠르게 응답할 수 있습니다. 자세한 내용은 [샘플 쿼리를 사용하여 경고 설정](#set-up-alerts-with-sample-queries)을 참조하세요.

## 샘플 쿼리를 사용하여 경고 설정

Surface Hub에서 소프트웨어 또는 하드웨어 문제를 보고할 경우 경고를 사용하여 빠르게 응답할 수 있습니다. 경고 규칙은 일정에 따라 로그 검색을 자동으로 실행하고 결과가 특정 기준과 일치할 경우 하나 이상의 작업을 실행합니다. 자세한 내용은 [Log Analytics의 경고](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/)를 참조하세요.
 
Surface Hub Log Analytics 솔루션에는 적절한 경고를 설정하고 발생할 수 있는 문제의 해결 방법을 이해하도록 돕는 일련의 샘플 쿼리가 함께 제공됩니다. 샘플 쿼리를 시작점으로 모니터링 및 지원 전략을 계획할 수 있습니다.

이 표에서는 Surface Hub의 샘플 쿼리에 대해 설명합니다.

| 경고 유형 | 영향 | 권장되는 수정 | 세부 정보 |
| ---------- | ------ | ----------------------- | ------- |
| 소프트웨어   | 오류  | **디바이스를 다시 시작합니다**. <br> 수동으로 다시 시작하거나 [Reboot configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx)(구성 서비스 공급자 다시 시작)를 사용하여 다시 시작합니다. <br> 조직의 구성원에게 미치는 영향을 최소화하려면 모임 사이에 이 작업을 수행하는 것이 좋습니다. | 트리거 조건: <br> - 셸, 프로젝션 또는 Skype와 같은 Surface Hub 운영 체제의 핵심 프로세스가 작동이 중단되거나 응답하지 않습니다. <br> - 지난 24시간 내에 디바이스가 하트비트를 보고하지 않았습니다. 이는 네트워크 연결 문제가 있거나, 네트워크 관련 하드웨어 오류가 있거나, 진단 데이터 보고 시스템에 오류가 있음을 나타냅니다. |
| 소프트웨어   | 오류  | **Exchange 서비스를 확인합니다**. <br> 다음을 확인합니다. <br> - 서비스가 사용 가능한지 <br> - 디바이스 계정 암호가 최신 상태인지 – 자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.| 디바이스 일정을 Exchange와 동기화하는 중 오류가 발생한 경우 트리거됩니다. |
| 소프트웨어   | 오류  | **비즈니스용 Skype 서비스를 확인합니다**. <br> 다음을 확인합니다. <br> - 서비스가 사용 가능한지 <br> - 디바이스 계정 암호가 최신 상태인지 – 자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요. <br> - 비즈니스용 Skype의 도메인 이름이 제대로 구성되었는지 - [도메인 이름 구성](use-fully-qualified-domain-name-surface-hub.md)을 참조하세요. | Skype가 로그인에 실패하면 트리거됩니다. |
| 소프트웨어   | 오류  | **디바이스를 초기화합니다**. <br> 이 작업에는 다소 시간이 걸리므로 디바이스를 오프라인으로 전환해야 합니다. <br> 자세한 내용은 [디바이스 초기화](device-reset-surface-hub.md)를 참조하세요.| 세션 종료 시 사용자 및 앱 데이터를 정리할 때 오류가 발생하면 트리거됩니다. 이 작업이 반복해서 실패하면 사용자 데이터를 보호하기 위해 디바이스가 잠깁니다. 계속하려면 디바이스를 초기화해야 합니다. |
| 하드웨어   | 경고 | **없음**. 기능에 대한 무시할 수 있는 영향을 나타냅니다.| 다음 하드웨어 구성 요소에 오류가 있으면 트리거됩니다. <br> - 가상 펜 슬롯 <br> - NFC 드라이버 <br> - USB 허브 드라이버 <br> - Bluetooth 드라이버 <br> - 근접 센서 <br> - 그래픽 성능(비디오 카드 드라이버) <br> - 일치하지 않는 하드 드라이브 <br> - 검색되는 키보드/마우스 없음 |
| 하드웨어   | 오류 | **Microsoft 지원에 문의합니다**. <br> 핵심 기능(예: Skype, 프로젝션, 터치 및 인터넷 연결)에 대한 영향을 나타냅니다. <br> **참고** 하트비트를 비롯한 일부 이벤트에는 지원 부서에 문의할 때 사용할 수 있는 디바이스의 일련 번호가 포함됩니다.| 다음 하드웨어 구성 요소에 오류가 있으면 트리거됩니다. <br> **Skype에 영향을 주는 구성 요소**: <br> - 스피커 드라이버 <br> - 마이크 드라이버 <br> - 카메라 드라이버 <br> **유선 및 무선 프로젝션에 영향을 주는 구성 요소**: <br> - 유선 touchback 드라이버 <br> - 유선 수집 드라이버 <br> - 무선 어댑터 드라이버 <br> - Wi-Fi Direct 오류 <br> **기타 구성 요소**: <br> - 터치 디지타이저 드라이버 <br> - 네트워크 어댑터 오류(OMS에 보고되지 않음)|

**경고를 설정하려면**
1. Surface Hub 솔루션에서 샘플 쿼리 중 하나를 선택합니다.
2. 원하는 대로 쿼리를 수정합니다. 자세한 내용은 Log Analytics 검색 참조를 참조하세요.
3. 페이지 맨 위에서 **경고**를 클릭하여 **경고 규칙 추가** 화면을 엽니다. 경고 구성 옵션에 대한 자세한 내용은 [Log Analytics의 경고](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/)를 참조하세요.
4. **저장**을 클릭하여 경고 규칙을 완료합니다. 실행이 즉시 시작됩니다.

## Surface Hub 등록

Surface Hub를 OMS 서비스에 연결하고 등록하려면 URL 및 도메인의 포트 번호에 대한 액세스 권한이 있어야 합니다. 이 표에는 OMS에 필요한 포트가 나와 있습니다. 자세한 내용은 [Log Analytics에서 프록시 및 방화벽 설정 구성](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/)을 참조하세요.

>[!NOTE]
>현재 Surface Hub는 OMS 서비스와 통신을 위한 프록시 서버의 사용을 지원하지 않습니다.

| Agent 리소스              | 포트 | HTTPS 검사 무시 여부 |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | 예 |
| *.oms.opinsights.azure.com  | 443   | 예 |
| *.blob.core.windows.net     | 443   | 예 |
| ods.systemcenteradvisor.com | 443   | 아니요  |

디바이스를 OMS에 연결하는 데 사용되는 Microsoft Monitoring Agent는 Surface Hub 운영 체제에 통합되므로 Surface Hub를 OMS에 연결하기 위해 추가 클라이언트를 설치할 필요가 없습니다.
 
OMS 작업 영역이 설정된 후 다음과 같은 여러 가지 방법으로 Surface Hub 디바이스를 등록할 수 있습니다.
- [설정 앱](#enroll-using-the-settings-app)
- [프로비저닝 패키지](#enroll-using-a-provisioning-package)
- [MDM 공급자](#enroll-using-a-mdm-provider)(예: Microsoft Intune 및 Configuration Manager)
 
OMS 작업 영역의 작업 영역 ID 및 기본 키가 필요합니다. 이러한 항목은 OMS 포털에서 얻을 수 있습니다.
 
### 설정 앱을 사용하여 등록

**설정 앱을 사용하여 등록하려면**

1. Surface Hub에서 **설정**을 시작합니다.
2. 메시지가 표시되면 디바이스 관리자 자격 증명을 입력합니다.
3. **이 장치**를 선택하고 **장치 관리**로 이동합니다.
4. **모니터링**에서 **OMS 설정 구성**을 선택합니다.
5. OMS 설정 대화 상자에서 **모니터링 사용**을 선택합니다.
6. OMS 작업 영역의 작업 영역 ID 및 기본 키를 입력합니다. 이러한 항목은 OMS 포털에서 얻을 수 있습니다.
7. **확인**을 클릭하여 구성을 완료합니다.
 
OMS 구성이 디바이스에 적용되었는지 여부를 알리는 확인 대화 상자가 나타납니다. 적용된 경우 디바이스가 데이터를 OMS로 보내기 시작합니다.

### 프로비저닝 패키지를 사용하여 등록
프로비저닝 패키지를 사용하여 Surface Hub를 등록할 수 있습니다. 자세한 내용은 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.
 
### MDM 공급자를 사용하여 등록
SurfaceHub CSP를 사용하여 Surface Hub를 OMS에 등록할 수 있습니다. Intune 및 Configuration Manager에서는 Surface Hub에 대한 정책 템플릿을 만드는 데 도움되는 기본 제공 환경을 제공합니다. 자세한 내용은 [MDM 공급자 설정 관리(Surface Hub)](manage-settings-with-mdm-for-surface-hub.md)를 참조하세요.

## 관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)

 

 





