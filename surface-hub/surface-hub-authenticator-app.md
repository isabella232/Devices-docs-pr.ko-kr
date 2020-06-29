---
title: Microsoft Authenticator로 Surface Hub 로그인
description: 모바일 디바이스에서 Microsoft Authenticator를 사용하여 Surface Hub에 로그인합니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835255"
---
# <span data-ttu-id="eade1-103">Microsoft Authenticator로 Surface Hub 로그인</span><span class="sxs-lookup"><span data-stu-id="eade1-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="eade1-104">조직의 사용자는 Android 및 iOS에서 사용 가능한 Microsoft Authenticator 앱을 사용하여 암호 없이 Surface Hub에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <span data-ttu-id="eade1-105">조직 필수 조건</span><span class="sxs-lookup"><span data-stu-id="eade1-105">Organization prerequisites</span></span>

<span data-ttu-id="eade1-106">조직의 사용자를 암호 대신 휴대전화나 기타 장치로 Surface Hub에 로그인하도록 하려면 조직인 다음 필수 조건을 만족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="eade1-107">Azure Active Directory(Azure AD)에서 지원하는 조직은 하이브리드 또는 클라우드 전용 조직이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="eade1-108">자세한 내용은 [Azure Active Directory란?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eade1-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="eade1-109">Office 365 E3 구독 이상이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="eade1-110">[Multi-factor Authentication 구성](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="eade1-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="eade1-111">**모바일 앱을 통한 알림**이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![Multi-Factor Authentication 옵션](images/mfa-options.png)

- <span data-ttu-id="eade1-113">Office, SharePoint 등의 Azure AD 서비스에서 콘텐츠 호스팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="eade1-114">Surface Hub는 Windows 10 버전 1703 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="eade1-115">Surface Hub는 로컬 또는 도메인 가입 계정으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

<span data-ttu-id="eade1-116">현재 Microsoft Authenticator를 사용하여 Azure AD에 가입된 Surface Hub에 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-116">Currently, you cannot use Microsoft Authenticator to sign in to Surface Hubs that are joined to Azure AD.</span></span>

## <span data-ttu-id="eade1-117">개별 사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="eade1-117">Individual prerequisites</span></span>

- <span data-ttu-id="eade1-118">6.0 이상을 실행하는 Android폰 또는 iOS9 이상을 실행하는 iPhone 또는 iPad</span><span class="sxs-lookup"><span data-stu-id="eade1-118">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="eade1-119">적격 앱 스토어의 Microsoft Authenticator 앱의 최신 버전</span><span class="sxs-lookup"><span data-stu-id="eade1-119">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="eade1-120">iOS에서 앱 버전은 5.4.0 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-120">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="eade1-121">Windows 운영 체제를 실행하는 휴대폰에 설치된 Microsoft Authenticator 앱은 Surface Hub에 로그인하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-121">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="eade1-122">디바이스에서 사용할 수 있는 암호 또는 화면 잠금</span><span class="sxs-lookup"><span data-stu-id="eade1-122">Passcode or screen lock on your device is enabled</span></span>

- <span data-ttu-id="eade1-123">표준 SMTP 메일 주소(예: joe@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eade1-123">A standard SMTP email address (example: joe@contoso.com).</span></span> <span data-ttu-id="eade1-124">비 표준 또는 베니티 SMTP 메일 주소(예: firstname.lastname@contoso.com)는 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-124">Non-standard or vanity SMTP email addresses (example: firstname.lastname@contoso.com) currently don’t work.</span></span>

## <span data-ttu-id="eade1-125">Microsoft Authenticator 앱을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="eade1-125">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="eade1-126">회사 포털이 Android 디바이스에 설치된 경우 Microsoft Authenticator를 설정하기 전에 이를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-126">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="eade1-127">앱을 설정한 후 회사 포털을 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-127">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="eade1-128">이미 휴대폰에 Microsoft Authenticator를 설정했고 장치를 등록한 경우 로그인 지침으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-128">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="eade1-129">Multi-Factor Authentication에 대한 Microsoft Authenticator의 회사 또는 학교 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-129">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="eade1-130">IT 부서에서 제공되는 QR 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-130">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="eade1-131">도움말은 [Microsoft Authenticator 앱 시작](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eade1-131">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="eade1-132">**설정**으로 이동하여 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-132">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="eade1-133">계정 페이지로 돌아가 계정 드롭다운 메뉴에서 **전화 로그인 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-133">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <span data-ttu-id="eade1-134">모임 중 Surface Hub에 로그인하는 방법</span><span class="sxs-lookup"><span data-stu-id="eade1-134">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="eade1-135">모임을 설정한 후 Surface Hub로 이동하고 **모임과 파일을 보려면 로그인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-135">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="eade1-136">Surface Hub에서 모임을 예약하는 방법을 모를 경우 [Surface Hub에서 모임 예약](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eade1-136">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![Surface Hub의 로그인 옵션 스크린샷](images/sign-in.png)

2. <span data-ttu-id="eade1-138">모임에 초대된 사람 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-138">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="eade1-139">자신(또는 로그인하려는 사람 - 이 사용자가 모임 전에 디바이스를 설정하는 단계를 거쳤는지 확인하세요)을 선택한 다음 **계속**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-139">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![모임에 참석한 사람 목록의 스크린샷](images/attendees.png)

    <span data-ttu-id="eade1-141">Surface Hub에서 코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-141">You'll see a code on the Surface Hub.</span></span>

    ![로그인 승인에 대한 코드 스크린샷](images/approve-signin.png)

3. <span data-ttu-id="eade1-143">로그인을 승인하려면 Authenticator 앱을 열고 Surface Hub에 표시되는 4자리 코드를 입력하고 **승인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-143">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="eade1-144">PIN을 입력하거나 지문을 사용하여 로그인을 완료하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-144">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![Microsoft Authenticator에서 로그인 승인 화면 스크린샷](images/approve-signin2.png)

<span data-ttu-id="eade1-146">이제 OneDrive 앱을 통해 모든 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eade1-146">You can now access all files through the OneDrive app.</span></span>