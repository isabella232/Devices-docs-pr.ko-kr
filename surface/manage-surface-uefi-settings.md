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
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835855"
---
# Surface UEFI 설정 관리

모든 현재 및 향후 세대의 Surface 디바이스는 특별히 이러한 장치용으로 Microsoft에서 엔지니어링 한 고유한 통합 확장 가능 펌웨어 인터페이스 (UEFI)를 사용 합니다. Surface UEFI 설정은 기본 제공 디바이스 및 구성 요소를 사용 하거나 사용 하지 않도록 설정 하 고, UEFI 설정이 변경 되지 않도록 보호 하 고, Surface device boot 설정을 조정할 수 있는 기능을 제공 합니다. 

## 클라우드 기반 관리 지원

Microsoft Intune (공개 미리 보기에서 사용 가능)에 빌드된 DFCI (디바이스 펌웨어 구성 인터페이스) 프로필을 사용 하면 Surface UEFI 관리에서 최신 관리 스택을 UEFI 하드웨어 수준으로 확장 합니다. DFCI는 0 터치 프로비저닝을 지원 하 고, BIOS 암호를 제거 하 고, 부팅 옵션 및 기본 제공 주변 장치를 비롯 한 보안 설정 제어를 제공 하며, 앞으로 고급 보안 시나리오의 토대를 배치 합니다. 현재 Surface Pro 7, Surface Pro X 및 Surface 노트북 3에는 DFCI를 사용할 수 있습니다. 자세한 내용은 [SURFACE UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)를 참조 하세요.

## 서피스 UEFI 메뉴 열기

시스템 시작 중에 UEFI 설정을 조정 하려면 다음을 수행 합니다.

1. 화면을 종료 하 고 10 초의 시간이 지난 후 종료 되었는지 확인 합니다.
2. **볼륨 위로** 단추를 길게 누르고 나 서 **전원 단추** 를 눌렀다가 놓습니다.
3. 화면에 Microsoft 또는 Surface 로고가 표시 됨에 따라 UEFI 화면이 나타날 때까지 **볼륨** 단추를 계속 누르고 있습니다.

## UEFI PC 정보 페이지

PC 정보 페이지에는 Surface device에 대 한 자세한 정보가 포함 됩니다. 

- **모델** – surface Book 2 또는 surface Pro 7과 같이 surface 디바이스의 모델이 여기에 표시 됩니다. 프로세서, 디스크 크기, 메모리 크기와 같은 정확한 디바이스 구성은 표시되지 않습니다. 
- **UUID** – 이 Universally Unique Identifier 번호는 디바이스별로 고유하며, 배포 또는 관리하는 동안 디바이스를 식별하는 데 사용됩니다. 

