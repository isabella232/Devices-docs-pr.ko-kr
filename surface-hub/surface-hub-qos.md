---
title: Surface Hub에서 서비스 품질 구현
ms.reviewer: ''
manager: laurawi
description: Surface Hub에서 QoS를 구성 하는 방법에 대해 알아봅니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835191"
---
# <span data-ttu-id="899bc-103">Surface Hub에서 QoS (서비스 품질)를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="899bc-104">QoS (서비스 품질)는 관리자가 실시간 오디오/비디오 및 응용 프로그램 공유 통신 환경을 최적화 하는 데 사용할 수 있는 네트워크 기술의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="899bc-105">Surface Hub에서 비즈니스용 [Skype에 대해 QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 를 구성 하려면 [MDM (모바일 디바이스 관리) 공급자](manage-settings-with-mdm-for-surface-hub.md) 를 사용 하거나 [제공 패키지](provisioning-packages-for-surface-hub.md)를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="899bc-106">이 절차에서는 Microsoft Intune을 사용 하 여 Surface Hub에 대 한 QoS를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="899bc-107">Intune에서 [사용자 지정 정책을 만듭니다](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="899bc-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Intune의 사용자 지정 정책 만들기 대화 상자 스크린샷](images/qos-create.png)

2. <span data-ttu-id="899bc-109">**사용자 지정 OMA-URI 설정**에서 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="899bc-110">추가 하는 각 설정에 대해 이름, 설명 (선택 사항), 데이터 형식, OMA-URI 및 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![빈 OMA-URI 설정 대화 상자 스크린샷](images/qos-setting.png)

3. <span data-ttu-id="899bc-112">다음 사용자 지정 OMA-URI 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="899bc-113">이름</span><span class="sxs-lookup"><span data-stu-id="899bc-113">Name</span></span> | <span data-ttu-id="899bc-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="899bc-114">Data type</span></span> | <span data-ttu-id="899bc-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="899bc-115">OMA-URI</span></span><br><span data-ttu-id="899bc-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="899bc-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="899bc-117">값</span><span class="sxs-lookup"><span data-stu-id="899bc-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="899bc-118">오디오 원본 포트</span><span class="sxs-lookup"><span data-stu-id="899bc-118">Audio Source Port</span></span> | <span data-ttu-id="899bc-119">문자열</span><span class="sxs-lookup"><span data-stu-id="899bc-119">String</span></span> |  <span data-ttu-id="899bc-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="899bc-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="899bc-121">Skype 관리자에 게 서 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="899bc-122">오디오 DSCP</span><span class="sxs-lookup"><span data-stu-id="899bc-122">Audio DSCP</span></span> | <span data-ttu-id="899bc-123">정수</span><span class="sxs-lookup"><span data-stu-id="899bc-123">Integer</span></span> |  <span data-ttu-id="899bc-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="899bc-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="899bc-125">46</span><span class="sxs-lookup"><span data-stu-id="899bc-125">46</span></span>
    <span data-ttu-id="899bc-126">비디오 원본 포트</span><span class="sxs-lookup"><span data-stu-id="899bc-126">Video Source Port</span></span> | <span data-ttu-id="899bc-127">문자열</span><span class="sxs-lookup"><span data-stu-id="899bc-127">String</span></span> |  <span data-ttu-id="899bc-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="899bc-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="899bc-129">Skype 관리자에 게 서 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="899bc-130">비디오 DSCP</span><span class="sxs-lookup"><span data-stu-id="899bc-130">Video DSCP</span></span> | <span data-ttu-id="899bc-131">정수</span><span class="sxs-lookup"><span data-stu-id="899bc-131">Integer</span></span> |  <span data-ttu-id="899bc-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="899bc-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="899bc-133">34</span><span class="sxs-lookup"><span data-stu-id="899bc-133">34</span></span>
    <span data-ttu-id="899bc-134">오디오 프로세스 이름</span><span class="sxs-lookup"><span data-stu-id="899bc-134">Audio Process Name</span></span> | <span data-ttu-id="899bc-135">문자열</span><span class="sxs-lookup"><span data-stu-id="899bc-135">String</span></span> |  <span data-ttu-id="899bc-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="899bc-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="899bc-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="899bc-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="899bc-138">비디오 프로세스 이름</span><span class="sxs-lookup"><span data-stu-id="899bc-138">Video Process Name</span></span> | <span data-ttu-id="899bc-139">문자열</span><span class="sxs-lookup"><span data-stu-id="899bc-139">String</span></span> |  <span data-ttu-id="899bc-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="899bc-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="899bc-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="899bc-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="899bc-142">각 **OMA URI** 경로는로 시작 `./Device/Vendor/MSFT/NetworkQoSPolicy` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="899bc-143">예를 들어 오디오 원본 포트 설정의 전체 경로는 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 입니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="899bc-144">정책이 만들어졌으면 [Surface Hub에 배포 합니다.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="899bc-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="899bc-145">현재 [Networkqospolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)에서 **Ipprotocolmatchcondition** 설정을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="899bc-146">이 설정이 구성 되 면 정책이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="899bc-146">If this setting is configured, the policy will fail to apply.</span></span>
 
