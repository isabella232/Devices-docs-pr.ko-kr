---
title: Surface Laptop SE 개요
description: 이 문서에서는 교육 Surface Laptop SE 대한 개요를 제공합니다.
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
appliesto:
- Windows 11
ms.openlocfilehash: 2d16d63dda53bbfffbf5d7d9cb080c4e595217a5
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472587"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE 개요

Surface Laptop SE 저렴한 비용으로 학생들을 위한 학습을 간소화하는 관리되는 디바이스 환경을 제공합니다. 클라우드 우선 OS인 Windows 11 SE 실행되며 Microsoft Teams, Word, PowerPoint, Excel, OneNote, Edge, Minecraft: Education Edition, Flipgrid 같은 [널리 사용되는 앱이 미리 로드](#pre-installed-apps)됩니다. , 및 기타. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Windows 11 SE 시작 메뉴 보여 주는 Surface Laptop SE":::<br>
*그림 1. Windows 11 SE 시작 메뉴 보여 주는 Surface Laptop SE*

Surface Laptop SE PWA(프로그레시브 Web Apps), UWP(유니버설 Windows 플랫폼 앱) 및 [큐레이팅된 Win32 & Microsoft Store 앱 집합](#install-optional-apps)을 포함하여 학생과 교육자에게 필요한 대부분의 애플리케이션을 지원합니다. 다른 Surface 디바이스와 달리 Surface Laptop SE 사용자가 자신의 앱을 설치할 수 없습니다. 대신 IT 관리자 또는 기술 리더는 Microsoft Intune, 교육용 Microsoft Intune 및 새 [Surface Management Portal](surface-management-portal.md)을 포함하는 [Microsoft Endpoint Manager](/mem/intune/fundamentals/what-is-intune) 사용하여 [Surface Laptop SE](https://www.microsoft.com/education/intune) 디바이스를 관리합니다. 

> [!NOTE]
> 이 문서는 학교 사용자를 위해 디바이스를 배포하고 관리하는 IT 관리자 및 교육 담당자를 위한 것입니다. 일반 정보 또는 주문은 [학생용 슬림 노트북 Surface Laptop SE 참조하세요](https://www.microsoft.com/surface/business/surface-laptop-se).

## <a name="simplified-deployment-management--security"></a>간소화된 배포, 관리 & 보안

- Windows Autopilot을 사용하여 새 디바이스에 대한 낮은 터치 배포를 완료하고, 정책을 신속하게 적용하고, 앱을 설치합니다. Windows Autopilot은 많은 앱과 정책이 미리 설치되고 미리 구성된 낮은 터치 배포 및 이미징을 제공합니다. IT는 펌웨어 설정을 포함하여 디바이스 설정을 쉽게 조정할 수 있으며, 학생들이 디바이스에서 처음 전원을 켭니다.
- 디바이스가 배포되면 Microsoft Intune 학년 내내 간소화된 원격 관리를 제공하여 IT 부서에서 앱을 관리하고, 보안 및 개인 정보를 제어하고, 규정 준수 보고서를 생성할 수 있는 기능을 제공합니다.
- 노트북을 닫을 때 뚜껑 잠금으로 운영 체제를 잠그고 통합 켄싱턴 Nano 보안 슬롯을 사용하여 물리적 액세스를 제어합니다™.
- 새로 디자인된 노출되지 않은 힌지, 플라스틱 섀시 및 베젤로 나가는 화면을 둘러싼 플라스틱 테두리는 학생 사용의 요구와 요구를 더 잘 충족하기 위해 추가 내구성을 제공합니다.
- Intune 및 DFCI는 펌웨어 계층에 대한 보안 디바이스 업데이트 및 관리를 지원합니다. IT 관리자는 마이크, USB 포트, 카메라 및 Bluetooth 같은 하드웨어 요소를 제어하고 주변 장치에 대한 전원을 제거할 수 있습니다. 스캔 가능한 고유한 Surface 패키징을 사용하면 디바이스를 쉽게 식별할 수 있으며, 다시 등록할 때 디바이스 ID 번호가 동일하게 유지됩니다.

### <a name="surface-management-portal"></a>Surface 관리 포털

클라우드 관리를 위해 Surface Laptop SE 등록하고 사용자가 처음으로 로그인하면 이러한 Surface 디바이스의 정보가 [자동으로 Surface 관리 포털](surface-management-portal.md)로 전달되어 Surface 관련 디바이스 관리 활동을 위한 단일 창이 제공됩니다. 디바이스 규정 준수, 지원 활동 및 보증 범위에 대한 인사이트를 얻을 수 있습니다. 각 디바이스의 상태( 아직 보증 중이거나 곧 만료됨) 및 활성 지원 요청의 상태를 빠르게 확인합니다.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Surface Laptop SE 대한 보증 적용 범위를 보여 주는 Surface Management Portal":::
*그림 2. Surface Laptop SE 대한 보증 적용 범위를 보여 주는 Surface Management Portal*

## <a name="common-admin-scenarios"></a>일반적인 관리자 시나리오

| 시나리오                                                            | 설명                                                                                                                                                                                                                                                                                                                          | 세부 정보                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot을 사용하여 Surface Laptop SE 디바이스 원격 구성 | Windows Autopilot은 많은 앱과 정책이 미리 설치되고 미리 구성된 낮은 터치 배포 및 이미징을 제공합니다. IT는 펌웨어 설정을 포함하여 디바이스 설정을 쉽게 조정할 수 있으며, 학생들이 디바이스에서 처음 전원을 켭니다.                 |[Windows Autopilot을 사용하여 교육용 Intune 설정](/intune-education/windows-autopilot-setup)<br><br>[디바이스를 등록하려면 어떻게 해야 하나요?](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| 교육용 Intune 통해 업데이트 배포                             | IT 관리자는 Microsoft Intune 사용하여 일년 내내 학교 전체의 Surface Laptop SE 디바이스에 OS 및 앱 업데이트를 푸시할 수 있습니다. 필요한 경우 개별 디바이스에서 카메라 또는 Bluetooth 같은 하드웨어 요소를 사용하지 않도록 설정하거나 학생이 기술적인 문제가 발생하는 경우 특정 디바이스를 다시 설정할 수 있습니다. |[Windows 11 SE 실행하는 디바이스 관리](/intune-education/windows-11-se-overview)<br><br>[Microsoft Education 문서 및 리소스](/microsoft-365/education/)<br><br>[교육용 Intune 시작](/microsoft-365/education/deploy/intune-for-education)<br><br>[Intune for Education을 사용하여 그룹, 앱 및 설정 관리](/microsoft-365/education/deploy/use-intune-for-education) |
| 필요에 따라 디바이스 교체                                           | 학생이 화면을 깨뜨리거나 디바이스를 손상시키는 경우 IT 관리자는 예비 디바이스를 신속하게 배포하여 학생의 클라우드 ID를 새 디바이스로 전송할 수 있습니다.                                                                                                  |[교육용 Intune 원격 디바이스 작업](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Intune 통해 새 앱 배포                                          | 교사가 새 앱을 요청하는 경우 IT 관리자는 Intune 사용하여 모든 학생 디바이스에 원격으로 설치할 수 있습니다.                                                                                                                                                                                                                            |[모든 사용자용으로 앱 설치](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Intune 통해 디바이스 다시 설정                                            | 학생이 학년 말에 Surface Laptop SE 디바이스를 켜면 IT 관리자는 Intune 사용하여 다음 학년 초에 필요한 다음 수업에 필요한 디바이스를 다시 설정할 수 있습니다.                                                                                                           |[Autopilot 재설정을 사용하여 교육용 Intune 디바이스 다시 구성](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>사전 설치된 앱

Surface LaptopSE 다음과 같은 사전 설치된 앱이 제공됩니다.  

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
- 조각화 도구
- 스티커 메모
- Surface 앱
- Surface 진단 도구 키트
- 팁
- 음성 녹음기
- 날씨
- 워드

## <a name="install-optional-apps"></a>선택적 앱 설치

IT 관리자는 Intune 통해 Chrome 또는 Zoom과 같은 [추가 앱을](/education/windows/windows-11-se-overview#available-apps) 설치할 수 있습니다. Surface Laptop SE 대한 앱 스토어가 없습니다. 앱 배포를 완료하려면 다음 지침을 참조하세요. 

- [앱 배포](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>복구 기능

Surface Laptop SE Surface Laptop SE 핵심 구성 요소를 신속하게 대체하여 숙련된 기술자가 로컬에서 디바이스를 서비스할 수 있도록 설계되었습니다.

- 모듈 표시  
- 키보드 & 버킷
- Speaker & Wi-Fi 모듈
- 배터리
- 피트

학교는 [Surface 서비스 가이드](https://www.microsoft.com/download/100440)에서 제공하는 Microsoft 제공 "Surface Laptop SE 서비스 가이드"에 따라 공인 서비스 공급자 또는 숙련된 기술자를 사용하여 현장의 장치를 복구할 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [Surface Laptop SE 복구 비디오](https://youtu.be/fVjjSqfp75g)
- [Surface 장치에 대한 주요 지원 솔루션](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop SE 기술 사양

| 기능                     | 설명                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **차원**              | - 11.17" x 7.6" x 0.70"(283.70mm x 193.05mm x 17.85mm)                                                                                                                                                |
| ****<sup>Storage 1</sup>     | - 온보드, 포함된 멀티미디어 카드(eMMC) 64GB 또는 128GB                                                                                                                                                 |
| **Display**                 | - 화면: 11.6" TFT Liquid Crystal Display 모듈<br>- 디스플레이 해상도: 1366 x 768(135PPI)<br>- 가로 세로 비율: 16:9<br>- 대비 비율: 800:1(일반)<br>- 광도: 220니트<br>- 덮개 유리 없음 |
| **배터리**                 | - 35Wh(명목), 33.9Wh(분)<br>- 배터리 수명 <sup>16시간 2</sup>                                                                                                                                              |
| **메모리**                  | - 4GB 또는 8GB DDR4(2400MHz 분)                                                                                                                                                                          |
| **CPU/그래픽**          | - Intel® Celeron® Processor N4020 / Intel® UHD Graphics 600<br>- 인텔® 셀러론® 프로세서 N4120 / 인텔® UHD 그래픽 600                                                                                |
| **연결**             | - 1 x USB-A<br>- 1 x USB-C<br>- 배럴 형식 DC 커넥터 1개<br>- 1 x 3.5mm 헤드폰/마이크 잭                                                                                                           |
| **보안**                | - 모든 구성에서 펌웨어 TPM(상용)<br>- Nano 보안 잠금 슬롯                                                                                                                        |
| **카메라, 비디오, & 오디오** | - 최대 720p 30fps 비디오의 1MP 전면 카메라<br>- 2W 스테레오 스피커<br>- 단일 디지털 마이크                                                                                              |
| **소프트웨어**                | - Windows 11 SE<br>- 교육<sup>용 Microsoft 365 3</sup>                                                                                                                                                         |
| **무선**                | - Wi-Fi: 802.11ac(2x2)<br>- Bluetooth 무선 5.0 LE                                                                                                                                                    |
| **센서**                 | - 홀 효과 센서 1개                                                                                                                                                                                  |
| **외부**                | - 대/소문자: 모든 플라스틱 본문 무매수<br>- 색: 빙하<br>- 물리적 단추: 키보드의 전원 및 볼륨<br>- 힌지: 135도 열린 각도                                                          |
| **무게**                  | - 2.45lb. (1,111.3 g)                                                                                                                                                                                    |
| **키보드 및 트랙 패드**   | - 백라이트가 없는 11.6인치 표준 Windows 키보드<br>- 표준 부동 정밀도 트랙 패드 없음                                                                                                      |
| **상승 기류**                | - 수동 냉각                                                                                                                                                                                        |
| **전원 공급 장치**            | - DC 배럴 충전기를 포함한 45W의 기본 제공                                                                                                                                                                      |
| **상자 안**              | - Surface 디바이스<br>- 전원 공급 장치<br>- 빠른 시작 가이드<br>- 안전 및 보증 문서                                                                                                              |
| **보증**<sup> 4</sup>    | - 1년 제한 하드웨어 보증                                                                                                                                                                      |

## <a name="references"></a>참조

1. 시스템 소프트웨어 및 업데이트는 상당한 스토리지 공간을 사용합니다. 사용 가능한 스토리지는 시스템 소프트웨어 및 업데이트 및 앱 사용에 따라 변경될 수 있습니다. 1GB = 10억 바이트. 1TB = 1,000GB. 자세한 내용은 [Surface Storage](https://support.microsoft.com/help/4023513/surface-surface-storage?) 참조하세요.
2. 배터리 수명은 사용량, 네트워크 및 기능 구성, 신호 강도, 설정 및 기타 요인에 따라 크게 달라집니다. 자세한 내용은 [Surface 배터리 테스트 및 예상 성능을](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) 참조하세요.
3. Microsoft 365 또는 Office 365 라이선스를 별도로 판매해야 합니다. [Microsoft 365 교육 계획을 비교합니다](https://aka.ms/EDU-Plan-Comparison).
4. Microsoft의 제한된 보증은 소비자 법률 권한에 추가됩니다.


## <a name="learn-more"></a>세부 정보

- [주문 Surface Laptop SE](https://www.microsoft.com/surface/business/surface-laptop-se)
- [교육용 Surface Laptop SE 소개](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [교육용 Windows 11 SE](/education/windows/windows-11-se-overview)
- [Windows 11 SE 실행하는 디바이스 관리](/intune-education/windows-11-se-overview)
- [Windows Autopilot을 사용하여 교육용 Intune 설정](/intune-education/windows-autopilot-setup)
- [Microsoft Education 문서 및 리소스](/microsoft-365/education/)
- [웹용 Outlook](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
- [교육용 하드웨어 & 소프트웨어 솔루션](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/a-purpose-built-hardware-amp-software-solution-for-education/ba-p/1419013)