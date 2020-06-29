---
title: 비즈니스용 Microsoft 스토어 또는 Microsoft Store (Surface)를 사용 하 여 Surface 앱 배포
description: Microsoft Store for Business 또는 교육용 Microsoft Store를 사용 하 여 Surface 앱을 추가 하 고 다운로드 하는 방법과 PowerShell 및 MDT를 사용 하 여 Surface 앱을 설치 하는 방법을 알아보세요.
keywords: surface app, app, 배포, 사용자 지정
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835124"
---
# <span data-ttu-id="13bdd-104">비즈니스를 위한 Microsoft 스토어 및 교육용 Surface 앱 배포</span><span class="sxs-lookup"><span data-stu-id="13bdd-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="13bdd-105">적용 대상</span><span class="sxs-lookup"><span data-stu-id="13bdd-105">Applies to</span></span>**

- <span data-ttu-id="13bdd-106">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="13bdd-106">Surface Pro 7</span></span>
- <span data-ttu-id="13bdd-107">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="13bdd-107">Surface Laptop 3</span></span>
- <span data-ttu-id="13bdd-108">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="13bdd-108">Surface Pro 6</span></span>
- <span data-ttu-id="13bdd-109">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="13bdd-109">Surface Laptop 2</span></span>
- <span data-ttu-id="13bdd-110">Surface Go</span><span class="sxs-lookup"><span data-stu-id="13bdd-110">Surface Go</span></span>
- <span data-ttu-id="13bdd-111">LTE를 사용 하 여 Surface Go</span><span class="sxs-lookup"><span data-stu-id="13bdd-111">Surface Go with LTE</span></span>
- <span data-ttu-id="13bdd-112">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="13bdd-112">Surface Book 2</span></span>
- <span data-ttu-id="13bdd-113">Surface Pro LTE Advanced(모델 1807)</span><span class="sxs-lookup"><span data-stu-id="13bdd-113">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="13bdd-114">Surface Pro(모델 1796)</span><span class="sxs-lookup"><span data-stu-id="13bdd-114">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="13bdd-115">Surface 노트북</span><span class="sxs-lookup"><span data-stu-id="13bdd-115">Surface Laptop</span></span>
- <span data-ttu-id="13bdd-116">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="13bdd-116">Surface Studio</span></span>
- <span data-ttu-id="13bdd-117">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="13bdd-117">Surface Studio 2</span></span>
- <span data-ttu-id="13bdd-118">Surface Book</span><span class="sxs-lookup"><span data-stu-id="13bdd-118">Surface Book</span></span>
- <span data-ttu-id="13bdd-119">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="13bdd-119">Surface Pro 4</span></span>
- <span data-ttu-id="13bdd-120">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="13bdd-120">Surface 3 LTE</span></span>
- <span data-ttu-id="13bdd-121">Surface 3</span><span class="sxs-lookup"><span data-stu-id="13bdd-121">Surface 3</span></span>
- <span data-ttu-id="13bdd-122">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="13bdd-122">Surface Pro 3</span></span>


<span data-ttu-id="13bdd-123">Surface app은 다음과 같이 다양 한 Surface 관련 설정 및 옵션을 제어 하는 간단한 Microsoft 스토어 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-123">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="13bdd-124">Surface 디바이스에서 Windows 단추를 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="13bdd-124">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="13bdd-125">Surface 펜의 감도 조정</span><span class="sxs-lookup"><span data-stu-id="13bdd-125">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="13bdd-126">Surface 펜 단추 동작을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="13bdd-126">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="13bdd-127">Surface 오디오의 향상된 기능을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="13bdd-127">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="13bdd-128">장치에 대 한 지원 문서 및 정보에 대 한 빠른 액세스</span><span class="sxs-lookup"><span data-stu-id="13bdd-128">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="13bdd-129">Windows 업데이트를 사용 하는 고객은 일반적으로 자동 업데이트의 일부로 Surface 앱을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-129">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="13bdd-130">그러나 조직에서 Surface 장치에 배포할 이미지를 준비 하는 경우 각 개별 장치의 사용자가 Microsoft Store 또는 비즈니스용 Microsoft Store에서 앱을 다운로드 하 고 설치 하도록 요구 하는 대신 Surface Hub와 같은 이전에 서피스 허브를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-130">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="13bdd-131">이 문서는 Surface Pro X에는 적용 되지 않습니다. 자세한 내용은 [Surface Pro X 배포, 관리 및 서비스](surface-pro-arm-app-management.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13bdd-131">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="13bdd-132">Surface app 개요</span><span class="sxs-lookup"><span data-stu-id="13bdd-132">Surface app overview</span></span>

