---
title: SEMM (Surface)에서 화면 디바이스의 등록을 해제 합니다.
description: Surface UEFI reset 패키지 또는 복구 요청 옵션을 사용 하 여 디바이스를 SEMM에서 등록 해제 하는 방법에 대해 알아봅니다.
keywords: surface enterprise 관리
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834607"
---
# SEMM에서 Surface 장치 등록 해제

Surface device가 Surface Enterprise 관리 모드 (SEMM)에 등록 되어 있는 경우 인증서는 해당 디바이스의 펌웨어에 저장 됩니다. 해당 인증서와 SEMM의 등록은 디바이스가 SEMM에 등록 되어 있는 동안 서피스 UEFI 설정 또는 옵션에 대 한 무단 변경을 방지 합니다. Surface UEFI 설정의 제어권을 사용자에 게 복원 하려면 Surface 디바이스를 unenrolled에서 다시 설정 또는 복구로 설명 하는 프로세스를 사용 해야 합니다. 디바이스의 등록을 해제 하는 데 사용할 수 있는 방법에는 서피스 UEFI 재설정 패키지 및 복구 요청과 같은 두 가지 방법이 있습니다.

>[!WARNING]
>디바이스의 등록을 해제 하 고 Surface UEFI 설정의 사용자 정의 컨트롤을 복원 하려면 디바이스를 사용 하는 데 사용한 semm 인증서가 필요 합니다. 이 인증서가 손실 되거나 손상 되 면 SEMM에서 등록을 취소 하지 못할 수 있습니다. 그에 따라 SEMM 인증서를 백업 하 고 보호 하세요.

SEMM에 대 한 자세한 내용은 [Microsoft Surface Enterprise 관리 모드](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)를 참조 하세요.

## Surface UEFI reset 패키지를 사용 하 여 Surface device를 SEMM에서 등록 해제

Surface UEFI reset 패키지는 Surface device를 SEMM에서 등록 해제 하는 데 사용 하는 기본 방법입니다. Surface UEFI 구성 패키지와 마찬가지로, 재설정 패키지는 디바이스에서 SEMM을 구성 하는 Windows Installer (.msi) 파일입니다. 구성 패키지와 달리 reset 패키지는 Surface 디바이스의 Surface UEFI 구성을 기본 설정으로 초기화 하 고, SEMM 인증서를 제거 하 고, 디바이스를 SEMM에서 등록 취소 합니다.

재설정 패키지는 개별 서피스 장치에 맞게 생성 됩니다. 다시 설정 패키지를 만드는 프로세스를 시작 하려면 등록을 해제 하려는 디바이스의 일련 번호와 디바이스를 등록 하는 데 사용 되는 SEMM 인증서가 필요 합니다. 그림 1과 같이 Surface UEFI의 **PC 정보** 페이지에서 surface device의 일련 번호를 찾을 수 있습니다. Surface UEFI가 암호로 보호 되 고 잘못 된 암호가 입력 된 경우에도이 페이지가 표시 됩니다.