- **일련 번호** - 이 번호는 자산 태깅 및 지원 시나리오에서 이 특정 Surface 디바이스를 식별하는 데 사용됩니다.
- **자산 태그** – 자산 태그는 [자산 태그 도구](https://docs.microsoft.com/surface/assettag)를 사용하여 Surface 디바이스에 할당됩니다. 

Surface 디바이스의 펌웨어에 대한 자세한 정보도 확인할 수 있습니다. Surface 디바이스에는 각각 다른 버전의 펌웨어를 실행하는 몇 가지 내부 구성 요소가 있습니다. 다음 디바이스 각각의 펌웨어 버전은 **PC 정보** 페이지에 표시됩니다(그림 1 참조). 

- 시스템 UEFI 

- SAM 컨트롤러 

- Intel 관리 엔진 

- 시스템 포함 컨트롤러 

- 터치 펌웨어 

![시스템 정보 및 펌웨어 버전 정보](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*그림 1. 시스템 정보 및 펌웨어 버전 정보*

Surface 디바이스의 최신 펌웨어 버전에 대한 최신 정보는 디바이스의 [Surface 업데이트 기록](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)에서 확인할 수 있습니다. 

## UEFI 보안 페이지 

![Surface UEFI 보안 설정 구성](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*그림 2. Surface UEFI 보안 설정 구성*

보안 페이지에서는 UEFI 설정을 보호 하는 암호를 설정할 수 있습니다. Surface 디바이스를 UEFI로 부팅할 때 이 암호를 입력해야 합니다. 암호에는 다음 문자를 포함할 수 있습니다 (그림 3). 

- 대문자: A-Z 

- 소문자: a-z 

- 숫자: 1-0 

- 특수 문자:! @ # $% ^& * ()? <>{} []-_ = + |.,;: ' ' " 

암호는 6자 이상이어야 하며 대/소문자를 구분합니다. 

![Surface UEFI 설정 보호를 위해 암호 추가](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*그림 3. Surface UEFI 설정 보호를 위해 암호 추가*

보안 페이지에서 Surface 디바이스에 대한 보안 부팅 구성을 변경할 수도 있습니다. 보안 부팅 기술은 무단 부팅 코드가 Surface 디바이스에서 부팅되는 문제를 방지하여 bootkit 및 루트킷 형식의 맬웨어 감염으로부터 보호합니다. Surface 디바이스에서 타사 운영 체제 또는 부팅 가능한 미디어를 허용하기 위해 보안 부팅을 사용하지 않도록 설정할 수 있습니다. 그림 4와 같이 타사 인증서와 작동 하도록 보안 부팅을 구성할 수도 있습니다. TechNet 라이브러리에서 [보안 부팅](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)에 대해 자세히 알아보세요.

![보안 부팅 구성](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*그림 4. 보안 부팅 구성*

장치에 따라 TPM을 사용 하거나 사용 하지 않도록 설정 하는 방법도 확인할 수 있습니다. **Tpm 사용** 설정이 표시 되지 않으면 그림 5와 같이 Windows에서 tpm을 열어 상태를 확인 합니다. TPM은 BitLocker로 디바이스 데이터에 대한 암호화를 인증하는 데 사용됩니다. 자세히 알아보려면 [BitLocker 개요](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)를 참조 하세요. 

![TPM 콘솔](images/manage-surface-uefi-fig5-a.png "TPM console")

*그림 5. TPM 콘솔*


## UEFI 메뉴: 장치 

Devices (장치) 페이지에서는 다음과 같은 특정 장치 및 구성 요소를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

- 도킹 및 USB 포트 

- MicroSD 또는 SD 카드 슬롯 

- 후면 카메라 

- 전면 카메라 

- IR(적외선) 카메라 

- Wi-Fi 및 Bluetooth 

- 온보드 오디오(스피커 및 마이크) 

각 장치에는 그림 6과 같이 **On** (enabled) 또는 **Off** (사용 안 함) 위치로 이동할 수 있는 슬라이더 단추가 표시 됩니다. 

![특정 디바이스를 사용하거나 사용하지 않도록 설정](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*그림 6. 특정 디바이스를 사용하거나 사용하지 않도록 설정*

## UEFI 메뉴: 부팅 구성 

부팅 구성 페이지를 통해 부팅 장치의 순서를 변경 하 고 다음 장치의 부팅을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 

- Windows 부팅 관리자 

- USB 저장소 

- PXE 네트워크 

- 내부 저장소 

특정 디바이스에서 즉시 부팅할 수도 있고, 터치 스크린을 사용하여 목록에서 해당 디바이스 항목을 왼쪽으로 살짝 밀 수도 있습니다. 또한 Surface 디바이스 전원이 꺼질 때 **볼륨 작게** 단추 및 **전원** 단추를 동시에 눌러 USB 디바이스 또는 USB 이더넷 어댑터로 즉시 부팅할 수도 있습니다. 

지정한 부팅 순서를 적용 하려면 그림 7과 같이 **대체 부팅 순서 사용** 옵션을 **On**으로 설정 해야 합니다. 

![Surface 디바이스에 대한 부팅 순서 구성](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*그림 7. Surface 디바이스에 대한 부팅 순서 구성* 

예를 들어 PXE를 사용하여 Windows 배포를 수행하는 경우(여기서 PXE 서버는 IPv4 전용으로 구성됨) **Enable IPv6 for PXE Network Boot**(PXE 네트워크 부팅을 위해 IPv6 사용) 옵션을 사용하여 PXE용 IPv6 지원을 켜거나 끌 수도 있습니다.  

## UEFI 메뉴: 관리
관리 페이지에서 0 터치 UEFI 관리 및 Surface Pro 7, Surface Pro X, Surface 랩톱 3을 비롯 한 적격 디바이스의 기타 기능 사용을 관리할 수 있습니다.  

![0 터치 UEFI 관리 및 기타 기능에 대 한 액세스를 관리 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *합니다 (그림 8). 제로 터치 UEFI 관리 및 기타 기능에 대 한 액세스 관리* 


0 터치 UEFI 관리를 사용 하면 Intune CI (디바이스 펌웨어 구성 인터페이스) 라는 장치 프로필을 통해 UEFI 설정을 원격으로 관리할 수 있습니다. 이 설정을 구성 하지 않으면 DFCI를 사용 하 여 적격 장치를 관리 하는 기능이 **준비**됨으로 설정 됩니다. DFCI를 방지 하려면 **옵트아웃**을 선택 합니다. 

> [!NOTE]
> UEFI 관리 설정 페이지와 DFCI의 사용은 Surface Pro 7, Surface Pro X 및 Surface 노트북 3 에서만 사용할 수 있습니다.  

자세한 내용은 [SURFACE UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)를 참조 하세요.

## UEFI 메뉴: 종료 

그림 9와 같이 **끝내기** 페이지의 **지금 다시 시작** 단추를 사용 하 여 UEFI 설정을 종료 합니다. 

![UEFI 화면을 종료하고 디바이스를 다시 시작](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*그림 9. 지금 다시 시작을 클릭하여 UEFI 화면을 종료하고 디바이스를 다시 시작*

## Surface UEFI 부팅 화면

Surface 디바이스 펌웨어를 업데이트할 때 Windows 업데이트나 수동 설치를 사용하여 업데이트가 디바이스에 즉시 적용되지 않고 다음 다시 부팅 주기 동안 적용됩니다. Surface 펌웨어 업데이트 프로세스에 대한 자세한 내용은 [Surface 드라이버 및 펌웨어 업데이트 관리](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)를 참조하세요. 펌웨어 업데이트 진행률이 화면에 표시되고 진행률 표시줄은 각 구성 요소의 펌웨어를 나타내는 여러 색으로 구성됩니다. 각 구성 요소의 진행률 표시줄은 그림 9 ~ 18에 표시 됩니다.

![파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*그림 10. 파랑 진행률 표시줄이 표시된 Surface UEFI 펌웨어 업데이트*

![녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*그림 11. 녹색 진행률 표시줄이 표시된 시스템 포함 컨트롤러 펌웨어*

![주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*그림 12. 주황색 진행률 표시줄이 표시된 SAM 컨트롤러 펌웨어 업데이트*

![빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*그림 13. 빨강 진행률 표시줄이 표시된 Intel 관리 엔진 펌웨어 업데이트*

![회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*그림 14. 회색 진행률 표시줄이 표시된 Surface 터치 펌웨어 업데이트*

![연한 녹색 진행률 표시줄이 있는 Surface KIP 펌웨어](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*그림 15. Surface KIP 펌웨어 업데이트는 연한 녹색 진행률 표시줄을 표시 합니다.*

![분홍색 진행률 표시줄이 있는 Surface ISH 펌웨어](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*그림 16 연한 분홍 진행률 표시줄을 표시 하는 Surface ISH 펌웨어 업데이트*

![회색 진행률 표시줄이 있는 Surface 트랙 패드 펌웨어](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*그림 17. Surface 트랙 패드 펌웨어 업데이트는 분홍색 진행률 표시줄을 표시 합니다.*

![연한 회색 진행률 막대가 있는 펌웨어의 표면 tc](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*그림 18. 펌웨어 업데이트의 Surface TCON 밝은 회색 진행률 표시줄을 표시 합니다.*


![연한 자주색 진행률 표시줄이 있는 Surface TPM 펌웨어](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*그림 19. Surface TPM 펌웨어 업데이트는 자주색 진행률 표시줄을 표시 합니다.*


>[!NOTE]
>그림 19와 같이 보안 부팅이 비활성화 됨을 나타내는 추가 경고 메시지가 표시 됩니다.

![보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*그림 20. Surface UEFI 설정에서 보안 부팅이 사용하지 않도록 설정되었음을 나타내는 Surface 부팅 화면*

## 관련 항목

- [Surface UEFI 설정의 Intune 관리](surface-manage-dfci-guide.md)

-  [Surface Enterprise 관리 모드](surface-enterprise-management-mode.md)
