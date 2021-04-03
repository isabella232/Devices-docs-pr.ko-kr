---
title: Microsoft Surface Hub에 앱 설치
description: 관리자는 Microsoft Store 또는 비즈니스용 Microsoft Store에서 앱을 설치할 수 있습니다.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: 앱 설치, Microsoft Store, 비즈니스용 Microsoft Store
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a6e791defed4970b9a1940580b5f80bbe4f006a4
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470476"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a><span data-ttu-id="f3777-104">Microsoft Surface Hub에 앱 설치</span><span class="sxs-lookup"><span data-stu-id="f3777-104">Install apps on your Microsoft Surface Hub</span></span>

<span data-ttu-id="f3777-105">팀 또는 조직의 요구 사항에 맞게 Surface Hub에 추가 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-105">You can install additional apps on your Surface Hub to fit your team or organization's needs.</span></span> <span data-ttu-id="f3777-106">앱을 개발 및 테스트하거나 릴리스된 앱을 배포할지에 따라 다양한 방법으로 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-106">There are different methods for installing apps depending on whether you are developing and testing an app, or deploying a released app.</span></span> <span data-ttu-id="f3777-107">이 항목에서는 각 시나리오에 대한 앱을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-107">This topic describes methods for installing apps for either scenario.</span></span>

