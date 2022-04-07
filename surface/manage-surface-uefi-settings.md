---
title: Surface UEFI 설정 관리
description: Surface UEFI 설정을 사용하여 디바이스나 구성 요소를 사용하거나 사용하지 않도록 설정하고, 보안 설정을 구성하고, Surface 디바이스 부팅 설정을 조정합니다.
keywords: 펌웨어, 보안, 기능, 구성, 하드웨어
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 04/01/2022
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e38fb3ae8a25fddfcb64985a64b41d4d2e084178
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472657"
---
# <a name="manage-surface-uefi-settings"></a>Surface UEFI 설정 관리

 Surface PC 디바이스는 특히 이러한 디바이스에 대해 Microsoft에서 엔지니어링한 고유한 UEFI(Unified Extensible Firmware Interface)를 활용하도록 설계되었습니다. Surface UEFI 설정은 기본 제공 디바이스 및 구성 요소를 사용하거나 사용하지 않도록 설정하고, UEFI 설정이 변경되지 않도록 보호하고, Surface 디바이스 부팅 설정을 조정하는 기능을 제공합니다.

## <a name="supported-products"></a>지원되는 제품

UEFI 관리는 다음에서 지원됩니다.

- Surface Pro 4, Surface Pro(5세대), Surface Pro 6, Surface Pro 7, Surface Pro 7 이상(상용 SKU만 해당), Surface Pro 8(상용 SKU만 해당), Surface Pro X
- Surface Laptop(1세대), Surface Laptop 2, Surface Laptop 3(인텔 프로세서만 해당), Surface Laptop Go, Surface Laptop 4(상용 SKU만 해당), Surface Laptop SE
- Surface Studio(1세대), Surface Studio 2
- Surface Book(모든 세대)
- Surface Laptop Studio(상업용 SKU만 해당)
- Surface Go, Surface Go [21<sup></sup>](#references), Surface Go 3(상업용 SKU만 해당)

>[!TIP]
> 상업용 SKU(비즈니스용Surface)는 Windows 10 Pro/Enterprise 실행하거나 Windows 11 Pro/Enterprise; 소비자 SKU는 Windows 10/Windows 11 Home 실행합니다. UEFI에서 상업용 SKU는 [디바이스 페이지](#uefi-devices-page) 및 [관리 페이지를](#uefi-management-page) 특징으로 하는 유일한 모델입니다. 자세한 내용은 [시스템 정보 보기를 참조하세요](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 


## <a name="support-for-cloud-based-management"></a>클라우드 기반 관리 지원

DFCI(디바이스 펌웨어 구성 인터페이스) 프로필이 Microsoft Intune(현재 공개 미리 보기로 제공됨)를 사용하면 Surface UEFI 관리는 최신 관리 스택을 UEFI 하드웨어 수준으로 확장합니다. DFCI는 제로 터치 프로비저닝을 지원하고, BIOS 암호를 제거하고, 부팅 옵션 및 기본 제공 주변 장치를 포함한 보안 설정을 제어하며, 향후 고급 보안 시나리오를 위한 토대를 마련합니다. DFCI는 현재 Surface Laptop SE, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3에 사용할 수 있습니다. Surface Laptop 3, Surface Pro 7 이상, Surface Pro 7 및 Surface Pro X입니다. 자세한 내용은 [Surface UEFI 설정의 Intune 관리를 참조하세요](surface-manage-dfci-guide.md).

## <a name="open-surface-uefi-menu"></a>Surface UEFI 메뉴 열기

시스템 시작 중에 UEFI 설정을 조정하려면 다음을 수행합니다.

1. Surface를 종료하고 10초 정도 기다렸다가 꺼져 있는지 확인합니다.
2. **볼륨 업** 단추를 길게 누르고 동시에 **전원 단추를** 누르고 놓습니다.
3. Microsoft 또는 Surface 로고가 화면에 표시되면 UEFI 화면이 나타날 때까지 **볼륨 업** 단추를 계속 유지합니다.

## <a name="uefi-pc-information-page"></a>UEFI PC 정보 페이지

PC 정보 페이지에는 Surface 디바이스에 대한 자세한 정보가 포함되어 있습니다.

- **모델** – Surface 디바이스의 모델이 여기에 표시됩니다(예: Surface Book 2 또는 Surface Pro 7). 디바이스의 정확한 구성이 표시되지 않습니다(예: 프로세서, 디스크 크기 또는 메모리 크기).
- **UUID** – 이 Universally Unique Identifier 번호는 디바이스별로 고유하며, 배포 또는 관리하는 동안 디바이스를 식별하는 데 사용됩니다.

- **일련 번호** – 이 숫자는 자산 태그 지정 및 지원 시나리오에 대해 이 특정 Surface 디바이스를 식별합니다.
- **자산 태그** – 자산 태그는 [자산 태그 도구](assettag.md)를 사용하여 Surface 디바이스에 할당됩니다.

Surface 디바이스의 펌웨어에 대한 자세한 정보도 확인할 수 있습니다. Surface 디바이스에는 각각 다른 버전의 펌웨어를 실행하는 몇 가지 내부 구성 요소가 있습니다. 다음 디바이스 각각의 펌웨어 버전은 **PC 정보** 페이지에 표시됩니다(그림 1 참조).

- 시스템 UEFI

- SAM 컨트롤러

- Intel 관리 엔진

- 시스템 포함 컨트롤러

- 터치 펌웨어

:::image type="content" alt-text="시스템 정보 및 펌웨어 버전 정보입니다." source="images/manage-surface-uefi-figure-1.png":::

*그림 1. 시스템 정보 및 펌웨어 버전 정보*

Surface 디바이스의 최신 펌웨어 버전에 대한 최신 정보는 디바이스의 [Surface 업데이트 기록](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)에서 확인할 수 있습니다.

## <a name="uefi-security-page"></a>UEFI 보안 페이지

:::image type="content" alt-text="Surface UEFI 보안 설정을 구성합니다." source="images/manage-surface-uefi-fig4.png":::

*그림 2. Surface UEFI 보안 설정 구성*

보안 페이지에서 암호를 설정하여 UEFI 설정을 보호할 수 있습니다. Surface 디바이스를 UEFI로 부팅할 때 이 암호를 입력해야 합니다. 암호는 다음 문자를 포함할 수 있습니다(그림 3에 표시된 대로).

- 대문자: A-Z

- 소문자: a-z

- 숫자: 1-0

- 특수 문자: !@#$%^&*()?<>{}[]-_=+|.,;:''

암호는 6자 이상이어야 하며 대/소문자를 구분합니다.

![Surface UEFI 설정을 보호하는 암호를 추가합니다.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*그림 3. Surface UEFI 설정 보호를 위해 암호 추가*

보안 페이지에서 Surface 디바이스에서 보안 부팅의 구성을 변경할 수도 있습니다. 보안 부팅 기술은 무단 부팅 코드가 Surface 디바이스에서 부팅되는 문제를 방지하여 bootkit 및 루트킷 형식의 맬웨어 감염으로부터 보호합니다. Surface 디바이스에서 타사 운영 체제 또는 부팅 가능한 미디어를 허용하기 위해 보안 부팅을 사용하지 않도록 설정할 수 있습니다. 그림 4와 같이 타사 인증서로 작동하도록 보안 부팅을 구성할 수도 있습니다. 자세한 내용은 [보안 부팅](/windows-hardware/design/device-experiences/oem-secure-boot)을 참조하세요.

![보안 부팅을 구성합니다.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*그림 4. 보안 부팅 구성*

디바이스에 따라 TPM이 사용 또는 비활성화되었는지도 확인할 수 있습니다. **TPM 사용** 설정이 표시되지 않으면 그림 5와 같이 Windows tpm.msc를 열어 상태를 확인합니다. TPM은 BitLocker를 사용하여 디바이스 데이터에 대한 암호화를 인증하는 데 사용됩니다. 자세한 내용은 [BitLocker 개요를](/windows/security/information-protection/bitlocker/bitlocker-overview) 참조하세요.

![TPM 콘솔.](images/manage-surface-uefi-fig5-a.png "TPM console")

*그림 5. TPM 콘솔*

## <a name="uefi-devices-page"></a>UEFI 디바이스 페이지

디바이스 페이지에서는 Surface Pro 8, Surface Go 3, Surface Laptop Studio, Surface Pro 7 이상, Surface Pro 7, Surface Pro X, Surface Laptop 4 등 적격 디바이스에서 특정 구성 요소를 사용하거나 사용하지 않도록 설정할 수 있습니다. Surface Laptop 3, Surface Laptop SE 및 Surface Book 3입니다. 구성 요소는 다음으로 구성됩니다.

- USB 포트 도킹

- MicroSD 또는 SD 카드 슬롯

- 후면 카메라

- 전면 카메라

- IR(적외선) 카메라

- Wi-Fi 및 Bluetooth

- 온보드 오디오(스피커 및 마이크)

각 디바이스는 그림 6과 같이 **켜** 기(사용) 또는 **끄기** (사용 안 함) 위치로 이동할 수 있는 슬라이더 단추와 함께 나열됩니다.

:::image type="content" alt-text="특정 디바이스를 사용하거나 사용하지 않도록 설정합니다." source="images/manage-surface-uefi-fig5a.png":::

*그림 6. 특정 디바이스를 사용하거나 사용하지 않도록 설정*

## <a name="uefi-boot-configuration-page"></a>UEFI 부팅 구성 페이지

부팅 구성 페이지에서 부팅 디바이스의 순서를 변경하고 다음 디바이스의 부팅을 사용하거나 사용하지 않도록 설정할 수 있습니다.

- Windows 부팅 관리자

- USB 저장소

- PXE 네트워크

- 내부 저장소

특정 디바이스에서 즉시 부팅하거나 터치 스크린을 사용하여 목록의 해당 디바이스 항목에서 왼쪽으로 살짝 밀 수 있습니다. 또한 Surface 디바이스 전원이 꺼질 때 **볼륨 작게** 단추 및 **전원** 단추를 동시에 눌러 USB 디바이스 또는 USB 이더넷 어댑터로 즉시 부팅할 수도 있습니다.

지정한 부팅 순서가 적용되려면 그림 7과 같이 **대체 부팅 시퀀스 사용** 옵션을 **켜**짐으로 설정해야 합니다.

:::image type="content" alt-text="Surface 디바이스에 대한 부팅 순서를 구성합니다." source="images/manage-surface-uefi-fig6.png":::

*그림 7. Surface 디바이스에 대한 부팅 순서 구성*

PXE용 IPv6 네트워크 부팅 사용 옵션을 사용하여 **PXE에 대한 IPv6** 지원을 켜고 끌 수도 있습니다. 예를 들어 PXE 서버가 IPv4용으로만 구성된 PXE를 사용하여 Windows 배포를 수행할 때도 있습니다.  

## <a name="uefi-management-page"></a>UEFI 관리 페이지

관리 페이지에서는 제로 터치 UEFI Management 및 적격 디바이스(Surface Pro 8, Surface Go 3, Surface Laptop Studio, Surface Pro 7 이상, Surface Pro 7, Surface Pro X 포함)의 기타 기능을 관리할 수 있습니다. Surface Laptop 4, Surface Laptop 3, Surface Laptop SE 및 Surface Book 3입니다. 

:::image type="content" alt-text="Zero Touch UEFI Management 및 기타 기능에 대한 액세스를 관리합니다." source="images/manage-surface-uefi-fig7a.png":::

*그림 8. Zero Touch UEFI Management 및 기타 기능에 대한 액세스 관리*

Zero Touch UEFI Management를 사용하면 DFCI(디바이스 펌웨어 구성 인터페이스)라는 Intune 내의 디바이스 프로필을 사용하여 UEFI 설정을 원격으로 관리할 수 있습니다. 이 설정을 구성하지 않으면 DFCI를 사용하여 적격 디바이스를 관리하는 기능이 **Ready**로 설정됩니다. DFCI를 방지하려면 **옵트아웃을** 선택합니다.

> [!NOTE]
> DFCI의 UEFI 관리 설정 페이지 및 사용은 현재 Surface Laptop SE, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go에 사용할 수 있습니다. Surface Book 3, Surface Laptop 3, Surface Pro 7 이상, Surface Pro 7 및 Surface Pro X입니다.  자세한 내용은 [Surface UEFI 설정의 Intune 관리를 참조하세요](surface-manage-dfci-guide.md).

## <a name="uefi-exit-page"></a>UEFI 종료 페이지

그림 9와 같이 **종료** 페이지의 **지금 다시 시작** 단추를 사용하여 UEFI 설정을 종료합니다.

:::image type="content" alt-text="Surface UEFI를 종료하고 디바이스를 다시 시작합니다." source="images/manage-surface-uefi-fig7.png":::

*그림 9. 지금 다시 시작을 클릭하여 UEFI 화면을 종료하고 디바이스를 다시 시작*

## <a name="surface-uefi-boot-screens"></a>Surface UEFI 부팅 화면

Windows 업데이트 또는 수동 설치를 사용하여 Surface 디바이스 펌웨어를 업데이트하는 경우 업데이트는 디바이스에 즉시 적용되지 않고 다음 재부팅 주기 동안 적용됩니다. [Surface 드라이버 및 펌웨어 업데이트 관리 및 배포에서 Surface 펌웨어 업데이트](manage-surface-driver-and-firmware-updates.md) 프로세스에 대해 자세히 알아볼 수 있습니다. 각 구성 요소의 펌웨어를 나타내기 위해 펌웨어 업데이트 진행률이 다른 진행률 표시줄이 화면에 표시됩니다. 각 구성 요소의 진행률 표시줄은 그림 9~18에 표시됩니다.

![파란색 진행률 표시줄을 사용하여 Surface UEFI 펌웨어 업데이트](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*그림 10. 파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트*

![녹색 진행률 표시줄이 있는 시스템 임베디드 컨트롤러 펌웨어.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*그림 11. 녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어*

![주황색 진행률 표시줄을 사용하여 SAM 컨트롤러 펌웨어를 업데이트합니다.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*그림 12. 주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트*

![빨간색 진행률 표시줄이 있는 인텔 관리 엔진 펌웨어.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*그림 13. 빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트*

![회색 진행률 표시줄이 있는 Surface 터치 펌웨어입니다.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*그림 14. 회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트*

![밝은 녹색 진행률 표시줄이 있는 Surface KIP 펌웨어입니다.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*그림 15. Surface KIP 펌웨어 업데이트에 밝은 녹색 진행률 표시줄이 표시됩니다.*

![분홍색 진행률 표시줄이 있는 Surface ISH 펌웨어.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*그림 16 Surface ISH 펌웨어 업데이트는 연한 분홍색 진행률 표시줄을 표시합니다.*

![회색 진행률 표시줄이 있는 Surface 트랙 패드 펌웨어입니다.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*그림 17. Surface 트랙 패드 펌웨어 업데이트에 분홍색 진행률 표시줄이 표시됩니다.*

![밝은 회색 진행률 표시줄이 있는 Surface TCON 펌웨어입니다.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*그림 18. Surface TCON 펌웨어 업데이트에 밝은 회색 진행률 표시줄이 표시됩니다.*

![밝은 자주색 진행률 표시줄이 있는 Surface TPM 펌웨어입니다.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*그림 19. Surface TPM 펌웨어 업데이트에 자주색 진행률 표시줄이 표시됩니다.*

>[!NOTE]
>그림 19와 같이 보안 부팅이 비활성화되었음을 나타내는 추가 경고 메시지가 표시됩니다.

![보안 부팅이 비활성화되었음을 나타내는 Surface 부팅 화면입니다.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*그림 20. Surface UEFI 설정에서 보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면*

## <a name="references"></a>참조

1. Surface Go 및 Surface Go 2는 타사 UEFI를 사용하며 DFCI를 지원하지 않습니다. DFCI는 현재 Surface Laptop SE, Surface Laptop Studio, Surface Pro 8, Surface Go 3, Surface Laptop 4, Surface Laptop Go, Surface Book 3에 사용할 수 있습니다. Surface Laptop 3, Surface Pro 7 이상, Surface Pro 7 및 Surface Pro X입니다.

## <a name="related-topics"></a>관련 항목

- [Surface UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)

- [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
