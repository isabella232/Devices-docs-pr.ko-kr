---
title: Surface (Microsoft 배포 도구 키트)를 사용 하 여 Surface 장치를 Windows 10으로 업그레이드
description: Surface 장치에 Windows 10 업그레이드 배포를 수행 하는 방법에 대해 알아봅니다.
keywords: windows 10 surface, upgrade, 사용자 지정, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835535"
---
# <span data-ttu-id="35f9c-104">Microsoft 배포 도구 키트를 사용 하 여 Surface 장치를 Windows 10으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="35f9c-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="35f9c-105">적용 대상</span><span class="sxs-lookup"><span data-stu-id="35f9c-105">Applies to</span></span>
- <span data-ttu-id="35f9c-106">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="35f9c-106">Surface Pro 6</span></span>
- <span data-ttu-id="35f9c-107">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="35f9c-107">Surface Laptop 2</span></span>
- <span data-ttu-id="35f9c-108">Surface Go</span><span class="sxs-lookup"><span data-stu-id="35f9c-108">Surface Go</span></span>
- <span data-ttu-id="35f9c-109">LTE를 사용 하 여 Surface Go</span><span class="sxs-lookup"><span data-stu-id="35f9c-109">Surface Go with LTE</span></span>
- <span data-ttu-id="35f9c-110">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="35f9c-110">Surface Book 2</span></span>
- <span data-ttu-id="35f9c-111">Surface Pro LTE Advanced(모델 1807)</span><span class="sxs-lookup"><span data-stu-id="35f9c-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="35f9c-112">Surface Pro(모델 1796)</span><span class="sxs-lookup"><span data-stu-id="35f9c-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="35f9c-113">Surface 노트북</span><span class="sxs-lookup"><span data-stu-id="35f9c-113">Surface Laptop</span></span>
- <span data-ttu-id="35f9c-114">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="35f9c-114">Surface Studio</span></span>
- <span data-ttu-id="35f9c-115">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="35f9c-115">Surface Studio 2</span></span>
- <span data-ttu-id="35f9c-116">Surface Book</span><span class="sxs-lookup"><span data-stu-id="35f9c-116">Surface Book</span></span>
- <span data-ttu-id="35f9c-117">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="35f9c-117">Surface Pro 4</span></span>
- <span data-ttu-id="35f9c-118">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="35f9c-118">Surface 3 LTE</span></span>
- <span data-ttu-id="35f9c-119">Surface 3</span><span class="sxs-lookup"><span data-stu-id="35f9c-119">Surface 3</span></span>
- <span data-ttu-id="35f9c-120">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="35f9c-120">Surface Pro 3</span></span>
- <span data-ttu-id="35f9c-121">Surface Pro 2</span><span class="sxs-lookup"><span data-stu-id="35f9c-121">Surface Pro 2</span></span>
- <span data-ttu-id="35f9c-122">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="35f9c-122">Surface Pro</span></span>
- <span data-ttu-id="35f9c-123">Windows 10</span><span class="sxs-lookup"><span data-stu-id="35f9c-123">Windows 10</span></span>

<span data-ttu-id="35f9c-124">Reimaging 장치의 전통적인 배포 방법 외에도 Windows 8.1 또는 Windows 10을 실행 하는 Surface 장치를 업그레이드 하려는 관리자에 게 업그레이드를 배포 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f9c-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="35f9c-125">업그레이드 배포를 수행 하면 사용자, 앱 또는 구성을 제거 하지 않고도 Windows 10을 장치에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f9c-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="35f9c-126">배포 된 디바이스의 사용자는 업그레이드 전에 사용 하는 것과 동일한 앱 및 설정이 있는 장치를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f9c-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="35f9c-127">MDT를 사용 하 여 surface 장치를 업그레이드 하는 방법에 대 한 최신 정보는 [mdt로 Windows 10에서 현재 위치 업그레이드 수행](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35f9c-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

