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
ms.openlocfilehash: f8a2bf8ddb75ca6dd3ff89e16fe0d37e099be29d
ms.sourcegitcommit: 85f5a2e67b34fe073ec588ed441ebee239ab0ac6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400739"
---
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a><span data-ttu-id="22b62-103">Microsoft Authenticator로 Surface Hub 로그인</span><span class="sxs-lookup"><span data-stu-id="22b62-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="22b62-104">조직의 사용자는 Android 및 iOS에서 사용 가능한 Microsoft Authenticator 앱을 사용하여 암호 없이 Surface Hub에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <a name="organization-prerequisites"></a><span data-ttu-id="22b62-105">조직 필수 조건</span><span class="sxs-lookup"><span data-stu-id="22b62-105">Organization prerequisites</span></span>

<span data-ttu-id="22b62-106">조직의 사용자를 암호 대신 휴대전화나 기타 장치로 Surface Hub에 로그인하도록 하려면 조직인 다음 필수 조건을 만족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="22b62-107">Azure Active Directory(Azure AD)에서 지원하는 조직은 하이브리드 또는 클라우드 전용 조직이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="22b62-108">자세한 내용은 [Azure Active Directory란?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22b62-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="22b62-109">Office 365 E3 구독 이상이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="22b62-110">[Multi-factor Authentication 구성](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="22b62-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="22b62-111">**모바일 앱을 통한 알림**이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![Multi-Factor Authentication 옵션](images/mfa-options.png)

- <span data-ttu-id="22b62-113">Office, SharePoint 등의 Azure AD 서비스에서 콘텐츠 호스팅을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="22b62-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="22b62-114">Surface Hub는 Windows 10 버전 1703 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="22b62-115">Surface Hub는 로컬 또는 도메인 가입 계정으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

## <a name="individual-prerequisites"></a><span data-ttu-id="22b62-116">개별 사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="22b62-116">Individual prerequisites</span></span>

- <span data-ttu-id="22b62-117">6.0 이상을 실행하는 Android폰 또는 iOS9 이상을 실행하는 iPhone 또는 iPad</span><span class="sxs-lookup"><span data-stu-id="22b62-117">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="22b62-118">적격 앱 스토어의 Microsoft Authenticator 앱의 최신 버전</span><span class="sxs-lookup"><span data-stu-id="22b62-118">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="22b62-119">iOS에서 앱 버전은 5.4.0 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-119">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="22b62-120">Windows 운영 체제를 실행하는 휴대폰에 설치된 Microsoft Authenticator 앱은 Surface Hub에 로그인하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-120">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="22b62-121">디바이스에서 사용할 수 있는 암호 또는 화면 잠금</span><span class="sxs-lookup"><span data-stu-id="22b62-121">Passcode or screen lock on your device is enabled</span></span>

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a><span data-ttu-id="22b62-122">Microsoft Authenticator 앱을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="22b62-122">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="22b62-123">회사 포털이 Android 디바이스에 설치된 경우 Microsoft Authenticator를 설정하기 전에 이를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-123">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="22b62-124">앱을 설정한 후 회사 포털을 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-124">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="22b62-125">이미 휴대폰에 Microsoft Authenticator를 설정했고 장치를 등록한 경우 로그인 지침으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-125">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="22b62-126">Multi-Factor Authentication에 대한 Microsoft Authenticator의 회사 또는 학교 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-126">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="22b62-127">IT 부서에서 제공되는 QR 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-127">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="22b62-128">도움말은 [Microsoft Authenticator 앱 시작](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22b62-128">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="22b62-129">**설정**으로 이동하여 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-129">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="22b62-130">계정 페이지로 돌아가 계정 드롭다운 메뉴에서 **전화 로그인 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-130">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a><span data-ttu-id="22b62-131">모임 중 Surface Hub에 로그인하는 방법</span><span class="sxs-lookup"><span data-stu-id="22b62-131">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="22b62-132">모임을 설정한 후 Surface Hub로 이동하고 **모임과 파일을 보려면 로그인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-132">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="22b62-133">Surface Hub에서 모임을 예약하는 방법을 모를 경우 [Surface Hub에서 모임 예약](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22b62-133">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![Surface Hub의 로그인 옵션 스크린샷](images/sign-in.png)

2. <span data-ttu-id="22b62-135">모임에 초대된 사람 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-135">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="22b62-136">자신(또는 로그인하려는 사람 - 이 사용자가 모임 전에 디바이스를 설정하는 단계를 거쳤는지 확인하세요)을 선택한 다음 **계속**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-136">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![모임에 참석한 사람 목록의 스크린샷](images/attendees.png)

    <span data-ttu-id="22b62-138">Surface Hub에서 코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-138">You'll see a code on the Surface Hub.</span></span>

    ![로그인 승인에 대한 코드 스크린샷](images/approve-signin.png)

3. <span data-ttu-id="22b62-140">로그인을 승인하려면 Authenticator 앱을 열고 Surface Hub에 표시되는 4자리 코드를 입력하고 **승인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-140">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="22b62-141">PIN을 입력하거나 지문을 사용하여 로그인을 완료하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-141">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![Microsoft Authenticator에서 로그인 승인 화면 스크린샷](images/approve-signin2.png)

<span data-ttu-id="22b62-143">이제 OneDrive 앱을 통해 모든 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b62-143">You can now access all files through the OneDrive app.</span></span>
