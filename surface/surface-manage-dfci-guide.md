---
title: Surface UEFI 설정의 Intune 관리
description: 이 문서에서는 Microsoft Intune에서 DFCI 환경을 구성하고 대상 지정된 Surface 장치에 대한 공식 엔터프라이즈 설정을 관리하는 방법을 설명합니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/19/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
ms.openlocfilehash: 9d83fe9b7febf996d2cb314399505ed050a69a92
ms.sourcegitcommit: b94832cba98e01014f7d184c85d79f8339e046c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941664"
---
# Surface UEFI 설정의 Intune 관리

## 소개

클라우드에서 장치를 관리하는 기능은 간소화된 IT 배포및 수명 주기 전반에 프로비전하는 기능입니다. Microsoft Intune에 기본으로 제공되는 DFCI(장치 정보 구성 인터페이스) 프로필(현재 공개 [미리 보기에](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)제공)을 사용하여 Surface UEFI 관리는 최신 관리 스키터를 UEFI 하드웨어 수준으로 확장합니다. DFCI는 0과 터치 프로비저닝을 지원하고, BIOS 암호를 제거하고, 부트 수능 옵션, 기본 제공 주기 등의 보안 설정을 제어하고 향후 보안 시나리오에 대한 지연력을 제공합니다. 자주 묻는 질문에 대한 대답은 [Ignite 2019: Intune에서 Surface UEFI 설정의 원격 관리 발표를 참조하세요.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)

### Background

