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
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643834"
---
# <a name="surface-asset-tag-tool"></a><span data-ttu-id="6b486-103">Surface 자산 태그 도구</span><span class="sxs-lookup"><span data-stu-id="6b486-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="6b486-104">Surface 자산 태그는 Surface 디바이스에 할당된 자산 태그 값을 보고 할당하고 수정할 수 있는 CLI(명령줄 인터페이스) 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="6b486-105">3 및 Surface Pro Surface 디바이스에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="6b486-106">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b486-106">System requirements</span></span>

- <span data-ttu-id="6b486-107">Surface Pro 3 이상</span><span class="sxs-lookup"><span data-stu-id="6b486-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="6b486-108">UEFI 펌웨어 버전 3.9.150.0 이상</span><span class="sxs-lookup"><span data-stu-id="6b486-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <a name="using-surface-asset-tag"></a><span data-ttu-id="6b486-109">Surface 자산 태그 사용</span><span class="sxs-lookup"><span data-stu-id="6b486-109">Using Surface Asset Tag</span></span>

<span data-ttu-id="6b486-110">Surface 자산 태그를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-110">To run Surface Asset Tag:</span></span>

1. <span data-ttu-id="6b486-111">Surface 디바이스에서 Microsoft Tag.zip센터에서 Surface [](https://www.microsoft.com/download/details.aspx?id=46703) **Asset Tag.zip** 다운로드하고 zip 파일을 추출한 다음 원하는 폴더(이 예에서는 C:\\assets)에 AssetTag.exe 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download  Center](https://www.microsoft.com/download/details.aspx?id=46703),  extract the zip file, and save AssetTag.exe in desired folder (in  this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b486-112">X Surface Pro ZIP 파일의 AssetTag_x86 **응용** 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span>

2. <span data-ttu-id="6b486-113">관리자 권한으로 명령 콘솔을 열고 AssetTag.exe 전체 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3. <span data-ttu-id="6b486-114">Surface를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-114">Restart Surface.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b486-115">자산 태그를 설정한 후 WMI에 나타나기 전에 두 번째 재부팅이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-115">After setting the asset tag, a second reboot is required before it appears in WMI.</span></span>

### <a name="asset-tag-tool-commands"></a><span data-ttu-id="6b486-116">자산 태그 도구 명령</span><span class="sxs-lookup"><span data-stu-id="6b486-116">Asset Tag tool commands</span></span>

<span data-ttu-id="6b486-117">다음 예제에서는 AssetTag.exe(C:\assets)의 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-117">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span>

<span data-ttu-id="6b486-118">제안된 자산 태그를 얻기 위해 **AssetTag -g :**</span><span class="sxs-lookup"><span data-stu-id="6b486-118">To get the proposed asset tag, run **AssetTag -g**:</span></span>

```console
C:\assets\AssetTag.exe -g
```

<span data-ttu-id="6b486-119">제안된 자산 태그를 지우기 위해 **AssetTag -s를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="6b486-119">To clear the proposed asset tag, run **AssetTag -s**:</span></span>

```console
C:\assets\AssetTag.exe -s
```

<span data-ttu-id="6b486-120">제안된 자산 태그를 설정하기 위해 **AssetTag -s testassettag12를 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="6b486-120">To set the proposed asset tag, run **AssetTag -s testassettag12**:</span></span>

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="6b486-121">자산 태그 값은 1-36자 사이를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-121">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="6b486-122">유효한 문자로는 A-Z, a-z, 0-9, period(.) 및 하이픈(-)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-122">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>

## <a name="managing-asset-tags"></a><span data-ttu-id="6b486-123">자산 태그 관리</span><span class="sxs-lookup"><span data-stu-id="6b486-123">Managing asset tags</span></span>

<span data-ttu-id="6b486-124">UEFI 설정의 장치 정보(제어판 > 복구 또는 고급 시작 시작 > 지금 다시 시작)의 UEFI**설정에서 기존 자산 태그를 > 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6b486-124">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="6b486-125">아래 그림은 Surface Go에서 자산 태그 도구를 실행한 결과를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-125">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![Surface Go에서 Surface 자산 태그 도구를 실행한 결과입니다.](images/assettag-fig1.png)

> **<span data-ttu-id="6b486-127&quot;>그림 1.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6b486-127&quot;>Figure 1.</span></span>** <span data-ttu-id=&quot;6b486-128&quot;>Surface Go에서 Surface 자산 태그 도구를 실행한 결과</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6b486-128&quot;>Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id=&quot;6b486-129&quot;>또는 WMI를 사용하여 디바이스의 기존 자산 태그를 쿼리할 수 있습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;6b486-129&quot;>Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id=&quot;6b486-130&quot;>(Get-WmiObject -query &quot;Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="6b486-130">(Get-WmiObject -query "Select \* from Win32_SystemEnclosure")</span></span>

### <a name="example"></a><span data-ttu-id="6b486-131">예제</span><span class="sxs-lookup"><span data-stu-id="6b486-131">Example</span></span>

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a><span data-ttu-id="6b486-132">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="6b486-132">Using PowerShell</span></span>

<span data-ttu-id="6b486-133">아래 스크립트를 제안된 값을 받고 오류를 해석하는 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b486-133">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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
