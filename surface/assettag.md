---
title: Surface 자산 태그 도구
description: 이 항목에서는 Surface 자산 태그 도구를 사용하는 방법을 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 3b6525c979160d6f732e330086565c3de6f73cbd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449151"
---
# <a name="surface-asset-tag-tool"></a>Surface 자산 태그 도구

Surface 자산 태그는 Surface 디바이스에 할당된 자산 태그 값을 보고 할당하고 수정할 수 있는 CLI(명령줄 인터페이스) 유틸리티입니다. 3 및 Surface Pro Surface 디바이스에서 작동합니다.

## <a name="system-requirements"></a>시스템 요구 사항

- Surface Pro 3 이상

- UEFI 펌웨어 버전 3.9.150.0 이상

## <a name="using-surface-asset-tag"></a>Surface 자산 태그 사용

Surface 자산 태그를 실행합니다.

1. Surface 디바이스에서 Microsoft Tag.zip센터에서 **Surface Asset Tag.zip** 다운로드하고 zip 파일을 [](https://www.microsoft.com/download/details.aspx?id=46703)추출한 다음 원하는 폴더(이 예에서는 C:\\assets)에 AssetTag.exe 파일을 저장합니다.

    > [!NOTE]
    > X Surface Pro ZIP 파일에 **AssetTag_x86 응용 프로그램을** 사용 합니다.

2. 관리자 권한으로 명령 콘솔을 열고 AssetTag.exe 전체 경로를 입력합니다.

3. Surface를 다시 시작합니다.

    > [!NOTE]
    > 자산 태그를 설정한 후 WMI에 나타나기 전에 두 번째 재부팅이 필요합니다.

### <a name="asset-tag-tool-commands"></a>자산 태그 도구 명령

다음 예제에서는 AssetTag.exe(C:\assets)의 디렉터리에 저장됩니다.

제안된 자산 태그를 얻기 위해 **AssetTag -g를 실행합니다**.

```console
C:\assets\AssetTag.exe -g
```

제안된 자산 태그를 지우기 위해 **AssetTag -s를 실행합니다**.

```console
C:\assets\AssetTag.exe -s
```

제안된 자산 태그를 설정하기 위해 **AssetTag -s testassettag12를 실행합니다**.

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>자산 태그 값은 1-36자 사이를 포함해야 합니다. 유효한 문자로는 A-Z, a-z, 0-9, period(.) 및 하이픈(-)이 포함됩니다.

## <a name="managing-asset-tags"></a>자산 태그 관리

UEFI 설정의 장치 정보(제어판 > 복구 및 고급 시작 > 지금 다시 시작)의 UEFI **설정에서 기존 자산 태그를 > 있습니다**.

아래 그림은 Surface Go에서 자산 태그 도구를 실행한 결과를 보여줍니다.

![Surface Go에서 Surface 자산 태그 도구를 실행한 결과입니다.](images/assettag-fig1.png)

> **그림 1.** Surface Go에서 Surface 자산 태그 도구를 실행한 결과

또는 WMI를 사용하여 디바이스의 기존 자산 태그를 쿼리할 수 있습니다.

(Get-WmiObject -query "Select * from Win32_SystemEnclosure")

### <a name="example"></a>예제

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a>PowerShell 사용

아래 스크립트를 제안된 값을 받고 오류를 해석하는 방법으로 사용할 수 있습니다.

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```
