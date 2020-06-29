---
title: Surface Hub 2S용 프로비전 패키지 만들기
description: 이 페이지에서는 프로비저닝 패키지 및 기타 도구를 사용 하 여 Surface Hub 2S를 배포 하는 방법을 설명 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836939"
---
# Surface Hub 2S용 프로비전 패키지 만들기

Windows 구성 디자이너 (WCD)를 사용 하 여 Surface Hub 2S 배포 프로세스를 자동화 하는 프로비저닝 패키지를 만들 수 있습니다. 배포 패키지를 사용 하 여 인증서를 추가 하 고 프록시를 구성 하 고 디바이스 관리자 및 장치 계정을 설정 합니다. 구성 파일과 함께 프로비저닝 패키지를 사용 하 여 단일 USB 엄지 드라이브로 여러 Surface Hub를 배포할 수도 있습니다.

### Windows 구성 디자이너 설치

Windows 10 용 Windows ADK (평가 및 배포 키트)에서 Windows 구성 디자이너를 설치 합니다. [Windows 10 버전 1703 용 ADK](https://go.microsoft.com/fwlink/p/?LinkId=845542)를 다운로드 하 여 설치 합니다. 자세한 내용은 [WINDOWS ADK 다운로드 및 설치](https://docs.microsoft.com/windows-hardware/get-started/adk-install)를 참조 하세요.

### 인증서 추가

Surface Hub 2S 인증 기관 인증서를 가져올 수 있습니다.
Surface Hub 2S에 인증서를 추가 하려면 각 인증서의 복사본이 .cer 형식의 x.509로 필요 합니다. .Crt, .pfx 또는 기타 컨테이너 형식을 가져올 수 없습니다. 인증서를 Windows 구성 디자이너로 가져오고 계층 구조로 정렬 해야 합니다.

 ![인증서 추가](images/sh2-wcd.png)

### OOBE 중 프록시 구성

Windows 구성 디자이너에서 프록시 설정 구성 탭으로 이동 하 여 아래와 같이 적절 한 설정을 입력 합니다.

 ![프록시 설정 구성](images/sh2-proxy.png) 

> [!NOTE]
> 프록시 설정을 구성할 때 설정 스크립트 또는 프록시 서버를 사용 하려는 경우 **자동으로 설정 검색** 기능을 해제 합니다. 설치 *스크립트나 프록시 서버는 둘* 다 사용할 수 없습니다.

### Azure Active Directory를 사용 하는 계열사 Surface Hub 2S

프로 비전 패키지를 사용 하 여 Azure Active directory와의 계열사 Surface Hub 2S를 사용할 수 있습니다. Azure Active Directory 전역 관리자는 대량 토큰을 사용 하 여 많은 수의 새 Windows 장치를 Azure Active Directory 및 Intune에 참가할 수 있습니다.

대량 토큰을 만들려면 이름을 지정 하 고 만료 날짜 (최대 30 일)를 구성 하 고 관리자 자격 증명을 사용 하 여 아래와 같이 토큰을 취득 합니다.

 ![장치 관리자 설정](images/sh2-token.png) <br><br>
 ![장치 관리자 설정](images/sh2-token2.png) <br><br>
 ![장치 관리자 설정](images/sh2-token3.png) <br><br>

### 여러 장치 프로 비전 (.csv 파일)

배포 패키지 외에도 Surface Hub 구성 파일을 사용 하 여 디바이스를 더 쉽게 설정할 수 있습니다. Surface Hub 구성 파일에는 디바이스 계정 목록과 무선 프로젝션에 대 한 친숙 한 이름이 포함 되어 있습니다. 처음 실행 하는 동안 구성 파일에서 디바이스 계정과 이름을 선택 하는 옵션이 표시 됩니다.

### Surface Hub 구성 파일을 만들려면

1. Microsoft Excel 또는 다른 CSV 편집기를 사용 하 여 다음 이름의 CSV 파일을 만듭니다. **SurfaceHubConfiguration.csv**
2. 다음과 같은 형식으로 디바이스 계정과 이름 목록을 입력 합니다.

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. PPKG 파일을 복사한 USB 엄지 드라이브의 루트에 파일을 저장 합니다.

    ![구성 파일 예제](images/sh2-config-file.png)
