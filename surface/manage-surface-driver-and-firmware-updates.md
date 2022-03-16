---
title: Surface 드라이버 및 펌웨어 업데이트 관리 및 배포
description: 이 문서에서는 Surface 디바이스용 드라이버 및 펌웨어 업데이트를 포함하는 다운로드 가능한 패키지에 대한 링크를 제공하며 사용 가능한 관리 및 배포 솔루션에 대해 설명합니다.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 8, Surface Go, Surface Laptop, Surface Studio, Surface Pro 3, 펌웨어, 업데이트, 장치, 관리, 배포, 드라이버, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/14/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: f914678f2317ce4e08554d27b74bac4e33e3c641
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449641"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Surface 드라이버 및 펌웨어 업데이트 관리 및 배포

Surface 드라이버 및 펌웨어 업데이트를 관리하는 방법은 환경 및 조직 요구 사항에 따라 다를 수 있습니다. 대규모 조직에서 IT 관리자는 일반적으로 내부적으로 배포를 단계화하고 업그레이드를 사용자 장치에 배포하기 전에 테스트할 시간을 할당합니다.

> [!NOTE]
> 이 문서는 IT 전문가 및 기술 지원 에이전트를 위한 것으로 Surface 디바이스에만 적용됩니다. 홈 디바이스에 Surface 업데이트 또는 펌웨어를 설치하는 데 도움이 필요한 경우 Surface용 드라이버 및 펌웨어 다운로드를 [참조하세요](https://support.microsoft.com/help/4023505).

엔터프라이즈급 소프트웨어 배포 솔루션은 계속 발전하고 있는 반면, 업데이트를 중앙에서 관리하기 위한 비즈니스 근거는 동일합니다. Surface 디바이스의 보안을 유지하고 최신 운영 체제 및 기능 개선 사항으로 업데이트된 상태로 유지하세요. 이는 안정적인 프로덕션 환경을 유지하며 사용자가 생산성을 차단하지 못하게 하는 데 필수적입니다.

## <a name="whats-in-surface-driver-and-firmware-updates"></a>Surface 드라이버 및 펌웨어 업데이트의 소식

Windows Installer .msi 파일에 Surface 디바이스에 필요한 모든 누적 드라이버 및 펌웨어 업데이트가 포함되어 있습니다. 업데이트 패키지에는 다음 구성 요소 중 일부 또는 전체가 포함되어 있을 수 있습니다.

- Wi-Fi 및 LTE
- 비디오
- 솔리드 스테이트 드라이브
- SAM(시스템 집계 모듈)
- 배터리
- 키보드 컨트롤러
- EC(포함 컨트롤러)
- 관리 엔진(ME)
- UEFI(Unified Extensible Firmware Interface)

## <a name="download-msi-files"></a>파일 .msi 다운로드

이 섹션에서는 Surface 디바이스용 드라이버 및 펌웨어 업데이트를 포함하는 다운로드 가능한 패키지에 대한 직접 링크를 제공합니다. 

1. 적절한 Windows 10 Windows 11 선택합니다. 
2. 여러 개의 .msi 장치의 경우 조직에 배포된 Surface .msi 버전과 일치하는 Windows 파일 이름을 선택합니다.  


| Surface 디바이스                                                                                                                                        | 다운로드 가능한 .msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ Surface Pro 7+(LTE)](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5(LTE)](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5(Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **surface 노트북**                                                                                                                                    | - [Surface Laptop 이동](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop 4 및 Intel 프로세서](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop 4 AMD 프로세서](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 Intel 프로세서](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop 3 AMD 프로세서](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop 스튜디오**                                                                                                                             | - [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go(Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go(LTE)](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3(Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3(LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3(LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3(LTE) - 북미 통신 사업자 잠금 해제](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3(LTE) - 북미 외 및 일본 Y!모바일](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub Windows 10 Pro** [**또는 Windows 10 Enterprise**](/surface-hub/surface-hub-2s-migrate-os)   | - [Windows 10 Pro Enterprise OS 및 Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub 2020 Windows 10 Teams 실행 중인 업데이트**                                                                                                  | - [Manage Windows updates on Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface Dock 2**                                                                                                                                    | - [Surface Dock 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> 다른 Windows 다른 파일이 포함된 이전 장치의 경우 Surface 모델 및 .msi 버전과 일치하는 파일 이름을 Windows. .msi 파일 이름에는 드라이버와 펌웨어를 설치하는 Windows 지원되는 최소 빌드 번호가 포함되어 있습니다. 예를 들어 빌드 18362가 Surface Book 2를 업데이트하기 위해 Windows 10 선택SurfaceBook2_Win10_18362_19.101.13994.msi ** .** 빌드 Surface Book 16299가 있는 Windows 10 2의 경우 를 **SurfaceBook2_Win10_16299_1803509_3.msi**.

## <a name="central-update-management-in-commercial-environments"></a>상업용 환경의 중앙 업데이트 관리

드라이버 및 펌웨어 업데이트를 비롯한 장치 관리 도구는 [Microsoft Endpoint Manager.](https://devicemanagement.microsoft.com/) 

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Configuration Manager 및 Intune을 사용하여 업데이트 관리

Microsoft Endpoint Configuration Manager Surface 펌웨어 및 드라이버 업데이트를 Configuration Manager 클라이언트와 동기화하고 배포할 수 있습니다. 사용자와 Microsoft Intune 통합하면 관리되고 공동 관리되는 모든 장치를 한 곳으로 볼 수 있습니다. 이는 대규모 조직에서 Surface 업데이트를 관리하는 데 권장되는 솔루션입니다.

자세한 단계는 다음 리소스를 참조하세요.

- [Configuration Manager에서 구성 관리자 관리](manage-surface-driver-updates-configuration-manager.md)
- [Configuration Manager를 통해 응용 프로그램 배포](/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager 설명서](/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Microsoft Deployment Toolkit

MDT(Microsoft Deployment Toolkit)는 Endpoint Configuration Manager에 포함되어 있습니다. 환경에 따라 사용할 수 있는 선택적 배포 도구가 포함되어 있습니다.  여기에는 Windows ADK(Windows Assessment and Deployment Kit), Windows SIM(Windows System Image Manager), DISM(배포 이미지 서비스 및 관리) 및 USMT(사용자 환경 마이그레이션 도구)가 포함됩니다. Microsoft Deployment Toolkit 다운로드 페이지에서 최신 버전의 MDT를 [다운로드할 수 있습니다](https://www.microsoft.com/download/details.aspx?id=54259).

자세한 단계는 다음 리소스를 참조하세요.

- [Microsoft Deployment Toolkit 설명서](/configmgr/mdt/)
- [MDT를 사용하여 배포 준비](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)

Endpoint Configuration Manager를 사용하여 업데이트를 배포하는 방법에 대한 지침은 Configuration Manager를 사용하여 응용 프로그램 배포 [를 참조하세요](/configmgr/apps/deploy-use/deploy-applications). MDT를 사용하여 업데이트를 배포하는 방법에 대한 지침은 [MDT를 사용하여 Windows 10 이미지 배포를 참조하세요](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**WindowsPE 및 Surface 펌웨어 및 드라이버**

끝점 구성 관리자와 MDT는 배포 프로세스 중에 Windows WindowsPE(사전 설치 환경)를 모두 사용하게 됩니다. WindowsPE는 네트워크 어댑터 및 저장소 컨트롤러와 같은 제한된 기본 드라이버 집합만 지원됩니다. WindowsPE에 Windows 구성 요소에 대한 드라이버로 오류가 발생할 수 있습니다. WindowsPE 단계에서 필요한 드라이버만 사용하려면 배포 프로세스를 구성하여 이러한 오류를 방지하는 것이 가장 좋습니다.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

Endpoint Configuration Manager부터 Configuration Manager 클라이언트를 사용하여 Microsoft Surface 펌웨어 및 드라이버 업데이트를 동기화하고 배포할 수 있습니다. 자세한 내용은 KB 4098906 Configuration [Manager에서 Surface 드라이버 업데이트 관리를 참조하세요](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## <a name="supported-devices"></a>지원되는 디바이스

다운로드 가능한 .msi 파일은 Surface Pro 2 이상 장치에서 사용할 수 있습니다(Surface Pro X에서 실행되는 Windows 10 ARM).

## <a name="managing-firmware-with-dfci"></a>DFCI로 펌웨어 관리

Surface UEFI 관리는 [Intune](/intune/configuration/device-firmware-configuration-interface-windows)에 기본 제공되는 DFCI(장치 펌웨어 구성 인터페이스) 프로필을 사용하여 최신 관리 스택을 UEFI 하드웨어 수준으로 확장합니다. DFCI는 제로 터치 프로비전을 지원하고, BIOS 암호를 제거하고, 보안 설정(시작 옵션 및 기본 제공 주변 장치 포함)을 제어하며, 향후 고급 보안 시나리오를 위한 초안을 마련합니다. 자세한 내용은 다음을 참조하십시오.

- [Surface 장치에서 DFCI 관리](surface-manage-dfci-guide.md)
- [Ignite 2019: Intune에서 Surface UEFI 설정의 원격 관리를 발표합니다](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## <a name="best-practices-for-update-deployment-processes"></a>업데이트 배포 프로세스 모범 사례

안정적인 환경을 유지 관리하기 위해 최신 버전의 최신 버전과 패리티를 유지하는 것이 Windows 10.  모범 사례 권장 사항은 클라이언트 업데이트에 대한 서비스 전략 Windows [참조하세요](/windows/deployment/update/waas-deployment-rings-windows-10-updates).

### <a name="surface-msi-naming-convention"></a>Surface .msi 이름 규칙

2019년 8월부터 .msi 파일에서 다음 명명 규칙을 사용하고 있습니다.

- *제품*_*Windows 릴리스*_*Windows*_**_ 번호 버전 번호비전(일반적으로 *0)입니다*.

**예제**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

이 파일 이름은 다음 정보를 제공합니다.

- **제품:** SurfacePro6
- **Windows 릴리스:** Win10
- **빌드:** 18362
- **버전:** 19.073.44195 – 다음과 같이 파일이 만들어진 날짜와 시간이 표시됩니다.
  - **연도:** 19(2019)
  - **월 및 주:** 073(7월의 셋째 주)
  - **월의 분:** 44195
- **버전 개정:** 0(이 버전의 첫 번째 릴리스)

### <a name="legacy-surface-msi-naming-convention"></a>레거시 Surface .msi 규칙

레거시 .msi 파일(2019년 8월 이전의 파일)은 동일한 전체 명명 수식을 따랐지만 버전 번호를 파생하기 위해 다른 방법을 사용했습니다.

**예제**

- SurfacePro6_Win10_16299_1900307_0.msi

이 파일 이름은 다음 정보를 제공합니다.

- **제품:** SurfacePro6
- **Windows 릴리스:** Win10
- **빌드:** 16299
- **버전:** 1900307 – 다음과 같이 파일을 만든 날짜와 릴리스 순서의 해당 위치를 보여 주며,
  - **연도:** 19(2019)
  - **릴리스 수:** 003(연도의 세 번째 릴리스)
  - **제품 버전 번호:** 07(Surface Pro 6은 공식적으로 7번째 버전의 Surface Pro)
- **버전 개정:** 0(이 버전의 첫 번째 릴리스)

## <a name="learn-more"></a>세부 정보

- [Windows 클라이언트 업데이트를 위한 서비스 전략 준비](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [Configuration Manager에서 구성 관리자 관리](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Configuration Manager를 통해 응용 프로그램 배포](/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager 설명서](/configmgr/)
- [Microsoft Deployment Toolkit 설명서](/configmgr/mdt/)
- [MDT를 사용하여 배포 준비](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Surface 장치에서 DFCI 관리](surface-manage-dfci-guide.md)
- [Ignite 2019: Intune에서 Surface UEFI 설정의 원격 관리를 발표합니다](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

