---
title: SEMM(Surface)에서 Surface 디바이스의 사용 안 하게 합니다.
description: Surface UEFI 재설정 패키지 또는 복구 요청 옵션을 사용하여 SEMM에서 디바이스를 초기화하는 방법을 알아보십시오.
keywords: surface 엔터프라이즈 관리
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 4942dd5ab187b7350e5093d8d189ad52536ef5bd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448561"
---
# <a name="unenroll-surface-devices-from-semm"></a>SEMM에서 Surface 디바이스 등록 취소

Surface 디바이스가 SEMM(Surface Enterprise 관리 모드)에 등록하면 인증서가 디바이스의 펌웨어에 저장됩니다. 인증서가 존재하고 SEMM에 등록하면 장치가 SEMM에 등록되는 동안 Surface UEFI 설정 또는 옵션이 무단으로 변경되는 것을 방지할 수 있습니다. Surface UEFI 설정에 대한 제어를 사용자에게 복원하려면 Surface 디바이스를 SEMM에서 초기화 또는 복구로 설명하는 프로세스에서 회수해야 합니다. SEMM에서 디바이스를 초기화하는 데 사용할 수 있는 방법은 Surface UEFI 재설정 패키지와 복구 요청의 두 가지입니다.

>[!WARNING]
>SEMM에서 디바이스 등록을 끄고 Surface UEFI 설정의 사용자 제어를 복원하려면 SEMM에 장치를 등록하는 데 사용된 SEMM 인증서가 있어야 합니다. 이 인증서가 손실되거나 손상되면 SEMM에서 등록을 해지할 수 없습니다. 그에 따라 SEMM 인증서를 백업하고 보호합니다.

