---
title: Surface용 절전 모드 해제를 사용하도록 설정하는 방법
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Surface 디바이스의 전원 절전 모드 해제 및 해제 방법을 설명하는 문서입니다.
keywords: 업데이트, 배포, 드라이버, wol, 절전 모드 해제
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271562"
---
# Surface 디바이스에 대한 Wake On Power

책상에 있는 동안 Surface 디바이스를 꺼지거나 최대 절전 모드로 설정하여 배터리 사용 시간을 절약할 수 있습니다. 이러한 디바이스의 관리 성능을 향상하기 위해 절전 모드 해제를 사용하면 호환되는 Surface 디바이스가 전원에 다시 연결될 때 자동으로 시작됩니다. 전원 절전 모드 해제를 구성하기 위해 Surface UEFI 구성기 또는 UEFI 관리자를 통해 SURFACE SEMM(엔터프라이즈 관리 모드)을 사용할 수 있습니다.

절전 모드 해제 기능은 다음 장치에서 사용할 수 있습니다.

- Surface Pro 7+
- Surface Book 3
- Surface Pro 7
- Surface 노트북 3
- Surface 노트북 이동
- Surface Pro X 


## 개요 및 선행 사항

Surface UEFI 구성 도구를 사용하면 대상 장치에 배포하기 위해 개별 UEFI 설정을 Windows Installer .msi 패키지에 저장할 수 있습니다. 

> [!NOTE]
> 이 문서에서는 SEMM 사용 방법을 알고 있는 것으로 가정합니다. 자세한 내용은 [SURFACE SEMM(엔터프라이즈 관리 모드) 설명서를 참조하세요.](surface-enterprise-management-mode.md)

## 절전 모드 해제를 사용하도록 설정하려면

1.  최신 버전의 [Surface UEFI 구성기 다운로드](https://www.microsoft.com/download/confirmation.aspx?id=46703)
2.  관리자 권한으로 Surface 디바이스에 로그인하고 **Surface UEFI 구성**관리자를 열고 **Surface 디바이스를**선택한 후 다음을 **선택합니다.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Surface 디바이스를 선택하고 다음을 선택합니다.":::
3.  시작을 선택한 다음 **구성 패키지에서** **** **만들기를 선택합니다.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="구성 패키지 만들기를 선택합니다.":::
4.  인증서 **보호를 선택하고**인증서 .pfx 파일을 추가합니다. 
5. Enter your password, select **Next,** add **Password Protection**, as appropriate, and then select **Next.**
6.  대상으로 **지정하려는 Surface** 유형 선택 페이지에서 대상 디바이스를 적절하게 선택합니다. 예를 들어 **Surface Pro 7을 선택합니다.**
7.  고급 기능 **페이지에서** 전원 **** 절전 모드 해제를 선택하고 기능을 **On으로**설정한 후 다음을 **선택합니다.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="전원 절전 모드 해제를 선택하고 설정으로 설정"::: 
8.  성공 **페이지에서** 종료를 **선택합니다.**

    > [!NOTE]
    > 장치에 설정을 처음 제공하는 경우 인증서 지문의 마지막 두 문자도 제공하라는 메시지가 표시됩니다. 
9.  .msi 패키지를 저장합니다. 

## MSI 패키지 적용 

Microsoft Endpoint Configuration Manager와 같은 소프트웨어 배포 도구를 사용하여 네트워크의 장치에 MSI 패키지를 적용할 수 있습니다. 이 절차에는 로컬 컴퓨터에 패키지를 설치하는 단계가 포함됩니다. 

1.  승격된 명령 프롬프트에서 .msi 파일의 전체 경로를 입력하여 .msi 패키지를 실행합니다. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  경고 **대화** 상자에서 확인을 **선택하거나** BitLocker를 사용하지 않도록 설정하십시오.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="확인을 선택하거나 BitLocker를 적절하게 사용하지 않도록 설정하십시오.":::
3.  시작 페이지에서 다음을 **선택하여** 패키지를 실행하고 새로 구성된 UEFI 설정을 적용합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="시작 페이지 중 하나에서 다음을 선택합니다.":::
4.  장치를 다시 시작합니다. 

전원 절전 모드 해제가 구성됩니다. 설정을 테스트하려면 디바이스를 끄고 전원을 끊은 다음 전원을 다시 연결합니다. 장치가 자동으로 시작해야 합니다. 

## 참조

자세한 내용은 다음 문서를 참조하세요. 

- [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
- [Surface 디바이스용 LAN 절전 모드 해제](wake-on-lan-for-surface-devices.md)

그래도 문제가 해결되지 않을 경우 Microsoft [커뮤니티로 이동](https://answers.microsoft.com/)