---
title: Surface Book 3 GPU 기술 개요
description: 이 문서에서는 3개 모델의 GPU 기능에 대한 기술 Surface Book 제공합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 5/06/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 31ce5192670b8c9051ba499273909fdf31c1062d
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911963"
---
# <a name="surface-book-3-gpu-tech-overview"></a>Surface Book 3 GPU 기술 개요

## <a name="introduction"></a>소개

Surface Book 가장 강력한 Surface 노트북인 Surface Book 3은 완전히 현대화된 컴퓨팅 및 그래픽 기능을 이 폼 팩터에 통합합니다.  15인치 모델의 쿼드 코어 10세대 Intel® Core™ i7 및 NVIDIA® Quadro RTX™ 3000 GPU(그래픽 처리 장치)가 주도하는 Surface Book 3은 소비자, 창의적 전문가, 설계자, 엔지니어 및 데이터 처리기에서 다양한 구성을 제공합니다. 이 문서에서는 13인치 및 15인치 모델에서 GPU 구성과 3의 15인치 모델 간의 주요 Surface Book 설명합니다.

3 모델에서 중요한 Surface Book GPU 구성입니다. 모든 모델에 기본 제공되는 통합 Intel GPU 외에도, 13.5인치 코어 i5 장치를 포함해 모든 항목은 모바일 폼 팩터에 에너지 효율성을 최적화하는 기능을 통합하는 Max-Q 디자인이 있는 별도 NVIDIA GPU를 제공합니다.

키보드 기반에 기본 제공되는 추가 NVIDIA GPU는 고급 그래픽 렌더링 기능을 제공하며, 소비자 또는 창의적 전문가를 위한 GeForce® GTX® 1650/1660 Ti와 고급 그래픽 또는 딥러닝 기능이 필요한 창의적 전문가, 엔지니어 및 기타 비즈니스 전문가를 위한 Quadro RTX 3000의 두 가지 기본 구성으로 제공합니다. 또한 이 문서에서는 통합된 iGPU와 불연결 NVIDIA GPU를 사용할 앱을 지정하여 GPU의 앱 사용률을 최적화하는 방법에 대해 설명합니다.

## <a name="surface-book-3-gpus"></a>Surface Book 3개

