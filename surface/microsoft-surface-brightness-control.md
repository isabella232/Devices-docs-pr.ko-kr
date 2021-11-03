---
title: Surface 밝기 제어
description: 이 항목에서는 Surface 밝기 컨트롤 앱을 사용하여 판매 시점 및 키오스크 시나리오에서 디스플레이 밝기를 관리하는 방법을 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 518db8ad0070e5e7355ef57b96057c6f4ae45137
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154073"
---
# <a name="surface-brightness-control"></a>Surface 밝기 제어

판매 시점 또는 다른 "항상 사용" 키오스크 시나리오에서 Surface 디바이스를 배포할 때 새로운 Surface Brightness Control 앱을 사용하여 전원 관리를 최적화할 수 있습니다. Surface Brightness Control은 열 부하를 줄이고 배포된 Surface 디바이스의 전체적인 카본 공간 감소를 지원하도록 디자인되었습니다. 이 도구는 사용하지 않을 때 자동으로 화면을 어리게 표시하며 다음과 같은 구성 옵션을 포함합니다.

- 디스플레이를 희미하게 하기 전의 비활성 기간입니다.
- 희미하게 할 때의 밝기 수준입니다.
- 사용 중일 때의 최대 밝기 수준입니다.

[IT용 Surface Tools에서 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=46703) 사용 가능한 ** 목록에서Surface_Brightness_Control_v1.16.137.0.msi** 파일을 선택합니다.

## <a name="supported-devices"></a>지원되는 디바이스

- Surface Pro 3 이상
- Surface Pro X(모든 세대)
- Surface 3
- Surface Book(모든 세대)
- Surface Laptop Studio
- Surface Studio(모든 세대)
- Surface Laptop(모든 세대)
- Surface Laptop 이동
- Surface Go(모든 세대)


## <a name="run-surface-brightness-control"></a>Surface 밝기 컨트롤 실행

- 대상 **Surface_Brightness_Control_v1.16.137.0.msi** 설치하면 Surface Brightness Control이 즉시 작동하기 시작됩니다.

## <a name="configure-surface-brightness-control"></a>Surface 밝기 컨트롤 구성

 레지스트리를 통해 기본값을 Windows 있습니다. Windows 레지스트리 사용에 대한 자세한 내용은 레지스트리 설명서를 [참조하십시오.](/windows/desktop/sysinfo/registry)

1. 명령 프롬프트에서 regedit를 실행하여 Windows 레지스트리 편집기를 여는 것입니다.
2. Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control으로 이동합니다.
3. 다음 표에 설명된 레지스트리 키 값을 조정합니다.

> [!TIP]
> 이전 버전의 Surface Brightness 컨트롤을 실행하는 경우 컴퓨터\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\Surface Brightness Control\로 이동합니다.

| 레지스트리 설정 | 데이터| 설명  
|-----------|------------|---------------
| 밝기 컨트롤 사용  |  기본값: 01  <br> 옵션: 01, 00 <br> 유형: REG_BINARY |  이 설정을 사용하면 Surface Brightness Control을 켜거나 끄는 데 사용할 수 있습니다. Surface Brightness Control을 사용하지 않도록 설정하기 위해 값을 00으로 설정합니다. 이 설정을 구성하지 않은 경우 Surface Brightness Control이 설정됩니다. |
| 전원 사용 시 밝기 컨트롤| 기본값: 01 <br> 옵션: 01, 00 <br> 유형: REG_BINARY | 이 설정을 사용하면 디바이스가 전원에 직접 연결되어 있는 경우 Surface Brightness Control을 해제할 수 있습니다. 전원이 연결되어 있는 경우 Surface Brightness Control을 사용하지 않도록 설정하고 값을 00으로 설정합니다. 이 설정을 구성하지 않은 경우 Surface Brightness Control이 설정됩니다. |
| 희미하게 밝기   | 기본값: 20  <br>옵션: 화면 밝기에서 0~100% 범위 <br> 데이터 형식: 양의 정수 <br> 유형: REG_DWORD | 이 설정을 사용하면 비활성 기간 동안 밝기 범위를 관리할 수 있습니다. 이 설정을 구성하지 않은 경우 30초 동안 비활성화하면 밝기 수준이 전체 밝기의 20%로 떨어집니다. |
전체 밝기   | 기본값: 100  <br>옵션: 화면 밝기에서 0~100% 범위 <br> 데이터 형식: 양의 정수 <br> 유형: REG_DWORD  | 이 설정을 사용하면 장치의 최대 밝기 범위를 관리할 수 있습니다. 이 설정을 구성하지 않는 경우 최대 밝기 범위는 100%입니다.|  
| 비활성 시간 제한| 기본값: 30초 <br>옵션: 모든 숫자 값  <br>데이터 형식: 정수  <br> 유형: REG_DWORD | 이 설정을 사용하면 장치를 희미하게 하기 전에 비활성 기간을 관리할 수 있습니다. 이 설정을 구성하지 않는 경우 비활성 시간 제한은 30초입니다.|
| 원격 분석 사용 | 기본값: 01 <br>옵션: 01, 00 <br> 유형: REG_BINARY  | 이 설정을 사용하면 앱 사용 현황 정보 공유를 관리하여 소프트웨어를 개선하고 더 나은 사용자 환경을 제공할 수 있습니다. 원격 분석 기능을 사용하지 않도록 설정하기 위해 값을 00으로 설정합니다. 이 설정을 구성하지 않는 경우 Microsoft 개인 정보 취급 방침에 따라 원격 분석 정보가 [Microsoft와 공유됩니다.](https://privacy.microsoft.com/privacystatement) |

## <a name="changes-and-updates"></a>변경 및 업데이트

### <a name="version-116137br"></a>버전 1.16.137<br>

*릴리스 날짜: 2019년 10월 22일*<br>
이 버전의 Surface Brightness Control은 -Recompiled for x86에 대한 지원을 추가하여 Surface Pro 7, Surface Pro X 및 Surface Laptop 3에 대한 지원을 추가합니다.

### <a name="version-1122390"></a>버전 1.12.239.0

*릴리스 날짜: 2019년 4월 26일*<br>
이 버전의 Surface Brightness Control은 다음에 대한 지원을 추가합니다.

- 터치 지연 수정.

## <a name="related-topics"></a>관련 항목

- [배터리 제한 설정](battery-limit.md)
