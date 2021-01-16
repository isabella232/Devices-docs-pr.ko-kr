---
title: 비즈니스용 Surface 진단 도구 키트 배포
description: 이 항목에서는 비즈니스용 Surface 진단 Toolkit 방법을 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271582"
---
# 비즈니스용 Surface 진단 도구 키트 배포

IT Toolkit SDT(비즈니스용 Microsoft Surface Diagnostic Toolkit)를 사용하면 IT 관리자가 Surface 디바이스에서 하드웨어, 소프트웨어 및 펌웨어 문제를 신속하게 조사, 문제 해결 및 해결할 수 있습니다. 다양한 진단 테스트 및 소프트웨어 복구를 실행할 수 있으며, 문제 해결을 위한 장치 상태 정보 및 지침을 얻을 수 있습니다. 

특히 비즈니스용 SDT를 사용하면 다음을 할 수 있습니다.

- [패키지를 사용자 지정합니다.](#preparing-the-sdt-package-for-distribution)
- [명령을 사용하여 앱을 실행합니다.](surface-diagnostic-toolkit-command-line.md)
- [여러 하드웨어 테스트를 실행하여 문제를 해결합니다.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [문제를 분석하기 위한 로그를 생성합니다.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [장치와 최적의 구성을 비교하는 자세한 보고서를 얻습니다.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## 기본 시나리오 및 리소스 다운로드 

비즈니스용 SDT를 실행하려면 다음 표에 나열된 구성 요소를 다운로드합니다.


모드 |  기본 시나리오 | 다운로드 | 자세히 알아보기
--- | --- | --- | ---
데스크톱 모드 |  사용자가 Surface 디바이스에서 SDT를 실행하여 문제를 해결할 수 있도록 지원합니다.<br>하나 이상의 Surface 디바이스에 배포할 사용자 지정 패키지를 만들어 사용자가 수집 및 분석할 특정 로그를 선택할 수 있습니다. | SDT 배포 가능 MSI 패키지:<br>비즈니스용 Microsoft Surface Toolkit 설치 관리자<br>[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703) | [데스크톱 모드에서 Surface 진단 Toolkit 사용](surface-diagnostic-toolkit-desktop-mode.md)
명령줄 |  Configuration Manager와 같은 표준 도구를 사용하여 사용자 조작 없이 원격으로 Surface 디바이스 문제를 직접 해결합니다. 여기에는 다음 명령이 포함됩니다.<br>`-DataCollector` 모든 로그 파일 수집<br>`-bpa` 모범 사례 분석기를 사용하여 상태 진단을 실행합니다.<br>`-windowsupdate` Windows 업데이트에서 펌웨어 또는 드라이버 업데이트 누락을 확인합니다.<br>`-warranty` 보증 정보를 검사합니다. <br><br>| SDT 콘솔 앱:<br>Microsoft Surface 진단 앱 콘솔<br>[IT용 Surface 도구](https://www.microsoft.com/download/details.aspx?id=46703) | [명령을 사용하여 Surface Toolkit 실행](surface-diagnostic-toolkit-command-line.md)

## 지원되는 디바이스 

비즈니스용 SDT는 다음을 포함하여 Surface 3 이상 디바이스에서 지원됩니다.

- Surface Book - 모든 세대
- Surface Go - 모든 세대
- Surface 노트북 - 모든 세대
- Surface Pro 3 이상
- Surface Pro X - 모든 세대
- Surface Studio - 모든 세대
- Surface 3 LTE
- Surface 3


## 비즈니스용 Surface 진단 Toolkit 설치

조직의 사용자에게 배포할 수 있는 SDT 패키지를 만들 수 있습니다.

1. 관리자 계정을 사용하여 Surface 디바이스에 로그인합니다.
2. [Surface Tools for IT 다운로드](https://www.microsoft.com/download/details.aspx?id=46703) 페이지에서 SDT Windows Installer 패키지(.msi)를 다운로드하여 Surface 디바이스의 기본 설정 위치(예: 데스크톱)에 복사합니다.
3. 그림 1과 같이 SDT 설정 마법사가 나타납니다. **다음**을 클릭합니다. 

    >[!NOTE]
    >설치 마법사가 나타나지 않는 경우 컴퓨터의 관리자 계정에 로그인해야 합니다. 

    ![Surface Diagnostic Toolkit 마법사 시작](images/sdt-1.png)

    *그림 1. Surface 진단 Toolkit 설정 마법사*

4. SDT 설정 마법사가 나타나면 다음을 **클릭하고**EULA(최종 사용자 사용권 계약)에 동의합니다.

5. 설치 옵션 화면에서 원하는 경우 기본 설치 위치를 변경합니다. 
6. 설치 유형에서 고급을 **선택합니다.** 

    >[!NOTE]
    >표준 옵션을 사용하면 관리자 계정을 사용하여 장치에 로그인한 경우 Surface 장치에서 직접 진단 도구를 실행할 수 있습니다. 
    
     ![설치 옵션: 고급](images/sdt-install.png)

7. 다음을 **클릭하고** 설치를 **클릭합니다.** 

## 명령줄을 사용하여 설치
원하는 경우 명령 프롬프트에서 SDT를 설치하고 사용자 지정 플래그를 설정하여 관리 모드로 도구를 설치할 수 있습니다. SDT에는 다음과 같은 설치 옵션 플래그가 포함되어 있습니다.

- `SENDTELEMETRY` 원격 분석 데이터를 Microsoft로 전송합니다. 플래그를 사용할 수 없습니다. 또는 `0` `1` 활성화할 수 있습니다. 기본값은 원격 분석 `1` 전송입니다.
- `ADMINMODE` 관리 모드로 설치할 도구를 구성합니다. 플래그는 클라이언트 모드 또는 IT 관리자 `0` `1` 모드에 허용됩니다. 기본값은 `0`입니다.

### 명령줄에서 SDT를 설치하려면

1. 명령 프롬프트를 열고 다음을 입력합니다.

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **예제:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Surface 디바이스에서 SDT 찾기

SDT와 SDT 앱 콘솔이 모두 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 에 설치됩니다.

SDT는 .exe 파일 외에 그림 2와 같이 JSON 파일과 admin.dll 파일(modules\admin.dll)을 설치합니다.

![파일 탐색기에서 설치된 SDT 파일 목록](images/sdt-2.png)

*그림 2. SDT에서 설치한 파일*

## 배포를 위해 SDT 패키지 준비

사용자 지정 패키지를 만들면 도구를 알려진 특정 문제로 대상으로 지정하는 데 사용할 수 있습니다.

1. 시작> **실행을 클릭하고** **Surface를** 입력한 다음 **비즈니스용 Surface 진단**Toolkit 클릭합니다. 
2. 도구가 열리면 **** 그림 3과 같이 사용자 지정 패키지 만들기를 클릭합니다.

    ![사용자 지정 패키지 옵션 만들기](images/sdt-3.png)

    *그림 3. 사용자 지정 패키지 만들기*

### 언어 및 원격 분석 설정

  패키지를 만들 때 언어 설정을 선택하거나 Microsoft에 원격 분석 정보를 보내지 옵트아웃(opt out)할 수 있습니다. 기본적으로 SDT는 Microsoft 개인 정보 취급 방침에 따라 응용 프로그램을 개선하는 데 사용되는 원격 분석 [기능을 Microsoft로 전송합니다.](https://privacy.microsoft.com/privacystatement) 거부할 경우 아래와 같이 사용자 지정 패키지를 만들 때 확인란의 선택을 취소합니다. 또는 SDT 설치 중에 설치 옵션 **** 페이지에서 **Microsoft로** 원격 분석 보내기 확인란의 선택을 취소합니다. 

>[!NOTE]
>이 설정은 Windows 업데이트 및 소프트웨어 복구와 같은 인터넷 연결이 필요한 테스트 및 복구를 실행하거나 앱 도구 모음의 스마일 또는 까다로워진 단추를 사용하여 피드백을 제공하는 경우 Microsoft 서버에 자동으로 저장되는 최소 원격 분석에는 영향을 주지 않습니다. 


![언어 및 원격 분석 설정 선택](images/sdt-4.png)

*그림 4. 언어 및 원격 분석 설정 선택*


### Windows 업데이트 페이지

조직에 적합한 옵션을 선택합니다. 일반적으로 사용자가 여러 명인 조직에서는 그림 5와 같이 WSUS(Windows Server Update Services)를 통해 업데이트를 받게 됩니다. 로컬 Windows 업데이트 패키지 또는 WSUS를 사용하는 경우 경로를 적절하게 입력합니다. 

![Windows 업데이트 옵션 선택](images/sdt-5.png)

*그림 5. Windows 업데이트 옵션*

### 소프트웨어 복구 페이지

이렇게 하면 소프트웨어 복구 업데이트를 실행하기 위한 옵션을 선택하거나 제거할 수 있습니다. 

![소프트웨어 복구 옵션 선택](images/sdt-6.png)

*그림 6. 소프트웨어 복구 옵션*

### 로그 수집 및 패키지 저장 페이지

응용 프로그램, 드라이버, 하드웨어 및 운영 체제에서 다양한 로그를 실행하기로 선택할 수 있습니다. 적절한 영역을 클릭하고 사용 가능한 로그의 메뉴에서 선택합니다. 그런 다음 사용자가 액세스할 수 있는 소프트웨어 배포 지점 또는 이에 상응하는 위치에 패키지를 저장할 수 있습니다. 

![로그 옵션 선택](images/sdt-7.png)

*그림 7. 로그 옵션 및 패키지 저장*

## 다음 단계

- [비즈니스용 Surface 진단 도구 키트를 데스크톱 모드에서 사용](surface-diagnostic-toolkit-desktop-mode.md)
- [명령을 사용하여 비즈니스용 Surface Toolkit 프로그램 사용](surface-diagnostic-toolkit-command-line.md)

## 변경 및 업데이트

### 버전 2.131.139.0

이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.

- Surface Pro 7+ 지원
- Surface Pro X의 원활한 지원 환경
- 보안 개선
- 포괄 사용자 환경 개선

### 버전 2.124.139.0

이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.

- 원활한 통합 지원
- 모든 테스트 결과 저장
- 이미지를 사용자 지정으로 만들지 확인
- 장치 관리자의 경고 포함
- Dock 펌웨어 버전
- 저장소 테스트에서 잠재적인 오류로 드라이브 플래그 지정
- 저장소 링크 제거 

### 버전 2.121.139
*릴리스 날짜: 2020년 7월 31일*<br>
이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.

- 원활한 지원 환경
- 버그 수정

### 버전 2.94.139.0
*릴리스 날짜: 2020년 5월 11일*<br>
이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.

- 하드웨어 검사를 수행하기 위해 Windows 업데이트를 건너뛰는 기능을 제공합니다.
- 최신 버전 업데이트에 대한 알림을 받을 수 있는 능력
- Surface Go 2
- Surface Book 3
- 진행률 표시기 표시


### 버전 2.43.139.0
*릴리스 날짜: 2019년 10월 21일*<br>
이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다.

- Surface Pro 7
- Surface 노트북 3

### 버전 2.42.139.0
*릴리스 날짜: 2019년 9월 24일*<br>
이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다. 
- 하드웨어 보고서를 다운로드하는 기능을 제공합니다.
- 도구에서 직접 Microsoft 지원에 문의할 수 있습니다. <br>

### 버전 2.41.139.0
*릴리스 날짜: 2019년 6월 24일*<br>
이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다. 
- 로그 및 보고서에 포함된 드라이버 버전 정보입니다.
- 앱에 대한 피드백을 제공하는 능력.<br>


### 버전 2.36.139.0
*릴리스 날짜: 2019년 4월 26일*<br>
이 버전의 비즈니스용 Surface Diagnostic Toolkit 다음에 대한 지원이 추가되었습니다. 
- 명령줄 구성 없이 설치 관리자 UI를 통해 관리자 기능을 잠금 해제하는 고급 설치 옵션입니다.
- 접근성 개선.
- 로그에 포함된 표면 밝기 컨트롤 설정입니다.
- 보고서 생성기의 외부 모니터 호환성 지원 링크
