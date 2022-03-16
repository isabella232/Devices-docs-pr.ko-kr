---
title: 비즈니스용 Surface 진단 도구 키트
description: 이 항목에서는 IT 관리자가 Surface 디바이스에서 하드웨어, 소프트웨어 및 펌웨어 문제를 신속하게 조사, 문제 해결 및 해결할 수 있도록 하는 비즈니스용 Surface Toolkit 배포 및 사용하는 방법에 대해 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/25/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 7d33d3d557a134584a7984279ed9187b116d9959
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448701"
---
# <a name="surface-diagnostic-toolkit-for-business"></a>비즈니스용 Surface 진단 도구 키트

Surface가 제대로 작동하지 않는 경우 비즈니스용 Microsoft Surface Toolkit(SDT)는 관리자나 관리자가 문제를 찾고 해결하는 데 도움이 될 수 있습니다.  비즈니스용 SDT를 사용하면 네트워크를 통해 Surface 디바이스에서 하드웨어, 소프트웨어 및 펌웨어 문제를 신속하게 조사, 문제 해결 및 해결할 수 있습니다.

> [!NOTE]
> 비즈니스용 Surface Toolkit 디바이스를 위해 제작되었습니다. 장치가 회사 또는 학교에서 관리하지 않는 개인 장치인 경우 [Surface Diagnostic Toolkit](https://support.microsoft.com/help/4037239/surface-fix-common-surface-problems-using-surface-diagnostic-toolkit) 실행합니다.

특히 비즈니스용 SDT를 사용하면 다음을 할 수 있습니다.

- [패키지를 사용자 지정합니다.](#preparing-the-sdt-package-for-distribution)
- [명령을 사용하여 앱을 실행합니다.](surface-diagnostic-toolkit-command-line.md)
- [여러 하드웨어 테스트를 실행하여 문제를 해결합니다.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [문제를 분석하기 위한 로그를 생성합니다.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [장치와 최적의 구성을 비교하는 자세한 보고서를 얻습니다.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)

## <a name="primary-scenarios-and-download-resources"></a>기본 시나리오 및 리소스 다운로드

비즈니스용 Surface 진단 Toolkit 실행하려면 다음 표에 나열된 구성 요소를 다운로드합니다.

모드 | 기본 시나리오 | 다운로드 | 세부 정보
--- | --- | --- | ---
데스크톱 모드 | 사용자가 Surface 디바이스에서 SDT를 실행하여 문제를 해결할 수 있도록 지원합니다.<br>사용자가 수집 및 분석할 특정 로그를 선택할 수 있도록 하나 이상의 Surface 디바이스에 배포할 사용자 지정 패키지를 만드십시오. | SDT 배포 가능 MSI 패키지:<br>비즈니스용 Microsoft Surface Toolkit 설치 관리자<br>[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703) | [데스크톱 모드에서 Surface 진단 Toolkit 사용](surface-diagnostic-toolkit-desktop-mode.md)
명령줄 | Configuration Manager와 같은 표준 도구를 사용하여 사용자 조작 없이 원격으로 Surface 디바이스 문제를 직접 해결합니다. 여기에는 다음 명령이 포함됩니다.<br>`-DataCollector` 모든 로그 파일 수집<br>`-bpa` 모범 사례 분석기를 사용하여 상태 진단을 실행합니다.<br>`-windowsupdate` 업데이트에서 Windows 펌웨어 또는 드라이버 업데이트 누락을 확인합니다.<br>`-warranty` 보증 정보를 검사합니다. <br><br>| SDT 콘솔 앱:<br>Microsoft Surface 진단 앱 콘솔<br>[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703) | [비즈니스용 Surface 진단 앱을 사용하여 명령줄 Toolkit 실행](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices"></a>지원되는 디바이스

비즈니스용 SDT는 Surface 3 이상 디바이스에서 지원됩니다(S 모드로 구성된 디바이스 제외).

- Surface Book - 모든 세대
- Surface Laptop 스튜디오
- Surface Go - 모든 세대
- Surface Laptop - 모든 세대
- Surface Laptop Go
- Surface Pro 3 이상
- Surface Pro - 모든 세대
- Surface Studio - 모든 세대
- Surface 3 LTE
- Surface 3

## <a name="installing-surface-diagnostic-toolkit-for-business"></a>비즈니스용 Surface 진단 Toolkit 설치

조직의 사용자에게 배포할 수 있는 SDT 패키지를 만들 수 있는 경우:

1. 관리자 계정을 사용하여 Surface 디바이스에 로그인합니다.

2. SDT Windows 설치 관리자 패키지(.msi)를 [IT용 Surface 도구 다운로드 페이지에서 다운로드합니다](https://www.microsoft.com/download/details.aspx?id=46703).

    - Intel/AMD 장치의 경우 다음을 다운로드합니다. **Surface_Diagnostic_Toolkit_for_Business_v2.168.139.0.msi**.
    - 장치 ** ARM 다운로드: **Surface_Diagnostic_Toolkit_for_Business_v2.168.139.0_x86.msi.

3. 그림 1에 .msi 같이 Surface 디바이스의 기본 설정 위치(예: Desktop)에 .msi 파일을 복사합니다. SDT 설정 마법사가 나타납니다. **다음**을 클릭합니다.

    >[!NOTE]
    >설치 마법사가 나타나지 않는 경우 컴퓨터의 관리자 계정에 로그인해야 합니다.

    ![Surface Diagnostic Toolkit 시작해보아야 합니다.](images/sdt-1.png)<br/>
    *그림 1. Surface 진단 Toolkit 설정 마법사*

4. SDT 설치 마법사가 나타나면 **다음**을 클릭하고 EULA(최종 사용자 사용권 계약)에 동의합니다.

5. 설치 옵션 화면에서 원하는 경우 기본 설치 위치를 변경합니다.

6. 설치 유형에서 고급을 **선택합니다**.

    >[!NOTE]
    >표준 옵션을 사용하면 관리자 계정을 사용하여 디바이스에 로그인한 경우 Surface 디바이스에서 진단 도구를 직접 실행할 수 있습니다.

    ![설치 옵션: 고급.](images/sdt-install.png)

7. 다음 **을** 클릭한 다음 설치를 **클릭합니다**.

## <a name="installing-using-the-command-line"></a>명령줄을 사용하여 설치

원하는 경우 명령 프롬프트에서 SDT를 설치하고 사용자 지정 플래그를 설정하여 관리자 모드로 도구를 설치할 수 있습니다. SDT에는 다음과 같은 설치 옵션 플래그가 포함되어 있습니다.

- `SENDTELEMETRY` 원격 분석 데이터를 Microsoft로 전송합니다. 플래그는 사용하지 않도록 `0` 설정하거나 사용하도록 설정할 수 `1` 있습니다. 기본값은 원격 `1` 분석 전송입니다.
- `ADMINMODE` 관리 모드에서 설치할 도구를 구성합니다. 플래그는 클라이언트 `0` 모드 또는 `1` IT 관리자 모드에 허용됩니다. 기본값은 `0`입니다.

### <a name="to-install-sdt-from-the-command-line"></a>명령줄에서 SDT를 설치하려면

1. 명령 프롬프트를 열고 다음을 입력합니다.

    ```console
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```

    **예제:**

    ```console
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a>Surface 디바이스에서 SDT 찾기

SDT와 SDT 앱 콘솔이 모두 에 설치됩니다 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.

SDT는 .exe 파일 외에 그림 2와 같이 JSON 파일과 admin.dll 파일(modules\admin.dll)을 설치합니다.

:::image type="content" alt-text="파일 탐색기에서 설치된 SDT 파일 목록입니다." source="images/sdt-2.png":::<br/>
*그림 2. SDT에서 설치한 파일*

## <a name="preparing-the-sdt-package-for-distribution"></a>배포를 위해 SDT 패키지 준비

사용자 지정 패키지를 만들면 도구를 알려진 특정 문제에 대상으로 할 수 있습니다.

1. 시작 **> 시작을 클릭**하고 **Surface**를 입력한 다음 비즈니스용 **Surface 진단 Toolkit 클릭합니다**.

2. 그림 3과 같이 도구가 열리면 **사용자** 지정 패키지 만들기를 클릭합니다.

    ![사용자 지정 패키지 만들기 옵션.](images/sdt-3.png)<br/>
    *그림 3. 사용자 지정 패키지 만들기*

### <a name="language-and-telemetry-settings"></a>언어 및 원격 분석 설정

  패키지를 만들 때 언어 설정을 선택하거나 Microsoft에 원격 분석 정보 전송을 옵트아웃(opt out)할 수 있습니다. 기본적으로 SDT는 Microsoft 개인 정보 취급 방침에 따라 응용 프로그램을 개선하는 데 사용되는 [원격 데이터를 Microsoft로 전송합니다](https://privacy.microsoft.com/privacystatement). 거부할 경우 아래와 같이 사용자 지정 패키지를 만들 때 확인란의 선택을 취소합니다. 또는 SDT 설치 중에 설치 옵션 페이지에서 **Microsoft**에 원격 분석 보내 **** 기 확인란의 선택을 취소합니다.

>[!NOTE]
>이 설정은 Windows 업데이트 및 소프트웨어 복구와 같은 인터넷 연결이 필요한 테스트 및 복구를 실행하거나 앱 도구 모음의 스마일 또는 눈금 단추를 사용하여 피드백을 제공하는 경우 Microsoft 서버에 자동으로 저장되는 최소 원격 분석에는 영향을 주지 않습니다.

![언어 및 원격 분석 설정을 선택합니다.](images/sdt-4.png)<br/>
*그림 4. 언어 및 원격 분석 설정 선택*

### <a name="windows-update-page"></a>Windows 업데이트 페이지

조직에 적합한 옵션을 선택합니다. 일반적으로 여러 사용자가 있는 조직에서는 그림 5에 표시된 Windows Server Update Services(WSUS)를 통해 업데이트를 받게 됩니다. 로컬 Windows 업데이트 패키지 또는 WSUS를 사용하는 경우 경로를 적절하게 입력합니다.

![업데이트 Windows 선택합니다.](images/sdt-5.png)<br/>
*그림 5. Windows 업데이트 옵션*

### <a name="software-repair-page"></a>소프트웨어 복구 페이지

이렇게 하면 소프트웨어 복구 업데이트를 실행하기 위한 옵션을 선택하거나 제거할 수 있습니다.

![소프트웨어 복구 옵션을 선택합니다.](images/sdt-6.png)<br/>
*그림 6. 소프트웨어 복구 옵션*

### <a name="collecting-logs-and-saving-package-page"></a>로그 수집 및 패키지 저장 페이지

응용 프로그램, 드라이버, 하드웨어 및 운영 체제에서 다양한 로그를 실행하려면 선택할 수 있습니다. 해당 영역을 클릭하고 사용 가능한 로그의 메뉴에서 선택합니다. 그런 다음 사용자가 액세스할 수 있는 소프트웨어 배포 지점 또는 동등한 위치에 패키지를 저장할 수 있습니다.

![로그 옵션을 선택합니다.](images/sdt-7.png)<br/>
*그림 7. 로그 옵션 및 패키지 저장*

## <a name="next-steps"></a>다음 단계

- [비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용](surface-diagnostic-toolkit-desktop-mode.md)
- [비즈니스용 Surface 진단 앱을 사용하여 명령줄 Toolkit 실행](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a>변경 및 업데이트

### <a name="version-21681390"></a>버전 2.168.139.0

이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- Surface Pro 8
- Surface Laptop 스튜디오
- Surface Go 3

### <a name="version-21311390"></a>버전 2.131.139.0

이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- Surface Pro 7+
- X에서 원활한 지원 Surface Pro 환경
- 향상된 보안
- 포괄 사용자 환경 개선

### <a name="version-21241390"></a>버전 2.124.139.0

이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- 원활한 통합 지원
- 모든 테스트 결과 저장
- 이미지를 사용자 지정으로 만들지 확인
- 장치 관리자의 경고 포함
- Dock 펌웨어 버전
- 저장소 테스트에서 잠재적인 오류로 드라이브 플래그 지정
- 저장소 링크 제거

### <a name="version-2121139"></a>버전 2.121.139

*릴리스 날짜: 2020년 7월 31일*<br>
이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- 원활한 지원 환경
- 버그 수정

### <a name="version-2941390"></a>버전 2.94.139.0

*릴리스 날짜: 2020년 5월 11일*<br>
이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- 하드웨어 검사를 수행하기 위해 Windows 건너뛰는 능력.
- 최신 버전 업데이트에 대한 알림을 받을 수 있는 능력
- Surface Go 2
- Surface Book 3
- 진행률 표시기 표시

### <a name="version-2431390"></a>버전 2.43.139.0

*릴리스 날짜: 2019년 10월 21일*<br>
이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- Surface Pro 7
- Surface Laptop 3

### <a name="version-2421390"></a>버전 2.42.139.0

*릴리스 날짜: 2019년 9월 24일*<br>
이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- 하드웨어 보고서를 다운로드하는 능력.
- 도구에서 직접 Microsoft 지원에 문의할 수 있습니다.

### <a name="version-2411390"></a>버전 2.41.139.0

*릴리스 날짜: 2019년 6월 24일*<br>
이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- 로그 및 보고서에 포함된 드라이버 버전 정보입니다.
- 앱에 대한 피드백을 제공하는 능력.

### <a name="version-2361390"></a>버전 2.36.139.0

*릴리스 날짜: 2019년 4월 26일*<br>
이 버전의 비즈니스용 Surface Toolkit 다음에 대한 지원이 추가되었습니다.

- 명령줄 구성 없이 설치 관리자 UI를 통해 관리자 기능을 잠금 해제하는 고급 설치 옵션입니다.
- 접근성 개선.
- 로그에 포함된 표면 밝기 컨트롤 설정입니다.
- 보고서 생성기의 외부 모니터 호환성 지원 링크
