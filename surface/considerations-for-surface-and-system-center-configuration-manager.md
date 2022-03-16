---
title: Surface 및 Surface에 대한 고려 Microsoft Endpoint Configuration Manager
description: Configuration Manager를 통해 Surface 디바이스의 관리 및 배포는 기본적으로 다른 PC와 동일합니다. 이 문서에서는 추가 고려 사항이 필요할 수 있는 시나리오에 대해 설명합니다.
keywords: 관리, 배포, 업데이트, 드라이버, 펌웨어
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 08/12/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 88d25786601bdb88c027b689431d1c08c80cb9ec
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448341"
---
# <a name="considerations-for-surface-and-microsoft-endpoint-configuration-manager"></a>Surface 및 Surface에 대한 고려 Microsoft Endpoint Configuration Manager

기본적으로 Microsoft Endpoint Configuration Manager Surface 디바이스의 관리 및 배포는 다른 PC의 관리 및 배포와 동일합니다. 다른 PC와 마찬가지로 Surface 디바이스 배포에는 드라이버 가져오기, Windows 이미지 가져오기, 배포 작업 순서 준비, 컬렉션에 작업 순서 배포가 포함됩니다. 배포 후 Surface 장치는 다른 Windows 클라이언트와 같습니다. 앱, 설정 및 정책을 게시하려면 다른 디바이스에 사용하는 프로세스와 동일한 프로세스를 사용합니다.

자세한 내용은 설명서를 [Microsoft Endpoint Configuration Manager 참조하세요](/mem/configmgr/).

Surface 디바이스의 배포 및 관리는 기본적으로 다른 PC와 유사하기는 하지만 일부 시나리오에서는 이 문서에 설명된 바와 같이 추가 IT 작업이 필요할 수 있습니다. 

> [!TIP]
> Surface 디바이스[를 관리하기 Microsoft Endpoint Configuration Manager](/mem/configmgr/core/servers/manage/updates) 현재 분기를 사용할 수 있습니다.

## <a name="update-surface-device-drivers-and-firmware"></a>Surface 디바이스 드라이버 및 펌웨어 업데이트

Configuration Manager 또는 WSUS(구성 관리자)를 사용하여 장치 드라이버 및 펌웨어를 Windows Server Update Services Surface 드라이버 및 펌웨어 업데이트 관리를 [참조하세요](manage-surface-driver-and-firmware-updates.md).

## <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Surface Ethernet 어댑터 및 Configuration Manager 배포

Configuration Manager가 배포 중에 장치를 식별하는 데 사용하는 기본 메커니즘은 MAC(미디어 액세스 제어) 주소입니다. MAC 주소는 이더넷 컨트롤러와 연결되어 있기 때문에 여러 장치 간 공유되는 이더넷 어댑터로 인해 Configuration Manager가 각 장치를 단일 장치로 식별하여 배포에 실패하게 됩니다. 

배포 중에 동일한 이더넷 어댑터를 사용하는 Surface 장치가 고유한 장치로 식별되도록 구성 관리자에게 다른 방법을 사용하여 디바이스를 식별하도록 지시할 수 있습니다. 중복 하드웨어 식별자 관리에 설명된 따라 Configuration Manager에서 다른 식별 방법을 사용하게 [지정할 수 있습니다](/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers).

- Surface Ethernet 어댑터의 MAC 주소에 대한 제외를 추가합니다. 이 경우 Configuration Manager는 시스템 UUID의 기본 설정에서 MAC 주소를 간과해야 합니다.

- 스크립트를 사용하여 무선 어댑터의 MAC 주소로 새로 배포된 Surface 디바이스를 식별합니다.

### <a name="surface-ethernet-driver"></a>Surface Ethernet 드라이버