<span data-ttu-id="13bdd-133">Surface 앱은 [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)에서 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-133">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="13bdd-134">Microsoft Store에서 앱을 다운로드 하 고 설치할 수 있지만, 조직에서 Microsoft Store for Business를 사용 하는 경우에는 스토어의 재고에 추가 하 고 Windows 배포 프로세스의 일부로 앱을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-134">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="13bdd-135">이 문서 전체에서 이러한 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-135">These processes are discussed throughout this article.</span></span> <span data-ttu-id="13bdd-136">비즈니스용 Microsoft 스토어에 대 한 자세한 내용은 Windows TechCenter의 [비즈니스용 Microsoft 스토어](https://docs.microsoft.com/microsoft-store/) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13bdd-136">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="13bdd-137">비즈니스용 Microsoft Store 계정에 Surface 앱 추가</span><span class="sxs-lookup"><span data-stu-id="13bdd-137">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="13bdd-138">사용자가 회사의 Microsoft Store 비즈니스 계정에서 앱을 설치 하거나 배포 하기 전에 먼저 원하는 앱을 사용 하 고 비즈니스 사용자에 게 라이선스를 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-138">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="13bdd-139">아직 수행 하지 않은 경우 [비즈니스용 Microsoft 스토어 계정을](https://www.microsoft.com/business-store)만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-139">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="13bdd-140">포털에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-140">Log on to the portal.</span></span> 

