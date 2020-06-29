---
title: Surface Hub가 업데이트를 설치하고 유지 관리 시간 외에 다시 시작할 수 있음
description: 자동 업데이트와 관련 된 Surface Hub의 문제 해결 정보
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub, 유지 관리 창, 업데이트
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836404"
---
# <span data-ttu-id="e99c7-104">Surface Hub가 업데이트를 설치하고 유지 관리 시간 외에 다시 시작할 수 있음</span><span class="sxs-lookup"><span data-stu-id="e99c7-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="e99c7-105">특정 상황에서 Surface Hub는 정기 유지 관리 기간 대신 비즈니스 시간 동안 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="e99c7-106">필요한 경우 장치가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="e99c7-107">이 장치는 프로세스가 완료 될 때까지 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="e99c7-108">유지 관리 기간이 누락 된 경우이 동작은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="e99c7-109">이는 장치가 오랜 시간 동안 만료 된 경우에만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="e99c7-110">원인</span><span class="sxs-lookup"><span data-stu-id="e99c7-110">Cause</span></span>
<span data-ttu-id="e99c7-111">비즈니스 시간 동안 Surface Hub를 계속 사용할 수 있도록 하려면 설정에 정의 된 유지 관리 기간 동안 허브가 관리 기능을 수행 하도록 구성 되어 있는지 확인 합니다 (아래 "참조" 참조).</span><span class="sxs-lookup"><span data-stu-id="e99c7-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="e99c7-112">이 유지 관리 기간 동안 허브는 Windows Update 또는 WSUS (Windows Server Update Service)를 통해 사용 가능한 업데이트를 자동으로 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="e99c7-113">업데이트가 완료 되 면 허브가 다시 시작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="e99c7-114">Surface Hub가 켜져 있지만 사용 되지 않거나 예약 되어 있지 않은 경우에만 유지 관리 기간 동안 업데이트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="e99c7-115">예를 들어 Surface Hub가 24 시간 동안 지속 되는 모임에 대해 예약 된 경우 설치 하도록 예약 된 업데이트는 다음 유지 관리 창에서 허브를 사용할 수 있을 때까지 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="e99c7-116">허브가 계속 사용 중이 고 여러 유지 관리 창이 누락 되는 경우에는 허브가 결국 업데이트를 설치 하 고 다운로드 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="e99c7-117">이는 유지 관리 기간 중 또는 외부에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="e99c7-118">다운로드 및 설치가 시작 되 면 디바이스가 다시 시작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="e99c7-119">이 문제를 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="e99c7-119">To avoid this issue</span></span>

<span data-ttu-id="e99c7-120">관리 기능을 수행 하기 위해 Surface Hub에 대해 유지 관리 시간을 따로 설정 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="e99c7-121">화면 허브를 24 시간 간격으로 예약 하거나 유지 관리 창에서 장치를 사용 하 여 업데이트를 설치 하는 동안 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="e99c7-122">예약 된 유지 관리 기간에 허브를 사용 하거나 예약 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="e99c7-123">업데이트를 위해 2 시간 윈도를 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="e99c7-124">업데이트 가용성을 제어 하는 데 사용할 수 있는 한 가지 옵션은 WSUS (Windows Server Update Service)입니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="e99c7-125">WSUS는 설치 되는 업데이트 및 시기에 대 한 제어권을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e99c7-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="e99c7-126">참조</span><span class="sxs-lookup"><span data-stu-id="e99c7-126">References</span></span> 
 
[<span data-ttu-id="e99c7-127">Surface Hub 업데이트</span><span class="sxs-lookup"><span data-stu-id="e99c7-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="e99c7-128">유지 관리 기간</span><span class="sxs-lookup"><span data-stu-id="e99c7-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="e99c7-129">WSUS(WindowsServer Update Services)를 사용하여 Windows10 업데이트 배포</span><span class="sxs-lookup"><span data-stu-id="e99c7-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 


