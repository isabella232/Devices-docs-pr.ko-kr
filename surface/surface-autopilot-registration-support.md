---
title: Windows Autopilot용 Surface 등록 지원
description: 이 문서에서는 Autopilot 등록 요청을 Microsoft 지원에 제출하기 위한 요구 사항에 대해 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: b31cacad5a744dcb29fc3dd2822c656d528fcd40
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304841"
---
# <span data-ttu-id="6a5ca-103">Windows Autopilot용 Surface 등록 지원</span><span class="sxs-lookup"><span data-stu-id="6a5ca-103">Surface Registration Support for Windows Autopilot</span></span>

<span data-ttu-id="6a5ca-104">이제 Microsoft 지원에서 Windows Autopilot 배포를 위해 Surface 디바이스를 등록하는 간소화된 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-104">A simplified process of registering Surface devices for Windows Autopilot deployment is now available from Microsoft Support.</span></span> <span data-ttu-id="6a5ca-105">2020년 9월부터 고객 및 Microsoft CSP(클라우드 솔루션 공급자)는 Microsoft 지원에 요청을 제출하여 Surface 디바이스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-105">Beginning September 2020, customers and Microsoft Cloud Solution Providers (CSPs) can register Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="6a5ca-106">이 페이지에서는 지원되는 다음과 같은 Autopilot 등록 시나리오에 대한 요구 사항을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>
 
- <span data-ttu-id="6a5ca-107">**Surface Device Autopilot Registration**.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-107">**Surface Device Autopilot Registration**.</span></span> <span data-ttu-id="6a5ca-108">Surface 디바이스를 Windows Autopilot에 등록하기 위해 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-108">Submits request to register Surface devices into Windows Autopilot.</span></span>
- **<span data-ttu-id="6a5ca-109">Surface 디바이스 하드웨어 해시 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-109">Surface Device Hardware Hash Request.</span></span>** <span data-ttu-id="6a5ca-110">고객 또는 CSP가 Microsoft Intune 또는 Microsoft 파트너 센터를 통해 디바이스를 자체 등록하는 데 사용할 수 있는 하드웨어 해시를 제공하기 위해 Microsoft 지원에 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- **<span data-ttu-id="6a5ca-111">Surface Device Autopilot Deregistration.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-111">Surface Device Autopilot Deregistration.</span></span>** <span data-ttu-id="6a5ca-112">Windows Autopilot에서 장치 삭제 요청을 제출합니다. 일반적으로 장치 수명 종료 시나리오에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="6a5ca-113">Microsoft 지원에 등록 요청을 제출하기 전에 수집해야 하는 정보에 대한 자세한 내용은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-113">See the following table for details of the information you will need to collect prior to submitting registration requests to Microsoft Support.</span></span> <span data-ttu-id="6a5ca-114">모든 Surface 디바이스의 공식 시스템 모델 이름은 [Surface System SKU 참조를 참조합니다.](surface-system-sku-reference.md)</span><span class="sxs-lookup"><span data-stu-id="6a5ca-114">For the official System Model names of all Surface devices, refer to [Surface System SKU reference](surface-system-sku-reference.md).</span></span>
 
**<span data-ttu-id="6a5ca-115">표 1.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-115">Table 1.</span></span> <span data-ttu-id="6a5ca-116">Autopilot 등록 요청에 필요한 정보</span><span class="sxs-lookup"><span data-stu-id="6a5ca-116">Required information for Autopilot registration requests</span></span>**
 

