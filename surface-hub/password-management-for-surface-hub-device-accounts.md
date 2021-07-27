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
ms.openlocfilehash: ab2726577201157ed9a7ff4d265e826c063cf477
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676612"
---
# <a name="password-management-surface-hub"></a>암호 관리(Surface Hub)

모든 Microsoft Surface Hub 디바이스 계정은 인증하고 디바이스의 기능을 사용하도록 설정하려면 암호가 필요합니다. 보안상의 이유로 이 암호를 주기적으로 변경(또는 “순환”)할 수도 있습니다. 그러나 디바이스 계정의 암호가 변경되면 이전에 Surface Hub에 저장된 암호가 부적합해지고, 디바이스 계정에 종속된 모든 기능을 사용할 수 없게 됩니다. 이러한 기능을 다시 사용하도록 설정하려면 설정 앱에서 Surface Hub의 디바이스 계정 암호를 업데이트해야 합니다.

Surface Hub 디바이스 계정의 암호 관리를 간소화할 수 있는 다음 두 가지 옵션이 있습니다.

1.  디바이스 계정의 암호 만료 기능을 해제합니다.
2.  Surface Hub가 디바이스 계정의 암호를 자동으로 순환할 수 있게 합니다.


## <a name="turn-off-password-rotation-for-the-device-account"></a>디바이스 계정의 암호 순환 기능을 해제합니다.

디바이스 계정의 **PasswordNeverExpires** 속성을 True로 설정합니다. 조직의 보안 요구 사항을 충족하는지 여부를 확인해야 합니다.


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>Surface Hub가 디바이스 계정의 암호를 자동으로 순환할 수 있게 합니다.

이 Surface Hub 수동으로 업데이트하지 않고도 디바이스 계정의 암호를 자동으로 변경할 수 있습니다. 계정 에서 이 기능을 **설정**  >  **Surface Hub**  >  **있습니다.** 암호 순환을 설정하면 Surface Hub 동안 7일마다 암호를 변경하려고 시도합니다. 모임 중에 암호가 변경되지 않습니다. 마지막 암호 순환 이후 7일이 지났지만 Surface Hub 해제된 경우 켜져 있는 즉시 암호를 변경하거나 성공할 때까지 10분마다 변경을 시도합니다.

자동으로 생성된 암호에는 대문자 및 소문자, 숫자 및 특수 문자의 조합을 포함하여 15-32자까지 입력할 수 있습니다. 디바이스 계정의 암호를 변경하면 새 암호가 표시되지 않습니다. 계정에 로그인하거나 암호를 다시 제공해야 하는 경우(예: Surface Hub에서 장치 계정 설정을 변경하려는 경우) Active Directory 또는 Microsoft 365 관리자 포털을 사용하여 암호를 다시 설정해야 합니다.

> [!IMPORTANT]
> 디바이스를 처음 [설정하는](prepare-your-environment-for-surface-hub.md) 동안 선택된 장치 Surface Hub 암호 순환에 사용할 수 있는 장치 계정 형식에 영향을 미치게 됩니다. 허브는 **도메인\사용자** 이름 형식으로 입력한 장치 계정의 암호만 회전할 수 있습니다. Azure Active Directory 허브는 형식으로 입력된 장치 계정의 암호만 회전할 수 있지만 계정이 클라우드 전용 또는 AAD 도메인이 클라우드 인증 및 암호 쓰기 저장에 대해 구성된 경우만 회전할 수 `username@domain.com` 있습니다. [](/azure/active-directory/hybrid/choose-ad-authn#cloud-authentication) [](/azure/active-directory/authentication/concept-sspr-writeback)
