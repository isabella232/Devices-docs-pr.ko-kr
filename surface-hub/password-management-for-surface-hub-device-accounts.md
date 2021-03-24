---
title: 암호 관리(Surface Hub)
description: 모든 Microsoft Surface Hub 디바이스 계정은 인증하고 디바이스의 기능을 사용하도록 설정하려면 암호가 필요합니다.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: 암호, 암호 관리, 암호 순환, 디바이스 계정
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445584"
---
# <a name="password-management-surface-hub"></a><span data-ttu-id="526f5-104">암호 관리(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="526f5-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="526f5-105">모든 Microsoft Surface Hub 디바이스 계정은 인증하고 디바이스의 기능을 사용하도록 설정하려면 암호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="526f5-106">보안상의 이유로 이 암호를 주기적으로 변경(또는 “순환”)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="526f5-107">그러나 디바이스 계정의 암호가 변경되면 이전에 Surface Hub에 저장된 암호가 부적합해지고, 디바이스 계정에 종속된 모든 기능을 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="526f5-108">이러한 기능을 다시 사용하도록 설정하려면 설정 앱에서 Surface Hub의 디바이스 계정 암호를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="526f5-109">Surface Hub 디바이스 계정의 암호 관리를 간소화할 수 있는 다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="526f5-110">디바이스 계정의 암호 만료 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="526f5-111">Surface Hub가 디바이스 계정의 암호를 자동으로 순환할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <a name="turn-off-password-rotation-for-the-device-account"></a><span data-ttu-id="526f5-112">디바이스 계정의 암호 순환 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="526f5-113">디바이스 계정의 **PasswordNeverExpires** 속성을 True로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="526f5-114">조직의 보안 요구 사항을 충족하는지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a><span data-ttu-id="526f5-115">Surface Hub가 디바이스 계정의 암호를 자동으로 순환할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="526f5-116">Surface Hub는 수동으로 업데이트하지 않고도 디바이스 계정의 암호를 자동으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-116">The Surface Hub can automatically change a device account's password without requiring you to manually update it.</span></span> <span data-ttu-id="526f5-117">설정 Surface Hub 계정 **에서**이  >  **기능을 사용하도록 설정할 수**  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="526f5-117">You can enable this feature in **Settings** > **Surface Hub** > **Accounts**.</span></span> <span data-ttu-id="526f5-118">암호 순환을 설정하면 Surface Hub는 유지 관리 시간 동안 7일마다 암호를 변경하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-118">If you turn on Password Rotation, the Surface Hub will attempt to change the password every 7 days during maintenance hours.</span></span> <span data-ttu-id="526f5-119">모임 중에 암호가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-119">Passwords do not change during a meeting.</span></span> <span data-ttu-id="526f5-120">마지막 암호 순환 이후 7일이 지난 경우 Surface Hub가 꺼진 경우 켜져 있는 즉시 또는 성공할 때까지 10분마다 암호를 변경하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-120">If 7 days have passed since the last password rotation, but the Surface Hub was off, it will attempt to change the password immediately when turned on or every 10 minutes until successful.</span></span>

<span data-ttu-id="526f5-121">자동으로 생성된 암호에는 대문자 및 소문자, 숫자 및 특수 문자의 조합을 포함하여 15-32자까지 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-121">The automatically generated passwords contain 15-32 characters including a combination of uppercase and lowercase letters, numbers, and special characters.</span></span> <span data-ttu-id="526f5-122">디바이스 계정의 암호를 변경하면 새 암호가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-122">Note that when the device account's password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="526f5-123">계정에 로그인하거나 암호를 다시 제공해야 하는 경우(예: Surface Hub에서 디바이스 계정 설정을 변경하려는 경우) Active Directory 또는 Microsoft 365 관리 포털을 사용하여 암호를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-123">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Microsoft 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="526f5-124">Surface Hub에 디바이스 계정을 추가할 때 사용되는 형식은 [](prepare-your-environment-for-surface-hub.md) 암호 회전이 작동하기 위해 어떤 장치 회원 옵션을 사용해야 하는지 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-124">The format used when adding the device account to the Surface Hub has an impact on which [device affiliation](prepare-your-environment-for-surface-hub.md) option must be used in order for password rotation to work.</span></span> <span data-ttu-id="526f5-125">**도메인\사용자** 이름 형식의 계정을 추가하는 경우 초기 설정 중에 Hub를 On-premises Active Directory와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-125">If adding the account in **domain\username** format, affiliate the Hub with on-premises Active Directory during initial setup.</span></span> <span data-ttu-id="526f5-126">계정을 형식으로 추가하는 경우 초기 설정 중에 `username@domain.com` Azure Active Directory와 허브를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-126">If adding the account in `username@domain.com` format, affiliate the Hub with Azure Active Directory during initial setup.</span></span> <span data-ttu-id="526f5-127">그렇지 않으면 암호 순환이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="526f5-127">Otherwise, password rotation will not work.</span></span>
