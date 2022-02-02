---
title: Surface 배포용 OOBE 사용자 지정(Surface)
description: 이 문서에서는 조직에서 Surface 첫 실행 경험을 최종 사용자에게 맞게 사용자 지정하는 과정을 안내합니다.
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: 배포, 사용자 지정, 자동화, 네트워크, 펜, 쌍, 부팅
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: f460577c6c0d87586d80e183dfeaf2796b8a3bbe
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338301"
---
# <a name="customize-the-oobe-for-surface-deployments"></a>Surface 배포용 OOBE 사용자 지정

이 문서에서는 조직의 최종 사용자를 위해 Surface 첫 제공 환경을 사용자 지정하는 방법을 설명합니다.

일반적으로 Windows 배포 과정에서 배포된 컴퓨터를 처음 시작하는 사용자 환경, 즉 OOBE(첫 실행 경험)를 사용자 지정합니다.

>[!TIP]
>또한 대개 OOBE를 사용하여 사용자 환경이 표시되는 Windows 설치 프로그램의 단계(구성 단계)를 설명합니다. 설치 프로그램의 OOBE 단계에 대한 자세한 내용은 [구성 단계 작동 방식](/windows-hardware/manufacture/desktop/how-configuration-passes-work)을 참조하세요.

일부 시나리오에서는 배포가 종료되면 아무런 사용자 조작 없이 컴퓨터를 사용할 준비가 되도록 완전한 자동화 기능을 제공할 수 있습니다. 다른 시나리오에서는 사용자가 필요한 작업을 수행하거나 중요한 옵션 중에서 선택할 수 있도록 주요 환경 요소를 유지할 수도 있습니다. 이러한 각 시나리오에서 Surface 디바이스에 배포하는 관리자는 해결해야 할 고유한 과제가 있습니다.

> [!NOTE]
> 이 문서는 X에 적용되지 Surface Pro 않습니다. 자세한 내용은 X에서 배포[, 관리 및 Surface Pro 참조하세요.](surface-pro-arm-app-management.md)

이 문서에서는 배포 시 추가 단계가 필요할 수도 있는 시나리오를 요약하여 보여 줍니다. 또한 새로 배포된 Surface 디바이스에서 원하는 환경을 구현하는 데 필요한 정보를 제공합니다. 이 문서는 배포 프로세스뿐 아니라 응답 파일 및 [참조 이미지](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image)와 같은 개념에 익숙한 관리자를 대상으로 합니다.

>[!NOTE]
>설치의 OOBE 단계는 [MDT(Microsoft Deployment Toolkit) 또는 OSD](/mem/configmgr/mdt)(Microsoft Endpoint Configuration Manager [Operating System Deployment)](/mem/configmgr/osd/)와 같은 자동화된 배포 솔루션의 일부로 실행되고도 배포 마법사 및 작업 순서에 제공된 설정에 의해 자동화됩니다.

## <a name="scenario-1-wireless-networking-in-oobe-with-mdt-2013"></a>시나리오 1: MDT 2013을 사용하여 OOBE에서 무선 네트워킹

OOBE 중 무선 네트워크 어댑터가 표시되면 **무선 네트워크 연결** 페이지가 나타나 사용자에게 무선 네트워크에 연결하라는 메시지가 표시됩니다. 이 페이지는 MDT 2013과 같은 배포 기술에서 자동으로 숨겨지지 않습니다. 따라서 완벽하게 자동화되도록 배포를 구성한 경우에도 표시됩니다.

이 페이지에서 자동화된 배포가 중지되지 않도록 응답 파일 **HideWirelessSetupInOOBE**에서 추가 설정을 구성하여 페이지를 숨겨야 합니다. **HideWirelessSetupInOOBE** 설정에 대한 추가 정보는 [Windows 무인 설치 참조](/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-oobe-hidewirelesssetupinoobe)에서 참조할 수 있습니다.

## <a name="scenario-2-surface-pen-pairing-in-oobe"></a>시나리오 2: OOBE에서 Surface 펜 페어링

Surface 디바이스를 처음 받아 시작하면 팩터리 이미지의 첫 실행 경험에 포함된 Surface 펜을 디바이스에 페어링하라는 메시지가 포함됩니다. 이 프롬프트는 디바이스와 함께 제공되는 출하 시 이미지에서만 제공되며, 볼륨 라이선스 서비스 센터에서 다운로드하는 Windows Enterprise 설치 미디어와 같은 배포에 사용되는 다른 이미지에는 포함되지 않습니다. 이 환경이 아닌 상태에서 Bluetooth Surface 펜을 페어링할 경우에는 제어판 또는 PC 설정을 시작하여 Bluetooth 디바이스를 수동으로 페어링해야 하므로 페어링 작업을 수행하기 위해 사용자나 관리자가 이 프롬프트를 사용하도록 할 수 있습니다.

OOBE에서 처음 Surface 펜 페어링 환경을 제공하려면 출하 시 Surface 이미지 파일 4개를 참조 이미지로 복사해야 합니다. 참조 이미지를 캡처하기 전에 참조 환경으로 이 파일을 복사하거나, DISM(배포 이미지 서비스 및 관리)을 사용해 이미지를 마운팅하여 나중에 추가할 수 있습니다. 필요한 파일 4개는 다음과 같습니다.

- %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
- %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
- %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
- %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!TIP]
>배포하려는 동일한 모델 Surface 디바이스의 출하 시 이미지에서 파일을 복사해야 합니다. 예를 들어 Surface Pro 8의 파일을 사용하여 Surface Pro 8에 배포하고 Surface Book 3의 파일을 사용하여 Surface Book 3을 배포해야 하지만 Surface Pro 8의 파일을 사용하여 Surface Book 3 또는 Surface Pro 7.

이러한 필수 파일을 이미지에 추가하기 위한 단계별 프로세스는 [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/)(Surface Pro 3 펜 및 OneNote 팁 배포)를 참조하세요. 이 블로그에는 Surface 펜 빠른 노트 작성 환경에 필요한 업데이트를 설치하여 사용자가 한 번의 클릭으로 노트를 OneNote로 보낼 수 있게 하는 팁도 포함되어 있습니다.
