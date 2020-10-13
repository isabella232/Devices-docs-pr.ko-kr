---
title: Surface 드라이버 및 펌웨어 업데이트 관리 및 배포
description: 이 문서에서는 Surface 장치에 대 한 펌웨어 및 드라이버 업데이트를 관리 및 배포 하는 데 사용할 수 있는 옵션에 대해 설명 합니다
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, 펌웨어, 업데이트, 디바이스, 관리, 배포, 드라이버, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: 39022ca631e35f4328d3c353b7b0d1e2ebaee6a7
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114636"
---
# Surface 드라이버 및 펌웨어 업데이트 관리 및 배포

화면 드라이버와 펌웨어 업데이트를 관리 하는 방법은 환경과 조직의 요구 사항에 따라 달라 집니다. Surface 디바이스에서 펌웨어는 운영 체제에 드라이버로 표시 되며 장치 관리자에서 볼 수 있습니다. 이렇게 하면 Windows Update 또는 비즈니스용 Windows 업데이트를 사용 하 여 디바이스 펌웨어와 드라이버를 자동으로 업데이트할 수 있습니다. 이 간편한 접근 방법은 시작과 중소기업 또는 중간 규모의 기업에 게 적합 하지만 일반적으로 대규모 조직에서는 업데이트를 내부적으로 배포 하기 위해 IT 관리자가 필요 합니다. 여기에는 종합적인 계획, 응용 프로그램 호환성 테스트, 네트워크 전체에 대 한 최종 승인 및 배포 전에 파일럿 및 유효성 검사 업데이트가 포함 될 수 있습니다.

