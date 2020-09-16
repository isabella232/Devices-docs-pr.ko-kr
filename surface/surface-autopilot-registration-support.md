---
title: Windows Autopilot에 대 한 Surface Registration 지원
description: 이 문서에서는 Microsoft 지원에 Autopilot 등록 요청을 제출 하기 위한 요구 사항을 설명 합니다.
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
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016482"
---
# <span data-ttu-id="045b3-103">Windows Autopilot에 대 한 Surface Registration 지원</span><span class="sxs-lookup"><span data-stu-id="045b3-103">Surface Registration Support for Windows Autopilot</span></span>

<span data-ttu-id="045b3-104">이제 Microsoft 지원에서 Windows Autopilot 배포에 대 한 Surface 디바이스를 등록 하는 간단한 프로세스가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-104">A simplified process of registering Surface devices for Windows Autopilot deployment is now available from Microsoft Support.</span></span> <span data-ttu-id="045b3-105">2020 년 9 월부터 고객 및 Microsoft Csp (클라우드 솔루션 공급자)는 Microsoft 지원에 요청을 제출 하 여 Surface 디바이스를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-105">Beginning September 2020, customers and Microsoft Cloud Solution Providers (CSPs) can register Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="045b3-106">이 페이지에서는 다음과 같이 지원 되는 Autopilot 등록 시나리오에 대 한 요구 사항을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>
 

- <span data-ttu-id="045b3-107">**Surface Device Autopilot 등록**.</span><span class="sxs-lookup"><span data-stu-id="045b3-107">**Surface Device Autopilot Registration**.</span></span> <span data-ttu-id="045b3-108">Surface 디바이스 등록 요청을 Windows Autopilot에 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-108">Submits request to register Surface devices into Windows Autopilot.</span></span>
- **<span data-ttu-id="045b3-109">Surface 디바이스 하드웨어 해시 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-109">Surface Device Hardware Hash Request.</span></span>** <span data-ttu-id="045b3-110">고객 또는 Csp가 Microsoft Intune 또는 Microsoft 파트너 센터를 통해 자체 등록 디바이스에 사용할 수 있는 하드웨어 해시를 제공 하기 위해 Microsoft Support에 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- **<span data-ttu-id="045b3-111">Surface 디바이스 Autopilot 등록 취소.</span><span class="sxs-lookup"><span data-stu-id="045b3-111">Surface Device Autopilot Deregistration.</span></span>** <span data-ttu-id="045b3-112">Windows Autopilot에서 장치 삭제 요청을 제출 합니다. 일반적으로 장치 종료 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="045b3-113">Microsoft 지원에 등록 요청을 제출 하기 전에 수집 해야 하는 정보에 대 한 자세한 내용은 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="045b3-113">See the following table for details of the information you will need to collect prior to submitting registration requests to Microsoft Support.</span></span>
 
**<span data-ttu-id="045b3-114">표 1.</span><span class="sxs-lookup"><span data-stu-id="045b3-114">Table 1.</span></span> <span data-ttu-id="045b3-115">Autopilot 등록 요청에 필요한 정보</span><span class="sxs-lookup"><span data-stu-id="045b3-115">Required information for Autopilot registration requests</span></span>**
 

