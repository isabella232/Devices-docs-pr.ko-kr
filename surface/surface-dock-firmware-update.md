---
title: Microsoft Surface Dock 1 펌웨어 업데이트
description: 이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용하여 원래 Surface Dock 1에 펌웨어를 설치하고 관리하는 방법을 설명합니다. Surface 디바이스에 설치하면 Surface 디바이스에 연결된 Surface Dock 1 디바이스가 업데이트됩니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 2/08/2021
ms.openlocfilehash: 544aa8ab7cb9bb443f368bfbbcecb1fa256d32c5
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708759"
---
# <a name="surface-dock-1-firmware-update"></a>Surface Dock 1 펌웨어 업데이트

이 문서에서는 Microsoft Surface Dock 1 펌웨어 업데이트를 사용하여 원래 Surface Dock 1의 펌웨어를 설치하고 관리하는 방법을 설명합니다. Surface 디바이스에 설치하면 Surface 디바이스에 연결된 Surface Dock 1 디바이스가 업데이트됩니다.

> [!NOTE]
> 이 문서는 Windows 또는 업데이트 또는 기타 MSI 배포 도구를 사용하여 Microsoft Endpoint Configuration Manager 수신하는 [Surface Dock 2에는](surface-dock-whats-new.md)적용되지 않습니다.

이 도구는 이전에 IT용 Surface 도구의 일부로 다운로드할 수 있는 이전 Microsoft Surface Dock Updater 도구를 능가합니다. 이전 도구의 이름이 Surface_Dock_Updater_vx.xx.xxx.x.msi(여기서 x는 버전 번호를 나타임)로 이름이 지정되어 있으며 더 이상 다운로드할 수 없습니다.

> [!IMPORTANT]
> 이 문서에는 IT 관리자를 위한 기술 지침이 포함되어 있습니다. 가정적 사용자인 경우 Microsoft 지원 사이트에서 [Surface Dock 펌웨어를](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)업데이트하는   방법을 참조하세요. 지원 사이트의 지침은 아래 일반 설치 단계와 동일하지만 이 문서에는 네트워크의 여러 장치에 업데이트를 모니터링, 확인 및 배포하기 위한 추가 정보가 있습니다.

## <a name="install-surface-dock-1-firmware-update"></a>Surface Dock 1 펌웨어 업데이트 설치

이 섹션에서는 Surface Dock 1에 펌웨어 업데이트를 수동으로 설치하는 방법을 설명합니다.

> [!TIP]
> Microsoft는 주기적으로 새 버전의 Surface Dock 1 펌웨어 업데이트를 릴리스합니다. MSI 파일이 자체 업데이트되지 않습니다. Surface 디바이스에 MSI를 배포하고 새 버전의 펌웨어가 릴리스된 경우 새 버전을 배포해야 합니다.

