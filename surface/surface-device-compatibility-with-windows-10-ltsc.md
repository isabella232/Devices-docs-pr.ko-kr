---
title: Surface 서비스 채널과 Windows 10 Long-Term Surface 장치 호환성(Surface)
description: LTSB 버전에서 실행되는 Surface 디바이스의 호환성 및 Windows 10 Enterprise 대해 확인합니다.
keywords: ltsb, 업데이트, 표면 서비스 옵션
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 07/21/2021
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: d8c1e0996b02ac385b587661f3894ce30e406d9a
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448921"
---
# <a name="surface-device-compatibility-with-windows-10-long-term-servicing-channel-ltsc"></a>LTSC(Windows 10 Long-Term 채널)와 Surface 장치 호환성

Surface 디바이스는 생산성 및 일반용 시나리오에서 동급 최고의 환경을 제공하도록 디자인되었습니다. 정기적인 업데이트를 통해 Surface 디바이스는 혁신을 가져와 새로운 기능 업데이트로 Windows 10 있습니다. 기능 업데이트는 SAC(Windows 10 Pro 채널)를 통해 Windows 10 Enterprise 업데이트를 받는 Semi-Annual 버전에서만 사용할 수 있습니다.

이전의 CB(현재 분기) 또는 CBB(비즈니스용 현재 분기) 서비스 옵션인 SAC 서비스 옵션과 달리, LTSC(Long-Term 서비스 채널) 옵션은 Windows 10 없습니다. LTSC 서비스 옵션을 사용하려면 Windows 10 Enterprise LTSC(Windows 10 Enterprise LTSB(장기 서비스 분기)라고 하는 별도의 Windows 10 Enterprise LTSC 에디션을 설치해야 합니다.

>[!TIP]
>LTSC에 대한 최신 정보는 FAQ: [다음 Windows 10 LTSC](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/the-next-windows-10-long-term-servicing-channel-ltsc-release/ba-p/2147232)(장기 서비스 채널) 릴리스를 참조하세요.

 Windows 10 Enterprise LTSC 버전은 확장된 서비스 모델을 제공하는 것 외에도 여러 가지 Windows 구성 요소를 제거할 수 있는 환경을 제공합니다. LTSC가 영향을 미치는 핵심 Surface 환경은 다음과 같습니다.

* Windows 기능을 포함하여 다음과 같은 기능을 업데이트합니다.

  * Windows 10 버전 1607에서 제공된 Direct Ink 및 팜 거부 기능 개선(1주년 업데이트라고도 지칭)
  * 크리에이터스 업데이트라고도 하는 Windows 10 버전 1703에서 제공되는 높은 DPI 응용 프로그램에 대한 지원이 개선되었습니다.

* Surface 앱에서 제공하는 압력 민감도 설정

* Windows Ink 작업 영역

* Microsoft Edge, OneNote, 일정 및 카메라를 비롯한 터치 최적화된 주요 인박스 응용 프로그램

Surface 디바이스에서 Windows 10 Enterprise LTSC 환경을 사용하면 최종 사용자 환경이 최적화되어 있으며 사용자가 고급 최신 사용자 환경을 원하고 기대하는 환경에서는 이 환경을 사용하지 않도록 해야 합니다.

LTSC 서비스 옵션은 주요 특성이 절대 변경되지 않는 기능의 장치 유형 및 시나리오를 위해 디자인되었습니다. 예로는 전력 제조 또는 의료 장비 시스템 또는 ATM 또는 공항 티켓 매기기 시스템과 같은 키오스크의 포함 시스템이 있습니다.

>[!NOTE]
>LTSC를 비롯한 Windows 분기에 대한 일반적인 정보는 Overview [of Windows as a Service](/windows/deployment/update/waas-overview).

일반적으로 다음 기준을 충족하는 장치는 일반용 장치로 간주되어 Windows 10 Pro 또는 Windows 10 Enterprise 채널 서비스 옵션을 사용하여 Semi-Annual 페어링해야 합니다.

* 생산성 소프트웨어를 실행하는 장치(예: Microsoft Office

* 응용 프로그램을 사용하는 Microsoft Store 장치

* 일반 인터넷 검색에 사용되는 장치(예: 리서치 또는 소셜 미디어 액세스)

Surface 디바이스에서 Windows 10 Enterprise LTSC 에디션을 사용하기 전에 다음 제한 사항을 고려하십시오.

* 드라이버 및 펌웨어 업데이트는 LTSC의 릴리스에 대해 명시적으로 Windows 10 Enterprise 않습니다.

* 문제가 발생하면 Microsoft 지원에서 문제 해결 지원을 제공합니다. 그러나 Windows LTSC의 서비스 특성으로 인해 문제 해결을 위해서는 SAC 서비스 옵션을 사용하여 장치를 최신 버전의 Windows 10 Enterprise LTSC 또는 Windows 10 Pro Enterprise 버전으로 업그레이드해야 할 수 있습니다.

* Surface 디바이스 교체(예: 무상수리로 교체된 디바이스)에는 업데이트된 장치 드라이버 및 펌웨어가 필요한 하드웨어 구성 요소의 미묘한 변형이 포함될 수 있습니다. 이러한 업데이트와의 호환성을 위해서는 SAC 서비스 옵션을 사용하여 LTSC 또는 Windows 10 Enterprise Windows 10 Pro Enterprise 버전을 설치해야 할 수 있습니다.

>[!NOTE]
>특정 버전의 Windows 10 Enterprise LTSC를 표준화하는 조직은 이후 버전의 버전으로 업데이트하지 않고는 Surface Pro 8, Surface Pro X 또는 Surface Laptop 4와 같은 새로운 Surface 하드웨어를 채택할 수 없습니다. Windows 10 Enterprise LTSC 또는 Windows 10 Pro Enterprise. 자세한 내용은 수명 [주기 FAQ -](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--) Windows.

LTSC Windows 10 Enterprise 실행되는 Surface 디바이스는 새로운 기능을 받지 않습니다. 대부분의 경우 고객은 Surface 하드웨어의 사용 가능성과 기능을 개선하기 위해 이러한 기능을 요청합니다. 예를 들어 버전 1703의 높은 DPI 응용 Windows 10 개선되었습니다. LTSC 구성에서 Surface 장치를 사용하는 고객은 새 Windows 10 Enterprise LTSC 릴리스로 업데이트하거나 SAC 서비스 옵션을 지원하여 Windows 10 버전으로 업그레이드할 때까지 개선된 기능을 볼 수 없습니다.

디바이스는 Windows 10 Enterprise LTSC에서 최신 버전의 Windows 10 Enterprise SAC 서비스 옵션을 지원하여 업그레이드 설치를 수행하여 사용자 데이터를 잃지 않고도 변경할 수 있습니다. MDT(Microsoft Deployment Toolkit)에서 사용할 수 있는 업그레이드 작업 순서 템플릿을 사용하여 여러 장치에서 업그레이드 설치를 수행할 수도 Microsoft Endpoint Configuration Manager. 자세한 내용은 [Microsoft Deployment Windows 10 Surface 장치 업그레이드를 Toolkit](upgrade-surface-devices-to-windows-10-with-mdt.md).
