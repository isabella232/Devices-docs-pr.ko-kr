---
title: Surface UEFI 설정의 Intune 관리
description: 이 문서에서는 Microsoft Intune에서 DFCI 환경을 구성 하는 방법과 대상 Surface 장치에 대 한 펌웨어 설정을 관리 하는 방법을 설명 합니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/13/2019
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 0aa69bb229f0d76972620bc58f236e43e03075b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835583"
---
# Surface UEFI 설정의 Intune 관리

## 소개

클라우드에서 디바이스를 관리 하는 기능을 통해 수명 주기 동안 IT 구축과 구축이 대폭 간소화 되었습니다. Microsoft Intune ( [공개 미리 보기](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)에서 사용 가능)에 빌드된 Dfci (디바이스 펌웨어 구성 인터페이스) 프로필을 사용 하면 Surface uefi 관리에서 최신 관리 스택을 UEFI 하드웨어 수준으로 확장 합니다. DFCI는 0 터치 프로비저닝을 지원 하 고, BIOS 암호를 제거 하 고, 부팅 옵션 및 기본 제공 주변 장치를 비롯 한 보안 설정 제어를 제공 하며, 앞으로 고급 보안 시나리오의 토대를 배치 합니다. 자주 묻는 질문에 대 한 답변은 [Ignite 2019: Intune에서 SURFACE UEFI 설정의 원격 관리](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)를 참조 하세요.

### Background

Windows 10을 실행 하는 컴퓨터와 마찬가지로 Surface 디바이스는 SoC에 저장 된 코드를 사용 하 여 CPU가 하드 드라이브, 디스플레이 장치, USB 포트 및 기타 장치에 대해 인터페이스를 사용할 수 있도록 합니다. 이 읽기 전용 메모리 (ROM)에 저장 된 프로그램을 펌웨어 라고 하며, 동적 미디어에 저장 된 프로그램을 소프트웨어 라고 합니다.

현재 시중에 제공 되는 다른 Windows 10 장치와 대조적으로, Surface는 풍부한 UEFI 구성 설정을 통해 펌웨어를 구성 하 고 관리 하는 기능을 IT 관리자에 게 제공 합니다. 이는 MDM (모바일 디바이스 관리) 정책, 구성 관리자 또는 그룹 정책을 통해 구현 되는 소프트웨어 기반 정책 관리 위에 하드웨어 컨트롤 계층을 제공 합니다. 예를 들어 중요 한 정보를 사용 하 여 매우 안전한 영역에 장치를 배포 하는 조직은 하드웨어 수준에서 기능을 제거 하 여 카메라 사용을 방지할 수 있습니다. 디바이스 측면에서 펌웨어 설정을 통해 카메라를 끄면 카메라를 물리적으로 제거 하는 것과 같습니다. 펌웨어 수준의 관리에 대 한 추가 보안을 운영 체제 소프트웨어 설정에만 의존 하도록 비교 합니다. 예를 들어 도메인 환경에서 정책 설정을 통해 Windows 오디오 서비스를 사용 하지 않도록 설정 하는 경우 로컬 관리자가 서비스를 다시 사용 하도록 설정할 수 있습니다.

### DFCI 및 SEMM

지금까지 펌웨어 관리에는 디바이스를 Surface Enterprise 관리 모드 (SEMM)에 등록 해야 하며 수동 IT 집약적 작업을 진행 하는 오버 헤드가 있습니다. 예를 들어, 인증서 관리 프로세스의 일부로 두 자리 pin을 입력 하려면 IT 담당자가 각 PC에 실제로 액세스 해야 합니다. SEMM은 엄격 하 게 온-프레미스 환경에서 조직에 좋은 솔루션으로 남아 있지만, 복잡도와 IT 집약적 요구 사항은 사용 비용이 필요 합니다.

Microsoft Intune의 새로운 통합 UEFI 펌웨어 관리 기능을 사용 하는 경우, 하드웨어를 잠그는 기능은 단일 콘솔에서 모두 [Microsoft 끝점 관리자로](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)통합 되는 배포, 보안 및 간소화 업데이트를 위한 새 기능을 간편 하 게 사용할 수 있습니다. 다음 그림은 장치 (왼쪽)에서 직접 표시 되 고 끝점 관리자 콘솔 (오른쪽)에 표시 되는 UEFI 설정을 보여 줍니다.

![장치에 표시 된 UEFI 설정 (왼쪽) 및 끝점 관리자 콘솔 (오른쪽)](images/uefidfci.png)

