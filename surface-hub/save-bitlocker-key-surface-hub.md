---
title: BitLocker 키 저장(Surface Hub)
description: 모든 Microsoft Surface Hub가 BitLocker 드라이브 암호화 소프트웨어를 사용하여 자동으로 설정됩니다. BitLocker 복구 키를 백업하는 것이 좋습니다.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, Bitlocker 복구 키
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836463"
---
# BitLocker 키 저장(Surface Hub)


모든 Microsoft Surface Hub가 BitLocker 드라이브 암호화 소프트웨어를 사용하여 자동으로 설정됩니다. BitLocker 복구 키를 백업하는 것이 좋습니다.

Surface Hub에서 BitLocker 키를 관리하는 몇 가지 방법이 있습니다.

1.  Surface Hub를 도메인에 가입한 경우 장치가 도메인에 키를 백업하고 컴퓨터 개체 아래에 저장합니다.

    장치를 도메인에 가입한 후 BitLocker 키를 찾을 수 없는 경우 Active Directory 스키마에서 BitLocker 키 백업을 지원하지 않을 가능성이 큽니다. 스키마를 변경하지 않으려면 설정으로 이동한 다음 로컬 관리자 계정을 사용하는 절차에 따라 BitLocker 키를 저장할 수 있습니다. 해당 절차는 이 목록의 뒷부분에서 자세히 설명합니다.

2.  Surface Hub를 Azure AD(Active Directory)에 가입한 경우 장치를 가입하는 데 사용된 계정 아래에 BitLocker 키가 저장됩니다.

3.  로컬 관리자 계정을 사용 하 여 장치를 관리 하는 경우 **설정** 앱으로 이동 하 여 BitLocker 키를 저장 하 고 **& 보안** 복구를 업데이트 하도록 탐색할 수 있습니다 &gt; **Recovery**. USB 드라이브를 삽입하고 BitLocker 키를 저장하는 옵션을 선택합니다. 키는 USB 드라이브의 텍스트 파일에 저장됩니다.


## 관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)

 

 





