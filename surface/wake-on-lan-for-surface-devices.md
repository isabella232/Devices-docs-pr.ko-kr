---
title: Surface 장치에 대 한 Wake On LAN (Surface)
description: Wake on LAN을 사용 하 여 관리 또는 유지 관리 작업을 수행 하기 위해 원격으로 장치를 종료 하거나, 디바이스의 전원이 꺼져 있는 경우에도 관리 솔루션을 자동으로 사용 하도록 설정할 수 있는 방법에 대해 알아봅니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835511"
---
# Surface Configuration Manager에 대한 Wake On LAN

Windows 10, 버전 1607 (Windows 10 기념 업데이트 라고도 함) 이상을 실행 하는 surface 디바이스는 연결 된 대기 상태에서 Wake On LAN (WOL)을 사용할 수 있습니다. WOL을 사용 하면 관리 또는 유지 관리 작업을 수행 하도록 디바이스를 원격으로 종료 하거나 관리 솔루션 (예: Microsoft Endpoint Configuration Manager)을 자동으로 사용 하도록 설정할 수 있습니다. 예를 들어, 사무실이 비어 있는 경우 야간 모드의 창 중에 Microsoft 끝점 구성 관리자를 사용 하 여 surface Dock 또는 Surface Pro 3 도킹 스테이션과 도킹 된 Surface 장치에 응용 프로그램을 배포할 수 있습니다.

>[!NOTE]
>Surface 장치는 WOL을 지원 하기 위해 AC 전원 및 연결 된 대기 (절전)에 연결 되어야 합니다. 최대 절전 모드 또는 전원을 끄고 켠 장치에서는 WOL을 사용할 수 없습니다.

## 지원되는 디바이스

WOL에 대해 지원 되는 장치는 다음과 같습니다.

* Surface Ethernet 어댑터
* Surface USB-C ~ 이더넷 및 USB 어댑터
* Surface 도크
* Surface Pro 3의 surface 도킹 스테이션
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (다섯째 Gen)
* LTE Advanced를 사용 하는 Surface Pro (다섯 번째 Gen)
* Surface Book
* Surface 노트북 (첫번째 Gen)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go LTE Advanced
* Surface Studio 2 (아래 Surface Studio 2 지침 참조)
* Surface Pro 7
* Surface 노트북 3

## WOL 드라이버

Surface 장치에서 WOL 지원을 사용 하도록 설정 하려면 Surface Ethernet 어댑터에 대 한 특정 드라이버가 필요 합니다. 이 드라이버는 Surface 장치에 대 한 표준 드라이버 및 펌웨어 팩에 포함 되어 있지 않습니다.-별도로 다운로드 하 여 설치 해야 합니다. Microsoft 다운로드 센터의 [IT 페이지 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 surface WOL 드라이버 (SurfaceWOL.msi)를 다운로드할 수 있습니다.

Surface 장치에서이 Microsoft Windows Installer (.msi) 파일을 실행 하 여 Surface WOL 드라이버를 설치 하거나, Microsoft 끝점 구성 관리자와 같은 응용 프로그램 배포 솔루션을 사용 하 여 Surface 디바이스에 배포할 수 있습니다. 배포 중에 Surface WOL 드라이버를 포함 하려면 배포 프로세스 중에 .msi 파일을 응용 프로그램으로 설치할 수 있습니다. 배포 프로세스에 포함할 Surface WOL 드라이버 파일을 추출할 수도 있습니다. 예를 들어, MDT (Microsoft Deployment Toolkit) 배포 공유에 포함 시킬 수 있습니다. Windows 10 배포의 MDT를 사용 하 여 Surface 배포에 대 한 자세한 내용은 [Microsoft 배포 툴킷를 사용 하 여 surface 디바이스에](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)참조 하세요.

> [!NOTE]
> SurfaceWOL.msi를 설치 하는 동안 다음 레지스트리 키 값이 1로 설정 되어 있는 경우 WOL 드라이버가 설치 된 시스템을 쉽게 식별할 수 있습니다. 배포 중에 별도로 드라이버를 추출 하 고 설치 하도록 선택한 경우이 레지스트리 키가 구성 되지 않으며 수동으로 또는 스크립트를 사용 하 여 구성 해야 합니다.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

SurfaceWOL.msi의 내용을 추출 하려면 다음 예제와 같이 MSIExec 관리 설치 옵션 (**/a**)을 사용 하 여 C:\WOL\ 폴더에 콘텐츠를 추출 합니다.

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Surface Studio 2 지침

Surface Studio 2에서 WOL을 사용 하도록 설정 하려면 다음 절차를 사용 해야 합니다.

1. 다음 레지스트리 키를 만듭니다.

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. 다음 명령을 실행 합니다.

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Surface WOL 사용

Surface WOL 드라이버는 장치가 매직 패킷으로 알려진 특별 한 네트워크 통신을 통해 woken 하는 WOL 표준을 준수 합니다. 매직 패킷은 6 바이트의 255 (또는 16 진수로 FF)로 구성 되 고 대상 컴퓨터의 MAC 주소에 대 한 16 회 반복 됩니다. 마법의 패킷과, [위키백과](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)의 WOL 표준에 대해 자세히 읽어 볼 수 있습니다.

>[!NOTE]
>자동 패킷을 보내고 WOL을 사용 하 여 디바이스를 깨우기 하려면 대상 디바이스 및 이더넷 어댑터의 MAC 주소를 알아야 합니다. 매직 패킷에서는 IP 네트워크 프로토콜을 사용 하지 않기 때문에 장치의 IP 주소 또는 DNS 이름을 사용할 수 없습니다.

구성 관리자와 같은 대부분의 관리 솔루션은 WOL에 대 한 기본 제공 지원을 제공 합니다. 또한 Microsoft Store 앱, PowerShell 모듈, 타사 응용 프로그램, 그리고 장치를 종료 하는 데 매직 패킷을 보낼 수 있는 타사 관리 솔루션 등 다양 한 솔루션이 있습니다. 예를 들어 TechNet 스크립트 센터에서 [Wake ON LAN PowerShell 모듈](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) 을 사용할 수 있습니다. 

>[!NOTE]
>장치가 매직 패킷으로 woken 된 후에는 응용 프로그램이 시스템에서 절전 모드를 방해 하지 않는 경우 또는 AllowSystemRequiredPowerRequests 레지스트리 키가 1로 구성 되지 않은 경우 응용 프로그램이 절전 모드를 막을 수 있도록 장치가 절전 모드로 돌아갑니다. 이 레지스트리 키에 대 한 자세한 내용은이 문서의 [WOL 드라이버](#wol-driver) 섹션을 참조 하세요.
