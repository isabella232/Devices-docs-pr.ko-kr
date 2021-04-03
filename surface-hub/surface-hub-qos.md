---
title: Surface Hub에서 서비스 품질 구현
ms.reviewer: ''
manager: laurawi
description: Surface Hub에서 QoS를 구성하는 방법을 알아보십시오.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470486"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="4bae0-103">Surface Hub에서 QoS(서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="4bae0-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="4bae0-104">QoS(서비스 품질)는 관리자가 실시간 오디오/비디오 및 응용 프로그램 공유 통신 환경을 최적화할 수 있도록 하는 네트워크 기술의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="4bae0-105">Surface Hub에서 비즈니스용 Skype에 대한 [QoS](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 구성은 [MDM(모바일](manage-settings-with-mdm-for-surface-hub.md) 장치 관리) 공급자 또는 프로비저닝 패키지를 사용하여 구성할 [수 있습니다.](provisioning-packages-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="4bae0-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="4bae0-106">이 절차에서는 Microsoft Intune을 사용하여 Surface Hub에 대한 QoS를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="4bae0-107">Intune에서 [사용자 지정 정책 을 생성합니다.](https://docs.microsoft.com/intune/custom-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="4bae0-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Intune의 사용자 지정 정책 만들기 대화 상자 스크린샷](images/qos-create.png)

2. <span data-ttu-id="4bae0-109">사용자 **지정 OMA-URI 설정에서**추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4bae0-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="4bae0-110">추가하는 각 설정에 대해 이름, 설명(선택 사항), 데이터 형식, OMA-URI 및 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![빈 OMA-URI 설정 대화 상자의 스크린샷](images/qos-setting.png)

3. <span data-ttu-id="4bae0-112">다음 사용자 지정 OMA-URI 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="4bae0-113">이름</span><span class="sxs-lookup"><span data-stu-id="4bae0-113">Name</span></span> | <span data-ttu-id="4bae0-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4bae0-114">Data type</span></span> | <span data-ttu-id="4bae0-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4bae0-115">OMA-URI</span></span><br><span data-ttu-id="4bae0-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="4bae0-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="4bae0-117">값</span><span class="sxs-lookup"><span data-stu-id="4bae0-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="4bae0-118">오디오 원본 포트</span><span class="sxs-lookup"><span data-stu-id="4bae0-118">Audio Source Port</span></span> | <span data-ttu-id="4bae0-119">문자열</span><span class="sxs-lookup"><span data-stu-id="4bae0-119">String</span></span> |  <span data-ttu-id="4bae0-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4bae0-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="4bae0-121">Skype 관리자로부터 값 얻기</span><span class="sxs-lookup"><span data-stu-id="4bae0-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="4bae0-122">오디오 DSCP</span><span class="sxs-lookup"><span data-stu-id="4bae0-122">Audio DSCP</span></span> | <span data-ttu-id="4bae0-123">정수</span><span class="sxs-lookup"><span data-stu-id="4bae0-123">Integer</span></span> |  <span data-ttu-id="4bae0-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="4bae0-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="4bae0-125">46</span><span class="sxs-lookup"><span data-stu-id="4bae0-125">46</span></span>
    <span data-ttu-id="4bae0-126">비디오 원본 포트</span><span class="sxs-lookup"><span data-stu-id="4bae0-126">Video Source Port</span></span> | <span data-ttu-id="4bae0-127">문자열</span><span class="sxs-lookup"><span data-stu-id="4bae0-127">String</span></span> |  <span data-ttu-id="4bae0-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4bae0-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="4bae0-129">Skype 관리자로부터 값 얻기</span><span class="sxs-lookup"><span data-stu-id="4bae0-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="4bae0-130">비디오 DSCP</span><span class="sxs-lookup"><span data-stu-id="4bae0-130">Video DSCP</span></span> | <span data-ttu-id="4bae0-131">정수</span><span class="sxs-lookup"><span data-stu-id="4bae0-131">Integer</span></span> |  <span data-ttu-id="4bae0-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="4bae0-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="4bae0-133">34</span><span class="sxs-lookup"><span data-stu-id="4bae0-133">34</span></span>
    <span data-ttu-id="4bae0-134">오디오 프로세스 이름</span><span class="sxs-lookup"><span data-stu-id="4bae0-134">Audio Process Name</span></span> | <span data-ttu-id="4bae0-135">문자열</span><span class="sxs-lookup"><span data-stu-id="4bae0-135">String</span></span> |  <span data-ttu-id="4bae0-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4bae0-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="4bae0-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="4bae0-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="4bae0-138">비디오 프로세스 이름</span><span class="sxs-lookup"><span data-stu-id="4bae0-138">Video Process Name</span></span> | <span data-ttu-id="4bae0-139">문자열</span><span class="sxs-lookup"><span data-stu-id="4bae0-139">String</span></span> |  <span data-ttu-id="4bae0-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4bae0-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="4bae0-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="4bae0-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="4bae0-142">각 **OMA-URI** 경로는 로 `./Device/Vendor/MSFT/NetworkQoSPolicy` 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="4bae0-143">예를 들어 오디오 원본 포트 설정의 전체 경로는 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="4bae0-144">정책이 만들어지면 Surface Hub에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="4bae0-145">현재 [NetworkQoSPolicy CSP에서](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) **IPProtocolMatchCondition** 설정을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="4bae0-146">이 설정을 구성하면 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bae0-146">If this setting is configured, the policy will fail to apply.</span></span>
 
