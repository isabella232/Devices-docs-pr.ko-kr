---
title: Surface Hub 2S 암호 없는 휴대폰 로그인 구성
description: 모바일 장치에서 비밀 번호 없는 휴대폰 로그인을 사용 하 여 Surface Hub 2S에 로그인 하는 방법을 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 95873e41588a6f07ece53fd04f7d63bf56143914
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835367"
---
# <span data-ttu-id="c941b-104">Surface Hub 2S 암호 없는 휴대폰 로그인 구성</span><span class="sxs-lookup"><span data-stu-id="c941b-104">Configure password-less phone sign-in  for Surface Hub 2S</span></span>

<span data-ttu-id="c941b-105">비밀 번호가 적은 휴대폰 로그인은 Surface Hub 2S에서 모임과 파일에 로그인 하는 것을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-105">Password-less phone sign-in simplifies signing-in to your meetings and files on Surface Hub 2S.</span></span>

> [!NOTE]
> <span data-ttu-id="c941b-106">비밀 번호가 적은 휴대폰 로그인을 사용 하려면 기본 전자 메일 주소가 UPN과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-106">Password-less phone sign-in requires that your primary email address must match your UPN.</span></span>

## <span data-ttu-id="c941b-107">비밀 번호가 적은 휴대폰 로그인을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="c941b-107">To set up password-less phone sign-in</span></span>

1. <span data-ttu-id="c941b-108">IPhone 또는 Android 용 [Microsoft Authenticator](https://www.microsoft.com/account/authenticator) 앱을 휴대폰에 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-108">Download the [Microsoft Authenticator](https://www.microsoft.com/account/authenticator) app for iPhone or Android to your phone.</span></span>
2. <span data-ttu-id="c941b-109">PC에서으로 이동 하 여 [https://aka.ms/MFASetup](https://aka.ms/MFASetup) 계정으로 로그인 하 고 다음을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="c941b-109">From your PC, go to [https://aka.ms/MFASetup](https://aka.ms/MFASetup) , sign in with your account, and select **Next.**</span></span>
3. <span data-ttu-id="c941b-110">추가 보안 확인 화면에서 모바일 앱을 선택 하 고 확인 코드를 사용한 다음 **설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-110">In the Additional security verification screen, select Mobile App and Use verification code, and then select **Setup**.</span></span>

## <span data-ttu-id="c941b-111">모바일 앱을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="c941b-111">To configure mobile app</span></span>

1. <span data-ttu-id="c941b-112">휴대폰의 Microsoft authenticator 앱에서 계정을 추가 하 고 **회사 또는 학교 계정을**선택한 다음 PC에 표시 되는 QR 코드를 스캔 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-112">In the Microsoft authenticator app on your phone, add an account, choose **Work or School Account**, and then scan the QR code displayed on your PC</span></span>
2. <span data-ttu-id="c941b-113">휴대폰에 알림을 보낸 다음 로그인 요청을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-113">Send a notification to your phone and then approve the sign-in request.</span></span>
3. <span data-ttu-id="c941b-114">휴대폰의 인증자 앱에서 계정 옆에 있는 드롭다운 메뉴를 사용 하 여 **전화 로그인 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-114">In the Authenticator app on your phone, use the drop-down menu next to your account and select **Enable phone sign-in**.</span></span>
4. <span data-ttu-id="c941b-115">필요한 경우 조직에 디바이스를 등록 하 고 화면에 나타나는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-115">If required, register your device with your organization and follow the on-screen instructions.</span></span>

## <span data-ttu-id="c941b-116">Surface Hub에 로그인 하려면</span><span class="sxs-lookup"><span data-stu-id="c941b-116">To sign in to Surface Hub</span></span>

1. <span data-ttu-id="c941b-117">Surface Hub에서 **내 모임 및 파일** 에 로그인 하 고 메시지가 표시 되 면 **알림 보내기를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-117">On Surface Hub, sign into **My meetings and files** and select **Send notification** when prompted.</span></span>
2. <span data-ttu-id="c941b-118">휴대폰에 표시 되는 번호와 Surface Hub에 표시 된 번호를 일치 하 여 로그인 요청을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-118">Match the number displayed on your phone with the number displayed on Surface Hub to approve your sign-in request.</span></span>
3. <span data-ttu-id="c941b-119">메시지가 표시 되 면 휴대폰에 PIN 또는 생체 인식 ID를 입력 하 여 로그인을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c941b-119">If prompted, enter the PIN or biometric ID on your phone to complete sign-in.</span></span>

## <span data-ttu-id="c941b-120">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="c941b-120">Learn more</span></span>
<span data-ttu-id="c941b-121">자세한 내용은 [Microsoft Authenticator 앱을 사용 하 여 비밀 번호-적은 전화 로그인](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-phone-sign-in)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c941b-121">For more information, see [Password-less phone sign-in with the Microsoft Authenticator app](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-phone-sign-in).</span></span>
