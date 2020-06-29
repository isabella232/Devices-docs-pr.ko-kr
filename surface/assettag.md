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
# <span data-ttu-id="2aed3-103">Surface 자산 태그 도구</span><span class="sxs-lookup"><span data-stu-id="2aed3-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="2aed3-104">Surface Asset 태그는 Surface 디바이스에 대해 할당 된 자산 태그 값을 보고 할당 하 고 수정할 수 있는 CLI (명령줄 인터페이스) 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="2aed3-105">Surface Pro 3 및 모든 신형 Surface 장치에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="2aed3-106">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2aed3-106">System requirements</span></span>

- <span data-ttu-id="2aed3-107">Surface Pro 3 이상</span><span class="sxs-lookup"><span data-stu-id="2aed3-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="2aed3-108">UEFI 펌웨어 버전 3.9.150.0 이상</span><span class="sxs-lookup"><span data-stu-id="2aed3-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="2aed3-109">Surface Asset 태그 사용</span><span class="sxs-lookup"><span data-stu-id="2aed3-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="2aed3-110">서피스 자산 태그를 실행 하려면:</span><span class="sxs-lookup"><span data-stu-id="2aed3-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="2aed3-111">Surface 장치에서 [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=46703)에서 **surface Tag.zip자산** 을 다운로드 하 고, zip 파일을 추출 하 고, 원하는 폴더 (이 예제에서는 c:\\assets)에 AssetTag.exe를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="2aed3-112">Surface Pro X의 경우 ZIP 파일의 **AssetTag_x86** 라는 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="2aed3-113">명령 콘솔을 관리자로 열고 도구에 대 한 전체 경로를 입력 하 AssetTag.exe를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="2aed3-114">Surface를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-114">Restart Surface.</span></span>

### <span data-ttu-id="2aed3-115">자산 태그 도구 명령</span><span class="sxs-lookup"><span data-stu-id="2aed3-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="2aed3-116">다음 예제에서 AssetTag.exe는 로컬 컴퓨터 (C:\assets)의 디렉터리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="2aed3-117">제안 된 자산 태그를 얻으려면 AssetTag-g를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="2aed3-118">예</span><span class="sxs-lookup"><span data-stu-id="2aed3-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="2aed3-119">제안 된 자산 태그를 지우려면 AssetTag-s를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="2aed3-120">예</span><span class="sxs-lookup"><span data-stu-id="2aed3-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="2aed3-121">제안 된 자산 태그를 설정 하려면 AssetTag-s testassettag12를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="2aed3-122">예</span><span class="sxs-lookup"><span data-stu-id="2aed3-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="2aed3-123">자산 태그 값에는 1 ~ 36 자를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="2aed3-124">유효한 문자에는 a-z, a-z, 0-9, 마침표 (.) 및 하이픈 (-)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="2aed3-125">자산 태그 관리</span><span class="sxs-lookup"><span data-stu-id="2aed3-125">Managing asset tags</span></span>

<span data-ttu-id="2aed3-126">**제어판 > 복구 > 고급 시작 > 지금 다시 시작**하는 장치 정보 아래의 UEFI 설정에서 기존 자산 태그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="2aed3-127">아래 그림은 Surface Go에서 자산 태그 도구를 실행 한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="2aed3-128">Surface Go에서 Surface Asset 태그 도구를 실행 한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="2aed3-129">그림 1.</span><span class="sxs-lookup"><span data-stu-id="2aed3-129">Figure 1.</span></span>** <span data-ttu-id="2aed3-130">Surface Go에서 Surface Asset 태그 도구 실행 결과</span><span class="sxs-lookup"><span data-stu-id="2aed3-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="2aed3-131">또는 WMI를 사용 하 여 디바이스에서 기존 자산 태그를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="2aed3-132">(Get-WmiObject-쿼리 "Select \* in Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="2aed3-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="2aed3-133">예</span><span class="sxs-lookup"><span data-stu-id="2aed3-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="2aed3-134">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="2aed3-134">Using PowerShell</span></span>

<span data-ttu-id="2aed3-135">아래 스크립트를 사용 하 여 제안 된 값을 가져오고 오류를 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aed3-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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