| <span data-ttu-id="6a5ca-117">필수 정보</span><span class="sxs-lookup"><span data-stu-id="6a5ca-117">Required information</span></span>                   | <span data-ttu-id="6a5ca-118">설명</span><span class="sxs-lookup"><span data-stu-id="6a5ca-118">Description</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="6a5ca-119">Autopilot Registration</span><span class="sxs-lookup"><span data-stu-id="6a5ca-119">Autopilot Registration</span></span> | <span data-ttu-id="6a5ca-120">하드웨어 해시 요청</span><span class="sxs-lookup"><span data-stu-id="6a5ca-120">Hardware Hash Request</span></span> | <span data-ttu-id="6a5ca-121">Autopilot</span><span class="sxs-lookup"><span data-stu-id="6a5ca-121">Autopilot</span></span><br><span data-ttu-id="6a5ca-122">Deregistration</span><span class="sxs-lookup"><span data-stu-id="6a5ca-122">Deregistration</span></span> |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **<span data-ttu-id="6a5ca-123">Azure Active Directory 테넌트 ID</span><span class="sxs-lookup"><span data-stu-id="6a5ca-123">Azure Active Directory Tenant ID</span></span>**   | <span data-ttu-id="6a5ca-124">Azure Active Directory 테넌트 ID는 조직 이름 또는 도메인과 다른 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-124">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span><br> <br><span data-ttu-id="6a5ca-125">Azure Portal에 테넌트 ID 로그인을 [찾으세요.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="6a5ca-125">To find your Tenant ID sign into the Azure Portal [here](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> | <span data-ttu-id="6a5ca-126">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-126">Y</span></span>                      | <span data-ttu-id="6a5ca-127">N</span><span class="sxs-lookup"><span data-stu-id="6a5ca-127">N</span></span>                     | <span data-ttu-id="6a5ca-128">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-128">Y</span></span>                           |
| **<span data-ttu-id="6a5ca-129">Azure Active Directory 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="6a5ca-129">Azure Active Directory Domain Name</span></span>** | <span data-ttu-id="6a5ca-130">최상위 도메인 이름 예를 들어 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-130">Your top-level domain name; for example, contoso.com.</span></span>                                                                                                                                                                                                                                          | <span data-ttu-id="6a5ca-131">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-131">Y</span></span>                      | <span data-ttu-id="6a5ca-132">N</span><span class="sxs-lookup"><span data-stu-id="6a5ca-132">N</span></span>                     | <span data-ttu-id="6a5ca-133">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-133">Y</span></span>                           |
| **<span data-ttu-id="6a5ca-134">소유권 증명</span><span class="sxs-lookup"><span data-stu-id="6a5ca-134">Proof of ownership</span></span>**                 | <span data-ttu-id="6a5ca-135">원래 판매 청구서 또는 송장을 PDF 형식으로 업로드하여 소유권 증명을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-135">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="6a5ca-136">스크린샷은 수락되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-136">Screenshots are not accepted.</span></span><br> <br><span data-ttu-id="6a5ca-137">판매 청구서 또는 송장에는 다음이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-137">The bill of sale or invoice  must include the following:</span></span><br><span data-ttu-id="6a5ca-138">디바이스 일련 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-138">Device serial numbers.</span></span><br><span data-ttu-id="6a5ca-139">회사 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-139">Company name.</span></span>                                                           | <span data-ttu-id="6a5ca-140">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-140">Y</span></span>                      | <span data-ttu-id="6a5ca-141">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-141">Y</span></span>                     | <span data-ttu-id="6a5ca-142">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-142">Y</span></span>                           |
| **<span data-ttu-id="6a5ca-143">디바이스 일련 번호</span><span class="sxs-lookup"><span data-stu-id="6a5ca-143">Device serial numbers</span></span>**              | <span data-ttu-id="6a5ca-144">각 장치 일련 번호가 새 줄에 있는 CSV 형식으로 Excel 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ca-144">Upload Excel file in CSV format with each device serial number in a new line.</span></span>                                                                                                                                                                                                                  | <span data-ttu-id="6a5ca-145">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-145">Y</span></span>                      | <span data-ttu-id="6a5ca-146">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-146">Y</span></span>                     | <span data-ttu-id="6a5ca-147">Y</span><span class="sxs-lookup"><span data-stu-id="6a5ca-147">Y</span></span>                           |

 

## <span data-ttu-id="6a5ca-148">지원 요청 제출</span><span class="sxs-lookup"><span data-stu-id="6a5ca-148">Submit support requests</span></span>

  [![G<span data-ttu-id="6a5ca-149">et Autopilot Registration Support for Surface]</span><span class="sxs-lookup"><span data-stu-id="6a5ca-149">et Autopilot Registration Support for Surface]</span></span>(images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <span data-ttu-id="6a5ca-150">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="6a5ca-150">Learn more</span></span>

- [<span data-ttu-id="6a5ca-151">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="6a5ca-151">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="6a5ca-152">Windows Autopilot을 사용하여 Intune에 Windows 장치 등록</span><span class="sxs-lookup"><span data-stu-id="6a5ca-152">Enroll Windows devices in Intune by using Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [<span data-ttu-id="6a5ca-153">Windows Autopilot 개요</span><span class="sxs-lookup"><span data-stu-id="6a5ca-153">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [<span data-ttu-id="6a5ca-154">Surface 시스템 SKU 참조</span><span class="sxs-lookup"><span data-stu-id="6a5ca-154">Surface System SKU reference</span></span>](surface-system-sku-reference.md)

 
 
 

