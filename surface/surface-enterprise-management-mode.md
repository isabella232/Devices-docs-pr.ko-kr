---
title: Surface Enterprise 관리 모드(Surface)
description: Surface UEFI를 사용하여 Surface 디바이스의 이 기능을 통해 조직 내에서 펌웨어 설정을 보호하고 관리하는 방법을 확인합니다.
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
ms.date: 04/16/2021
ms.openlocfilehash: 08221db2e4a49ccce1b372689b4dc30d8241ad0d
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676702"
---
# <a name="microsoft-surface-enterprise-management-mode"></a>Microsoft Surface Enterprise 관리 모드

Microsoft Surface Enterprise 관리 모드(SEMM)는 Surface UEFI(Unified Extensible Firmware Interface)가 있는 Surface 디바이스의 기능입니다. SEMM을 사용하여 다음을 할 수 있습니다.

- 조직의 펌웨어 설정을 보호하고 관리합니다.
- UEFI 설정 구성을 준비하고 Surface 디바이스에 설치합니다.

또한 SEMM은 인증서를 사용하여 무단 변조 또는 제거로부터 구성을 보호합니다. 2S를 Surface Hub 2S를 Windows 10 Pro Windows Enterprise SEMM이 필요합니다.

>[!NOTE]
>SEMM은 Surface UEFI 펌웨어가 있는 디바이스에서만 사용할 수 있습니다. 여기에는 Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 상업용 SKUS(Intel 프로세서 포함Surface Laptop 4개 상업용 SKUS, Surface Laptop Intel 프로세서가 포함된 상업용 SK 3개, Surface Laptop Go 등 대부분의 Surface 장치가 포함됩니다. SEMM은 AMD 프로세서가 있는 15인치 Surface Laptop 3 SKU에서 지원되지 않습니다(일반 정품 SKU로만 사용 가능).

Surface 디바이스는 SEMM에서 구성하고 SEMM 인증서로 보호되는 경우 ** SEMM에 등록된 것으로 간주됩니다. SEMM 인증서가 제거되고 UEFI 설정 제어가 디바이스 사용자에게 반환되면 Surface 디바이스는 SEMM에서 등록되지 않은 것으로 간주됩니다. **

SEMM을 관리하고 Surface 디바이스를 등록하는 데 사용할 수 있는 두 가지 관리 옵션이 있습니다.

- SEMM 독립 실행형 도구인 Microsoft Surface UEFI 구성기는 이 문서에 설명되어 있습니다.

- 통합 Microsoft Endpoint Configuration Manager. 자세한 내용은 [USE Microsoft Endpoint Configuration Manager to manage devices with SEMM을 참조하세요.](use-system-center-configuration-manager-to-manage-devices-with-semm.md)

> [!NOTE]
> SEMM은 UEFI Surface Pro X에서만 지원됩니다. IT용 Surface 도구에서 UEFI [관리자를 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=46703) 자세한 내용은 [X에서 배포, 관리 및 Surface Pro 참조하세요.](surface-pro-arm-app-management.md)

## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI 구성기

SEMM의 기본 작업 영역은 그림 1에 표시된 Microsoft Surface UEFI Configurator입니다.

Microsoft Surface UEFI 구성기에서 다음을 할 수 있습니다.

- 설치 Windows 설치 관리자(.msi) 패키지를 만들 수 있습니다.
- WinPE 이미지를 사용하여 Surface 디바이스에서 SEMM을 등록, 구성 및 등록을 해지합니다.

이러한 패키지에는 UEFI 설정을 지정하는 구성 파일이 포함되어 있습니다. SEMM 패키지에는 펌웨어에 설치 및 저장되는 인증서도 포함되어 있으며 UEFI 설정이 적용되기 전에 구성 파일의 서명을 확인하는 데 사용됩니다.

>[!TIP]
>이제 Surface UEFI 구성기 및 SEMM을 사용하여 Surface Dock 2에서 포트를 관리할 수 있습니다. 자세한 내용은 [SEMM을 통해 Surface Dock 2 포트 보호를 참조합니다.](secure-surface-dock-ports-semm.md)

![Microsoft Surface UEFI 구성기](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*그림 1. Microsoft Surface UEFI 구성기*

Microsoft Surface UEFI 구성기 도구를 세 가지 모드로 사용할 수 있습니다.

- [Surface UEFI 구성 패키지](#configuration-package). 이 모드를 사용하여 Surface UEFI 구성 패키지를 만들어 SEMM에 Surface 디바이스를 등록하고 등록된 디바이스에서 UEFI 설정을 구성합니다.
- [Surface UEFI 재설정 패키지](#reset-package). 이 모드를 사용하여 SEMM에서 Surface 디바이스의 선택을 끄십시오.
- [Surface UEFI 복구 요청](#recovery-request). 이 모드를 사용하여 복구 요청에 응답하여 패키지 초기화 작업이 성공하지 않은 경우 SEMM에서 Surface 디바이스를 초기화합니다.

### <a name="download-microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI 구성기 다운로드

Microsoft Surface UEFI 구성기는 Microsoft 다운로드 센터의 [Surface Tools for IT(IT용 Surface 도구)](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 다운로드할 수 있습니다.

### <a name="configuration-package"></a>구성 패키지

Surface UEFI 구성 패키지는 Surface 디바이스에서 SEMM을 구현하고 관리하는 기본 메커니즘입니다. 이러한 패키지에는 그림 2에 표시된 구성 파일과 인증서 파일이 포함되어 있습니다. 구성 파일에는 Microsoft Surface UEFI 구성기에서 패키지를 만들 때 지정된 UEFI 설정이 포함되어 있습니다. 구성 패키지가 SEMM에 아직 등록되지 않은 Surface 디바이스에서 처음으로 실행되는 경우 디바이스의 펌웨어에서 인증서 파일을 프로비전하고 SEMM에 장치를 등록합니다. SEMM에 장치를 등록할 때 및 인증서가 저장되고 등록이 완료되기 전에 SEMM 인증서 지문의 마지막 두 자리 숫자를 제공하여 작업을 확인하는 메시지가 표시됩니다. 이 확인을 수행하려면 등록하는 동안 사용자가 실제로 디바이스에 존재해야 합니다.

![인증서를 통해 SEMM 구성 패키지 보안](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*그림 2. 인증서를 통해 SEMM 구성 패키지 보안*

SEMM 인증서의 요구 사항에 대한 자세한 내용은 이 문서 [부분의 Surface Enterprise 관리](#surface-enterprise-management-mode-certificate-requirements) 모드 인증서 요구 사항 섹션을 참조하세요.

>[!TIP]
>SEMM을 사용하여 UEFI 암호를 요구할 수 있습니다. 이 경우 Surface UEFI의 **보안,** **장치,** 부팅 구성 및 보안 관리 Enterprise 암호가 필요합니다. **** ****

장치가 SEMM에 등록된 후 구성 파일을 읽고 파일에 지정된 설정이 UEFI에 적용됩니다. 이미 SEMM에 등록된 장치에서 구성 패키지를 실행하면 구성 파일의 서명이 장치 펌웨어에 저장된 인증서에 대해 확인됩니다. 서명이 일치하지 않는 경우 장치에 변경 내용이 적용되지 않습니다.

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>SEMM을 사용하여 Surface UEFI에서 장치 사용 또는 사용 안 하도록 설정

다음 목록에는 SEMM에서 관리할 수 있는 모든 사용 가능한 장치가 표시됩니다.

- USB 포트 도킹
- 보드 오디오
- 디지털 그래픽 처리 장치
- 표지 형식
- 마이크로 SD 카드
- 전면 카메라
- 후면 카메라
- 적외선 카메라(Windows Hello)
- Bluetooth 전용
- 무선 네트워크 및 Bluetooth
- LTE(장기 발전)

 >[!NOTE]
>UEFI 장치 페이지에서 기본 제공 장치는 장치 또는 회사 환경에 따라 다를 수 있습니다. 예를 들어 UEFI 장치 페이지는 X에서 지원되지 Surface Pro 않습니다. LTE는 LTE가 탑재된 디바이스에만 표시됩니다.

### <a name="configure-advanced-settings-with-semm"></a>SEMM을 사용하여 고급 설정 구성

**표 1. 고급 설정**

| 설정                            | 설명                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PXE 부팅용 IPv6                  | PXE 부팅에 대한 IPv6 지원을 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 PXE 부팅에 대한 IPv6 지원을 사용할 수 없습니다.                                                                               |
| 대체 부팅                     | 부팅하는 동안 볼륨 감소 단추와 전원 단추를 모두 눌러 USB 또는 이더넷 디바이스로 직접 부팅하기 위해 대체 부팅 순서 사용을 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 대체 부팅이 사용하도록 설정됩니다. |
| 부팅 순서 잠금                    | 변경을 방지하기 위해 부팅 순서를 잠글 수 있습니다. 이 설정을 구성하지 않은 경우 부팅 순서 잠금을 사용할 수 없습니다.                                                                                                        |
| USB 부팅                           | USB 장치에 대한 부팅을 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 USB 부팅이 사용하도록 설정됩니다.                                                                                                                 |
| 네트워크 스택                      | 네트워크 스택 부팅 설정을 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 네트워크 스택 부팅 설정을 관리하는 기능을 사용할 수 없습니다.                                                                                                           |
| 자동 전원 공급                      | 자동 전원 사용 부팅 설정을 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 자동 전원 사용이 사용하도록 설정됩니다.                                                                                                        |
| SMT(동시 다중 스레딩) | SMT(동시 다중 스레딩)를 관리하여 하이퍼스레딩을 활성화 또는 비활성화할 수 있습니다. 이 설정을 구성하지 않은 경우 SMT가 사용하도록 설정됩니다.                                                  |
|배터리 제한 사용| 배터리 제한 기능을 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 배터리 제한이 사용하도록 설정됩니다. |
| Security                           | Surface UEFI **** 보안 페이지를 표시됩니다. 이 설정을 구성하지 않은 경우 보안 페이지가 표시됩니다.                                                                                                                 |
| 장치                            | Surface UEFI 장치 **페이지를** 표시됩니다. 이 설정을 구성하지 않은 경우 장치 페이지가 표시됩니다.                                                                                                                     |
| Boot                               | Surface UEFI **** 부팅 페이지를 표시됩니다. 이 설정을 구성하지 않은 경우 부팅 페이지가 표시됩니다.                                                                                                                                                            |
| DateTime                           | Surface UEFI **DateTime 페이지를** 표시됩니다. 이 설정을 구성하지 않은 경우 DateTime 페이지가 표시됩니다.                                                                                                                |
| EnableOSMigration                          | 2에서 Surface Hub 2를 마이그레이션할 Windows 10 Team Windows 10 Pro Enterprise. 이 설정을 구성하지 않는 경우 Surface Hub 2 장치가 하나의 OS만 실행할 Windows 10 Team 있습니다. 참고: Windows 10 Team 및 Windows 10 Pro/Enterprise 2에서는 이중 부팅을 사용할 Surface Hub 없습니다.                                                                                                           |

>[!TIP]
>SEMM 구성 패키지를 만들면 그림 3과 같이 성공 페이지에 두 문자가 표시됩니다. ****

![인증서 지문 표시](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*그림 3. 성공 페이지에서 인증서 지문의 마지막 두 문자 표시*

이러한 문자는 인증서 지문의 마지막 두 문자로, 기록하거나 기록해야 합니다. 그림 4에 표시된 같이 문자는 Surface 디바이스의 SEMM 등록을 확인하는 데 필요합니다.

![SEMM에서 등록 확인](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*그림 4. SEMM 인증서 지문을 통해 SEMM에 등록 확인*

>[!TIP]
>인증서 파일(.pfx)에 액세스할 수 있는 관리자는 CertMgr에서 .pfx 파일을 열면 지문을 읽을 수 있습니다. CertMgr을 통해 지문을 볼 수 있습니다.
>
>1. .pfx 파일을 선택하고 보류(또는 마우스 오른쪽 단추 클릭)한 다음 **열기 를 선택합니다.**
>2. 탐색 창에서 폴더를 확장합니다.
>3. 인증서를 **선택합니다.**
>4. 주 창에서 인증서를 선택하고 보유(또는 마우스 오른쪽 단추 클릭)한 다음 열기 **를 선택합니다.**
>5. 세부 **정보 탭을** 선택합니다.
>6. 표시 **드롭다운** 메뉴에서 **모두** 또는 속성만 **선택해야** 합니다.
>7. 지문 **필드를** 선택합니다.

SEMM에 Surface 디바이스를 등록하거나 구성 패키지에서 UEFI 구성을 적용하려면 의도한 Surface .msi 권한으로 .msi 파일을 실행합니다. 응용 프로그램 배포 또는 운영 체제 [](/mem/configmgr) 배포 기술(Microsoft Endpoint Configuration Manager [또는 Microsoft Deployment Toolkit.](/mem/configmgr/mdt) SEMM에 장치를 등록할 때 장치에 등록을 확인하려면 물리적으로 있어야 합니다. SEMM에 이미 등록된 장치에 구성을 적용하는 경우 사용자 조작이 필요하지 않습니다.

SEMM에 Surface 디바이스를 등록하거나 SEMM을 사용하여 Surface UEFI 구성을 적용하는 방법에 대한 단계별 단계를 확인하려면 SeMM을 사용하여 Surface 디바이스 등록 및 구성을 [참조하세요.](enroll-and-configure-surface-devices-with-semm.md)

### <a name="reset-package"></a>패키지 초기화

Surface UEFI 재설정 패키지는 SEMM에서 Surface 디바이스를 초기화하기 위해 하나의 작업만 수행하는 데 사용됩니다. 재설정 패키지에는 장치의 펌웨어에서 SEMM 인증서를 제거하고 UEFI 설정을 공장 기본 설정으로 다시 설정하는 서명된 지침이 포함되어 있습니다. Surface UEFI 구성 패키지와 마찬가지로 초기화 패키지는 Surface 디바이스에 프로비전된 동일한 SEMM 인증서를 사용하여 서명해야 합니다. SEMM 재설정 패키지를 만들 때 초기화하려는 Surface 디바이스의 일련 번호를 제공해야 합니다. SEMM 초기화 패키지는 유니버설이 아니며 하나의 장치에만 해당합니다.

### <a name="recovery-request"></a>복구 요청

일부 시나리오에서는 Surface UEFI 재설정 패키지를 사용하는 것이 불가능할 수 있습니다. 예를 들어 Surface Windows 사용할 수 없는 경우) 이러한 시나리오에서는 복구 요청 작업을 사용하여 Surface UEFI의 Enterprise 관리 페이지를 통해 SeMM에서 Surface 디바이스의 설치를 해지할 수 있습니다. ****

> [!div class="mx-imgBorder"]
> ![SEMM 복구 요청 시작](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*그림 5. Enterprise 페이지에서 SEMM 복구 요청 시작*

surface 디바이스에서 Enterprise **** 관리 페이지에서 프로세스를 사용하여 SEMM을 다시 설정하면 초기화 요청이 제공됩니다. 이 재설정 요청은 USB 드라이브에 파일로 저장하거나 텍스트로 복사하거나 모바일 장치를 사용하여 QR 코드로 읽을 수 있습니다. Microsoft Surface UEFI 구성기 다시 설정 요청 옵션을 사용하여 다시 설정 요청 파일을 로드하거나 요청 텍스트 또는 QR 코드 재설정을 입력합니다. Microsoft Surface UEFI 구성기는 Surface 디바이스에 입력할 수 있는 확인 코드를 생성합니다. Surface 디바이스에 코드를 입력하고 다시 **** 시작을 선택하면 장치가 SEMM에서 인가되지 않습니다.

>[!NOTE]
>재설정 요청은 생성된 후 2시간 후에 만료됩니다.

SEMM에서 Surface 디바이스를 인가하는 방법에 대한 단계별 실무는 SEMM에서 Surface 장치 인인을 [언인라운드를 참조합니다.](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Surface Enterprise 관리 모드 인증서 요구 사항

Microsoft Surface UEFI 구성기에서 SEMM을 사용하며 UEFI 설정을 적용하려면 구성 파일의 서명을 확인하는 데 인증서가 필요합니다. 이 인증서는 장치가 SEMM에 등록한 후 승인된 인증서로 만든 패키지만 UEFI 설정을 수정하는 데 사용할 수 있도록 합니다.

>[!NOTE]
>등록된 Surface 디바이스에서 SEMM 또는 Surface UEFI 설정을 수정하려면 SEMM 인증서가 필요합니다. SEMM 인증서가 손상되거나 손실된 경우 SEMM을 제거하거나 다시 설정할 수 없습니다. 백업 및 복구를 위한 적절한 솔루션을 사용하여 SEMM 인증서를 적절하게 관리

Microsoft Surface UEFI 구성기 도구를 사용하여 만든 패키지는 인증서로 서명됩니다. 이 인증서는 장치가 SEMM에 등록된 후 승인된 인증서로 만든 패키지만 UEFI 설정을 수정하는 데 사용할 수 있도록 합니다.

### <a name="recommended-certificate-settings"></a>권장 인증서 설정

SEMM 인증서에 권장되는 설정은 다음과 같습니다.

- **키 알고리즘** - RSA
- **키 길이** – 2048
- **해시 알고리즘** - SHA-256
- **유형** - SSL 서버 인증
- **키 사용** - 디지털 서명, 키 인시퍼멘트
- **공급자** - Microsoft Enhanced RSA 및 AES 암호화 공급자
- **만료 날짜** - 인증서 생성 후 15개월
- **키 내보내기 정책** - 내보낼 수 있습니다.

또한 중간 CA(인증 기관)가 SEMM 전용인 2계층 PKI(공개 키 인프라) 아키텍처에서 SEMM 인증서를 인증하여 인증서 해지가 가능한 것이 좋습니다. 2계층 PKI 구성에 대한 자세한 내용은 [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy를 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11))

### <a name="self-signed-certificate"></a>자체 서명된 인증서

다음 예제 PowerShell 스크립트를 사용하여 개념 증명 시나리오에서 사용할 자체 서명된 인증서를 만들 수 있습니다.
이 스크립트를 사용 하 고 다음 텍스트를 복사 하는 메모장 파일을 PowerShell 스크립트 (.ps1).

> [!NOTE]
> 이 스크립트는 의 암호를 사용하여 인증서를 `12345678` 만듭니다. 이 스크립트로 생성된 인증서는 프로덕션 환경에는 권장되지 않습니다.
  
```powershell
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

>[!IMPORTANT]
>SEMM 및 Microsoft Surface UEFI 구성기에서 사용하려면 개인 키와 암호 보호를 사용하여 인증서를 내보내야 합니다. Microsoft Surface UEFI 구성기에서 SEMM 인증서 파일(.pfx) 및 인증서 암호를 선택하라는 메시지가 표시됩니다.

자체 서명된 인증서를 만들 수 있는 경우:

1. C: 드라이브에서 스크립트를 저장할 폴더를 생성합니다. 예: C:\SEMM.
2. 예제 스크립트를 메모장(또는 해당하는 텍스트 편집기)에 복사한 다음 파일을 PowerShell 스크립트(.ps1) 저장합니다.
3. 관리자 자격 증명을 사용하여 컴퓨터에 로그인한 다음 관리자 권한 PowerShell 세션을 열 수 있습니다.
4. 스크립트 실행을 허용하도록 사용 권한이 설정되어 있는지 확인 기본적으로 실행 정책을 수정하지 않으면 스크립트가 실행되지 않습니다. 자세한 내용은 실행 정책 [정보를 참조합니다.](/powershell/module/microsoft.powershell.core/about/about_execution_policies)
5. 명령 프롬프트에서 스크립트의 전체 경로를 입력한 다음 Enter 를 **입력합니다.** 이 스크립트는 TempOwner.pfx라는 데모 인증서를 만듭니다.

또는 PowerShell을 사용하여 자체 서명된 인증서를 만들 수 있습니다. 자세한 내용은 [New-SelfSignedCertificate를 참조하세요.](/powershell/module/pkiclient/new-selfsignedcertificate)

>[!NOTE]
>PKI 인프라에서 오프라인 루트를 사용하는 조직의 경우 MICROSOFT Surface UEFI 구성기는 SEMM 인증서를 인증하기 위해 루트 CA에 연결된 환경에서 실행해야 합니다. Microsoft Surface UEFI Configurator에서 생성한 패키지는 파일로 전송할 수 있으므로 USB 스틱과 같은 이동식 저장소를 사용하여 오프라인 네트워크 환경 외부로 전송할 수 있습니다.

### <a name="managing-certificates-faq"></a>인증서 관리 FAQ

권장되는 *최소* 길이는 15개월입니다. 15개월 미만으로 만료되는 인증서를 사용할 수도 있습니다. 또는 15개월보다 오래 만료되는 인증서를 사용할 수 있습니다.

>[!NOTE]
>인증서가 만료되면 자동으로 갱신되지 않습니다.

**만료된 인증서가 SEMM 등록 장치의 기능에 영향을 미치나요?**<br><br>
아니요. 인증서는 SEMM의 IT 관리자 관리 작업에만 영향을 미치며 만료 시 장치 기능에는 영향을 주지 않습니다.

**SEMM 패키지 및 인증서가 있는 모든 컴퓨터의 SEMM 패키지 및 인증서를 업데이트해야 합니까?**<br><br>
SEMM 재설정 또는 복구가 작동하게 하려는 경우 인증서가 유효해야 하고 만료되지 않은 것입니다.

**주문하는 각 표면에 대해 패키지를 대량 재설정할 수 있나요? 환경의 모든 컴퓨터를 다시 설정하는 기능을 구축할 수 있나요?**<br><br>
특정 장치 유형에 대한 구성 패키지를 만드는 PowerShell 샘플을 사용하여 일련 번호가 독립적인 초기화 패키지를 만들 수도 있습니다. 인증서가 여전히 유효한 경우 PowerShell을 사용하여 SEMM을 다시 설정하는 재설정 패키지를 만들 수 있습니다.

## <a name="version-history"></a>버전 기록

### <a name="version-2831390"></a>버전 2.83.139.0

이 SEMM 버전에는 다음이 포함됩니다.

- 4 Surface Laptop 지원
- 7에 대한 동시 다중 스레드 옵션 Surface Pro 지원
- 더 이상 사용되지 않습니다. SEMM 설정 제거  
- 향상된 MSI 서명

### <a name="version-2791390"></a>버전 2.79.139.0

이 SEMM 버전에는 다음이 포함됩니다.

- 7+Surface Pro 지원
- 사용자 환경 개선.

### <a name="version-2781390"></a>버전 2.78.139.0

이 SEMM 버전에는 다음이 포함됩니다.

- 이동 및 Surface Laptop 지원 Surface Pro 합니다.
- 새 버전 릴리스에 대한 알림입니다.
- 소유권을 변경하기 위해 사용자 지정 패키지를 만드는 능력
- 버그 수정.

### <a name="version-2731360"></a>버전 2.73.136.0

이 SEMM 버전에는 다음이 포함됩니다.

- SEMM을 사용하여 Surface Hub2S에서 오디오를 사용하지 않도록 설정하는 기능을 제공합니다.
- Dock 2용 Surface Pro X 지원
- Dock 2 관련 작업에 대한 UEFI 관리자 지원
- Surface Go 패키지 버그 수정.
- Surface Hub OS에서 Windows 10 Team 또는 Windows 10 Pro 장치로 Enterprise.

### <a name="version-2711390"></a>버전 2.71.139.0

이 버전의 SEMM은 Surface Book 3, Surface Laptop 3 및 Surface Pro 7에 대한 Surface Dock 2 관리 기능을 추가합니다. 여기에는 다음이 포함됩니다.

- 오디오(잠금/잠금 해제) 및 이더넷 및 USB 포트를 사용하도록 설정하는 기능입니다.
- 인증된 호스트와 인증되지 않은 호스트 모두에 대해 Dock 패키지를 만드는 기능을 제공합니다.

### <a name="version-2701300"></a>버전 2.70.130.0

이 SEMM 버전에는 다음이 포함됩니다.

- Surface Go 2에 대한 지원.
- Surface Book 지원 3.
- 버그 수정.

### <a name="version-2591390"></a>버전 2.59.139.0

이 SEMM 버전에는 다음이 포함됩니다.

- Intel 프로세서가 Surface Pro 7, Surface Pro X 및 Surface Laptop 3 13.5인치 및 15인치 모델이 지원됩니다.
    >[!NOTE]
    >Surface Laptop 3 15인치 AMD 프로세서는 지원되지 않습니다.
- 절전 모드 해제 기능 지원.

### <a name="version-2541390"></a>버전 2.54.139.0

이 SEMM 버전에는 다음이 포함됩니다.

- 2S Surface Hub 지원.
- 버그 수정.

### <a name="version-2431360"></a>버전 2.43.136.0

이 SEMM 버전에는 다음이 포함됩니다.

- 동시 다중 스레드를 활성화/비활성화할 수 있습니다.
- 일부 디바이스에 대해 무선 네트워킹 및 Bluetooth 별도의 옵션입니다.
- 배터리 제한이 제거된 Surface Studio.

### <a name="version-2261360"></a>버전 2.26.136.0

이 SEMM 버전에는 다음이 포함됩니다.

- Surface Studio 지원 2.
- 배터리 제한 기능.

### <a name="version-2211360"></a>버전 2.21.136.0

이 SEMM 버전에는 다음이 포함됩니다.

- Surface Pro 6.
- Surface Laptop 지원 2.

### <a name="version-2141360"></a>버전 2.14.136.0

이 SEMM 버전에는 다음이 포함됩니다.

- Surface Go 지원.

### <a name="version-291360"></a>버전 2.9.136.0

이 SEMM 버전에는 다음이 포함됩니다.

- Surface Book 지원 2.
- LTE Surface Pro 지원.
- 접근성 개선.

### <a name="version-10740"></a>버전 1.0.74.0

이 SEMM 버전에는 다음이 포함됩니다.

- 지원 Surface Laptop.
- 지원 Surface Pro.
- 버그 수정 및 일반적인 개선

## <a name="related-topics"></a>관련 항목

- [SEMM을 사용하여 Surface 장치 등록 및 구성](enroll-and-configure-surface-devices-with-semm.md)
- [SEMM에서 Surface 디바이스 등록 취소](unenroll-surface-devices-from-semm.md)
- [Secure Surface Dock 2 포트(SEMM 포함)](secure-surface-dock-ports-semm.md)