2016년 이후로 Surface Ethernet 어댑터용 드라이버는 기본적으로 Windows IT 구성이 필요 없습니다. 드라이버에 포함하기 Windows 10 Microsoft 다운로드 센터에서 더 이상 드라이버를 다운로드할 수 없습니다. 이전 버전의 Windows 10 Pro 배포해야 하는 경우 Microsoft 업데이트 카탈로그에서 최신 드라이버를 다운로드[할 수 있습니다](https://www.catalog.update.microsoft.com/Search.aspx?q=surface%20ethernet%20drivers).

## <a name="deploy-surface-app-with-configuration-manager"></a>Configuration Manager를 통해 Surface 앱 배포

릴리스가 비즈니스용 Microsoft Store Surface 앱은 더 이상 드라이버 및 펌웨어 다운로드로 사용할 수 없습니다. Surface 앱을 관리되는 Surface 디바이스에 배포하거나 Configuration Manager를 통해 배포하는 조직은 먼저 Surface 앱을 취득해야 비즈니스용 Microsoft Store. 자세한 내용은 [Surface](deploy-surface-app-with-windows-store-for-business.md) 앱 배포를 비즈니스용 Microsoft Store.

## <a name="use-prestaged-media-with-surface-clients"></a>Surface 클라이언트에서 미리 준비된 미디어 사용

조직에서 Configuration Manager를 사용하여 배포하기 전에 미리 준비된 미디어를 사용하여 컴퓨터로 배포 리소스를 로드하는 경우 UEFI 장치로 Surface 장치의 특성에 따라 추가 단계를 수행해야 할 수 있습니다. 특히 기본 UEFI 환경에서는 시스템의 부팅 디스크에 여러 파티션을 만들어야 합니다. 미리 준비된 미디어에 대한 설명서[](/mem/configmgr/osd/deploy-use/create-prestaged-media)를 따라 진행하는 경우 지침은 단일 파티션 부팅 디스크에만 제공하므로 Surface 디바이스에 적용하면 오류가 발생합니다.

Surface 디바이스와 같은 UEFI 장치에 미리 준비된 미디어를 적용하는 방법에 대한 지침은 시스템 블로그 게시물의 BIOS 또는 UEFI PC용 다중 분할된 디스크에 Task [Sequence Prestaged Media](https://techcommunity.microsoft.com/t5/configuration-manager-archive/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned/ba-p/392239) 를 적용하는 방법 블로그 게시물에서 찾을 수 있습니다.

## <a name="licensing-conflicts-with-oem-activation-30"></a>OEM 정품 인증 3.0과 라이선스 충돌

Surface 디바이스는 사용이 허가된 디바이스 복사본과 함께 Windows. 사전 설치한 이 Windows 라이선스 키는 OEM 정품 인증 [3.0(OA 3.0](/windows-hardware/manufacture/desktop/oem-activation-3))이 있는 장치의 펌웨어에 포함되어 있습니다. OA Windows 사용하여 디바이스에서 Windows 설치 미디어를 실행하면 설치 프로그램이 Windows 자동으로 라이선스 키를 읽고 라이선스 키를 사용하여 설치 및 정품 인증을 Windows. 사용자가 라이선스 키를 찾거나 입력할 Windows 것이 아니기 때문에 대부분의 경우 이 방법을 사용하면 설치를 간소화할 수 있습니다.

이 라이선스 키를 사용하여 장치를 다시 Windows Enterprise 포함된 라이선스 키로 인해 충돌이 발생하지는 않습니다. 이는 Windows Enterprise 설치 미디어가 Enterprise 버전만 설치하도록 Windows 시스템 펌웨어에 포함된 라이선스 키와 비호칭적이기 때문에 그렇습니다. 키 관리 서비스[KMS] 또는 Active Directory 기반 정품 인증을 사용하여 정품 인증하려는 경우와 같이 제품 키를 지정하지 않으면 해당 기술 중 하나에서 정품 인증을 Windows 때까지 GVLK(일반 볼륨 라이선스 키)가 사용됩니다.

그러나 조직에서 펌웨어 포함 키와 호환되는 Windows 버전을 사용하려는 경우 문제가 발생할 수 있습니다. 예를 들어 Windows 10 Pro Windows 10 Home 함께 배송된 장치에 Windows 10 Pro 설치하려는 조직은 Windows 설치 중에 Home edition 키를 자동으로 읽고 홈 에디션 키로 설치하는 Windows 10 Home 발생할 수 있습니다. Windows 10 Pro. 이러한 충돌을 방지하려면 Ei.cfg 또는 Pid.txt 파일을 사용하여 제품 키를 Windows 설치에 명시적으로 지시하거나 배포 작업 순서에 특정 제품 키를 입력합니다. 자세한 내용은 Setup [Edition Windows 제품 ID 파일을 참조하세요](/windows-hardware/manufacture/desktop/windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt). 특정 키가 없는 경우 해당 키에 기본 제품 키를 사용할 Windows. 자세한 내용은 [Deploy Windows 10](/windows/deployment/deploy).

## <a name="apply-an-asset-tag-during-deployment"></a>배포 중 자산 태그 적용

[Surface 자산 태그 도구를](assettag.md) 사용하면 운영 체제가 실패한 경우에도 UEFI에서 장치를 식별할 수 있습니다. Configuration Manager를 통해 자산 관리에 대한 자세한 내용은 Configuration Manager의 자산 인텔리전스 [소개를 참조합니다](/mem/configmgr/core/clients/manage/asset-intelligence/introduction-to-asset-intelligence).

## <a name="configure-push-button-reset"></a>원스위치 재설정 구성

Surface Windows 배포할 때 Windows 단추 재설정 기능은 기본적으로 환경을 아직 구성하지 않은 상태로 다시 되돌리도록 구성됩니다. 재설정 함수를 사용하는 경우 시스템은 설치된 응용 프로그램 및 설정을 삭제합니다. 경우에 따라 응용 프로그램 및 설정이 없는 상태로 시스템을 복원하는 것이 유용할 수 있습니다. 그러나 전문 환경에서는 최종 사용자가 시스템을 사용할 수 없습니다.

그러나 최종 사용자가 사용할 준비가 된 상태로 시스템 구성을 복원하기 위해 원스위치 재설정을 구성할 수 있습니다. 원스위치 초기화 기능 배포에 설명된 프로세스에 [따라](/windows-hardware/manufacture/desktop/deploy-push-button-reset-features) 장치에 대한 원스위치 초기화 환경을 사용자 지정합니다.
