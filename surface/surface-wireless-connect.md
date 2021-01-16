---
title: Surface 장치에 대한 Wi-Fi 연결 최적화
description: 이 항목에서는 Surface Wi-Fi 환경 및 모바일 시나리오에서 계속 연결되도록 하는 권장 설정에 대해 설명합니다.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.date: 01/15/2021
ms.openlocfilehash: 69ca7bc7383a122dfd4f069135319b92ff7edfb0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271382"
---
# <span data-ttu-id="760f4-103">Surface 장치에 대한 Wi-Fi 연결 최적화</span><span class="sxs-lookup"><span data-stu-id="760f4-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="760f4-104">하루 종일 배터리 사용 수명과 연결된 상태 유지를 위해 Surface 장치는 성능과 전원 절약의 균형을 조정하는 무선 연결 설정을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="760f4-105">가장 까다로운 모바일 시나리오 외부에서 사용자는 기본 네트워크 어댑터 또는 관련 설정을 수정하지 않고도 충분한 무선 연결을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> <span data-ttu-id="760f4-106">이 페이지에서는 Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3 및 Surface Pro 7을 비롯한 최신 Surface 장치를 사용하는 모바일 시나리오에서 주요 무선 연결 고려 사항을 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-106">This page highlights key wireless connectivity considerations in mobile scenarios using the latest Surface devices including Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3, and Surface Pro 7.</span></span>

## <span data-ttu-id="760f4-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="760f4-107">Prerequisites</span></span>

<span data-ttu-id="760f4-108">이 문서에서는 주요 장비 공급업체의 모범 사례 권장 사항에 따라 802.11n(Wi-Fi 4) 이상을 지원하는 무선 네트워크를 성공적으로 배포했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-108">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="760f4-109">최적의 로밍 기능을 위한 액세스 지점 구성</span><span class="sxs-lookup"><span data-stu-id="760f4-109">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="760f4-110">다양한 유형의 클라이언트 장치에서 일반적으로 액세스하는 무선 네트워크를 관리하는 경우 [802.11k, 802.11v 및 802.11r의](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)빠른 로밍에 설명된 바와 같이 WLAN의 AP(액세스 지점)에서 특정 프로토콜을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-110">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="760f4-111">Surface 디바이스는 다음과 같은 무선 프로토콜을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-111">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="760f4-112">802.11r.</span><span class="sxs-lookup"><span data-stu-id="760f4-112">802.11r.</span></span>** <span data-ttu-id="760f4-113">"빠른**BSS** 전환"은 디바이스를 이동할 때 디바이스가 다른 AP에 액세스하기 전에 필요한 프레임 수를 줄여 새 무선 액세스 지점에 빠르게 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-113">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span> <span data-ttu-id="760f4-114">2019년 이후 출시된 새로운 Surface 디바이스에서 최종 사용자는 디바이스에서 로밍 적극성 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-114">In the new generation of Surface devices released since 2019, end users may gain access to roaming aggressiveness settings on their device.</span></span> <span data-ttu-id="760f4-115">기본 설정을 수정하는 것은 권장되지는 않습니다. 그러나 사용자는 이 기능을 인식하고 특정 설정이 연결된 상태로 유지되는 기능에 어떤 영향을 줄 수 있는지 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-115">Although modifying default settings is not recommended, users should be aware of this capability and understand how specific settings can impact their ability to remain connected.</span></span>
- **<span data-ttu-id="760f4-116">802.11k.</span><span class="sxs-lookup"><span data-stu-id="760f4-116">802.11k.</span></span>** <span data-ttu-id="760f4-117">**"인접 보고서"는** 인접한 액세스 지점의 현재 조건에 대한 정보를 장치에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-117">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="760f4-118">이는 Surface 디바이스가 AP 사용률과 같은 신호 강도가 아니라 다른 조건을 사용하여 최상의 AP를 선택하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-118">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="760f4-119">특정 Surface 디바이스는 802.11k와 매우 같은 기능을 하는 802.11v "BSS 전환 관리 프레임"을 사용하여 가까운 후보 AP에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-119">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="760f4-120">여기에는 Surface Pro 7+, Surface Go, Surface Go 2, Surface Pro 7, Surface Pro X 및 Surface 노트북 3이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-120">These include Surface Pro 7+, Surface Go, Surface Go 2, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="760f4-121">사용자 설정 관리</span><span class="sxs-lookup"><span data-stu-id="760f4-121">Managing user settings</span></span>

<span data-ttu-id="760f4-122">모든 액세스 지점에서 802.11r 및 802.11k를 지원하는 잘 설계된 네트워크를 통해 최적의 로밍 기능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-122">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="760f4-123">사용자에게 최상의 무선 환경을 제공하도록 네트워크가 제대로 구성되어 있는지 확인하려면 개별 디바이스에서 사용자 설정을 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-123">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> 

### <span data-ttu-id="760f4-124">권장되는 사용자 설정 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="760f4-124">Recommended user settings and best practices</span></span>

