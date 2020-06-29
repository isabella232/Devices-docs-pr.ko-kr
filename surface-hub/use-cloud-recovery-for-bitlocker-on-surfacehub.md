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
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834871"
---
# 요약

이 문서에서는 Surface Hub 장치에서 BitLocker에 의해 예기치 않게 메시지가 표시 되는 경우 클라우드 복구 기능을 사용 하는 방법에 대해 설명 합니다.

> [!NOTE]
> BitLocker 복구 키를 사용할 수 없는 경우에만이 단계를 수행 해야 합니다.

> [!WARNING]
> * 이 복구 프로세스는 내부 드라이브의 내용을 삭제 합니다. 프로세스가 실패 하면 내부 드라이브를 완전히 사용할 수 없게 됩니다. 이 문제가 발생 하는 경우 문제 해결을 위해 Microsoft에 서비스 요청을 기록해 야 합니다.
> * 복구 프로세스가 완료 되 면 디바이스는 공장 설정으로 재설정 되 고 기본 경험 치 상태로 반환 됩니다.
> * 복구 후 Surface Hub를 완전히 다시 구성 해야 합니다.

> [!IMPORTANT]
> 이 프로세스에는 프록시 또는 다른 인증 방법을 사용 하지 않는 개방형 인터넷 연결이 필요 합니다.

## 클라우드 복구 프로세스

클라우드 복구를 수행 하려면 다음 단계를 따르세요.

1. **추가 복구 옵션을 보려면 Esc 키를 누르세요 .를**선택 합니다.

   ![이스케이프 스크린샷](images/01-escape.png)

1. **이 드라이브 건너뛰기를**선택 합니다.

   ![이 드라이브 건너뛰기 스크린샷](images/02-skip-this-drive.png)

1. **클라우드에서 복구**를 선택 합니다.

   ![클라우드에서 복구 스크린샷](images/03-recover-from-cloud.png)

1. **예**를 선택 합니다.

   ![예 스크린샷](images/04-yes.png)

1. **다시 설치**를 선택 합니다.

   ![재설치 스크린샷](images/05a-reinstall.png)

   ![다운로드 스크린샷](images/05b-downloading.png)

1. 클라우드 복구 프로세스가 완료 되 면 **부재 중 환경을**사용 하 여 재구성을 시작 합니다.

   ![상자 밖의 스크린샷](images/06-out-of-box.png)

## "문제가 발생 했습니다." 오류 메시지

이 오류는 일반적으로 복구 다운로드 중 발생 하는 네트워크 문제 때문에 발생 합니다. 이 문제가 발생 하면 다시 시작할 수 없기 때문에 허브를 끄지 마세요. 이 오류 메시지가 나타나면 "클라우드에서 복구" 단계를 돌아간 다음 복구 프로세스를 다시 시작 합니다.

1. **취소**를 선택 합니다.

   ![취소 스크린샷](images/07-cancel.png)

1. **문제 해결**을 선택 합니다.

   ![문제 해결 스크린샷](images/08-troubleshoot.png)

1. **클라우드에서 복구**를 선택 합니다.

   ![클라우드에서 복구 스크린샷](images/09-recover-from-cloud2.png)

1. **유선 네트워크를 찾을 수 없는** 경우 오류가 발생 하는 경우 **취소**를 선택 하 고 Surface Hub가 유선 네트워크를 다시 검색 하도록 합니다.

   ![유선 네트워크 스크린샷 찾을 수 없음](images/10-cancel.png)