3. <span data-ttu-id="13bdd-141">오프 라인 라이선스 사용: 그림 1에 나와 있는 것 처럼 **관리->스토어 설정을**클릭 하 고 **스토어의 사용자 쇼핑에 오프 라인 라이선스가 있는 앱 표시** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-141">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="13bdd-142">비즈니스용 Microsoft Store 앱 라이선스 모델에 대 한 자세한 내용은 [Microsoft Store 비즈니스 에디션 및 교육용 앱](https://docs.microsoft.com/microsoft-store/)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13bdd-142">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span><br/> <br/>
   ![오프 라인 라이선스 앱 표시 확인란](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="13bdd-144">그림 1.</span><span class="sxs-lookup"><span data-stu-id="13bdd-144">Figure 1.</span></span> <span data-ttu-id="13bdd-145">앱을 오프 라인으로 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="13bdd-145">Enable apps for offline use</span></span>*

4. <span data-ttu-id="13bdd-146">이 절차를 따라 비즈니스용 Microsoft Store 계정에 Surface 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-146">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>
    * <span data-ttu-id="13bdd-147">**상점** 메뉴를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-147">Click the **Shop** menu.</span></span>
    * <span data-ttu-id="13bdd-148">검색 상자에 **Surface app**을 입력 한 다음 검색 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-148">In the search box, type **Surface app**, and then click the search icon.</span></span>
    * <span data-ttu-id="13bdd-149">Surface 앱이 검색 결과에 표시 되 면 앱의 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-149">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    * <span data-ttu-id="13bdd-150">그림 2와 같이 선택 ( **온라인** 또는 **오프 라인**)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-150">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span><br/><br/>
    
    ![오프 라인 라이선스 모드를 선택 하 고 앱을 인벤토리에서 추가 합니다.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *<span data-ttu-id="13bdd-152">그림 2.</span><span class="sxs-lookup"><span data-stu-id="13bdd-152">Figure 2.</span></span> <span data-ttu-id="13bdd-153">오프 라인 라이선스 모드를 선택 하 고 앱을 인벤토리에서 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-153">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="13bdd-154">오프 **라인** 을 클릭 하 여 오프 라인 라이선스 모드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-154">Click **Offline** to select the Offline licensing mode.</span></span>
    * <span data-ttu-id="13bdd-155">**앱 다운로드** 를 클릭 하 여 Microsoft Store 비즈니스 에디션 인벤토리에 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-155">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="13bdd-156">그림 3에 표시 된 대로, 관리 도구를 사용 하 여 앱을 배포 하거나 개인 저장소의 회사 재고 페이지에서 다운로드할 수 있다는 메시지를 표시 하는 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-156">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
    ![오프 라인-라이선스가 부여 된 앱 승인 창](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *<span data-ttu-id="13bdd-158">그림 3.</span><span class="sxs-lookup"><span data-stu-id="13bdd-158">Figure 3.</span></span> <span data-ttu-id="13bdd-159">오프 라인에서 사용이 허가 된 앱 승인</span><span class="sxs-lookup"><span data-stu-id="13bdd-159">Offline-licensed app acknowledgement</span></span>*
    * <span data-ttu-id="13bdd-160">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-160">Click **OK**.</span></span>

## <span data-ttu-id="13bdd-161">Microsoft Store 비즈니스 에디션 계정에서 Surface 앱 다운로드</span><span class="sxs-lookup"><span data-stu-id="13bdd-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="13bdd-162">오프 라인 모드에서 Microsoft 비즈니스용 스토어 계정에 앱을 추가한 후에는 앱을 배포 공유에 대 한 .Appxbundle로 다운로드 하 고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>
1. <span data-ttu-id="13bdd-163">Microsoft Store for Business 계정에 로그온 https://businessstore.microsoft.com 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>
2. <span data-ttu-id="13bdd-164">**관리->앱 & 소프트웨어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="13bdd-165">이 문서의 [비즈니스용 Microsoft Store 계정에 surface App 추가](#add-surface-app-to-a-microsoft-store-for-business-account) 섹션에 추가한 surface 앱을 포함 하 여 회사의 모든 앱 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>
3. <span data-ttu-id="13bdd-166">**작업**에서 줄임표 (**...**)를 클릭 한 다음 Surface app의 **오프 라인 사용을 위해 다운로드** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>
4. <span data-ttu-id="13bdd-167">그림 4와 같이 선택한 앱에 대해 사용할 수 있는 선택 항목에서 원하는 **플랫폼** 및 **아키텍처** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    ![.Appxbundle 패키지의 예](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *<span data-ttu-id="13bdd-169">그림 4.</span><span class="sxs-lookup"><span data-stu-id="13bdd-169">Figure 4.</span></span> <span data-ttu-id="13bdd-170">앱에 대 한 .Appxbundle 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="13bdd-170">Download the AppxBundle package for an app</span></span>*
5. <span data-ttu-id="13bdd-171">**다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-171">Click **Download**.</span></span> <span data-ttu-id="13bdd-172">.Appxbundle 패키지가 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="13bdd-173">다운로드 한 파일의 경로를 확인 하 고이 문서의 뒷부분에 나와 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>
6. <span data-ttu-id="13bdd-174">**인코딩된 라이선스** 또는 **인코딩되지 않은 라이선스** 옵션 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="13bdd-175">인코딩된 라이선스 옵션은 Microsoft 끝점 구성 관리자와 같은 관리 도구와 함께 사용 하거나 Windows 구성 디자이너를 사용 하 여 배포 패키지를 만드는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="13bdd-176">Microsoft 배포 도구 키트 (MDT)를 포함 하 여 이미징을 기반으로 하는 DISM (배포 이미지 서비스 및 관리) 또는 배포 솔루션을 사용 하는 경우 인코딩되지 않음 라이선스 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>
7. <span data-ttu-id="13bdd-177">**생성** 을 클릭 하 여 앱에 대 한 라이선스를 생성 하 고 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="13bdd-178">이 문서의 뒷부분에 필요한 경우 라이선스 파일의 경로를 기록해 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="13bdd-179">Surface 앱과 같이 오프 라인으로 사용할 앱을 다운로드 하면 **필수 프레임 워크로**표시 된 페이지 아래쪽에 섹션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="13bdd-180">대상 컴퓨터에서 앱을 실행 하기 위해 설치 된 프레임 워크를 사용 해야 하므로 아키텍처 (x86 또는 x64)에 대해 필요한 각 프레임 워크에 대해 다운로드 프로세스를 반복 하 고이 문서의 뒷부분에 설명 된 Windows 배포의 일부로이를 포함 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="13bdd-181">그림 5는 Surface 앱에 대 한 필수 프레임 워크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

![Surface 앱에 대 한 필수 프레임 워크](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*<span data-ttu-id="13bdd-183">그림 5.</span><span class="sxs-lookup"><span data-stu-id="13bdd-183">Figure 5.</span></span> <span data-ttu-id="13bdd-184">Surface 앱에 대 한 필수 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="13bdd-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="13bdd-185">앱이 업데이트 되 면 Surface app 및 필수 프레임 워크의 버전 번호가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="13bdd-186">Microsoft Store for Business의 Surface app 및 각 프레임 워크의 최신 버전을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="13bdd-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="13bdd-187">비즈니스를 위해 Microsoft Store에서 제공 하는 Surface app 및 추천 프레임 워크 버전을 항상 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="13bdd-188">오래 된 프레임 워크 나 올바르지 않은 버전을 사용 하면 오류 또는 응용 프로그램 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="13bdd-189">Surface 앱에 대 한 필수 프레임 워크를 다운로드 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="13bdd-189">To download the required frameworks for the Surface app, follow these steps:</span></span>
1. <span data-ttu-id="13bdd-190">**140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**에서 **다운로드** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="13bdd-191">140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe를 다운로드 합니다. 지정 된 폴더에 Appx 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>
2. <span data-ttu-id="13bdd-192">**MICROSOFT net.tcp. 1.1 _ 1.1.23406**에서 **다운로드** 단추를 클릭 합니다. 0_x64__8wekyb3d8bbwe.</span><span class="sxs-lookup"><span data-stu-id="13bdd-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="13bdd-193">이렇게 하면 1.1.23406 _. m a t. m a t. m a t. m a t. 0_x64__8wekyb3d8bbwe .Appx 파일이 지정 된 폴더로 다운로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="13bdd-194">Surface 장치에 각 프레임 워크의 64 비트 (x64) 버전만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="13bdd-195">Surface 디바이스는 기본 64 비트 UEFI 장치 이며 32 비트 프레임 워크를 필요로 하는 32 비트 (x86) 버전의 Windows와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="13bdd-196">PowerShell을 사용 하 여 컴퓨터에 Surface 앱 설치</span><span class="sxs-lookup"><span data-stu-id="13bdd-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="13bdd-197">다음 절차는 Surface 앱을 컴퓨터에 프로 비전 하 고 나중에 컴퓨터에서 만든 모든 사용자 계정에서 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>
1. <span data-ttu-id="13bdd-198">이 문서의 [Microsoft Store 비즈니스 계정에서 surface 앱을 다운로드 하는 방법](#download-surface-app-from-a-microsoft-store-for-business-account) 섹션에 설명 된 절차를 사용 하 여 Surface app .appxbundle 및 라이선스 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 
2. <span data-ttu-id="13bdd-199">관리자 권한 PowerShell 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="13bdd-200">관리자로 PowerShell을 실행 하지 않는 경우에는 앱을 설치 하는 데 필요한 권한이 세션에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="13bdd-201">관리자 권한 PowerShell 세션에서 다음 명령을 복사한 다음 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-201">In the elevated PowerShell session, copy and paste the following command:</span></span>
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="13bdd-202">`<DownloadPath>`비즈니스용 Microsoft Store 계정에서 .appxbundle 및 라이선스 파일을 다운로드 한 폴더는 어디에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="13bdd-203">예를 들어 파일을 c:\Temp로 다운로드 한 경우 실행 하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13bdd-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
