---
title: Surface DMA 보호
description: 이 문서에서는 호환 되는 화면 장치의 DMA 보호에 대해 설명 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835108"
---
# Surface 장치에 대 한 DMA 보호

DMA (직접 메모리 액세스) 보호는 이동식 SSDs 또는 외부 저장 장치를 사용 하는 것과 관련 된 잠재적인 보안 문제를 완화 하도록 설계 되었습니다. 새로운 Surface 장치는 기본적으로 DMA 보호를 사용 하 여 출하 됩니다. 여기에는 Surface Pro 7, Surface 랩탑을 3 및 Surface Pro X가 포함 됩니다.  장치에서 DMA 보호 기능이 있는지 확인 하려면**Start**  >  아래 그림에 표시 된 대로 시스템 정보 (시작**msinfo32.exe**)를 엽니다.

![DMA 보호 사용이 표시 된 시스템 정보](images/systeminfodma.png)

Surface 이동식 SSD가 훼손 된 경우 디바이스는 전원을 차단 합니다. 결과적으로 다시 부팅 하면 UEFI가 메모리를 지우고 나머지 데이터를 지웁니다.
