---
title: Microsoft Surface Dock 펌웨어 업데이트-IT 관리자를 위한 기술 정보
description: 이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용 하 여 Surface Dock 펌웨어를 업데이트 하는 방법을 설명 합니다. Surface 디바이스에 설치 되 면 surface 디바이스에 연결 된 모든 표면 도크가 업데이트 됩니다.
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
ms.openlocfilehash: aab4c67a6a262b11cd5982ebe145afbddfeaa1c9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834631"
---
# Microsoft Surface Dock 펌웨어 업데이트: IT 관리자를 위한 기술 정보

> [!IMPORTANT]
> 이 문서에는 IT 관리자를 위한 기술 지침이 포함 되어 있습니다. 가정용 사용자 인 경우 Microsoft 지원 사이트에서 [Surface Dock 펌웨어를 업데이트 하는 방법을](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)참조 하세요   . 지원 사이트의 지침은 아래의 일반적인 설치 단계와 동일 하지만이 문서에는 네트워크의 여러 장치에 대 한 업데이트 모니터링, 확인 및 배포에 대 한 추가 정보가 있습니다.

이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용 하 여 Surface Dock 펌웨어를 업데이트 하는 방법을 설명 합니다. Surface 디바이스에 설치 되 면 surface 디바이스에 연결 된 모든 표면 도크가 업데이트 됩니다. 

이 도구는 이전 Microsoft Surface Dock 업데이트 도구를 대체 합니다. 이전에는이를 위해 Surface 도구의 일부로 다운로드할 수 있습니다. 앞의 도구에는 Surface_Dock_Updater_vx.xx.xxx.x.msi 이름이 지정 되어 있으며 (여기서 x는 버전 번호를 나타냄) 더 이상 다운로드할 수 없으며 사용할 수 없습니다.

## Surface Dock 펌웨어 업데이트 설치

이 섹션에서는 펌웨어 업데이트를 수동으로 설치 하는 방법에 대해 설명 합니다.

> [!NOTE]
> Microsoft는 Surface Dock 펌웨어 업데이트의 새 버전을 정기적으로 릴리스 합니다. MSI 파일이 자동으로 업데이트 되지 않습니다. MSI를 Surface 디바이스에 배포한 경우 펌웨어의 새 버전이 릴리스되면 새 버전을 배포 해야 합니다.

