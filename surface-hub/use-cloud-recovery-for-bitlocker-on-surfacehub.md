---
title: Surface Hub에서 BitLocker에 대한 클라우드 복구를 사용하는 방법
description: Surface Hub에서 BitLocker에 대한 클라우드 복구를 사용하는 방법
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: 접근성 설정, 설정 앱, 접근성
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: e220be7d4613fcb6a14180e482dc4f2c66a5ddc8
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911033"
---
# <a name="summary"></a>요약

이 문서에서는 특정 장치에서 BitLocker에 예기치 않게 메시지가 표시될 경우 클라우드 복구 기능을 사용하는 Surface Hub 설명되어 있습니다.

> [!NOTE]
> BitLocker 복구 키를 사용할 수 없는 경우 다음 단계를 따라야 합니다.

> [!WARNING]
> * 이 복구 프로세스는 내부 드라이브의 내용을 삭제합니다. 프로세스가 실패하면 내부 드라이브를 완전히 사용되지 않습니다. 이 경우 해결을 위해 Microsoft에 서비스 요청을 기록해야 합니다.
> * 복구 프로세스가 완료되면 장치가 공장 설정으로 다시 설정하고 첫 경험 상태가 됩니다.
> * 복구 후 복구 Surface Hub 완전히 다시 구성해야 합니다.

> [!IMPORTANT]
> 이 프로세스를 수행하려면 프록시 또는 기타 인증 방법을 사용하지 않는 개방형 인터넷 연결이 필요합니다.

## <a name="cloud-recovery-process"></a>클라우드 복구 프로세스

클라우드 복구를 수행하기 위해 다음 단계를 수행합니다.

1. 추가 **복구 옵션을 사용하려면 Esc 누르기 를 선택합니다.**

   ![이스케이프 스크린샷.](images/01-escape.png)

1. 이 **드라이브 건너뛰기 를 선택합니다.**

   ![Screenshot of Skip this drive.](images/02-skip-this-drive.png)

1. 클라우드에서 **복구를 선택합니다.**

   ![클라우드에서 복구의 스크린샷.](images/03-recover-from-cloud.png)

1. 예를 **선택합니다.**

   ![예의 스크린샷.](images/04-yes.png)

1. 다시 **설치를 선택합니다.**

   ![다시 설치의 스크린샷.](images/05a-reinstall.png)

   ![다운로드 스크린샷.](images/05b-downloading.png)

1. 클라우드 복구 프로세스가 완료되면 Out of Box Experience 를 사용하여 재구성을 **시작하십시오.**

   ![Screenshot of Out of the Box.](images/06-out-of-box.png)

## <a name="something-went-wrong-error-message"></a>"문제가 발생했습니다." 오류 메시지

이 오류는 일반적으로 복구 다운로드 중에 발생하는 네트워크 문제로 인해 발생합니다. When this issue occurs, don't turn off the Hub because you won't be able to restart it. 이 오류 메시지가 표시될 경우 "클라우드에서 복구" 단계로 돌아가 복구 프로세스를 다시 시작합니다.

1. 취소를 **선택합니다.**

   ![취소 스크린샷.](images/07-cancel.png)

1. 문제 **해결을 선택합니다.**

   ![문제 해결 스크린샷.](images/08-troubleshoot.png)

1. 클라우드에서 **복구를 선택합니다.**

   ![클라우드에서 복구의 스크린샷.](images/09-recover-from-cloud2.png)

1. 유선 **** 네트워크를 찾을 수 없는 경우 **** 취소 를 선택한 다음 유선 네트워크를 다시 Surface Hub 수 있습니다.

   ![유선 네트워크 스크린샷을 찾을 수 없습니다.](images/10-cancel.png)