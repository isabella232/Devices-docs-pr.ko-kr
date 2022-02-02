---
title: Surface 디바이스에 대한 Wake On Power
ms.author: greglin
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Surface 디바이스용 절전 모드 해제를 활성화 및 비활성화하는 방법을 설명하는 문서입니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 12/08/2021
ms.openlocfilehash: e8e4ddbd559fc6aea2d04e61208b911ebef3ec22
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338401"
---
# <a name="wake-on-power-for-surface-devices"></a>Surface 디바이스에 대한 Wake On Power

책상에서 벗어날 때 Surface 디바이스의 전원을 끄거나 최대 절전 모드로 설정하여 배터리 사용 시간을 절약할 수 있습니다. 이러한 디바이스의 관리성을 개선하기 위해 절전 모드 해제를 사용하면 호환되는 Surface 디바이스가 전원에 다시 연결될 때 자동으로 시작할 수 있습니다. 절전 모드 해제를 구성하기 위해 Surface UEFI Enterprise UEFI 관리자를 통해 Surface Enterprise 관리 모드(SEMM)를 사용할 수 있습니다.

절전 모드 해제 기능은 다음 장치에서 사용할 수 있습니다.

- Surface Pro 8(상업용 SUS만 해당)
- Surface Pro 7+(상업용 SKUS만 해당)
- Surface Pro X(모든 SKUS)
- Surface Pro 7(모든 SKUS)
- Surface Go 3(상업용 SKUS만 해당)
- Surface Laptop Studio(상업용 SKUS만 해당)
- Surface Book 3(모든 SUS)
- Surface Laptop 4(상업용 SUS만 해당)
- Surface Laptop 3(모든 SKUS)
- Surface Laptop 이동(모든 SKUS)


>[!TIP]
> 상업용 SKUS(비즈니스용Surface)는 Windows 10 Pro/Enterprise 또는 Windows 11 Pro/Enterprise 실행되고 소비자 SKUS는 Windows 10/Windows 11 Home. 자세한 내용은 시스템 정보 보기 [를 참조하세요](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 

## <a name="overview-and-prerequisites"></a>개요 및 선행 준비

Surface UEFI 구성 도구를 사용하면 개별 UEFI 설정을 대상 Windows 배포할 .msi 설치 관리자 패키지에 저장할 수 있습니다. 

> [!NOTE]
> 이 문서에서는 SEMM 사용 방법을 알고 있는 것으로 가정합니다. 자세한 내용은 [Surface Enterprise 관리 모드(SEMM) 설명서를 참조](surface-enterprise-management-mode.md)하세요.

## <a name="to-enable-wake-on-power"></a>절전 모드 해제를 사용하도록 설정하려면

1.  [Surface UEFI 구성기 최신 버전을 다운로드합니다](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  관리자 권한으로 Surface 디바이스에 로그인하고 **Surface UEFI 구성** 관리자를 열고 **Surface 디바이스**를 선택한 후 다음을 **선택합니다**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Surface 디바이스를 선택하고 다음을 선택합니다.":::
3.  시작**을** 선택한 다음 구성 패키지**에서 만들기****를 선택합니다**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="구성 패키지 만들기를 선택합니다.":::
4.  인증서 **보호를 선택하고** 인증서 .pfx 파일을 추가합니다. 
5. 암호를 입력하고 **다음을 선택하고** 암호 **보호를 적절하게** 추가한 후 다음을 **선택합니다**.
6.  대상 **을 지정하려는 Surface 유형** 선택 페이지에서 대상 장치를 적절하게 선택합니다. 예를 들어 7을 **Surface Pro 선택합니다**.
7.  고급 **기능 페이지에서** 절전 모드 해제 **를 선택하고 기능을** **설정**으로 설정한 후 다음을 **선택합니다**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="절전 모드 해제를 선택하고 으로 설정합니다."::: 
8.  성공 **페이지에서** 끝을 **선택합니다**.

    > [!NOTE]
    > 디바이스에 설정을 처음 제공하는 경우 인증서 지문의 마지막 두 문자도 제공하라는 메시지가 표시됩니다. 
9.  패키지를 .msi 저장합니다. 

## <a name="apply-the-msi-package"></a>MSI 패키지 적용 

네트워크의 디바이스에 MSI 패키지를 적용할 수 있습니다( 예: Microsoft Endpoint Configuration Manager. 이 절차에는 로컬 컴퓨터에 패키지를 설치하는 단계가 포함됩니다. 

1.  승격된 명령 프롬프트에서 .msi 파일의 전체 경로를 입력하여 .msi 실행합니다. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  경고 **대화 상자**에서 확인을 선택 **** 하거나 BitLocker를 사용하지 않도록 설정하십시오.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="확인을 선택하거나 BitLocker를 적절하게 사용하지 않도록 설정하십시오.":::
3.  시작 페이지에서 **다음을 선택하여** 패키지를 실행하고 새로 구성된 UEFI 설정을 적용합니다.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="시작 페이지 중 하나에서 다음을 선택합니다.":::
4.  장치를 다시 시작합니다. 

이제 절전 모드 해제가 구성됩니다. 설정을 테스트하려면 장치를 끄고 전원을 끊은 다음 전원을 다시 연결합니다. 장치가 자동으로 시작됩니다. 

## <a name="references"></a>참조

자세한 내용은 다음 문서를 참조하세요. 

- [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
- [Surface 디바이스용 LAN 절전 모드 해제](wake-on-lan-for-surface-devices.md)

그래도 문제가 해결되지 않을 경우 [Microsoft](https://answers.microsoft.com/) Community.