1. [Microsoft Surface Dock 펌웨어 업데이트](https://www.microsoft.com/download/details.aspx?id=46703)를 다운로드 하 여 설치 합니다.
    - 업데이트에는 Windows 10 버전 1803 이상을 실행 하는 Surface 장치가 필요 합니다.
    - MSI 파일을 설치 하면 Surface를 다시 시작 하 라는 메시지가 표시 될 수 있습니다. 그러나 업데이트를 수행 하는 데는 다시 시작이 필요 하지 않습니다.

2. Surface Dock (전원 어댑터 사용)에서 Surface 디바이스의 연결을 끊고 ~ 5 초간 기다린 다음 다시 연결 합니다. Surface Dock 펌웨어 업데이트는 백그라운드에서 자동으로 도크를 업데이트 합니다. 이 프로세스는 완료 하는 데 몇 분 정도 소요 될 수 있으며 중단 된 경우에도 계속 됩니다. 

## Surface Dock 펌웨어 업데이트 모니터링

이 섹션은 선택 사항이 며 펌웨어 업데이트 설치를 모니터링 하는 방법에 대 한 개요를 제공 합니다. 

업데이트를 모니터링 하려면 다음을 수행 합니다.

1. 이벤트 뷰어를 열고 **Windows 로그 > 응용 프로그램**으로 이동한 다음 오른쪽 창의 **작업** 에서 **현재 로그 필터링**을 클릭 하 고 **이벤트 원본**옆에 **SurfaceDockFwUpdate** 를 입력 한 다음 **확인**을 클릭 합니다.

2. 관리자 권한 명령 프롬프트에서 다음 명령을 입력 합니다.

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. 이 문서의 [다음 섹션](#install-the-surface-dock-firmware-update) 에 설명 된 대로 업데이트를 설치 합니다.
4. 다음 텍스트를 포함 하는 이벤트 2007에 업데이트 **완료 됨 펌웨어가 업데이트 되었습니다. hr = 0 Driverementry EventCode = 2007**. 
    - 업데이트가 실패 하면 이벤트 ID 2007이 **정보가**아닌 **오류** 이벤트로 표시 됩니다. 또한 Windows 레지스트리에 보고 된 버전은 최신 상태가 아닙니다.
5. 업데이트가 완료 되 면 최신 버전의 도구에 해당 하는 업데이트 된 DWORD 값이 Windows 레지스트리에 표시 됩니다. 자세한 내용은이 문서의 [버전 참조](#versions-reference) 섹션을 참조 하세요. 예:
    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>이벤트 텍스트에서 "SurfaceDockFwUpdate에서 이벤트 ID xxxx에 대 한 설명을 찾을 수 없음"이 표시 되는 경우이는 예상 되는 것으로, 무시할 수 있습니다.

또한이 문서의 다음 섹션을 참조 하세요. 
  - [펌웨어 업데이트가 완료 되었는지 확인 하는 방법](#how-to-verify-completion-of-the-firmware-update)
  - [이벤트 로깅](#event-logging)
  - [문제 해결 팁](#troubleshooting-tips)
  - [버전 참조](#versions-reference)

## 네트워크 배포

Windows Installer 명령 (Msiexec.exe)을 사용 하 여 네트워크를 통해 여러 장치에 Surface Dock 펌웨어 업데이트를 배포할 수 있습니다. Microsoft 끝점 구성 관리자 또는 기타 배포 도구를 사용 하는 경우 설치가 자동으로 수행 되도록 다음 구문을 입력 합니다.

- **Msiexec.exe/i \<path to msi file\> /quiet/norestart** 

  예:
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > 로그 파일은 기본적으로 생성 되지 않습니다. 로그 파일을 만들기 위해서는 "/l*v [path]"를 추가 해야 합니다. 예: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI "

  자세한 내용은 명령줄 [옵션](https://docs.microsoft.com/windows/win32/msi/command-line-options) 설명서를 참조 하세요.

> [!IMPORTANT]
> 다른 방법을 사용 하 여 화면 도크를 업데이트 된 상태로 유지 하려는 경우에는 [Surface Dock 업데이트](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 에 대 한 자세한 내용을 참조 하세요.

## Intune 배포

Intune을 사용 하 여 Surface Dock 펌웨어 업데이트를 디바이스에 배포할 수 있습니다. 먼저, 다음 설명서의 설명에 따라 MSI 파일을 intunewin 형식으로 변환 해야 합니다. [Intune 독립 실행형-Win32 앱 관리](https://docs.microsoft.com/intune/apps/apps-win32-app-management)

다음 명령을 사용 합니다.
  - **msiexec/i \<path to msi file\> /quiet/q**

## 펌웨어 업데이트가 완료 되었는지 확인 하는 방법

서피스 도크 펌웨어는 다음 두 가지 구성 요소로 구성 됩니다.

- **Component10:** 마이크로 장치 컨트롤러 단위 (MCU) 펌웨어
- **Component20:** 디스플레이 포트 (DP) 펌웨어.

Surface Dock 펌웨어 업데이트가 성공적으로 완료 되 면 이러한 펌웨어 구성 요소에 대 한 새 레지스트리 키 값이 생성 됩니다.

**업데이트를 확인 하려면 다음을 수행 합니다.**

1. Regedit를 열고 다음 레지스트리 경로로 이동 합니다.

    - **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. 현재 디바이스에 있는 펌웨어를 참조 하는 **Component10CurrentFwVersion 및 Component20CurrentFwVersion**레지스트리 키를 찾습니다.

   ![Surface Dock 펌웨어 업데이트 설치 프로세스](images/regeditDock.png)

3. 새 레지스트리 키 값이이 문서 뒷부분의 버전 참조에 나열 된 업데이트 된 레지스트리 키 값과 일치 하는지 확인 합니다. 값이 일치 하는 경우 펌웨어가 성공적으로 업데이트 된 것입니다.

4. 확인할 수 없는 경우 다음 섹션에서 이벤트 로깅 및 문제 해결 팁을 검토 하세요.

## 이벤트 로깅

**표 1. Surface Dock 펌웨어 업데이트에 대 한 로그 파일**

| Log                              | 위치                               | 참고                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Dock 펌웨어 업데이트 로그 | 경로를 지정 해야 합니다 (참고 참조). | 이전 버전의이 도구는 응용 프로그램 및 서비스 Logs\Microsoft Surface Dock 업데이트에 이벤트를 기록 했습니다.                                                                                                  |
| Windows 장치 설치 로그       | %windir%\inf\setupapi.dev.log           | 장치 설치 로그 사용에 대 한 자세한 내용은 [SetupAPI 로깅](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 설명서를 참조 하세요. |


**표 2. Surface Dock 펌웨어 업데이트에 대 한 이벤트 로그 Id**<br>
이벤트는 응용 프로그램 이벤트 로그에 기록 됩니다.  참고: 이전 버전의이 도구는 응용 프로그램 및 서비스 Logs\Microsoft Surface Dock 업데이트에 이벤트를 기록 했습니다.

| 이벤트 ID | 이벤트 유형                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Dock 펌웨어 업데이트가 시작 되었습니다.                                    |
| 2002     | Dock 펌웨어 업데이트는 연결이 최신으로 알려져 있으므로 건너뛰었습니다. |
| 2003     | Dock 펌웨어 업데이트에서 펌웨어 버전을 가져오지 못했습니다.                 |
| 2004     | 펌웨어 버전을 쿼리 하는 중입니다.                                       |
| 2005     | 도킹 펌웨어에서 업데이트를 시작 하지 못했습니다.                                |
| 2006     | 제공/페이로드 쌍을 보내지 못했습니다.                                  |
| 2007     | 펌웨어 업데이트가 완료 되었습니다.                                            |
| 2008     | 원격 분석을 시작 합니다.                                                |
| 2011     | Dock 원격 분석 종료.                                                  |

## 문제 해결 팁

- 화면 도크를 재설정 하기 위해 AC 전원에서 Surface dock의 전원을 완전히 끊습니다.
- Surface Dock을 제외한 모든 주변 장치를 분리 합니다.
- 현재 Surface Dock 펌웨어 업데이트를 제거 하 고 최신 버전을 설치 합니다.
- Surface Dock의 연결이 해제 되었는지 확인 한 다음 도크의 이더넷 포트에서 LED를 통해 모니터 한 대로 업데이트가 완료 될 때까지 충분히 기다립니다. 전원에서 Surface Dock을 분리 하기 전에 LED가 깜박임을 멈출 때까지 기다립니다.
- 화면 도크를 다른 장치에 연결 하 여 도크를 업데이트할 수 있는지 확인 합니다.

## 버전 참조

>[!NOTE]
>**Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (예: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 인 설치 파일은 기본적으로 C:\Program Files\SurfaceUpdate.에 설치 되 고 다음과 같은 이름 지정 형식으로 릴리스됩니다.

### 버전 1.42.139 
*릴리스 날짜: 18 2019 년 9 월*

이 버전은 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI에 포함 되어 있으며, 백그라운드에서 펌웨어를 업데이트 합니다. 
**업데이트 된 레지스트리 키 값:**<br>

- Component10CurrentFwVersion가 **4ac3970**으로 업데이트 되었습니다.
- Component20CurrentFwVersion가 **4a1d570**로 업데이트 되었습니다.

Surface Pro 7 및 Surface 노트북 3에 대 한 지원을 추가 합니다.

## 레거시 버전

### 버전 2.23.139.0
*릴리스 날짜: 2018 년 10 월 11 일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- Surface Pro 6에 대 한 지원 추가
- Surface 노트북 2에 대 한 지원 추가


### 버전 2.22.139.0
*릴리스 날짜: 26 7 월 2018*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

- 업데이트 안정성 향상
- Surface Go에 대 한 지원 추가

### 버전 2.12.136.0
*릴리스 날짜: 2018년 1월 29일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.
* Surface Dock 메인 칩 펌웨어 업데이트
* Surface Dock DisplayPort 펌웨어 업데이트
* Surface Book 또는 Surface Book 2와 함께 사용하는 경우 외부 디스플레이의 디스플레이 안정성이 개선

또한, 이 버전의 Surface Dock 업데이트 프로그램을 Surface Book 디바이스에 설치하면 다음이 함께 포함됩니다.
* Surface Book 본체 펌웨어 업데이트
* Surface Book 디바이스를 대상으로 하는 개선 기능이 포함된 Surface Dock 펌웨어 업데이트에 대한 지원이 추가


### 버전 2.9.136.0
*릴리스 날짜: 2017년 11월 3일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

* Surface Dock DisplayPort 펌웨어 업데이트
* 패시브 디스플레이 포트 어댑터의 오디오 문제를 해결합니다.

### 버전 2.1.15.0
*출시 날짜: 2017년 6월 19일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

* Surface 노트북
* Surface Pro

### 버전 2.1.6.0
*릴리스 날짜: 2017년 4월 7일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

* Surface Dock DisplayPort 펌웨어 업데이트
* Windows 10 필요

### 버전 2.0.22.0
*릴리스 날짜: 2016년 10월 21일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

* Surface Dock USB 펌웨어 업데이트
* 이더넷, 오디오 및 USB 포트의 안전성 개선

### 버전 1.0.8.0
*릴리스 날짜: 2016년 4월 26일*

이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.

* Surface Dock Main Chipset 펌웨어 업데이트
* Surface Dock DisplayPort 펌웨어 업데이트

