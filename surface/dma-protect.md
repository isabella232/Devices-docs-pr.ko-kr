---
title: Surface DMA 보호
description: 이 문서에서는 호환되는 Surface 디바이스의 DMA 보호에 대해 설명
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: d2656b141908ef203f748518ddf49a7fbcbab255
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911353"
---
# <a name="dma-protection-on-surface-devices"></a>Surface 디바이스의 DMA 보호

DMA(직접 메모리 액세스) 보호는 이동식 SSD 또는 외부 저장 장치를 사용하는 경우와 관련된 잠재적인 보안 취약성을 완화하도록 디자인되었습니다. 새로운 Surface 디바이스는 기본적으로 DMA 보호를 사용하도록 설정되어 있습니다. 여기에는 7 Surface Pro 포함됩니다. Surface Pro 7, Surface Laptop 3 및 Surface Pro X입니다.  장치에서 DMA 보호 기능의 존재를 확인하려면 아래 그림과 같이 시스템 정보(시작msinfo32.exe)를****  >  ** **열어 보십시오.

![DMA 보호를 사용하도록 설정한 시스템을 보여 주며 시스템 정보입니다.](images/systeminfodma.png)

Surface 이동식 SSD가 변조된 경우 장치가 전원을 끄게 됩니다. 그러면 UEFI가 메모리를 지우고 모든 잔류 데이터를 지우게 됩니다.
