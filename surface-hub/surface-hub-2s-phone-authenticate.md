---
title: Surface Hub에서 비밀 번호 더 적은 로그인 구성
description: Surface Hub에 간편 하 게 로그인 하는 방법을 알아보세요.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893050"
---
# <span data-ttu-id="68f3e-104">Surface Hub에서 암호를 더 적게 로그인 구성</span><span class="sxs-lookup"><span data-stu-id="68f3e-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="68f3e-105">암호를 사용 하지 않는 로그인은 앱, 모임 및 파일에 대 한 액세스를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="68f3e-106">Surface Hub는 조직에서 제공 하는 Microsoft Authenticator 앱 및 FIDO2 보안 키를 사용 하 여 로그인을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="68f3e-107">**중요:** 이 콘텐츠는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="68f3e-108">Passwordless 로그인을 사용 하려면 IT 관리자가 조직에 대해 passwordless 인증을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="68f3e-109">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68f3e-109">For more information, see:</span></span>

- [<span data-ttu-id="68f3e-110">Passwordless 휴대폰 로그인 사용</span><span class="sxs-lookup"><span data-stu-id="68f3e-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="68f3e-111">Passwordless 보안 키 로그인 사용</span><span class="sxs-lookup"><span data-stu-id="68f3e-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="68f3e-112">Microsoft Authenticator 앱을 사용 하 여 로그인 구성</span><span class="sxs-lookup"><span data-stu-id="68f3e-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="68f3e-113">**참고:** Windows 10 팀 2020 업데이트로 시작 하는 사용자는 Azure AD의 기본 전자 메일 별칭, UPN (사용자 계정 이름)을 사용 하 여 Microsoft 인증자를 사용 하 여 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="68f3e-114">예를 들어 사용자는 기본 별칭 (John.Doe@contoso.com) 또는 UPN (jdoe@contoso.com) 중 하나를 사용 하 여 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="68f3e-115">Microsoft Authenticator 앱은 모바일 장치를 사용 하 여 Surface Hub에 로그인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="68f3e-116">Microsoft Authenticator를 사용 하 여 로그인을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="68f3e-117">모바일 장치에서 Microsoft Authenticator 앱을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="68f3e-118">Google Android: Android 장치에서 Google Play로 이동 하 여 [Microsoft Authenticator 앱을 다운로드 하 고 설치](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="68f3e-119">Apple ios: Apple iOS 장치에서 App Store로 이동 하 여 [Microsoft Authenticator 앱을 다운로드 하 고 설치](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="68f3e-120">PC 또는 학교 계정에 대 한 [보안 정보 페이지에서 Microsoft Authenticator 앱](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) 을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="68f3e-121">모바일 장치의 Microsoft Authenticator 앱에서 회사 또는 학교 계정에 대해 [휴대폰 로그인을 켜고 사용](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="68f3e-122">FIDO2 보안 키를 사용 하 여 로그인 구성</span><span class="sxs-lookup"><span data-stu-id="68f3e-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="68f3e-123">FIDO2 보안 키를 사용 하 여 Surface Hub에 로그인 하는 것이 더 적은 Windows 10 팀 2020 업데이트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68f3e-124">Surface Hub는 USB 보안 키만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="68f3e-125">조직에서 제공 하는 FIDO2 보안 키를 사용 하 여 Surface Hub에 로그인 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="68f3e-126">보안 키를 사용 하 여 로그인을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="68f3e-127">PC에서 페이지로 이동 하 여 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 회사 또는 학교 계정에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="68f3e-128">왼쪽 탐색 창 또는 **보안 정보** 블록의 링크에서 **보안 정보** 를 선택 하 고 **보안 정보** 페이지에서 **메서드 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="68f3e-129">**메서드 추가** 페이지의 드롭다운 목록에서 **보안 키** 를 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="68f3e-130">**보안 키** 페이지에서 **USB 장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="68f3e-131">보안 키를 준비 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="68f3e-132">나타나는 대화 상자에서 지침에 따라 보안 키를 삽입 하 고, PIN을 만들거나 입력 하 고, 필요한 제스처 (생체 인식 또는 터치)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="68f3e-133">**보안 키** 페이지에서 보안 키에 이름을 지정한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="68f3e-134">**완료** 를 선택 하 여 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="68f3e-135">Surface Hub에 로그인</span><span class="sxs-lookup"><span data-stu-id="68f3e-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="68f3e-136">Passwordless 로그인을 구성한 후에는이를 사용 하 여 Surface Hub의 앱, 모임 및 파일에 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="68f3e-137">모임에 빠르게 참가 하 고 최근 Microsoft 365 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="68f3e-138">자세한 내용은 [**로그인 하 여 모임 및 파일 보기**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f3e-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="68f3e-139">화이트 보드, PowerPoint, Word, Excel, OneDrive, Power BI 등의 Microsoft 앱에 빠르게 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="68f3e-140">새 Microsoft Edge에 빠르게 로그인 하 여 즐겨찾기 및 검색 환경 설정에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="68f3e-141">자세한 내용은 [새 Microsoft Edge 설치 및 구성을](surface-hub-install-chromium-edge.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f3e-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="68f3e-142">Surface Hub에 로그인 한 후 **세션 종료**를 선택할 때까지 다시 로그인 하지 않아도 다른 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="68f3e-143">**세션 종료** 를 선택 하면 장치에서 자격 증명, 파일 및 개인 데이터가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="68f3e-144">자세한 내용은 [세션 종료](finishing-your-surface-hub-meeting.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f3e-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="68f3e-145">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="68f3e-145">Learn more</span></span>

- [<span data-ttu-id="68f3e-146">Azure Active Directory에 대 한 암호 인증 옵션을 간단히 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="68f3e-147">Microsoft Authenticator 앱을 사용 하 여 암호 보다 적은 로그인</span><span class="sxs-lookup"><span data-stu-id="68f3e-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="68f3e-148">FIDO2 보안 키를 사용 하 여 암호를 덜 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f3e-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

