---
title: Windows 10 Team 2020 업데이트 설치
description: Surface Hub 운영 체제, Windows 10 Team 2020 업데이트의 최신 업데이트를 다운로드 하세요.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 90bd5714b7427880f6e73c7031c26894d55ac500
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145953"
---
# <span data-ttu-id="b223b-104">Windows 10 Team 2020 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="b223b-104">Install Windows 10 Team 2020 Update</span></span> 

<span data-ttu-id="b223b-105">Windows 10 버전 20H2를 기반으로 하는 **windows 10 Team 2020 업데이트**인 새 surface hub 운영 체제를 이제 모든 Surface hub 2S 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-105">The new Surface Hub operating system, **Windows 10 Team 2020 Update**, based on Windows 10 version 20H2, is now available for all Surface Hub 2S devices.</span></span>  

## <span data-ttu-id="b223b-106">배포</span><span class="sxs-lookup"><span data-stu-id="b223b-106">Distribution</span></span>

<span data-ttu-id="b223b-107">다음 방법 중 하나를 사용 하 여 Windows 2020 업데이트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-107">You can obtain Windows 2020 Update using one of the following methods:</span></span>

- <span data-ttu-id="b223b-108">**비즈니스용 Windows 업데이트**.</span><span class="sxs-lookup"><span data-stu-id="b223b-108">**Windows Update for Business**.</span></span>
- <span data-ttu-id="b223b-109">**완전 복구 (BMR) 이미지**</span><span class="sxs-lookup"><span data-stu-id="b223b-109">**Bare metal recovery (BMR) image**.</span></span> <span data-ttu-id="b223b-110">Azure Active Directory에 디바이스를 참가 시키는 고객이 인터넷에서 업데이트를 받을 수 있도록 허용 하지 않는 경우 권장 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-110">Recommended option for customers who join their devices to Azure Active Directory or don’t allow their devices to receive updates from the internet.</span></span> <span data-ttu-id="b223b-111">시작 하려면 [화면에 대 한 복구 이미지 다운로드](https://support.microsoft.com/surfacerecoveryimage)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b223b-111">To get started, see [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>
- **<span data-ttu-id="b223b-112">Windows 업데이트.</span><span class="sxs-lookup"><span data-stu-id="b223b-112">Windows Update.</span></span>** <span data-ttu-id="b223b-113">사용 가능 여부는 다음 표에 나와 있는 것 처럼 지역/국가에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-113">Availability varies by region/country, as noted in the following table:</span></span>

| <span data-ttu-id="b223b-114">단계</span><span class="sxs-lookup"><span data-stu-id="b223b-114">Phase</span></span> | <span data-ttu-id="b223b-115">국가/지역</span><span class="sxs-lookup"><span data-stu-id="b223b-115">Country/Region</span></span>                         | <span data-ttu-id="b223b-116">시작</span><span class="sxs-lookup"><span data-stu-id="b223b-116">Starting</span></span>          |
| ----- | -------------------------------------- | ----------------- |
| <span data-ttu-id="b223b-117">raid-1</span><span class="sxs-lookup"><span data-stu-id="b223b-117">1</span></span>     | <span data-ttu-id="b223b-118">NZ, 오스트레일리아, 캐나다, 벨기에, 멕시코</span><span class="sxs-lookup"><span data-stu-id="b223b-118">NZ, Australia, Canada, Belgium, Mexico</span></span> | <span data-ttu-id="b223b-119">2020 년 10 월 27 일</span><span class="sxs-lookup"><span data-stu-id="b223b-119">October 27, 2020</span></span>  |
| <span data-ttu-id="b223b-120">2</span><span class="sxs-lookup"><span data-stu-id="b223b-120">2</span></span>     | <span data-ttu-id="b223b-121">영국, 일본, 스위스, 이탈리아</span><span class="sxs-lookup"><span data-stu-id="b223b-121">UK, Japan, Switzerland, Italy</span></span>          | <span data-ttu-id="b223b-122">2020 년 11 월 10 일</span><span class="sxs-lookup"><span data-stu-id="b223b-122">November 10, 2020</span></span> |
| <span data-ttu-id="b223b-123">3-4</span><span class="sxs-lookup"><span data-stu-id="b223b-123">3</span></span>     | <span data-ttu-id="b223b-124">미국, 독일</span><span class="sxs-lookup"><span data-stu-id="b223b-124">US, Germany</span></span>                            | <span data-ttu-id="b223b-125">2020 년 11 월 30 일</span><span class="sxs-lookup"><span data-stu-id="b223b-125">November 30, 2020</span></span> |
| <span data-ttu-id="b223b-126">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="b223b-126">4</span></span>     | <span data-ttu-id="b223b-127">전체적</span><span class="sxs-lookup"><span data-stu-id="b223b-127">Global</span></span>                                 | <span data-ttu-id="b223b-128">2020 년 12 월 7 일</span><span class="sxs-lookup"><span data-stu-id="b223b-128">December 7, 2020</span></span>  |


## <span data-ttu-id="b223b-129">V1 장치 지원</span><span class="sxs-lookup"><span data-stu-id="b223b-129">V1 device support</span></span> 

<span data-ttu-id="b223b-130">Surface hub 2S 장치에 대 한 초기 릴리스 Windows Windows 10 Team 2020 업데이트는 Surface Hub v1 장치에 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-130">Initially released for Surface Hub 2S devices, Windows Windows 10 Team 2020 Update will soon be available for Surface Hub v1 devices.</span></span> <span data-ttu-id="b223b-131">자세히 알아보려면 [SURFACE IT Pro 블로그](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b223b-131">To learn more, see [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739).</span></span>
 
## <span data-ttu-id="b223b-132">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="b223b-132">What’s new</span></span>

<span data-ttu-id="b223b-133">Windows 10 Team 2020 업데이트는 Windows 10의 최신 기능과 함께 장치 배포 및 관리 효율성을 대폭 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-133">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> 
 
## <span data-ttu-id="b223b-134">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="b223b-134">Before you begin</span></span>

<span data-ttu-id="b223b-135">Windows 10 team 2020 업데이트를 설치 하기 전에 장치와 연결 된 BitLocker 키를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-135">Prior to installing Windows 10 team 2020 update, make sure you save the BitLocker key associated with your device.</span></span> <span data-ttu-id="b223b-136">자세히 알아보려면 [Windows 10 Team 2020 업데이트의 새로운 기능](surface-hub-2020-update-whats-new.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b223b-136">To learn more, see [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).</span></span>

**<span data-ttu-id="b223b-137">BitLocker 키를 수동으로 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="b223b-137">To manually save your BitLocker key</span></span>**

1. <span data-ttu-id="b223b-138">Surface Hub에 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-138">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="b223b-139">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-139">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="b223b-140">**& 보안**  >  **복구**업데이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-140">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="b223b-141">**BitLocker**에서 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-141">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="b223b-142">BitLocker 키가 USB 드라이브의 텍스트 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-142">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="b223b-143">자세히 알아보려면 [BitLocker 키 저장](save-bitlocker-key-surface-hub.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b223b-143">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>


## <span data-ttu-id="b223b-144">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="b223b-144">Learn more</span></span>


- [<span data-ttu-id="b223b-145">공개 미리 보기에 대 한 새로운 Surface Hub OS 업데이트를 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b223b-145">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)

