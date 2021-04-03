---
title: Windows 10 Team 2020 업데이트 설치
description: Surface Hub 운영 체제 Windows 10 Team 2020 업데이트의 최신 업데이트를 다운로드합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470416"
---
# <a name="install-windows-10-team-2020-update"></a><span data-ttu-id="f1876-104">Windows 10 Team 2020 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="f1876-104">Install Windows 10 Team 2020 Update</span></span> 

<span data-ttu-id="f1876-105">Windows 10 버전 20H2를 기반으로 하는 새로운 Surface Hub 운영 체제인 **Windows 10 Team 2020 Update를**이제 Surface Hub 2S 및 원래 Surface Hub(v1)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-105">The new Surface Hub operating system, **Windows 10 Team 2020 Update**, based on Windows 10 version 20H2, is now available for Surface Hub 2S and the original Surface Hub (v1).</span></span> 

- <span data-ttu-id="f1876-106">참조: [알려진 문제: Windows 10 Team 2020 업데이트](surface-hub-2020-team-update-known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="f1876-106">See also: [Known issues: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)</span></span>

## <a name="distribution"></a><span data-ttu-id="f1876-107">배포</span><span class="sxs-lookup"><span data-stu-id="f1876-107">Distribution</span></span>

<span data-ttu-id="f1876-108">다음 방법 중 하나를 사용하여 Windows 2020 Update를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-108">You can obtain Windows 2020 Update using one of the following methods:</span></span>

- <span data-ttu-id="f1876-109">**비즈니스용 Windows 업데이트**.</span><span class="sxs-lookup"><span data-stu-id="f1876-109">**Windows Update for Business**.</span></span>
- <span data-ttu-id="f1876-110">**BMR(Bare metal recovery) 이미지**.</span><span class="sxs-lookup"><span data-stu-id="f1876-110">**Bare metal recovery (BMR) image**.</span></span> <span data-ttu-id="f1876-111">장치를 Azure Active Directory에 가입하거나 장치가 인터넷에서 업데이트를 수신하도록 허용하지 않는 고객에게 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-111">Recommended option for customers who join their devices to Azure Active Directory or don’t allow their devices to receive updates from the internet.</span></span> <span data-ttu-id="f1876-112">시작하려면 [Surface에 대한 복구 이미지 다운로드를 참조합니다.](https://support.microsoft.com/surfacerecoveryimage)</span><span class="sxs-lookup"><span data-stu-id="f1876-112">To get started, see [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>
- **<span data-ttu-id="f1876-113">Windows 업데이트.</span><span class="sxs-lookup"><span data-stu-id="f1876-113">Windows Update.</span></span>** <span data-ttu-id="f1876-114">가용성은 다음 표에 설명된 지역/국가에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-114">Availability varies by region/country, as noted in the following table:</span></span>

| <span data-ttu-id="f1876-115">단계</span><span class="sxs-lookup"><span data-stu-id="f1876-115">Phase</span></span> | <span data-ttu-id="f1876-116">국가/지역</span><span class="sxs-lookup"><span data-stu-id="f1876-116">Country/Region</span></span>                         | <span data-ttu-id="f1876-117">시작</span><span class="sxs-lookup"><span data-stu-id="f1876-117">Starting</span></span>          |
| ----- | -------------------------------------- | ----------------- |
| <span data-ttu-id="f1876-118">1</span><span class="sxs-lookup"><span data-stu-id="f1876-118">1</span></span>     | <span data-ttu-id="f1876-119">NZ, 오스트레일리아, 캐나다, 벨기에, 멕시코</span><span class="sxs-lookup"><span data-stu-id="f1876-119">NZ, Australia, Canada, Belgium, Mexico</span></span> | <span data-ttu-id="f1876-120">2020년 10월</span><span class="sxs-lookup"><span data-stu-id="f1876-120">October 2020</span></span>  |
| <span data-ttu-id="f1876-121">2</span><span class="sxs-lookup"><span data-stu-id="f1876-121">2</span></span>     | <span data-ttu-id="f1876-122">영국, 일본, 스위스, 이탈리아</span><span class="sxs-lookup"><span data-stu-id="f1876-122">UK, Japan, Switzerland, Italy</span></span>          | <span data-ttu-id="f1876-123">2020년 11월</span><span class="sxs-lookup"><span data-stu-id="f1876-123">November 2020</span></span> |
| <span data-ttu-id="f1876-124">3</span><span class="sxs-lookup"><span data-stu-id="f1876-124">3</span></span>     | <span data-ttu-id="f1876-125">독일, 네덜란드</span><span class="sxs-lookup"><span data-stu-id="f1876-125">Germany, Netherlands</span></span>                   | <span data-ttu-id="f1876-126">2021년 2월 말</span><span class="sxs-lookup"><span data-stu-id="f1876-126">Late February 2021</span></span> |
| <span data-ttu-id="f1876-127">4</span><span class="sxs-lookup"><span data-stu-id="f1876-127">4</span></span>     | <span data-ttu-id="f1876-128">Global</span><span class="sxs-lookup"><span data-stu-id="f1876-128">Global</span></span>                                 | <span data-ttu-id="f1876-129">2021년 3월 초</span><span class="sxs-lookup"><span data-stu-id="f1876-129">Early March 2021</span></span> |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a><span data-ttu-id="f1876-130">Windows 10 Team Edition 버전 1703으로 Surface Hub 서비스</span><span class="sxs-lookup"><span data-stu-id="f1876-130">Servicing Surface Hubs with Windows 10 Team Edition version 1703</span></span> 

<span data-ttu-id="f1876-131">[Windows 10 Team Edition 버전 1703에](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) 대한 전체 서비스 지원은 2021년 3월 16일까지 계속될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-131">Full servicing support for [Windows 10 Team Edition version 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) is scheduled to continue until March 16, 2021.</span></span>

### <a name="2s-devices"></a><span data-ttu-id="f1876-132">2S 장치</span><span class="sxs-lookup"><span data-stu-id="f1876-132">2S devices</span></span> 

<span data-ttu-id="f1876-133">모든 지역의 고객은 Surface Hub 2S의 초기화 및 복구에 설명된 Windows 업데이트, 비즈니스용 Windows 업데이트를 통해 또는 BMR(메탈 복구) 이미지를 사용하여 Surface [Hub 2S 장치를 2020](surface-hub-2s-recover-reset.md)업데이트로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-133">Customers in all regions can update their Surface Hub 2S devices to the 2020 Update through Windows Update, Windows Update for Business or by using the bare metal recovery (BMR) image, as explained in [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

### <a name="v1-devices"></a><span data-ttu-id="f1876-134">V1 장치</span><span class="sxs-lookup"><span data-stu-id="f1876-134">V1 devices</span></span> 

<span data-ttu-id="f1876-135">모든 지역의 고객은 Windows 업데이트, 비즈니스용 Windows 업데이트 또는 Surface Hub 복구 도구를 사용하여 Surface Hub v1 장치를 2020 업데이트로 업데이트할 [수 있습니다.](surface-hub-recovery-tool.md)</span><span class="sxs-lookup"><span data-stu-id="f1876-135">Customers in all regions can update their Surface Hub v1 devices to the 2020 Update through Windows Update, Windows Update for Business, or by [using the Surface Hub Recovery Tool](surface-hub-recovery-tool.md).</span></span> <span data-ttu-id="f1876-136">대기 업데이트를 수신하려면 KB5000749를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-136">KB5000749 must be installed in order to receive the update over-the-air.</span></span> <span data-ttu-id="f1876-137">자세한 내용은 [Surface IT Pro 블로그를 참조하세요.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371)</span><span class="sxs-lookup"><span data-stu-id="f1876-137">To learn more, see [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).</span></span>
 
## <a name="whats-new"></a><span data-ttu-id="f1876-138">새로운 What's new</span><span class="sxs-lookup"><span data-stu-id="f1876-138">What’s new</span></span>

<span data-ttu-id="f1876-139">Windows 10 Team 2020 Update는 최신 Windows 10 기능과 함께 장치 배포 및 관리성을 대대적으로 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-139">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="f1876-140">자세한 내용은 [Windows 10 Team 2020 Update의 새로운 내용을 참조합니다.](surface-hub-2020-update-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="f1876-140">To learn more, see [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).</span></span>
 
## <a name="before-you-begin"></a><span data-ttu-id="f1876-141">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="f1876-141">Before you begin</span></span>

<span data-ttu-id="f1876-142">Windows 10 Team 2020 업데이트를 설치하기 전에 장치와 연결된 BitLocker 키를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-142">Prior to installing Windows 10 Team 2020 Update, make sure you save the BitLocker key associated with your device.</span></span> 

**<span data-ttu-id="f1876-143">BitLocker 키를 수동으로 저장하려면</span><span class="sxs-lookup"><span data-stu-id="f1876-143">To manually save your BitLocker key</span></span>**

1. <span data-ttu-id="f1876-144">Surface Hub에 USB 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-144">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="f1876-145">Surface Hub에서 설정을 **열고** 메시지가 표시될 때 관리자 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-145">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="f1876-146">Update & Security Recovery **로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1876-146">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="f1876-147">**BitLocker에서**저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1876-147">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="f1876-148">BitLocker 키는 USB 드라이브의 텍스트 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1876-148">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="f1876-149">자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="f1876-149">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="f1876-150">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="f1876-150">Learn more</span></span>

- [<span data-ttu-id="f1876-151">Windows 10 Team 2020 업데이트의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="f1876-151">What's new in Windows 10 Team 2020 Update</span></span>](surface-hub-2020-update-whats-new.md)
- [<span data-ttu-id="f1876-152">Windows 10 Team 출시 업데이트</span><span class="sxs-lookup"><span data-stu-id="f1876-152">Update to the Windows 10 Team rollout</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
