---
title: Surface 및 SEMM(Secure Surface Dock 2) 관리 모드를 Enterprise Surface Dock 2 포트
description: 이 문서에서는 Surface Book 3, Surface Laptop 3 및 Surface Pro 7을 비롯한 호환되는 Surface 디바이스에 연결된 경우 Surface Dock 2에 대한 UEFI 포트 설정을 구성하기 위한 지침을 제공합니다.
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
ms.date: 08/02/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9a98eb9bab9b0be7f225dedf00ee6cfe7944b05e
ms.sourcegitcommit: 657d0d73a51f0dd35ad60740ed523164a55d2e04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2021
ms.locfileid: "11720932"
---
# <a name="secure-surface-dock-2-ports-with-surface-enterprise-management-mode-semm"></a>Surface 및 SEMM(Secure Surface Dock 2) 관리 모드를 Enterprise Surface Dock 2 포트

## <a name="introduction"></a>소개

SURFACE Enterprise 관리 모드(SEMM)를 사용하면 IT 관리자가 회사 환경에서 호환되는 Surface 디바이스에 배포된 Windows Installer 구성 패키지(.msi 파일)에서 UEFI 설정을 구성하여 Surface Dock 2 포트를 보호하고 관리할 수 있습니다.

### <a name="supported-devices"></a>지원되는 디바이스

SEMM을 통해 Surface Dock 2를 관리하는 것은 Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Laptop Go, Surface Pro 7+, Surface Pro 7 및 Surface Pro X에 연결된 도크에 사용할 수 있습니다. 이러한 호환되는 Surface 디바이스를 일반적으로 호스트 **장치라고 합니다.** 호스트 장치가 인증되거나 인증되지 않은 경우를 **** 기준으로 패키지가 호스트 장치에 **적용됩니다.** 구성된 설정은 호스트 디바이스의 UEFI 계층에 있으므로 IT 관리자는 카메라와 같은 다른 기본 제공 주변 장치와 마찬가지로 Surface Dock 2를 관리할 수 있습니다.

>[!NOTE]
>도크가 호환되는 디바이스인 Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 중 하나에 연결되어 있는 경우 Surface Dock 2 포트를 관리할 수 있습니다. UEFI 인증 정책 설정을 받지 않는 모든 장치는 본질적으로 인증되지 않은 장치입니다.

### <a name="scenarios"></a>시나리오

