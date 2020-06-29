---
title: SEMM (Surface)을 사용 하 여 Surface 장치 등록 및 구성
description: Surface uefi의 설정을 제어 하는 Surface UEFI 구성 패키지를 만드는 방법과 surface 디바이스를 SEMM에 등록 하는 방법에 대해 알아봅니다.
keywords: surface enterprise 관리
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835951"
---
# SEMM을 사용하여 Surface 장치 등록 및 구성

Microsoft Surface Enterprise 관리 모드 (SEMM)를 사용 하 여 surface device의 Surface UEFI 설정을 안전 하 게 구성 하 고 조직의 Surface 장치에서 해당 설정을 관리할 수 있습니다. Surface 디바이스를 SEMM로 관리 하는 경우 해당 디바이스를 *등록* 하는 것으로 간주 됩니다 (활성화 됨이 라고도 함). 이 문서에서는 Surface UEFI의 설정을 제어 하는 데만 사용할 수 있는 Surface UEFI 구성 패키지를 만드는 방법에 대해 설명 하 고, Surface 디바이스를 SEMM에도 등록 하 게 됩니다.

SEMM에 대 한 더 높은 수준의 개요는 [Microsoft Surface Enterprise 관리 모드](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)를 참조 하세요.

Surface Pro 7의 클라우드에서 펌웨어를 관리 하는 효율적인 방법으로 이제 공개 미리 보기를 통해 surface Pro X 및 Surface 랩톱 3을 사용할 수 있습니다. 자세한 내용은 [SURFACE UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)를 참조 하세요.

> [!NOTE]
> SEMM은 UEFI 관리자를 통해 Surface Pro X에서 지원 됩니다. 자세한 내용은 [Surface Pro X 배포, 관리 및 서비스](surface-pro-arm-app-management.md)를 참조 하세요.

#### Microsoft Surface UEFI 구성자 다운로드 및 설치
SEMM 패키지를 만드는 데 사용 되는 도구는 Microsoft Surface UEFI 구성자입니다. Microsoft Surface UEFI Configurator를 다운로드 센터의 IT 페이지의 [Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703) 에서 다운로드할 수 있습니다.
Microsoft Surface UEFI Configurator Windows Installer (.msi) 파일을 실행 하 여 도구의 설치를 시작 합니다. 설치 관리자가 완료 되 면 시작 메뉴의 모든 앱 섹션에서 Microsoft Surface UEFI 구성자를 찾습니다.

>[!NOTE]
>Microsoft Surface UEFI 구성자는 Windows 10 에서만 지원 됩니다.

## Surface UEFI 구성 패키지 만들기

Surface UEFI 구성 패키지는 SEMM으로 관리 되는 surface 장치에 Surface UEFI 설정의 새 구성을 적용 하는 역할을 모두 수행 하 고, SEMM의 Surface 디바이스를 등록 하는 역할을 합니다. 구성 패키지를 만들려면 각 Surface 디바이스에서 UEFI 설정의 구성을 보호 하기 위해 SEMM와 함께 서명 인증서를 사용 해야 합니다. SEMM 인증서의 요구 사항에 대 한 자세한 내용은 [Microsoft Surface Enterprise 관리 모드](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)를 참조 하세요.

Surface UEFI 구성 패키지를 만들려면 다음 단계를 따릅니다.

