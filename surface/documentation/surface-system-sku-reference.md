---
title: Surface 시스템 SKU 참조
description: 이 항목에서는 특정 장치의 컴퓨터 상태를 빠르게 확인 하는 데 사용할 수 있는 시스템 SKU 이름에 대 한 참조를 제공 합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835103"
---
# <span data-ttu-id="93837-103">Surface System SKU 참조</span><span class="sxs-lookup"><span data-stu-id="93837-103">Surface System SKU Reference</span></span>
<span data-ttu-id="93837-104">이 문서는 PowerShell, WMI 및 관련 도구를 사용 하 여 특정 장치의 컴퓨터 상태를 빠르게 확인 하는 데 사용할 수 있는 시스템 SKU 이름에 대 한 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93837-104">This document provides a reference of System SKU names that you can use to quickly determine the machine state of a specific device using PowerShell, WMI, and related tools.</span></span> 

<span data-ttu-id="93837-105">System SKU는 Surface 디바이스의 UEFI 계층에 있는 SMBIOS (시스템 관리 BIOS) 표에 저장 된 변수 (시스템 모델 및 기타)입니다.</span><span class="sxs-lookup"><span data-stu-id="93837-105">System SKU is a variable (along with System Model and others) stored in System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices.</span></span>  <span data-ttu-id="93837-106">System SKU 이름을 사용 하 여 Surface Pro 및 Surface Pro와 같은 시스템 모델 이름 (예: LTE Advanced를 사용 하는 장치)을 구분 해야 할 경우</span><span class="sxs-lookup"><span data-stu-id="93837-106">Use the System SKU name whenever you need to differentiate between devices with the same System Model name, such as Surface Pro and Surface Pro with LTE Advanced.</span></span> 

