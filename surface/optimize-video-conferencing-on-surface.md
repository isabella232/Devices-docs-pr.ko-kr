---
title: Surface 장치에서 비디오 회의 최적화
description: 이 페이지에서는 Surface 디바이스에서 Microsoft Teams 및 기타 비디오 회의 솔루션을 사용하는 모범 사례를 제공합니다.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/10/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 28ad64b41dedb7d66092cf98388920a732fee737
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449681"
---
# <a name="optimize-video-conferencing-on-surface-devices"></a>Surface 장치에서 비디오 회의 최적화

Surface 장치는 모바일 장치 에너지 소비의 최신 발전을 활용하여 워크로드에 최적화된 간소화된 환경을 제공합니다. 대부분의 워크로드에서 이 기능은 훌륭한 환경을 제공합니다. Microsoft Teams 또는 기타 비디오 회의 응용 프로그램을 사용하는 일부 워크로드의 경우 최상의 환경을 보장하기 위해 이러한 권장 사항을 따라야 합니다.

## <a name="surface-drivers-and-firmware"></a>Surface 드라이버 및 펌웨어

Microsoft는 Surface 디바이스에 대한 업데이트를 정기적으로 릴리스하고 다음을 포함하여 비디오 회의 워크로드를 대상으로 하는 여러 Surface 업데이트를 출시했습니다.

- 시스템 성능 개선
- 카메라 드라이버의 전원 소비 개선
- 그래픽 드라이버 업데이트
- 전원 설정 최적화

### <a name="get-updates-to-all-devices"></a>모든 장치에 대한 업데이트 다운로드

조직에서 장치에 이러한 업데이트를 받는 프로세스가 있도록 합니다. 비즈니스용 Windows 또는 Windows [업데이트를](/windows/deployment/update/waas-manage-updates-wufb) 사용하는 경우 릴리스될 때 최신 Surface 업데이트가 이미 수신됩니다. 업데이트를 사용하여 Windows 확인하고 최신 Surface 업데이트가 설치되어 있는지 확인합니다. 자세한 내용은 다음을 참조합니다.

- [Surface 업데이트 기록](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)
- [Surface 및 Windows 설치](https://www.microsoft.com/surface/support/performance-and-maintenance/install-software-updates-for-surface?)

다른 옵션을 사용하여 Surface 드라이버 및 펌웨어 업데이트를 설치하는 경우 게시된 MSI 파일을 사용하여 최신 Surface 업데이트를 수동으로 설치하거나 Configuration Manager를 사용하여 업데이트를 설치해야 합니다. 자세한 내용은 다음을 참조합니다.

- [Surface용 드라이버 및 펌웨어 다운로드](https://support.microsoft.com/help/4023482)
- [Surface 드라이버 및 펌웨어 업데이트 관리 및 배포](manage-surface-driver-and-firmware-updates.md)
- [Configuration Manager에서 Surface 드라이버 업데이트를 관리하는 방법](https://support.microsoft.com/help/4098906)

### <a name="graphics-driver-updates-for-microsoft-teams"></a>사용자에 대한 그래픽 드라이버 Microsoft Teams

10세대 및 11세대 Intel 프로세서가 탑재된 최신 Surface 디바이스 모델은 비디오 회의 워크로드에 도움이 되는 그래픽 드라이버 업데이트를 수신했습니다. 이러한 향상된 기능을 사용하려면 다음을 설치해야 합니다.

- Microsoft Teams **버전 1.4.00.22472** 이상입니다.
- Intel 그래픽 드라이버 **27.20.100.9621** 이상.

### <a name="power-settings-optimizations"></a>전원 설정 최적화

Surface 장치는 디바이스의 전원 모드라고도 하는 Windows 성능 슬라이더 위치를 변경하여 성능 관련 전원 설정을 Windows 10 수 Windows 11.

일부 Surface 디바이스는 전원 슬라이더 위치 또는 전원 모드를 기반으로 비디오 회의 워크로드에 대한 전원 설정 최적화를 포함 하는 업데이트를 수신했습니다. 그러나 Windows 10 및 Windows 11 회의 워크로드에 권장 전원 슬라이더 위치 **** 및 전원 모드 위치를 사용하기 때문에 이러한 최적화를 사용하도록 전원 슬라이더를 조정해야 합니다.

1. 커넥트 수 있습니다(배터리 전원을 사용할 때 최적화가 실행되지 않습니다).  
2. 전원 슬라이더 또는 전원 모드 위치를 조정하여 더 **** 나은 성능 또는 최상의 **성능을 사용할 수 있습니다.**

## <a name="learn-more"></a>세부 정보

- [Surface 장치의 모범 사례 전원 설정](maintain-optimal-power-settings-on-surface-devices.md)
- [Surface 배터리 사용 시간 최대화](https://support.microsoft.com/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)