1. 시작 메뉴에서 Microsoft Surface UEFI 구성자를 엽니다.
2. **시작**을 클릭합니다.
3. 그림 1에 표시 된 대로 **구성 패키지**를 클릭 합니다.

   ![SEMM 등록 패키지 만들기](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *그림 1. 구성 패키지를 선택 하 여 SEMM 등록 및 구성에 대 한 패키지를 만듭니다.*

4. 그림 2와 같이 개인 키 (.pfx)를 사용 하 여 내보낸 인증서 파일을 추가 하려면 **인증서 보호** 를 클릭 합니다. 인증서 파일의 위치로 이동 하 여 파일을 선택한 다음 **확인**을 클릭 합니다.

   ![SEM certificate 및 Surface UEFI 암호를 구성 패키지에 추가](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *그림 2. Surface UEFI 구성 패키지에 SEMM 인증서 및 Surface UEFI 암호 추가*

5. 인증서 암호를 확인 하 라는 메시지가 나타나면 인증서 파일에 대 한 암호를 입력 하 고 확인 한 다음 **확인**을 클릭 합니다.
6. **암호 보호** 를 클릭 하 여 Surface UEFI에 암호를 추가 합니다. UEFI로 부팅할 때마다이 암호가 필요 합니다. 이 암호를 입력 하지 않으면 **PC 정보**, **정보**, **엔터프라이즈 관리**및 **종료** 페이지만 표시 됩니다. 이것은 선택 사항입니다.
7. 메시지가 표시 되 면 Surface UEFI에 대해 선택한 암호를 입력 하 고 확인 한 다음 **확인**을 클릭 합니다. 기존 Surface UEFI 암호를 지우려면 암호 필드를 비워 둡니다.
8. Surface UEFI 패키지를 특정 장치에 적용 하지 않으려면 **대상으로 지정할 표면 유형 선택** 페이지에서 해당 surface Book 또는 Surface Pro 4 이미지 아래에 있는 슬라이더를 클릭 하 여 **해당 위치에 놓습니다.** (그림 3에 표시 된 것과 같습니다.)
   > [!NOTE] 
   > 기본적으로 선택 되어 있지 않은 장치를 선택 해야 합니다.

   ![패키지 호환성 장치 선택](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *그림 3. 패키지 호환성 장치 선택*

9. **다음**을 클릭합니다.
10. 관리 되는 Surface 디바이스에서 구성 요소를 비활성화 하려면 **활성화할 구성 요소 선택** 페이지에서 비활성화할 장치 또는 장치 그룹 옆에 있는 슬라이더를 클릭 하 여 슬라이더가 **꺼짐** 위치에 오도록 합니다. (그림 4에 표시 됩니다.) 각 장치에 대 한 기본 구성은 **켜져**있습니다. 모든 슬라이더를 기본 위치로 되돌리려면 **원래 대로** 단추를 클릭 합니다.

    ![Surface 구성 요소를 사용 하지 않거나 사용 하도록 설정](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *그림 4. 개별 Surface 구성 요소 사용 또는 사용 안 함*

11. **다음**을 클릭합니다.
12. Surface UEFI의 고급 옵션을 사용 하거나 사용 하지 않도록 설정 하거나 Surface UEFI 페이지를 표시 하려면 **장치에 대 한 고급 설정 선택** 페이지에서 원하는 설정 옆에 있는 슬라이더를 클릭 하 여 해당 옵션을 **on** 또는 **Off** 로 구성 합니다 (그림 5에 표시 됨). **Uefi 프론트 페이지** 섹션에서 **보안**, **장치**, **부팅** 슬라이더를 사용 하 여 Surface UEFI로 부팅 하는 사용자가 사용할 수 있는 페이지를 제어할 수 있습니다. Surface UEFI 설정에 대 한 자세한 내용은 [SURFACE uefi 설정 관리](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)를 참조 하세요. 패키지를 생성 하 고 저장 하는 옵션을 선택 했으면 **빌드** 를 클릭 합니다.

    ![고급 표면 UEFI 설정 및 Surface UEFI 페이지 제어](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *그림 5. 고급 표면 UEFI 설정 및 Surface UEFI 페이지 (SEMM 사용) 제어*

13. 다른 이름 **으로 저장** 대화 상자에서 Surface UEFI 구성 패키지의 이름을 지정 하 고 파일을 저장할 위치로 이동한 다음 **저장**을 클릭 합니다.
14. 패키지를 만들고 저장 하면 **성공** 페이지가 표시 됩니다.

>[!NOTE]
>그림 6과 같이이 페이지에 표시 되는 인증서 지문 문자를 기록 합니다. 이 문자는 새 Surface 디바이스의 등록을 확인 하는 데 필요 합니다 (SEMM). **끝내기** 를 클릭 하 여 패키지 만들기를 완료 하 고 MICROSOFT Surface UEFI 구성자를 닫습니다.

![인증서 지문 문자 표시](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*그림 6. 인증서 손도장의 마지막 두 문자가 성공한 페이지에 표시 됨*

이제 Surface UEFI 구성 패키지를 만들었으므로 Surface 디바이스를 등록 하거나 구성할 수 있습니다.

>[!NOTE]
>Surface UEFI 구성 패키지가 만들어지면 바탕 화면에 구성 패키지 설정 및 옵션에 대 한 세부 정보가 포함 된 로그 파일이 만들어집니다.

## Surface device를 SEMM로 등록
Surface UEFI 구성 패키지가 실행 되 면 SEMM 인증서 및 Surface UEFI 구성 파일은 Surface 디바이스의 펌웨어 저장소에 준비 됩니다. Surface 장치를 다시 부팅 하면 Surface UEFI는 이러한 파일을 처리 하 고 그림 7과 같이 surface UEFI 구성을 적용 하거나 Surface device를 등록 하는 프로세스를 시작 합니다.

![Surface UEFI 또는 등록을 구성 하기 위한 SEMM 프로세스](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*그림 7. Surface UEFI 또는 Surface device의 등록 구성에 대 한 SEMM 프로세스*

Surface device를 SEMM에 등록 하기 위한 프로세스를 시작 하기 전에 먼저 인증서 손도장의 마지막 두 문자를 보유 하 고 있는지 확인 합니다. 디바이스의 등록을 확인 하는 데 다음 문자가 필요 합니다 (그림 6 참조).

Surface UEFI 구성 패키지를 사용 하 여 Surface device를 SEMM에 등록 하려면 다음 단계를 따릅니다.

1. 등록 하려는 Surface 장치에서 Surface UEFI 구성 패키지 .msi 파일을 SEMM에 실행 합니다. 이는 디바이스의 펌웨어에 Surface UEFI 구성 파일을 프로 비전 합니다.
2. **사용권 계약에 동의** 확인란을 선택 하 여 EULA (최종 사용자 사용권 계약)를 수락 하 고 **설치** 를 클릭 하 여 설치 프로세스를 시작 합니다.
3. **마침을** 클릭 하 여 surface UEFI 구성 패키지 설치를 완료 하 고 메시지가 표시 되 면 surface 장치를 다시 시작 합니다.
4. Surface UEFI는 구성 파일을 로드 하 고 디바이스에서 SEMM이 활성화 되지 않은 것을 확인 합니다. Surface UEFI는 다음과 같이 SEMM 등록 프로세스를 시작 합니다.
   * Surface UEFI는 SEMM 구성 파일에 SEMM 인증서가 포함 되어 있는지 확인 합니다.
   * Surface UEFI는 그림 8과 같이 Surface 디바이스의 등록을 확인 하기 위해 인증서 손도장의 마지막 두 문자를 입력 하 라는 메시지를 표시 합니다.

      ![SEMM 등록에는 인증서 손도장의 마지막 두 문자가 필요 합니다.](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *그림 8. SEMM의 등록에는 인증서 손도장의 마지막 두 문자가 필요 합니다.*

   * Surface UEFI는 펌웨어에 SEMM 인증서를 저장 하 고 Surface UEFI 구성 파일에 지정 된 구성 설정을 적용 합니다.
   
5. Surface 디바이스는 이제 SEMM에 등록 되어 있으며 Windows로 부팅 됩니다.

화면 장치가 **프로그램 및 기능** (그림 9에 표시 된 대로) 또는 **Microsoft surface UEFI 구성자** 로그에 저장 되어 있는 이벤트 (그림 10의 이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 에 있음 **)에서 성공적** 으로 등록 되었는지 확인할 수 있습니다.

![프로그램 및 기능에서 Surface device의 등록 확인 (SEMM)](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*그림 9. 프로그램 및 기능에서 Surface device 등록 확인 (SEMM)*

![이벤트 뷰어에서 SEMM의 Surface device 등록 확인](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*그림 10. 이벤트 뷰어에서 SEMM의 Surface 장치 등록 확인*

디바이스를 Surface UEFI의 SEMM에 등록 했는지 확인할 수도 있습니다. 디바이스를 등록 하는 동안 Surface UEFI에는 **엔터프라이즈 관리** 페이지가 포함 됩니다 (그림 11 참조).

![Surface UEFI 엔터프라이즈 관리 페이지](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*그림 11. Surface UEFI Enterprise 관리 페이지*


## SEMM을 사용 하 여 Surface UEFI 설정 구성

디바이스가 SEMM에 등록 되 면 동일한 SEMM 인증서로 서명 된 Surface UEFI 구성 패키지를 실행 하 여 새 Surface UEFI 설정을 적용할 수 있습니다. 이러한 설정은 사용자가 개입할 필요 없이 다음에 장치가 부팅 될 때 자동으로 적용 됩니다. Microsoft 끝점 구성 관리자와 같은 응용 프로그램 배포 솔루션을 사용 하 여 surface 장치에 surface UEFI 구성 패키지를 배포 하 여 surface UEFI의 설정을 변경 하거나 관리할 수 있습니다.

구성 관리자를 사용 하 여 Windows Installer (.msi) 파일을 배포 하는 방법에 대 한 자세한 내용은 [Microsoft Endpoint Configuration Manager를 사용 하 여 응용 프로그램 배포 및 관리](https://technet.microsoft.com/library/mt627959)를 참조 하세요.

암호를 사용 하 여 Surface UEFI를 보호 하는 경우 Surface UEFI로 부팅 하려고 시도 하는 암호 없이는 **PC 정보**, **엔터프라이즈 관리**및 해당 **사용자에 게**표시 되는 **종료** 페이지만 사용할 수 있습니다.

암호를 사용 하 여 Surface UEFI 보안을 설정 하지 않은 경우 또는 사용자가 암호를 올바르게 입력 하는 경우 SEMM을 사용 하 여 구성한 설정이 흐리게 표시 되 고 (사용할 수 없음) 조직에서 관리 하는 일부 설정이 페이지 위쪽에 표시 됩니다 (그림 12).

![Surface UEFI에서 SEMM을 사용 하 여 관리 되는 설정](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*그림 12. SEMM로 관리 되는 설정은 Surface UEFI에서 사용할 수 없게 됩니다.*