| **<span data-ttu-id="93837-107">장치</span><span class="sxs-lookup"><span data-stu-id="93837-107">Device</span></span>**| **<span data-ttu-id="93837-108">시스템 모델</span><span class="sxs-lookup"><span data-stu-id="93837-108">System Model</span></span>** | **<span data-ttu-id="93837-109">시스템 SKU</span><span class="sxs-lookup"><span data-stu-id="93837-109">System SKU</span></span>**|
| --- | ---| --- |
| <span data-ttu-id="93837-110">Surface 3 WiFI</span><span class="sxs-lookup"><span data-stu-id="93837-110">Surface 3 WiFI</span></span>                                               | <span data-ttu-id="93837-111">Surface 3</span><span class="sxs-lookup"><span data-stu-id="93837-111">Surface 3</span></span>        | <span data-ttu-id="93837-112">Surface_3</span><span class="sxs-lookup"><span data-stu-id="93837-112">Surface_3</span></span>                        |
| <span data-ttu-id="93837-113">&T의 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="93837-113">Surface 3 LTE AT&T</span></span>                                           | <span data-ttu-id="93837-114">Surface 3</span><span class="sxs-lookup"><span data-stu-id="93837-114">Surface 3</span></span>        | <span data-ttu-id="93837-115">Surface_3_US1</span><span class="sxs-lookup"><span data-stu-id="93837-115">Surface_3_US1</span></span>                    |
| <span data-ttu-id="93837-116">Surface 3 LTE Verizon</span><span class="sxs-lookup"><span data-stu-id="93837-116">Surface 3 LTE Verizon</span></span>                                        | <span data-ttu-id="93837-117">Surface 3</span><span class="sxs-lookup"><span data-stu-id="93837-117">Surface 3</span></span>        | <span data-ttu-id="93837-118">Surface_3_US2</span><span class="sxs-lookup"><span data-stu-id="93837-118">Surface_3_US2</span></span>                    |
| <span data-ttu-id="93837-119">Surface 3 LTE 북아메리카</span><span class="sxs-lookup"><span data-stu-id="93837-119">Surface 3 LTE North America</span></span>                                  | <span data-ttu-id="93837-120">Surface 3</span><span class="sxs-lookup"><span data-stu-id="93837-120">Surface 3</span></span>        | <span data-ttu-id="93837-121">Surface_3_NAG</span><span class="sxs-lookup"><span data-stu-id="93837-121">Surface_3_NAG</span></span>                    |
| <span data-ttu-id="93837-122">북미 외부의 Surface 3 LTE 및 일본의 T-모바일</span><span class="sxs-lookup"><span data-stu-id="93837-122">Surface 3 LTE Outside of North America and T-Mobile In Japan</span></span> | <span data-ttu-id="93837-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="93837-123">Surface 3</span></span>        | <span data-ttu-id="93837-124">Surface_3_ROW</span><span class="sxs-lookup"><span data-stu-id="93837-124">Surface_3_ROW</span></span>                    |
| <span data-ttu-id="93837-125">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93837-125">Surface Pro</span></span>                                                  | <span data-ttu-id="93837-126">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93837-126">Surface Pro</span></span>      | <span data-ttu-id="93837-127">Surface_Pro_1796</span><span class="sxs-lookup"><span data-stu-id="93837-127">Surface_Pro_1796</span></span>                 |
| <span data-ttu-id="93837-128">Surface Pro LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="93837-128">Surface Pro with LTE Advanced</span></span>                                | <span data-ttu-id="93837-129">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="93837-129">Surface Pro</span></span>      | <span data-ttu-id="93837-130">Surface_Pro_1807</span><span class="sxs-lookup"><span data-stu-id="93837-130">Surface_Pro_1807</span></span>                 |
| <span data-ttu-id="93837-131">Surface Book 2 13inch</span><span class="sxs-lookup"><span data-stu-id="93837-131">Surface Book 2 13inch</span></span>                                        | <span data-ttu-id="93837-132">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="93837-132">Surface Book 2</span></span>   | <span data-ttu-id="93837-133">Surface_Book_1832</span><span class="sxs-lookup"><span data-stu-id="93837-133">Surface_Book_1832</span></span>                |
| <span data-ttu-id="93837-134">Surface Book 2 15inch</span><span class="sxs-lookup"><span data-stu-id="93837-134">Surface Book 2 15inch</span></span>                                        | <span data-ttu-id="93837-135">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="93837-135">Surface Book 2</span></span>   | <span data-ttu-id="93837-136">Surface_Book_1793</span><span class="sxs-lookup"><span data-stu-id="93837-136">Surface_Book_1793</span></span>                |
| <span data-ttu-id="93837-137">Surface Go 소비자</span><span class="sxs-lookup"><span data-stu-id="93837-137">Surface Go Consumer</span></span>                                          | <span data-ttu-id="93837-138">Surface Go</span><span class="sxs-lookup"><span data-stu-id="93837-138">Surface Go</span></span>       | <span data-ttu-id="93837-139">Surface_Go_1824_Consumer</span><span class="sxs-lookup"><span data-stu-id="93837-139">Surface_Go_1824_Consumer</span></span>         |
| <span data-ttu-id="93837-140">Surface Go 상업용</span><span class="sxs-lookup"><span data-stu-id="93837-140">Surface Go Commercial</span></span>                                        | <span data-ttu-id="93837-141">Surface Go</span><span class="sxs-lookup"><span data-stu-id="93837-141">Surface Go</span></span>       | <span data-ttu-id="93837-142">Surface_Go_1824_Commercial</span><span class="sxs-lookup"><span data-stu-id="93837-142">Surface_Go_1824_Commercial</span></span>       |
| <span data-ttu-id="93837-143">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="93837-143">Surface Go 2</span></span>                                                 | <span data-ttu-id="93837-144">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="93837-144">Surface Go 2</span></span>     | <span data-ttu-id="93837-145">Surface_Go_2_1927</span><span class="sxs-lookup"><span data-stu-id="93837-145">Surface_Go_2_1927</span></span>                |
| <span data-ttu-id="93837-146">Surface Pro 6 소비자</span><span class="sxs-lookup"><span data-stu-id="93837-146">Surface Pro 6 Consumer</span></span>                                       | <span data-ttu-id="93837-147">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="93837-147">Surface Pro 6</span></span>    | <span data-ttu-id="93837-148">Surface_Pro_6_1796_Consumer</span><span class="sxs-lookup"><span data-stu-id="93837-148">Surface_Pro_6_1796_Consumer</span></span>      |
| <span data-ttu-id="93837-149">Surface Pro 6 상업용</span><span class="sxs-lookup"><span data-stu-id="93837-149">Surface Pro 6 Commercial</span></span>                                     | <span data-ttu-id="93837-150">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="93837-150">Surface Pro 6</span></span>    | <span data-ttu-id="93837-151">Surface_Pro_6_1796_Commercial</span><span class="sxs-lookup"><span data-stu-id="93837-151">Surface_Pro_6_1796_Commercial</span></span>    |
| <span data-ttu-id="93837-152">Surface 노트북 2 소비자</span><span class="sxs-lookup"><span data-stu-id="93837-152">Surface Laptop 2 Consumer</span></span>                                    | <span data-ttu-id="93837-153">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="93837-153">Surface Laptop 2</span></span> | <span data-ttu-id="93837-154">Surface_Laptop_2_1769_Consumer</span><span class="sxs-lookup"><span data-stu-id="93837-154">Surface_Laptop_2_1769_Consumer</span></span>   |
| <span data-ttu-id="93837-155">Surface 노트북 2 상업용</span><span class="sxs-lookup"><span data-stu-id="93837-155">Surface Laptop 2 Commercial</span></span>                                  | <span data-ttu-id="93837-156">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="93837-156">Surface Laptop 2</span></span> | <span data-ttu-id="93837-157">Surface_Laptop_2_1769_Commercial</span><span class="sxs-lookup"><span data-stu-id="93837-157">Surface_Laptop_2_1769_Commercial</span></span> |

