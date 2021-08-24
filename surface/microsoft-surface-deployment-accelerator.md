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
ms.openlocfilehash: 48f89e8929bdb9d075bea988558fea234da5bbd2
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911423"
---
# <a name="microsoft-surface-deployment-accelerator"></a>Microsoft Surface 배포 가속기

Microsoft SDA(Surface 배포 가속기)는 무료 Microsoft 배포 도구를 사용하여 Microsoft 권장 배포 환경의 생성 및 구성을 자동화합니다.

회사 환경에서 Surface 이미지 배포를 간소화하고 자동화하기 위해 2020년 4월에 다시 디자인된 SDA 도구를 사용하면 조직의 요구 사항에 맞게 사용자 지정할 수 있는 "공장과 같은" Windows 이미지를 빌드할 수 있습니다.

오픈 소스 스크립트 기반 SDA 도구는 테스트 또는 프로덕션 환경에서 WIM(Windows 이미지)을 만들 수 있는 Windows 10 ADK(Windows Assessment and Deployment Kit)를 활용합니다. 최신 ADK가 설치되어 있지 않은 경우 SDA 도구를 실행하면 다운로드 및 설치됩니다.

결과 이미지는 미리 설치된 응용 프로그램(예: Microsoft Office 또는 Surface UWP 응용 프로그램 없이 BMR(Bare Metal Recovery) 이미지의 구성과 밀접하게 일치합니다.

## <a name="requirements"></a>요구 사항

1. USB 썸 드라이브(16GB 이상) USB 드라이브의 서식이 지정됩니다.
2. .iso 파일(Windows 10 Pro 또는 Windows 10 Enterprise. 미디어 만들기 도구를 사용하여 파일을 다운로드하고 Windows 10 파일을 만들 수 있습니다. 자세한 내용은 다운로드 를 [Windows 10.](https://www.microsoft.com/software-download/windows10)
3. 인터넷에 Windows 10 버전 2004 이상을 실행하는 장치입니다.

자세한 요구 사항 목록은 README 문서의 [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) 섹션을 참조하십시오.

## <a name="how-to-run-the-sda"></a>SDA를 실행하는 방법

**SDA를 실행합니다.**

1. 에서 [SurfaceDeploymentAccelerator로](https://github.com/microsoft/SurfaceDeploymentAccelerator) GitHub. 
2. [README 설명서를 검토합니다.](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md)
3. [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 페이지에서 코드 단추를 클릭한 다음 **ZIP** 다운로드를 선택하여 컴퓨터에 로컬로 파일을 저장합니다. ****
4. 파일 .zip 마우스 오른쪽 단추로 클릭한 다음 속성을 **클릭합니다.**
5. 일반 **탭에서** 차단 해제 **확인란을** 선택한 다음 확인 을 **클릭합니다.**
6. 하드 .zip 위치로 파일 추출(예: C:\SDA).
7. 승강된 Windows PowerShell 프롬프트를 열고 현재 세션의 ExecutionPolicy를 무제한으로 설정합니다.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. 환경에 대한 매개 변수를 지정하는 SDA 스크립트를 실행합니다. 이 스크립트를 사용하여 다양한 Surface 디바이스에 Windows 10 이미지를 만들 수 있습니다. 지원되는 장치의 전체 목록은 SDA README 문서의 [Device 매개](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 변수 설명을 참조하세요. 

    예를 들어 다음 명령은 [2에](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)설치하는 데 사용할 수 있는 부팅 가능한 USB 드라이브를 Windows 10 Surface Hub 있습니다.

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    샘플 스크립트 출력은 아래에 있습니다.

   ![Surface 배포 가속기 도구를 실행합니다.](images/sda1.png)

    스크립트를 실행하려면 약 45분이 필요하지만 사용 가능한 CPU 및 디스크 리소스에 따라 더 오래 걸릴 수 있습니다. 

    스크립트를 Windows USB 드라이브의 드라이브 문자를 삽입하고 확인하게 됩니다. 그런 다음 USB 드라이브의 서식을 지정하고 부팅 가능으로 구성하며, Surface 디바이스에 대한 사용자 지정 Windows 10 이미지를 설치할 수 있도록 복사됩니다.

9. USB 드라이브를 설치하려는 장치에 USB 드라이브를 Windows 10 다시 시작하여 설치를 Windows 10. USB 부팅은 BIOS에서 사용하도록 설정해야 합니다. 이 경우 보안 부팅을 일시적으로 사용하지 않도록 설정해야 할 수 있습니다.

> [!IMPORTANT]
> USB 드라이브에서 부팅하면 즉시 USB 드라이브 설치가 Windows 10. USB를 삽입하고 다시 시작하기 전에 장치가 준비되어 있는지 확인합니다. 

## <a name="related-links"></a>관련 링크

 - [2016년 8월에 릴리스된 오픈 소스 이미지 GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [ADK 다운로드 Windows 설치](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