이 섹션에서는 3개 모델에 걸쳐 통합된 Surface Book GPP에 대해 설명합니다. 모든 모델의 구성에 대한 자세한 내용은 [부록 A: Surface Book 3 SKUS를 참조하세요.](#)

### <a name="intel-iris-plus-graphics"></a>Intel Iris™ Plus Graphics

모든 Surface Book 3 모델에 포함된 통합 GPU(iGPU)는 LPDDR4X를 지원하는 더 넓은 그래픽 엔진과 다시 디자인된 메모리 컨트롤러를 통합합니다. 대부분의 Surface Book 3 모델에서 보조 GPU로 설치된 Intel Iris Plus Graphics는 코어 i5, 13.5인치 모델에서 단수 GPU로 기능합니다. Surface Book 3줄의 항목 수준 장치는 물론 소비자, 취미 및 온라인 작성자가 Adobe Creative Cloud와 같은 최신 생산성 소프트웨어를 실행하거나 1080p에서 게임 타이틀을 즐길 수 있도록 하는 고급 그래픽 기능을 제공합니다.  

### <a name="nvidia-geforce-gtx-1650"></a>NVIDIA GeForce GTX 1650

NVIDIA GeForce GTX 1650 Max-Q 디자인은 최신 게임의 복잡한 그래픽을 보다 효율적으로 처리하도록 핵심 스트리밍 멀티 프로세서를 대폭 업그레이드합니다. 부동 소수점 및 정수 연산을 동시 실행하여 최신 게임이 계산이 많은 작업에서 성능을 향상합니다. 선행 캐시의 두 배에 해당 캐시가 있는 새로운 통합 메모리 아키텍처를 사용하면 복잡한 최신 게임에 대한 성능을 향상할 수 있습니다. 새로운 음영 발전은 성능을 향상하고, 이미지 품질을 향상하며, 기하 도형 복잡성의 새로운 수준을 제공합니다.

### <a name="nvidia-geforce-gtx-1660-ti"></a>NVIDIA GeForce GTX 1660 Ti

GeForce GTX 1650과 비교할 때 더 빠른 GeForce GTX 1660 Ti는 추가 성능 향상과 함께 Surface Book 3을 제공하며 새로운 NVIDIA 인코더와 업그레이드된 NVIDIA 인코더를 포함하기 때문에 소비자, 게이머, 라이브 스트리머 및 크리에이티브 전문가에게 더 좋습니다.

6GB의 GDDR6 그래픽 메모리 덕분에 NVIDIA GeForce GTX 1660 TI가 탑재된 Surface Book 3 모델은 특히 최신 타이틀이나 라이브스트링을 실행하는 경우 고급 비즈니스 생산성 소프트웨어 및 인기 게임에 대해 뛰어난 속도를 제공합니다. 선택적 2TB SSD(미국에서만 사용 가능)를 통해 GeForce GTX 1660 Ti가 적용된 15인치 모델은 모든 3개 장치에서 가장 Surface Book 제공합니다.

### <a name="nvidia-quadro-rtx-3000"></a>NVIDIA Quadro RTX 3000

NVIDIA Quadro RTX 3000은 전문 사용자를 위한 여러 가지 주요 기능인 광선 추적 렌더링 및 AI 가속, 고급 그래픽 및 계산 성능의 잠금을 해제합니다. 30개 RT 코어, 240개 텐서 코어 및 6GB의 GDDR6 그래픽 메모리를 조합하여 사용하면 Al-powered 워크플로, 3D 콘텐츠 만들기, 고급 비디오 편집, 전문 브로드캐스트 및 다중 앱 워크플로를 비롯한 여러 고급 워크로드를 사용할 수 있습니다. Enterprise 수준 하드웨어 및 소프트웨어 지원은 배포 도구를 통합하여 운영 시간을 최대화하고 IT 지원 요구 사항을 최소화합니다. 세계에서 가장 고급 소프트웨어에 대해 인증된 Quadro 드라이버는 전문 응용 프로그램에 최적화되어 있으며 앱 인증, 엔터프라이즈 수준의 안정성, 안정성, 가용성 및 확장된 제품 가용성 지원을 제공하도록 조정, 테스트 및 유효성 검사를 통과합니다.
 

## <a name="comparing-gpus-across-surface-book-3"></a>3에서 GPUS Surface Book 비교

NVIDIA GPUS는 게임, 라이브스트림 및 콘텐츠 만들기에 대한 훌륭한 성능을 사용자에게 제공합니다. GeForce GTX 제품은 게이머 및 콘텐츠 작성자에게 매우 좋은 제품입니다. Quadro RTX 제품은 전문 사용자를 대상으로 하여 게임 및 콘텐츠 생성에 큰 성능을 제공하고 다음 기능을 추가합니다.

- 광선 추적 및 AI에 대한 RTX 가속. 이를 통해 물리적으로 정확한 그림자, 반사 및 반지름을 사용하여 영화 품질, 실제적 개체 및 환경을 렌더링할 수 있습니다.  또한 하드웨어 가속 AI 기능은 인기 있는 응용 프로그램의 고급 AI 기반 기능을 이전보다 빠르게 실행할 수 있습니다.
- Enterprise 수준 하드웨어, 드라이버 및 지원뿐만 아니라 ISV 앱 인증도 제공합니다.
- 운영 시간을 최대화하고 IT 지원 요구 사항을 최소화하는 데 도움이 되는 원격 관리를 위한 전용 엔터프라이즈 도구의 추가 계층을 포함한 IT 관리 기능

 고급 엔지니어링, 디자인, 아키텍처 또는 데이터 과학 전문가의 순위를 계산하지 않는 한 NVIDIA GeForce Surface Book 3이 요구 사항을 충족할 수 있습니다. 반대로 Quadro RTX 3000을 사용하여 어디에서나 작업할 수 있는 이동식 폼 팩터의 고급 그래픽 기능이 필요한 전문 기술에 이미 참여하고 있는 경우 3을 사용할 수 있습니다. Surface Book 자세한 내용은 Surface Book Quadro RTX 3000 기술 개요를 참조하세요.
 
**표 1. SURFACE BOOK 3의 불연산 GPUS**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 Ti**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **대상 사용자**     | 게이머, 취미인 및 온라인 작성자  | 게이머, 크리에이티브 전문가 및 온라인 작성자 | 크리에이티브 전문가, 설계자, 엔지니어, 개발자, 데이터 전문가                                |
| **워크플로**        | 그래픽 디자인<br>사진<br>비디오 | 그래픽 디자인<br>사진<br>비디오             | Al-powered Workflows  <br>앱 인증<br>고해상도 비디오<br>Pro 브로드캐스트<br>다중 앱 워크플로 |
| **주요 앱**         | Adobe Creative Suite                   | Adobe Creative Suite                               | Adobe Creative Suite<br>Autodesk AutoCAD<br>Dassault Systemes SolidWorks                                  |
| **GPU 가속** | 비디오 및 이미지 처리             | 비디오 및 이미지 처리                         | 광선 추적 + AI + 6K 비디오<br>Pro 브로드캐스트 기능<br>Enterprise 지원                            |


**표 2. 3의 GPU 기술 Surface Book 사양**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 Ti** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **NVIDIA CUDA 처리 코어**                         | 1024                 | 1536                    | 1920                |
| **NVIDIA 텐서 코어**                                  | 아니오                   | 아니오                      | 240                 |
| **NVIDIA RT Cores**                                      | 아니오                   | 아니오                      | 30                  |
| **GPU 메모리**                                           | 4GB                 | 6GB                    | 6GB                |
| **메모리 대역폭(GB/초)**                            | 최대 112개            | 최대 288개               | 최대 288개           |
| **메모리 유형**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **메모리 인터페이스**                                     | 128비트              | 192비트                 | 192비트             |
| **부스트 클럭 MHz**                                      | 1245                 | 1425                    | 1305                |
| **기본 클럭(MHz)**                                     | 1020                 | 1245                    | 765                 |
| **실시간 광선 추적**                                | 아니오                   | 아니오                      | 예                 |
| **AI 하드웨어 가속**                             | 아니오                   | 아니오                      | 예                 |
| **하드웨어 인코더**                                     | 예                  | 예                     | 예                 |
| **게임 준비 드라이버(GRD)**                              | 예 <sup> 1</sup>                                   | 예  <sup> 1</sup>          |예 <sup> 2</sup> 
| **SD(Studio Driver)**                                   | 예  <sup> 1</sup>            | 예 <sup> 1</sup>                 | 예  <sup> 1</sup>           |
| **ODE(최적 Enterprise)**                  | 아니오                   | 아니오                      | 예            |
| **쿼드로 새 기능 드라이버(QNF)**                      | 아니오                   | 아니오                      | 예            |
| **Microsoft DirectX 12 API, Vulkan API, Open GL 4.6**    | 예                  | 예                     | 예                 |
| **HDCP(High bandwidth Digital Content Protection) 2.2** | 예                  | 예                     | 예                 |
| **NVIDIA GPU 향상**                                     | 예                  | 예                     | 예                 |


 1. *권장 사항*
 2.  *지원함*

## <a name="optimizing-power-and-performance-on-surface-book-3"></a>3에서 전원 및 성능 Surface Book 최적화

Windows 10 성능 슬라이더가 있는 배터리 절약 모드가 포함되어 있습니다. 이 슬라이더를 사용하면 앱 성능을 최대화하거나(오른쪽으로 밀어서) 배터리 사용 시간을 보존할 수 있습니다. Surface Book 3에서는 다음 구성 요소에서 전원 및 성능을 최적화하기 위해 알고리즘적으로 이 기능을 구현합니다.

- CPU 에너지 효율성 레지스터(Intel 속도 전환 기술) 및 기타 SoC 조정 매개 변수를 사용하여 효율성을 극대화합니다.
- 팬 최대 RPM에는 quiet, nominal, performance 및 max의 네 가지 모드가 있습니다.
- 프로세서 전원 캡(PL1/PL2).
- 프로세서 IA Turbo 제한.

기본적으로 배터리가 20% 미만으로 떨어지면 배터리 절약 모드가 설정을 조정하여 배터리 사용 시간을 연장합니다. 전원에 연결된 경우 Surface Book 3은 기본적으로 "최상의 성능" 설정을 사용하여 앱이 모든 i7 Surface Book 3 시스템에 있는 보조 NVIDIA GPU에서 고성능 모드로 실행되도록 합니다.

랩톱으로 사용되거나 태블릿 또는 스튜디오 모드에 있는 경우 최적의 성능을 위해 기본 설정을 사용하는 것이 좋습니다. 작업 표시줄의 오른쪽에 있는 배터리 아이콘을 선택하여 배터리 절약에 액세스할 수 있습니다.

### <a name="game-mode"></a>게임 모드

Surface Book 3에는 실행 시 최대 성능 설정을 자동으로 선택하는 새로운 게임 모드가 포함되어 있습니다.

### <a name="safe-detach"></a>금고 Detach

Surface Book 3의 새로운 기능을 사용하면 분리할 수 금고 사용하도록 설정된 앱을 통해 앱이 GPU를 사용하는 동안 연결을 끊을 수 있습니다. World of *Warcraft와*같은 지원되는 앱의 경우, 작업을 iGPU로 이동됩니다.

### <a name="modifying-app-settings-to-always-use-a-specific-gpu"></a>항상 특정 GPU를 사용하기 위해 앱 설정 수정

절전 기능을 사용할 수 있지만 기본 제공 Intel 그래픽과 더 강력한 불연속 NVIDIA GPU 간에 전환할 수 있으며 GPU를 특정 앱과 연결합니다. 기본적으로 Windows 10 GPU를 자동으로 선택하고 그래픽으로 요구되는 앱을 고유한 NVIDIA GPU에 할당합니다. 대부분의 경우 이러한 설정을 수동으로 조정할 필요가 없습니다. 그러나 그래픽으로 요구되는 앱을 사용하는 동안 키보드 기반에서 디스플레이를 자주 연결하고 다시 연결하려면 일반적으로 앱을 닫아야 합니다. 디스플레이를 디스패치하거나 다시 설정할 때마다 앱을 닫지 않고도 앱을 계속 사용할 수 있도록 하여 그래픽 성능이 일부 손실되어도 통합 GPU에 할당할 수 있습니다.  

경우에 따라 Windows 10 그래픽으로 요구되는 앱을 iGPU로 할당할 수 있습니다. 예를 들어 앱이 하이브리드 그래픽에 대해 완전히 최적화되지 않은 경우입니다. 이를 위해 수동으로 불연산 NVIDIA GPU에 앱을 할당할 수 있습니다.

**GPU당 사용자 지정 옵션을 사용하여 앱을 구성하는 경우:**  

1. 시스템 **설정**  >  ****  >  **으로 이동하고** 그래픽 및 **설정.**

    1. 데스크톱 Windows 클래식 앱 찾아보기를 선택한 ****  >  **** 다음 프로그램을 찾습니다.
    2. UWP 앱의 경우 유니버설 앱을 선택한 **다음** 드롭다운 목록에서 앱을 선택합니다.

2. **추가를** 선택하여 선택한 프로그램의 목록에 새 항목을 만들고 옵션을 선택하여 그래픽 사양을 연 다음 원하는 옵션을 선택합니다.

   ![절전 또는 고성능 GPU 옵션을 선택합니다.](./images/graphics-settings2.png)

3. 각 앱에 사용되는 GPU를 확인하려면 작업 관리자를 **열고 성능을** 선택한 **다음** **GPU 엔진 열을** 니다.


## <a name="appendix-a-surface-book-3-skus"></a>부록 A: Surface Book 3개 SKUS

| **Display**   | **프로세서**                     | **GPU**                                                                                              | **RAM**    | **Storage** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13.5인치** | 쿼드 코어 10세대 Core i5-1035G7 | Intel Iris™ Plus Graphics                                                                            | 16 LPDDR4x | 256GB      |
| **13.5인치** | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1650. 4GB GDDR5 그래픽 메모리가 있는 최대 Q 디자인    | 16 LPDDR4x | 256GB      |
| **13.5인치** | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1650. 4GB GDDR5 그래픽 메모리가 있는 최대 Q 디자인    | 32 LPDDR4x | 512GB      |
| **13.5인치** | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1650. 4GB GDDR5 그래픽 메모리가 있는 최대 Q 디자인    | 32 LPDDR4x | 1TB        |
| **15인치**   | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1660 Ti. 6GB GDDR6 그래픽 메모리가 있는 최대 Q 디자인 | 16 LPDDR4x | 256GB      |
| **15인치**   | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1660 Ti. 6GB GDDR6 그래픽 메모리가 있는 최대 Q 디자인 | 32 LPDDR4x | 512GB      |
| **15인치**   | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1660 Ti. 6GB GDDR6 그래픽 메모리가 있는 최대 Q 디자인 | 32 LPDDR4x | 1TB        |
| **15인치**   | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA GeForce GTX 1660 Ti. 6GB GDDR6 그래픽 메모리가 있는 최대 Q 디자인 | 32 LPDDR4x | 2 TB        |
| **15인치**   | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA Quadro RTX 3000. 6GB GDDR6 그래픽 메모리가 있는 최대 Q 디자인     | 32 LPDDR4x | 512GB      |
| **15인치**   | 쿼드 코어 10세대 Core i7-1065G7 | Intel Iris Plus 그래픽<br>NVIDIA Quadro RTX 3000. 6GB GDDR6 그래픽 메모리가 있는 최대 Q 디자인     | 32 LPDDR4x | 1TB        |

> [!NOTE]
> 미국에서만 사용할 수 있는 2TB SSD: NVIDIA GTX 1660Ti Surface Book 3 15인치

## <a name="summary"></a>요약

성능을 위해 Surface Book 3에는 특정 작업량 및 사용 요구 사항을 충족하도록 최적화된 다양한 GPU 구성이 포함되어 있습니다. 통합 Intel Iris 그래픽 GPU는 기본 Core i5 디바이스에서 유일한 GPU로 작동하며 다른 모든 모델에서 보조 GPU로 기능합니다. GeForce GTX 1650은 복잡한 그래픽을 보다 효율적으로 실행할 수 있도록 핵심 스트리밍 멀티프로세서의 대대적인 업그레이드를 제공합니다. 더 빠른 GeForce GTX 1660 Ti는 Surface Book 3을 제공하면 소비자, 게이머, 라이브 스트리머 및 크리에이티브 전문가에게 더 나은 성능을 제공합니다. Quadro RTX 3000은 전문 사용자를 위한 여러 주요 기능인 광선 추적 렌더링 및 AI 가속, 고급 그래픽 및 계산 성능의 잠금을 해제합니다.


## <a name="learn-more"></a>자세히 알아보기

- [Surface Book 3 Quadro RTX 3000 기술 개요](surface-book-quadro.md)
- [비즈니스용 Surface](https://www.microsoft.com/surface/business)