<span data-ttu-id="760f4-125">특정 상황에서는 Surface 디바이스에 기본 제공되는 고급 네트워크 어댑터 설정을 수정하면 보다 안정적인 연결을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-125">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="760f4-126">그러나 액세스 지점 문제, 네트워킹 디자인 결점 또는 환경 사이트 문제로 인해 무선 리소스에 연결할 수 없는 경우가 더 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-126">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="760f4-127">Surface Pro 또는 Surface Go를 보유하는 방법도 신호 강도에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-127">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="760f4-128">대역폭 손실이 발생하는 경우 디스플레이의 맨 위에 있지 않은지, Wi-Fi 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-128">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="760f4-129">디스플레이 위쪽을 잡아도 무선 신호가 차단되지는 않습니다. 그러나 장치 드라이버가 연결을 줄이는 변경을 시작하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-129">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="760f4-130">이중 대역폭 기능에 대한 기본 자동 설정 유지</span><span class="sxs-lookup"><span data-stu-id="760f4-130">Keep default Auto setting for dual bandwidth capability</span></span>

<span data-ttu-id="760f4-131">대부분의 Surface 장치에서는 5GHz 이상 무선 APS에만 연결하거나, 2.4GHz를 통해만 연결하거나, 운영 체제에서 최상의 옵션(기본 자동 설정)을 선택하도록 클라이언트 네트워크 어댑터 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-131">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="760f4-132">네트워크 어댑터 설정에 액세스하려면 다음으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-132">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="760f4-133">**시작**  >  **제어판**  >  **네트워크 및 공유 센터**  >  **Wi-Fi 어댑터**  >  **속성**  >  **구성**  >  **고급**.</span><span class="sxs-lookup"><span data-stu-id="760f4-133">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi-band settings\*](images/wifi-band.png) <br>

<span data-ttu-id="760f4-135">2.4GHz는 5GHz에 대한 몇 가지 이점이 있습니다. 벽이나 기타 실선 개체를 통해 더 확장하고 더 쉽게 침투합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-135">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="760f4-136">5GHz에 연결하는 명확한 사용 사례가 없는 한 가능한 부정적인 결과를 피하기 위해 대역 설정을 기본 상태로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-136">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="760f4-137">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-137">For example:</span></span>


- <span data-ttu-id="760f4-138">커피숍, 커피숍 및 공항에 있는 많은 핫스팟은 여전히 2.4GHz만 사용하며, 밴드가 5GHz로 설정된 경우 장치에 대한 액세스가 효과적으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-138">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="760f4-139">Miracast 무선 디스플레이 연결을 사용하려면 2.4GHz 채널을 통해 초기 핸드세이크를 완료해야 하기 때문에 디바이스는 5GHz에서만 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-139">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="760f4-140">기본적으로 Surface 디바이스는 사용 가능한 경우 5GHz에 연결하는 것을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-140">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="760f4-141">그러나 배터리가 부족한 상태로 전원을 유지하기 위해 Surface는 먼저 2.4GHz 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-141">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="760f4-142">환경에 맞게 필요한 경우 밴드 설정을 전환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-142">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="760f4-143">예를 들어 Wi-Fi 핫스팟이 여러 개 있는 고밀도 아파트 건물에 거주하는 사용자는 모두 2.4GHz를 통해 브로드캐스트하는 소비자 장치가 있는 동안에는 Surface 디바이스를 5GHz에서만 연결한 다음 필요한 경우 자동으로 되감아도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-143">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="760f4-144">Intel 어댑터를 사용하여 Surface 디바이스의 로밍 적극성 설정</span><span class="sxs-lookup"><span data-stu-id="760f4-144">Roaming aggressiveness settings on Surface devices with Intel adapters</span></span> 

<span data-ttu-id="760f4-145">사용자는 신호가 떨어질 때 장치에 새 액세스 지점을 검색하라는 메시지를 표시하는 신호 강도 임계값을 선택할 수 있습니다(로밍 적극성).</span><span class="sxs-lookup"><span data-stu-id="760f4-145">Users may wish to select a signal strength threshold that prompts the device to search for a new access point when the signal drops (roaming aggressiveness).</span></span> <span data-ttu-id="760f4-146">기본적으로 Intel 어댑터가 있는 Surface 장치는 신호 강도가 중간(신호 강도 72%) 이하로 떨어질 경우 새 액세스 지점으로 로밍을 시도합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="760f4-146">By default, Surface devices with Intel adapters attempt to roam to a new access point if the signal strength drops below **Medium** (72 percent signal strength).</span></span> <span data-ttu-id="760f4-147">또한 조직은 이 페이지의 앞부분에서 설명한 대로 로밍이 번거로워진 네트워크 환경을 용이하게 하기 위해 여러 네트워크 액세스 지점에서 용도에 따라 구축된 무선 프로토콜을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-147">Note also that organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming congested network environments, as explained earlier on this page.</span></span> 

