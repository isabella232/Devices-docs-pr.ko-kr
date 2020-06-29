---
title: 첫 실행 프로그램(Surface Hub)
description: '\ 0034;첫 실행\ 0034;이란 용어는 처음으로 Microsoft Surface Hub의 전원을 켤 때 수행하는 일련의 단계를 가리키며, OOBE(\ 0034;첫 실행 경험\ 0034;)와 의미가 같습니다. 이 섹션에서 프로세스를 안내합니다.'
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: 첫 실행, Surface Hub, 첫 실행 경험, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0ad65170b3cc2534fec1b22730c718025026d7bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836228"
---
# <span data-ttu-id="e3f09-105">첫 실행 프로그램(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="e3f09-105">First-run program (Surface Hub)</span></span>


<span data-ttu-id="e3f09-106">"첫 실행"이란 용어는 처음으로 Microsoft Surface Hub의 전원을 켤 때 수행하는 일련의 단계를 가리키며, OOBE("첫 실행 경험")와 의미가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-106">The term "first run" refers to the series of steps you'll go through the first time you power up your Microsoft Surface Hub, and means the same thing as "out-of-box experience" (OOBE).</span></span> <span data-ttu-id="e3f09-107">이 섹션에서 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-107">This section will walk you through the process.</span></span>

<span data-ttu-id="e3f09-108">지금까지 이전 단계를 모두 완료했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-108">By now, you should have gone through all of the previous steps:</span></span>

-   [<span data-ttu-id="e3f09-109">Surface Hub에 대한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="e3f09-109">Prepare your environment for Surface Hub</span></span>](prepare-your-environment-for-surface-hub.md)
-   <span data-ttu-id="e3f09-110">[물리적으로 Surface Hub 디바이스 설치](physically-install-your-surface-hub-device.md)및</span><span class="sxs-lookup"><span data-stu-id="e3f09-110">[Physically install your Surface Hub device](physically-install-your-surface-hub-device.md), and</span></span>
-   [<span data-ttu-id="e3f09-111">설치 워크시트</span><span class="sxs-lookup"><span data-stu-id="e3f09-111">Setup worksheet</span></span>](setup-worksheet-surface-hub.md)

<span data-ttu-id="e3f09-112">완료했다고 가정하면 첫 실행은 간단하고 빠르게 진행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-112">Assuming that's the case, first run should be both simple and quick.</span></span>
<span data-ttu-id="e3f09-113">일반적인 절차는 다음 6단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-113">The normal procedure goes through six steps:</span></span>

