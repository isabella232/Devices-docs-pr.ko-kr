---
title: Surface UEFI 설정의 Intune 관리
description: 이 문서에서는 Microsoft Intune에서 DFCI 환경을 구성하고 대상 Surface 디바이스의 펌웨어 설정을 관리하는 방법을 설명합니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271572"
---
# Surface UEFI 설정의 Intune 관리

## 소개

클라우드에서 장치를 관리하는 능력은 수명 주기 전반에 걸쳐 IT 배포 및 프로비저닝을 크게 간소화했습니다. [Microsoft Intune에](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)기본 제공되는 DFCI(장치 펌웨어 구성 인터페이스) 프로필을 사용하여 Surface UEFI 관리는 최신 관리 스택을 UEFI 하드웨어 수준으로 확장합니다. DFCI는 제로 터치 프로비전을 지원하고, BIOS 암호를 제거하고, 부팅 옵션 및 기본 제공 주변 장치를 비롯한 보안 설정을 제어하며, 향후 고급 보안 시나리오를 위한 초안을 마련합니다. 자주 묻는 질문에 대한 답변은 [Ignite 2019: Intune에서 Surface UEFI](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)설정의 원격 관리 발표를 참조하세요.

### Background

Windows 10을 실행하는 모든 컴퓨터와 마찬가지로 Surface 디바이스는 CPU가 하드 드라이브, 디스플레이 장치, USB 포트 및 기타 장치와 연결할 수 있도록 SoC에 저장된 코드를 사용합니다. 이 읽기 전용 메모리(ROM)에 저장된 프로그램을 펌웨어라고 합니다(동적 미디어에 저장된 프로그램을 소프트웨어라고도 합니다).

현재 시장에서 사용 가능한 다른 Windows 10 장치와 달리 Surface는 IT 관리자에게 다양한 UEFI 구성 설정 집합을 통해 펌웨어를 구성하고 관리하는 기능을 제공합니다. 이렇게 하면 MDM(모바일 장치 관리) 정책, Configuration Manager 또는 그룹 정책을 통해 구현되는 소프트웨어 기반 정책 관리 위에 하드웨어 제어 계층이 구현됩니다. 예를 들어 중요한 정보가 있는 높은 보안 영역에 장치를 배포하는 조직은 하드웨어 수준에서 기능을 제거하여 카메라 사용을 방지할 수 있습니다. 디바이스 관점에서 펌웨어 설정을 통해 카메라를 끄는 것은 카메라를 물리적으로 제거하는 데 해당합니다. 펌웨어 수준에서 추가된 관리 보안을 운영 체제 소프트웨어 설정에만 적용하는지 비교합니다. 예를 들어 도메인 환경에서 정책 설정을 통해 Windows 오디오 서비스를 사용하지 않도록 설정한 경우 로컬 관리자가 서비스를 다시 사용하도록 설정할 수 있습니다.

### DFCI와 SEMM

이전에 펌웨어를 관리하려면 수동 IT를 많이 사용하는 작업의 오버헤드를 통해 Surface SEMM(엔터프라이즈 관리 모드)에 장치를 등록해야 합니다. 예를 들어 SEMM을 사용하려면 IT 직원이 인증서 관리 프로세스의 일부로 두 자리 핀을 입력하기 위해 각 PC에 물리적으로 액세스해야 합니다. SEMM은 엄격하게 온-프레미스 환경의 조직에 좋은 솔루션으로 유지되어도 복잡성과 IT를 많이 사용하는 요구 사항으로 인해 비용이 많이 드는 것입니다.

 Microsoft Intune의 통합된 UEFI 펌웨어 관리 기능을 통해 하드웨어를 잠그는 기능이 간소화되고 프로비저닝, 보안 및 간소화된 업데이트에 대한 새로운 기능을 단일 콘솔에서 사용할 수 있으며, [이제는 Microsoft Endpoint Manager로](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)통합되었습니다. 다음 그림에서는 디바이스(왼쪽)에서 직접 보고 끝점 관리자 콘솔(오른쪽)에 표시한 UEFI 설정을 보여줍니다.

![디바이스(왼쪽) 및 Endpoint Manager 콘솔에 표시되는 UEFI 설정(오른쪽)](images/uefidfci.png)

