---
title: Surface (Microsoft 배포 도구 키트)를 사용 하 여 Windows 10을 Surface devices에 배포
description: Microsoft 배포 도구 키트를 사용 하 여 Windows 10을 Surface 장치에 배포 하는 방법에 대 한 권장 절차를 안내 합니다.
keywords: windows 10 surface, 자동화, 사용자 지정, mdt
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
ms.openlocfilehash: b13b0a7fa486d2360c5e69ad1578c85a5e46a91d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835663"
---
# <span data-ttu-id="1afea-104">Microsoft 배포 도구 키트를 사용 하 여 Windows 10을 Surface 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="1afea-104">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>

**<span data-ttu-id="1afea-105">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1afea-105">Applies to</span></span>**

- <span data-ttu-id="1afea-106">Surface Studio 이상</span><span class="sxs-lookup"><span data-stu-id="1afea-106">Surface Studio and later</span></span>
- <span data-ttu-id="1afea-107">Surface Pro 4 이상</span><span class="sxs-lookup"><span data-stu-id="1afea-107">Surface Pro 4 and later</span></span>
- <span data-ttu-id="1afea-108">Surface Book 이상</span><span class="sxs-lookup"><span data-stu-id="1afea-108">Surface Book and later</span></span>
- <span data-ttu-id="1afea-109">Surface 노트북 이상</span><span class="sxs-lookup"><span data-stu-id="1afea-109">Surface Laptop and later</span></span>
- <span data-ttu-id="1afea-110">Surface Go</span><span class="sxs-lookup"><span data-stu-id="1afea-110">Surface Go</span></span>
- <span data-ttu-id="1afea-111">Surface 3</span><span class="sxs-lookup"><span data-stu-id="1afea-111">Surface 3</span></span>
- <span data-ttu-id="1afea-112">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1afea-112">Windows 10</span></span>

> [!NOTE]
> <span data-ttu-id="1afea-113">MDT는 Surface Pro X에서 지원 되지 않습니다. 자세한 내용은 [Surface Pro X 배포, 관리 및 서비스](surface-pro-arm-app-management.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1afea-113">MDT is not supported on Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

<span data-ttu-id="1afea-114">MDT 사용에 대 한 최신 정보는 MDT를 [사용 하 여 Windows 10 이미지 배포](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1afea-114">For the latest information about using MDT, refer to [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>

