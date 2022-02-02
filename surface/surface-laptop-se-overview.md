---
title: Surface Laptop SE 개요
description: 이 문서에서는 교육용 Surface Laptop SE 개요를 제공합니다.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/11/2022
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 2496c50db10454674f80aec03734849bacf63f38
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338671"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE 개요

Surface Laptop SE 사용하면 저렴한 비용으로 학생을 위한 학습을 간소화하는 관리되는 디바이스 환경을 제공합니다. 클라우드 우선 Windows 11 SE 운영 체제를 실행하며, Microsoft Teams, Word, PowerPoint[](#pre-installed-apps), Excel, OneNote, Edge, Minecraft: Education Edition, Flipgrid 등. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop SE 보여 Windows 11 SE 시작 메뉴":::<br>
*그림 1. Surface Laptop SE 보여 Windows 11 SE 시작 메뉴*

Surface Laptop SE PW(Progressive Web Apps), UWP(유니버설 Windows 플랫폼 앱) 및 큐레이터[된 Win32](#install-optional-apps) 앱 집합을 포함하여 학생과 강사에게 필요한 대부분의 응용 프로그램을 & Microsoft Store 지원합니다. 다른 Surface 디바이스와 달리 Surface Laptop SE 앱을 설치할 수 없습니다. 대신 IT 관리자 또는 기술 잠재 고객들은 Microsoft Endpoint Manager, 교육용 Microsoft Intune Microsoft Intune 새로운 Surface 관리 포털을 포함하는 Surface Laptop SE 디바이스를 [](/mem/intune/fundamentals/what-is-intune)[관리합니다](surface-management-portal.md). [](https://www.microsoft.com/education/intune) 

> [!NOTE]
> 이 문서는 학교 사용자를 위한 디바이스를 배포하고 관리하는 IT 관리자 및 교육 담당자를 위한 것입니다. 일반 정보 또는 주문은 학생용 [랩톱 Surface Laptop SE 랩톱을 참조하세요](https://www.microsoft.com/surface/business/surface-laptop-se).

## <a name="simplified-deployment-management--security"></a>간소화된 배포, 관리 & 보안

- Autopilot을 사용하여 새 디바이스에 대한 Windows 배포를 완료하고 정책을 신속하게 적용하고 앱을 설치합니다. Windows Autopilot은 많은 앱 및 정책이 미리 설치 및 미리 구성된 로우 터치 배포 및 이미징을 제공합니다. IT는 펌웨어 설정을 비롯한 장치 설정을 쉽게 조정하고 학생이 디바이스에서 처음 전원을  필요할 때 모든 준비가 완료될 수 있도록 필요한 앱을 설치할 수 있습니다.
- 디바이스가 배포되면 Microsoft Intune 간소화된 원격 관리를 통해 IT가 앱을 관리하고, 보안 및 개인 정보를 제어하고, 규정 준수 보고서를 생성할 수 있습니다.
- 랩톱을 닫을 때 lid-lock으로 운영 체제를 잠그고 통합된 Kensington Nano 보안 슬롯을 사용하여 물리적 액세스를 제어합니다™.
- 새로 디자인된 노출되지 않는 힌지, 구부러진 섀시 및 화면 주변에 있는 테두리가 베지셀로 나갑니다. 이 테두리는 학생의 요구와 요구 사항을 보다 잘 충족할 수 있는 추가 내구성을 제공합니다.
- Intune 및 DFCI는 펌웨어 계층에 대한 보안 장치 업데이트 및 관리를 지원합니다. IT 관리자는 마이크, USB 포트, 카메라 및 장치와 같은 하드웨어 요소를 제어하고 Bluetooth 주변 장치로 전원을 제거할 수 있습니다. 스캔 가능한 고유한 Surface 패키징을 사용하면 장치를 쉽게 식별할 수 있습니다. 장치 ID 번호는 다시 등록할 때와 동일하게 유지됩니다.

### <a name="surface-management-portal"></a>Surface 관리 포털

클라우드 Surface Laptop SE 등록하고 사용자가 처음으로 로그인하면 이러한 Surface 디바이스의 정보가 [Surface 관리](surface-management-portal.md) 포털로 자동으로 이동하여 Surface 관련 장치 관리 활동을 위한 단일 창을 제공합니다. 장치 준수, 지원 활동 및 보증 범위에 대한 인사이트를 얻을 수 있습니다. 보증 또는 곧 만료되는 각 장치의 상태와 활성 지원 요청의 상태를 빠르게 확인합니다.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Surface Management Portal에 대한 보증 범위를 Surface Laptop SE":::
*그림 2. Surface Management Portal에 대한 보증 범위를 Surface Laptop SE*

## <a name="common-admin-scenarios"></a>일반적인 관리자 시나리오

| 시나리오                                                            | 설명                                                                                                                                                                                                                                                                                                                          | 세부 정보                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Autopilot을 사용하여 Surface Laptop SE 원격으로 Windows 구성 | Windows Autopilot은 많은 앱 및 정책을 미리 설치 및 미리 구성하여 로우 터치 배포 및 이미징을 제공합니다. IT는 펌웨어 설정을 비롯한 장치 설정을 쉽게 조정하고 학생이 디바이스에서 처음 전원을  필요할 때 모든 준비가 완료될 수 있도록 필요한 앱을 설치할 수 있습니다.                 |[Autopilot을 통해 Intune for Education Windows 설정](/intune-education/windows-autopilot-setup)<br><br>[장치를 등록하는 방법](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| Intune for Education을 통해 업데이트 배포                             | IT 관리자는 1년 Microsoft Intune 사용하여 OS 및 앱 업데이트를 Surface Laptop SE 장치로 푸시할 수 있습니다. 필요한 경우 카메라 또는 디바이스와 같은 하드웨어 요소를 사용하지 않도록 설정하거나 Bluetooth 기술 문제가 발생하는 경우 특정 장치를 다시 설정할 수 있습니다. |[실행 중인 Windows 11 SE](/intune-education/windows-11-se-overview)<br><br>[Microsoft Education 문서 및 리소스](/microsoft-365/education/)<br><br>[Intune for Education 시작](/microsoft-365/education/deploy/intune-for-education)<br><br>[Intune for Education을 사용하여 그룹, 앱 및 설정 관리](/microsoft-365/education/deploy/use-intune-for-education) |
| 필요한 경우 장치 바꾸기                                           | 학생이 화면을 크랙하거나 장치를 손상하면 IT 관리자는 예비 장치를 신속하게 배포하여 학생의 클라우드 ID를 새 디바이스로 전송할 수 있습니다.                                                                                                  |[Intune for Education의 원격 장치 작업](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Intune을 통해 새 앱 배포                                          | 교사가 새 앱을 요청하는 경우 IT 관리자는 Intune을 사용하여 모든 학생 디바이스에 원격으로 설치할 수 있습니다.                                                                                                                                                                                                                            |[모든 사용자용으로 앱 설치](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Intune을 통해 장치 초기화                                            | 학생이 학년 말에 Surface Laptop SE 디바이스를 켜면 IT 관리자는 Intune을 사용하여 다음 학년 초에 필요한 다음 수업용 디바이스를 초기화할 수 있습니다.                                                                                                           |[Autopilot Reset을 사용하여 Intune for Education으로 장치 다시 구성](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>미리 설치된 앱

Surface LaptopSE 다음과 같은 미리 설치된 앱과 함께 사용할 수 있습니다.  

- Microsoft Excel
- Flipgrid
- Groove 음악
- 지도
- Microsoft Edge
- Microsoft 뉴스
- Microsoft Teams
- Microsoft To Do
- Microsoft Whiteboard
- Minecraft Education Edition
- 메모장
- Microsoft Office
- OneDrive
- OneNote
- 웹용 Outlook
- 그림판
- 사진
- PowerPoint
- 스니핑 도구
- 스티커 메모
- Surface 앱
- Surface 진단 도구 키트
- 팁
- 음성 녹음기
- 날씨
- 워드

## <a name="install-optional-apps"></a>선택적 앱 설치

IT 관리자는 Intune을 [통해](/education/windows/windows-11-se-overview#available-apps) Chrome 또는 Zoom과 같은 추가 앱을 설치할 수 있습니다. 앱 스토어가 없는지 Surface Laptop SE. 앱 배포를 완료하기 위해 다음 지침을 참조하세요. 

- [앱 배포](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>복구 가능성

Surface Laptop SE Surface Laptop SE 기술자가 핵심 구성 요소를 신속하게 교체하여 장치를 로컬로 서비스할 수 있도록 디자인되었습니다.

- 디스플레이 모듈  
- 키보드 & 버킷
- 스피커 & Wi-Fi 모듈
- 배터리
- 피트

학교는 Surface 서비스 가이드에서 제공되는 Microsoft에서 제공하는 "Surface Laptop SE 서비스 가이드"에 따라 공인 서비스 공급자 또는 숙련된 기술자를 사용하여 현장에서 장치를 복구할 [수 있습니다](https://www.microsoft.com/download/100440).

자세한 내용은 다음을 참조합니다.

- [Surface Laptop SE 복구 비디오](https://youtu.be/fVjjSqfp75g)
- [Surface 장치에 대한 주요 지원 솔루션](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop SE 기술 사양

| 기능                     | 설명                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **차원**              | - 11.17" x 7.6" x 0.70" (283.70 x 193.05 x 17.85mm)                                                                                                                                                |
| ****<sup>Storage 1</sup>     | - On board, Embedded Multimedia Card (eMMC) 64GB or 128GB                                                                                                                                                 |
| **Display**                 | - 화면: 11.6인치 TFT 원시 디스플레이 모듈<br>- 디스플레이 해상도: 1366 x 768(135 PPI)<br>- 화면 비율: 16:9<br>- 명암비: 800:1(일반)<br>- 광도: 220 nits<br>- 커버 유리 없음 |
| **배터리**                 | - 35Wh(공명), 33.9Wh(최소)<br>- 16시간의 배터리 사용 <sup>시간 2</sup>                                                                                                                                              |
| **메모리**                  | - 4GB 또는 8GB DDR4(2400MHz 분)                                                                                                                                                                          |
| **CPU/그래픽**          | - Intel® Celeron® Processor N4020/Intel® UHD Graphics 600<br>- Intel® Celeron® Processor N4120/Intel® UHD Graphics 600                                                                                |
| **연결**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x 통 유형 DC 커넥터<br>- 1 x 3.5mm Headphone/Mic Jack                                                                                                           |
| **Security**                | - 모든 구성의 펌웨어 TPM(상업용)<br>- Nano 보안 잠금 슬롯                                                                                                                        |
| **카메라, 비디오, & 오디오** | - 최대 720p 30fps 비디오가 있는 1MP 전면 카메라<br>- 2W 스테레오 스피커<br>- 단일 디지털 마이크                                                                                              |
| **소프트웨어**                | - Windows 11 SE<br>- Microsoft 365 for Education3<sup></sup>                                                                                                                                                         |
| **무선**                | - Wi-Fi: 802.11ac(2x2)<br>- Bluetooth 무선 5.0 LE                                                                                                                                                    |
| **센서**                 | - 1 x 홀 효과 센서                                                                                                                                                                                  |
| **외부**                | - 대/소문자: 모든 본체가 페인트되지 않은 경우<br>- 색: 빙하<br>- 물리적 단추: 키보드의 전원 및 볼륨<br>- 힌지: 135도 열린 각도                                                          |
| **무게**                  | - 2.45lb(1,111.3g)                                                                                                                                                                                    |
| **키보드 및 트랙 패드**   | - 11.6인치의 표준 Windows 키보드(백라이트가 없는 경우)<br>- 표준 부동 정밀도 트랙 패드 없음                                                                                                      |
| **열**                | - 수동 냉각                                                                                                                                                                                        |
| **전원 공급 장치**            | - 인박스, DC 통 충전기 45W                                                                                                                                                                      |
| **상자 안**              | - Surface 디바이스<br>- 전원 공급 장치<br>- 빠른 시작 가이드<br>- 안전 및 보증 문서                                                                                                              |
| **보증**<sup> 4</sup>    | - 1년 제한 하드웨어 보증                                                                                                                                                                      |

## <a name="references"></a>참조

1. 시스템 소프트웨어 및 업데이트는 상당한 저장소 공간을 사용 합니다. 사용 가능한 저장소는 시스템 소프트웨어 및 업데이트 및 앱 사용 현황에 따라 변경될 수 있습니다. 1GB = 10억바이트. 1 TB = 1,000GB. 자세한 [Storage Surface](https://support.microsoft.com/help/4023513/surface-surface-storage?) 2013을 참조합니다.
2. 배터리 사용 시간은 사용, 네트워크 및 기능 구성, 신호 강도, 설정 및 기타 요인에 따라 크게 다릅니다. 자세한 [내용은 Surface 배터리 테스트 및 예상 성능을](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) 참조합니다.
3. 별도로 판매되는 Microsoft 365 Office 365 라이선스가 필요합니다. [교육 Microsoft 365 비교합니다](https://aka.ms/EDU-Plan-Comparison).
4. Microsoft의 제한된 보증은 소비자 법률 권리 외에 추가됩니다.


## <a name="learn-more"></a>세부 정보

- [주문 Surface Laptop SE](https://www.microsoft.com/surface/business/surface-laptop-se)
- [교육용 Surface Laptop SE 소개](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [교육용 Windows 11 SE](/education/windows/windows-11-se-overview)
- [실행 중인 Windows 11 SE](/intune-education/windows-11-se-overview)
- [Autopilot을 통해 Intune for Education Windows 설정](/intune-education/windows-autopilot-setup)
- [Microsoft Education 문서 및 리소스](/microsoft-365/education/)
- [웹용 Outlook](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