Crucially, DFCI는 제로 터치식 관리를 사용 하 여 IT 관리자가 수동으로 조작 해야 하는 것을 제거 합니다. DFCI는 Intune에서 장치 프로필 기능을 사용 하 여 Windows Autopilot를 통해 배포 됩니다. 장치 프로필을 사용 하면 조직 내 관리에 등록 된 장치에 배포할 수 있는 설정을 추가 및 구성할 수 있습니다. 장치에서 디바이스 프로필을 수신 하면 기능과 설정이 자동으로 적용 됩니다. 일반 장치 프로필의 예로는 전자 메일, 장치 제한, VPN, Wi-fi 및 관리 서식 파일이 있습니다. DFCI는 온-프레미스 인프라를 유지 관리할 필요 없이 클라우드에서 UEFI 구성 설정을 관리 하는 데 사용할 수 있는 추가 디바이스 프로필입니다.  

## 지원되는 디바이스

이번에는 다음 장치에서 DFCI가 지원 됩니다.

- Surface Pro 7
- Surface Pro X
- Surface 노트북 3

> [!NOTE]
> Surface Pro X는 기본 제공 카메라, 오디오 및 Wi-fi/Bluetooth에 대 한 DFCI 설정 관리를 지원 하지 않습니다.

## 필수 구성 요소

