---
title: Surface (기업 엔터프라이즈 관리 모드)
description: Surface UEFI를 사용 하는 Surface 디바이스의이 기능을 사용 하 여 조직 내에서 펌웨어 설정을 보호 하 고 관리 하는 방법을 알아봅니다.
keywords: uefi, 구성, 펌웨어, 보안, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 05/26/2020
ms.openlocfilehash: 116aeb6d1d92f387efa34319f7852febda729207
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835607"
---
# Microsoft Surface Enterprise 관리 모드

Microsoft Surface Enterprise 관리 모드 (SEMM)는 조직 내에서 펌웨어 설정을 보호 하 고 관리 하는 데 사용할 수 있는 surface UEFI를 사용 하는 Surface 디바이스의 기능입니다. SEMM을 사용 하면 IT 전문가는 UEFI 설정의 구성을 준비 하 고 Surface 장치에 설치할 수 있습니다. SEMM은 UEFI 설정을 구성 하는 기능 외에도 인증서를 사용 하 여 무단 무단 변경 또는 제거 로부터 구성을 보호 합니다.

>[!NOTE]
>SEMM은 Surface UEFI 펌웨어가 있는 디바이스 에서만 사용할 수 있습니다. 여기에는 인텔 프로세서와 함께 Surface Pro 7, Surface Pro X 및 Surface 랩탑 3 상업용 Sku를 비롯 한 대부분의 Surface 장치가 포함 됩니다. 15 "Surface 랩탑 3 SKU (AMD 프로세서 포함)에서 지원 되지 않습니다 (정품 SKU로 서만 제공). 

Surface 디바이스는 SEMM로 구성 되 고 SEMM 인증서로 보호 되는 경우 SEMM로 *등록* 된 것으로 간주 됩니다. SEMM 인증서가 제거 되 고 UEFI 설정의 제어가 장치 사용자에 게 반환 되는 경우 Surface 디바이스는 *unenrolled* 로 간주 됩니다.

SEMM 및 등록 된 Surface 디바이스를 관리 하는 데 사용할 수 있는 두 가지 관리 옵션으로 독립 실행형 도구 또는 Microsoft 끝점 구성 관리자와의 통합이 있습니다. 이 문서에서는 Microsoft Surface UEFI 구성자 이라고 하는 모든 독립 실행형 도구에 대해 설명 합니다. Microsoft Endpoint Configuration Manager에서 SEMM을 관리 하는 방법에 대 한 자세한 내용은 [Microsoft Endpoint Configuration manager를 사용 하 여 디바이스 관리 (SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm))를 참조 하세요.


## Microsoft Surface UEFI 구성자

그림 1에 나와 있는 것 처럼 SEMM의 기본 작업 영역은 Microsoft Surface UEFI 구성자입니다. Microsoft Surface UEFI 구성자는 Surface 장치에서 SEMM을 등록, 구성 및 등록 해제 하는 데 사용 되는 Windows Installer (.msi) 패키지 또는 WinPE 이미지를 만드는 데 사용 되는 도구입니다. 이러한 패키지에는 UEFI에 대 한 설정을 지정 하는 구성 파일이 포함 되어 있습니다. SEMM 패키지에는 또한 펌웨어에서 설치 및 저장 되며 UEFI 설정이 적용 되기 전에 구성 파일의 서명을 확인 하는 데 사용 되는 인증서가 포함 되어 있습니다.

>[!NOTE]
>이제 Surface UEFI 구성자 및 SEMM을 사용 하 여 Surface Dock 2의 포트를 관리할 수 있습니다. 자세한 내용은 [SEMM의 보안 Surface Dock 2 포트](secure-surface-dock-ports-semm.md)를 참조 하세요.

