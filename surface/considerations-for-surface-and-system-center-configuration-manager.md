---
title: Surface 및 Microsoft 끝점 구성 관리자에 대 한 고려 사항
description: 구성 관리자를 사용 하 여 Surface 장치를 관리 하 고 배포 하는 것은 기본적으로 다른 PC와 동일 합니다. 이 문서에서는 추가 고려 사항이 필요할 수 있는 시나리오에 대해 설명 합니다.
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
ms.openlocfilehash: 4fa62d227deb0b0b07fa0fbc6552ea5b04c1b87b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834732"
---
# Surface 및 Microsoft 끝점 구성 관리자에 대 한 고려 사항

기본적으로 Microsoft Endpoint Configuration Manager를 사용 하 여 Surface 장치를 관리 하 고 배포 하는 것은 다른 PC의 관리 및 배포와 동일 합니다. 다른 PC와 마찬가지로 Surface 장치에 대 한 배포에는 드라이버 가져오기, Windows 이미지 가져오기, 배포 작업 순서 준비, 컬렉션에 작업 순서 배포 등이 포함 됩니다. 배포 후 Surface 디바이스는 다른 Windows 클라이언트와 유사 합니다. 앱, 설정 및 정책을 게시 하려면 다른 장치에 대해 사용 하는 것과 동일한 프로세스를 사용 합니다.

