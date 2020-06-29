---
title: 디바이스 계정 암호 순환 관리
description: PowerShell을 사용 하 여 Surface Hub 2S 온-프레미스 계정을 구성 하는 방법에 대해 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836639"
---
# 디바이스 계정 암호 순환 관리

디바이스 계정 정보를 수동으로 업데이트할 필요 없이 디바이스 계정 암호를 자동으로 변경 하도록 Surface Hub 2S를 구성할 수 있습니다.

암호 회전을 설정 하는 경우 Surface Hub 2S는 7 일 마다 암호를 변경 합니다. 자동으로 생성 된 암호에는 대/소문자, 숫자 및 특수 문자의 조합을 포함 하 여 15-32 문자가 포함 됩니다.

모임 중에 암호가 변경 되지 않습니다. Surface Hub 2S이 꺼져 있는 경우 설정 하거나 성공할 때까지 10 분 마다 암호를 즉시 변경 하려고 시도 합니다.
