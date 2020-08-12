---
title: Surface Hub에 대한 Windows 10 버전 1703의 새로운 기능
description: Windows 10 버전 1703(크리에이터스 업데이트)는 Microsoft Surface Hub에 새로운 기능을 제공합니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924944"
---
# <span data-ttu-id="1938e-103">Microsoft Surface Hub에 대한 Windows 10 버전 1703의 새로운 기능은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1938e-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="1938e-104">Surface Hub 엔지니어 Jordan Marchese가 소개하는 Microsoft Surface Hub의 현재 Windows 10 버전 1703(크리에이터스 업데이트)를 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="1938e-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="1938e-105">Windows 10, 버전 1703(크리에이터스 업데이트라고도 함)은 Microsoft Surface Hub에 다음과 같은 변경 내용을 도입하였습니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="1938e-106">새로운 설정</span><span class="sxs-lookup"><span data-stu-id="1938e-106">New settings</span></span>

<span data-ttu-id="1938e-107">MDM(모바일 디바이스 관리) 및 CSP(구성 서비스 공급자)에 설정이 추가되어 Surface Hub 관리 기능을 확장하였습니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="1938e-108">[새 설정에 추가된 내용](manage-settings-with-mdm-for-surface-hub.md):</span><span class="sxs-lookup"><span data-stu-id="1938e-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="1938e-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="1938e-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="1938e-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="1938e-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="1938e-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="1938e-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="1938e-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="1938e-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="1938e-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="1938e-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="1938e-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="1938e-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="1938e-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="1938e-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="1938e-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="1938e-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="1938e-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="1938e-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="1938e-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="1938e-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="1938e-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="1938e-119">System/AllowStorageCard</span></span>

<span data-ttu-id="1938e-120">추가 설정은 새 [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) 및 [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="1938e-121">프로비전 마법사</span><span class="sxs-lookup"><span data-stu-id="1938e-121">Provisioning wizard</span></span>

<span data-ttu-id="1938e-122">사용하기 쉬운 마법사로 여러 Surface Hub 디바이스에 적용할 수 있는 프로비저닝 패키지를 신속하게 만들 수 있으며 Azure Active Directory에 대한 대량 가입이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="1938e-123">Surface Hub 프로비저닝 패키지를 만드는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1938e-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![Surface Hub 디바이스 프로비저닝 마법사의 단계](images/wcd-wizard.png)
    
## <span data-ttu-id="1938e-125">기존 무선 네트워크 또는 LAN의 Miracast</span><span class="sxs-lookup"><span data-stu-id="1938e-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="1938e-126">Microsoft는 직접 무선 링크가 아니라 [로컬 네트워크를 통해 Miracast 스트림을 보낼 수 있는](miracast-over-infrastructure.md) 기능을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="1938e-127">클라우드 복구</span><span class="sxs-lookup"><span data-stu-id="1938e-127">Cloud recovery</span></span>

<span data-ttu-id="1938e-128">Surface Hub 디바이스를 초기화하면 이제 클라우드에서 운영 체제의 초기 빌드를 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="1938e-129">클라우드 복구에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="1938e-130">프록시 서버를 사용하는 경우 클라우드 복구는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![다시 설치](images/reinstall.png)
    
## <span data-ttu-id="1938e-132">세션 종료</span><span class="sxs-lookup"><span data-stu-id="1938e-132">End session</span></span>

<span data-ttu-id="1938e-133">**완료**가 이제 **세션 종료**로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1938e-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="1938e-134">세션 종료를 사용하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1938e-134">Learn how to use End session.</span></span>](finishing-your-surface-hub-meeting.md) 

![세션 종료](images/end-session.png)



 

 
