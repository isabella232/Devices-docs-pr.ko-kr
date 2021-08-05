---
title: Surface 디바이스에서 PEAP, EAP-FAST 및 Cisco LEAP 사용(Surface)
description: Surface 디바이스에서 PEAP, EAP-FAST 또는 Cisco LEAP 프로토콜을 지원하도록 설정하는 방법에 대해 알아보세요.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: 네트워크, 무선, 디바이스, 배포, 인증 프로토콜
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: e887a449fb00b76c14de5b8ede51a1ba91a6b4c4
ms.sourcegitcommit: 6d531906c36da51cb4032a220d70182e686114a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2021
ms.locfileid: "11721248"
---
# <a name="enable-peap-eap-fast-and-cisco-leap-on-surface-devices"></a>Surface 디바이스에서 PEAP, EAP-FAST 및 Cisco LEAP 사용

Surface 디바이스에서 PEAP, EAP-FAST 또는 Cisco LEAP 프로토콜을 지원하도록 설정하는 방법에 대해 알아보세요.

엔터프라이즈 네트워크에서 PEAP, EAP-FAST 또는 Cisco LEAP를 사용하는 경우 이러한 세 가지 무선 인증 프로토콜이 기본 제공되는 Surface 디바이스에서 지원되지 않음을 이미 알고 있을 수도 있습니다. 무선 네트워크에 연결하려고 할 때 또는 파일 공유와 내부 사이트와 같이 네트워크 내부 리소스에 대한 액세스 권한을 얻지 못할 때 알 수도 있습니다. 자세한 내용은 [Extensible Authentication Protocol](/windows-server/networking/technologies/extensible-authentication-protocol/network-access)(확장할 수 있는 인증 프로토콜)을 참조하세요.

USB 스틱 또는 파일 공유에서 작은 MSI 패키지를 실행하여 각 프로토콜에 대한 지원을 추가할 수 있습니다. Surface 디바이스에서 EAP 지원을 사용하도록 설정하려는 조직의 경우 MSI 패키지 형식은 MDT(Microsoft Deployment Toolkit) 및 배포와 같은 다양한 관리 및 배포 도구를 Microsoft Endpoint Configuration Manager.

## <a name="download-peap-eap-fast-or-cisco-leap-installation-files"></a><a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a>PEAP, EAP-FAST 또는 Cisco LEAP 설치 파일 다운로드

EAP, EAP-FAST 또는 Cisco LEAP에 대한 MSI 설치 파일을 Microsoft 다운로드 센터에서 하나의 zip 보관 파일로 다운로드할 수 있습니다. 이 파일을 다운로드하려면 Microsoft 다운로드 센터에서 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)(IT용 Surface 도구) 페이지로 이동하여 **Download**(다운로드)를 클릭한 다음 **Cisco EAP-Supplicant Installer.zip** 파일을 선택하세요.

## <a name="deploy-peap-eap-fast-or-cisco-leap-with-mdt"></a>MDT로 PEAP, EAP-FAST 또는 Cisco LEAP 배포

조직에서 Surface 디바이스에 Windows 배포를 이미 수행 중인 경우 빠르고 쉽게 각 프로토콜에 대한 설치 파일을 배포 공유에 추가하고 배포 중 자동 설치를 구성할 수 있습니다. 업데이트에서 이전에 Surface 디바이스를 배포한 작업 순서를 구성하여 동일한 프로세스로 이러한 프로토콜에 대한 지원을 제공할 수 있습니다.

새로 배포된 Surface 디바이스에서 PEAP, EAP-FAST 또는 Cisco LEAP에 대한 지원을 사용하도록 설정하려면 다음 단계를 따르세요.

1. 각 프로토콜에 대한 설치 파일을 다운로드하고 추출하여 쉽게 액세스할 수 있는 위치에 폴더를 분리합니다.

2. MDT Deployment Workbench를 열고 배포 공유를 **Applications**(응용 프로그램) 폴더로 확장합니다.