## <span data-ttu-id="93837-158">시스템 SKU 변수 사용</span><span class="sxs-lookup"><span data-stu-id="93837-158">Using System SKU variables</span></span> 

### <span data-ttu-id="93837-159">PowerShell</span><span class="sxs-lookup"><span data-stu-id="93837-159">PowerShell</span></span>

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### <span data-ttu-id="93837-160">시스템 정보</span><span class="sxs-lookup"><span data-stu-id="93837-160">System Information</span></span>
<span data-ttu-id="93837-161">시스템 정보에서 장치에 대 한 시스템 SKU 및 시스템 모델을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93837-161">You can also find the System SKU and System Model for a device in System Information.</span></span> 
- <span data-ttu-id="93837-162">MSInfo32 **시작**  >   **MSInfo32**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="93837-162">Click **Start** >  **MSInfo32**.</span></span>  

### <span data-ttu-id="93837-163">WMI</span><span class="sxs-lookup"><span data-stu-id="93837-163">WMI</span></span>
<span data-ttu-id="93837-164">Microsoft 배포 도구 키트 (MDT) 또는 Microsoft 끝점 구성 관리자에서 작업 순서 WMI 조건에 시스템 SKU 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93837-164">You can use System SKU variables in a Task Sequence WMI Condition in the Microsoft Deployment Toolkit (MDT) or Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="93837-165">예:</span><span class="sxs-lookup"><span data-stu-id="93837-165">For example:</span></span> 

    - <span data-ttu-id="93837-166">WMI 네임 스페이스 – Root\WMI</span><span class="sxs-lookup"><span data-stu-id="93837-166">WMI Namespace – Root\WMI</span></span>
    - <span data-ttu-id="93837-167">WQL Query – SystemSKU = "Surface_Pro_1796" 인 MS_SystemInformation를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="93837-167">WQL Query – SELECT \* FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"</span></span>

 
 
 


