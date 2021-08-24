---
title: SEMM을 사용하여 Surface Hub 2S 보안 및 관리
description: SEMM을 통해 2S Surface Hub 보안에 대해 자세히 알아보아야 합니다.
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
ms.openlocfilehash: b22bfc39c07facb84ca57438ec16038492f85d15
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911043"
---
# <a name="secure-and-manage-surface-hub-2s-with-semm-and-uefi"></a>SEMM 및 UEFI를 사용하여 Surface Hub 2S 보호 및 관리

Surface Hub 2S의 새로운 기능을 사용하면 SEMM을 사용하여 장치의 UEFI 설정을 관리할 수 있습니다.
Microsoft Surface UEFI 구성 요소를 사용하여 다음 구성 요소를 제어합니다.

- 유선 LAN
- 카메라
- Bluetooth
- Wi-Fi
- 점유 센서

Microsoft Surface UEFI 구성기에서 다음 UEFI 설정을 켜거나 끄십시오.

- Boot

    - PXE 부팅용 IPv6
    - 대체 부팅
    - 부팅 순서 잠금
    - USB 부팅
- UEFI 프런트 페이지

    - 장치
    - Boot
    - 날짜/시간

## <a name="create-uefi-configuration-image"></a>UEFI 구성 이미지 만들기

다른 Surface 디바이스와 달리 MSI 파일 또는 Win PE 이미지를 사용하여 2S에서 이러한 설정을 Surface Hub 없습니다. 대신 디바이스에 로드할 USB 이미지를 만들어야 합니다. Surface Hub 2S UEFI 구성 이미지를 만들하려면 Microsoft 다운로드 센터의 Surface [Tools for IT(IT용 Surface](https://www.microsoft.com/download/details.aspx?id=46703) 도구) 페이지에서 최신 버전의 Microsoft Surface UEFI 구성 도구를 다운로드하여 설치합니다. UEFI 및 SEMM 사용에 대한 자세한 내용은 Microsoft Surface Enterprise [관리 모드를 참조하세요.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)

## <a name="to-configure-uefi-on-surface-hub-2s"></a>2S에서 UEFI를 Surface Hub

1. UEFI 구성을 시작하고 첫 번째 화면에서 구성 패키지 **를 선택하십시오.**<br><br>
![* UEFI 구성을 시작하고 구성 패키지*를 선택하십시오.](images/sh2-uefi1.png) <br> <br>
2. 패키지에 인증서를 추가하려면 패키지에 서명하고 보호하려면 .pfx 파일 형식의 개인 키가 있는 유효한 인증서가 있어야 합니다. **+ 인증서 보호를 선택합니다.** <br>
![* + 인증서 보호 *를 선택합니다.](images/sh2-uefi2.png) <br><br>
3. 인증서의 개인 키 암호를 입력합니다.<br>
![* 인증서의 개인 키 암호 *를 입력합니다.](images/sh2-uefi3.png) <br><br>
4. 개인 키를 가져온 후 패키지 만들기를 계속합니다.<br>
![* 패키지 만들기 계속 *.](images/sh2-uefi4.png) <br><br>
5. **허브를** Surface Hub UEFI 구성 패키지의 대상으로 **2S를** 지정합니다.<br>
![* 허브를 선택하고 Surface Hub 2S를 UEFI 구성 패키지의 대상으로 지정 *.](images/sh2-uefi5.png) <br><br>
6. 2S에서 활성화하거나 비활성화할 구성 요소 및 Surface Hub 선택합니다.<br>
![* 활성화하거나 비활성화할 구성 요소 및 설정을 선택합니다.](images/sh2-uefi6.png) <br><br>
7. USB 옵션을 사용하여 파일을 내보낼 수 있습니다.<br>
![* USB 옵션을 사용하여 *파일을 내보낼 수 있습니다.](images/sh2-uefi8.png) <br><br>
8. 이 패키지에 사용할 USB 드라이브를 삽입하고 선택하십시오. USB 드라이브의 서식이 지정되어 있으며 이 드라이브에 있는 정보가 손실됩니다.<br>
![* 패키지의 USB 드라이브를 삽입하고 선택 *.](images/sh2-uefi9.png) <br><br>
9. 패키지를 성공적으로 만들면 Configurator에 인증서 지문의 마지막 두 문자가 표시됩니다. 2S를 설치하기 위해 구성으로 가져올 때 이러한 Surface Hub 필요합니다.<br>
![* 패키지의 성공적인 구성 *.](images/sh2-uefi10.png) <br>

## <a name="to-boot-into-uefi"></a>UEFI로 부팅

2S Surface Hub 해제합니다. 볼륨 업 **단추를 누르고** **전원 단추를** 누릅니다. UEFI 메뉴가 나타날 때까지 볼륨 업 단추를 계속 누릅니다.
