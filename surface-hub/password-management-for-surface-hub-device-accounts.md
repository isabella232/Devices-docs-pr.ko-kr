---
title: 암호 관리(Surface Hub)
description: 모든 Microsoft Surface Hub 디바이스 계정은 인증하고 디바이스의 기능을 사용하도록 설정하려면 암호가 필요합니다.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: 암호, 암호 관리, 암호 순환, 디바이스 계정
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836679"
---
# 암호 관리(Surface Hub)

모든 Microsoft Surface Hub 디바이스 계정은 인증하고 디바이스의 기능을 사용하도록 설정하려면 암호가 필요합니다. 보안상의 이유로 이 암호를 주기적으로 변경(또는 “순환”)할 수도 있습니다. 그러나 디바이스 계정의 암호가 변경되면 이전에 Surface Hub에 저장된 암호가 부적합해지고, 디바이스 계정에 종속된 모든 기능을 사용할 수 없게 됩니다. 이러한 기능을 다시 사용하도록 설정하려면 설정 앱에서 Surface Hub의 디바이스 계정 암호를 업데이트해야 합니다.

Surface Hub 디바이스 계정의 암호 관리를 간소화할 수 있는 다음 두 가지 옵션이 있습니다.

1.  디바이스 계정의 암호 만료 기능을 해제합니다.
2.  Surface Hub가 디바이스 계정의 암호를 자동으로 순환할 수 있게 합니다.


## 디바이스 계정의 암호 순환 기능을 해제합니다.

디바이스 계정의 **PasswordNeverExpires** 속성을 True로 설정합니다. 조직의 보안 요구 사항을 충족하는지 여부를 확인해야 합니다.


## Surface Hub가 디바이스 계정의 암호를 자동으로 순환할 수 있게 합니다.

Surface Hub는 디바이스 계정 정보를 수동으로 업데이트하도록 요구하지 않고 자주 변경하여 디바이스 계정의 암호를 관리할 수 있습니다. **설정**에서 이 기능을 사용하도록 설정할 수 있습니다. 사용할 경우 디바이스 계정의 암호가 매주 유지 관리 시간 중에 변경됩니다.

디바이스 계정의 암호가 변경된 경우 새 암호는 표시되지 않습니다. 계정에 로그인하거나 암호를 다시 입력해야 하는 경우(예: Surface Hub의 디바이스 계정 설정을 변경하려는 경우) Active Directory 또는 Office 365 관리 포털을 사용하여 암호를 재설정해야 합니다.

> [!IMPORTANT]
> 조직에서 하이브리드 토폴로지(일부 서비스가 온-프레미스로 호스트되고 일부는 Office 365를 통해 온라인으로 호스트됨)를 사용할 경우 **domain\username** 형식으로 디바이스 계정을 설정해야 합니다. 그렇지 않으면 암호 순환이 작동하지 않습니다.