![Surface device의 일련 번호가 표시 됩니다.](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*그림 1. Surface device의 일련 번호가 Surface UEFI PC 정보 페이지에 표시 됩니다.*

>[!NOTE]
>Surface UEFI로 부팅 하려면 장치를 끄는 동안 **볼륨을 위아래로** 누르고 동시에 **전원을 켭니다** . Surface 로고가 표시 되 고 장치가 부팅 되기 시작할 때까지 **볼륨을** 길게 누릅니다.

Surface UEFI 다시 설정 패키지를 만들려면 다음 단계를 따릅니다.

1. 시작 메뉴에서 Microsoft Surface UEFI 구성자를 엽니다.
2. **시작**을 클릭합니다.
3. 그림 2에 표시 된 대로 **패키지 다시 설정을**클릭 합니다.

   ![패키지 다시 설정을 선택 하 여 패키지를 등록 해제 Surface device (SEMM)로 만듭니다.](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *그림 2. 패키지 재설정을 클릭 하 여 Surface 디바이스의 등록을 취소 하는 패키지 만들기 (SEMM)*

4. 그림 3과 같이 개인 키 (.pfx)를 사용 하 여 SEMM 인증서 파일을 추가 하려면 **인증서 보호** 를 클릭 합니다. 인증서 파일의 위치로 이동 하 여 파일을 선택한 다음 **확인**을 클릭 합니다.

   ![Surface UEFI 다시 설정 패키지에 SEMM 인증서 추가](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *그림 3. Surface UEFI 다시 설정 패키지에 SEMM 인증서 추가*

5. **다음**을 클릭합니다.
6. (그림 4)에서 등록을 취소 하려는 장치의 일련 번호를 입력 한 다음 **빌드** 를 클릭 하 여 Surface UEFI 다시 설정 패키지를 생성 합니다.

   ![Surface 디바이스의 일련 번호를 사용 하 여 Surface UEFI 다시 설정 패키지 만들기](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *그림 4. Surface device의 일련 번호를 사용 하 여 Surface UEFI 다시 설정 패키지 만들기*

7. 다른 이름 **으로 저장** 대화 상자에서 Surface UEFI 다시 설정 패키지의 이름을 지정 하 고 파일을 저장할 위치로 이동한 다음 **저장**을 클릭 합니다.
8. 패키지 생성이 완료 되 면 **성공** 페이지가 표시 됩니다. **끝내기** 를 클릭 하 여 패키지 만들기를 완료 하 고 MICROSOFT Surface UEFI 구성자를 닫습니다.

Surface 장치에서 Surface UEFI 다시 설정 패키지 Windows Installer (.msi) 파일을 실행 하 여 디바이스를 SEMM에서 등록 해제 합니다. 다시 설정 패키지는 등록 해제 작업을 수행 하기 위해 다시 부팅 해야 합니다. 장치가 unenrolled 된 후에는 **프로그램 및 기능** (그림 5)에서 **Microsoft Surface 구성 패키지** 항목이 더 이상 표시 되지 않도록 하 여 제거를 확인할 수 있습니다.

![장치가 표시 되는 화면은 SEMM로 등록 되어 있습니다.](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*그림 5. 프로그램 및 기능에 Microsoft Surface Configuration Package 항목이 있는 경우 장치가 SEMM에 등록 됨을 나타냅니다.*

## 복구 요청과 함께 Surface device의 등록을 해제 합니다.

일부 시나리오에서 Surface UEFI reset 패키지는 Surface device (예: Windows를 사용할 수 없게 되는 경우)를 등록 하는 데 사용할 수 없는 옵션이 아닐 수도 있습니다. 이러한 시나리오에서는 Surface UEFI 내에서 생성 된 복구 요청을 사용 하 여 디바이스의 등록을 제거할 수 있습니다. Surface UEFI 암호가 없는 장치 에서도 복구 요청 프로세스를 시작할 수 있습니다.

복구 요청 프로세스는 Surface device의 Surface UEFI에서 시작 되 고, 다른 컴퓨터에서 Microsoft Surface UEFI 구성자을 승인 하 고, Surface UEFI에 완료 됩니다. 다시 설정 패키지와 마찬가지로, Microsoft Surface UEFI 구성자를 사용 하 여 복구 요청을 승인 하려면 Surface 디바이스를 등록 하는 데 사용 된 SEMM 인증서에 대 한 액세스 권한이 필요 합니다.

복구 요청을 시작 하려면 다음 단계를 따릅니다.

1. Unenrolled에서 Surface UEFI로 연결할 Surface 디바이스를 부팅 합니다.
2. 서피스 UEFI 비밀 번호를 입력 하 라는 메시지가 표시 되 면 암호를 입력 합니다.
3. 그림 6에 표시 된 대로 **엔터프라이즈 관리** 페이지를 클릭 합니다.

   ![엔터프라이즈 관리 페이지](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *그림 6. 엔터프라이즈 관리 페이지는 SEMM로 등록 된 디바이스의 Surface UEFI에 표시 됩니다.*

4. **시작**을 클릭 하거나 누릅니다.
5. 복구 요청 프로세스를 시작 하려면 **다음** 을 클릭 하거나을 누릅니다.
   >[!NOTE]
   >복구 요청은 만든 후 두 시간에 만료 됩니다. 복구 요청이 지금 완료 되지 않은 경우 복구 요청 프로세스를 다시 시작 해야 합니다.
6. **Semm 키 재설정** 페이지 (그림 7에 표시 됨)에 표시 된 인증서 목록에서 **semm 인증서** 를 선택 하 고 다음을 클릭 하거나 **다음**을 누릅니다.

   ![복구 요청에 대해 SEMM 인증서 선택](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *그림 7. 복구 요청에 대해 SEMM 인증서 선택 (재설정 요청)*

7. (으)로 **설정 된 확인 코드 입력** 페이지에서 **QR 코드** 또는 **텍스트** 단추를 클릭 하 여 복구 요청 (다시 설정 요청)을 그림 8과 같이 표시 하거나, **usb** 단추로 복구 요청 (재설정 요청)을 Usb 드라이브에 파일로 저장할 수 있습니다 (그림 9).

   ![QR 코드로 표시 된 복구 요청](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *그림 8. QR 코드로 표시 되는 복구 요청 (재설정 요청)*

   ![USB 드라이브에 복구 요청 저장](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *그림 9. 복구 요청 (재설정 요청)을 USB 드라이브에 저장*

   * QR 코드 복구 요청 (재설정 요청)을 사용 하려면 모바일 장치에서 QR 읽기 프로그램을 사용 하 여 코드를 읽습니다. QR 리더 앱은 QR 코드를 영숫자 문자열로 번역 합니다. 그런 다음 Microsoft Surface UEFI Configurator를 사용 하 여 재설정 확인 코드를 생성 하는 관리자에 게 해당 문자열을 전자 메일로 보내거나 메시지를 보낼 수 있습니다.
   * USB 드라이브에 파일로 저장 된 복구 요청 (재설정 요청)을 사용 하려면 USB 드라이브를 사용 하 여 Microsoft Surface UEFI Configurator를 사용 하 여 초기화 확인 코드를 생성 하는 컴퓨터로 파일을 전송 합니다. 또한 다른 장치의 USB 드라이브에서 파일을 복사 하 여 네트워크를 통해 전자 메일로 보내거나 전송할 수 있습니다.
   * 복구 요청 (다시 설정 요청)을 텍스트로 사용 하려면 Microsoft Surface UEFI 구성자에 직접 텍스트를 입력 하면 됩니다.

8. 다른 컴퓨터의 시작 메뉴에서 Microsoft Surface UEFI 구성자를 엽니다.
    >[!NOTE]
    >Microsoft Surface UEFI 구성자은 SEMM 인증서의 인증서 체인을 인증할 수 있는 환경에서 실행 되어야 합니다.
9. **시작**을 클릭합니다.
10. 그림 10에 나와 있는 것 처럼 **복구 요청**을 클릭 합니다.

    ![프로세스를 시작 하 여 복구 요청 승인](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *그림 10. 복구 요청을 클릭 하 여 복구 요청 승인 프로세스 시작*

11. **인증서 보호** 를 클릭 하 여 semm 인증서로 복구 요청을 인증 합니다.
12. SEMM 인증서 파일을 찾아 선택한 다음 **확인**을 클릭 합니다.
13. 그림 11과 같이 인증서 암호를 입력 하 라는 메시지가 나타나면 인증서 파일에 대 한 암호를 입력 하 고 확인 한 다음 **확인**을 클릭 합니다.

    ![SEMM 인증서 비밀 번호 입력](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *그림 11. SEMM 인증서의 비밀 번호를 입력 합니다.*

14. **다음**을 클릭합니다.
15. 복구 요청 (다시 설정 요청)을 입력 한 다음 **생성** 을 클릭 하 여 재설정 된 확인 코드를 만듭니다 (그림 12).

    ![복구 요청 입력](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *그림 12. 복구 요청 (다시 설정 요청) 입력*

    * 복구 요청 (재설정 요청)을 재설정 되는 Surface 디바이스의 텍스트로 표시 한 경우 키보드를 사용 하 여 제공 된 필드에 복구 요청 (재설정 요청)을 입력 합니다.
    * 복구 요청 (재설정 요청)을 QR 코드로 표시 한 후 메시지 또는 전자 메일 응용 프로그램을 사용 하 여 Microsoft Surface UEFI Configurator를 사용 하 여 컴퓨터에 코드를 보내는 경우 제공 된 필드에 해당 코드를 복사 하 여 붙여넣습니다.
    * 복구 요청 (재설정 요청)을 USB 드라이브에 파일로 저장 한 경우, **가져오기** 단추를 클릭 하 고 복구 요청 (재설정 요청) 파일을 찾아 선택한 다음 **확인**을 클릭 합니다.

16. 다시 설정 확인 코드는 그림 13과 같이 Microsoft Surface UEFI 구성자에 표시 됩니다.

    ![다시 설정 확인 코드 표시](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *그림 13. Microsoft Surface UEFI 구성자에 표시 되는 다시 설정 확인 코드*

    * **공유** 단추를 클릭 하 여 다시 설정 확인 코드를 전자 메일로 보냅니다.

17. Surface 디바이스의 제공 된 필드에 다시 설정 된 확인 코드 (그림 8)를 입력 한 다음 **확인** 을 클릭 하거나 눌러 장치를 초기화 하 고 디바이스를 semm에서 등록 취소 합니다.
18. 그림 14와 같이 semm **reset 성공** 페이지에서 **지금 다시 시작** 을 클릭 하거나 눌러 unenrollment를 완료 합니다.

    ![SEMM에서 성공한 unenrollment 표시 하는 예제](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *그림 14. Unenrollment에서 성공한 시작*

19. Microsoft Surface UEFI 구성자에서 **End** 를 클릭 하 여 복구 요청 (초기화 요청) 프로세스를 완료 하 고 MICROSOFT Surface UEFI 구성자를 닫습니다.