<span data-ttu-id="760f4-148">중간보다 높은 로밍 적극성을 **높이면** 정체성이 높은 사무실이나 환경 환경의 연결이 향상될 수 있는 반면, 이러한 환경 외부로 스테이핑하면 연결이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-148">While increasing roaming aggressiveness above **Medium** may yield improved connectivity in highly congested office or residential environments, it can result in degraded connectivity when stepping outside of these environments.</span></span> 

<span data-ttu-id="760f4-149">회의 중에 음성 및 비디오 연결을 유지하면서 환경 사이트 검사 수행과 같은 특정 모바일 시나리오에서 연결 문제가 발생하는 경우를 하지 않는 한 로밍 적극성 설정을 기본 상태로 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-149">It’s recommended to leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="760f4-150">개선된 상태가 없는 경우 기본 보통 상태로 되버립니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-150">If you don’t notice any improvement, revert to the default Medium state.</span></span> <span data-ttu-id="760f4-151">로밍 적극성을 높이면 배터리 전원 소비도 가속화됩니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-151">Note that if you increase roaming aggressiveness, you also accelerate battery power consumption.</span></span> 

**<span data-ttu-id="760f4-152">Surface에서 로밍 적극성을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="760f4-152">To enable roaming aggressiveness on Surface:</span></span>**

1. <span data-ttu-id="760f4-153">장치 \*\*\*\* 관리자  >  **시작으로 이동**</span><span class="sxs-lookup"><span data-stu-id="760f4-153">Go to **Start** > **Device Manager**.</span></span>
2. <span data-ttu-id="760f4-154">네트워크 **어댑터에서** Intel Wi-Fi **6을** 선택한 다음 속성을 마우스 오른쪽 단추로 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="760f4-154">Under **Network adapters** select **Intel Wi-Fi 6** and then right click **Properties**.</span></span>
3. <span data-ttu-id="760f4-155">고급 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-155">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="760f4-156">로밍 **적극성을** 선택하고 드롭다운 메뉴에서 원하는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-156">Select **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 로밍 적극성 설정-Intel \*](images/wifi-roaming-int.png) <br>

### <span data-ttu-id="760f4-158">Surface Go 및 Surface Pro X의 로밍 적극성 설정</span><span class="sxs-lookup"><span data-stu-id="760f4-158">Roaming aggressiveness settings on Surface Go and Surface Pro X</span></span>

<span data-ttu-id="760f4-159">Surface Go를 사용하는 프런트 라인 작업자는 신호 강도가 떨어질 때 디바이스가 새 액세스 지점을 검색하라는 메시지를 표시하는 신호 강도 임계값을 선택할 수 있습니다(로밍 적극성).</span><span class="sxs-lookup"><span data-stu-id="760f4-159">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="760f4-160">기본적으로 Surface 장치는 신호 강도가 중간(신호 강도 50%) 미만으로 떨어지는 경우 새 액세스 지점으로 로밍을 시도합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="760f4-160">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="760f4-161">로밍 적극성을 높이면 배터리 전원 소비가 가속화됩니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-161">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="760f4-162">회의 중에 음성 및 비디오 연결을 유지하면서 환경 사이트 검사 수행과 같은 특정 모바일 시나리오에서 연결 문제가 발생하는 경우를 한 로밍 적극성을 기본 상태로 하세요.</span><span class="sxs-lookup"><span data-stu-id="760f4-162">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="760f4-163">개선된 상태가 없는 경우 기본 보통 상태로 **되버립니다.**</span><span class="sxs-lookup"><span data-stu-id="760f4-163">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="760f4-164">Surface Go에서 로밍 적극성을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="760f4-164">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="760f4-165">제어판 **>** 네트워크 및 인터넷 네트워크 및 공유  >  \*\*\*\*  >  **센터로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="760f4-165">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="760f4-166">**연결에서** **Wi-Fi를 선택한** 다음 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="760f4-166">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="760f4-167">**Microsoft Networks용 클라이언트를 선택한** 다음 **구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="760f4-167">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="760f4-168">고급 **로밍**적극성을 선택하고 드롭다운 메뉴에서 원하는  >  \*\*\*\* 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-168">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 로밍 적극성 설정-QualComm \*](images/wifi-roaming.png) <br>


## <span data-ttu-id="760f4-170">결론</span><span class="sxs-lookup"><span data-stu-id="760f4-170">Conclusion</span></span>

<span data-ttu-id="760f4-171">Surface 디바이스는 배터리 수명을 보존해야 하는 필요와 함께 최적의 무선 연결 균형을 위해 기본 설정으로 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-171">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="760f4-172">Surface 디바이스에 안정적인 연결을 설정하는 가장 효과적인 방법은 802.11r 및 802.11k를 지원하는 잘 디자인된 네트워크를 통해서입니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-172">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="760f4-173">사용자는 네트워크 어댑터 설정 또는 로밍 적극성을 조정할 수 있지만 특정 환경 요인에 대한 응답으로만 조정하고, 눈에 띄는 개선이 없는 경우 기본 상태로 되감아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="760f4-173">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>
