---
title: Surface Hub 2S 초기화 및 복구
description: Surface Hub 2S를 복구 및 초기화하는 방법을 알아보십시오.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304811"
---
# Surface Hub 2S 초기화 및 복구

Surface Hub 2S에 문제가 발생하면 장치를 공장 설정으로 초기화하거나 USB 드라이브를 사용하여 복원할 수 있습니다.

시작하려면 관리자 자격 증명으로 Surface Hub 2S에 **** 로그인하고 **** 설정 앱을 열고 보안 업데이트 & 선택한 다음 **복구를 선택합니다.**

## 장치 초기화

   > [!IMPORTANT]
   > 디바이스를 초기화하기 전에 BitLocker 키를 사용할 수 있도록 합니다. 나중에 요청이 표시되기 전에 이 키를 사용할 수 있도록 합니다. 자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md)

1. 디바이스를 초기화하려면 **시작을 선택합니다.**

2. 이 장치 **초기화 준비 완료 창이** 나타나면 재설정을 **선택합니다.** 
  
   > [!IMPORTANT]
   > 허브가 복구 파티션에 다시 시작하면 BitLocker 키를 입력하라는 메시지가 표시됩니다. 이 프롬프트를 건너뛰면 재설정이 실패합니다. BitLocker 키를 입력하면 허브가 복구 파티션에서 운영 체제를 다시 설치합니다. 완료하는 데 최대 1시간이 걸릴 수 있습니다.
  
3. 장치를 다시 구성하려면 첫 번째 설치 프로그램을 실행합니다.

4. Microsoft Intune 또는 다른 모바일 장치 관리 솔루션을 사용하여 장치를 관리하는 경우 이전 레코드를 사용 중지하고 삭제한 다음 새 장치를 다시 등록합니다. 자세한 내용은 장치 지우기, 사용 중지 또는 수동으로 장치 초기화를 사용하여 장치 [제거를 참조하세요.](https://docs.microsoft.com/intune/devices-wipe)

   > [!div class="mx-imgBorder"]
   > ![*Surface Hub 2S의 초기화 및 복구*](images/sh2-reset.png)
   <br/>*그림 1. Surface Hub 2S 초기화 및 복구* 

## USB 복구 드라이브를 사용하여 Surface Hub 2S 복구

Surface Hub 2S의 새로운 기능을 통해 복구 이미지를 사용하여 디바이스를 다시 설치할 수 있습니다.

### USB 드라이브에서 복구

Surface Hub 2S를 사용하여 복구 이미지를 사용하여 디바이스를 다시 설치할 수 있습니다. 이렇게 하면 BitLocker 키를 분실하거나 설정 앱에 대한 관리자 자격 증명이 더 이상 없는 경우 장치를 공장 설정에 다시 설치합니다.

>[!NOTE]
>FAT32로 포맷된 8GB 또는 16GB의 저장소가 있는 USB 3.0 드라이브를 사용 합니다.

1. 별도의 PC에서 [Surface 복구](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 웹 사이트에서 .zip 파일 복구 이미지를 다운로드한 다음 다음 지침으로 돌아오세요. 

1. 다운로드한 파일의 파일을 USB 드라이브의 루트에 언스파이프합니다.  

1. Usb 드라이브를 Surface Hub 2S의 USB-C 또는 USB-A 포트에 연결합니다.

1. 디바이스를 끄는 경우:

   1. 볼륨 아래로 단추를 누를 때 전원 단추를 누릅니다.
   1. Windows 로고가 표시될 때까지 두 단추를 계속 누릅니다.
   1. 전원 단추를 해제하지만 설치 UI가 시작될 때까지 볼륨 아래로 단추를 계속 누릅니다.

      ![*볼륨 감소 및 전원 단추를 사용하여 복구 시작*](images/sh2-keypad.png)
      <br>*그림 2. 볼륨 및 전원 단추*

1. 언어 선택 화면에서 Surface Hub 2S의 표시 언어를 선택합니다.

1. Select **Recover from a drive** and Fully clean the **drive,** and then select **Recover**. BitLocker 키를 입력하라는 메시지가 표시될 경우 이 드라이브 **건너뛰기를 선택합니다.** Surface Hub 2S는 여러 번 다시 시작하며 복구 프로세스를 완료하는 데 약 30분 정도 걸립니다.

처음 설치 화면이 나타나면 USB 드라이브를 제거합니다.

## 고객 지원

질문이나 도움이 필요한 경우 지원 요청을 [만들 수 있습니다.](https://support.microsoft.com/supportforbusiness/productselection)