Windows 10을 실행하는 모든 컴퓨터와 마치 Surface 장치는 CPU가 하드 드라이브, 디스플레이 디바이스, USB 포트 및 기타 장치와 인터페이스할 수 있게 해주는 소프트에 저장된 코드에 의해 의도하게 됩니다. 이 읽기 전용 메모리(ROM)에 저장된 프로그램을 친숙한 미디어에 저장된 프로그램을 사자라고 합니다. (동적 미디어에 저장된 프로그램을 소프트웨어라고 합니다.

현재 시장에 제공되는 다른 Windows 10 장치와 달리, Surface는 UEFI 구성 설정 집합을 통해 금지를 구성하고 관리할 수 있는 기능을 제공합니다. 이는 MDM(모바일 장치 관리) 정책, Configuration Manager 또는 그룹 정책을 사용하여 구현된 소프트웨어 기반 정책 관리를 위한 하드웨어 집단을 제공합니다. 예를 들어 중요한 정보가 있는 장단점에 장치를 배포하는 조직은 하드웨어 수준에서 기능을 제거하여 카메라에서 사용을 방지할 수 있습니다. 디바이스 스위치에서 시끄러지 설정을 통한 카메라를 꺼서 카메라를 실제로 제거하는 것과 상관이 있습니다. 사운드 시스템 소프트웨어 설정을 사용하기 위해 사기 기호 수준에서 관리하는 추가 보안을 비교합니다. 예를 들어 도메인 환경의 정책 설정을 사용하여 Windows 오디오 서비스를 사용하지 않도록 설정하면 로컬 관리자가 계속 서비스를 다시 사용하도록 설정할 수 있습니다.

### DFCI와 SEMM

지금까지는 계속해서 수동 IT 을 사용하는 수동 작업의 오버헤드를 사용하여 필요한 프리웨어를 SEMM(엔터프라이즈 관리 모드)로 관리합니다. 예를 들어 SEMM에는 IT 직원이 인증서 관리 프로세스의 일부로 두 자리 PC에 물리적으로 액세스해야 합니다. SEMM은 원주운 전통 환경에서의 조직에서 원격 솔루션을 유지하지만, It 복잡성 및 IT 사용을 많이 사용하는 요구 사항으로 인해 SEMM을 유용하게 사용할 수 있습니다.

이제 Microsoft Intune에서 새로 통합된 UEFI firmware management 기능을 통해 하드웨어를 잠그는 기능이 간소화되어 단일 본체에서 Microsoft 끝점 관리자로 통합된 단일 본체에서 새로운 기능을 제공하고 보안을 설정하고 다시 [관리하는 기능을 사용하기가 더 쉽습니다.](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 다음 그림은 장치(왼쪽)에서 직접 보고 끝점 관리자 본체(오른쪽)에서 본 UEFI 설정을 보여주는 그림입니다.

![장치(왼쪽) 및 끝점 관리자 본체에 표시된 UEFI 설정(오른쪽)](images/uefidfci.png)

전에 DFCI는 터치 관리를 지원하있으면 IT 관리자가 수동 상호 작용을 할 필요가 없습니다. DFCI는 Intune의 장치 프로필 기능을 사용하여 Windows Autopilot을 사용하여 배포됩니다. 장치 프로필을 사용해 조직 내 관리에 등록된 장치에 배포할 수 있는 설정을 추가하고 구성할 수 있습니다. 장치가 장치 프로필을 받으면 기능 및 설정이 자동으로 적용됩니다. 일반적인 장치 프로필의 예로는 전자 메일, 장치 제한, VPN, Wi-Fi 및 관리 템플릿이 있습니다. DFCI는 간단히, 프레미스 인프라를 유지 관리하지 않고도 클라우드에서 UEFI 구성 설정을 관리할 수 있는 추가 장치 프로필입니다.  

## 지원되는 디바이스

DFCI는 다음과 같은 장치에서 지원됩니다.

- Surface Pro 7
- Surface Pro X
- Surface 노트북 3
- Surface Book 3

> [!NOTE]
> Surface Pro X는 기본 제공 카메라, 오디오 및 Wi-Fi/Bluetooth 을 위한 DFCI 설정 관리를 지원하지 않습니다.

## 필수 구성 요소

- 장치는 [Microsoft CSP(클라우드](https://partner.microsoft.com/membership/cloud-solution-provider) 솔루션 공급자) 파트너 또는 OEM 배포자에 의해 Windows Autopilot에 등록되어 있어야 합니다.

- Surface용 DFCI를 구성하기 전에  [Microsoft Intune](https://docs.microsoft.com/intune/) 및 Azure AD(Azure [Active Directory)에서](https://docs.microsoft.com/azure/active-directory/) Autopilot 구성 요구 사항을 숙지해야 합니다.

## 시작하기 전에

Azure AD 보안 그룹에 대상 Surface 장치를 추가합니다. 보안 그룹 만들기 및 관리에 대한 자세한 내용은 [Intune 설명서를 참조하세요.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## Surface 장치에 대해 DFCI 관리 구성

DFCI 환경을 사용하려면 등록된 장치에 설정을 적용하려면 설정과 Autopilot 프로필이 포함된 DFCI 프로필을 설정해야 합니다. 사용자가 디바이스를 처음 시작할 때 OOBE 설정 중에 설정이 제거되게 하려면 등록 상태 프로필을 보내는 것이 좋습니다. 이 가이드에서는 DFCI 환경을 구성하고 대상이 지정된 Surface 장치에 대한 UEFI 구성 설정을 관리하는 방법을 설명합니다.

## DFCI 프로필 만들기

DFCI 정책 설정을 구성하기 전에 먼저 DFCI 프로필을 만들어 대상 디바이스가 포함된 Azure AD 보안 그룹에 할당합니다.

1. 비디오에서 테넌트에 devicemanagement.microsoft.com.
2. Microsoft 끝점 관리자 관리 센터에서 장치 구성 **프로필을 > 선택하고 > 입력합니다.** 예를 들어 **DFCI 구성 정책.**
3. **플랫폼 유형의 경우 Windows 10** 이상을 선택합니다.
4. 프로필 유형 드롭다운 목록에서 장치 팩트 **구성** 인터페이스를 선택하여 사용 가능한 모든 정책 설정이 포함된 DFCI 블레이드를 엽니다. DFCI 설정에 대한 자세한 내용은 이 페이지의 표 1 또는 [Intune 설명서를 참조하세요.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) 초기 설정 프로세스 중에 DFCI 설정을 구성하려면 DFCI 프로필을 편집하여 구성할 수 있습니다.

    ![DFCI 프로필 만들기](images/df1.png)

5. 확인을 **클릭한** 다음 만들기를 **선택합니다.**
6. 다음 **그림에 표시된** **대로 과제를** 선택하고 선택하여 대상 장치가 포함된 Azure AD 보안 그룹을 선택합니다. **Save**을 클릭합니다.

    ![보안 그룹 지정 그룹](images/df2a.png)

## Autopilot 프로필 만들기

1. 네트워크 기준 끝점에서 devicemanagement.microsoft.com **장치를 선택하고 아래 >로** 스크롤하여 배포 **프로필을 배포합니다.**
2. 프로필 **만들기를 선택하고** 이름입력; 예를 들어 **내 Autopilot 프로필을 선택하고**다음을 **선택합니다.**
3. 다음 설정을 선택합니다.

    - 배포 모드: **사용자 고정용.**
    - 조인 유형: Azure **AD에 가입됨.**

4. 나머지 기본 설정은 변경되지 않은 상태로 그대로 두고 다음 그림에 표시된 다음중 선택합니다. **Next**

    ![Autopilot 프로필 만들기](images/df3b.png)

5. 과제 페이지에서 포함할 **그룹을 선택하고** Azure AD 보안 그룹을 클릭합니다. **다음**을 선택합니다.
6. 요약을 수락한 다음 만들기를 **선택합니다.** 이제 Autopilot 프로필이 만들어지고 그룹에 할당됩니다.

## 등록 상태 구성 페이지

사용자가 로그인하기 전에 장치가 OOBE 중에 DFCI 구성을 적용하도록 하려면 등록 상태를 구성해야 합니다.

자세한 내용은 [등록 상태 페이지를 참조하세요.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)


## Surface 장치에서 DFCI 설정 구성

DFCI에는 하드웨어 수준에서 디바이스를 잠그어 추가 수준의 보안을 제공하는 간소화된 UEFI 구성 정책 집합이 포함됩니다. DFCI는 소프트웨어 수준의 모바일 장치 관리 설정과 함께 사용하라고 디자인되었습니다. DFCI 설정은 Surface 장치에 기본으로 제공되는 하드웨어 구성 요소에만 영향을 주며 USB 웹cam과 같은 주위사용 장치에 첨부되지 않습니다. (그러나 Intune의 장치 제한 정책을 사용하여 소프트웨어 수준에서 첨부된 주기 장치에 대한 액세스를 해제할 수 있습니다.)

아래 그림과 같이 끝점 관리자의 DFCI 프로필을 편집하여 DFCI 정책 설정을 구성합니다. 

- Office의 끝점 devicemanagement.microsoft.com 관리자에서 Windows > > > 구성 프로필 **id > 속성 > 선택합니다.**

    ![DFCI 설정 구성](images/dfciconfig.png)

### 사용자가 UEFI 설정에 액세스 차단

많은 고객의 경우 UEFI 설정을 변경하지 못하도록 차단하는 기능은 중요하고 DFCI를 사용해야 하는 주된 이유입니다. 표 1에 나열된 것처레코드는 로컬 사용자가 **UEFI 설정을 변경할 수 있도록 설정을 통해 관리됩니다.** 이 설정을 편집하거나 구성하지 않는 경우 로컬 사용자는 Intune에서 관리하지 않는 UEFI 설정을 변경할 수 있습니다. 따라서 로컬 사용자가 UEFI 설정을 변경할 **수 있도록 허용을 해제하는 것이 좋습니다.**
DFCI 설정의 나비 부분을 사용하면 사용자가 사용할 수 있는 기능을 해제할 수 있습니다. 예를 들어 중요한 정보를 고도로 안전하게 보호해야 하는 경우 카메라를 사용하지 않도록 설정할 수 있습니다. USB 드라이브의 부부를 받지 않으려면 이 기능을 사용하지 않도록 설정하면 됩니다.

### 표 1. DFCI 시나리오

| 장치 관리 목표                        | 구성 단계                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 로컬 사용자가 UEFI 설정을 변경하지 차단 | 보안 **기능>에서 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용하고**증명을 **선택합니다.**              |
| 디스메이너 비활성화                               | 기본 **제공 하드웨어 > 성격에서 사용**안 함을 **선택합니다.**                                       |
| 마이크 및 스피커 사용 안 함              | **하드웨어 새로 > 내레이터마크 및 스피커에서 사용**안 함을 **선택합니다.**                      |
| 라디오 디오오(Bluetooth, Wi-Fi)             | **하드웨어 장치 > 라디오(Bluetooth, Wi-Fi 등)에서**사용 안 **함을 선택합니다.**                   |
| 외부 미디어에서 부트수 비활성화(USB, SD)    | **기본 하드웨어 > Boot 옵션> 외부 미디어(USB, SD)에서 부스부를**받도록 선택하도록 **선택합니다.** |

> [!CAUTION]
> 유선 **이더넷 연결이 설치된 장치에서만 사용 안 함(Bluetooth, Wi-Fi)** 설정을 사용해야 합니다.
 
> [!NOTE]
>  Intune의 DFCI에는 현재 Surface 장치에 적용되지 않는 두 가지 설정이 포함되어 있습니다. (1) CPU 및 IO 가상화 및 (2) 네트워크 어터터에서 부피를 부스 해제하는 2개의 설정이 포함되어 있습니다.
 
Intune은 범위 태그를 제공하여 관리 권한과 장치 유형을 관리하기 위한 합법적인 권한과 계열사 규칙을 위임할 수 있습니다. 정책 관리 지원 및 모든 DFCI 설정에 대한 자세한 내용은 [Microsoft Intune 문서를 참조하세요.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

## Autopilot에서 장치 등록

위에서 설명한 것 과정에서 하며, DFCI는 재판매인 또는 배포자가 Windows Autopilot에 등록된 장치에서만 적용될 수 있으며 현재는 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에서만 지원됩니다. 보안상의 이유로 디바이스를 Autopilot에 "자체 프로비저닝"할 수 없습니다.

## Autopilot 장치를 수동으로 동기화

일반적으로 Intune 정책 설정은 즉시 적용되지만 설정이 대상 디바이스에 적용되기 10분 지연이 있을 수 있습니다. 드문 경우이스크인 경우 최대 8시간의 지연이 가능합니다. 설정이 가능한 한 빠르게 적용되도록 하려면(예: 테스트 시나리오)을 수동으로 적용할 수 있습니다.

- 현재 Microsoft devicemanagement.microsoft.com 엔드 관리자에서 장치 > 장치 등록 **> Windows Autopilot 장치에 만든 > 동기화를** **선택합니다.**

 자세한 내용은 Windows [장치를 수동으로 동기화를 참조하세요.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> UEFI에서 직접 설정을 조정하는 경우 장치가 표준 Windows 로그인으로 전체 다시 시작되는지 확인해야 합니다.

## DFCI 관리 장치에서 UEFI 설정 확인

테스트 환경에서는 Surface UEFI 인터페이스에서 설정을 확인할 수 있습니다.

1. 축소판 + 및 전원 버튼을 **동시에** **누르는 작업을** 하는 Surface UEFI를 엽니다.
2. 장치를 **선택합니다.** UEFI 메뉴는 다음 그림에 표시된 대로 구성된 설정을 반정합니다.

    ![Surface UEFI](images/df3.png)

    참고 방법:

      - 로컬 사용자가 UEFI 설정을 없음으로 변경할 수 **있도록 허용하므로 설정은 회색으로** 표시됩니다.
      - 마이크 및 **스피커가 사용 안 함으로 설정되어 있으므로 오디오가** 꺼져 **설정됩니다.**

## DFCI 정책 설정 제거

DFCI 프로필을 만들면, 구성된 모든 설정이 관리 프로필 범위 내의 모든 장치에서 적용됩니다. DFCI 프로필을 직접 편집하여만 DFCI 정책 설정을 제거할 수 있습니다.

원래 DFCI 프로필이 삭제된 경우 새 프로필을 만들고 적절한 대로 설정을 편집하여 정책 설정을 제거할 수 있습니다.

## DFCI 관리 제거

**DFCI 관리를 제거하고 장치를 새 상태로 반환하려면:**

1. Intune에서 장치 사용 중지:
    1. PC의 끝점 관리자에서 devicemanagement.microsoft.com **모든 장치> 선택합니다.** 사용 중지할 장치를 선택한 다음 사용 **중지/지우기를 선택합니다.** 장치 데이터 지우기를 사용하거나 사용 중지 또는 수동으로 장치를 등록 [취소하여 디바이스 제거를 참조하세요.](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 
2. Intune에서 Autopilot 레지스트리를 삭제합니다.
    1.  **장치등록에서 장치 > 등록을 > 선택합니다.**
    2. Windows Autopilot 장치에서 삭제할 장치를 선택한 다음 삭제를 **선택합니다.**
3. Surface 대역계 어플레이어를 사용하여 장치를 유선 인터넷에 연결합니다. 장치를 다시 시작하고 UEFI 메뉴를 엽니다(볼륨 크게 단추를 길게 누른 상태에서 전원 단추를 눌러
4. 네트워크에서 **새로 > 새 >로 고침 구성을 선택한 다음** **Opt out을 선택합니다.**

Intune으로 장치 관리를 계속 유지하고 DFCI 관리는 생각하지 않으려면 장치를 Autopilot에 등록하고 Intune에 등록합니다. DFCI는 자체 등록 디바이스에 적용되지 않습니다.

## 자세히 알아보기
- [Ignite 2019: Intune에서 Surface UEFI 설정의 원격 관리 발표](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md) 
- [Microsoft Intune에서 Windows 장치의 DFCI 프로필 사용](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
