---
title: Surface 밝기 제어
description: 이 항목에서는 Surface 명도 컨트롤 앱을 사용 하 여 판매 시점 및 키오스크 시나리오에서 디스플레이 밝기를 관리 하는 방법에 대해 설명 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835807"
---
# Surface 밝기 제어

판매 시점이 나 다른 "항상 켜져 있는" 키오스크 시나리오에서 Surface 디바이스를 배포 하는 경우 새 Surface 밝기 제어 앱을 사용 하 여 전원 관리를 최적화할 수 있습니다.

[해당 앱에 대 한 Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703)를 사용 하 여 다운로드할 수 있습니다.
Surface 밝기 제어는 열 로드를 줄이고 배포 된 Surface 디바이스의 전체 지원 공간을 낮출 수 있도록 설계 되었습니다.
다운로드 페이지에서이 도구만 가져오려는 경우 사용 가능한 목록에서 **Surface_Brightness_Control_v1.16.137.0.msi** 파일을 선택 합니다.
이 도구는 사용 하지 않는 경우 화면을 자동으로 어둡게 하 고 다음 구성 옵션을 포함 합니다.

- 디스플레이를 흐리게 하기 전의 비활성 시간입니다.

- 흐리게 표시 되는 경우 밝기 수준

- 사용 중인 경우 최대 밝기 수준

**Surface 밝기 제어를 실행 하려면:**

- 대상 장치에 surfacebrightnesscontrol.msi 설치 하 고 Surface 명도 컨트롤이 즉시 작동을 시작 합니다.

## 표면 밝기 제어 구성

Windows 레지스트리를 통해 기본 값을 조정할 수 있습니다. Windows 레지스트리를 사용 하는 방법에 대 한 자세한 내용은 [레지스트리 설명서](https://docs.microsoft.com/windows/desktop/sysinfo/registry)를 참조 하세요.

1.  명령 프롬프트에서 regedit를 실행 하 여 Windows 레지스트리 편집기를 엽니다.
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 밝기 제어 \ 
    
    이전 버전의 Surface 명도 컨트롤을 실행 중인 경우에는 대신 다음 명령을 실행 합니다.
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface 밝기 제어 \


| 레지스트리 설정 | 데이터| 설명  
|-----------|------------|---------------
| 밝기 컨트롤 사용  |  기본값: 01  <br> 옵션: 01, 00 <br> 종류: REG_BINARY |  이 설정을 통해 Surface 명도 컨트롤을 켜거나 끌 수 있습니다. Surface 밝기 제어를 해제 하려면 값을 00으로 설정 합니다. 이 설정을 구성 하지 않으면 Surface 밝기 컨트롤이 켜져 있습니다. |
| 전원을 사용할 때 밝기 제어| 기본값: 01 <br> 옵션: 01, 00 <br> 종류: REG_BINARY | 이 설정을 사용 하면 디바이스가 직접 전원에 연결 되어 있을 때 Surface 명도 컨트롤을 끌 수 있습니다. 전원이 연결 된 상태에서 Surface 밝기 제어를 비활성화 하려면 값을 00으로 설정 합니다. 이 설정을 구성 하지 않으면 Surface 밝기 컨트롤이 켜져 있습니다. |
| 흐린 밝기   | 기본값: 20  <br>옵션: 0-100% 화면 밝기의 범위 <br> 데이터 형식: 양의 정수 <br> 종류: REG_DWORD | 이 설정을 사용 하면 비활성 기간 동안 밝기 범위를 관리할 수 있습니다. 이 설정을 구성 하지 않으면 약 30 초 후에 밝기 수준이 전체 밝기의 20%로 조정 됩니다. |
전체 밝기   | 기본값: 100  <br>옵션: 0-100% 화면 밝기의 범위 <br> 데이터 형식: 양의 정수 <br> 종류: REG_DWORD  | 이 설정을 통해 디바이스의 최대 밝기 범위를 관리할 수 있습니다. 이 설정을 구성 하지 않으면 최대 밝기 범위는 100%입니다.|  
| 비활성 시간 제한| 기본값: 30 초 <br>옵션: 모든 숫자 값  <br>데이터 형식: Integer  <br> 종류: REG_DWORD | 이 설정을 사용 하면 장치를 흐리게 표시 하기 전에 비활동 기간을 관리할 수 있습니다. 이 설정을 구성 하지 않으면 비활동 제한 시간이 30 초입니다.|
| 원격 분석 사용 | 기본값: 01 <br>옵션: 01, 00 <br> 종류: REG_BINARY  | 이 설정을 사용 하면 앱 사용 정보의 공유를 관리 하 여 소프트웨어를 개선 하 고 더 나은 사용자 환경을 제공할 수 있습니다. 원격 분석을 사용 하지 않으려면 값을 00으로 설정 합니다. 이 설정을 구성 하지 않으면 [microsoft](https://privacy.microsoft.com/privacystatement)에서 원격 분석 정보를 사용할 수 있습니다. |

## 변경 및 업데이트

### 버전 1.16.137<br>
*릴리스 날짜: 2019 년 10 월 22 일*<br>
이 버전의 Surface light 컨트롤은 x86 용으로 다시 컴파일한 다음이에 대 한 지원을 추가 하 고 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에 대 한 지원을 추가 합니다. 

### 버전 1.12.239.0
*릴리스 날짜: 26 년 4 월 2019*<br>
이 버전의 Surface 명도 컨트롤은 다음에 대 한 지원을 추가 합니다.
- 터치 지연 수정.


## 관련 항목

- [배터리 용량 한도 설정](battery-limit.md)
