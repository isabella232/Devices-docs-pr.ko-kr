---
title: 비즈니스용 Surface 진단 도구 키트 배포
description: 이 항목에서는 비즈니스를 위해 Surface 진단 도구 키트를 사용 하는 방법에 대해 설명 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 07/31/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 9c250cef63b760f3faab9172aa950c305e4e47e5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902986"
---
# 비즈니스용 Surface 진단 도구 키트 배포

Microsoft Surface (비즈니스 관련 진단 도구 키트) (SDT)는 IT 관리자가 Surface 장치에서 하드웨어, 소프트웨어 및 펌웨어 문제를 빠르게 조사, 문제 해결 및 해결할 수 있도록 합니다. 장치 상태 정보 활용 및 문제 해결에 대 한 지침을 얻고, 다양 한 진단 테스트 및 소프트웨어 복구를 실행할 수 있습니다. 

특히, 비즈니스의 SDT에서는 다음을 수행할 수 있습니다.

- [패키지를 사용자 지정 합니다.](#create-custom-sdt)
- [명령을 사용 하 여 앱을 실행 합니다.](surface-diagnostic-toolkit-command-line.md)
- [여러 하드웨어 테스트를 실행 하 여 문제를 해결 하세요.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [문제 분석을 위한 로그를 생성 합니다.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [디바이스 vs 최적의 구성을 비교 하는 자세한 보고서를 얻습니다.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## 기본 시나리오 및 다운로드 리소스 

비즈니스에 대해 SDT를 실행 하려면 다음 표에 나열 된 구성 요소를 다운로드 합니다.


모드 |  기본 시나리오 | 다운로드 | 자세히 알아보기
--- | --- | --- | ---
데스크톱 모드 |  표면 장치에서 SDT를 실행 하는 사용자가 문제를 해결 하도록 지원 합니다.<br>사용자가 수집 하 고 분석할 특정 로그를 선택할 수 있도록 하나 이상의 Surface 장치에 배포 하는 사용자 지정 패키지를 만듭니다. | SDT 배포 가능 MSI 패키지:<br>비즈니스 설치 관리자 용 Microsoft Surface 진단 도구 키트<br>[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703) | [데스크톱 모드에서 Surface 진단 도구 키트 사용](surface-diagnostic-toolkit-desktop-mode.md)
명령줄 |  구성 관리자와 같은 표준 도구를 사용 하 여 사용자 조작 없이 원격으로 Surface 디바이스의 문제를 해결 합니다. 여기에는 다음 명령이 포함 됩니다.<br>`-DataCollector` 모든 로그 파일 수집<br>`-bpa` 모범 사례 분석기를 사용 하 여 상태 진단을 실행 합니다.<br>`-windowsupdate` Windows 업데이트에서 누락 된 펌웨어 또는 드라이버 업데이트가 있는지 확인 합니다.<br>`-warranty` 무상 수리 정보를 확인 합니다. <br><br>| SDT 콘솔 앱:<br>Microsoft Surface Diagnostics 앱 콘솔<br>[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703) | [명령을 사용 하 여 Surface 진단 도구 키트 실행](surface-diagnostic-toolkit-command-line.md)

## 지원되는 디바이스 

다음을 포함 하 여 Surface 3 및 이후 장치에서 비즈니스의 SDT가 지원 됩니다.

- Surface Book 3
- Surface Go 2
- Surface Pro X
- Surface Pro 7
- Surface 노트북 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- LTE를 사용 하 여 Surface Go
- Surface Book 2
- Surface Pro LTE Advanced(모델 1807)
- Surface Pro(모델 1796)
- Surface 노트북
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3

## 비즈니스를 위한 Surface 진단 도구 키트 설치

조직의 사용자에 게 배포할 수 있는 SDT 패키지를 만들려면 다음을 수행 합니다.

1. 관리자 계정을 사용 하 여 Surface device에 로그인 합니다.
2. [IT 다운로드 페이지의 표면 도구](https://www.microsoft.com/download/details.aspx?id=46703) 에서 Sdt Windows Installer 패키지 (.msi)를 다운로드 하 고 데스크톱 등의 surface 장치에서 원하는 위치에 복사 합니다.
3. SDT 설정 마법사가 표시 됩니다 (그림 1). **다음**을 클릭합니다. 

    >[!NOTE]
    >설치 마법사가 표시 되지 않으면 컴퓨터에서 관리자 계정에 로그인 되어 있는지 확인 합니다. 

    ![Surface 진단 도구 키트 설정 마법사 시작](images/sdt-1.png)

    *그림 1. Surface 진단 도구 키트 설정 마법사*

4. SDT 설정 마법사가 나타나면 **다음**을 클릭 하 여 최종 사용자 사용권 계약 (EULA)에 동의 합니다.

5. 설치 옵션 화면에서 원하는 경우 기본 설치 위치를 변경 합니다. 
6. 설치 유형 아래에서 **고급**을 선택 합니다. 

    >[!NOTE]
    >표준 옵션을 사용 하면 관리자 계정으로 장치에 로그인 한 경우 사용자는 Surface device에서 진단 도구를 직접 실행할 수 있습니다. 
    
     ![설치 옵션: 고급](images/sdt-install.png)

7. **다음** 을 클릭 하 고 **설치**를 클릭 합니다. 

## 명령줄을 사용 하 여 설치
필요한 경우 명령 프롬프트에서 SDT를 설치 하 고 사용자 지정 플래그를 설정 하 여 해당 도구를 관리 모드로 설치할 수 있습니다. SDT에는 다음 설치 옵션 플래그가 포함 되어 있습니다.

- `SENDTELEMETRY` 원격 분석 데이터를 Microsoft에 보냅니다. 플래그는 `0` 사용 안 함 또는 `1` 사용으로 허용 됩니다. 기본값은 `1` 원격 분석을 보내는 것입니다.
- `ADMINMODE` 관리 모드에서 설치 되도록 도구를 구성 합니다. 플래그는 `0` 클라이언트 모드 또는 `1` IT 관리자 모드에 대해 허용 됩니다. 기본값은 `0`입니다.

### 명령줄에서 SDT를 설치 하려면 다음을 수행 합니다.

1. 명령 프롬프트를 열고 다음을 입력 합니다.

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **예제:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Surface 장치에서 SDT 찾기

SDT 및 SDT 앱 콘솔 모두에 설치 됩니다 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

SDT는 .exe 파일 외에도 그림 2와 같이 JSON 파일과 admin.dll 파일 (modules\admin.dll)을 설치 합니다.

![파일 탐색기에 설치 된 SDT의 파일 목록](images/sdt-2.png)

*그림 2. SDT에서 설치 된 파일*

<span id="create-custom-sdt" />

## 배포를 위해 SDT 패키지 준비

사용자 지정 패키지를 만들면 도구가 알려진 특정 문제를 대상으로 할 수 있습니다.

1. **시작 > 실행**을 클릭 하 고 **화면** 을 입력 한 다음 **surface 진단 도구 키트**를 클릭 하 여 비즈니스를 선택 합니다. 
2. 도구가 열리면 그림 3에 나와 있는 것 처럼 **사용자 지정 패키지 만들기**를 클릭 합니다.

    ![사용자 지정 패키지 만들기 옵션](images/sdt-3.png)

    *그림 3. 사용자 지정 패키지 만들기*

### 언어 및 원격 분석 설정

  패키지를 만들 때 언어 설정을 선택 하거나 Microsoft에 원격 분석 정보를 보내는 것을 옵트아웃 할 수 있습니다. 기본적으로 SDT는 [microsoft](https://privacy.microsoft.com/privacystatement)에 대 한 원격 분석을 전송 하는 데 사용 됩니다. 거절 하려는 경우 아래와 같이 사용자 지정 패키지를 만들 때 확인란의 선택을 취소 합니다. 또는 SDT 설치 중 **옵션 설치** 페이지에서 **Microsoft로 원격 분석 보내기** 확인란의 선택을 취소 합니다. 

>[!NOTE]
>이 설정은 Windows Update 및 소프트웨어 복구와 같은 인터넷 연결이 필요한 테스트 및 복구를 실행 하거나 앱 도구 모음에서 웃는 얼굴 또는 찡그린 얼굴 보내기 단추를 사용 하 여 피드백을 제공 하는 경우 Microsoft 서버에 자동으로 저장 되는 최소 원격 분석에 영향을 주지 않습니다. 


![언어 및 원격 분석 설정 선택](images/sdt-4.png)

*그림 4. 언어 및 원격 분석 설정 선택*


### Windows 업데이트 페이지

조직에 적합 한 옵션을 선택 합니다. 일반적으로 여러 사용자가 있는 조직에서는 그림 5와 같이 WSUS (Windows Server Update Services)를 통해 업데이트를 받도록 선택 합니다. 로컬 Windows 업데이트 패키지 또는 WSUS를 사용 하는 경우 적절 하 게 경로를 입력 합니다. 

![Windows 업데이트 옵션 선택](images/sdt-5.png)

*그림 5. Windows 업데이트 옵션*

### 소프트웨어 복구 페이지

이렇게 하면 소프트웨어 복구 업데이트를 실행 하는 옵션을 선택 하거나 제거할 수 있습니다. 

![소프트웨어 복구 옵션 선택](images/sdt-6.png)

*그림 6. 소프트웨어 복구 옵션*

### 로그 수집 및 패키지 저장 페이지

다양 한 로그를 응용 프로그램, 드라이버, 하드웨어 및 운영 체제 간에 실행 하도록 선택할 수 있습니다. 적절 한 영역을 클릭 하 고 사용 가능한 로그 메뉴에서 선택 합니다. 그런 다음 패키지를 사용자가 액세스할 수 있는 소프트웨어 배포 지점이 나 동등한 위치에 저장할 수 있습니다. 

![로그 옵션 선택](images/sdt-7.png)

*그림 7. 로그 옵션 및 패키지 저장*

## 다음 단계

- [비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용](surface-diagnostic-toolkit-desktop-mode.md)
- [명령을 사용 하 여 비즈니스를 위한 Surface 진단 도구 키트 사용](surface-diagnostic-toolkit-command-line.md)

## 변경 및 업데이트


### 버전 2.121.139
*릴리스 날짜: 31 2020 년 7 월*<br>
이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.

- 원활한 지원 환경
- 버그 수정

### 버전 2.94.139.0
*릴리스 날짜: 5 월 11 일 2020*<br>
이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.

- Windows 업데이트를 건너뛰고 하드웨어 검사를 수행 하는 기능
- 최신 버전 업데이트에 대 한 알림을 받을 수 있는 기능
- Surface Go 2
- Surface Book 3
- 진행률 표시기 표시


### 버전 2.43.139.0
*릴리스 날짜: 2019 년 10 월 21 일*<br>
이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다.

- Surface Pro 7
- Surface 노트북 3

### 버전 2.42.139.0
*릴리스 날짜: 2019 년 9 월 24 일*<br>
이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다. 
- 하드웨어 보고서를 다운로드할 수 있습니다.
- 도구에서 바로 Microsoft Support에 문의할 수 있습니다. <br>

### 버전 2.41.139.0
*릴리스 날짜: 2019 년 6 월 24 일*<br>
이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다. 
- 로그 및 보고서에 포함 된 드라이버 버전 정보입니다.
- 앱에 대 한 피드백을 제공 하는 기능입니다.<br>


### 버전 2.36.139.0
*릴리스 날짜: 2019 년 4 월 26 일*<br>
이 버전의 비즈니스용 Surface 진단 도구 키트에는 다음에 대 한 지원이 추가 되었습니다. 
- 명령줄 구성을 요구 하지 않고 설치 관리자 UI를 통해 관리 기능을 잠금 해제 하는 고급 설정 옵션
- 접근성 개선.
- 화면 밝기 제어 설정이 로그에 포함 됩니다.
- 보고서 생성기의 외부 모니터 호환성 지원 링크입니다.