| <span data-ttu-id="045b3-116">필수 정보</span><span class="sxs-lookup"><span data-stu-id="045b3-116">Required information</span></span>                   | <span data-ttu-id="045b3-117">설명</span><span class="sxs-lookup"><span data-stu-id="045b3-117">Description</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="045b3-118">Autopilot 등록</span><span class="sxs-lookup"><span data-stu-id="045b3-118">Autopilot Registration</span></span> | <span data-ttu-id="045b3-119">하드웨어 해시 요청</span><span class="sxs-lookup"><span data-stu-id="045b3-119">Hardware Hash Request</span></span> | <span data-ttu-id="045b3-120">Autopilot</span><span class="sxs-lookup"><span data-stu-id="045b3-120">Autopilot</span></span><br><span data-ttu-id="045b3-121">취소</span><span class="sxs-lookup"><span data-stu-id="045b3-121">Deregistration</span></span> |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **<span data-ttu-id="045b3-122">Azure Active Directory 테 넌 트 ID</span><span class="sxs-lookup"><span data-stu-id="045b3-122">Azure Active Directory Tenant ID</span></span>**   | <span data-ttu-id="045b3-123">Azure Active Directory 테 넌 트 ID가 조직 이름 또는 도메인과는 다른 전역 고유 식별자 (GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-123">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span><br> <br><span data-ttu-id="045b3-124">테 넌 트 ID를 찾으려면 [여기](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)에서 Azure 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-124">To find your Tenant ID sign into the Azure Portal [here](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> | <span data-ttu-id="045b3-125">예</span><span class="sxs-lookup"><span data-stu-id="045b3-125">Y</span></span>                      | <span data-ttu-id="045b3-126">N</span><span class="sxs-lookup"><span data-stu-id="045b3-126">N</span></span>                     | <span data-ttu-id="045b3-127">예</span><span class="sxs-lookup"><span data-stu-id="045b3-127">Y</span></span>                           |
| **<span data-ttu-id="045b3-128">Azure Active Directory 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="045b3-128">Azure Active Directory Domain Name</span></span>** | <span data-ttu-id="045b3-129">최상위 수준의 도메인 이름 예를 contoso.com.</span><span class="sxs-lookup"><span data-stu-id="045b3-129">Your top-level domain name; for example, contoso.com.</span></span>                                                                                                                                                                                                                                          | <span data-ttu-id="045b3-130">예</span><span class="sxs-lookup"><span data-stu-id="045b3-130">Y</span></span>                      | <span data-ttu-id="045b3-131">N</span><span class="sxs-lookup"><span data-stu-id="045b3-131">N</span></span>                     | <span data-ttu-id="045b3-132">예</span><span class="sxs-lookup"><span data-stu-id="045b3-132">Y</span></span>                           |
| **<span data-ttu-id="045b3-133">소유권 증명</span><span class="sxs-lookup"><span data-stu-id="045b3-133">Proof of ownership</span></span>**                 | <span data-ttu-id="045b3-134">원본 판매 증서 또는 송장을 PDF 형식으로 업로드 하 여 소유권 증명을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-134">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="045b3-135">스크린샷이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-135">Screenshots are not accepted.</span></span><br> <br><span data-ttu-id="045b3-136">할인 증서 또는 송장에는 다음이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-136">The bill of sale or invoice  must include the following:</span></span><br><span data-ttu-id="045b3-137">장치 일련 번호.</span><span class="sxs-lookup"><span data-stu-id="045b3-137">Device serial numbers.</span></span><br><span data-ttu-id="045b3-138">회사 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-138">Company name.</span></span>                                                           | <span data-ttu-id="045b3-139">예</span><span class="sxs-lookup"><span data-stu-id="045b3-139">Y</span></span>                      | <span data-ttu-id="045b3-140">Y</span><span class="sxs-lookup"><span data-stu-id="045b3-140">Y</span></span>                     | <span data-ttu-id="045b3-141">예</span><span class="sxs-lookup"><span data-stu-id="045b3-141">Y</span></span>                           |
| **<span data-ttu-id="045b3-142">장치 일련 번호</span><span class="sxs-lookup"><span data-stu-id="045b3-142">Device serial numbers</span></span>**              | <span data-ttu-id="045b3-143">각 장치 일련 번호를 새 줄에 포함 하 여 CSV 형식으로 Excel 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="045b3-143">Upload Excel file in CSV format with each device serial number in a new line.</span></span>                                                                                                                                                                                                                  | <span data-ttu-id="045b3-144">예</span><span class="sxs-lookup"><span data-stu-id="045b3-144">Y</span></span>                      | <span data-ttu-id="045b3-145">Y</span><span class="sxs-lookup"><span data-stu-id="045b3-145">Y</span></span>                     | <span data-ttu-id="045b3-146">예</span><span class="sxs-lookup"><span data-stu-id="045b3-146">Y</span></span>                           |

 

## <span data-ttu-id="045b3-147">지원 요청 제출</span><span class="sxs-lookup"><span data-stu-id="045b3-147">Submit support requests</span></span>

  [![G<span data-ttu-id="045b3-148">et Autopilot 등록 지원 화면]</span><span class="sxs-lookup"><span data-stu-id="045b3-148">et Autopilot Registration Support for Surface]</span></span>(images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <span data-ttu-id="045b3-149">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="045b3-149">Learn more</span></span>

- [<span data-ttu-id="045b3-150">Windows Autopilot 및 Surface 디바이스</span><span class="sxs-lookup"><span data-stu-id="045b3-150">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="045b3-151">Windows Autopilot을 사용하여 Intune에 Windows 장치 등록</span><span class="sxs-lookup"><span data-stu-id="045b3-151">Enroll Windows devices in Intune by using Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [<span data-ttu-id="045b3-152">Windows Autopilot 개요</span><span class="sxs-lookup"><span data-stu-id="045b3-152">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

