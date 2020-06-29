---
title: Surface 자산 태그 도구
description: 이 항목에서는 Surface 자산 태그 도구를 사용 하는 방법에 대해 설명 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834748"
---
# Surface 자산 태그 도구

Surface Asset 태그는 Surface 디바이스에 대해 할당 된 자산 태그 값을 보고 할당 하 고 수정할 수 있는 CLI (명령줄 인터페이스) 유틸리티입니다. Surface Pro 3 및 모든 신형 Surface 장치에서 작동 합니다.

## 시스템 요구 사항

- Surface Pro 3 이상

- UEFI 펌웨어 버전 3.9.150.0 이상

## Surface Asset 태그 사용 

서피스 자산 태그를 실행 하려면:

1.  Surface 장치에서 [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=46703)에서 **surface Tag.zip자산** 을 다운로드 하 고, zip 파일을 추출 하 고, 원하는 폴더 (이 예제에서는 c:\\assets)에 AssetTag.exe를 저장 합니다.

    > [!NOTE]
    > Surface Pro X의 경우 ZIP 파일의 **AssetTag_x86** 라는 응용 프로그램을 사용 합니다. 

2.  명령 콘솔을 관리자로 열고 도구에 대 한 전체 경로를 입력 하 AssetTag.exe를 실행 합니다.

3.  Surface를 다시 시작 합니다.

### 자산 태그 도구 명령   
다음 예제에서 AssetTag.exe는 로컬 컴퓨터 (C:\assets)의 디렉터리에 저장 됩니다. 

제안 된 자산 태그를 얻으려면 AssetTag-g를 실행 합니다.

**예**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 제안 된 자산 태그를 지우려면 AssetTag-s를 실행 합니다.
 
 **예**
 
   ```
C:\assets\AssetTag.exe -s
  ```
제안 된 자산 태그를 설정 하려면 AssetTag-s testassettag12를 실행 합니다.

**예**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>자산 태그 값에는 1 ~ 36 자를 포함 해야 합니다. 유효한 문자에는 a-z, a-z, 0-9, 마침표 (.) 및 하이픈 (-)이 포함 됩니다.


## 자산 태그 관리

**제어판 > 복구 > 고급 시작 > 지금 다시 시작**하는 장치 정보 아래의 UEFI 설정에서 기존 자산 태그를 볼 수 있습니다.

아래 그림은 Surface Go에서 자산 태그 도구를 실행 한 결과를 보여 줍니다.

![Surface Go에서 Surface Asset 태그 도구를 실행 한 결과입니다.
](images/assettag-fig1.png)

> **그림 1.** Surface Go에서 Surface Asset 태그 도구 실행 결과

또는 WMI를 사용 하 여 디바이스에서 기존 자산 태그를 쿼리할 수 있습니다.

(Get-WmiObject-쿼리 "Select * in Win32_SystemEnclosure")

**예**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### PowerShell 사용

아래 스크립트를 사용 하 여 제안 된 값을 가져오고 오류를 해석할 수 있습니다.

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