Configuration Manager를 사용 하 여 [Microsoft 끝점 구성 관리자에 대 한 설명서](https://docs.microsoft.com/sccm/index)에서 장치를 배포 하 고 관리 하는 방법에 대 한 자세한 내용은를 참조 하세요.

Surface 디바이스의 배포 및 관리는 기본적으로 다른 PC와 동일 하지만 추가 고려 사항이 나 단계가 필요할 수 있는 몇 가지 시나리오가 있습니다. 이 문서에서는 이러한 시나리오에 대 한 설명과 지침을 제공 합니다. 이 문서에 설명 된 해결 방법은 다른 장치 및 제조업체에도 적용 될 수 있습니다.

> [!NOTE]
> Surface 디바이스 관리의 경우 Microsoft 끝점 구성 관리자의 현재 분기를 사용 하는 것이 좋습니다.

## Surface 디바이스 드라이버 및 펌웨어 업데이트

Windows Update를 통해 업데이트를 수신 하는 디바이스의 경우 Surface 구성 요소의 드라이버와 펌웨어 업데이트는 Windows 업데이트 프로세스의 일부로 자동으로 적용 됩니다. WSUS (Windows Server Update Services) 또는 Configuration Manager를 통해 업데이트 된 업데이트 등의 관리 되는 장치는 [Surface driver 및 펌웨어 업데이트 관리](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates/)를 참조 하세요.

> [!NOTE]
> Surface 디바이스 드라이버와 펌웨어는 SHA-256으로 서명 되며,이는 Windows Server 2008 R2에서 기본적으로 지원 되지 않습니다. 해결 방법은 Windows Server 2008 R2에서 실행 되는 Configuration Manager 환경에서 사용할 수 있습니다. 자세한 내용은 [Microsoft Endpoint Configuration Manager (KB3025419)에 드라이버를 가져올 수 없음](https://support.microsoft.com/kb/3025419)을 참조 하세요.

## Surface Ethernet 어댑터 및 Configuration Manager 배포

배포 중에 구성 관리자가 장치를 식별 하는 데 사용 되는 기본 메커니즘은 MAC (미디어 액세스 제어) 주소입니다. MAC 주소는 이더넷 컨트롤러와 연결 되어 있으므로 여러 장치에서 공유 되는 이더넷 어댑터는 구성 관리자가 각 장치를 단일 장치로 식별 하도록 합니다. 이로 인해 Windows의 Configuration Manager 배포가 의도 된 장치에 적용 되지 않을 수 있습니다.

배포 중에 동일한 이더넷 어댑터를 사용 하는 Surface 장치가 고유한 장치로 식별 되도록 하기 위해 구성 관리자에 게 다른 방법을 사용 하 여 디바이스를 식별 하도록 지시할 수 있습니다. 이 다른 방법은 무선 네트워크 어댑터의 MAC 주소 또는 시스템 유니버설 고유 식별자 (시스템 UUID) 일 수 있습니다. 다음 옵션을 사용 하 여 Configuration Manager에서 다른 식별 방법을 사용 하도록 지정할 수 있습니다.

* [Microsoft Endpoint Configuration MANAGER OSD 블로그 post에서 여러 PXE 시작 배포에 대해 동일한 NIC](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) 를 다시 사용 하는 방법에 명시 된 것 처럼 Configuration Manager가 시스템 UUID의 mac 주소를 간과 하도록 강제 설정 하는 Surface Ethernet 어댑터의 mac 주소에 대 한 제외를 추가 합니다.

* [Microsoft Endpoint Configuration MANAGER OSD 블로그 post에서 여러 PXE 시작 배포에 대해 동일한 NIC](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) 다시 사용에 설명 된 대로 시스템 UUID에의 한 준비 장치입니다.

* 스크립트를 사용 하 여 [여러 SCCM OSD 블로그 게시물에 대해 동일한 외부 이더넷 어댑터를 사용](https://blogs.technet.microsoft.com/askpfeplat/2014/07/27/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm-osd/) 하는 방법에 명시 된 대로 무선 어댑터의 MAC 주소로 새로 배포 된 Surface 장치를 식별 합니다.

구성 관리자를 사용 하 여 배포 하는 동안 Surface Ethernet 어댑터에 대 한 또 다른 고려 사항은 이더넷 컨트롤러용 드라이버입니다. Windows 10, 버전 1511에서 시작 하는 Surface Ethernet 어댑터용 드라이버는 Windows에 기본적으로 포함 되어 있습니다. 최신 버전의 Windows 10을 배포 하 고 최신 버전의 WinPE를 사용 하려는 조직의 경우 Surface Ethernet 어댑터를 사용 하는 데 추가 작업이 필요 하지 않습니다.

Windows 10, 버전 1511 (Windows 10 RTM 및 Windows 8.1 포함) 이전 버전의 경우 Surface Ethernet 어댑터 드라이버를 설치 하 고 WinPE 부팅 미디어에 드라이버를 포함 해야 할 수 있습니다. Windows 10에 포함 된 드라이버는 Microsoft 다운로드 센터에서 더 이상 다운로드할 수 없습니다. Surface Ethernet 어댑터 드라이버를 다운로드 하려면, 핵심 팀 소개 블로그에서 [Surface Ethernet Drivers](https://blogs.technet.microsoft.com/askcore/2016/08/18/surface-ethernet-drivers/) 블로그 게시물에 명시 된 대로 Microsoft Update 카탈로그에서 다운로드 하세요.

## Configuration Manager를 사용 하 여 Surface 앱 배포

Microsoft Store for Business를 사용 하는 경우 Surface 앱을 더 이상 드라이버 및 펌웨어 다운로드로 사용할 수 없습니다. Surface app을 관리 되는 Surface 장치에 배포 하거나 구성 관리자를 사용 하 여 배포 하는 경우 비즈니스를 위해 Microsoft Store를 통해 Surface 앱을 얻은 다음 PowerShell을 사용 하 여 Surface 앱을 배포 해야 합니다. Surface 앱 배포에 대 한 PowerShell 명령, surface 앱을 다운로드 하는 지침, TechNet 라이브러리의 [Microsoft Store 비즈니스](https://technet.microsoft.com/itpro/surface/deploy-surface-app-with-windows-store-for-business) 문서를 포함 하는 surface app의 Microsoft Store 비즈니스 스토어의 필수 구성 요소 프레임 워크를 찾을 수 있습니다.

## Surface 클라이언트에서 미리 준비 되어 있는 미디어 사용

조직에서 사전 준비 된 미디어를 사용 하 여 구성 관리자를 통해 배포 하기 전에 컴퓨터에 배포 리소스를 미리 로드 하는 경우, Surface 디바이스의 특성으로 인해 추가 단계를 수행 해야 할 수 있습니다. 특히 네이티브 UEFI 환경에서는 시스템의 부팅 디스크에 파티션을 여러 개 만들어야 합니다. [사전 준비 된 미디어에 대 한 설명서](https://technet.microsoft.com/library/79465d90-4831-4872-96c2-2062d80f5583?f=255&MSPPError=-2147217396#BKMK_CreatePrestagedMedia)를 팔 로우 하는 경우에는 단일 파티션 부팅 디스크에 대 한 명령도 제공 하므로 Surface 디바이스에 적용 되는 경우에는 실패 합니다.

Surface 디바이스와 같은 UEFI 장치에 미리 준비 된 미디어를 적용 하는 방법에 대 한 지침은 [Microsoft Endpoint Configuration Manager 블로그 게시물의 다중 분할 디스크에서 BIOS 또는 UEFI pc 용 작업 순서 미리 준비 된 미디어를 적용 하는 방법](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2014/04/02/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned-disks-for-bios-or-uefi-pcs-in-system-center-configuration-manager/) 에 나와 있습니다.

## OEM 정품 인증 3.0의 라이선스 충돌

Surface 디바이스는 Windows의 라이선스가 있는 복사본으로 사전 설치 되어 있습니다. 예를 들어 Surface Pro 4는 Windows 10 Professional을 사용 하 여 미리 설치 되어 있습니다. 이 사전 설치 된 Windows 복사본의 라이선스 키는 OEM 정품 인증 3.0 (OA 3.0)을 사용 하 여 디바이스의 펌웨어에 포함 되어 있습니다. OA 3.0 키를 사용 하 여 디바이스에서 Windows 설치 미디어를 실행 하면 Windows 설치 프로그램이 자동으로 라이선스 키를 읽고이를 사용 하 여 Windows를 설치 하 고 정품 인증 합니다. 대부분의 경우 사용자가 라이선스 키를 찾거나 입력할 필요가 없기 때문에 Windows를 다시 설치 하는 것이 단순해 집니다.

Windows Enterprise를 사용 하 여 장치를 이미지로 삽입 하면이 포함 된 라이선스 키로 인해 충돌이 발생 하지 않습니다. Windows Enterprise 용 설치 미디어는 Windows의 엔터프라이즈 버전만 설치 하도록 구성 되어 있으므로 시스템 펌웨어에 포함 된 라이선스 키와 호환 되지 않기 때문입니다. 제품 키가 지정 되지 않은 경우 (예: KMS (키 관리 서비스) 또는 Active Directory 기반 정품 인증을 사용 하려는 경우) 이러한 기술 중 하나에 의해 Windows가 활성화 될 때까지 GVLK (일반 볼륨 라이선스 키)가 사용 됩니다.

그러나 조직에서 펌웨어 포함 키와 호환 되는 버전의 Windows를 사용 하려고 할 때 문제가 발생할 수 있습니다. 예를 들어 windows 10 Home edition과 함께 제공 되는 Surface 3 장치에 Windows 10 Professional을 설치 하려는 조직은 설치 중에 Windows 설치 시 Home edition 키를 자동으로 읽을 때 문제가 발생할 수 있으며,이 경우에는 Professional이 아닌 Home edition으로 설치 됩니다. 이러한 충돌을 방지 하려면 Ei 또는 Pid.txt 파일을 사용 하 여 Windows 설치 프로그램이 제품 키를 묻는 메시지를 표시 하도록 명시적으로 지시할 수 있고, 배포 작업 순서에 특정 제품 키를 입력할 수도 있습니다. 자세한 내용은 [Windows 설치 에디션 구성 및 제품 ID 파일](https://technet.microsoft.com/library/hh824952.aspx)을 참조 하세요. 특정 키가 없는 경우 windows 용 기본 제품 키를 사용 하 여 디바이스 파트너 센터의 [windows 10 운영 체제 사용자 지정 및 배포](https://dpcenter.microsoft.com/en/Windows/Build/cp-Windows-10-build) 에서 찾을 수 있습니다.

## 배포 중 자산 태그 적용

Surface Studio, Surface Book, Surface Pro 4, Surface Pro 3 및 Surface 3 장치는 모두 UEFI의 자산 태그 응용 프로그램을 지원 합니다. 이 자산 태그는 운영 체제에 오류가 발생 해도 UEFI에서 디바이스를 식별 하는 데 사용할 수 있으며, 운영 체제 내 에서도 쿼리할 수 있습니다. Surface Asset Tag 함수에 대 한 자세한 내용을 보려면 [Surface Pro 3 블로그 게시물에 대 한 자산 태그 도구](https://blogs.technet.microsoft.com/askcore/2014/10/20/asset-tag-tool-for-surface-pro-3/) 를 참조 하세요.

Configuration Manager 배포 작업 순서 중에 [Surface Asset TAG CLI 유틸리티](https://www.microsoft.com/download/details.aspx?id=44076) 를 사용 하 여 자산 태그를 적용 하려면 [구성 관리자 작업 순서 블로그 게시물에서 Surface asset 태그 설정](https://blogs.technet.microsoft.com/jchalfant/set-surface-pro-3-asset-tag-during-a-configuration-manager-task-sequence/) 에 있는 스크립트와 지침을 사용 합니다.

## 밀기 단추 재설정 구성

Surface 장치에 Windows를 배포 하는 경우 Windows의 푸시 단추 다시 설정 기능은 기본적으로 시스템을 환경이 아직 구성 되지 않은 상태로 다시 되돌리기 위해 구성 됩니다. Reset 함수를 사용 하는 경우 시스템은 설치 된 모든 응용 프로그램 및 설정을 무시 합니다. 일부 경우에는 응용 프로그램 및 설정이 없는 상태로 시스템을 복원 하는 것이 유용할 수 있지만, 전문 환경에서는 최종 사용자가 시스템을 사용할 수 없도록 효과적으로 렌더링 하는 것이 좋습니다.

단, 시스템 구성을 최종 사용자가 사용할 준비가 된 상태로 복원 하기 위해 누름-버튼 재설정을 구성할 수 있습니다. 장치에 대 한 푸시 단추 다시 설정 기능을 사용자 지정 하려면 [푸시 단추를 배포](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/deploy-push-button-reset-features) 하는 방법에 설명 된 프로세스를 따릅니다.