Surface Dock 2를 회사 호스트 장치에 로그인한 권한이 있는 사용자로 제한하면 다른 데이터 보호 계층이 있습니다. Surface Dock 2를 잠그는 기능은 엄격한 보안 프로토콜을 준수하면서 도크의 기능과 생산성 이점을 원하는 특정 고객에게 중요합니다. Surface Dock 2에 사용되는 SEMM은 특히 보안상의 이유로 USB 포트를 잠그고자 하는 고객에게 열려 있는 사무실 및 공유 공간에서 특히 유용할 것으로 예상합니다. 비디오 데모는 [Surface Dock 2용 SEMM을 확인 합니다.](https://youtu.be/VLV19ISvq_s)

## <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>Surface Dock 2에 대한 UEFI 설정 구성 및 배포

이 섹션에서는 다음 작업에 대한 단계별 지침을 제공합니다.

1. IT용 Surface 도구에서 Surface **UEFI 구성** [도구를 설치합니다.](https://www.microsoft.com/download/details.aspx?id=46703)
1. 공개 키 인증서를 만들거나 얻습니다.
1. 구성 .msi 만들 수 있습니다.
   1. 인증서를 추가합니다.
   1. Surface Dock 2 장치의 16자리 RN 번호를 입력합니다.
   1. UEFI 설정을 구성합니다.
1. 대상 Surface 디바이스(Surface Book 3, Surface Laptop 3 또는 Surface Pro 7)에 구성 패키지를 빌드하고 적용합니다.

>[!NOTE]
>**RN(난수)은** 출하 시 프로비전되어 도킹 밑면에 작은 형식의 인쇄되는 고유한 16자리 16자리 16자리 16자리 코드 식별자입니다. RN은 전자적으로 읽을 수 없다는 점에서 대부분의 일련 번호와 다릅니다. 따라서 소유권 증명은 주로 장치에 물리적으로 액세스할 때 RN을 읽어야만 설정됩니다. 구매 거래 중에 RN을 얻을 수도 있으며 Microsoft 인벤토리 시스템에 기록됩니다.

### <a name="install-semm-and-surface-uefi-configurator"></a>SEMM 및 Surface UEFI 구성기 설치

다음을 실행하여 ** SEMM을SurfaceUEFI_Configurator_v2.83.139.0.msi.** 독립 실행형 설치 관리자로 Surface Dock 2용 구성 패키지를 만들고 배포하는 데 필요한 모든 것이 포함되어 있습니다.

- IT용 Surface 도구에서 Surface **UEFI 구성** 도구를 [다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=46703)

## <a name="create-public-key-certificates"></a>공개 키 인증서 만들기

이 섹션에서는 Surface Dock 2의 포트를 관리하는 데 필요한 인증서를 만들기 위한 사양을 제공합니다.

### <a name="prerequisites"></a>필수 구성 요소

이 문서에서는 타사 공급자로부터 인증서를 얻거나 이미 PKI 인증서 서비스에 대한 전문 지식을 가지고 있으며 자체 인증서를 만드는 방법을 알고 있는 것으로 가정합니다.  한 가지 예외를 제외하고 Surface Enterprise 관리 [모드(SEMM)](surface-enterprise-management-mode.md) 설명서에 설명된 바와 같이 인증서를 만들기 위한 일반 권장 사항을 잘 알고 따라야 합니다. 이 페이지에 설명된 인증서에는 **Dock**인증 기관의 만료 기간은 30년, 호스트 인증 인증서는 20년이 **됩니다.**

자세한 내용은 [Certificate Services Architecture](/windows/win32/seccrypto/certificate-services-architecture) 설명서를 참조하고 Windows Server [2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)또는 Windows Server [2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) available from Microsoft Press의 해당 장을 참조하십시오.

### <a name="root-and-host-certificate-requirements"></a>루트 및 호스트 인증서 요구 사항

구성 패키지를 만들기 전에 Surface Dock 2의 소유권을 인증하는 공개 키 인증서를 준비하고 장치 수명 주기 동안 소유권 변경을 촉진해야 합니다. 호스트 및 프로비저닝 인증서를 사용하려면 클라이언트 인증 **EKU(Enhanced Key Usage)** 개체 식별자(OID)라고도 하는 EKU ID를 입력해야 합니다.

필수 EKU 값은 표 1 및 표 2에 나열되어 있습니다.

#### <a name="table-1-root-and-dock-certificate-requirements"></a>표 1. 루트 및 도크 인증서 요구 사항

|Certificate|알고리즘|설명|만료|EKU OID|
|---|---|---|---|---|
|루트 인증 기관|ECDSA_P384|- ECDSA(384비트 소수 타원 곡선 디지털 서명 알고리즘)가 있는 루트 인증서<br>- SHA 256 키 사용:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>- CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30년|해당 없음
|Dock 인증 기관|ECC P256 곡선|- ECC(256비트 타원 곡선 암호화)가 있는 호스트 인증서<br>- SHA 256 키 사용:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>- 경로 길이 제약 조건 = 0|20년|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >Dock CA는 .p7b 파일로 내보내야 합니다.

### <a name="provisioning-administration-certificate-requirements"></a>프로비저닝 관리 인증서 요구 사항

각 호스트 장치에는 표 2에 표시된 두 개의 인증서와 doc CA가 있어야 합니다.

#### <a name="table-2-provisioning-administration-certificate-requirements"></a>표 2. 관리 인증서 요구 사항 프로비전

|Certificate|알고리즘|설명|EKU OID|
|---|---|---|---|
|호스트 인증 인증서|ECC P256<br>SHA 256|호스트 장치의 ID를 증명합니다.|1.3.6.1.4.1.311.76.9.21.2|
|프로비저닝 관리 인증서|ECC P256<br>SHA256|현재 도크에 설치된 CA를 교체할 수 있도록 하여 Dock 소유권 및/또는 정책 설정을 변경할 수 있습니다.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >호스트 인증 및 프로비저닝 인증서를 .pfx 파일로 내보내야 합니다.

### <a name="create-configuration-package"></a>구성 패키지 만들기

인증서를 얻거나 만들면 대상 Surface 디바이스에 적용할 .msi 구성 패키지를 빌드할 수 있습니다.

1. Surface **UEFI 구성기 를 실행합니다.**

   ![Surface UEFI 구성기 실행](images/secure-surface-dock-ports-semm-1.png)

1. **Surface Dock를 선택합니다.**

   ![Surface Dock 선택](images/secure-surface-dock-ports-semm-2.png)

1. 인증서 **페이지에**  적절한 인증서를 입력합니다. 데모 인증서는 [Surface Tools for IT(IT용 Surface 도구)](https://www.microsoft.com/download/details.aspx?id=46703): 다운로드 인증서를 다운로드하고SEMM_PowerShell.zip참조할 **수CreateSurfaceDock2Certificates.ps1. ** **** 데모 스크립트를 **실행하기 SurfaceDock2_WmiInstanceProvider** 설치해야 합니다.

   ![적절한 인증서 입력](images/secure-surface-dock-ports-semm-3.png)

1. 목록에 적절한 dock RNS를 추가합니다.

   >[!TIP]
   >여러 Surface Dock 2 장치에 대한 구성 패키지를 만들 때 각 RN을 수동으로 입력하는 대신 RN 목록이 포함된 .csv 파일을 사용할 수 있습니다.

1. USB 데이터, 이더넷 및 오디오 포트에 대한 정책 설정을 지정합니다. UEFI 구성 도구를 사용하면 인증된 사용자(인증된 정책) 및 인증되지 않은 사용자(인증되지 않은 정책)에 대한 정책 설정을 구성할 수 있습니다. 다음 그림에서는 인증된 사용자에 대해 포트 액세스가 설정되어 있으며 인증되지 않은 사용자에 대해 포트 액세스가 해제되어 있습니다.

   ![활성화하거나 비활성화할 구성 요소를 선택하십시오.](images/secure-surface-dock-ports-semm-4.png)

   - 인증된 사용자는 대상 장치에 적용한 .msi 구성 패키지에 구성된 적절한 인증서가 설치된 Surface 디바이스를 참조합니다. 디바이스에 로그인하는 인증된 사용자에게 적용됩니다.
   - 무단 사용자는 다른 모든 장치를 참조합니다.
   - 초기화 **를** 선택하여 Dock에서 수락한 이전 구성 패키지를 제거하는 특수 "초기화" 패키지를 만들 수 있습니다.

1. **빌드를** 선택하여 지정된 패키지를 만들 수 있습니다.

### <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>Surface Dock 2에 구성 패키지 적용

1. Surface .msi UEFI 구성기에서 생성한 파일로 받아 Surface 호스트 디바이스에 설치합니다. 호환 가능한 호스트 장치는 Surface Book 3, Surface Laptop 3 또는 Surface Pro 있습니다.
1. 커넥트 디바이스를 Surface Dock 2에 연결합니다. 도킹 UEFI 정책 설정이 연결될 때 적용됩니다.

## <a name="verify-managed-state-using-the-surface-app"></a>Surface App을 사용하여 관리 상태 확인

구성 패키지를 적용한 후 모든 Surface 디바이스에 기본적으로 설치되는 Surface App에서 직접 도킹의 결과 정책 상태를 빠르게 확인할 수 있습니다. Surface 앱이 장치에 없는 경우 디바이스에서 다운로드하여 설치할 수 Microsoft Store.

### <a name="test-scenario"></a>테스트 시나리오

목표: 인증된 사용자만 포트 액세스를 허용하도록 정책 설정을 구성합니다.

1. 인증된 사용자에 대한 모든 포트를 켜고 인증되지 않은 사용자에 대해 포트를 해제합니다.

   ![인증된 사용자에 대해 포트 사용](images/secure-surface-dock-ports-semm-4.png)

1. 대상 장치에 구성 패키지를 적용한 다음 Surface Dock 2를 연결합니다.

1. **Surface App을** 열고 **Surface Dock를** 선택하여 Surface Dock의 결과 정책 상태를 볼 수 있습니다. 정책 설정이 적용된 경우 Surface App은 포트를 사용할 수 있는 것으로 표시됩니다.

   ![Surface 앱에서 인증된 사용자가 모든 포트를 사용할 수 있는 것으로 표시](images/secure-surface-dock-ports-semm-5.png)

1. 이제 정책 설정이 인증되지 않은 사용자에 대한 모든 포트를 해제하는지 확인해야 합니다. 커넥트 Surface Dock 2에서 관리되지 않는 디바이스( 예: 만든 구성 패키지의 관리 범위를 벗어날 수 있는 Surface 디바이스)입니다.

1. **Surface App을 열고** **Surface Dock를 선택합니다.** 결과 정책 상태는 포트가 꺼져 있는 것을 나타냅니다.

   ![비인식 사용자에 대한 포트를 표시하는 Surface 앱 ](images/secure-surface-dock-ports-semm-6.png)

>[!TIP]
>장치의 소유권을 유지하지만 모든 사용자가 모든 액세스를 허용하려는 경우 모든 것이 켜져 있는 새 패키지를 만들 수 있습니다. 디바이스의 제한 사항과 소유권을 완전히 제거하려면(관리되지 않는) **** Surface UEFI 구성기에서 재설정을 선택하여 대상 장치에 적용할 패키지를 만드십시오.

축하합니다. 대상 호스트 디바이스에서 Surface Dock 2 포트를 성공적으로 관리했습니다.

## <a name="learn-more"></a>자세히 알아보기

- [Surface Enterprise SEMM(관리 모드) 설명서](surface-enterprise-management-mode.md)
- [인증서 서비스 아키텍처](/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI 및 인증서 보안](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
