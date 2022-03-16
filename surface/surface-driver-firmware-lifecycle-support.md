---
title: Windows 기반 장치용 Surface 드라이버 및 펌웨어 수명 주기
description: 이 문서에서는 하드웨어 및 소프트웨어 배포를 계획하고 관리하는 데 도움이 되는 자세한 수명 주기 정보를 제공합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/30/2021
ms.reviewer: phorton
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 54a6fd560b16d29e8a155bcf24efd814a6d5bf77
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449621"
---
# <a name="surface-driver-and-firmware-lifecycle-for-windows-based-devices"></a>Windows 기반 장치용 Surface 드라이버 및 펌웨어 수명 주기
 
하드웨어 및 소프트웨어 배포를 계획하고 관리하는 데 도움이 되는 보다 자세한 수명 주기 정보에 대한 고객의 요청에 따라 Surface는 드라이버 및 펌웨어 업데이트에 대한 추가 지침을 제공합니다.
 
이 수명 주기 정책은 Windows 기반 Surface 장치용 드라이버 및 펌웨어 릴리스에 적용됩니다. 수명 주기는 장치가 처음 출시될 때 시작되어 서비스 종료 날짜에 Surface에서 드라이버 및 펌웨어 업데이트 게시를 중단할 때 종료됩니다. 다음 섹션에서는 수명 주기 정책과 서비스 종료 날짜를 정의합니다.

## <a name="surface-driver-and-firmware-support-lifecycle"></a>Surface 드라이버 및 펌웨어 지원 수명 주기
 
Surface 드라이버 및 펌웨어 수명 주기는 장치에 대한 드라이버 및 펌웨어 지원 기간과 해당 기간 동안 OS 버전에 대해 제공되는 지원의 두 부분으로 구성됩니다.

- **장치 지원 기간.** 장치 지원 기간은 Surface가 장치에 대한 드라이버 및 펌웨어 업데이트를 지원하는 기간을 정의합니다. 장치 지원 기간은 장치가 출시되면 시작됩니다. Surface 장치는 장치가 처음 출시된 후 최소 4년 동안 드라이버 및 펌웨어 업데이트를 받습니다. 지원 기간이 4년보다 긴 경우 업데이트된 서비스 종료 날짜는 마지막 서비스 날짜보다 먼저 게시됩니다.