3. **Action**(동작) 창에서 **New Application**(새 응용 프로그램)을 선택합니다.

4. **Application with source files**(응용 프로그램 및 원본 파일)를 선택하여 배포 공유에 MSI 파일을 복사합니다.

5. 원하는 프로토콜에 대해 1단계에서 만든 폴더를 선택합니다.

6. 배포 공유에서 설치 파일을 저장할 폴더의 이름을 지정합니다.

7. 명령줄을 지정하여 응용 프로그램을 배포합니다.

    - PEAP: **EAP PEAP.msi /qn /norestart**.

    - LEAP: **EAP LEAP.msi /qn /norestart**.

    - EAP-FAST: **EAP FAST.msi /qn /norestart**.

8. 기본 옵션을 사용하여 새 응용 프로그램 마법사를 완료합니다.

9. 원하는 각 프로토콜에 대해 3-8단계를 반복합니다.

위의 단계를 수행하여 응용 프로그램으로 세 가지 MSI 패키지를 MDT로 가져오면 Windows 배포 마법사의 Applications(응용 프로그램) 페이지에서 선택할 수 있습니다. 일부 간단한 배포 시나리오에서는 관리자가 배포 시 각 패키지를 선택하도록 해도 충분하지만 권장되지는 않습니다. 이 사례에서는 관리자가 Surface 디바이스가 아닌 컴퓨터에 이 패키지를 적용하려고 하거나, 휴먼 오류로 인해 EAP 지원 없이 Surface 디바이스를 배포할 수 있는 가능성에 대해 소개합니다.

Install Applications page(응용 프로그램 설치) 페이지에서 이러한 응용 프로그램을 숨기려면 각 응용 프로그램의 속성에서 **Hide this application in the Deployment Wizard**(배포 마법사에서 이 응용 프로그램 숨기기) 확인란을 선택합니다. 응용 프로그램이 숨겨지면 배포 중에는 선택적 응용 프로그램으로 표시되지 않습니다. Surface 배포 작업 순서에서 배포하려면 작업 순서에서 별도의 단계를 통해 설치할 수 있도록 명시적으로 정의해야 합니다.

프로토콜을 명시적으로 지정하려면 다음 단계를 따르세요.

1. MDT Deployment Workbench에서 Surface 배포 작업 순서 속성을 엽니다.

2. **Task Sequence**(작업 순서) 탭에서 **State Restore**(상태 복원) 아래의 **Install Applications**(응용 프로그램 설치)를 선택합니다. 일반적으로 사전 응용 프로그램 및 사후 응용 프로그램의 Windows 업데이트 단계 사이에서 발생합니다.

3. **Add**(추가) 단추를 사용하여 **General**(일반) 범주 아래에서 새 **Install Application**(응용 프로그램 설치) 단계를 만듭니다.

4. **속성** 탭에서 **Install a single application**(단일 응용 프로그램 설치) 단계를 선택합니다.

5. 목록에서 원하는 EAP 프로토콜을 선택합니다.

6. 원하는 각 프로토콜에 대해 2-5단계를 반복합니다.

## <a name="deploy-peap-eap-fast-or-cisco-leap-with-configuration-manager"></a>Configuration Manager를 사용하여 PEAP, EAP-FAST 또는 Cisco LEAP 배포

Configuration Manager를 사용하여 Surface 디바이스를 관리하는 조직의 경우 PEAP, EAP-FAST 또는 Cisco LEAP 지원을 Surface 디바이스에 배포하는 것이 훨씬 더 간단합니다. 소프트웨어 라이브러리에서 각 MSI 파일을 응용 프로그램으로 가져와 Surface 디바이스 컬렉션에 배포를 구성하기만 하면 됩니다.

Configuration Manager를 사용하여 응용 프로그램을 배포하는 방법에 대한 자세한 내용은 Configuration Manager를 사용하여 응용 프로그램 만들기 및 [배포를 참조하세요.](/mem/configmgr/apps/get-started/create-and-deploy-an-application.md)
