---
title: 2S를 사용 하 여 Surface Hub를 보호 하 고 관리 합니다.
description: Surface Hub 보안 유지에 대 한 자세한 내용은 SEMM을 2S.
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835271"
---
# SEMM 및 UEFI를 사용하여 Surface Hub 2S 보호 및 관리

Surface Hub 2S의 새로운 경우 SEMM을 사용 하 여 장치의 UEFI 설정을 관리할 수 있습니다.
Microsoft Surface UEFI 구성자를 사용 하 여 다음 구성 요소를 제어 합니다.

- 유선 LAN
- 카메라
- Bluetooth
- Wi-Fi
- 점유 센서

Microsoft Surface UEFI 구성자를 사용 하 여 다음 UEFI 설정을 설정 하거나 해제 합니다.

- Boot

    - PXE 부팅용 IPv6
    - 대체 부팅
    - 부팅 순서 잠금
    - USB 부팅
- UEFI 프론트 페이지

    - 장치
    - Boot
    - 날짜/시간

## UEFI 구성 이미지 만들기

다른 Surface 디바이스와 달리, MSI 파일 또는 Win PE 이미지를 사용 하 여 Surface Hub 2S에 이러한 설정을 적용할 수 없습니다. 대신 장치에 로드 하는 데 사용할 USB 이미지를 만들어야 합니다. Surface Hub 2S UEFI 구성 이미지를 만들려면 Microsoft 다운로드 센터의 [Surface Tools (IT](https://www.microsoft.com/download/details.aspx?id=46703) ) 페이지에서 MICROSOFT Surface UEFI 구성자의 최신 버전을 다운로드 하 여 설치 합니다. UEFI 및 SEMM을 사용 하는 방법에 대 한 자세한 내용은 [Microsoft Surface Enterprise 관리 모드](https://docs.microsoft.com/surface/surface-enterprise-management-mode)를 참조 하세요.

## Surface Hub 2S에서 UEFI를 구성 하려면

1. UEFI 구성자를 시작 하 고 첫 번째 화면에서 **구성 패키지**를 선택 합니다.<br><br>
![* UEFI 구성자를 시작 하 고 구성 패키지 *를 선택 합니다.](images/sh2-uefi1.png) <br> <br>
2. 패키지에 인증서를 추가 하려면 패키지에 서명 하 고 보호할 수 있는 개인 키를 포함 하는 유효한 인증서가 .pfx 파일 형식으로 되어 있어야 합니다. **+ 인증서 보호를 선택 합니다.** <br>
![* 선택 + 인증서 보호 *](images/sh2-uefi2.png) <br><br>
3. 인증서의 개인 키 암호를 입력 합니다.<br>
![* 인증서의 개인 키 암호 입력 *](images/sh2-uefi3.png) <br><br>
4. 개인 키를 가져온 후 패키지 만들기를 계속 합니다.<br>
![* 패키지 계속 만들기 *](images/sh2-uefi4.png) <br><br>
5. **허브** 및 **Surface HUB 2S** 을 UEFI 구성 패키지의 대상으로 선택 합니다.<br>
![* 허브 및 Surface Hub 2S을 UEFI 구성 패키지의 대상으로 선택 합니다.](images/sh2-uefi5.png) <br><br>
6. Surface Hub 2S에서 활성화 또는 비활성화 하려는 구성 요소 및 설정을 선택 합니다.<br>
![* 활성화 또는 비활성화 하려는 구성 요소 및 설정 선택 *](images/sh2-uefi6.png) <br><br>
7. USB 옵션을 사용 하 여 파일을 내보냅니다.<br>
![* USB 옵션을 사용 하 여 파일 내보내기 *](images/sh2-uefi8.png) <br><br>
8. 이 패키지에 사용할 USB 드라이브를 삽입 하 고 선택 합니다. USB 드라이브에 서식이 지정 되 고, 사용 중인 정보가 손실 됩니다.<br>
![* 추가 하 고 패키지용 USB 드라이브를 선택 하십시오 *](images/sh2-uefi9.png) <br><br>
9. 패키지가 성공적으로 생성 되 면 구성자에는 인증서 손도장의 마지막 두 문자가 표시 됩니다. Surface Hub 2S 구성으로 가져올 때 이러한 문자가 필요 합니다.<br>
![* 패키지의 성공한 구성](images/sh2-uefi10.png) <br>

## UEFI로 부팅 하려면

Surface Hub 2S을 끄십시오. **볼륨 크게** 단추를 길게 누른 상태에서 **전원** 단추를 누릅니다. UEFI 메뉴가 나타날 때까지 볼륨을 위로 유지 단추를 누르고 있습니다.
