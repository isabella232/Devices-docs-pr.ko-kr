---
title: Microsoft Surface Hub에 대한 알려진 문제 및 추가 정보
description: Microsoft Surface Hub의 알려진 문제점에 대해 간략하게 설명 합니다.
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: surface, hub, 문제
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835431"
---
# Microsoft Surface Hub에 대한 알려진 문제 및 추가 정보

지금 청취 하 고 있습니다. 품질은 주요 우선 순위로, 고객에 게 영향을 주는 문제에 대 한 알림을 유지 하려고 합니다. 다음은 Microsoft Surface Hub의 몇 가지 알려진 문제입니다.

- **비즈니스용 Skype가 RS2의 미디어 트래픽에 대 한 프록시를 사용 하 고 있지 않습니다.**
<br/>프록시 뒤에 있는 일부 Surface Hub 사용자의 경우 비즈니스용 Skype는 미디어 용 프록시 서버를 사용 하지 않습니다. 그러나 Surface Hub는 계정에 로그인 할 수 있습니다. 사용자 의견을 받았으며 프록시를 사용 하는 경우 미디어 트래픽 문제에 대해 알고 있습니다. 이 문제를 적극적으로 조사 하 고 있으며, 솔루션을 식별 하 고 테스트 하는 즉시 수정 사항을 릴리스 합니다. 

- **AAD에 연결 된 디바이스의 경우 사용자가 "내 모임 & 파일"에 로그인 하려고 할 때 Surface Hub가 인터넷에 연결 되어 있지 않은 것을 보고 함**
<br/>Surface Hub에서 로그인 및 문서 액세스에 영향을 주는 문제 집합을 알고 있습니다. 이 문제를 적극적으로 조사 하 고 있습니다. 해결 방법을 사용할 때까지 고객은 장치를 재설정 하 고 로컬 관리자 계정을 사용 하도록 허브를 설정할 수 있습니다. 로컬 관리자 계정을 사용 하도록 다시 구성 하 고 나면 "내 모임 및 파일"이 예상 대로 작동 합니다.
- **Azure AD에 참가 한 경우 Single sign-on**
<br/>Surface Hub는 사용자 자격 증명이 저장 되는 방식에 영향을 주는 공동 공간을 위해 디자인 되었습니다. 이 때문에 장치가 Azure AD에 연결 된 경우 single sign-on 작동 방식에는 현재 제한 사항이 있습니다. Microsoft는 이러한 제한을 인식 하 고 있으며 해결을 위한 옵션을 적극적으로 조사 하 고 있습니다.
- **Surface Hub의 이름에 점 문자 (.)가 있는 경우 Surface Hub에 대 한 인프라 투영을 통해 Miracast가 실패 합니다.**
<br/>Surface Hub 사용자 이름에 마침표 또는 점이 이름에 포함 되는 경우 (예: "Room42")에는 해당 장치에 대 한 문제가 발생할 수 있습니다. 이 문제를 해결 하려면 **설정**  >  **Surface Hub**의 허브 이름을 변경한  >  **About**다음 장치를 다시 시작 합니다. Microsoft는이 문제를 해결 하기 위해 노력 하 고 있습니다.