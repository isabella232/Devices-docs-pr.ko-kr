---
title: 이더넷 어댑터 및 Surface 배포(Surface)
description: 이 문서에서는 Surface 디바이스에 네트워크 배포를 수행하는 데 도움이 되는 지침과 답변을 제공합니다.
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: 이더넷, 배포, 이동식, 네트워크, 연결, 부팅, 펌웨어, 디바이스, 어댑터, PXE 부팅, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ec73d437d2784ffbceb350f38507524e761df8dd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448481"
---
# <a name="ethernet-adapters-and-surface-deployment"></a>이더넷 어댑터 및 Surface 배포

이 문서에서는 Surface Pro 3 이상을 포함하여 최신 Surface 디바이스의 네트워크 배포를 수행하는 방법에 대해 설명합니다.

Surface 디바이스에 대한 네트워크 배포 작업의 경우 시스템 관리자에게 몇 가지 고유한 문제가 발생할 수 있습니다. 네이티브 유선 이더넷 어댑터가 부족하여 관리자는 이동식 이더넷 어댑터를 통해 연결해야 합니다.

## <a name="select-an-ethernet-adapter-for-surface-devices"></a>Surface 디바이스용 이더넷 어댑터 선택

배포 환경으로 부팅하는 방법 또는 배포 솔루션에서 디바이스를 인식하는 방법에 대한 문제를 해결하려면 먼저 유선 네트워크 어댑터를 사용해야 합니다.