- **OS 버전 지원.** dOS 버전 지원은 장치 지원 기간 동안 Surface에서 지원하는 운영 체제 버전을 정의합니다. Surface 장치는 이전 30개월 동안 릴리스된 Windows OS 버전용 드라이버 및 펌웨어 업데이트를 받습니다. Surface는 장치 릴리스에서 지원되는 OS 버전보다 이전 Windows OS 버전을 지원하지 않습니다. Surface 장치의 최소 지원 OS 버전은 [Surface 지원 운영체제](https://support.microsoft.com/help/2858199/surface-supported-operating-systems)를 참조하세요.  

 
서비스 종료일에 장치 지원 기간이 종료되면 장치는 [Microsoft 수명 주기 정책 지원 페이지](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy)에 설명된 대로 Windows 수명 주기 정책에 따라 Windows OS 기능 및 보안 업데이트를 계속 받게 됩니다.
 

## <a name="surface-driver-and-firmware-servicing-dates"></a>Surface 드라이버 및 펌웨어 서비스 날짜

다음 표에는 드라이버 및 펌웨어 수명 주기 정책이 정의된 각 Surface 장치의 출시 날짜와 서비스 종료 날짜가 나와 있습니다.
 

 장치                             | 출시 날짜 | 서비스 종료 날짜 |
| ---------------------------------- | ------------ | --------------------- |
| Surface RT<sup>1</sup>             | 2012년 10월 26일   | 2017년 4월 11일             |
| Surface Pro<sup>1</sup>            | 2013년 2월 9일     | 2017년 4월 11일             |
| Surface 2<sup>1</sup>              | 2013년 10월 22일   | 2018년 4월 10일             |
| Surface Pro 2<sup>1</sup>          | 2013년 10월 22일   | 2018년 4월 10일             |
| Surface Pro 3                      | 2014년 6월 20일    | 2021년 11월 13일            |
| Surface 3                          | 2015년 5월 5일     | 2021년 11월 13일            |
| Surface Book                       | 2015년 10월 26일   | 2021년 11월 13일            |
| Surface Pro 4                      | 2015년 10월 26일   | 2021년 11월 13일            |
| 성능 기반이 포함된 Surface Book | 2016년 11월 10일   | 2021년 11월 13일            |
| Surface Studio(1세대)           | 2016년 12월 15일   | 2021년 11월 13일            |
| Surface Laptop(1세대)           | 2017년 6월 14일    | 2021년 11월 13일            |
| Surface Pro(5세대)              | 2017년 6월 15일    | 2024년 1월 15일            |
| Surface Book 2                     | 2017년 11월 17일   | 2023년 5월 30일            |
| Surface Pro LTE(모델 1807)       | 2017년 12월 1일    | 2024년 1월 15일             |
| Surface Go                         | 2018년 8월 2일     | 2022년 8월 2일              |
| Surface Studio 2                   | 2018년 10월 2일    | 2024년 10월 2일             |
| Surface Laptop 2                   | 2018년 10월 16일   | 2022년 12월 27일            |
| Surface Pro 6                      | 2018년 10월 16일   | 2023년 6월 30일           |
| Surface Go LTE Advanced       | 2018년 11월 20일   | 2022년 11월 20일            |
| Surface Laptop 3                   | 2019년 10월 22일   | 2023년 10월 22일            |
| Surface Pro 7                      | 2019년 10월 22일   | 2023년 10월 22일            |
| Surface Pro X                      | 2019년 11월 5일    | 2024년 10월 13일             |
| Surface Go 2                       | 2020년 5월 6일     | 2024년 5월 6일              |
| Surface Book 3                     | 2020년 5월 26일    | 2024년 5월 26일             |
| Surface Laptop Go                  | 2020년 10월 13일   | 2024년 10월 13일            |
| Surface Pro 7+                     | 2021년 1월 15일 | 2025년 1월 15일 |
| Surface Laptop 4                   | 2021년 4월 15일   | 2025년 4월 15일 |
| Surface Pro 8                      | 2021년 10월 5일   |2025년 10월 5일|
| Surface Laptop 스튜디오              | 2021년 10월 5일   |2025년 10월 5일|
| Surface Go 3                       | 2021년 10월 5일   |2025년 10월 5일|

 **1.** *이전에 선언된 펌웨어/드라이버 서비스 지원 날짜가 종료된 장치를 나타냅니다.*

## <a name="surface-hub-driver-and-firmware-support-lifecycle"></a>Surface Hub 드라이버 및 펌웨어 지원 수명 주기

다음 표에는 드라이버 및 펌웨어 수명 주기 정책이 정의된 각 Surface Hub 장치 및 Hub 액세서리의 출시 날짜와 서비스 종료 날짜가 나와 있습니다.
 

| Surface 허브 장치     | 출시 날짜              | 서비스 종료 날짜   |
| ---------------------- | ------------------------- | ---------------------------- |
| Surface 허브 55         | 2015년 6월 1일              | 2022년 11월 30일 |
| Surface 허브 84         | 2015년 6월 1일              | 2022년 11월 30일 |
| Surface Hub 2S         | 2019년 4월 17일            | 2023년 4월 17일    |
| Surface 허브 2S 85"     | 2021년 1월 11일          | 2025년 1월 11일  | 
 
## <a name="learn-more"></a>세부 정보

LTSC 지원에 대한 추가 정보는 [Windows 10 장기 서비스 채널(LTSC)과의 Surface 장치 호환성](surface-device-compatibility-with-windows-10-ltsc.md)을 참조하세요.

하드웨어 보증 및 고객 지원에 대한 추가 정보는 [Surface 보증 및 지원 계획](https://www.microsoft.com/surface/business/warranty-service-offerings-and-support)을 참조하세요.
