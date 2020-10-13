---
title: Surface Enterprise 관리 모드를 사용 하는 보안 Surface Dock 2 포트 (SEMM)
description: 이 문서에서는 Surface Book 3, Surface 랩탑을 3 및 Surface Pro 7을 비롯 한 호환 가능한 Surface 장치에 연결 된 경우 Surface Dock 2에 대 한 UEFI 포트 설정을 구성 하는 지침을 제공 합니다.
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: 일반적인 문제 해결, 설치 문제
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 641d023b59426582130dcfb7e0d86c6f3af456e8
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114696"
---
# Surface Enterprise 관리 모드를 사용 하는 보안 Surface Dock 2 포트 (SEMM)

## 소개

Surface 엔터프라이즈 관리 모드 (SEMM)를 사용 하면 IT 관리자가 Windows installer 구성 패키지 ()에서 UEFI 설정을 구성 하 여 Surface Dock 2 포트를 보호 하 고 관리할 수 있습니다. MSI 파일)은 회사 환경에서 호환 되는 Surface 장치에 배포 됩니다.

### 지원되는 디바이스

SEMM이 있는 Surface Dock 2 관리는 Surface Book 3, Surface 노트북 3, Surface 노트북 Go, surface pro X에 연결 된 항구에서 사용할 수 있습니다. 이러한 호환 가능한 서피스 장치를 일반적으로 **호스트 장치**라고 합니다. 패키지는 호스트 디바이스의 **인증** **또는 인증 여부에**따라 호스트 디바이스에 적용 됩니다. 구성 된 설정은 카메라와 같은 다른 기본 제공 주변 기기와 마찬가지로 Surface Dock 2를 관리 하기 위해 호스트 디바이스의 UEFI 계층에 있습니다 (IT 관리자).

>[!NOTE]
>Dock이 호환 되는 다음 장치 중 하나에 연결 된 경우에만 Surface Dock 2 포트를 관리할 수 있습니다: 가이드 3, Surface 랩톱 3 및 Surface Pro 7. UEFI 인증 된 정책 설정을 받지 않는 모든 장치는 본질적으로 인증 되지 않은 장치입니다.

### 시나리오