SEMM에 대한 자세한 내용은 [Microsoft Surface Enterprise 모드를 참조하세요](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

## <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>Surface UEFI 재설정 패키지를 사용하여 SEMM에서 Surface 디바이스의 로그인을 끄기

Surface UEFI 재설정 패키지는 SEMM에서 Surface 디바이스를 초기화하는 데 사용하는 기본 방법입니다. Surface UEFI 구성 패키지와 마찬가지로 초기화 패키지는 Windows SEMM을 구성하는 .msi(설치 관리자) 파일입니다. 구성 패키지와 달리 초기화 패키지는 Surface 디바이스의 Surface UEFI 구성을 기본 설정으로 다시 설정하고, SEMM 인증서를 제거하고, SEMM에서 디바이스 등록을 제거합니다.

초기화 패키지는 개별 Surface 디바이스용으로 특별히 만들어집니다. 초기화 패키지를 만드는 프로세스를 시작하려면 등록을 해지할 장치의 일련 번호와 장치를 등록하는 데 사용되는 SEMM 인증서가 필요합니다. 그림 1과 같이 Surface UEFI의 **PC** 정보 페이지에서 Surface 디바이스의 일련 번호를 찾을 수 있습니다. 이 페이지는 Surface UEFI가 암호로 보호되어 있으며 잘못된 암호를 입력한 경우에도 표시됩니다.

![Surface 디바이스의 일련 번호가 표시됩니다.](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*그림 1. Surface 디바이스의 일련 번호가 Surface UEFI PC 정보 페이지에 표시됩니다.*

>[!NOTE]
>Surface UEFI로 부팅하려면 장치가 꺼진 동안 **볼륨** 업 및 **전원** 을 동시에 누르십시오. Hold **Volume Up** until the Surface logo is displayed and the device begins to boot.

Surface UEFI 재설정 패키지를 만들 수 있는 경우 다음 단계를 따르세요.

1. 다음 창에서 Microsoft Surface UEFI 구성 시작 메뉴.
2. **시작**을 클릭합니다.
3. 그림 2 **와 같이** 패키지 다시 설정을 클릭합니다.

   ![패키지 초기화 를 선택하여 SEMM에서 Surface 디바이스를 초기화하는 패키지를 만들 수 있습니다.](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *그림 2. 패키지 재설정을 클릭하여 SEMM에서 Surface 디바이스를 초기화하는 패키지를 만들 수 있습니다.*

4. 그림 3 **과** 같이 인증서 보호를 클릭하여 개인 키(.pfx)가 있는 SEMM 인증서 파일을 추가합니다. 인증서 파일의 위치로 이동하여 파일을 선택한 다음 확인을 **클릭합니다**.

   ![Surface UEFI 재설정 패키지에 SEMM 인증서를 추가합니다.](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *그림 3. Surface UEFI 재설정 패키지에 SEMM 인증서 추가*

5. **다음**을 클릭합니다.
6. SEMM에서 초기화할 장치의 일련 번호를 입력한 다음(그림 4에 표시된) 빌드를 클릭하여 Surface UEFI 재설정 패키지를 **** 생성합니다.

   ![일련 번호의 Surface 디바이스를 사용하여 Surface UEFI 재설정 패키지를 만드십시오.](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *그림 4. Surface 디바이스의 일련 번호를 사용하여 Surface UEFI 재설정 패키지 만들기*

7. 다른 이름으로 **** 저장 대화 상자에서 Surface UEFI 재설정 패키지의 이름을 지정하고 파일을 저장할 위치로 이동한 다음 저장을 **클릭합니다**.
8. 패키지 생성이 완료되면 성공 **페이지** 가 표시됩니다. 종료 **를** 클릭하여 패키지 만들기를 완료하고 Microsoft Surface UEFI 구성을 닫습니다.

Surface 디바이스에서 Surface Windows 설치 관리자(.msi) 파일로 Surface UEFI 재설정 패키지를 실행하여 SEMM에서 디바이스를 초기화합니다. 초기화 패키지를 다시 설치하려면 다시 부과하여 계정이 없는 작업을 수행해야 합니다. 디바이스의 인증을 제거한 후 프로그램 및 기능(그림 5에 표시)의 **Microsoft Surface** 구성 패키지 항목이 더 이상 존재하지 않는지 **** 확인하여 성공적인 제거를 확인할 수 있습니다.

![장치가 SEMM에 등록된 것으로 표시하는 화면입니다.](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*그림 5. 프로그램 및 기능에 Microsoft Surface 구성 패키지 항목이 있는 경우 장치가 SEMM에 등록되어 있는 것입니다.*

## <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>복구 요청을 사용하여 SEMM에서 Surface 디바이스의 설치를 끄기

일부 시나리오에서는 Surface UEFI 재설정 패키지가 SEMM에서 Surface 디바이스를 초기화하는 데 사용할 수 없는 옵션일 수 있습니다(예: Windows 수 없는 경우). 이러한 시나리오에서는 Surface UEFI 내에서 생성된 복구 요청을 사용하여 디바이스를 회수할 수 있습니다. Surface UEFI 암호가 없는 장치에서도 복구 요청 프로세스를 시작할 수 있습니다.

복구 요청 프로세스는 Surface 디바이스의 Surface UEFI에서 시작하여 다른 컴퓨터에서 Microsoft Surface UEFI 구성기 승인을 받은 다음 Surface UEFI에서 완료됩니다. 초기화 패키지와 마찬가지로 Microsoft Surface UEFI 구성기에서 복구 요청을 허용하려면 Surface 디바이스를 등록하는 데 사용된 SEMM 인증서에 액세스해야 합니다.

복구 요청을 시작하기 위해 다음 단계를 수행합니다.

1. SEMM에서 Surface UEFI로의 인가를 끄는 Surface 디바이스를 부팅합니다.
2. 묻는 메시지가 표시될 경우 Surface UEFI 암호를 입력합니다.
3. 그림 6**에 Enterprise** 관리 페이지를 클릭합니다.

   ![Enterprise 페이지입니다.](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *그림 6. Enterprise 관리 페이지가 SEMM에 등록된 장치의 Surface UEFI에 표시됩니다.*

4. 를 클릭하거나 **시작**.
5. 다음을 **클릭하거나 눌러** 복구 요청 프로세스를 시작할 수 있습니다.
   >[!NOTE]
   >복구 요청은 생성된 후 2시간 후에 만료됩니다. 이번에 복구 요청이 완료되지 않은 경우 복구 요청 프로세스를 다시 시작해야 합니다.
6. 그림 7에 **표시된 SEMM** 재설정 키 선택 페이지에 표시된 인증서 목록에서 **SEMM** 인증서를 선택하고 다음을 클릭하거나 **누를 수 있습니다**.

   ![복구 요청에 대해 SEMM 인증서를 선택합니다.](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *그림 7. 복구 요청에 대해 SEMM 인증서 선택(다시 설정 요청)*

7. 그림 9와 같이 **SEMM** 다시 설정 확인 코드 입력 페이지에서 **QR** 코드 또는 텍스트 **** 단추를 클릭하여 그림 8과 같이 복구 요청(다시 설정 요청)을 표시하거나 **USB** 단추를 클릭하여 복구 요청(다시 설정 요청)을 USB 드라이브에 파일로 저장할 수 있습니다.

   ![복구 요청이 QR 코드로 표시됩니다.](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *그림 8. QR 코드로 표시되는 복구 요청(다시 설정 요청)*

   ![복구 요청을 USB 드라이브에 저장합니다.](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *그림 9. USB 드라이브에 복구 요청 저장(다시 설정 요청)*

   * QR 코드 복구 요청(다시 설정 요청)을 사용하려면 모바일 장치에서 QR 판독기 앱을 사용하여 코드를 읽습니다. QR 판독기 앱은 QR 코드를 영문 문자열로 변환합니다. 그런 다음 Microsoft Surface UEFI 구성기에서 다시 설정 확인 코드를 생성하는 관리자에게 해당 문자열을 전자 메일로 보내거나 메시지를 보낼 수 있습니다.
   * USB 드라이브에 저장된 복구 요청(다시 설정 요청)을 파일로 사용하려면 USB 드라이브를 사용하여 Microsoft Surface UEFI 구성기에서 재설정 확인 코드를 생성하는 데 사용할 컴퓨터로 파일을 전송합니다. 다른 장치의 USB 드라이브에서 파일을 복사하여 네트워크를 통해 전자 메일로 보내거나 전송할 수도 있습니다.
   * 복구 요청(다시 설정 요청)을 텍스트로 사용하기 위해 Microsoft Surface UEFI 구성 도구에 직접 텍스트를 입력하면 됩니다.

8. 다른 컴퓨터의 웹 시작 메뉴 Microsoft Surface UEFI 구성기 를  여십시오.
    >[!NOTE]
    >Microsoft Surface UEFI 구성기는 SEMM 인증서에 대한 인증서 체인을 인증할 수 있는 환경에서 실행해야 합니다.
9. **시작**을 클릭합니다.
10. 그림 10 **과 같이** 복구 요청을 클릭합니다.

    ![복구 요청을 승인하는 프로세스를 시작하십시오.](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *그림 10. 복구 요청을 클릭하여 복구 요청 승인 프로세스를 시작*

11. 인증서 **보호를 클릭하여** SEMM 인증서로 복구 요청을 인증합니다.
12. SEMM 인증서 파일을 찾아 선택한 다음 확인을 **클릭합니다**.
13. 그림 11에 표시된 인증서 암호를 입력하라는 메시지가 표시되면 인증서 파일의 암호를 입력하고 확인한 다음 확인을 **클릭합니다**.

    ![SEMM 인증서의 암호를 입력합니다.](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *그림 11. SEMM 인증서의 암호를 입력합니다.*

14. **다음**을 클릭합니다.
15. 복구 요청(다시 설정 요청)을 입력한 다음 **** 생성을 클릭하여 초기화 확인 코드를 생성합니다(그림 12에 표시).

    ![복구 요청을 입력합니다.](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *그림 12. 복구 요청 입력(다시 설정 요청)*

    * 초기화할 Surface 디바이스에서 복구 요청(다시 설정 요청)을 텍스트로 표시한 경우 키보드를 사용하여 제공된 필드에 복구 요청(다시 설정 요청)을 입력합니다.
    * 복구 요청(다시 설정 요청)을 QR 코드로 표시한 다음 메시징 또는 전자 메일 응용 프로그램을 사용하여 Microsoft Surface UEFI 구성기에서 컴퓨터에 코드를 보내는 경우 코드를 복사하여 제공된 필드에 붙여넣습니다.
    * 복구 요청(다시 설정 요청)을 USB 드라이브에 파일로 저장한 경우 가져오기 단추를 **** 클릭하고 복구 요청(다시 설정 요청) 파일을 찾아 선택한 다음 확인을 **클릭합니다**.

16. 초기화 확인 코드는 그림 13에 표시된 Microsoft Surface UEFI 구성기에서 표시됩니다.

    ![초기화 확인 코드 표시](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *그림 13. Microsoft Surface UEFI 구성기에서 표시되는 재설정 확인 코드*

    * 공유 단추 **를** 클릭하여 전자 메일로 재설정 확인 코드를 전송합니다.

17. 그림 8에 표시된 Surface 디바이스의 제공된 필드에 재설정 확인 코드를 입력한 다음 Verify(확인)을 클릭하거나 눌러 **** 장치를 초기화하고 SEMM에서 디바이스를 초기화하고 디바이스를 초기화합니다.
18. 그림 14 **** 에 표시된 같이 **SEMM** 다시 설정 성공 페이지에서 지금 다시 시작을 클릭하거나 눌러 SEMM에서의 계정 해지를 완료합니다.

    ![SEMM에서 성공적인 인가를 표시하는 예제입니다.](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *그림 14. SEMM에서 성공적 인가*

19. Microsoft **** Surface UEFI 구성기에서 종료를 클릭하여 복구 요청(초기화 요청) 프로세스를 완료하고 Microsoft Surface UEFI 구성을 닫습니다.