이더넷 어댑터를 선택할 때 주요 관심사는 어댑터가 네트워크에서 Surface 디바이스를 부팅하는 방식입니다. WDS(Windows Deployment Services)를 사용하여 클라이언트를 미리 준비하거나 Microsoft Endpoint Configuration Manager. 이 경우 이동식 이더넷 어댑터가 특정 Surface 디바이스 전용인지 아니면 여러 디바이스에서 공유될지 고려할 수도 있습니다. 공유 어댑터와의 잠재적인 충돌에 대한 자세한 내용은 이 문서 의 부분에 있는 이동식 이더넷 어댑터를 사용하여 [MAC](#manage-mac-addresses) 주소 관리를 참조하세요.

네트워크에서 부팅(PXE 부팅)은 이더넷 어댑터 또는 Microsoft의 도킹 스테이션을 사용할 때만 지원됩니다. 이더넷 어댑터 또는 도크의 칩세트는 Surface 디바이스 펌웨어에서 부팅 장치로 검색하고 구성해야 합니다. Surface Ethernet Adapter 및 [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock)와 같은 Microsoft 이더넷 어댑터는 Surface 펌웨어와 호환되는 칩셋을 사용합니다.

Surface 디바이스를 사용하는 네트워크 부팅에 지원되는 이더넷 디바이스는 다음과 같습니다.

- Surface USB-C에서 이더넷 및 USB 3.0 어댑터로
- Surface USB 3.0에서 기가비트 이더넷 어댑터까지
- Microsoft USB-C 여행 허브
- Surface 도크
- Surface Dock 2
- Surface 3용 도킹 스테이션
- Surface Pro 3용 도킹 스테이션 
- Surface Pro와 Surface Pro 2용 도킹 스테이션

타사 이더넷 어댑터의 경우 PXE 부팅이 지원되지는 않지만 네트워크 배포에는 지원됩니다. 타사 이더넷 어댑터를 사용하려면 배포 부팅 이미지에 드라이버를 로드해야 합니다. USB 스틱과 같은 별도의 저장 장치에서 해당 부팅 이미지를 실행해야 합니다.

## <a name="boot-surface-devices-from-the-network"></a>네트워크에서 Surface 디바이스 부팅

네트워크 또는 연결된 USB 스틱에서 부팅하려면 Surface 디바이스가 대체 부팅 디바이스에서 부팅하도록 지시해야 합니다. 시스템 펌웨어에서 부팅 순서를 변경하여 부팅 프로세스 중에 USB 부팅 장치의 우선 순위를 지정하거나 대체 부팅 장치에서 부팅할 수 있습니다.

**대체 부팅 장치에서 부팅하려면:**

1. Surface 디바이스가 꺼졌는지 확인합니다.
2. **볼륨 작게** 단추를 길게 누릅니다.
3. **전원** 단추를 눌렀다 놓습니다.
4. USB 스틱 또는 이더넷 어댑터에서 시스템 부팅이 시작되고 나면 **볼륨 작게** 단추를 놓습니다.

>[!NOTE]
>이더넷 어댑터 외에도 키보드를 Surface 디바이스에 연결하여 사전 설치 환경에서 배포 마법사를 탐색해야 할 수도 있습니다.

Windows 10 버전 1511 이상(Windows 10 버전 1511용 Windows ADK(Windows Assessment and Deployment Kit) 포함)의 경우 기본적으로 Microsoft Surface Ethernet Adapter용 드라이버가 제공됩니다. Microsoft Deployment Toolkit와 같이 WinPE(Windows Preinstallation Environment)를 사용하는 배포 솔루션을 사용하고 PXE를 사용하여 네트워크에서 부팅하는 경우 배포 솔루션에서 최신 버전의 Windows ADK를 사용하는지 확인합니다.

## <a name="manage-mac-addresses-with-removable-ethernet-adapters"></a><a href="" id="manage-mac-addresses"></a>이동식 이더넷 어댑터를 사용하여 MAC 주소 관리

네트워크를 통해 Windows 수행하는 관리자의 또 다른 고려 사항은 동일한 이더넷 어댑터를 사용하여 두 대 이상의 컴퓨터에 배포할 때 컴퓨터를 식별하는 것입니다. 배포 기술에서 사용되는 일반적인 식별자는 각 이더넷 어댑터와 연결된 MAC(미디어 액세스 제어) 주소입니다. 그러나 동일한 이더넷 어댑터를 사용하여 여러 컴퓨터에 배포하는 경우 다른 컴퓨터에서 사용할 때 이동식 어댑터의 MAC 주소를 차별화할 수 있는 방법이 아니기 때문에 MAC 주소를 검사하는 배포 기술을 사용할 수 없습니다.

MAC 주소 충돌을 피하는 가장 간단한 방법은 각 Surface 디바이스에 대해 전용 이동식 이더넷 어댑터를 제공하는 것입니다. 이렇게 하면 여러 시나리오에서 이더넷 어댑터 또는 도킹 스테이션의 추가 기능을 정기적으로 사용할 수 있습니다. 그러나 도킹 스테이션의 추가 연결 또는 무선 네트워크 지원이 모든 시나리오에 필요하지는 않습니다.

어댑터가 공유될 때 충돌을 방지하는 또 다른 잠재적 해결 방법으로는 [MDT(Microsoft Deployment Toolkit)](/mem/configmgr/mdt)를 사용하여 Surface 디바이스에 배포를 수행하는 것입니다. MDT에서는 개별 컴퓨터 식별에 MAC 주소를 사용하지 않으므로 이 제한 사항이 적용되지 않습니다. 그러나 MDT는 Windows Deployment Services를 사용하여 PXE 부팅 기능을 제공하며, 이 섹션의  나중에 설명하는 바와 같이 미리 준비된 클라이언트에 대한 제한이 적용될 수 있습니다.

배포를 위해 공유 어댑터를 사용하는 경우 영향을 받는 배포 기술에 대한 해결 방법은 다른 방법을 사용하여 고유한 시스템을 식별하는 것입니다. 이 문제의 영향을 받을 수 있는 Configuration Manager 및 WDS의 경우 해결 방법은 컴퓨터 제조업체가 컴퓨터 펌웨어에 포함된 시스템 UUID(유니버설 고유 식별자)를 사용하는 것입니다. Surface 디바이스의 경우 **디바이스 정보** 아래에 있는 컴퓨터 펌웨어에서 이 항목을 볼 수 있습니다.

**Surface 디바이스의 펌웨어에 액세스하려면**

1. Surface 디바이스가 꺼졌는지 확인합니다.
2. **볼륨 크게** 단추를 길게 누릅니다.
3. **전원** 단추를 눌렀다 놓습니다.
4. 컴퓨터 부팅이 시작되면 **볼륨 업 단추를 해제** 합니다.

WDS를 사용하여 배포할 때 배포 서버가 미리 구성되어 알려진 클라이언트에만 응답하도록 구성되는 경우 MAC 주소는 컴퓨터를 식별하는 용도로만 사용됩니다. 클라이언트를 미리 구성하는 경우 관리자는 Active Directory에서 컴퓨터 계정을 만들고 MAC 주소 또는 시스템 UUID로 해당 컴퓨터를 정의합니다. 공유 이더넷 어댑터로 인해 발생하는 ID 충돌을 방지하려면 [시스템 UUID를 사용하여 미리 구성된 클라이언트를 정의](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11))해야 합니다. 

또는 MAC 주소 또는 시스템 UUID로 정의할 필요가 없는 알 수 없는 클라이언트에 응답하도록 WDS를 구성할 수 있습니다. 배포 서버 **속성**의 [**PXE**](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11)) 응답 탭에서 모든 클라이언트 **컴퓨터에 Windows 선택합니다**.

공유 이더넷 어댑터와의 충돌은 Configuration Manager가 훨씬 가능성이 높습니다. WDS는 MAC 주소만 사용하여 개별 시스템을 정의하는 경우 Configuration Manager는 새 컴퓨터 또는 알 수 없는 컴퓨터에 배포할 때마다 MAC 주소를 사용하여 별도의 시스템을 정의합니다. 이렇게 하면 디바이스가 잘못 구성되거나, 공유 이더넷 어댑터로 두 개 이상의 시스템을 배포할 수 없게 됩니다. 이러한 상황에 대한 몇 가지 잠재적인 해결 방법에 대한 자세한 내용은 [How to Use The Same External Ethernet Adapter For Multiple SCCM OSD에 설명되어 있습니다](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374).