기업 호스트 장치에 로그인 한 승인 된 사람에 게 Surface Dock 2를 제한 하면 데이터 보호를 위한 다른 계층을 제공 합니다. 화면 도크 2를 잠그는 기능은 엄격한 보안 프로토콜과의 호환성을 유지 하면서 Dock의 기능 및 생산성 혜택을 원하는 매우 안전한 환경의 특정 고객에 게 매우 중요 합니다. Surface Dock 2와 함께 사용 되는 SEMM은 특히 보안상의 이유로 USB 포트를 잠그려고 하는 고객을 위해 열려 있는 사무실 및 공유 공간에서 특히 유용 합니다. 비디오 데모는 [Surface Dock 2의 경우 Semm](https://youtu.be/VLV19ISvq_s)을 확인 하세요.

## Surface Dock 2에 대 한 UEFI 설정 구성 및 배포

이 섹션에서는 다음 작업에 대 한 단계별 지침을 제공 합니다.

1. [**SURFACE UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703)를 설치 합니다.
1. 공개 키 인증서를 만들거나 가져옵니다.
1. 를 만듭니다. MSI 구성 패키지.
   1. 인증서를 추가 합니다.
   1. Surface Dock 2 장치에 대해 16 자리 체크 인 번호를 입력 합니다.
   1. UEFI 설정을 구성 합니다.
1. 구성 패키지를 빌드하여 대상 Surface 장치 (Surface Book 3, Surface 랩탑을 3 또는 Surface Pro 7)에 적용 합니다.

>[!NOTE]
>**임의 숫자 (0)** 는 공장에서 프로 비전 되 고 도크 아래쪽에 작은 형식으로 인쇄 되는 고유한 16 자리 16 진수 코드 식별자입니다. T e t는 대부분의 일련 번호와 다르므로 전자적으로 읽을 수 없습니다. 이는 실제로 장치에 액세스 하는 경우를 읽기만 하 여 소유권 증명을 설정 하는 것을 보장 합니다. 이 서비스는 구매 거래 중에도 얻을 수 있으며 Microsoft 인벤터리 시스템에 기록 됩니다.

### SEMM 및 Surface UEFI 구성자 설치

**SurfaceUEFI_Configurator_v2.71.139.0.msi**를 실행 하 여 semm을 설치 합니다. 독립 실행형 설치 관리자 이며, Surface Dock 2에 대 한 구성 패키지를 만들고 배포 하는 데 필요한 모든 것이 포함 되어 있습니다.

- Surface [Tools](https://www.microsoft.com/en-us/download/details.aspx?id=46703)에서 **surface UEFI 구성자** 을 다운로드 합니다.

## 공개 키 인증서 만들기

이 섹션에서는 Surface Dock 2의 포트를 관리 하는 데 필요한 인증서 만들기에 대 한 사양을 제공 합니다.

### 필수 구성 요소

이 문서에서는 타사 공급자 로부터 인증서를 획득 하거나 이미 PKI 인증서 서비스에 대 한 전문 지식이 있고 사용자가 직접 만드는 방법을 알고 있다고 가정 합니다.  한 가지 예외를 제외 하 고는 [Surface (엔터프라이즈 관리 모드)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 설명서에 설명 된 것 처럼 인증서 만들기에 대 한 일반 권장 사항을 숙지 하 고 준수 해야 합니다. 이 페이지에서 설명 하는 인증서는 **도크 인증 기관**에 대 한 30 년의 만료 약관이 필요 하며 **호스트**인증서의 경우 20 년입니다.

자세한 내용은 [인증서 서비스 아키텍처](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) 설명서를 참조 하 고 [Windows Server 2019 내부 출력](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)또는 [Windows Server 2008 PKI 및](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) Microsoft Press에서 제공 하는 인증서 보안에서 해당 장을 검토 하세요.

### 루트 및 호스트 인증서 요구 사항

구성 패키지를 만들기 전에 Surface Dock 2의 소유권을 인증 하는 공개 키 인증서를 준비 하 고 디바이스 수명 주기 동안 소유권에 대 한 이후 변경 내용을 활용 해야 합니다. 호스트 및 프로비저닝 인증서의 경우 **클라이언트 인증 eku (확장 된 키 사용) 개체 식별자 (oid)** 로 알려진 eku id를 입력 해야 합니다.

필수 EKU 값은 표 1 및 표 2에 나열 되어 있습니다.

#### 표 1. 루트 및 도크 인증서 요구 사항

|Certificate|알고리즘|설명|만료|EKU OID|
|---|---|---|---|---|
|루트 인증 기관|ECDSA_P384|-384 비트 프라임 elliptic 곡선 디지털 서명 알고리즘 (ECDSA)이 있는 루트 인증서<br>-SHA 256 키 사용:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>-CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 년|해당 없음
|Dock 인증 기관|ECC P256 곡선|-256 비트 elliptic-커브 암호화 (ECC)를 사용 하는 호스트 인증서<br>-SHA 256 키 사용:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>-Path 길이 제약 조건 = 0|20 년|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >Dock CA는. p7b 파일로 내보내야 합니다.

### 관리 인증서 요구 사항 프로 비전

각 호스트 장치에는 표 2에 나와 있는 것 처럼 doc CA와 두 개의 인증서가 있어야 합니다.

#### 표 2. 관리 인증서 요구 사항 프로 비전

|Certificate|알고리즘|설명|EKU OID|
|---|---|---|---|
|호스트 인증 인증서|ECC P256<br>SHA 256|호스트 디바이스의 id를 증명 합니다.|1.3.6.1.4.1.311.76.9.21.2|
|관리 인증서 프로 비전|ECC P256<br>SHA256|현재 도크에 설치 되어 있는 CA를 바꿀 수 있도록 허용 하 여 도크 소유권 및/또는 정책 설정을 변경할 수 있습니다.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >호스트 인증 및 프로 비전 인증서는 .pfx 파일로 내보내야 합니다.

### 구성 패키지 만들기

인증서를 얻거나 만들었으면 대상 Surface 장치에 적용 되는 MSI 구성 패키지를 빌드할 수 있습니다.

1. Surface **UEFI 구성자**을 실행 합니다.

   ![Surface UEFI 구성자 실행](images/secure-surface-dock-ports-semm-1.png)

1. **서피스 도크**를 선택 합니다.

   ![서피스 도크 선택](images/secure-surface-dock-ports-semm-2.png)

1. 인증서 페이지에서 적절 한 **인증서**를 입력 합니다.

   ![적절 한 인증서 입력](images/secure-surface-dock-ports-semm-3.png)

1. 목록에 적절 한 도크 RNs를 추가 합니다.

   >[!NOTE]
   >여러 Surface Dock 2 장치에 대 한 구성 패키지를 만들 때 각 사용자를 수동으로 입력 하는 대신 RNs 목록을 포함 하는 .csv 파일을 사용할 수 있습니다.

1. USB 데이터, 이더넷 및 오디오 포트에 대 한 정책 설정을 지정 합니다. UEFI 구성자를 사용 하 여 인증 된 사용자 (인증 된 정책) 및 인증 되지 않은 사용자 (인증 되지 않은 정책)의 정책 설정을 구성할 수 있습니다. 다음 그림에서는 인증 된 사용자에 대해 포트 액세스를 설정 하 고 인증 되지 않은 사용자의 경우 해제 하는 방법을 보여 줍니다.

   ![활성화 또는 비활성화 하려는 구성 요소를 선택 합니다.](images/secure-surface-dock-ports-semm-4.png)

   - 인증 된 사용자는에서 구성한 대로 적절 한 인증서가 설치 된 Surface 장치를 참조 합니다. 대상 장치에 적용 한 MSI 구성 패키지입니다. 이는 장치에 로그인 하는 모든 사용자 인증 된 사용자에 게 적용 됩니다. 
   - 인증 되지 않은 사용자가 다른 장치를 참조 합니다.
   - ' **재설정** '을 선택 하 여 해당 도크가 수락한 이전 구성 패키지를 모두 제거 하는 특별 한 "Reset" 패키지를 만듭니다.

1. 지정 된 대로 패키지를 만들려면 **빌드** 를 선택 합니다.

### Surface Dock 2에 구성 패키지 적용

1. Surface UEFI 구성자에서 생성 한 MSI 파일을 사용 하 여 Surface host 장치에 설치 합니다. 호환 되는 호스트 장치는 Surface Book 3, Surface 랩톱 3 또는 Surface Pro 7입니다.
1. 호스트 장치를 Surface Dock 2에 연결 합니다. Dock UEFI 정책 설정이 적용 되는 경우 연결 합니다.

## Surface 앱을 사용 하 여 관리 상태 확인

구성 패키지를 적용 한 후에는 모든 Surface 장치에 기본적으로 설치 되는 Surface 앱에서 직접 도크의 결과 정책 상태를 빠르게 확인할 수 있습니다. Surface 앱이 장치에 없으면 Microsoft Store에서 다운로드 하 여 설치할 수 있습니다.

### 테스트 시나리오

목적: 인증 된 사용자만 포트에 액세스할 수 있도록 정책 설정을 구성 합니다.

1. 인증 된 사용자에 대 한 모든 포트를 설정 하 고 인증 되지 않은 사용자에 대해 해제 합니다.

   ![인증 된 사용자에 대해 포트 사용](images/secure-surface-dock-ports-semm-4.png)

1. 대상 장치에 구성 패키지를 적용 한 다음 Surface Dock 2를 연결 합니다.

1. Surface **dock을 열고** surface **dock** 을 선택 하 여 표면 도크의 결과 정책 상태를 봅니다. 정책 설정이 적용 된 경우 Surface App에서 포트를 사용할 수 있음을 나타냅니다.

   ![인증 된 사용자가 사용할 수 있는 모든 포트를 표시 하는 Surface 앱](images/secure-surface-dock-ports-semm-5.png)

1. 이제 정책 설정이 인증 되지 않은 사용자의 모든 포트를 성공적으로 해제 했는지 확인 해야 합니다. 생성 된 구성 패키지의 관리 범위 외부에 있는 Surface Dock 2를 관리 되지 않는 디바이스 (예:)에 연결 합니다.

1. **Surface 앱** 을 열고 **서피스 도크**를 선택 합니다. 결과 정책 상태는 포트가 꺼져 있음을 나타냅니다.

   ![인증 되지 않은 사용자에 대 한 포트 해제를 보여 주는 Surface 앱 ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
>장치의 소유권을 유지 하 되 모든 사용자에 게 모든 권한을 허용 하려는 경우 모든 기능이 설정 된 새 패키지를 만들 수 있습니다. 장치에 대 한 제한 및 소유권을 완전히 제거 하려면 (비관리형으로 만들려면 Surface UEFI 구성자에서 **재설정** 을 선택 하 여 대상 장치에 적용할 패키지를 만듭니다.)

축하합니다. 대상 호스트 디바이스에서 Surface Dock 2 포트를 관리 했습니다.

## 자세히 알아보기

- [Surface 엔터프라이즈 관리 모드 (SEMM) 설명서](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [인증서 서비스 아키텍처](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 내부 출력](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI 및 인증서 보안](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