중요하게 DFCI는 제로 터치 관리를 가능하게 하여 IT 관리자가 수동으로 상호 작용할 필요가 없습니다. DFCI는 Intune의 장치 프로필 기능을 사용하여 Windows Autopilot을 통해 배포됩니다. 장치 프로필을 사용하면 조직 내의 관리에 등록된 장치에 배포할 수 있는 설정을 추가하고 구성할 수 있습니다. 디바이스가 장치 프로필을 받으면 기능 및 설정이 자동으로 적용됩니다. 일반적인 장치 프로필의 예로는 전자 메일, 장치 제한, VPN, Wi-Fi 및 관리 템플릿이 있습니다. DFCI는 단순히 클라우드에서 UEFI 구성 설정을 관리할 수 있는 추가 장치 프로필로, 프레미스 인프라를 유지 관리하지 않고도 관리할 수 있습니다.  

## 지원되는 디바이스

DFCI는 다음 장치에서 지원됩니다.

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface 노트북 3
- Surface Book 3
- Surface 노트북 이동

> [!NOTE]
> Surface Pro X는 기본 제공 카메라, 오디오 및 Wi-Fi/에 대한 DFCI 설정 관리를 지원하지 Bluetooth.

## 필수 구성 요소

- 디바이스는 [Microsoft CSP(클라우드](https://partner.microsoft.com/membership/cloud-solution-provider) 솔루션 공급자) 파트너 또는 OEM 배포자가 Windows Autopilot에 등록해야 합니다.

- Surface에 대한 DFCI를 구성하기 전에  [Microsoft Intune](https://docs.microsoft.com/intune/) 및 Azure [AD(Azure Active](https://docs.microsoft.com/azure/active-directory/) Directory)의 Autopilot 구성 요구 사항에 익숙해야 합니다.

## 시작하기 전에

Azure AD 보안 그룹에 대상 Surface 디바이스를 추가합니다. 보안 그룹을 만들고 관리하는 데 대한 자세한 내용은 [Intune 설명서를 참조하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## Surface 디바이스에 대한 DFCI 관리 구성

DFCI 환경에서는 등록된 장치에 설정을 적용하기 위한 설정 및 Autopilot 프로필이 포함된 DFCI 프로필을 설정해야 합니다. 등록 상태 프로필은 사용자가 장치를 처음 시작할 때 OOBE 설정 중에 설정이 푸시되도록 하는 것이 좋습니다. 이 가이드에서는 대상 Surface 디바이스에 대한 DFCI 환경을 구성하고 UEFI 구성 설정을 관리하는 방법을 설명합니다.

## DFCI 프로필 만들기

DFCI 정책 설정을 구성하기 전에 먼저 DFCI 프로필을 만들어 대상 장치가 포함된 Azure AD 보안 그룹에 할당합니다.

1. 테넌트에 로그인하여 devicemanagement.microsoft.com.
2. Microsoft Endpoint Manager 관리 센터에서 장치 및 > 프로필을 선택하고 > 프로필을 만들고 이름을 입력합니다. **** 예: **DFCI 구성 정책**
3. 플랫폼 **유형으로 Windows 10 이상을** 선택합니다.
4. 프로필 유형 드롭다운 목록에서 장치 펌웨어 **구성** 인터페이스를 선택하여 사용 가능한 모든 정책 설정이 포함된 DFCI 블레이드를 니다. DFCI 설정에 대한 자세한 내용은 이 페이지 또는 [Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)설명서의 표 1을 참조하십시오. DFCI 프로필을 편집하여 초기 설치 프로세스 또는 이후 단계에서 DFCI 설정을 구성할 수 있습니다.

    ![DFCI 프로필 만들기](images/df1.png)

5. 확인을 **클릭한** 다음 만들기를 **선택합니다.**
6. 다음 그림과 **** 같이 **할당을** 선택하고 그룹 선택에 대상 장치가 포함된 Azure AD 보안 그룹을 선택합니다. **저장**을 클릭합니다.

    ![보안 그룹 할당](images/df2a.png)

## Autopilot 프로필 만들기

1. In Endpoint Manager at devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles.**
2. 프로필 **만들기를 선택하고** 이름을 입력합니다. 예를 들어 **내 Autopilot 프로필을 선택하고**다음을 **선택합니다.**
3. 다음 설정을 선택합니다.

    - 배포 모드: **사용자 기반**.
    - 가입 유형: Azure **AD 가입**.

4. 다음 그림과 같이 나머지 기본 **** 설정은 변경되지 않은 그대로 유지하고 다음을 선택합니다.

    ![Autopilot 프로필 만들기](images/df3b.png)

5. 배정 페이지에서 포함할 **** 그룹 선택을 선택하고 Azure AD 보안 그룹을 클릭합니다. **다음**을 선택합니다.
6. 요약을 수락한 다음 만들기를 **선택합니다.** 이제 Autopilot 프로필이 만들어지며 그룹에 할당됩니다.

## 등록 상태 구성 페이지

사용자가 로그인하기 전에 OOBE 중에 DFCI 구성을 적용하려면 등록 상태를 구성해야 합니다.

자세한 내용은 등록 상태 설정 [페이지를 참조하십시오.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)


## Surface 디바이스에서 DFCI 설정 구성

DFCI에는 하드웨어 수준에서 장치를 잠가 추가 수준의 보안을 제공하는 간소화된 UEFI 구성 정책 집합이 포함되어 있습니다. DFCI는 소프트웨어 수준에서 모바일 장치 관리 설정과 함께 사용할 수 있도록 디자인됩니다. DFCI 설정은 Surface 디바이스에 기본 제공되는 하드웨어 구성 요소에만 영향을 주며 USB 웹캠과 같은 연결된 주변 장치로 확장되지 않습니다. 그러나 Intune에서 장치 제한 정책을 사용하여 소프트웨어 수준에서 연결된 주변 장치에 대한 액세스를 해제할 수 있습니다.

아래 그림과 같이 끝점 관리자에서 DFCI 프로필을 편집하여 DFCI 정책 설정을 구성합니다. 

- Devicemanagement.microsoft.com 끝점 관리자에서 Windows > 구성 프로필 > **"DFCI 프로필 이름">** 속성 > 선택 > 선택합니다.

    ![DFCI 설정 구성](images/dfciconfig.png)

### UEFI 설정에 대한 사용자 액세스 차단

많은 고객의 경우 사용자가 UEFI 설정을 변경하지 못하게 차단하는 능력이 매우 중요하고 DFCI를 사용하는 주된 이유입니다. 표 1에 나열된 것 처럼 이 설정은 로컬 사용자가 UEFI 설정을 변경할 수 있도록 허용 설정을 **통해 관리됩니다.** 이 설정을 편집하거나 구성하지 않는 경우 로컬 사용자는 Intune에서 관리되지 않는 UEFI 설정을 변경할 수 있습니다. 따라서 로컬 사용자가 **UEFI** 설정을 변경할 수 있도록 허용하지 않도록 설정하는 것이 좋습니다.
나머지 DFCI 설정을 사용하면 사용자가 사용할 수 있는 기능을 해제할 수 있습니다. 예를 들어 보안이 높은 영역에서 중요한 정보를 보호해야 하는 경우 카메라를 사용하지 않도록 설정할 수 있으며, 사용자가 USB 드라이브에서 부팅하지 못하게 하려는 경우 이 기능도 사용하지 않도록 설정할 수 있습니다.

### 표 1. DFCI 시나리오

| 장치 관리 목표                        | 구성 단계                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 로컬 사용자가 UEFI 설정을 변경하지 못하게 차단 | 보안 **기능 > UEFI 설정을**변경할 수 있도록 허용하려면 없음을 **선택합니다.**              |
| 카메라를 사용하지 않도록 설정                               | 기본 제공 하드웨어 > **카메라에서**사용 안 을 **선택합니다.**                                       |
| 마이크 및 스피커 사용 안              | Built **in Hardware > Microphones and speakers,** select **Disabled**.                      |
| 라디오 사용 안 Bluetooth(Bluetooth, Wi-Fi)             | 기본 제공 하드웨어 > **라디오(Bluetooth, Wi-Fi 등)에서**사용 안 을 **선택합니다.**                   |
| 외부 미디어(USB, SD)에서 부팅을 사용하지 않도록 설정    | 기본 제공 하드웨어 > **부팅 옵션에서 >(USB, SD)에서**부팅하려면 사용 **안 을 선택합니다.** |

> [!CAUTION]
> 무선 **송수신 장치(Bluetooth, Wi-Fi)** 설정은 유선 이더넷 연결이 있는 디바이스에서만 사용해야 합니다.
 
> [!NOTE]
>  Intune의 DFCI에는 현재 Surface 장치에 적용되지 않는 두 가지 설정, 즉 (1) CPU 및 IO 가상화와 (2) 네트워크 어댑터에서 부팅을 사용하지 않도록 설정.
 
Intune은 관리 권한 및 적용성 규칙을 위임하여 장치 유형을 관리하는 범위 태그를 제공합니다. 모든 DFCI 설정에 대한 정책 관리 지원 및 전체 세부 정보에 대한 자세한 내용은 [Microsoft Intune 설명서를 참조하십시오.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

## Autopilot에서 장치 등록

위에서 설명한 대로 DFCI는 대리점 또는 배포자에 의해 Windows Autopilot에 등록된 디바이스에만 적용될 수 있으며 Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X 및 Surface Laptop 3에서만 지원됩니다. 보안상의 이유로 Autopilot에 장치를 "자체 프로비전"할 수 없습니다. 자세한 내용은 Windows [Autopilot에](surface-autopilot-registration-support.md)대한 Surface 등록 지원을 참조합니다. 

## Autopilot 장치 수동 동기화

Intune 정책 설정은 일반적으로 거의 즉시 적용되지만 설정이 대상 장치에 적용되기까지 10분의 지연이 있을 수 있습니다. 드물지만 최대 8시간의 지연이 가능합니다. 설정이 가능한 한 빨리 적용되도록(예: 테스트 시나리오) 대상 장치를 수동으로 동기화할 수 있습니다.

- In Endpoint Manager at devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync.**

 자세한 내용은 Windows 장치 수동 [동기화를 참조하세요.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> UEFI에서 직접 설정을 조정할 때 장치가 표준 Windows 로그인으로 완전히 다시 시작되도록 해야 합니다.

## DFCI 관리 장치에서 UEFI 설정 확인

테스트 환경에서는 Surface UEFI 인터페이스에서 설정을 확인할 수 있습니다.

1. 볼륨 + 및 전원 단추를 동시에 **** 누르는 **** 데 관련된 Surface UEFI를 니다.
2. 디바이스를 **선택합니다.** UEFI 메뉴는 다음 그림과 같이 구성된 설정을 반영합니다.

    ![Surface UEFI](images/df3.png)

    다음 방법을 참고합니다.

      - 로컬 사용자가 **UEFI** 설정을 변경할 수 있도록 허용이 없음으로 설정되어 있기 때문에 설정이 회색으로 표시됩니다.
      - 마이크와 스피커가 **** 사용 안 하게 설정되어 있기 때문에 오디오가 **꺼집니다.**

## DFCI 정책 설정 제거

DFCI 프로필을 만들면 구성된 모든 설정이 프로필 관리 범위 내의 모든 디바이스에서 계속 적용됩니다. DFCI 프로필을 직접 편집하여 DFCI 정책 설정만 제거할 수 있습니다.

원래 DFCI 프로필이 삭제된 경우 새 프로필을 만들고 설정을 적절하게 편집하여 정책 설정을 제거할 수 있습니다.

## DFCI 관리 제거

**DFCI 관리를 제거하고 장치를 공장 새 상태로 되 되 관리하려면**

1. Intune에서 디바이스를 사용 중지합니다.
    1. In Endpoint Manager at devicemanagement.microsoft.com, choose **Groups > All Devices.** 사용 중지할 장치를 선택한 다음 사용 **중지/지우기를 선택합니다.** 자세한 내용은 장치 지우기, 사용 중지 또는 수동으로 장치 초기화를 사용하여 장치 제거를 [참조하세요.](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 
2. Intune에서 Autopilot 등록을 삭제합니다.
    1.  Windows 등록 또는 > **장치 등록을 > 선택하세요.**
    2. Windows Autopilot 디바이스에서 삭제할 장치를 선택한 다음 삭제를 **선택하십시오.**
3. Surface 브랜드 이더넷 어댑터를 사용하여 장치를 유선 인터넷에 연결합니다. 장치를 다시 시작하고 UEFI 메뉴를 열어서(전원 단추를 누르고 하면서 볼륨 업 단추를 누르고 있습니다).
4. 네트워크에서 **> 관리** > 구성한 다음 **옵트아웃을 선택합니다.**

Intune을 사용하여 디바이스를 계속 관리하지만 DFCI 관리가 없는 경우 장치를 Autopilot에 자체 등록하고 Intune에 등록합니다. DFCI는 자체 등록 장치에 적용되지 않습니다.

## 자세히 알아보기
- [Ignite 2019: Intune에서 Surface UEFI](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 설정의 원격 관리 발표 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 및 Surface 디바이스](windows-autopilot-and-surface-devices.md) 
- [Microsoft Intune에서 Windows 장치에서 DFCI 프로필 사용](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
