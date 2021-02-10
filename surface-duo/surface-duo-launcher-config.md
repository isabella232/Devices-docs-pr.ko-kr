---
title: Surface Duo용 Microsoft Launcher 구성
description: 이 문서에서는 상업적 환경에서 관리되는 장치에 대해 Microsoft Launcher를 구성하는 방법을 요약합니다.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 1254f28ce65894c8d43d89188f22ed161cd72098
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326301"
---
# <span data-ttu-id="a028d-103">Surface Duo용 Microsoft Launcher 구성</span><span class="sxs-lookup"><span data-stu-id="a028d-103">Configure Microsoft Launcher for Surface Duo</span></span>

<span data-ttu-id="a028d-104">Surface Duo는 사용자가 휴대폰을 개인 설정하고, 이동 중의 구성을 유지하며, 모바일 장치와 PC 간에 일정, 작업, 메모 등을 원활하게 동기화할 수 있는 Android 응용 프로그램인 엔터프라이즈용 Microsoft Launcher를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-104">Surface Duo supports Microsoft Launcher for enterprise, an Android application that lets users personalize their phone, stay organized on the go, and seamlessly sync their Calendar, Task, Notes and more between mobile devices and their PCs.</span></span> <span data-ttu-id="a028d-105">실제로 Surface Duo 시작 장치는 조직의 완전히 관리되는 디바이스에서 기본 설정 환경을 정의하도록 조정하고 사용자가 이러한 회사 장치에서 환경을 개인 설정하는 몇 가지 옵션을 허용하도록 조정할 수 있는 2개의 화면 사용자 지정 버전의 Microsoft Launcher입니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-105">In fact, the Surface Duo launcher is a two-screen customized version of  Microsoft Launcher that you can adjust to define the preferred experiences on the fully managed devices for your organization as well as allow users some options to personalize their experiences on these corporate devices.</span></span> <span data-ttu-id="a028d-106">예를 들어 홈 화면에 고정할 앱을 선택하거나, 브랜드 배경 무늬를 배포하거나, 사용자가 원하는 경우 검색 표시줄을 사용하도록 설정하면서 검색 표시줄을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-106">For example, you can select which apps you want pinned to the home screen, deploy a branded wallpaper, or hide a search bar while allowing users to enable the Search bar if desired.</span></span>

## <span data-ttu-id="a028d-107">Microsoft 시작자 설정</span><span class="sxs-lookup"><span data-stu-id="a028d-107">Microsoft Launcher settings</span></span>

<span data-ttu-id="a028d-108">Microsoft 시작에는 최종 사용자 환경을 사용자 지정하기 위해 다음과 같은 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a028d-108">Microsoft Launcher includes the following settings to customize the end user experience:</span></span>


- <span data-ttu-id="a028d-109">홈 화면 앱 주문 사용자 변경 허용</span><span class="sxs-lookup"><span data-stu-id="a028d-109">Home Screen App Order User Change Allowed</span></span>
- <span data-ttu-id="a028d-110">그리드 크기 설정</span><span class="sxs-lookup"><span data-stu-id="a028d-110">Set Grid Size</span></span>
- <span data-ttu-id="a028d-111">장치 배경 무늬 설정</span><span class="sxs-lookup"><span data-stu-id="a028d-111">Set Device Wallpaper</span></span>
- <span data-ttu-id="a028d-112">장치 배경 무늬 사용자 변경 허용 설정</span><span class="sxs-lookup"><span data-stu-id="a028d-112">Set Device Wallpaper User Change Allowed</span></span>
- <span data-ttu-id="a028d-113">피드 사용</span><span class="sxs-lookup"><span data-stu-id="a028d-113">Feed Enable</span></span>
- <span data-ttu-id="a028d-114">피드 사용 사용자 변경 허용</span><span class="sxs-lookup"><span data-stu-id="a028d-114">Feed Enable User Change Allowed</span></span>
- <span data-ttu-id="a028d-115">검색 표시줄 배치</span><span class="sxs-lookup"><span data-stu-id="a028d-115">Search Bar Placement</span></span>
- <span data-ttu-id="a028d-116">검색 표시줄 배치 사용자 변경 허용</span><span class="sxs-lookup"><span data-stu-id="a028d-116">Search Bar Placement User Change Allowed</span></span>
- <span data-ttu-id="a028d-117">도킹 모드</span><span class="sxs-lookup"><span data-stu-id="a028d-117">Dock Mode</span></span>
- <span data-ttu-id="a028d-118">도킹 모드 사용자 변경 허용</span><span class="sxs-lookup"><span data-stu-id="a028d-118">Dock Mode User Change Allowed</span></span>

<span data-ttu-id="a028d-119">각 설정에 대한 자세한 내용은 [Intune을 사용하여 Android Enterprise용 Microsoft 시작 프로그램 구성을 참조합니다.](https://docs.microsoft.com/mem/intune/apps/configure-microsoft-launcher)</span><span class="sxs-lookup"><span data-stu-id="a028d-119">For full details of each setting, refer to [Configure Microsoft Launcher for Android Enterprise with Intune](https://docs.microsoft.com/mem/intune/apps/configure-microsoft-launcher).</span></span>

<span data-ttu-id="a028d-120">단계별 배포 지침은 [Intune을](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-launcher-on-android-enterprise-fully/ba-p/1482134)통해 Android Enterprise 완전히 관리되는 장치에서 Microsoft 시작 프로그램을 설정하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a028d-120">For step by step deployment instructions, refer to [How to Setup Microsoft Launcher on Android Enterprise Fully Managed Devices with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-launcher-on-android-enterprise-fully/ba-p/1482134).</span></span>