![Microsoft Surface UEFI 구성자](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*그림 1. Microsoft Surface UEFI 구성자*


다음 세 가지 모드에서 Microsoft Surface UEFI 구성자 도구를 사용할 수 있습니다.

* [SURFACE UEFI 구성 패키지](#configuration-package)입니다. 이 모드를 사용 하 여 surface UEFI 구성 패키지를 만들어 surface device를 SEMM에 등록 하 고 등록 된 디바이스에서 UEFI 설정을 구성할 수 있습니다.
* [SURFACE UEFI Reset 패키지](#reset-package)입니다. 이 모드를 사용 하 여 Surface 디바이스의 등록을 SEMM로 등록 해제 합니다.
* [SURFACE UEFI 복구 요청](#recovery-request)입니다. 패키지 다시 설정 작업이 실패 하는 경우이 모드를 사용 하 여 복구 요청에 응답 하 여 Surface device를 SEMM에서 등록 해제 합니다.


#### Microsoft Surface UEFI 구성자 다운로드

Microsoft Surface UEFI Configurator를 다운로드 센터의 IT 페이지의 [Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 에서 다운로드할 수 있습니다.

### 구성 패키지

Surface UEFI 구성 패키지는 Surface 디바이스의 SEMM을 구현 하 고 관리 하는 기본 메커니즘입니다. 이러한 패키지에는 그림 2와 같이 Microsoft Surface UEFI 구성자 및 인증서 파일에 패키지를 만드는 동안 지정 된 UEFI 설정의 구성 파일이 포함 됩니다. SEMM에 등록 되지 않은 Surface 장치에서 처음으로 구성 패키지를 실행 하는 경우 디바이스 펌웨어의 인증서 파일을 프로 비전 하 고이 장치를 SEMM에 등록할 수 있습니다. SEMM에서 디바이스를 등록 하는 경우 인증서 파일을 저장 하기 전에 SEMM 인증서 손도장의 마지막 두 자리를 제공 하 고 등록을 완료 하 라는 메시지가 표시 됩니다. 이 확인을 위해서는 등록할 때 장치에 사용자가 있어야 확인을 수행할 수 있습니다.

![인증서를 사용 하 여 SEMM 구성 패키지 보호](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*그림 2. 인증서를 사용 하 여 SEMM 구성 패키지 보호*

SEMM 인증서에 대 한 요구 사항에 대 한 자세한 내용은이 문서의 [Surface Enterprise 관리 모드 인증서 요구 사항](#surface-enterprise-management-mode-certificate-requirements) 섹션을 참조 하세요.

>[!NOTE]
>Surface UEFI의 **보안**, **장치**, **부팅 구성**또는 **엔터프라이즈 관리** 페이지를 보는 데 필요한 semm의 암호를 지정할 수도 있습니다.

디바이스가 SEMM에 등록 되 면 구성 파일을 읽고 파일에 지정 된 설정이 UEFI에 적용 됩니다. SEMM로 등록 된 장치에서 구성 패키지를 실행 하는 경우 구성 파일의 서명이 디바이스 펌웨어에 저장 된 인증서를 기준으로 검사 됩니다. 서명이 일치 하지 않으면 장치에 변경 내용이 적용 되지 않습니다.

### Surface UEFI에서 장치 사용 또는 사용 안 함 (SEMM)

다음 목록에는 SEMM에서 관리할 수 있는 모든 장치가 나와 있습니다.

* 도킹 USB 포트
* 온보드 오디오
* DGPU
* 타이핑 커버
* 마이크로 SD 카드
* 전면 카메라
* 후면 카메라
* 적외선 카메라, Windows Hello
* 블루투스만
* Wi-Fi 및 Bluetooth
*              LTE           

 >[!NOTE]
>UEFI 장치 페이지에 표시 되는 기본 제공 디바이스는 장치 또는 회사 환경에 따라 다를 수 있습니다. 예를 들어 UEFI 장치 페이지는 Surface Pro X에서 지원 되지 않습니다. LTE는 LTE 장착 장치에만 표시 됩니다. 
### SEMM을 사용 하 여 고급 설정 구성
**표 1. 고급 설정**

| 설정                            | 설명                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PXE 부팅용 IPv6                  | PXE 부팅에 대 한 Ipv6 지원을 관리할 수 있습니다. 이 설정을 구성 하지 않으면 PXE 부팅에 대 한 IPv6 지원이 사용 되지 않습니다.                                                                               |
| 대체 부팅                     | 부팅 중에 볼륨 아래로 단추와 전원 단추를 모두 눌러 USB 또는 이더넷 장치로 직접 부팅 하는 대체 부팅 순서의 사용을 관리할 수 있습니다. 이 설정을 구성 하지 않으면, 대체 부팅을 사용할 수 있습니다. |
| 부팅 순서 잠금                    | 부팅 순서를 잠궈 변경 되지 않도록 할 수 있습니다. 이 설정을 구성 하지 않으면, 부팅 순서 잠금을 사용할 수 없습니다.                                                                                                        |
| USB 부팅                           | USB 장치에 대 한 부팅을 관리할 수 있습니다. 이 설정을 구성 하지 않으면, USB Boot를 사용할 수 있습니다.                                                                                                                 |
| 네트워크 스택                      | 네트워크 스택 부팅 설정을 관리할 수 있습니다. 이 설정을 구성 하지 않으면 네트워크 스택 부팅 설정을 관리 하는 기능이 비활성화 됩니다.                                                                                                           |
| 자동 전원 켜기                      | 자동 전원 켜기 부팅 설정을 관리할 수 있습니다. 이 설정을 구성 하지 않으면 자동 전원을 켤 수 있습니다.                                                                                                        |
| SMT (동시 다중 스레드) | 하이퍼스레딩을 사용 하거나 사용 하지 않도록 설정 하는 동시 다중 스레드 (SMT)를 관리할 수 있습니다. 이 설정을 구성 하지 않으면 SMT가 사용 하도록 설정 됩니다.                                                  |
|배터리 한도 사용| 배터리 제한 기능을 관리할 수 있습니다. 이 설정을 구성 하지 않으면 배터리 한도가 사용 됩니다. |
| 보안                           | Surface UEFI **보안** 페이지를 표시 합니다. 이 설정을 구성 하지 않으면 보안 페이지가 표시 됩니다.                                                                                                                 |
| 장치                            | Surface UEFI **장치** 페이지를 표시 합니다. 이 설정을 구성 하지 않으면 장치 페이지가 표시 됩니다.                                                                                                                     |
| Boot                               | Surface UEFI **부팅** 페이지를 표시 합니다. 이 설정을 구성 하지 않으면 부팅 페이지가 표시 됩니다.                                                                                                                                                            |
| DateTime                           | Surface UEFI **날짜/시간** 페이지를 표시 합니다. 이 설정을 구성 하지 않으면 날짜/시간 페이지가 표시 됩니다.                                                                                                                |



>[!NOTE]
>SEMM 구성 패키지를 만들면 그림 3과 같이 **성공적** 페이지에 두 개의 문자가 표시 됩니다.

![인증서 지문 표시](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*그림 3. 성공 페이지에서 인증서 손도장의 마지막 두 문자 표시*

이러한 문자는 인증서 손도장의 마지막 두 자 이며, 적어 서 기록 하거나 기록해 야 합니다. 그림 4와 같이 Surface 장치에서 등록을 확인 하는 데 문자가 필요 합니다.

![등록 확인 (SEMM)](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*그림 4. Semm 인증서 지문이 있는 SEMM의 등록 확인*

>[!NOTE]
>인증서 파일 (.pfx)에 대 한 액세스 권한이 있는 관리자는 CertMgr에서 .pfx 파일을 열어 언제 든 지 지문을 읽을 수 있습니다. CertMgr를 사용 하 여 지문을 보려면 다음 프로세스를 따르세요.
>1. .Pfx 파일을 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 클릭 합니다.
>2. 탐색 창에서 폴더를 확장 합니다.
>3. **인증서**를 클릭합니다.
>4. 기본 창에서 인증서를 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 클릭 합니다.
>5. **세부 정보** 탭을 클릭 합니다.
>6. **표시** 드롭다운 메뉴에서 **모두** 또는 **속성만** 선택 해야 합니다.
>7. 필드 **지문을**선택 합니다.

Surface 장치를 SEMM에 등록 하거나 구성 패키지에서 UEFI 구성을 적용 하려면 의도 된 Surface 장치에서 관리자 권한으로 .msi 파일을 실행 하기만 하면 됩니다. [Microsoft 끝점 구성 관리자](https://technet.microsoft.com/library/mt346023) 또는 [microsoft 배포 툴킷](https://technet.microsoft.com/windows/dn475741)등의 운영 체제 배포 기술 또는 응용 프로그램 배포를 사용할 수 있습니다. 디바이스를 SEMM에 등록 하는 경우 장치에서 등록을 확인 하기 위해 있어야 합니다. SEMM에 이미 등록 된 장치에 구성을 적용 하는 경우 사용자 조작이 필요 하지 않습니다.

SEMM에서 Surface device를 등록 하거나 SEMM을 사용 하 여 Surface UEFI 구성을 적용 하는 방법에 대 한 단계별 연습을 보려면 [surface 장치 등록 및 구성 (SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm))을 참조 하세요.

### 패키지 다시 설정

Surface UEFI reset 패키지는 한 작업을 수행 하는 데 사용 되며, Surface device는 SEMM에서 등록을 해제 합니다. 패키지 초기화에는 디바이스의 펌웨어에서 SEMM 인증서를 제거 하 고 UEFI 설정을 출고시 기본값으로 다시 설정 하는 서명 된 지침이 포함 되어 있습니다. Surface UEFI 구성 패키지와 마찬가지로 reset 패키지는 Surface device에서 프로 비전 되는 동일한 SEMM 인증서로 서명 해야 합니다. SEMM reset 패키지를 만들 때, 다시 설정 하려는 Surface 디바이스의 일련 번호를 제공 해야 합니다. SEMM 재설정 패키지는 유니버설 하지 않으며 한 장치에만 해당 됩니다.

### 복구 요청

일부 시나리오에서는 Surface UEFI reset 패키지를 사용 하는 것이 불가능할 수도 있습니다. (예를 들어 Surface 장치에서 Windows를 사용할 수 없게 되는 경우) 이러한 시나리오에서는 surface UEFI (그림 5에 표시 됨)의 **엔터프라이즈 관리** 페이지를 통해 복구 요청 작업으로 surface 디바이스의 등록을 제거할 수 있습니다.

![SEMM 복구 요청 시작](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*그림 5. 엔터프라이즈 관리 페이지에서 SEMM 복구 요청 시작*

**엔터프라이즈 관리** 페이지의 프로세스를 사용 하 여 Surface DEVICE에서 semm을 다시 설정 하는 경우 초기화 요청이 제공 됩니다. 이 재설정 요청은 USB 드라이브에 파일로 저장 하거나, 텍스트로 복사 하거나, 모바일 장치를 사용 하 여 쉽게 전자 메일로 또는 messaged QR 코드로 읽을 수 있습니다. Microsoft Surface UEFI 구성자 초기화 요청 옵션을 사용 하 여 초기화 요청 파일을 로드 하거나 재설정 요청 텍스트 또는 QR 코드를 입력 합니다. Microsoft Surface UEFI 구성자는 Surface device에 입력할 수 있는 확인 코드를 생성 합니다. Surface 장치에 코드를 입력 하 고 **다시 시작**을 클릭 하면 디바이스는 semm에서 unenrolled 됩니다. 

>[!NOTE]
>재설정 요청은 생성 된 후 두 시간 후에 만료 됩니다.

Surface 디바이스의 등록을 해제 하는 방법에 대 한 단계별 연습을 보려면 semm에서 등록 해제 [화면 장치](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)를 참조 하세요.

## Surface 엔터프라이즈 관리 모드 인증서 요구 사항

>[!NOTE]
>등록 된 Surface 디바이스에서 SEMM 또는 Surface UEFI 설정에 대 한 수정 작업을 수행 하려면 SEMM 인증서가 필요 합니다. SEMM 인증서가 손상 되거나 손실 된 경우 SEMM을 제거 하거나 재설정할 수 없습니다. 적절 한 백업 및 복구 솔루션을 사용 하 여 SEMM 인증서를 관리 하세요.

Microsoft Surface UEFI 구성자 도구를 사용 하 여 만든 패키지는 인증서를 사용 하 여 서명 됩니다. 이 인증서는 디바이스를 SEMM에 등록 한 후 승인 된 인증서로 만든 패키지만 UEFI의 설정을 수정 하는 데 사용할 수 있도록 보장 합니다. SEMM 인증서에 대해 다음 설정을 권장 합니다.

* **키 알고리즘** – RSA 
* **키 길이** – 2048
* **해시 알고리즘** – sha-1-256
* **유형** – SSL 서버 인증
* **키 사용** – 디지털 서명, 키 암호화
* **공급자** – Microsoft 향상 된 RSA 및 AES 암호화 공급자
* **만료 날짜** – 인증서 생성 시 15 개월
* **키 내보내기 정책** – 내보낼 수 있습니다.

또한 인증서 해지를 활성화 하는 중간 CA (인증 기관)가 SEMM 인 2 계층 PKI (공개 키 인프라) 아키텍처에서 SEMM 인증서를 인증 하는 것이 좋습니다. 2 계층 PKI 구성에 대 한 자세한 내용은 [테스트 랩 가이드: AD CS 2 계층 PKI 계층 구조 배포](https://technet.microsoft.com/library/hh831348)를 참조 하세요.

>[!NOTE]
>다음 PowerShell 스크립트를 사용 하 여 개념 증명 시나리오에서 사용할 자체 서명 된 인증서를 만들 수 있습니다.
 > 이 스크립트를 사용 하려면 다음 텍스트를 메모장에 복사 하 고 파일을 PowerShell 스크립트 (. ps1)로 저장 합니다. 이 스크립트는 암호를 사용 하 여 인증서를 만듭니다 `12345678` .<br/><br/>이 스크립트에서 생성 된 인증서는 프로덕션 환경에는 권장 되지 않습니다.
  
   ```
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
   ```

SEMM 및 Microsoft Surface UEFI 구성자와 함께 사용 하려면 인증서를 개인 키와 암호 보호를 사용 하 여 내보내야 합니다. Microsoft Surface UEFI 구성자는 필요할 때 SEMM 인증서 파일 (.pfx) 및 인증서 암호를 선택 하 라는 메시지를 표시 합니다.

>[!NOTE]
>PKI 인프라에서 오프 라인 루트를 사용 하는 조직의 경우 Microsoft Surface UEFI 구성자을 루트 CA에 연결 된 환경에서 실행 해야 SEMM 인증서를 인증할 수 있습니다. Microsoft Surface UEFI 구성자에서 생성 된 패키지는 파일로 전송 될 수 있으므로 USB 스틱 같은 이동식 저장소를 사용 하 여 오프 라인 네트워크 환경 외부에서 전송할 수 있습니다.

### 인증서 관리 FAQ

권장 되는 *최소* 길이는 15 개월입니다. 15 개월 이내로 만료 되는 인증서를 사용 하거나 15 개월 넘게 만료 되는 인증서를 사용할 수 있습니다.

>[!NOTE] 
>인증서가 만료 되 면 자동으로 갱신 되지 않습니다. 

**15 개월 후에 기존 컴퓨터에서 bios 설정이 계속 적용 되나요?**

인증서가 유효 했을 때 패키지 자체에 서명이 있는 경우에만 가능 합니다.

**Will** **Semm 패키지와 인증서를 보유 하 고 있는 모든 컴퓨터에서이를 업데이트 해야 하나요?**

SEMM 재설정 또는 복구가 작동 하도록 하려면 인증서가 유효 하 고 만료 되지 않아야 합니다. 

**주문 하는 각 표면에 대해 패키지를 대량으로 다시 설정할 수 있습니까? 환경에서 모든 컴퓨터를 다시 설정 하는 빌드를 할 수 있나요?**

특정 디바이스 유형에 대 한 구성 패키지를 만드는 PowerShell 샘플을 사용 하 여 일련 번호를 독립적으로 설정 패키지를 만들 수도 있습니다. 인증서가 여전히 유효한 경우 PowerShell을 사용 하 여 reset 패키지를 만들어 SEMM을 다시 설정할 수 있습니다.

## 버전 기록

### 버전 2.71.139.0

이 SEMM에는 surface Book 3, Surface 랩톱 3 및 Surface Pro 7에 대 한 Surface Dock 2 관리 기능에 대 한 지원이 추가 됩니다.

- 오디오 사용 (잠금/잠금 해제), 이더넷 및 USB 포트
- 인증 된 호스트나 인증 되지 않은 호스트 모두에 대해 dock 패키지를 만들 수 있습니다.

### 버전 2.70.130.0

이 SEMM 버전에는 다음이 포함 됩니다.

- Surface Go 2 지원
- Surface Book 3에 대 한 지원
- 버그 수정


### 버전 2.59.139.0

* 인텔 프로세서를 사용 하는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3 13.5 "및 15" 모델에 대 한 지원. 참고: Surface 랩탑 3 15 "AMD 프로세서는 지원 되지 않습니다.

- 절전 모드 종료 기능 지원

### 버전 2.54.139.0
* Surface Hub 2S 지원
* 버그 수정

### 버전 2.43.136.0
* Simulatenous multithreating 사용/사용 안 함 지원 
* 일부 장치에 대 한 WiFi 및 블루투스 옵션 구분 
* Surface Studio에 대 한 배터리 제한 제거 됨 

### 버전 2.26.136.0
* Surface Studio 2에 대 한 지원 추가
* 배터리 제한 기능

### 버전 2.21.136.0
* Surface Pro 6에 대 한 지원 추가
* Surface 노트북 2에 대 한 지원 추가

### 버전 2.14.136.0
* Surface Go에 대 한 지원 추가

### 버전 2.9.136.0
* Surface Book 2에 대 한 지원 추가
* Surface Pro LTE에 대 한 지원 추가
* 접근성 개선

### 버전 1.0.74.0
* Surface 노트북에 대 한 지원 추가
* Surface Pro에 대 한 지원 추가
* 버그 수정 및 일반적인 개선

## 관련 항목

- [SEMM을 사용하여 Surface 장치 등록 및 구성](enroll-and-configure-surface-devices-with-semm.md)
- [SEMM에서 Surface 장치 등록 해제](unenroll-surface-devices-from-semm.md)
- [보안 Surface Dock 2 포트 (SEMM)](secure-surface-dock-ports-semm.md)
