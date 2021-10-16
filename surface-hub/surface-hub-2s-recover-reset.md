---
title: 2S용 Surface Hub 복구
description: 2S를 복구하고 다시 설정하는 Surface Hub 대해 자세히 알아보아야 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: cf87ec877548cd1ae527e8f64eb90d094c19c858
ms.sourcegitcommit: 74ab91db82ae611854c070ddb14daa28acf7051f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2021
ms.locfileid: "12096476"
---
# <a name="reset-and-recovery-for-surface-hub-2s"></a>2S용 Surface Hub 복구

2S에서 Surface Hub 발생하는 경우 장치를 공장 설정으로 초기화하거나 USB 드라이브를 사용하여 복원할 수 있습니다.

시작하려면 관리자 자격 증명으로 Surface Hub 2S에 로그인하고 **** 설정 앱을 열고 업데이트 & 보안 을 선택한 다음 복구 **를** **선택합니다.**

## <a name="reset-the-device"></a>장치 초기화

   > [!IMPORTANT]
   > 디바이스를 초기화하기 전에 BitLocker 키를 사용할 수 있도록 하세요. 나중에 다시하라는 메시지가 표시됩니다. 자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md)

1. 장치를 초기화하려면 를 **시작.**

2. 이 장치 **초기화 준비 완료 창이** 나타나면 초기화 를 **선택합니다.**
  
   > [!TIP]
   > 허브가 복구 파티션으로 다시 시작하면 BitLocker 키를 입력하라는 메시지가 표시됩니다. 이 프롬프트를 건너뛰면 재설정이 실패합니다. BitLocker 키를 입력하면 Hub는 복구 파티션에서 운영 체제를 다시 설치합니다. 완료하는 데 최대 1시간이 걸릴 수 있습니다.
  
3. 장치를 다시 구성하려면 첫 번째 설치 프로그램을 실행합니다.

4. 장치 또는 다른 모바일 Microsoft Intune 관리 솔루션을 사용하여 장치를 관리하는 경우 이전 레코드를 사용 중지하고 삭제한 다음 새 장치를 다시 등록합니다. 자세한 내용은 장치 초기화, 사용 중지 또는 수동으로 장치 초기화 를 사용하여 장치 [제거를 참조하세요.](/intune/devices-wipe)

   > [!div class="mx-imgBorder"]
   > ![*2S에서 다시 Surface Hub 복구합니다.](images/sh2-reset.png)
   <br/>*그림 1. 2S용 Surface Hub 복구*

## <a name="recover-surface-hub-2s-by-using-a-usb-recovery-drive"></a>USB Surface Hub 드라이브를 사용하여 2S 복구

Surface Hub 2S의 새로운 기능을 사용하면 복구 이미지를 사용하여 디바이스를 다시 설치할 수 있습니다.

### <a name="recovery-from-a-usb-drive"></a>USB 드라이브에서 복구

Surface Hub 2S를 사용하여 복구 이미지를 사용하여 장치를 다시 설치할 수 있습니다. 이렇게 하면 BitLocker 키를 잃어버린 경우 또는 앱에 대한 관리자 자격 증명이 더 이상 없는 경우 장치를 공장 설정에 다시 설정 있습니다.

>[!TIP]
>FAT32로 포맷된 8GB 또는 16GB의 저장소가 있는 USB 3.0 드라이브를 사용 합니다.

1. 별도의 PC에서 [Surface](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 복구 .zip 파일 복구 이미지를 다운로드한 다음 다음 지침으로 돌아오세요.

2. 작업 표시줄의 검색 상자에 **** 복구 드라이브를 입력한 다음 결과에서 **복구** 드라이브 또는 복구 드라이브 **만들기를** 선택합니다. 관리자 암호를 입력하거나 선택을 확인해야 할 수 있습니다.

3. 사용자 **계정 컨트롤 상자에서** 예를 **선택합니다.**

4. 시스템 파일을 복구 **** 드라이브에 백업 확인란의 선택을 취소하고 다음 을 **선택합니다.**

5. USB 드라이브를 선택하고 다음 **드라이브를 > 선택합니다.**  일부 유틸리티는 복구 드라이브에 복사해야 하여 몇 분 정도 걸릴 수 있습니다.

6. 복구 드라이브가 준비되면 마친 을 **선택합니다.**

7. 이전에 다운로드한 .zip 복구 이미지를 두 번 클릭하여 열 수 있습니다.

8. 복구 이미지 폴더에서 모든 파일을 선택하고 USB 드라이브의 루트에 복사한 다음 Choose **to replace the files in the destination 을 선택합니다.**

9. 파일 복사가 완료되면 작업 표시줄에서 안전하게 하드웨어 제거 및 미디어 제거 아이콘을 선택하고 USB 드라이브를 제거합니다. ****

10. 커넥트 USB 드라이브를 2S의 USB-C 또는 USB-A Surface Hub 연결합니다. 허브를 끄고 USB 드라이브에서 부팅합니다.

#### <a name="boot-surface-hub-from-usb-drive"></a>USB Surface Hub 부팅

>[!NOTE]
>장치가 언플러그되거나 전원이 꺼지거나 전원 코드가 풀린 경우 USB에서 부팅을 시도하기 전에 15초 이상 기다립니다.

1. 볼륨 감소 단추를 누를 때 전원 단추를 누릅니다.

2. 로고가 표시될 때까지 두 단추를 Windows 합니다.

3. 전원 단추를 해제하지만 설치 UI가 시작될 때까지 볼륨 감소 단추를 계속 누릅니다.

   ![*볼륨 감소 및 전원 단추를 사용하여 복구를 시작*.](images/sh2-keypad.png)
   <br>*그림 2. 볼륨 및 전원 단추*

4. 언어 선택 화면에서 2S에 대한 Surface Hub 선택합니다.

5. 드라이브에서 **복구를** 선택하고 드라이브를 완전히 **정리**를 선택한 다음 복구 를 **선택합니다.** BitLocker 키를 입력하라는 메시지가 표시될 경우 이 드라이브 **건너뛰기 를 선택합니다.** Surface Hub 2S는 여러 번 다시 시작하며 복구 프로세스를 완료하는 데 1시간 이상 걸릴 수 있습니다.

6. 처음 설치 화면이 나타나면 USB 드라이브를 제거합니다.

## <a name="contact-support"></a>고객 지원

질문이 있는 경우 또는 도움이 필요한 경우 지원 [요청을 만들 수 있습니다.](https://support.microsoft.com/supportforbusiness/productselection)