> [!NOTE]
> 이 문서는 기술 지원 에이전트 및 IT 전문가를 대상으로 하며 Surface 디바이스에만 적용 됩니다. 홈 장치에 Surface update 또는 펌웨어를 설치 하는 데 도움이 필요한 경우 [surface 펌웨어 및 Windows 10 업데이트](https://support.microsoft.com/help/4023505)를 참조 하세요.

엔터프라이즈 등급 소프트웨어 배포 솔루션이 계속 발전 하는 동안 중앙 집중적으로 관리 하는 비즈니스의 보안을 유지 하는 것은 그대로 유지 되며, 최신 운영 체제 및 기능 향상으로 업데이트 된 상태로 유지 됩니다. 이는 안정적인 프로덕션 환경을 유지 하 고 사용자가 생산성을 유지 하는 것이 차단 되지 않도록 하기 위해 반드시 필요 합니다. 이 문서에서는 대규모 조직에서 이러한 목표를 달성 하는 데 권장 되는 도구 및 프로세스에 대해 간략하게 설명 합니다.

## 상업용 환경의 중앙 업데이트 관리

Microsoft는 드라이버 및 펌웨어 업데이트를 포함 하 여 장치를 관리 하는 효율적인 도구를 [Microsoft Endpoint Manager 관리 센터](https://devicemanagement.microsoft.com/) 라는 단일 통합 환경으로, [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home)에서 액세스할 수 있습니다.

### Configuration Manager 및 Intune을 사용 하 여 업데이트 관리

Microsoft Endpoint Configuration Manager를 사용 하 여 Surface 펌웨어와 드라이버 업데이트를 Configuration Manager 클라이언트와 동기화 하 고 배포할 수 있습니다. Microsoft Intune과 통합 하면 관리 되는 공동 관리 및 파트너 관리 장치를 한 곳에서 볼 수 있습니다. 이는 대규모 조직에서 Surface update를 관리 하는 데 권장 되는 솔루션입니다.

자세한 단계는 다음 리소스를 참조 하세요.

- [Configuration Manager에서 구성 관리자 관리](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Configuration Manager를 사용 하 여 응용 프로그램 배포](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [끝점 구성 관리자 설명서](https://docs.microsoft.com/configmgr/)

### Microsoft 배포 도구 키트를 사용 하 여 업데이트 관리

Microsoft 배포 툴킷 (MDT)은 끝점 구성 관리자에 포함 되어 있습니다. 여기에는 환경에 따라 사용할 수 있는 선택적 배포 도구가 포함 되어 있습니다. 여기에는 windows ADK (평가 및 배포 키트), windows SIM (배포 이미지 서비스 및 관리) 및 USMT (사용자 상태 마이그레이션 도구)가 포함 됩니다. [Microsoft 배포 툴킷 다운로드 페이지](https://www.microsoft.com/download/details.aspx?id=54259)에서 최신 버전의 MDT를 다운로드할 수 있습니다.

자세한 단계는 다음 리소스를 참조 하세요.

- [Microsoft 배포 도구 키트 문서](https://docs.microsoft.com/configmgr/mdt/)
- [Microsoft Deployment Toolkit을 사용하여 Windows 10 배포](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Microsoft 배포 도구 키트를 사용 하 여 Windows 10을 Surface 장치에 배포](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Surface driver 및 펌웨어 업데이트는 Windows Installer (* .msi) 파일로 패키지 됩니다. 이러한 Windows Installer 패키지를 배포 하려면 끝점 구성 관리자 또는 MDT를 사용할 수 있습니다. 장치 및 운영 체제에 맞는 올바른 .msi 파일을 선택 하는 방법에 대 한 자세한 내용은 msi 파일 다운로드에 대 한 다음 섹션의 지침을 참조 하세요.

끝점 구성 관리자를 사용 하 여 업데이트를 배포 하는 방법에 대 한 지침은 [구성 관리자로 응용 프로그램 배포](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)를 참조 하세요. MDT를 사용 하 여 업데이트를 배포 하는 방법에 대 한 지침은 [mdt를 사용 하 여 Windows 10 이미지 배포](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)를 참조 하세요.

**WindowsPE 및 Surface 펌웨어와 드라이버**

끝점 구성 관리자와 MDT는 배포 프로세스 중에 WindowsPE (Windows 사전 설치 환경)를 사용 합니다. WindowsPE 네트워크 어댑터 및 저장소 컨트롤러와 같은 제한 된 기본 드라이버 집합만 지원 합니다. WindowsPE의 일부가 아닌 Windows 구성 요소의 드라이버는 오류를 생성할 수 있습니다. 가장 좋은 방법은 WindowsPE 단계 동안 필요한 드라이버만 사용 하도록 배포 프로세스를 구성 하 여 이러한 오류를 방지할 수 있다는 것입니다.

### Endpoint Configuration Manager

끝점 구성 관리자에서 시작 하 여 Configuration Manager 클라이언트를 사용 하 여 Microsoft Surface 펌웨어와 드라이버 업데이트를 동기화 하 고 배포할 수 있습니다. 자세한 내용은 KB 4098906, [Configuration Manager에서 화면 드라이버 업데이트를 관리 하는 방법을](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)참조 하세요.

## 지원되는 디바이스

다운로드 가능한 .msi 파일은 Surface Pro 2 및 이후 장치에서 사용할 수 있습니다 (ARM에서 Windows 10을 실행 하는 Surface Pro X 제외).

## DFCI를 사용 하 여 펌웨어 관리

Intune ( [공개 미리 보기](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)에서 사용 가능)에 장치 펌웨어 구성 인터페이스 (dfci) 프로필을 제공 함으로써 Surface uefi 관리는 최신 관리 스택을 UEFI 하드웨어 수준으로 확장 합니다. DFCI는 0 터치 프로비저닝을 지원 하 고, BIOS 암호를 제거 하 고, 시작 옵션 및 기본 제공 주변 장치를 포함 하 여 보안 설정 제어를 제공 하며 향후 고급 보안 시나리오를 위한 토대를 배치 합니다. 자세한 내용은 다음 문서를 참조하세요.

- [Surface UEFI 설정의 Intune 관리](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Intune에서 SURFACE UEFI 설정의 원격 관리를 발표](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)합니다.

## 배포 프로세스 업데이트 모범 사례

안정적인 환경을 유지 관리 하려면 최신 버전의 Windows 10과 함께 패리티를 유지 관리 하는 것이 좋습니다.  모범 사례 권장 사항은 [Windows 10 용 빌드 배포 링 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)를 참조 하세요.

## 다운로드 가능한 화면 업데이트 패키지

특정 버전의 Windows 10에는 각각 필요한 누적 드라이버와 Surface 장치에 대 한 펌웨어 업데이트가 모두 포함 된 별도의 .msi 파일이 있습니다. 업데이트 패키지에는 다음 구성 요소 중 일부 또는 모두가 포함 될 수 있습니다.

- Wi-Fi 및 LTE
- 비디오
- 고체 드라이브
- 시스템 집계 모듈 (SAM)
- 배터리
- 키보드 컨트롤러
- 포함 된 컨트롤러 (EC)
- 관리 엔진 (나)
- UEFI (통합 확장 가능 펌웨어 인터페이스)

### .Msi 파일 다운로드

1. Microsoft 다운로드 센터에서 [화면에 대 한 드라이버 및 펌웨어 다운로드](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) 를 찾습니다.
2. Surface model 및 Windows 버전과 일치 하는 .msi 파일 이름을 선택 합니다. .Msi 파일 이름에는 드라이버와 펌웨어를 설치 하는 데 필요한 최소 지원 Windows 빌드 번호가 포함 됩니다. 예를 들어 다음 그림을 참조 하세요. Windows 10 빌드 18362이 있는 Surface Book 2를 업데이트 하려면SurfaceBook2_Win10_18362_19.101.13994.msi를 선택 ** 합니다.** Windows 10 빌드 16299를 포함 하는 Surface Book 2의 경우 **SurfaceBook2_Win10_16299_1803509_3.msi**를 선택 합니다.

    ![그림 1. 화면 업데이트 다운로드](images/fig1-downloads-msi.png)

    *그림 1. 화면 업데이트 다운로드*

### Surface. msi 명명 규칙

2019 년 8 월, .msi 파일은 다음 명명 규칙을 사용 합니다.

- 버전 번호의 *제품*_*windows 릴리스*_*Windows 빌드 번호*_*버전 번호*_*(일반적으로 0)* 입니다.

**예**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

이 파일 이름에는 다음 정보가 제공 됩니다.

- **제품:** SurfacePro6
- **Windows 릴리스:** Win10
- **빌드:** 18362
- **버전:** 19.073.44195 – 파일이 생성 된 날짜와 시간이 다음과 같이 표시 됩니다.
  - **연도:** 19 (2019)
  - **월 및 주:** 073 (3 월 셋째 주)
  - **개월의 분:** 44195
- **버전 개정판:** 0 (이 버전의 첫 번째 릴리스)

### 레거시 Surface. msi 명명 규칙

레거시 .msi 파일 (8 월 2019 이전에 빌드된 파일)은 동일한 전체 명명 수식을 팔 로우 하지만 다른 메서드를 사용 하 여 버전 번호를 파생 합니다.

**예**

- SurfacePro6_Win10_16299_1900307_0.msi

이 파일 이름에는 다음 정보가 제공 됩니다.

- **제품:** SurfacePro6
- **Windows 릴리스:** Win10
- **빌드:** 16299
- **버전:** 1900307 – 파일을 만든 날짜와 릴리스 시퀀스에서의 위치가 다음과 같이 표시 됩니다.
  - **연도:** 19 (2019)
  - **릴리스 수:** 003 (연도의 세 번째 릴리스)
  - **제품 버전 번호:** 07 (surface pro 6은 정식 화면 pro의 일곱 번째 버전입니다.)
- **버전 개정판:** 0 (이 버전의 첫 번째 릴리스)

## 자세히 알아보기

- [Surface 용 드라이버 및 펌웨어 다운로드](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Configuration Manager에서 화면 드라이버 업데이트를 관리 하는 방법](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Configuration Manager를 사용 하 여 응용 프로그램 배포](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [끝점 구성 관리자 설명서](https://docs.microsoft.com/configmgr/)
- [Microsoft 배포 도구 키트 문서](https://docs.microsoft.com/configmgr/mdt/)
- [Microsoft Deployment Toolkit을 사용하여 Windows 10 배포](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Microsoft 배포 도구 키트를 사용 하 여 Windows 10을 Surface 장치에 배포](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Surface UEFI 설정의 Intune 관리](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Intune에서 SURFACE UEFI 설정의 원격 관리를 발표](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)합니다.
- [Windows10 업데이트 배포 링 빌드](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
