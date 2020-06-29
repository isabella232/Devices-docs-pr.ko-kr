---
title: Surface Hub에서 정규화된 도메인 이름 사용
description: 설치 문제, Exchange ActiveSync 오류를 포함하여 일반적인 문제를 해결합니다.
keywords:
- 일반적인 문제 해결
- 설치 문제
- Exchange ActiveSync 오류
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834852"
---
# 비즈니스용 Skype에 대한 도메인 이름 구성

몇 가지 시나리오에서는 비즈니스용 Skype 서버의 도메인 이름을 지정해야 합니다.
- **DNS 접미사가 여러 개임** - 비즈니스용 Skype 인프라에 비연속 네임스페이스가 있는 경우(예: 하나 이상의 서버에 Skype 비즈니스용 SIP(로그인 주소)의 접미사와 일치하지 않는 DNS 접미사가 있는 경우)  
- **비즈니스용 Skype와 Exchange 접미사가 서로 다름** - 비즈니스용 Skype에 대한 로그인 주소의 접미사가 디바이스 계정에 사용되는 Exchange 주소 접미사와 다른 경우
- **인증서 작업** -온-프레미스 비즈니스용 Skype 서버를 사용 하는 대규모 조직은 일반적으로 자체 루트 CA (인증 기관)와 함께 인증서를 사용 합니다. 일반적으로 CA 도메인은 비즈니스용 Skype 서버 도메인과 다르며 이로 인해 인증서를 신뢰할 수 없어 로그인에 실패하게 됩니다.  Skype에서는 트러스트 관계 설정을 위해 인증서의 도메인 이름에 대해 알고 있어야 합니다. 일반적으로 기업에서는 그룹 정책을 사용하여 Skype 바탕 화면으로 이 FQDN을 푸시하지만 Surface Hub에서는 그룹 정책이 지원되지 않습니다.

**비즈니스용 Skype 서버에 대한 도메인 이름을 구성하려면**</br>
1. Surface Hub에서 **설정**을 엽니다.
2. **Surface Hub**, **전화 및 오디오**를 차례로 클릭합니다. 
3. **비즈니스용 Skype 구성**에서 **도메인 이름 구성**을 클릭합니다. 
4. 비즈니스용 Skype 서버의 도메인 이름을 입력하고 **확인**을 클릭합니다. 
   > [!TIP]
   > 여러 도메인 이름을 쉼표로 구분하여 입력할 수 있습니다. <br> 예를 들면 lync.com, outlook.com, lync.glbdns.microsoft.com입니다.

    ![설정에 비즈니스용 Skype FQDN 추가](images/system-settings-add-fqdn.png)
