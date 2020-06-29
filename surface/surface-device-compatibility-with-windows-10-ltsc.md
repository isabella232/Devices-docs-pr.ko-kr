---
title: Windows 10 장기간 서비스 채널 (Surface)과의 surface 디바이스 호환성
description: Windows 10 Enterprise LTSB edition을 실행 하는 Surface 디바이스의 호환성 및 제한 사항에 대해 알아봅니다.
keywords: ltsb, update, surface 서비스 옵션
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: db3dfd57c3b79fcec507ffd146483915490801b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834292"
---
# Windows 10 장기 서비스 채널 (LTSC)과의 Surface 디바이스 호환성

Surface 디바이스는 생산성 및 범용 시나리오에서 최고의 경험을 제공 하도록 디자인 되었습니다. 일반 업데이트는 Surface 장치를 사용 하 여 새로운 혁신을 시작 하 고 Windows 10 기능 업데이트에서 제공 하는 새로운 기능을 개선 합니다. 기능 업데이트는 Windows 10 Pro 또는 Windows 10 Enterprise edition 에서만 사용할 수 있으며, SAC (반기 채널)를 통해 연속적인 업데이트를 받습니다.

이전에는 현재 분기 (CB) 또는 현재 비즈니스 (비즈니스용 분기) 서비스 옵션 이라고 하는 SAC 서비스 옵션과 대조적으로 Windows 10 설정의 LTSC (장기 서비스 채널) 옵션을 선택할 수 없습니다. LTSC 서비스 옵션을 사용 하려면 windows 10 enterprise LTSC 이라고 하는 별도의 Windows 10 Enterprise (이전의 Windows 10 enterprise LTSB (장기 서비스 분기)를 설치 해야 합니다. 확장 서비스 모델을 제공 하는 것 외에도 Windows 10 Enterprise LTSC edition은 여러 Windows 구성 요소를 제거 하는 환경을 제공 합니다. LTSC의 영향을 받는 핵심 표면 환경에는 다음이 포함 됩니다.

* 다음과 같은 향상 된 기능을 포함 하는 Windows 기능 업데이트

  *  Windows 10 버전 1607에서 제공 하는 직접적인 잉크 및 팜 거부에 대 한 개선 사항 (기념일 업데이트가 라고도 함)
  *  Windows 10 버전 1703 (작성자 업데이트 라고도 함)에서 제공 하는 high DPI 응용 프로그램에 대 한 지원 향상

* Surface 앱에서 제공 하는 압력 민감도 설정

* Windows Ink 작업 영역

* Microsoft Edge, OneNote, 일정, 카메라를 포함 하는 키 터치에 최적화 된 응용 프로그램

Surface 장치에서 Windows 10 Enterprise LTSC 환경을 사용 하는 경우 사용자가 최적화 된 최종 사용자 환경을 제공 하 게 되며,이를 사용 하는 것이 좋습니다.

LTSC 서비스 옵션은 주요 특성이 변경 되지 않는 기능 또는 기능에 대 한 디바이스 유형 및 시나리오에 맞게 설계 되었습니다. 예를 들면 power manufacturing 또는 의료 장비 시스템, Atm 또는 공항 티켓 시스템 등의 임베디드 시스템 등이 포함 됩니다.

>[!NOTE]
>LTSC를 포함 하 여 Windows 서비스 분기에 대 한 일반적인 내용은 [windows 서비스](https://technet.microsoft.com/itpro/windows/update/waas-overview#long-term-servicing-branch)에 대 한 개요를 참조 하세요.

일반적으로 다음 조건을 충족 하는 디바이스는 범용 장치로 간주 되며 반기 채널 서비스 옵션을 사용 하 여 Windows 10 Pro 또는 Windows 10 Enterprise와 쌍을 이루어야 합니다.

* Microsoft Office와 같은 생산성 소프트웨어를 실행 하는 장치

* Microsoft Store 응용 프로그램을 사용 하는 장치

* 일반 인터넷 검색에 사용 되는 장치 (예: 소셜 미디어에 대 한 연구 또는 액세스)

Surface 장치에서 Windows 10 Enterprise LTSC edition을 사용 하도록 선택 하기 전에 다음 제한을 고려해 야 합니다.

* 드라이버 및 펌웨어 업데이트는 Windows 10 Enterprise LTSC의 릴리스에 대해 명시적으로 테스트 되지 않습니다.

* 문제가 발생 하면 Microsoft 지원에서 문제 해결 지원을 제공 합니다. 그러나 문제 해결을 위해 Windows LTSC의 서비스 특성 때문에 장치를 최신 버전의 Windows 10 Enterprise LTSC 또는 SAC 서비스 옵션을 사용 하 여 Windows 10 Pro 또는 Enterprise로 업그레이드 해야 할 수 있습니다.

* Surface 디바이스 대체 (예: 무상 수리에 따라 바뀌는 장치)에는 업데이트 된 장치 드라이버 및 펌웨어가 필요한 하드웨어 구성 요소의 미세한 변형이 포함 될 수 있습니다. 이러한 업데이트와 호환 되는 경우 SAC 서비스 옵션을 사용 하 여 최신 버전의 Windows 10 Enterprise LTSC 또는 Windows 10 Pro 또는 Enterprise를 설치 해야 할 수 있습니다.

>[!NOTE]
>특정 버전의 Windows 10 Enterprise LTSC를 표준화 하는 조직은 Surface Pro 7, Surface Pro X 또는 Surface 랩톱 3과 같은 새 세대의 환경 하드웨어를 채택 하지 못할 수 있으며, 이후 버전의 Windows 10 Enterprise LTSC 또는 Windows 10 Pro 또는 Enterprise로도 업데이트 하지 않아도 됩니다. 자세한 내용은 windows **10 LTSBs 지원** 되는 방법에 대 한 자세한 내용은 [수명 주기 정책의 windows 제품](https://support.microsoft.com/help/18581/lifecycle-policy-faq-windows-products#b4)섹션 **에 있는 최신 프로세서 및 칩셋 관련** FAQ를 참조 하세요.

Windows 10 Enterprise LTSC edition을 실행 하는 Surface 디바이스는 새로운 기능을 수신 하지 않습니다. 대부분의 경우 이러한 기능은 Surface 하드웨어의 유용성 및 기능을 개선 하기 위해 고객이 요청 합니다. 예를 들어 Windows 10의 버전 1703에서 높은 DPI 응용 프로그램에 대 한 새로운 개선 사항이 적용 되었습니다. LTSC 구성에서 Surface 디바이스를 사용 하는 고객은 새 Windows 10 Enterprise LTSC 릴리스로 업데이트 하거나, SAC 서비스 옵션을 지 원하는 Windows 10 버전으로 업그레이드 하기 전까지 향상 된 기능을 볼 수 없습니다.

장치는 Windows 10 Enterprise LTSC에서 최신 버전의 Windows 10 Enterprise로 변경 될 수 있으며,이 경우 SAC 서비스 옵션을 지원 하 고, 업그레이드 설치를 수행 하 여 사용자 데이터를 잃지 않습니다. MDT (Microsoft 배포 도구 키트) 및 Microsoft 끝점 구성 관리자에서 사용할 수 있는 업그레이드 작업 순서 템플릿을 활용 하 여 여러 장치에서 업그레이드 설치를 수행할 수도 있습니다. 자세한 내용은 [Microsoft 배포 도구 키트를 사용 하 여 Surface 장치를 Windows 10으로 업그레이드](https://technet.microsoft.com/itpro/surface/upgrade-surface-devices-to-windows-10-with-mdt)를 참조 하세요.
