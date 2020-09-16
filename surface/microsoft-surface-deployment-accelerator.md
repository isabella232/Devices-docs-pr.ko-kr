---
title: Microsoft Surface 배포 가속기(Surface)
description: Microsoft Surface 배포 가속기는 조직에서 Surface 디바이스의 이미지를 다시 작성하기 위한 빠르고 간편한 배포 메커니즘을 제공합니다.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 배포, 설치, 도구
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 0e136bd0a69db7a4c4e5cea7d2c065727dcc8fcc
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016444"
---
# Microsoft Surface 배포 가속기

SDA (microsoft Surface Deployment Accelerator)는 무료 Microsoft 배포 도구를 사용 하 여 Microsoft 권장 배포 환경의 작성과 구성을 자동화 합니다.

2020 년 4 월에 다시 디자인 됨 기업 환경에서 화면 이미지 배포를 간소화 하 고 자동화 하기 위해 SDA 도구를 사용 하 여 조직의 요구 사항에 맞게 사용자 지정할 수 있는 "팩토리" Windows 이미지를 빌드할 수 있습니다.

오픈 소스, 스크립트 기반 SDA 도구는 Windows 10 용 Windows ADK (평가 및 배포 키트)를 활용 하 여 테스트 또는 프로덕션 환경에서 WIM (Windows 이미지) 만들기를 촉진 합니다. 최신 ADK가 아직 설치 되지 않은 경우, SDA 도구를 실행할 때 다운로드 및 설치 됩니다.

결과 이미지는 Microsoft Office 또는 Surface UWP 응용 프로그램과 같이 사전 설치 된 응용 프로그램 없이도 완전 복구 (BMR) 이미지의 구성과 일치 합니다.

## 요구 사항

1. USB 엄지 드라이브의 크기는 16gb 이상입니다. USB 드라이브의 포맷이 표시 됩니다.
2. Windows 10 Pro 또는 Windows 10 Enterprise를 사용 하는 .iso 파일 미디어 만들기 도구를 사용 하 여 Windows 10을 다운로드 하 고 .iso 파일을 만들 수 있습니다. 자세한 내용은 [Windows 10 다운로드](https://www.microsoft.com/software-download/windows10)를 참조 하세요.

## SDA를 실행 하는 방법

**SDA를 실행 하려면 다음을 수행 합니다.**

1. GitHub에서 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 으로 이동 합니다. 
2. [추가 정보](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 문서를 검토 합니다.
3. [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 페이지에서 **코드** 단추를 클릭 한 다음 **ZIP 다운로드** 를 선택 하 여 파일을 컴퓨터에 로컬로 저장 합니다.
4. .Zip 파일을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.
5. **일반** 탭에서 **차단 해제** 확인란을 선택 하 고 **확인**을 클릭 합니다.
6. 하드 드라이브의 위치 (예: C:\SDA)에 .zip 파일의 압축을 풉니다.
7. 관리자 권한 Windows PowerShell 프롬프트를 열고 현재 세션에 대 한 ExecutionPolicy를 무제한으로 설정 합니다.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. 사용자 환경에 대 한 매개 변수를 지정 하는 SDA 스크립트를 실행 합니다. 예를 들어 다음 명령을 실행 하면 Surface Hub 2에 Windows 10을 설치 하는 데 사용할 수 있는 부팅 가능 USB 드라이브가 만들어집니다.

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```

   ![Surface Deployment Accelerator 도구 실행](images/sda1.png)

    스크립트를 실행 하는 데 약 45 분이 필요 하지만 사용 가능한 CPU 및 디스크 리소스에 따라 시간이 더 걸릴 수 있습니다. 

    Windows 이미지를 만든 후 스크립트는 USB 드라이브의 드라이브 문자를 확인 하 라는 메시지를 표시 합니다. 그런 다음 USB 드라이브는 부팅 가능으로 구성 되 고 화면 장치에 대 한 사용자 지정 Windows 10 이미지의 설치를 위해 복사 된 파일을 사용 하도록 설정 됩니다.

9. Windows 10을 설치할 장치에 USB 드라이브를 삽입 하 고 다시 부팅 하 여 Windows 10 설치를 시작 합니다. BIOS에서 USB 부팅을 사용 하도록 설정 해야 하며, 보안 부팅을 일시적으로 사용 하지 않도록 설정할 수 있습니다.

> [!IMPORTANT]
> USB 드라이브에서 부팅 하는 즉시 Windows 10 설치를 시작 합니다. USB를 삽입 하 고 다시 시작 하기 전에 장치가 준비 되었는지 확인 합니다. 

## 관련 링크

 - [GitHub에서 릴리스된 소스 이미지 배포 도구 열기](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Windows ADK 다운로드 및 설치](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
