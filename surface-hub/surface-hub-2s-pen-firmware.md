---
title: Surface Hub 2S에서 펜 펌웨어 업데이트
description: 이 페이지에서는 Surface Hub 2 펜의 펌웨어를 업데이트하는 방법에 대해 설명하고 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: fb0948623ec9c12aa818e4829285ea77229bf71d
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911583"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>Surface Hub 2S에서 펜 펌웨어 업데이트

비즈니스용 업데이트 또는 Surface Hub PC에 다운로드하여 Windows 2 펜의 펌웨어를 업데이트할 수 있습니다. 업데이트된 펌웨어는 2020년 2월 26일부터 Windows 업데이트에서 사용할 수 있습니다. 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>비즈니스용 업데이트로 Windows 펜 펌웨어 업데이트

이 섹션에서는 기본적으로 야간 3시에 발생하도록 구성된 Windows 업데이트에 대한 자동화된 유지 관리 주기를 통해 펜 펌웨어를 업데이트하는 방법을 설명합니다. 업데이트는 2 펜에 적용하기 전에 두 가지 유지 관리 주기를 Surface Hub 합니다. 또는 다른 업데이트와 마찬가지로 WUfB(비즈니스용 Windows)를 사용하여 펜 펌웨어를 적용할 수 있습니다. 자세한 내용은 [Managing Windows updates on Surface Hub.](manage-windows-updates-for-surface-hub.md)

1. Surface Hub 2 펜이 Surface Hub: 흰색 표시등이 깜박이기 시작할 때까지 **** 위쪽 단추를 누르고 있습니다.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 펜](images/sh2-pen-1.png)

2. 모든 Surface Hub 관리자로 로그인하고, 설정 를 **연**다음 새 Bluetooth 검색합니다.

3. 페어링 프로세스를 완료하려면 펜을 선택합니다.

4. 펜의 **위쪽** 단추를 눌러 업데이트를 적용합니다. 완료하는 데 최대 2시간이 걸릴 수 있습니다.

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>개별 PC로 다운로드하여 펜 펌웨어 업데이트

2 펜의 펌웨어를 Surface Hub 실행 중인 별도의 PC에서 업데이트할 Windows 10. 또한 이 방법을 사용하면 펜 펌웨어가 최신 버전으로 성공적으로 업데이트되어 있는지 확인할 수 있습니다.

1. Surface Hub 2 펜을 Bluetooth 가능 PC에 페어링: 흰색 **** 표시기 LED 표시등이 깜박이기 시작할 때까지 위쪽 단추를 누르고 있습니다.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 펜](images/sh2-pen-1.png)

2. PC에서 새 디바이스를 Bluetooth 검색합니다.

3. 페어링 프로세스를 완료하려면 펜을 선택합니다.

4. 새 업데이트를 Surface Hub 전에 다른 모든 Surface Hub 펜의 연결을 끊습니다.

5. PC에 [Surface Hub 2 펜 펌웨어 업데이트 도구를](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) 다운로드합니다.

6. 실행 **PenCfu.exe.** 설치 진행률이 도구에 표시됩니다. 업데이트를 완료하는 데 몇 분 정도 걸릴 수 있습니다. 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>2 펜의 펌웨어 Surface Hub 확인

1. 펜 **get_version.bat** 단추를 실행하고 맨 위 단추를 누릅니다. ****

2. 이 도구는 펜의 펌웨어 버전을 보고합니다. 

   예제:
    - 이전 펌웨어는 468.2727.368입니다.
    - 새 펌웨어는 468.3347.368입니다.

## <a name="command-line-options"></a>명령줄 옵션

명령줄에서 Surface Hub 2 펜 펌웨어 업데이트 도구(PenCfu.exe)를 실행할 수 있습니다.

1. 펜을 PC에 페어링하고 펜의 위쪽 **단추를** 클릭합니다.

2. 펌웨어 **PenCfu.exe** 시작하려면 다음을 두 번 클릭합니다. 구성 파일 및 펌웨어 이미지 파일은 도구와 동일한 폴더에 저장해야 합니다.

3. 추가 옵션을PenCfu.exe ** -h를 실행하여** 다음 표에 나열된 사용 가능한 매개 변수를 표시합니다.  

   예제: `PenCfu.exe -h`

4. **Ctrl+C를** 입력하여 도구를 안전하게 종료합니다.


| 명령 | 설명 |
| -------------- |---------------------------- |
| -h 도움말        | 도구 명령줄 인터페이스 도움말을 표시하고 종료합니다. |
| -v 버전     | 도구 버전을 표시하고 종료합니다. |
| -l 로그 필터  | 로그 파일의 필터 수준을 설정하십시오. 로그 메시지의 가능한 수준은 DEBUG(가장 낮음), INFO, WARNING 및 ERROR(가장 높음)입니다. 로그 필터 수준을 설정하면 로그 메시지가 같은 수준 이상인 메시지로만 필터링됩니다. 예를 들어 필터 수준이 WARNING으로 설정된 경우 WARNING 및 ERROR 메시지만 기록됩니다. 기본적으로 이 옵션은 끄기로 설정되어 로깅을 사용하지 않도록 설정됩니다. |
| -g get-version | 지정된 경우 도구는 도구와 동일한 폴더에 저장된 구성 파일과 일치하는 연결된 펜의 FW 버전만 얻게 됩니다.  |