1. [IT용 Surface Tools로 이동하여](https://www.microsoft.com/download/details.aspx?id=46703) .msi 파일(Surface_Dock_FwUpdate.)을 다운로드하여 **설치한**다음 적절한 버전을 설치합니다. X를 실행하는 Surface Pro **.arm64 빌드를 다운로드합니다.** 다른 모든 디바이스의 경우 **.amd64 빌드를** 사용 합니다.  

    - 업데이트하려면 버전 1803 이상에서 Windows 10 Surface 디바이스가 필요합니다.
    - MSI 파일을 설치하면 Surface를 다시 시작하라는 메시지가 표시될 수 있습니다. 그러나 업데이트를 수행하는 데는 다시 시작할 필요는 없습니다.

2. Surface Dock에서 Surface 디바이스를 분리하고 ~5초간 기다렸다가 다시 연결합니다. Surface Dock 1 펌웨어 업데이트는 백그라운드에서 자동으로 도킹을 업데이트합니다. 프로세스가 완료되는 데 몇 분 정도 걸릴 수 있으며 중단된 경우에도 계속됩니다.

## <a name="monitor-the-surface-dock-1-firmware-update"></a>Surface Dock 1 펌웨어 업데이트 모니터링

이 섹션은 선택 사항이며 펌웨어 업데이트 설치를 모니터링하는 방법에 대한 개요를 제공합니다.

업데이트를 모니터링하는 경우:

1. 이벤트 뷰어를 열고 Windows **Logs > Application으로**이동한 **** 다음 오른쪽 창의 작업에서 현재 로그 필터링을 클릭하고 이벤트 원본 **** 옆에 **SurfaceDockFwUpdate를** 입력한 다음 확인을 **클릭합니다.** ****

2. 상승된 명령 프롬프트에 다음 명령을 입력합니다.

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```

3. 이 문서의 다음 섹션에 설명된 [바와 같이 업데이트를](#install-surface-dock-1-firmware-update) 설치합니다.

4. 다음 텍스트가 있는 이벤트 2007은 업데이트 성공을 나타냅니다. 펌웨어 업데이트가 **완료되었습니다. hr=0 DriverTelementry EventCode = 2007**.

   업데이트가 성공하지 못하면 이벤트 ID 2007이 정보 대신 **Error** 이벤트로 **표시됩니다.** 또한 Windows 레지스트리에 보고된 버전이 최신 버전이 아되지 않습니다.

5. 업데이트가 완료되면 업데이트된 DWORD 값이 현재 버전의 도구에 해당하는 Windows 레지스트리에 표시됩니다. 자세한 [내용은](#versions-reference) 이 문서의 버전 참조 섹션을 참조하세요. 예를 들어 다음과 같은 가치를 제공해야 합니다.

    - Component10CurrentFwVersion 0x04ac3970(78395760)
    - Component20CurrentFwVersion 0x04915a70(76634736)

>[!TIP]
>이벤트 텍스트에 "원본 SurfaceDockFwUpdate의 이벤트 ID xxxx에 대한 설명을 찾을 수 없습니다."가 표시될 경우 이는 예상되는 것이고 무시해도 됩니다.

이 문서의 다음 섹션도 참조하세요.

- [펌웨어 업데이트 완료를 확인하는 방법](#how-to-verify-completion-of-the-firmware-update)
  - [이벤트 로깅](#event-logging)
  - [문제 해결 팁](#troubleshooting-tips)
  - [버전 참조](#versions-reference)

## <a name="network-deployment"></a>네트워크 배포

설치 관리자 Windows (Msiexec.exe)를 사용하여 네트워크에서 여러 장치에 Surface Dock 1 펌웨어 업데이트를 배포할 수 있습니다. 설치 Microsoft Endpoint Configuration Manager 또는 기타 배포 도구를 사용할 때 다음 구문을 입력하여 설치가 자동으로 진행되도록 합니다.

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart**

예를 들어 다음과 같은 가치를 제공해야 합니다.

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> 로그 파일은 기본적으로 만들어지지 않습니다. 로그 파일을 만들하려면 "/l*v [path]"를 추가해야 합니다. 예: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"

자세한 내용은 명령줄 옵션 [설명서를 참조하십시오.](/windows/win32/msi/command-line-options)

> [!IMPORTANT]
> 다른 방법을 사용하여 Surface Dock를 업데이트된 것으로 유지하려는 경우 자세한 내용은 [Update your Surface Dock을](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 참조합니다.

## <a name="intune-deployment"></a>Intune 배포

Intune을 사용하여 Surface Dock 1 펌웨어 업데이트를 장치에 배포할 수 있습니다. 먼저 Intune 독립 실행형 - Win32 앱 관리 설명서에 설명된 바와 같이 MSI 파일을 .intunewin 형식으로 [변환해야 합니다.](/intune/apps/apps-win32-app-management)

다음 명령을 사용 합니다.

- **msiexec /i \<path to msi file\> /quiet /q**

## <a name="how-to-verify-completion-of-the-firmware-update"></a>펌웨어 업데이트 완료를 확인하는 방법

Surface Dock 펌웨어는 다음 두 가지 구성 요소로 구성됩니다.

- **Component10:** MCU(마이크로 컨트롤러 단위) 펌웨어
- **Component20:** DP(디스플레이 포트) 펌웨어.

Surface Dock 1 펌웨어 업데이트를 성공적으로 완료하면 이러한 펌웨어 구성 요소에 대한 새 레지스트리 키 값이 표시됩니다.

### <a name="to-verify-updates"></a>업데이트를 확인

1. Regedit를 열고 다음 레지스트리 경로로 이동합니다.

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. 레지스트리 키 **Component10CurrentFwVersion 및 Component20CurrentFwVersion**를 찾아서 현재 장치에 있는 펌웨어를 참조합니다.

   ![Surface Dock 1 펌웨어 업데이트 설치 프로세스](images/regeditDock.png)

3. 새 레지스트리 키 값이 이 문서 끝부분의 버전 참조에 나열된 업데이트된 레지스트리 키 값과 일치하는지 확인해야 합니다. 값이 일치하면 펌웨어가 성공적으로 업데이트되었습니다.

4. 확인할 수 없는 경우 다음 섹션의 이벤트 로깅 및 문제 해결 팁을 검토합니다.

## <a name="event-logging"></a>이벤트 로깅

### <a name="table-1-log-files-for-surface-dock-1-firmware-update"></a>표 1. Surface Dock 1 펌웨어 업데이트 로그 파일

| Log                              | 위치                               | 참고                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Dock 1 펌웨어 업데이트 로그 | 경로를 지정해야 합니다(참고 참조). | 이 도구의 이전 버전은 응용 프로그램 및 서비스 로그\Microsoft Surface Dock Updater에 이벤트를 기록합니다.                                                                                                  |
| Windows 장치 설치 로그       | %windir%\inf\setupapi.dev.log           | 장치 설치 로그 사용에 대한 자세한 내용은 [SetupAPI Logging 설명서를](/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 참조하십시오. |

### <a name="table-2-event-log-ids-for-surface-dock-1-firmware-update"></a>표 2. Surface Dock 1 펌웨어 업데이트에 대한 이벤트 로그 ID

이벤트는 응용 프로그램 이벤트 로그에 기록됩니다.  참고: 이 도구의 이전 버전은 Applications and Services Logs\Microsoft Surface Dock Updater에 이벤트를 기록합니다.

| 이벤트 ID | 이벤트 유형                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Dock 펌웨어 업데이트가 시작되었습니다.                                    |
| 2002     | Dock 펌웨어 업데이트는 도크가 최신 버전인 것으로 알려져 있기 때문에 건너뜁니다. |
| 2003     | Dock 펌웨어 업데이트를 통해 펌웨어 버전을 다운로드하지 못했습니다.                 |
| 2004     | 펌웨어 버전 쿼리                                       |
| 2005     | Dock 펌웨어가 업데이트를 시작하지 못했습니다.                                |
| 2006     | 제품/페이로드 쌍을 보내지 못했습니다.                                  |
| 2007     | 펌웨어 업데이트가 완료되었습니다.                                            |
| 2008     | BEGIN dock 원격 분석.                                                |
| 2011     | END dock telemetry.                                                  |

## <a name="troubleshooting-tips"></a>문제 해결 팁

- Ac 전원에서 Surface Dock의 전원을 완전히 분리하여 Surface Dock를 초기화합니다.
- Surface Dock를 제외한 모든 주변 장치를 분리합니다.
- 현재 Surface Dock 1 펌웨어 업데이트를 제거한 다음 최신 버전을 설치합니다.
- Surface Dock가 분리되어 있는지 확인한 다음 도크의 이더넷 포트에 있는 LED를 통해 모니터링되는 업데이트가 완료될 수 있도록 충분한 시간을 허용합니다. 전원에서 Surface Dock를 끄기 전에 LED가 깜박이지 않는 동안 기다렸다가
- 커넥트 디바이스에 연결하여 Dock를 업데이트할 수 있는지 확인합니다.

## <a name="versions-reference"></a>버전 참조

>[!NOTE]
>설치 파일은 다음 이름 지정 형식으로 ** 릴리스됩니다. **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI(예: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) C:\Program Files\SurfaceUpdate로 기본적으로 설치됩니다.

### <a name="version-1531390"></a>버전 1.53.139.0

#### <a name="release-date-august-4-2020"></a>릴리스 날짜: 2020년 8월 4일

이 버전의 Surface Dock 1 펌웨어 업데이트에는 버그 수정 및 다음에 대한 지원이 포함되어 있습니다.

- X에서 Surface Dock 1을 Surface Pro 업데이트합니다.

#### <a name="registry-key-values"></a>레지스트리 키 값

펌웨어 업데이트 상태를 나타내는 레지스트리 값은 이 도구의 이전 버전에서 변경되지 않습니다.

- Component10CurrentFwVersion이 **4ac3970으로 업데이트되었습니다.**
- Component20CurrentFwVersion이 **4a1d570으로 업데이트되었습니다.**

### <a name="version-142139"></a>버전 1.42.139

#### <a name="release-date-september-18-2019"></a>릴리스 날짜: 2019년 9월 18일

이 버전은 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 펌웨어를 백그라운드에서 업데이트합니다.

#### <a name="updated-registry-key-values"></a>레지스트리 키 값이 업데이트되었습니다.

- Component10CurrentFwVersion이 **4ac3970으로 업데이트되었습니다.**
- Component20CurrentFwVersion이 **4a1d570으로 업데이트되었습니다.**

7 및 Surface Pro 3에 대한 Surface Laptop 추가합니다.

## <a name="legacy-versions"></a>레거시 버전

### <a name="version-2231390"></a>버전 2.23.139.0

#### <a name="release-date-10-october-2018"></a>릴리스 날짜: 2018년 10월 10일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Pro 6에 대한 지원 추가
- 2에 대한 Surface Laptop 추가

### <a name="version-2221390"></a>버전 2.22.139.0

#### <a name="release-date-26-july-2018"></a>릴리스 날짜: 2018년 7월 26일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- 업데이트 안정성 향상
- Surface Go에 대한 지원 추가

### <a name="version-2121360"></a>버전 2.12.136.0

#### <a name="release-date-29-january-2018"></a>릴리스 날짜: 2018년 1월 29일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Dock 메인 칩 펌웨어 업데이트

- Surface Dock DisplayPort 펌웨어 업데이트

- Surface Book 또는 Surface Book 2와 함께 사용하는 경우 외부 디스플레이의 디스플레이 안정성이 개선

또한, 이 버전의 Surface Dock 업데이트 프로그램을 Surface Book 디바이스에 설치하면 다음이 함께 포함됩니다.

- Surface Book 본체 펌웨어 업데이트

- Surface Book 디바이스를 대상으로 하는 개선 기능이 포함된 Surface Dock 펌웨어 업데이트에 대한 지원이 추가

### <a name="version-291360"></a>버전 2.9.136.0

#### <a name="release-date-november-3-2017"></a>릴리스 날짜: 2017년 11월 3일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Dock DisplayPort 펌웨어 업데이트

- 패시브 디스플레이 포트 어댑터의 오디오 문제를 해결합니다.

### <a name="version-21150"></a>버전 2.1.15.0

#### <a name="release-date-june-19-2017"></a>출시 날짜: 2017년 6월 19일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface 노트북

- Surface Pro

### <a name="version-2160"></a>버전 2.1.6.0

#### <a name="release-date-april-7-2017"></a>릴리스 날짜: 2017년 4월 7일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Dock DisplayPort 펌웨어 업데이트

- Windows 10 필요

### <a name="version-20220"></a>버전 2.0.22.0

#### <a name="release-date-october-21-2016"></a>릴리스 날짜: 2016년 10월 21일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Dock USB 펌웨어 업데이트

- 이더넷, 오디오 및 USB 포트의 안전성 개선

### <a name="version-1080"></a>버전 1.0.8.0

#### <a name="release-date-april-26-2016"></a>릴리스 날짜: 2016년 4월 26일

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Dock Main Chipset 펌웨어 업데이트

- Surface Dock DisplayPort 펌웨어 업데이트