<span data-ttu-id="f3777-108">Surface Hub의 앱에 대해 알아야 하는 몇 가지 사항:</span><span class="sxs-lookup"><span data-stu-id="f3777-108">A few things to know about apps on Surface Hub:</span></span>
- <span data-ttu-id="f3777-109">Surface Hub에서는 [UWP(유니버설 Windows 플랫폼) 앱](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-109">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="f3777-110">[Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter)를 사용하여 만든 앱은 Surface Hub에서 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-110">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="f3777-111">앱은 [유니버설 장치 패밀리](https://msdn.microsoft.com/library/windows/apps/dn894631) 또는 Windows Team 장치 패밀리를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-111">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="f3777-112">Surface Hub는 [](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 비즈니스용 Microsoft Store의 오프라인 라이선스 [앱만 지원합니다.](https://businessstore.microsoft.com/store)</span><span class="sxs-lookup"><span data-stu-id="f3777-112">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="f3777-113">기본적으로 앱은 설치할 스토어 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-113">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="f3777-114">테스트 및 개발 중에 디바이스를 개발자 모드로 전환하여 개발자 서명된 UWP 앱을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-114">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="f3777-115">Microsoft Store에 앱을 제출할 때 개발자는 Surface Hub에서 앱을 실행할 수 있도록 디바이스 패밀리 가용성 및 조직 라이선스 옵션을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-115">When submitting an app to the Microsoft Store, developers need to set Device family availability and Organizational licensing options to make sure an app will be available to run on Surface Hub.</span></span>
- <span data-ttu-id="f3777-116">Surface Hub에 앱을 설치하려면 관리자 자격 증명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-116">You need admin credentials to install apps on your Surface Hub.</span></span> <span data-ttu-id="f3777-117">디바이스가 회의실 같은 공용 공간에서 사용하도록 설계되므로 사용자는 앱을 다운로드하고 설치하기 위해 Microsoft Store에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-117">Since the device is designed to be used in communal spaces like meeting rooms, people can't access the Microsoft Store to download and install apps.</span></span>


## <a name="develop-and-test-apps"></a><span data-ttu-id="f3777-118">앱 개발 및 테스트</span><span class="sxs-lookup"><span data-stu-id="f3777-118">Develop and test apps</span></span>
<span data-ttu-id="f3777-119">자체 앱을 개발하는 동안 Surface Hub에서 앱을 테스트할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-119">While you're developing your own app, there are a few options for testing apps on Surface Hub.</span></span>

### <a name="developer-mode"></a><span data-ttu-id="f3777-120">개발자 모드</span><span class="sxs-lookup"><span data-stu-id="f3777-120">Developer Mode</span></span>
<span data-ttu-id="f3777-121">기본적으로 Surface Hub는 Microsoft Store에 게시되고 여기에서 서명된 UWP 앱만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-121">By default, Surface Hub only runs UWP apps that have been published to and signed by the Microsoft Store.</span></span> <span data-ttu-id="f3777-122">Microsoft Store에 제출된 앱은 [앱 인증 프로세스](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process)의 일부로 보안 및 준수 테스트를 통과하므로, 이를 통해 악성 앱으로부터 Surface Hub를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-122">Apps submitted to the Microsoft Store go through security and compliance tests as part of the [app certification process](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process), so this helps safeguard your Surface Hub against malicious apps.</span></span>
 
<span data-ttu-id="f3777-123">개발자 모드를 사용하도록 설정하여 개발자 서명된 UWP 앱을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-123">By enabling developer mode, you can also install developer-signed UWP apps.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="f3777-124">개발자 모드를 사용하도록 설정한 후 사용하지 않도록 설정하려면 Surface Hub를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-124">After developer mode has been enabled, you will need to reset the Surface Hub to disable it.</span></span> <span data-ttu-id="f3777-125">디바이스를 초기화하면 모든 로컬 사용자 파일과 구성이 제거되고 Windows가 다시 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-125">Resetting the device removes all local user files and configurations and then reinstalls Windows.</span></span>

**<span data-ttu-id="f3777-126">개발자 모드를 켜려면</span><span class="sxs-lookup"><span data-stu-id="f3777-126">To turn on developer mode</span></span>** 
1. <span data-ttu-id="f3777-127">Surface Hub에서 **설정**을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-127">From your Surface Hub, start **Settings**.</span></span>
2. <span data-ttu-id="f3777-128">메시지가 표시되면 디바이스 관리자 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-128">Type the device admin credentials when prompted.</span></span>
3. <span data-ttu-id="f3777-129">**업데이트 및 보안** > **개발자용**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-129">Navigate to **Update & security** > **For developers**.</span></span>
4. <span data-ttu-id="f3777-130">**개발자 모드**를 선택하고 경고 프롬프트를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-130">Select **Developer mode** and accept the warning prompt.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="f3777-131">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3777-131">Visual Studio</span></span>
<span data-ttu-id="f3777-132">개발하는 동안 Surface Hub에서 앱을 테스트하는 가장 간편한 방법은 Visual Studio를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-132">During development, the easiest way to test your app on a Surface Hub is using Visual Studio.</span></span> <span data-ttu-id="f3777-133">Visual Studio의 원격 디버깅 기능을 통해 앱을 광범위하게 배포하기 전에 앱에서 문제를 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-133">Visual Studio's remote debugging feature helps you discover issues in your app before deploying it broadly.</span></span> <span data-ttu-id="f3777-134">자세한 내용은 [Visual Studio를 사용하여 Surface Hub 앱 테스트](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-134">For more information, see [Test Surface Hub apps using Visual Studio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).</span></span>

### <a name="provisioning-package"></a><span data-ttu-id="f3777-135">프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="f3777-135">Provisioning package</span></span>
<span data-ttu-id="f3777-136">Visual Studio를 사용하여 테스트 인증서를 사용하여 서명된 UWP 앱에 대한 [앱 패키지를 만듭니다](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3777-136">Use Visual Studio to [create an app package](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) for your UWP app, signed using a test certificate.</span></span> <span data-ttu-id="f3777-137">그런 다음 Windows ICD(이미징 및 구성 디자이너)를 사용하여 앱 패키지가 포함된 프로비저닝 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-137">Then use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package.</span></span> <span data-ttu-id="f3777-138">자세한 내용은 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-138">For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).</span></span>


## <a name="submit-apps-to-the-microsoft-store"></a><span data-ttu-id="f3777-139">Microsoft Store에 앱 제출</span><span class="sxs-lookup"><span data-stu-id="f3777-139">Submit apps to the Microsoft Store</span></span>
<span data-ttu-id="f3777-140">앱을 릴리스할 수 있게 되면 개발자는 앱을 Microsoft Store에 제출하여 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-140">Once an app is ready for release, developers need to submit and publish it to the Microsoft Store.</span></span> <span data-ttu-id="f3777-141">자세한 내용은 [Windows 앱 게시](https://developer.microsoft.com/store/publish-apps)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-141">For more information, see [Publish Windows apps](https://developer.microsoft.com/store/publish-apps).</span></span>

<span data-ttu-id="f3777-142">앱을 제출하는 동안 개발자는 **디바이스 패밀리 가용성** 및 **조직 라이선스** 옵션을 설정하여 Surface Hub에서 앱을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-142">During app submission, developers need to set **Device family availability** and **Organizational licensing** options to make sure the app will be available to run on Surface Hub.</span></span>

**<span data-ttu-id="f3777-143">디바이스 패밀리 가용성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f3777-143">To set device family availability</span></span>**

1. <span data-ttu-id="f3777-144">[Windows 개발자 센터](https://developer.microsoft.com)에서 앱 제출 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-144">On the [Windows Dev Center](https://developer.microsoft.com), navigate to your app submission page.</span></span>

2. <span data-ttu-id="f3777-145">**패키지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-145">Select **Packages**.</span></span>
3. <span data-ttu-id="f3777-146">**Device family availability**(디바이스 패밀리 가용성)에서 다음 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-146">Under **Device family availability**, select these options:</span></span>
    
    - **<span data-ttu-id="f3777-147">Windows 10 Team</span><span class="sxs-lookup"><span data-stu-id="f3777-147">Windows 10 Team</span></span>**
    - **<span data-ttu-id="f3777-148">Microsoft에서 이후 디바이스 패밀리에 앱을 제공할지 여부를 결정하도록 허용</span><span class="sxs-lookup"><span data-stu-id="f3777-148">Let Microsoft decide whether to make the app available to any future device families</span></span>**
  
   ![디바이스 패밀리 가용성 페이지를 보여 주는 이미지 - Microsoft Store 앱 제출 프로세스의 일부](images/device-family.png)  
    
   <span data-ttu-id="f3777-150">자세한 내용은 [디바이스 패밀리 가용성](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-150">For more information, see [Device family availability](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).</span></span>

**<span data-ttu-id="f3777-151">조직 라이선스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f3777-151">To set organizational licensing</span></span>**

1. <span data-ttu-id="f3777-152">[Windows 개발자 센터](https://developer.microsoft.com)에서 앱 제출 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-152">On the [Windows Dev Center](https://developer.microsoft.com), navigate to your app submission page.</span></span>

2. <span data-ttu-id="f3777-153">**가격 책정 및 가용성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-153">Select **Pricing and availability**.</span></span>

3. <span data-ttu-id="f3777-154">조직 라이선스에서 **Allow disconnected (offline) licensing for organizations**(조직에 연결이 끊어진 (오프라인) 라이선스 허용)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-154">Under Organizational licensing, select **Allow disconnected (offline) licensing for organizations**.</span></span>

   ![조직 라이선스 페이지를 보여 주는 이미지 - Microsoft Store 앱 제출 프로세스의 일부](images/sh-org-licensing.png)

   > [!NOTE]
   > <span data-ttu-id="f3777-156">**Make my app available to organizations with Store-managed (online) licensing and distribution**(스토어에서 관리하는 (온라인) 라이선싱 및 배포를 보유한 조직이 내 앱을 사용할 수 있도록 설정)이 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-156">**Make my app available to organizations with Store-managed (online) licensing and distribution** is selected by default.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f3777-157">개발자는 스토어에서 앱을 광범위하게 사용할 수 있도록 설정하지 않고 기간 업무 앱을 엔터프라이즈에 직접 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-157">Developers can also publish line-of-business apps directly to enterprises without making them broadly available in the Store.</span></span> <span data-ttu-id="f3777-158">자세한 내용은 [엔터프라이즈에 LOB 앱 배포](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-158">For more information, see [Distribute LOB apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).</span></span>

   <span data-ttu-id="f3777-159">자세한 내용은 [조직 라이선스 옵션](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-159">For more information, see [Organizational licensing options](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).</span></span>


## <a name="deploy-released-apps"></a><span data-ttu-id="f3777-160">릴리스된 앱 배포</span><span class="sxs-lookup"><span data-stu-id="f3777-160">Deploy released apps</span></span>

<span data-ttu-id="f3777-161">Microsoft Store에 릴리스된 앱을 몇 대의 디바이스에서 평가할지, 아니면 조직에 광범위하게 배포할지 여부에 따라 해당 앱을 설치할 수 있는 여러 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-161">There are several options for installing apps that have been released to the Microsoft Store, depending on whether you want to evaluate them on a few devices, or deploy them broadly to your organization.</span></span>

<span data-ttu-id="f3777-162">릴리스된 앱을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="f3777-162">To install released apps:</span></span>
- <span data-ttu-id="f3777-163">Microsoft Store 앱을 사용하여 앱을 다운로드하거나,</span><span class="sxs-lookup"><span data-stu-id="f3777-163">Download the app using the Microsoft Store app, or</span></span>
- <span data-ttu-id="f3777-164">비즈니스용 Microsoft Store에서 앱 패키지를 다운로드하고 프로비저닝 패키지 또는 지원되는 MDM 공급자를 사용하여 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-164">Download the app package from the Microsoft Store for Business, and distribute it using a provisioning package or a supported MDM provider.</span></span>

### <a name="microsoft-store-app"></a><span data-ttu-id="f3777-165">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="f3777-165">Microsoft Store app</span></span>
<span data-ttu-id="f3777-166">Microsoft Store에 릴리스된 앱을 평가하려면 Surface Hub의 Microsoft Store 앱을 사용하여 앱을 찾고 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-166">To evaluate apps released on the Microsoft Store, use the Microsoft Store app on the Surface Hub to browse and download apps.</span></span>

> [!NOTE]
> <span data-ttu-id="f3777-167">조직에 앱을 대규모로 배포하는 방법으로는 Microsoft Store 앱을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-167">Using the Microsoft Store app is not the recommended method of deploying apps at scale to your organization:</span></span>
> - <span data-ttu-id="f3777-168">앱을 다운로드하려면 Microsoft 계정 또는 조직 계정으로 Microsoft Store 앱에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-168">To download apps, you must sign in to the Microsoft Store app with a Microsoft account or organizational account.</span></span> <span data-ttu-id="f3777-169">그러나 한 번에 최대 10대의 디바이스에만 한 계정을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-169">However, you can only connect an account to a maximum of 10 devices at once.</span></span> <span data-ttu-id="f3777-170">Surface Hub 수가 10대를 초과할 경우에는 여러 계정을 만들거나 앱 설치 과정 사이에 계정에서 디바이스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-170">If you have more than 10 Surface Hubs, you will need to create multiple accounts or remove devices from your account between app installations.</span></span>
> - <span data-ttu-id="f3777-171">앱을 설치하려면 소유한 각 Surface Hub에서 Microsoft Store 앱에 수동으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-171">To install apps, you will need to manually sign in to the Microsoft Store app on each Surface Hub you own.</span></span>

**<span data-ttu-id="f3777-172">Surface Hub에서 Microsoft Store를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="f3777-172">To browse the Microsoft Store on Surface Hub</span></span>** 
1. <span data-ttu-id="f3777-173">Surface Hub에서 **설정**을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-173">From your Surface Hub, start **Settings**.</span></span>
2. <span data-ttu-id="f3777-174">메시지가 표시되면 디바이스 관리자 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-174">Type the device admin credentials when prompted.</span></span>
3. <span data-ttu-id="f3777-175">**이 장치** > **앱 및 기능**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-175">Navigate to **This device** > **Apps & features**.</span></span>
4. <span data-ttu-id="f3777-176">**스토어 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-176">Select **Open Store**.</span></span>

### <a name="download-app-packages-from-microsoft-store-for-business"></a><span data-ttu-id="f3777-177">비즈니스용 Microsoft Store에서 앱 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="f3777-177">Download app packages from Microsoft Store for Business</span></span>
<span data-ttu-id="f3777-178">앱 패키지를 다운로드하려면 Surface Hub에 앱을 설치하고 [비즈니스용 Microsoft Store](https://www.microsoft.com/business-store)를 방문해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-178">To download the app package you need to install apps on your Surface Hub, visit the [Microsoft Store for Business](https://www.microsoft.com/business-store).</span></span> <span data-ttu-id="f3777-179">비즈니스용 Store에서는 Surface Hub를 포함하여 조직의 Windows10 디바이스용 앱을 찾고 구매하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-179">The Store for Business is where you can find, acquire, and manage apps for the Windows 10 devices in your organization, including Surface Hub.</span></span>
 
> [!NOTE]
> <span data-ttu-id="f3777-180">현재 Surface Hub는 비즈니스용 Store를 통해 제공되는 오프라인 사용이 허가된 앱만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-180">Currently, Surface Hub only supports offline-licensed apps available through the Store for Business.</span></span> <span data-ttu-id="f3777-181">앱 개발자는 앱을 제출할 때 오프라인 라이선스 가용성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-181">App developers set offline-license availability when they submit apps.</span></span>

<span data-ttu-id="f3777-182">원하는 앱을 찾아서 구매하고 다음을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-182">Find and acquire the app you want, then download:</span></span>
- <span data-ttu-id="f3777-183">오프라인 사용이 허가된 앱 패키지(.appx 또는 .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="f3777-183">The offline-licensed app package (either an .appx or an .appxbundle)</span></span>
- <span data-ttu-id="f3777-184">*인코드되지 않은* 라이선스 파일(프로비저닝 패키지를 사용하여 앱을 설치하는 경우)</span><span class="sxs-lookup"><span data-stu-id="f3777-184">The *unencoded* license file (if you're using provisioning packages to install the app)</span></span>
- <span data-ttu-id="f3777-185">*인코드된* 라이선스 파일(MDM을 사용하여 앱을 배포하는 경우)</span><span class="sxs-lookup"><span data-stu-id="f3777-185">The *encoded* license file (if you're using MDM to distribute the app)</span></span>
- <span data-ttu-id="f3777-186">필요한 모든 종속성 파일</span><span class="sxs-lookup"><span data-stu-id="f3777-186">Any necessary dependency files</span></span>

<span data-ttu-id="f3777-187">자세한 내용은 [오프라인 사용이 허가된 앱 다운로드](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-187">For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).</span></span>

### <a name="provisioning-package"></a><span data-ttu-id="f3777-188">프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="f3777-188">Provisioning package</span></span>
<span data-ttu-id="f3777-189">프로비저닝 패키지를 사용하여 비즈니스용 Store에서 다운로드한 오프라인 사용이 허가된 앱을 몇몇 Surface Hub에 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-189">You can manually install the offline-licensed apps that you downloaded from the Store for Business on a few Surface Hubs using provisioning packages.</span></span> <span data-ttu-id="f3777-190">Windows ICD(이미징 및 구성 디자이너)를 사용하여 비즈니스용 Store에서 다운로드한 앱 패키지와 *인코드되지 않은* 라이선스 파일이 포함된 프로비저닝 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-190">Use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package and *unencoded* license file that you downloaded from the Store for Business.</span></span> <span data-ttu-id="f3777-191">자세한 내용은 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-191">For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).</span></span>

### <a name="supported-mdm-provider"></a><span data-ttu-id="f3777-192">지원되는 MDM 공급자</span><span class="sxs-lookup"><span data-stu-id="f3777-192">Supported MDM provider</span></span>
<span data-ttu-id="f3777-193">조직에서 많은 Surface Hub에 앱을 배포하려면 지원되는 MDM 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-193">To deploy apps to a large number of Surface Hubs in your organization, use a supported MDM provider.</span></span> <span data-ttu-id="f3777-194">아래 표는 오프라인 사용이 허가된 앱 패키지 배포를 지원하는 MDM 공급자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-194">The table below shows which MDM providers support deploying offline-licensed app packages.</span></span>

| <span data-ttu-id="f3777-195">MDM 공급자</span><span class="sxs-lookup"><span data-stu-id="f3777-195">MDM provider</span></span>                | <span data-ttu-id="f3777-196">오프라인 사용이 허가된 앱 패키지 지원</span><span class="sxs-lookup"><span data-stu-id="f3777-196">Supports offline-licensed app packages</span></span> |
|-----------------------------|----------------------------------------|
| <span data-ttu-id="f3777-197">Configuration Manager가 있는 사내 MDM(버전 1602부터)</span><span class="sxs-lookup"><span data-stu-id="f3777-197">On-premises MDM with  Configuration Manager (beginning in version 1602)</span></span> | <span data-ttu-id="f3777-198">예</span><span class="sxs-lookup"><span data-stu-id="f3777-198">Yes</span></span> |
|
| <span data-ttu-id="f3777-199">타사 MDM 공급자</span><span class="sxs-lookup"><span data-stu-id="f3777-199">Third-party MDM provider</span></span>    | <span data-ttu-id="f3777-200">MDM 공급자가 오프라인 사용이 허가된 앱 패키지 배포를 지원하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-200">Check to make sure your MDM provider supports deploying offline-licensed app packages.</span></span> |

**<span data-ttu-id="f3777-201">Microsoft Endpoint Configuration Manager를 사용하여 원격으로 앱을 배포하려면</span><span class="sxs-lookup"><span data-stu-id="f3777-201">To deploy apps remotely using Microsoft Endpoint Configuration Manager</span></span>**

> [!NOTE]
> <span data-ttu-id="f3777-202">이러한 지침은 Microsoft Endpoint Configuration Manager의 현재 분기를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-202">These instructions are based on the current branch of Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="f3777-203">MDM 관리에 Surface Hub를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-203">Enroll your Surface Hubs into MDM management.</span></span> <span data-ttu-id="f3777-204">자세한 내용은 [MDM 공급자를 사용하여 Surface Hub 관리를 참조하세요.](manage-settings-with-mdm-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="f3777-204">For more information, see [Manage Surface Hub with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).</span></span>

2. <span data-ttu-id="f3777-205">비즈니스용 Store에서 오프라인 사용이 허가된 앱 패키지, *인코드된* 라이선스 파일 및 필요한 모든 종속성 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-205">Download the offline-licensed app package, the *encoded* license file, and any necessary dependency files from the Store for Business.</span></span> <span data-ttu-id="f3777-206">자세한 내용은 [오프라인 사용이 허가된 앱 다운로드](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-206">For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).</span></span> <span data-ttu-id="f3777-207">다운로드한 파일을 네트워크 공유의 동일한 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-207">Place the downloaded files in the same folder on a network share.</span></span>

3. <span data-ttu-id="f3777-208">Configuration Manager 콘솔의 **소프트웨어 라이브러리** 작업 영역에서 **개요** > **응용 프로그램 관리** > **응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-208">In the **Software Library** workspace of the Configuration Manager console, click **Overview** > **Application Management** > **Applications**.</span></span>

4. <span data-ttu-id="f3777-209">**홈** 탭의 **만들기** 그룹에서 **응용 프로그램 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-209">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span>

5. <span data-ttu-id="f3777-210">**응용 프로그램 만들기 마법사**의 **일반** 페이지에서 **설치 파일에서 이 응용 프로그램에 대한 정보 자동 검색** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-210">On the **General** page of the **Create Application Wizard**, select the **Automatically detect information about this application from installation files** check box.</span></span>

6. <span data-ttu-id="f3777-211">**형식** 드롭다운 목록에서 **Windows 앱 패키지(\*.appx, \*.appxbundle)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-211">In the **Type** drop-down list, select **Windows app package (\*.appx, \*.appxbundle)**.</span></span>

7. <span data-ttu-id="f3777-212">**위치** 필드에서, 비즈니스용 Store에서 다운로드한 오프라인 사용이 허가된 앱 패키지에 대한 UNC 경로를 \\server\share\\filename 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-212">In the **Location** field, specify the UNC path in the form \\server\share\\filename for the offline-licensed app package that you downloaded from the Store for Business.</span></span> <span data-ttu-id="f3777-213">또는 **찾아보기**를 클릭하여 앱 패키지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-213">Alternatively, click **Browse** to browse to the app package.</span></span>

8. <span data-ttu-id="f3777-214">**정보 가져오기** 페이지에서 가져온 정보를 검토하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-214">On the **Import Information** page, review the information that was imported, and then click **Next**.</span></span> <span data-ttu-id="f3777-215">필요한 경우 **이전**을 클릭하여 돌아가서 오류를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-215">If necessary, you can click **Previous** to go back and correct any errors.</span></span>

9. <span data-ttu-id="f3777-216">**일반 정보** 페이지에서 앱에 대한 추가 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-216">On the **General Information** page, complete additional details about the app.</span></span> <span data-ttu-id="f3777-217">이 정보의 일부는 앱 패키지에서 자동으로 가져온 경우 미리 채워져 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-217">Some of this information might already be populated if it was automatically obtained from the app package.</span></span>

10. <span data-ttu-id="f3777-218">**다음**을 클릭하고, 요약 페이지에서 응용 프로그램 정보를 검토하고 나서, 응용 프로그램 만들기 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-218">Click **Next**, review the application information on the Summary page, and then complete the Create Application Wizard.</span></span> 

11. <span data-ttu-id="f3777-219">응용 프로그램에 대한 배포 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-219">Create a deployment type for the application.</span></span> <span data-ttu-id="f3777-220">자세한 내용은 [Create deployment types for the application](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application)(응용 프로그램에 대한 배포 유형 만들기)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3777-220">For more information, see [Create deployment types for the application](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).</span></span>

12. <span data-ttu-id="f3777-221">Surface Hub에 응용 프로그램을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-221">Deploy the application to your Surface Hubs.</span></span> <span data-ttu-id="f3777-222">자세한 내용은 [Microsoft Endpoint Configuration Manager를 통해 응용 프로그램 배포를 참조하세요.](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)</span><span class="sxs-lookup"><span data-stu-id="f3777-222">For more information, see [Deploy applications with Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).</span></span>

13. <span data-ttu-id="f3777-223">필요한 경우 비즈니스용 Store에서 새 패키지를 다운로드하고 Configuration Manager에 응용 프로그램 버전을 게시하여 앱을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-223">As needed, update the app by downloading a new package from the Store for Business, and publishing an application revision in Configuration Manager.</span></span> <span data-ttu-id="f3777-224">자세한 내용은 Microsoft Endpoint Configuration Manager를 통해 응용 프로그램 업데이트 및 [사용 중지를 참조하세요.](https://technet.microsoft.com/library/mt595704.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3777-224">For more information, see [Update and retire applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx).</span></span> 

> [!NOTE] 
> <span data-ttu-id="f3777-225">Microsoft Endpoint Configuration Manager(현재 분기)를 사용하는 경우 비즈니스용 스토어를 Configuration Manager에 연결하여 위의 단계를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-225">If you are using Microsoft Endpoint Configuration Manager (current branch), you can bypass the above steps by connecting the Store for Business to Configuration Manager.</span></span> <span data-ttu-id="f3777-226">이렇게 하면 구입한 앱 목록을 Configuration Manager와 동기화하고, Configuration Manager 콘솔에서 이러한 앱을 보고, 다른 앱처럼 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-226">By doing so, you can synchronize the list of apps you've purchased with Configuration Manager, view these in the Configuration Manager console, and deploy them like you would any other app.</span></span> <span data-ttu-id="f3777-227">자세한 내용은 Configuration Manager를 사용하여 비즈니스용 [Microsoft Store에서 앱 관리를 참조하세요.](https://technet.microsoft.com/library/mt740630.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3777-227">For more information, see [Manage apps from the Microsoft Store for Business with Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).</span></span>


## <a name="summary"></a><span data-ttu-id="f3777-228">요약</span><span class="sxs-lookup"><span data-stu-id="f3777-228">Summary</span></span>

<span data-ttu-id="f3777-229">앱을 개발하는지, 소수의 디바이스에서 앱을 평가하는지 또는 조직에 광범위하게 앱을 배포하는지 여부에 따라 Surface Hub에 앱을 설치할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-229">There are a few different ways to install apps on your Surface Hub depending on whether you are developing apps, evaluating apps on a small number of devices, or deploying apps broadly to your organization.</span></span> <span data-ttu-id="f3777-230">이 표에는 지원되는 방법이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3777-230">This table summarizes the supported methods:</span></span>

| <span data-ttu-id="f3777-231">설치 방법</span><span class="sxs-lookup"><span data-stu-id="f3777-231">Install method</span></span>             | <span data-ttu-id="f3777-232">앱 개발</span><span class="sxs-lookup"><span data-stu-id="f3777-232">Developing apps</span></span> | <span data-ttu-id="f3777-233">몇 개의 디바이스에서</span><span class="sxs-lookup"><span data-stu-id="f3777-233">Evaluating apps on</span></span> <br> <span data-ttu-id="f3777-234">앱 평가</span><span class="sxs-lookup"><span data-stu-id="f3777-234">a few devices</span></span> | <span data-ttu-id="f3777-235">조직에 광범위하게</span><span class="sxs-lookup"><span data-stu-id="f3777-235">Deploying apps broadly</span></span> <br> <span data-ttu-id="f3777-236">앱 배포</span><span class="sxs-lookup"><span data-stu-id="f3777-236">to your organization</span></span> |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| <span data-ttu-id="f3777-237">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3777-237">Visual Studio</span></span>              | <span data-ttu-id="f3777-238">X</span><span class="sxs-lookup"><span data-stu-id="f3777-238">X</span></span> |   |   |
| <span data-ttu-id="f3777-239">프로비저닝 패키지</span><span class="sxs-lookup"><span data-stu-id="f3777-239">Provisioning package</span></span>       | <span data-ttu-id="f3777-240">X</span><span class="sxs-lookup"><span data-stu-id="f3777-240">X</span></span> | <span data-ttu-id="f3777-241">X</span><span class="sxs-lookup"><span data-stu-id="f3777-241">X</span></span> |   |
| <span data-ttu-id="f3777-242">Microsoft Store 앱</span><span class="sxs-lookup"><span data-stu-id="f3777-242">Microsoft Store app</span></span>          |   | <span data-ttu-id="f3777-243">X</span><span class="sxs-lookup"><span data-stu-id="f3777-243">X</span></span> |   |
| <span data-ttu-id="f3777-244">지원되는 MDM 공급자</span><span class="sxs-lookup"><span data-stu-id="f3777-244">Supported MDM provider</span></span>     |   |   | <span data-ttu-id="f3777-245">X</span><span class="sxs-lookup"><span data-stu-id="f3777-245">X</span></span> |

## <a name="more-information"></a><span data-ttu-id="f3777-246">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="f3777-246">More information</span></span>

- [<span data-ttu-id="f3777-247">블로그 게시물: Intune를 사용하여 Surface Hub에 Windows 스토어 앱을 배포</span><span class="sxs-lookup"><span data-stu-id="f3777-247">Blog post:  Deploy Windows Store apps to Surface Hub using Intune</span></span>](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## <a name="related-topics"></a><span data-ttu-id="f3777-248">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f3777-248">Related topics</span></span>

[<span data-ttu-id="f3777-249">Microsoft Surface Hub 관리</span><span class="sxs-lookup"><span data-stu-id="f3777-249">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="f3777-250">Microsoft Surface Hub 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="f3777-250">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