- 장치는 [MICROSOFT CSP (Cloud Solution Provider) 파트너](https://partner.microsoft.com/membership/cloud-solution-provider) 또는 OEM 배포자가 Windows Autopilot에 등록 해야 합니다.

- Surface 용 DFCI를 구성 하기 전에 [Microsoft Intune](https://docs.microsoft.com/intune/) 및 [azure Active DIRECTORY](https://docs.microsoft.com/azure/active-directory/) (Azure AD)의 Autopilot 구성 요구 사항에 대해 잘 알고 있어야 합니다.

## 시작하기 전에

Azure AD 보안 그룹에 대상 Surface 디바이스를 추가 합니다. 보안 그룹을 만들고 관리 하는 방법에 대 한 자세한 내용은 [Intune 설명서](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)를 참조 하세요.

## Surface 장치에 대 한 DFCI 관리 구성

DFCI 환경에는 설정 및 Autopilot 프로필을 포함 하는 DFCI 프로필을 설정 하 여 등록 된 디바이스에 설정을 적용 해야 합니다. 또한 사용자가 장치를 처음 시작할 때 OOBE 설정 중 설정이 푸시 되도록 하려면 등록 상태 프로필을 설정 하는 것이 좋습니다. 이 가이드에서는 대상 Surface 장치에 대 한 UEFI 구성 설정을 관리 하 고 DFCI 환경을 구성 하는 방법에 대해 설명 합니다.

## DFCI 프로필 만들기

DFCI 정책 설정을 구성 하기 전에 먼저 DFCI 프로필을 만들고 대상 디바이스를 포함 하는 Azure AD 보안 그룹에 할당 합니다.

1. Devicemanagement.microsoft.com에서 테 넌 트에 로그인 합니다.
2. Microsoft Endpoint Manager 관리 센터에서 **장치 > 구성 프로필을 선택 > 프로필을 만들고** 이름을 입력 합니다. 예를 들어, **Dfci 구성 정책입니다.**
3. 플랫폼 유형을 보려면 **Windows 10 이상을** 선택 합니다.
4. 프로필 유형 드롭다운 목록에서 **장치 펌웨어 구성 인터페이스** 를 선택 하 여 사용 가능한 모든 정책 설정이 포함 된 dfci 블레이드를 엽니다. DFCI 설정에 대 한 자세한 내용은이 페이지의 표 1 또는 [Intune 설명서](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)를 참조 하세요. 초기 설정 프로세스 중 또는 나중에 DFCI 프로필을 편집 하 여 DFCI 설정을 구성할 수 있습니다.

    ![DFCI 프로필 만들기](images/df1.png)

5. **확인** 을 클릭 한 다음 **만들기**를 선택 합니다.
6. 다음 그림과 같이 **과제** 를 선택 하 고 **포함할 그룹 선택** 에서 대상 장치를 포함 하는 Azure AD 보안 그룹을 선택 합니다. **Save**을 클릭합니다.

    ![보안 그룹 할당](images/df2a.png)

## Autopilot 프로필 만들기

1. Devicemanagement.microsoft.com의 끝점 관리자에서 **Windows 등록을 > 장치** 를 선택 하 고 **배포 프로필**까지 아래로 스크롤합니다.
2. **프로필 만들기** 를 선택 하 고 이름을 입력 합니다. 예를 들어 **My Autopilot 프로필**을 선택한 후 **다음**을 선택 합니다.
3. 다음 설정을 선택 합니다.

    - 배포 모드: **사용자 구동**.
    - 조인 유형: Azure **AD가 참가**됨

4. 나머지 기본 설정을 변경 하지 않은 상태로 두고 다음 그림과 같이 **다음**을 선택 합니다.

    ![Autopilot 프로필 만들기](images/df3b.png)

5. 지정 페이지에서 **포함할 그룹 선택을** 선택 하 고 Azure AD 보안 그룹을 클릭 합니다. **다음**을 선택합니다.
6. 요약을 수락 하 고 **만들기**를 선택 합니다. 이제 Autopilot 프로필이 만들어지고 그룹에 할당 됩니다.

## 등록 상태 구성 페이지

사용자가 로그인 하기 전에 OOBE 중에 장치에서 DFCI 구성을 적용 하도록 하려면 등록 상태를 구성 해야 합니다.

자세한 내용은 [등록 상태 페이지 설정을](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)참조 하세요.


## Surface 장치에서 DFCI 설정 구성

DFCI에는 하드웨어 수준에서 장치를 잠금으로써 추가 보안 수준을 제공 하는 효율적인 UEFI 구성 정책 집합이 포함 되어 있습니다. DFCI는 소프트웨어 수준의 모바일 장치 관리 설정과 함께 사용할 수 있도록 설계 되었습니다. DFCI 설정은 Surface 디바이스에 기본 제공 되는 하드웨어 구성 요소에만 영향을 미치며 USB 웹캠 등의 연결 된 주변 장치로 확장 되지 않습니다. (그러나 Intune에서 장치 제한 정책을 사용 하 여 소프트웨어 수준에서 연결 된 주변 기기에 대 한 액세스를 해제할 수 있습니다.)

아래 그림에 표시 된 대로 끝점 관리자에서 DFCI 프로필을 편집 하 여 DFCI 정책 설정을 구성 합니다. 

- Devicemanagement.microsoft.com의 끝점 관리자에서 **장치 > Windows > 구성 프로필 > "DFCI 프로필 이름" > 속성 > 설정을**선택 합니다.

    ![DFCI 설정 구성](images/dfciconfig.png)

### UEFI 설정에 대 한 사용자 액세스 차단

대부분의 고객의 경우 UEFI 설정을 변경 하는 것을 차단 하는 기능은 매우 중요 하며,이는 DFCI를 사용 하는 주요 이유입니다. 표 1에 나열 된 대로이는 **로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용**설정을 통해 관리 됩니다. 이 설정을 편집 하거나 구성 하지 않으면 로컬 사용자가 Intune에서 관리 되지 않는 UEFI 설정을 변경할 수 있습니다. 따라서 **로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용** 하지 않는 것이 좋습니다.
나머지 DFCI 설정을 사용 하면 사용자에 게 제공 되는 기능을 끌 수 있습니다. 예를 들어 매우 안전한 영역에서 중요 한 정보를 보호 해야 하는 경우 카메라를 사용 하지 않도록 설정 하 고 사용자가 USB 드라이브에서 부팅할 수 없도록 하려는 경우에도이를 비활성화할 수 있습니다.

### 표 1. DFCI 시나리오

| 장치 관리 목표                        | 구성 단계                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 로컬 사용자가 UEFI 설정을 변경 하지 못하도록 차단 | **보안 기능에서 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용 >** 하 고 **없음**을 선택 합니다.              |
| 카메라 사용 안 함                               | **기본 하드웨어 > 카메라**에서 **사용 안 함**을 선택 합니다.                                       |
| 마이크 및 스피커 사용 안 함              | **기본 제공 하드웨어 > 마이크 및 스피커**에서 **사용 안 함**을 선택 합니다.                      |
| 무선 송수신 장치 해제 (블루투스, Wi-fi)             | **기본 제공 하드웨어 > 라디오 (블루투스, wi-fi 등)** 에서 **사용 안 함**을 선택 합니다.                   |
| 외부 미디어 (USB, SD)에서 부팅 사용 안 함    | **기본 제공 하드웨어 > 부팅 옵션에서 외부 미디어 (USB, SD)로 부팅 >** **사용 안 함**을 선택 합니다. |

> [!CAUTION]
> **무선 송수신 장치 (Bluetooth, wi-fi) 설정 비활성화** 는 유선 이더넷 연결이 있는 디바이스 에서만 사용 해야 합니다.
 
> [!NOTE]
>  Intune의 DFCI에는 현재 Surface 디바이스에 적용 되지 않는 두 가지 설정 (1) CPU 및 IO 가상화와 네트워크 어댑터에서 부팅할 수 없음이 포함 됩니다.
 
Intune은 장치 유형을 관리 하기 위해 관리 권한 및 적응성 규칙을 위임 하는 범위 태그를 제공 합니다. 모든 DFCI 설정에 대 한 자세한 내용 및 정책 관리 지원에 대 한 자세한 내용은 [Microsoft Intune 설명서](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)를 참조 하세요.

## Autopilot에서 디바이스 등록

위에서 설명한 것 처럼, DFCI는 리셀러 또는 배포자에의 한 Windows Autopilot 등록 된 장치에만 적용 될 수 있으며, 현재는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에서 지원 됩니다. 보안상의 이유로 장치를 Autopilot에 "자체 프로 비전" 할 수 없습니다.

## 수동으로 Autopilot 장치 동기화

Intune 정책 설정이 일반적으로 즉시 적용 되지만, 설정 된 장치에서 설정이 적용 되기까지 10 분이 걸릴 수 있습니다. 드문 경우 지만 최대 8 시간 동안 지연 될 수 있습니다. 테스트 시나리오와 같이 가능한 한 빨리 설정을 적용 하려면 대상 장치를 수동으로 동기화 할 수 있습니다.

- Devicemanagement.microsoft.com의 끝점 관리자에서 장치 **> 장치 등록 > windows > Windows Autopilot 장치로** 이동한 다음 **동기화**를 선택 합니다.

 자세한 내용은 [Windows 장치를 수동으로 동기화](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)를 참조 하세요.

> [!NOTE]
> UEFI에서 직접 설정을 조정할 때는 장치가 표준 Windows 로그인으로 완전히 다시 시작 되는지 확인 해야 합니다.

## DFCI 관리 장치에서 UEFI 설정을 확인 하는 중

테스트 환경에서는 Surface UEFI 인터페이스에서 설정을 확인할 수 있습니다.

1. 한 번에 **볼륨 +** 및 **전원** 단추를 누르는 것과 관련 된 UEFI 서피스를 엽니다.
2. **장치**를 선택 합니다. UEFI 메뉴에는 다음 그림과 같이 구성 된 설정이 반영 됩니다.

    ![Surface UEFI](images/df3.png)

    참고 방법:

      - **로컬 사용자가 UEFI를 변경할 수 있음 설정이** 없음으로 설정 되어 있으므로 설정이 회색으로 표시 됩니다.
      - **마이크와 스피커가** **사용 안 함으로**설정 되어 오디오는 꺼짐으로 설정 되어 있습니다.

## DFCI 정책 설정 제거

DFCI 프로필을 만들면 구성 된 모든 설정이 프로필의 관리 범위 내에 있는 모든 장치에 적용 됩니다. DFCI 프로필을 직접 편집 하 여 DFCI 정책 설정만 제거할 수 있습니다.

원래 DFCI 프로필을 삭제 한 경우 새 프로필을 만든 다음 설정을 편집 하 여 정책 설정을 제거할 수 있습니다.

## DFCI 관리 제거

**DFCI 관리를 제거 하 고 디바이스에서 출고시 새 상태로 돌아가려면 다음을 수행 합니다.**

1. Intune에서 장치 사용 중지:
    1. Devicemanagement.microsoft.com의 끝점 관리자에서 **모든 장치 > 그룹**을 선택 합니다. 사용 중지 하려는 장치를 선택 하 고 사용 **중지/지우기를 선택 합니다.** 자세한 내용은 [닦아내기, 중지 또는 수동으로 장치를 unenrolling 사용 하 여 디바이스 제거](https://docs.microsoft.com/intune/remote-actions/devices-wipe)를 참조 하세요. 
2. Intune에서 Autopilot 등록을 삭제 합니다.
    1.  **장치 등록 > Windows 등록 > 장치**를 선택 합니다.
    2. Windows Autopilot 장치에서 삭제 하려는 장치를 선택한 다음 **삭제**를 선택 합니다.
3. Surface 브랜드의 이더넷 어댑터를 사용 하 여 유선 인터넷에 장치를 연결 합니다. 장치를 다시 시작 하 고 UEFI 메뉴 (볼륨 위로 단추를 누른 상태에서 전원 단추를 눌렀다가 놓습니다)를 엽니다.
4. 관리 > 선택 하 여 **네트워크에서 > 새로 고침을 구성한** 다음 옵트아웃을 선택 **합니다.**

Intune CI 관리 없이 기기를 계속 관리 하려면 장치를 Autopilot에 자체 등록 하 고 Intune에 등록 합니다. DFCI가 자체 등록 디바이스에 적용 되지 않습니다.

## 자세히 알아보기
- [Ignite 2019: Intune에서 SURFACE UEFI 설정의 원격 관리를 발표 합니다.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md) 
- [Microsoft Intune에서 Windows 장치에 DFCI 프로필 사용](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