1.  [<span data-ttu-id="e3f09-114">안녕하세요 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-114">Hi there page</span></span>](#first-page)
2.  [<span data-ttu-id="e3f09-115">자동 설치 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-115">Set up for you page</span></span>](#set-up-for-you)
3.  [<span data-ttu-id="e3f09-116">디바이스 계정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-116">Device account page</span></span>](#device-account)
4.  [<span data-ttu-id="e3f09-117">이 디바이스 이름 지정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-117">Name this device page</span></span>](#name-this-device)
5.  [<span data-ttu-id="e3f09-118">이 디바이스에 대한 관리자 설정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-118">Set up admins for this device page</span></span>](#setup-admins)
6.  [<span data-ttu-id="e3f09-119">Surface Hub 업데이트</span><span class="sxs-lookup"><span data-stu-id="e3f09-119">Update the Surface Hub</span></span>](#update-surface-hub)

<span data-ttu-id="e3f09-120">각 섹션에는 변경 내용이 있을 때 사용할 수 있는 경로에 대한 정보도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-120">Each of these sections also contains information about paths you might take when something is different.</span></span> <span data-ttu-id="e3f09-121">예를 들어 대부분의 Surface Hub는 유선 네트워크 연결을 사용하지만 일부는 무선을 사용하여 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-121">For example, most Surface Hubs will use a wired network connection, but some of them will be set up with wireless instead.</span></span> <span data-ttu-id="e3f09-122">해당하는 경우 세부 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-122">Details are described where appropriate.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-123">시작하기 전에 Surface Hub와 함께 제공된 별도 키보드가 설치되고 준비되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-123">You should have the separate keyboard that came with your Surface Hub set up and ready before beginning.</span></span> <span data-ttu-id="e3f09-124">자세한 내용은 Surface Hub 설치 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-124">See the Surface Hub Setup Guide for details.</span></span>

 

## <a href="" id="first-page"></a><span data-ttu-id="e3f09-125">안녕하세요 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-125">Hi there page</span></span>


<span data-ttu-id="e3f09-126">처음으로 Surface Hub 전원을 켤 때 표시되는 첫 번째 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-126">This is the first screen you'll see when you power up the Surface Hub for the first time.</span></span> <span data-ttu-id="e3f09-127">여기서 장치에 대한 지역화 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-127">It's where you input localization information for your device.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-128">또한 프로비저닝 패키지를 배포하는 선택적 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-128">This is also where you begin the optional process of deploying a provisioning package.</span></span> <span data-ttu-id="e3f09-129">이 작업을 수행 중이면 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-129">See [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md) if that's what you're doing.</span></span>

 <span data-ttu-id="e3f09-130">언어를 선택하면 초기 설치 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-130">Select a language and the initial setup options are displayed.</span></span>

![ICD 옵션 검사 목록을 보여 주는 이미지입니다.](images/setuplocale.png)

### <span data-ttu-id="e3f09-132">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-132">Details</span></span>

<span data-ttu-id="e3f09-133">표시된 기본값이 올바르면 **다음**을 클릭하여 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-133">If the default values shown are correct, then you can click **Next** to go on.</span></span> <span data-ttu-id="e3f09-134">그렇지 않으면 해당 상자에 데이터를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-134">Otherwise, you'll need to enter data in the appropriate boxes.</span></span>

-   <span data-ttu-id="e3f09-135">**국가/지역:** Surface Hub를 사용할 국가 또는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-135">**Country/region:** Select the country or region where the Surface Hub will be used.</span></span>
-   <span data-ttu-id="e3f09-136">**앱 언어:** 앱과 기능은 이 언어와 언어 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-136">**App language:** Apps and features will display in this language and language format.</span></span>
-   <span data-ttu-id="e3f09-137">**키보드 레이아웃:** 디바이스와 함께 사용할 화상 및 실제 키보드의 키보드 레이아웃을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-137">**Keyboard layout:** Select the keyboard layout for the on-screen and physical keyboards that will be used with your device.</span></span>
-   <span data-ttu-id="e3f09-138">**표준 시간대:** Surface Hub를 사용할 표준 시간대를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-138">**Time zone:** Select the time zone where the Surface Hub will be used.</span></span>

### <span data-ttu-id="e3f09-139">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-139">What happens?</span></span>

>[!NOTE]
> <span data-ttu-id="e3f09-140">이 페이지의 설정을 입력한 후에는 디바이스를 초기화하지 않는 한 이 화면으로 돌아올 수 없습니다([디바이스 초기화](device-reset-surface-hub.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="e3f09-140">Once the settings on this page are entered, you can't come back to this screen unless you reset the device (see [Device reset](device-reset-surface-hub.md)).</span></span> <span data-ttu-id="e3f09-141">계속하기 전에 설정이 제대로 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-141">Make sure that the settings are properly configured before proceeding.</span></span>

 

<span data-ttu-id="e3f09-142">설정을 적용하면 디바이스가 유선 네트워크 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-142">When the settings are accepted, the device will check for a wired network connection.</span></span> <span data-ttu-id="e3f09-143">연결이 정상이면 [자동 설치 페이지](#set-up-for-you)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-143">If the connection is fine, it will display the [Set up for you page](#set-up-for-you).</span></span> <span data-ttu-id="e3f09-144">유선 연결에 문제가 있으면 디바이스에서 [네트워크 설정 페이지](#network-setup)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-144">If there is a problem with the wired connection, the device will display the [Network setup page](#network-setup).</span></span>

<span data-ttu-id="e3f09-145">유선 연결을 찾을 수 없는 경우 디바이스가 무선 연결을 설치하려고 하며 [네트워크 설정 페이지](#network-setup)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-145">If no wired connection can be found, then the device will attempt to set up a wireless connection, and will display the [Network setup page](#network-setup).</span></span>

## <a href="" id="network-setup"></a><span data-ttu-id="e3f09-146">네트워크 설정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-146">Network setup page</span></span>


<span data-ttu-id="e3f09-147">디바이스가 네트워크 또는 인터넷에 연결하는 데 사용할 수 있는 유선 연결을 검색하지 못하면 이 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-147">If your device does not detect a wired connection that it can use to connect to a network or the Internet, you will see this page.</span></span> <span data-ttu-id="e3f09-148">여기서 무선 네트워크에 연결하거나 네트워크 연결 설정을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-148">Here you can either connect to a wireless network, or skip making the network connection.</span></span>

![네트워크 설정 페이지를 보여 주는 이미지입니다.](images/setupnetworksetup-1.png)

### <span data-ttu-id="e3f09-150">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-150">Details</span></span>

<span data-ttu-id="e3f09-151">이 화면은 디바이스가 유선 네트워크를 검색하지 못한 경우에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-151">This screen is shown only if the device fails to detect a wired network.</span></span> <span data-ttu-id="e3f09-152">이 화면이 표시되는 경우 다음 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-152">If you see this screen, you have three choices:</span></span>

-   <span data-ttu-id="e3f09-153">표시된 무선 네트워크 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-153">You can select one of the wireless networks shown.</span></span> <span data-ttu-id="e3f09-154">네트워크가 보호된 경우 로그인 페이지로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-154">If the network is secured, you'll be taken to a login page.</span></span> <span data-ttu-id="e3f09-155">자세한 내용은 [무선 네트워크 설정](#wireless) 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-155">See [Wireless network setup](#wireless) for details.</span></span>
-   <span data-ttu-id="e3f09-156">네트워크 연결을 건너뛰려면 **이 단계 건너뛰기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-156">Click **Skip this step** to skip connecting to a network.</span></span> <span data-ttu-id="e3f09-157">[자동 설치 페이지](#set-up-for-you)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-157">You'll be taken to the [Set up for you page](#set-up-for-you).</span></span>
    >[!NOTE]
    ><span data-ttu-id="e3f09-158">건너뛸 경우 디바이스에 네트워크 연결이 없으며 시스템 업데이트, 메일 및 일정 동기화 등 네트워크 연결이 필요한 기능은 Surface Hub에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-158">If you skip this, the device will not have a network connection, and nothing that requires a network connection will work on your Surface Hub, including system updates and email and calendar synchronization.</span></span> <span data-ttu-id="e3f09-159">설정을 사용 하 여 나중에 무선 네트워크에 연결할 수 있습니다 ( [무선 네트워크 관리](wireless-network-management-for-surface-hub.md)참조).</span><span class="sxs-lookup"><span data-stu-id="e3f09-159">You can connect to a wireless network later using Settings (see [Wireless network management](wireless-network-management-for-surface-hub.md)).</span></span>

     

-   <span data-ttu-id="e3f09-160">이 화면이 표시되는 동안 네트워크 케이블을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-160">You can plug in a network cable while this screen is visible.</span></span> <span data-ttu-id="e3f09-161">디바이스가 연결을 검색하고 화면에 **다음** 이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-161">The device will detect it, and will add **Next** to the screen.</span></span> <span data-ttu-id="e3f09-162">유선 연결 만들기를 계속하려면 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-162">Click **Next** to continue with making the wired connection.</span></span>

### <span data-ttu-id="e3f09-163">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-163">What happens?</span></span>

<span data-ttu-id="e3f09-164">시작 시 디바이스에 유선 연결이 있고 네트워크 또는 인터넷 연결을 설정할 수 있는 경우에는 이 페이지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-164">If the device has a wired connection when it starts, and can establish a network or Internet connection, then this page will not be displayed.</span></span> <span data-ttu-id="e3f09-165">무선 연결에 디바이스를 연결하려는 경우 첫 실행 시 이더넷 케이블이 연결되지 않았는지 확인합니다. 이 화면으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-165">If you want to connect the device to a wireless connection, make sure no Ethernet cable is plugged in at first run, which will bring you to this screen.</span></span> <span data-ttu-id="e3f09-166">지금 설정하는 항목에 관계없이 나중에 [설정을 사용](wireless-network-management-for-surface-hub.md) 하여 다른 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-166">No matter what you choose to set up now, you can [use Settings](wireless-network-management-for-surface-hub.md) to set up different connections later.</span></span>

<span data-ttu-id="e3f09-167">이 페이지에서 보안 무선 네트워크에 연결하려는 경우 선택한 네트워크를 클릭하고 연결하는 데 필요한 정보(암호 또는 계정 자격 증명)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-167">If you want to connect to a secured wireless network from this page, click on the network of your choice, and then provide the necessary information (password or account credentials) to connect.</span></span> <span data-ttu-id="e3f09-168">[무선 네트워크 설정](#wireless)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-168">See [Wireless network setup](#wireless).</span></span>

## <a href="" id="wireless"></a><span data-ttu-id="e3f09-169">무선 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="e3f09-169">Wireless network setup</span></span>


<span data-ttu-id="e3f09-170">이 페이지는 보호된 무선 네트워크를 선택한 경우에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-170">This page will be shown when you've selected a secured wireless network.</span></span>

![무선 네트워크 설정 페이지를 보여 주는 이미지입니다.](images/setupnetworksetup-3.png)

### <span data-ttu-id="e3f09-172">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-172">Details</span></span>

-   <span data-ttu-id="e3f09-173">**사용자 이름:** 선택한 무선 네트워크에 대한 사용자 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-173">**User name:** Enter the user name for the selected wireless network.</span></span>
-   <span data-ttu-id="e3f09-174">**암호:** 네트워크 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-174">**Password:** This is the password for the network.</span></span>

### <span data-ttu-id="e3f09-175">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-175">What happens?</span></span>

<span data-ttu-id="e3f09-176">디바이스가 지정된 네트워크에 연결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-176">The device will attempt to connect to the specified network.</span></span> <span data-ttu-id="e3f09-177">성공하면 [자동 설치 페이지](#set-up-for-you)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-177">If it's successful, you'll be taken to the [Set up for you page](#set-up-for-you).</span></span>

## <a href="" id="proxy"></a><span data-ttu-id="e3f09-178">네트워크 프록시 설정</span><span class="sxs-lookup"><span data-stu-id="e3f09-178">Network proxy setup</span></span>


<span data-ttu-id="e3f09-179">이 페이지는 디바이스가 연결이 제한된 유선 연결을 검색하는 경우에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-179">This page will be shown when the device detects a wired connection with limited connectivity.</span></span> <span data-ttu-id="e3f09-180">다음 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-180">You have three options:</span></span>

-   <span data-ttu-id="e3f09-181">제한된 유선 연결 대신 사용할 무선 네트워크를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-181">You can select a wireless network to use instead of the limited wired connection.</span></span>
-   <span data-ttu-id="e3f09-182">**이 단계 건너뛰기**를 선택하여 네트워크 연결을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-182">You can skip connecting to a network by selecting **Skip this step**.</span></span> <span data-ttu-id="e3f09-183">[자동 설치 페이지](#set-up-for-you)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-183">You'll be taken to the [Set up for you page](#set-up-for-you).</span></span>
    <span data-ttu-id="e3f09-184">**참고**  이 작업을 건너뛰면 디바이스는 네트워크에 연결 되지 않으며 네트워크 연결이 필요한 경우에는 전자 메일 및 일정 동기화 등의 항목을 포함 하 여 Surface Hub에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-184">**Note**If you skip this, the device will not have a network connection, and nothing that requires a network connection will work on your Surface Hub, including things like email and calendar synchronization.</span></span> <span data-ttu-id="e3f09-185">설정을 사용 하 여 나중에 무선 네트워크에 연결할 수 있습니다 ( [무선 네트워크 관리](wireless-network-management-for-surface-hub.md)참조).</span><span class="sxs-lookup"><span data-stu-id="e3f09-185">You can connect to a wireless network later using Settings (see [Wireless network management](wireless-network-management-for-surface-hub.md)).</span></span>

     

-   <span data-ttu-id="e3f09-186">네트워크 프록시를 사용하는 방법을 지정할 수 있는 **프록시 설정 입력** 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-186">You can select **Enter proxy settings** which will allow you to specify how to use the network proxy.</span></span> <span data-ttu-id="e3f09-187">다음 화면으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-187">You'll be taken to the next screen.</span></span>

![네트워크 프록시 페이지를 보여 주는 이미지입니다.](images/setupnetworksetup-2.png)

<span data-ttu-id="e3f09-189">이전 화면에서 **프록시 설정 입력** 을 클릭한 경우에 표시되는 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-189">This is the screen you'll see if you clicked **Enter proxy settings** on the previous screen.</span></span>

![프록시 서버 설정 세부 정보를 보여 주는 이미지입니다.](images/setupnetworksetup-4.png)

### <span data-ttu-id="e3f09-191">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-191">Details</span></span>

<span data-ttu-id="e3f09-192">네트워크 연결을 설정하려면 스크립트 이름이나 프록시 서버 및 포트 정보 중 하나를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-192">In order to make a network connection, you'll need to fill in either a script name, or the proxy server and port info.</span></span>

-   <span data-ttu-id="e3f09-193">**프록시 스크립트:** 프록시 스크립트의 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-193">**Proxy script:** Provide the address of a proxy script.</span></span>
-   <span data-ttu-id="e3f09-194">**프록시 서버 및 포트:** 프록시 서버 주소와 포트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-194">**Proxy server and port:** You can provide the proxy server address and port.</span></span>

### <span data-ttu-id="e3f09-195">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-195">What happens?</span></span>

<span data-ttu-id="e3f09-196">**다음**을 클릭하면 디바이스가 프록시 서버에 연결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-196">When you click **Next**, the device will attempt to connect to the proxy server.</span></span> <span data-ttu-id="e3f09-197">성공하면 [자동 설치 페이지](#set-up-for-you)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-197">If successful, you'll be taken to the [Set up for you page](#set-up-for-you).</span></span>

<span data-ttu-id="e3f09-198">**이 단계 건너뛰기**를 선택하여 네트워크 연결을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-198">You can skip connecting to a network by selecting **Skip this step**.</span></span> <span data-ttu-id="e3f09-199">[자동 설치 페이지](#set-up-for-you)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-199">You'll be taken to the [Set up for you page](#set-up-for-you).</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-200">건너뛸 경우 디바이스에 네트워크 연결이 없으며 메일 및 일정 동기화 등 네트워크 연결이 필요한 기능은 Surface Hub에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-200">If you skip this, the device will not have a network connection, and nothing that requires a network connection will work on your Surface Hub, including things like email and calendar synchronization.</span></span> <span data-ttu-id="e3f09-201">설정을 사용 하 여 나중에 무선 네트워크에 연결할 수 있습니다 ( [무선 네트워크 관리](wireless-network-management-for-surface-hub.md)참조).</span><span class="sxs-lookup"><span data-stu-id="e3f09-201">You can connect to a wireless network later using Settings (see [Wireless network management](wireless-network-management-for-surface-hub.md)).</span></span>

 

## <a href="" id="set-up-for-you"></a><span data-ttu-id="e3f09-202">자동 설치 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-202">Set up for you page</span></span>


<span data-ttu-id="e3f09-203">이 화면은 정보 제공 목적으로만 사용되며, 기본적으로 사용되는 권장 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-203">This screen is purely informational, and shows which recommended settings have been enabled by default.</span></span>

![자동 설치 페이지를 보여 주는 이미지입니다.](images/setupsetupforyou.png)

### <span data-ttu-id="e3f09-205">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-205">Details</span></span>

<span data-ttu-id="e3f09-206">이 화면을 읽고 기본적으로 사용되는 서비스를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-206">You should read this screen and note which services have been enabled by default.</span></span> <span data-ttu-id="e3f09-207">필요한 경우 설정 앱을 사용하여 모두 변경할 수 있지만 변경할 경우의 결과에 대해 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-207">All of them can be changed using the Settings app if need be, but you should be careful about the effects of doing so.</span></span> <span data-ttu-id="e3f09-208">자세한 내용은 [Surface Hub 소개](intro-to-surface-hub.md) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-208">See [Intro to Surface Hub](intro-to-surface-hub.md) for details.</span></span>

<span data-ttu-id="e3f09-209">설정 검토를 마쳤으면 **다음** 을 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-209">Once you're done reviewing the settings, click **Next** to go on.</span></span>

### <span data-ttu-id="e3f09-210">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-210">What happens?</span></span>

<span data-ttu-id="e3f09-211">페이지에 표시된 설정은 이미 지정되었으며, 첫 실행이 완료될 때까지 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-211">The settings shown on the page have already been made, and can't be changed until after first run is completed.</span></span>

## <a href="" id="device-account"></a><span data-ttu-id="e3f09-212">디바이스 계정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-212">Device account page</span></span>


<span data-ttu-id="e3f09-213">이 페이지에서 Surface Hub는 이전에 구성된 디바이스 계정의 자격 증명을 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-213">On this page, the Surface Hub will ask for credentials for the device account that you previously configured.</span></span> <span data-ttu-id="e3f09-214">([디바이스 계정 만들기 및 테스트](create-and-test-a-device-account-surface-hub.md) 참조). Surface Hub는 계정의 다양한 속성을 검색하려고 하며, 실패할 경우 다른 페이지에서 추가 정보를 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-214">(See [Create and test a device account](create-and-test-a-device-account-surface-hub.md).) The Surface Hub will attempt to discover various properties of the account, and may ask for more information on another page if it does not succeed.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-215">첫 실행 중에 발생할 수 있는 특정 오류는 이 섹션에서 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-215">This section does not cover specific errors that can happen during first run.</span></span> <span data-ttu-id="e3f09-216">오류에 대한 자세한 내용은 [Surface Hub 문제 해결](troubleshoot-surface-hub.md) 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-216">See [Troubleshoot Surface Hub](troubleshoot-surface-hub.md) for more information on errors.</span></span>


![디바이스 계정 정보 입력 페이지를 보여 주는 이미지입니다.](images/setupdeviceacct.png)

### <span data-ttu-id="e3f09-218">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-218">Details</span></span>

<span data-ttu-id="e3f09-219">첫 번째 입력 필드에서 **UPN(사용자 계정 이름)** 또는 **도메인\\사용자 이름**을 계정 식별자로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-219">Use either a **user principal name (UPN)** or a **domain\\user name** as the account identifier in the first entry field.</span></span> <span data-ttu-id="e3f09-220">환경과 일치하는 형식을 사용하고 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-220">Use the format that matches your environment, and enter the password.</span></span>


|                      <span data-ttu-id="e3f09-221">환경</span><span class="sxs-lookup"><span data-stu-id="e3f09-221">Environment</span></span>                      | <span data-ttu-id="e3f09-222">디바이스 계정의 필수 형식</span><span class="sxs-lookup"><span data-stu-id="e3f09-222">Required format for device account</span></span> |
|-------------------------------------------------------|------------------------------------|
|         <span data-ttu-id="e3f09-223">디바이스 계정이 온라인에만 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-223">Device account is hosted only online.</span></span>         |        <span data-ttu-id="e3f09-224">username@domain.com</span><span class="sxs-lookup"><span data-stu-id="e3f09-224">username@domain.com</span></span>         |
|        <span data-ttu-id="e3f09-225">디바이스 계정이 온-프레미스에만 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-225">Device account is hosted only on-prem.</span></span>         |          <span data-ttu-id="e3f09-226">도메인\사용자 이름</span><span class="sxs-lookup"><span data-stu-id="e3f09-226">DOMAIN\username</span></span>           |
| <span data-ttu-id="e3f09-227">디바이스 계정이 온라인 및 온-프레미스에 호스트됩니다(하이브리드).</span><span class="sxs-lookup"><span data-stu-id="e3f09-227">Device account is hosted online and on-prem (hybrid).</span></span> |          <span data-ttu-id="e3f09-228">도메인\사용자 이름</span><span class="sxs-lookup"><span data-stu-id="e3f09-228">DOMAIN\username</span></span>           |

<span data-ttu-id="e3f09-229">디바이스 계정 설정을 건너뛰려면 **디바이스 계정 설정 건너뛰기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-229">Click **Skip setting up a device account** to skip setting up a device account.</span></span> <span data-ttu-id="e3f09-230">그러나 디바이스 계정을 설정하지 않으면 디바이스가 인프라에 완벽하게 통합되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-230">However, if you don't set up a device account, the device will not be fully integrated into your infrastructure.</span></span> <span data-ttu-id="e3f09-231">예를 들어 사용자가 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-231">For example, people won't be able to:</span></span>

-   <span data-ttu-id="e3f09-232">시작 화면에서 모임 일정 확인</span><span class="sxs-lookup"><span data-stu-id="e3f09-232">See a meeting calendar on the Welcome screen</span></span>
-   <span data-ttu-id="e3f09-233">시작 화면에서 모임 시작</span><span class="sxs-lookup"><span data-stu-id="e3f09-233">Start a meeting from the Welcome screen</span></span>
-   <span data-ttu-id="e3f09-234">OneNote에서 화이트보드를 메일로 보내기</span><span class="sxs-lookup"><span data-stu-id="e3f09-234">Email whiteboards from OneNote</span></span>
-   <span data-ttu-id="e3f09-235">모임에 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-235">Use Skype for Business for meetings</span></span>

<span data-ttu-id="e3f09-236">지금 설정을 건너뛰는 경우 나중에 설정 앱을 사용하여 디바이스 계정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-236">If you skip setting it up now, you can add a device account later by using the Settings app.</span></span>

<span data-ttu-id="e3f09-237">**디바이스 계정 설정 건너뛰기**를 클릭하면 디바이스에 디바이스 계정이 없을 경우 발생하는 동작을 보여 주는 대화 상자가 디바이스에서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-237">If you click **Skip setting up a device account**, the device will display a dialog box showing what will happen if the device doesn't have a device account.</span></span> <span data-ttu-id="e3f09-238">**예, 건너뛰겠습니다.** 를 선택하면 [이 디바이스 이름 지정 페이지](#name-this-device)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-238">If you choose **Yes, skip this**, you will be sent to the [Name this device page](#name-this-device).</span></span>

![디바이스 계정 만들기를 건너뛸지 여부를 확인 하기 위해가 표시 되는 메시지를 보여 주는 이미지](images/setupskipdeviceacct.png)

### <span data-ttu-id="e3f09-240">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-240">What happens?</span></span>

<span data-ttu-id="e3f09-241">디바이스는 디바이스 계정의 UPN이나 도메인\\사용자 이름 및 암호를 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-241">The device will use the UPN or DOMAIN\\User name and password for the device account to do the following:</span></span>

-   <span data-ttu-id="e3f09-242">계정이 AD(Active Directory)에 있는지 또는 Azure AD(Azure Active Directory)에 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-242">Check if the account exists in Active Directory (AD) or Azure Active Directory (Azure AD):</span></span>

    -   <span data-ttu-id="e3f09-243">UPN을 입력한 경우 디바이스는 Azure AD에서 계정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-243">If a UPN was entered: the device will look for the account in Azure AD.</span></span>
    -   <span data-ttu-id="e3f09-244">도메인\\사용자 이름을 입력한 경우 디바이스는 AD에서 계정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-244">If a DOMAIN\\User name was entered: the device will look for the account in AD.</span></span>
-   <span data-ttu-id="e3f09-245">계정의 사서함에 대한 Microsoft Exchange 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-245">Look up the Microsoft Exchange server for the account’s mailbox.</span></span>
-   <span data-ttu-id="e3f09-246">계정의 SIP(Session Initiation Protocol) 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-246">Look up the Session Initiation Protocol (SIP) address for the account.</span></span>
-   <span data-ttu-id="e3f09-247">계정의 표시 이름 및 별칭 특성을 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-247">Pull the account’s display name and alias attributes.</span></span>

## <a href="" id="exchange-server"></a><span data-ttu-id="e3f09-248">Exchange 서버 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-248">Exchange server page</span></span>


<span data-ttu-id="e3f09-249">이 페이지는 문제가 있는 경우에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-249">This page will only be shown if there's a problem.</span></span> <span data-ttu-id="e3f09-250">일반적으로 이는 제공한 디바이스 계정이 AD(Active Directory) 또는 Azure AD(Azure Active Directory)에 있지만 계정의 Exchange 서버가 검색되지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-250">Typically, it means that the device account that you provided was found in Active Directory (AD) or Azure Active Directory (Azure AD), but the Exchange server for the account was not discovered.</span></span>

![Exchange 서버 페이지를 보여 주는 이미지입니다.](images/setupexchangeserver-01.png)

### <span data-ttu-id="e3f09-252">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-252">Details</span></span>

<span data-ttu-id="e3f09-253">디바이스 계정의 사서함이 호스트된 Exchange 서버의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-253">Enter the name of the Exchange server where the device account's mailbox is hosted.</span></span>

<span data-ttu-id="e3f09-254">이 단계를 건너뛰려면 **Exchange 서비스 설정 건너뛰기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-254">Click **Skip setting up Exchange services** to skip this step.</span></span> <span data-ttu-id="e3f09-255">건너뛰면 사용자가 다음 작업을 수행할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-255">If you do, people will not be able to:</span></span>

-   <span data-ttu-id="e3f09-256">시작 화면에서 모임 일정 확인</span><span class="sxs-lookup"><span data-stu-id="e3f09-256">See a meeting calendar on the welcome screen.</span></span>
-   <span data-ttu-id="e3f09-257">시작 화면에서 모임 시작</span><span class="sxs-lookup"><span data-stu-id="e3f09-257">Start a meeting from the welcome screen.</span></span>
-   <span data-ttu-id="e3f09-258">OneNote에서 화이트보드를 메일로 보내기</span><span class="sxs-lookup"><span data-stu-id="e3f09-258">Email whiteboards from OneNote.</span></span>

<span data-ttu-id="e3f09-259">설치 종속성에 대한 자세한 내용은 [Surface Hub 소개](intro-to-surface-hub.md) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-259">See [Intro to Surface Hub](intro-to-surface-hub.md) for details on setup dependencies.</span></span>

<span data-ttu-id="e3f09-260">나중에 설정 앱을 사용하여 디바이스 계정에 Exchange 서비스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-260">You can enable Exchange services for a device account later by using the Settings app.</span></span>

<span data-ttu-id="e3f09-261">**Exchange 서비스 설정 건너뛰기**를 클릭하면 발생하는 동작을 보여 주는 대화 상자가 디바이스에서 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-261">If you click **Skip setting up Exchange services**, the device will display a dialog showing what will happen.</span></span> <span data-ttu-id="e3f09-262">**예, 건너뛰겠습니다.** 를 선택하면 Exchange 서비스가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-262">If you choose **Yes, skip this**, then Exchange services will not be set up.</span></span>

![Exchange 서비스 설정을 건너뛸 때 표시되는 확인 메시지를 보여 주는 이미지입니다.](images/setupexchangeserver-02.png)

### <span data-ttu-id="e3f09-264">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-264">What happens?</span></span>

<span data-ttu-id="e3f09-265">Surface Hub는 여기에 입력한 Exchange 서버에서 디바이스 계정의 유효성을 검사하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-265">The Surface Hub will attempt to validate the device account on the Exchange server that you enter here.</span></span> <span data-ttu-id="e3f09-266">Exchange 서버에 연결하고 유효성을 검사할 수 있는 경우 첫 실행이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-266">If the Exchange server can be reached and validates, then first run will proceed.</span></span>

<span data-ttu-id="e3f09-267">Exchange 서비스 설정을 건너뛰도록 선택하면 Surface Hub가 Exchange 서버 찾기를 중지하고 Exchange 서비스(메일 및 일정)가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-267">If you choose to skip setting up Exchange services, the Surface Hub will stop looking for the Exchange server, and no Exchange services (mail and calendar) will be enabled.</span></span>

## <a href="" id="exchange-policies"></a><span data-ttu-id="e3f09-268">Exchange 정책 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-268">Exchange policies page</span></span>


<span data-ttu-id="e3f09-269">이 페이지는 다음과 같은 경우에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-269">This page will be shown when:</span></span>

-   <span data-ttu-id="e3f09-270">디바이스 계정에서 PasswordEnabled 정책이 1로 설정된 EAS(Exchange Active Sync) 정책을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="e3f09-270">The device account is using an Exchange Active Sync (EAS) policy where the PasswordEnabled policy is set to 1.</span></span>
-   <span data-ttu-id="e3f09-271">Exchange 연결이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="e3f09-271">There’s no connection to Exchange.</span></span>
-   <span data-ttu-id="e3f09-272">Exchange에서 오류를 나타내는 상태 코드를 반환하는 경우</span><span class="sxs-lookup"><span data-stu-id="e3f09-272">Exchange returns a status code indicating an error.</span></span> <span data-ttu-id="e3f09-273">(예: 계정이 너무 많은 디바이스에 프로비전된 경우)</span><span class="sxs-lookup"><span data-stu-id="e3f09-273">(For example: The account has been provisioned to too many devices.)</span></span>
-   <span data-ttu-id="e3f09-274">Exchange 지원 프로토콜이 Surface Hub에서 지원되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="e3f09-274">Exchange supported protocols are not supported by the Surface Hub.</span></span>
-   <span data-ttu-id="e3f09-275">Exchange에서 잘못된 XML을 반환하는 경우</span><span class="sxs-lookup"><span data-stu-id="e3f09-275">Exchange returns incorrect XML.</span></span>

![Exchange 정책 페이지를 보여 주는 이미지입니다.](images/setupexchangepolicies.png)

### <span data-ttu-id="e3f09-277">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-277">Details</span></span>

<span data-ttu-id="e3f09-278">이 페이지는 정보 제공 목적으로만 사용되므로 입력이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-278">This page is purely informational, so no input is required.</span></span> <span data-ttu-id="e3f09-279">그러나 건너뛰거나 오류가 발생한 유효성 검사를 다시 시도하는 두 가지 진행 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-279">However, you have two options for proceeding: either skipping ahead or retrying the validation that caused the error.</span></span> <span data-ttu-id="e3f09-280">가장 적합한 옵션을 결정하기 전에 다음 **발생하는 동작** 섹션을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-280">Before deciding which option is best, please read the following **What happens?** section.</span></span> <span data-ttu-id="e3f09-281">옵션 중 하나를 클릭하기 전에 다른 곳에서 문제를 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-281">You may be able to fix the problem elsewhere before you click on one of the options.</span></span>

-   <span data-ttu-id="e3f09-282">**지원되지 않는 정책을 계속 사용하려면 여기를 클릭하세요.**: 첫 실행을 계속하려면 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-282">**Click here to continue using unsupported policies**: click on this to continue first run.</span></span> <span data-ttu-id="e3f09-283">Surface Hub는 Exchange 서비스를 사용하거나 동기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-283">The Surface Hub will not be able to use Exchange services, or sync.</span></span>
-   <span data-ttu-id="e3f09-284">**다시 시도**: Exchange 서버의 정책을 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-284">**Retry**: check the policy on the Exchange server again.</span></span>

### <span data-ttu-id="e3f09-285">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-285">What happens?</span></span>

<span data-ttu-id="e3f09-286">Surface Hub는 디바이스 계정의 EAS 정책에 PasswordEnabled 정책이 0(False)으로 설정되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-286">The Surface Hub checks whether the device account’s EAS policy has the PasswordEnabled policy set to 0 (False).</span></span> <span data-ttu-id="e3f09-287">설정되지 않은 경우 메일 및 일정을 동기화할 수 없으며 Surface Hub에서 Exchange 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-287">If this is not the case, mail and calendar can't be synced and the Surface Hub can't use any Exchange services.</span></span> <span data-ttu-id="e3f09-288">PC에서 Exchange 관리 도구를 사용하여 디바이스 계정에 PasswordEnabled 정책이 0으로 설정되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-288">You can use your Exchange management tools from a PC to check that the device account has the PasswordEnabled policy set to 0.</span></span> <span data-ttu-id="e3f09-289">설정되지 않은 경우 여기서 계정을 다시 구성하고 **다시 시도** 를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-289">If that's not the case, you can reconfigure the account and click **Retry** here.</span></span>

<span data-ttu-id="e3f09-290">정책이 이미 올바르게 구성된 경우 디바이스가 네트워크 또는 인터넷에 제대로 연결되었는지 확인하고, 이 페이지는 Surface Hub가 Exchange 서버에 연결할 수 없는 경우에도 표시되므로 Exchange 서버에 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-290">If the policy has already been configured properly, check that your device is properly connected to the network or Internet, and can reach your Exchange server, because this page will also be shown if the Surface Hub can't reach the Exchange server.</span></span>

<span data-ttu-id="e3f09-291">Exchange에 연결할 수 없는 다른 가능한 이유는 인증서 기반 인증 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-291">Another possible reason for not being able to reach Exchange is because of certificate-based authentication.</span></span> <span data-ttu-id="e3f09-292">인증서 문제 때문에 이 페이지가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-292">You may wind up on this page because of certificate issues.</span></span> <span data-ttu-id="e3f09-293">디바이스에서 0x80072F0D 또는 0X800C0019 오류 코드를 표시하는 경우 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-293">Note that if the device displays error codes 0x80072F0D or 0X800C0019, then a certificate is required.</span></span> <span data-ttu-id="e3f09-294">프로비전은 첫 실행 프로세스의 첫 페이지에서 수행되기 때문에 **지원되지 않는 정책을 계속 사용하려면 여기를 클릭하세요.** 를 클릭하여 Exchange 서비스를 사용하지 않도록 설정한 다음 설정 앱을 통해 올바른 인증서를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-294">Because provisioning is done on the first page of the first run process, you must disable Exchange services by clicking **Click here to continue using unsupported policies**, and then install the correct certificates through the Settings app.</span></span>

<span data-ttu-id="e3f09-295">이 확인을 건너뛰도록 선택하면 Surface Hub가 Exchange 서버 찾기 및 EAS 정책 유효성 검사를 중지하고 Exchange 서비스가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-295">If you choose to skip this check, the Surface Hub will stop looking for the Exchange server and validating EAS policies, and no Exchange services will be enabled.</span></span> <span data-ttu-id="e3f09-296">설치 종속성에 대한 자세한 내용은 [Surface Hub 소개](intro-to-surface-hub.md) 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-296">See [Intro to Surface Hub](intro-to-surface-hub.md) for details on setup dependencies.</span></span>

## <a href="" id="name-this-device"></a><span data-ttu-id="e3f09-297">이 디바이스 이름 지정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-297">Name this device page</span></span>


<span data-ttu-id="e3f09-298">이 페이지에는 Surface Hub를 식별하는 데 사용할 두 개의 이름을 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-298">This page asks you to provide two names that will be used for identifying the Surface Hub.</span></span>

![이 디바이스 이름 지정 페이지를 보여 주는 이미지입니다.](images/setupnamedevice.png)

### <span data-ttu-id="e3f09-300">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-300">Details</span></span>

<span data-ttu-id="e3f09-301">표시된 기본값이 올바르면 **다음** 을 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-301">If the default values shown are correct, then you can click **Next** to go on.</span></span> <span data-ttu-id="e3f09-302">그렇지 않으면 텍스트 상자 중 하나 또는 둘 다에 데이터를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-302">Otherwise, enter data in one or both of the text boxes.</span></span>

-   <span data-ttu-id="e3f09-303">**이름:** 사용자가 Surface Hub에 무선으로 연결하려고 할 때 표시되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-303">**Friendly name:** This is the name that people will see when they want to wirelessly connect to the Surface Hub.</span></span>
-   <span data-ttu-id="e3f09-304">**디바이스 이름:** 화면에 설명된 대로 임의의 고유 이름으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-304">**Device name:** Can be set to any unique name as described on the screen.</span></span>

<span data-ttu-id="e3f09-305">두 이름이 모두 길이 요구 사항 이내이고 제한된 문자를 사용하지 않는 한, **다음** 을 클릭하면 다음 페이지인 [이 디바이스에 대한 관리자 설정](#setup-admins)으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-305">As long as both names are within the length requirements and do not use restricted characters, clicking **Next** will take you to the next page, [Set up admins for this device](#setup-admins).</span></span>

### <span data-ttu-id="e3f09-306">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-306">What happens?</span></span>

<span data-ttu-id="e3f09-307">Surface Hub에는 두 개의 디바이스 이름이 필요하며, 기본적으로 다음과 같이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-307">The Surface Hub requires two names for the device, which will default to:</span></span>

-   <span data-ttu-id="e3f09-308">**이름:** 기본적으로 디바이스 계정의 표시 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-308">**Friendly name:** Defaults to the Display Name of the device account</span></span>
-   <span data-ttu-id="e3f09-309">**디바이스 이름:** 기본적으로 디바이스 계정의 별칭으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-309">**Device name:** Defaults to the alias of the device account</span></span>

<span data-ttu-id="e3f09-310">나중에 이름 중 하나를 변경할 수 있지만 다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-310">While either of the names can be changed later, keep in mind that:</span></span>

-   <span data-ttu-id="e3f09-311">사용자가 무선으로 연결하려고 할 때 Surface Hub 간에 구분할 수 있도록 이름은 인식 가능하고 서로 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-311">The friendly name should be recognizable and different so that people can distinguish one Surface Hub from another when trying to wirelessly connect.</span></span>
-   <span data-ttu-id="e3f09-312">디바이스를 도메인에 가입하려는 경우 디바이스 이름은 계정의 Active Directory 도메인에 있는 다른 디바이스의 이름과 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-312">If you decide to domain join the device, the device name must not be the same as any other device on the account’s Active Directory domain.</span></span> <span data-ttu-id="e3f09-313">디바이스가 도메인에 가입된 다른 디바이스와 동일한 이름을 사용하는 경우에는 도메인에 가입할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-313">The device can't join the domain if it is using the same name as another domain-joined device.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-314">[인프라를 통해 Miracast](miracast-over-infrastructure.md)를 사용하려는 경우 디바이스 이름을 DNS을 통해 검색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-314">If you want to enable [Miracast over Infrastructure](miracast-over-infrastructure.md), the device name needs to be discoverable via DNS.</span></span> <span data-ttu-id="e3f09-315">Surface Hub가 동적 DNS를 통해 자동으로 등록하도록 하거나 수동으로 Surface Hub의 디바이스 이름에 대한 A 또는 AAAA 레코드를 만들어 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-315">You can achieve this by either allowing your Surface Hub to register automatically via Dynamic DNS, or by manually creating an A or AAAA record for the Surface Hub's device name.</span></span>

## <a href="" id="setup-admins"></a><span data-ttu-id="e3f09-316">이 디바이스에 대한 관리자 설정 페이지</span><span class="sxs-lookup"><span data-stu-id="e3f09-316">Set up admins for this device page</span></span>


<span data-ttu-id="e3f09-317">이 페이지에서는 디바이스를 로컬로 관리하기 위해 관리자 계정을 설정하려는 방법에 대한 몇 가지 옵션 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-317">On this page, you will choose from several options for how you want to set up admin accounts to locally manage your device.</span></span>

<span data-ttu-id="e3f09-318">각 Surface Hub를 사용할 수 있는 인증된 직원 수에 제한이 없으므로 세션 간에 변경되지 않도록 설정이 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-318">Because every Surface Hub can be used by any number of authenticated employees, settings are locked down so that they can't change from session to session.</span></span> <span data-ttu-id="e3f09-319">관리자만 디바이스의 설정을 구성할 수 있으며, 이 페이지에서 해당 권한을 가진 관리자 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-319">Only admins can configure the settings on the device, and on this page, you’ll choose which type of admins have that privilege.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-320">이 페이지는 주로 디바이스의 UI에서 디바이스를 구성할 수 있는 사용자, 즉 실제로 디바이스를 방문하고, 로그인하고, 설정 앱을 열고, 설정을 변경할 수 있는 사용자를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-320">The purpose of this page is primarily to determine who can configure the device from the device’s UI; that is, who can actually visit a device, log in, open up the Settings app, and make changes to the Settings.</span></span>

 

![이 디바이스에 대한 관리자 설정 페이지를 보여 주는 이미지입니다.](images/setupsetupadmins.png)

### <span data-ttu-id="e3f09-322">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-322">Details</span></span>

<span data-ttu-id="e3f09-323">사용 가능한 다음 세 가지 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-323">Choose one of the three available options:</span></span>

-   **<span data-ttu-id="e3f09-324">Microsoft Azure Active Directory 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-324">Use Microsoft Azure Active Directory</span></span>**
-   **<span data-ttu-id="e3f09-325">Active Directory 도메인 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-325">Use Active Directory Domain Services</span></span>**
-   **<span data-ttu-id="e3f09-326">로컬 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-326">Use a local admin</span></span>**

### <span data-ttu-id="e3f09-327">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-327">What happens?</span></span>

<span data-ttu-id="e3f09-328">옵션을 선택할 때 발생하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-328">This is what happens when you choose an option.</span></span>

-   **<span data-ttu-id="e3f09-329">Microsoft Azure Active Directory 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-329">Use Microsoft Azure Active Directory</span></span>**

    <span data-ttu-id="e3f09-330">이 옵션을 클릭하면 디바이스를 Azure AD에 가입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-330">Clicking this option allows you to join the device to Azure AD.</span></span> <span data-ttu-id="e3f09-331">**다음**을 클릭하면 디바이스가 일부 설정을 적용하기 위해 다시 시작되고, [Microsoft Azure Active Directory 사용](#use-microsoft-azure) 페이지로 이동된 다음 Azure AD에 가입할 수 있는 자격 증명을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-331">Once you click **Next**, the device will restart to apply some settings, and then you’ll be taken to the [Use Microsoft Azure Active Directory](#use-microsoft-azure) page and asked to enter credentials that can allow you to join Azure AD.</span></span> <span data-ttu-id="e3f09-332">참가 한 조직의 Azure 전역 관리자 역할 구성원은 설정 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-332">Members of the Azure Global Admins role from the joined organization will be able to use the Settings app.</span></span> <span data-ttu-id="e3f09-333">허용되는 특정 사용자는 Azure AD 구독 및 Azure AD 조직의 설정을 구성한 방식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-333">The specific people that will be allowed depends on your Azure AD subscription and how you’ve configured the settings for your Azure AD organization.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e3f09-334">Azure AD에 디바이스에 참가 한 후 Azure 디바이스 관리자 역할에 추가 된 관리자는 설정 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-334">Administrators added to the Azure Device Administrators role after you join the device to Azure AD will be unable to use the Settings app.</span></span>
    >
    > <span data-ttu-id="e3f09-335">첫 실행 설치를 실행하는 동안 Surface Hub에 가입하면 Office 앱용 SSO(Single Sign-On)가 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-335">If you join Surface Hub to Azure AD during first-run setup, single sign-on (SSO) for Office apps will not work properly.</span></span> <span data-ttu-id="e3f09-336">사용자는 각 Office 앱에 개별적으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-336">Users will have to sign in to each Office app individually.</span></span>

-   **<span data-ttu-id="e3f09-337">Active Directory 도메인 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-337">Use Active Directory Domain Services</span></span>**

    <span data-ttu-id="e3f09-338">장치를 AD에 가입하려면 이 옵션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-338">Click this option to join the device to AD.</span></span> <span data-ttu-id="e3f09-339">**다음**을 클릭하면 [Active Directory 도메인 서비스 사용](#use-active-directory) 페이지로 이동되며 지정된 도메인에 가입할 수 있는 자격 증명을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-339">Once you click **Next**, you’ll be taken to the [Use Active Directory Domain Services](#use-active-directory) page and asked to enter credentials that allow you to join the specified domain.</span></span> <span data-ttu-id="e3f09-340">가입 후에 가입된 도메인에서 보안 그룹을 선택할 수 있으며, 해당 보안 그룹의 사용자는 설정 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-340">After joining, you can pick a security group from the joined domain, and people from that security group will be able to use the Settings app.</span></span>

-   **<span data-ttu-id="e3f09-341">로컬 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-341">Use a local admin</span></span>**

    <span data-ttu-id="e3f09-342">이 관리자는 디렉터리 서비스에서 백업되지 않으므로 디바이스가 Azure AD 또는 AD에 액세스할 수 없는 경우에만 이 옵션을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-342">Choosing this option will allow you to create a single local admin. This admin won’t be backed by any directory service, so we recommend you only choose this case if the device does not have access to Azure AD or AD.</span></span> <span data-ttu-id="e3f09-343">[로컬 관리자 사용](#use-a-local-admin) 페이지에서 관리자의 사용자 이름 및 암호를 만든 후 설정 앱을 열 때마다 동일한 자격 증명을 다시 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-343">Once you create an admin’s user name and password on the [Use a local admin](#use-a-local-admin) page, you will need to re-enter those same credentials whenever you open the Settings app.</span></span>

    <span data-ttu-id="e3f09-344">로컬 관리자가 로그인하려면 Surface Hub에 실제로 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-344">Note that a local admin must have physical access to the Surface Hub to log in.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-345">이 프로세스를 마친 후에는 디바이스를 초기화하지 않는 한 디바이스의 관리 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-345">After you finish this process, you won't be able to change the device's admin option unless you reset the device.</span></span>

 

### <a href="" id="use-microsoft-azure"></a><span data-ttu-id="e3f09-346">Microsoft Azure Active Directory 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-346">Use Microsoft Azure Active Directory</span></span>

<span data-ttu-id="e3f09-347">Surface Hub를 Azure AD(Azure Active Directory)에 가입하는 경우 이 **다음에 발생하는 동작** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-347">If you've decided to join your Surface Hub to Azure Active Directory (Azure AD), you'll see this **What happens next** page.</span></span> <span data-ttu-id="e3f09-348">페이지를 읽고 **다음** 을 클릭하여 **로그인 페이지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-348">Read it and click **Next** to go to the **Let's get you signed in page**.</span></span>

<span data-ttu-id="e3f09-349">Azure AD에 가입하면 다음 두 가지 주요 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-349">Joining Azure AD has two primary benefits:</span></span>

1.  <span data-ttu-id="e3f09-350">조직의 일부 직원이 관리자로 디바이스에 액세스할 수 있으며, 설정 앱을 시작하고 디바이스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-350">Some employees from your organization will be able to access the device as admins, and will be able to start the Settings app and configure the device.</span></span> <span data-ttu-id="e3f09-351">관리자 권한이 있는 사용자는 Azure AD 구독에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-351">People that have admin permissions will be defined in your Azure AD subscription.</span></span>
2.  <span data-ttu-id="e3f09-352">Azure AD가 MDM(모바일 디바이스 관리) 솔루션에 연결된 경우 정책 및 구성을 적용할 수 있도록 디바이스가 해당 MDM 솔루션에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-352">If your Azure AD is connected to a mobile device management (MDM) solution, the device will enroll with that MDM solution so you can apply policies and configuration.</span></span>

![Surface Hub를 Azure Active Directory에 연결할 때의 메시지를 보여 주는 이미지입니다.](images/setupjoiningazuread-1.png)

### <span data-ttu-id="e3f09-354">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-354">Details</span></span>

<span data-ttu-id="e3f09-355">다음 입력이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-355">The following input is required:</span></span>

-   <span data-ttu-id="e3f09-356">**사용자의 UPN:** Azure AD에 가입할 수 있는 계정의 UPN(사용자 계정 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-356">**User's UPN:** The user principal name (UPN) of an account that can join Azure AD.</span></span>
-   <span data-ttu-id="e3f09-357">**암호:** Azure AD에 가입하는 데 사용하는 계정의 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-357">**Password:** The password of the account you’re using to join Azure AD.</span></span>

![계정 로그인 정보를 보여 주는 이미지입니다.](images/setupjoiningazuread-2.png)

<span data-ttu-id="e3f09-359">이 시점까지 Azure AD 계정에 대한 유효한 자격 증명이 없을 경우 디바이스에서 로컬 관리자 계정을 만들지 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-359">If you get to this point and don't have valid credentials for an Azure AD account, the device will allow you to continue by creating a local admin account.</span></span> <span data-ttu-id="e3f09-360">**대신 로컬 계정으로 Windows를 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-360">Click **Set up Windows with a local account instead**.</span></span>

![관리자 계정 설정 페이지를 보여 주는 이미지입니다.](images/setupjoiningazuread-3.png)

### <span data-ttu-id="e3f09-362">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-362">What happens?</span></span>

<span data-ttu-id="e3f09-363">유효한 Azure AD 계정 자격 증명을 입력하면 디바이스가 연결된 Azure AD 조직에 가입하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-363">Once you enter valid Azure AD account credentials, the device will try to join the associated Azure AD organization.</span></span> <span data-ttu-id="e3f09-364">성공하면 디바이스가 해당 조직의 직원을 디바이스의 로컬 관리자로 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-364">If this succeeds, then the device will provision employees in that organization to be local admins on the device.</span></span> <span data-ttu-id="e3f09-365">Azure AD 테넌트가 구성된 경우에는 디바이스가 MDM에도 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-365">If your Azure AD tenant was configured for it, the device will also enroll into MDM.</span></span>

### <a href="" id="use-active-directory"></a><span data-ttu-id="e3f09-366">Active Directory 도메인 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-366">Use Active Directory Domain Services</span></span>

<span data-ttu-id="e3f09-367">이 페이지에는 Surface Hub가 보안 그룹을 디바이스 관리자로 프로비전할 수 있도록 도메인 가입을 위한 자격 증명을 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-367">This page will ask for credentials to join a domain so that the Surface Hub can provision a security group as administrators of the device.</span></span>

<span data-ttu-id="e3f09-368">디바이스가 도메인에 가입되고 나면 가입한 도메인의 보안 그룹을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-368">Once the device has been domain joined, you must specify a security group from the domain you joined.</span></span> <span data-ttu-id="e3f09-369">이 보안 그룹은 Surface Hub에서 관리자로 프로비전되며, 보안 그룹의 모든 사용자가 해당 도메인 자격 증명을 입력하여 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-369">This security group will be provisioned as administrators on the Surface Hub, and anyone from the security group can enter their domain credentials to access Settings.</span></span>

![도메인 가입 페이지를 사용한 관리자 설정을 보여 주는 이미지입니다.](images/setupdomainjoin.png)

### <span data-ttu-id="e3f09-371">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-371">Details</span></span>

<span data-ttu-id="e3f09-372">다음 입력이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-372">The following input is required:</span></span>

-   <span data-ttu-id="e3f09-373">**도메인:** 가입하려는 도메인의 FQDN(정규화된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-373">**Domain:** This is the fully qualified domain name (FQDN) of the domain that you want to join.</span></span> <span data-ttu-id="e3f09-374">이 도메인의 보안 그룹을 사용하여 디바이스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-374">A security group from this domain can be used to manage the device.</span></span>
-   <span data-ttu-id="e3f09-375">**사용자 이름:** 지정된 도메인에 가입할 수 있는 권한이 있는 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-375">**User name:** The user name of an account that has sufficient permission to join the specified domain.</span></span> 
-   <span data-ttu-id="e3f09-376">**암호:** 계정의 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-376">**Password:** The password for the account.</span></span>

<span data-ttu-id="e3f09-377">자격 증명이 확인된 후 보안 그룹 이름을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-377">After the credentials are verified, you will be asked to type a security group name.</span></span> <span data-ttu-id="e3f09-378">이 입력은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-378">This input is required.</span></span>

![보안 그룹 입력 페이지를 보여 주는 이미지입니다.](images/setupsecuritygroup-1.png)

### <span data-ttu-id="e3f09-380">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-380">What happens?</span></span>

<span data-ttu-id="e3f09-381">제공된 도메인, [Active Directory 도메인 서비스 사용 페이지](#use-active-directory) 의 계정 자격 증명 및 [이 디바이스 이름 지정](#name-this-device) 페이지의 디바이스 이름을 사용하여 Surface Hub가 도메인에 가입하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-381">Using the provided domain, account credentials from the [Use Active Directory Domain Services page](#use-active-directory) and the device name from the [Name this device](#name-this-device) page, the Surface Hub will attempt to join the domain.</span></span> <span data-ttu-id="e3f09-382">가입에 성공하면 첫 실행이 계속되고 보안 그룹을 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-382">If the join is successful, first run will continue, and will ask for a security group.</span></span> <span data-ttu-id="e3f09-383">가입에 실패하면 첫 실행이 중지되고 제공한 정보를 변경하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-383">If the join is not successful, first run will halt and ask you to change the information provided.</span></span>

<span data-ttu-id="e3f09-384">가입에 성공하면 **보안 그룹 입력** 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-384">If the join is successful, you'll see the **Enter a security group** page.</span></span> <span data-ttu-id="e3f09-385">이 페이지에서 **선택** 단추를 클릭하면 디바이스가 도메인에서 지정된 보안 그룹을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-385">When you click the **Select** button on this page, the device will search for the specified security group on your domain.</span></span> <span data-ttu-id="e3f09-386">찾으면 그룹이 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-386">If found, the group will be verified.</span></span> <span data-ttu-id="e3f09-387">**마침** 을 클릭하여 첫 실행 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-387">Click **Finish** to complete the first run process.</span></span>

>[!NOTE]
><span data-ttu-id="e3f09-388">Surface Hub를 도메인에 가입한 후에는 디바이스를 초기화하지 않고 가입 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-388">If you domain join the Surface Hub, you can't unjoin the device without resetting it.</span></span>

 

### <span data-ttu-id="e3f09-389">로컬 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="e3f09-389">Use a local admin</span></span>

<span data-ttu-id="e3f09-390">Azure AD(Azure Active Directory) 또는 AD(Active Directory)를 사용하여 Surface Hub를 관리하지 않으려는 경우 로컬 관리자 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-390">If you decide not to use Azure Active Directory (Azure AD) or Active Directory (AD) to manage the Surface Hub, you'll need to create a local admin account.</span></span>

![로컬 관리자의 관리자 계정 설정을 보여 주는 이미지입니다.](images/setuplocaladmin.png)

### <span data-ttu-id="e3f09-392">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3f09-392">Details</span></span>

<span data-ttu-id="e3f09-393">다음 입력이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-393">The following input is required:</span></span>

-   <span data-ttu-id="e3f09-394">**사용자 이름:** 이 Surface Hub에 대해 만들 로컬 관리자 계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-394">**User name:** This is the user name of the local admin account that will be created for this Surface Hub.</span></span>
-   <span data-ttu-id="e3f09-395">**암호:** 디바이스 계정의 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-395">**Password:** This is the password of the device account.</span></span>
-   <span data-ttu-id="e3f09-396">**암호 다시 입력:** 이전 상자와 동일한 암호를 입력하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-396">**Re-enter password:** Verifying the password as in the previous box.</span></span>

### <span data-ttu-id="e3f09-397">발생하는 동작</span><span class="sxs-lookup"><span data-stu-id="e3f09-397">What happens?</span></span>

<span data-ttu-id="e3f09-398">이 페이지는 여기에 입력된 자격 증명을 사용하여 새 관리자 계정을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-398">This page will attempt to create a new admin account using the credentials that you enter here.</span></span> <span data-ttu-id="e3f09-399">성공하면 첫 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-399">If it's successful, then first run will end.</span></span> <span data-ttu-id="e3f09-400">실패하면 다른 자격 증명을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-400">If not, you'll be asked for different credentials.</span></span>

## <a href="" id="update-surface-hub"></a><span data-ttu-id="e3f09-401">Surface Hub 업데이트</span><span class="sxs-lookup"><span data-stu-id="e3f09-401">Update the Surface Hub</span></span>


>[!IMPORTANT]
><span data-ttu-id="e3f09-402">업데이트를 수행하기 전에 키의 백업이 있는지 확인하기 위해 [BitLocker 키 저장](save-bitlocker-key-surface-hub.md)을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-402">Before you do the updates, make sure you read [Save your BitLocker key](save-bitlocker-key-surface-hub.md) in order to make sure you have a backup of the key.</span></span>

 

<span data-ttu-id="e3f09-403">최신 기능과 수정 사항을 가져오려면 앞의 첫 실행 단계를 모두 완료하는 즉시 Surface Hub를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-403">In order to get the latest features and fixes, you should update your Surface Hub as soon as you finish all of the preceding first-run steps.</span></span>

1.  <span data-ttu-id="e3f09-404">디바이스가 Windows 업데이트 서버 또는 WSUS(WindowsServer Update Services)에 액세스할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-404">Make sure the device has access to the Windows Update servers or to Windows Server Update Services (WSUS).</span></span> <span data-ttu-id="e3f09-405">WSUS를 구성하려면 [WSUS 사용](manage-windows-updates-for-surface-hub.md#use-windows-server-update-services)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3f09-405">To configure WSUS, see [Using WSUS](manage-windows-updates-for-surface-hub.md#use-windows-server-update-services).</span></span>
2.  <span data-ttu-id="e3f09-406">설정을 열고 **업데이트 및 보안**, **Windows 업데이트**, **업데이트 확인**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-406">Open Settings, click **Update & security**, then **Windows Update**, and then click **Check for updates**.</span></span>
3.  <span data-ttu-id="e3f09-407">업데이트를 사용할 수 있으면 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-407">If updates are available, they will be downloaded.</span></span> <span data-ttu-id="e3f09-408">다운로드가 완료된 후 **지금 업데이트** 단추를 클릭하여 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-408">Once downloading is complete, click the **Update now** button to install the updates.</span></span>
4.  <span data-ttu-id="e3f09-409">업데이트가 설치된 후 화면의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-409">Follow the onscreen prompts after the updates are installed.</span></span> <span data-ttu-id="e3f09-410">디바이스를 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f09-410">You may need to restart the device.</span></span>

 

 





