---
title: Surface 장치에 대한 Wi-Fi 연결 최적화
description: 이 항목에서는 Surface devices가 혼잡 네트워크 환경 및 모바일 시나리오에서 연결 된 상태를 유지 하도록 권장 되는 Wi-Fi 설정에 대해 설명 합니다.
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
ms.date: 10/26/2020
ms.openlocfilehash: d211ceea20b89824d45e433cf9670abe137130a0
ms.sourcegitcommit: 07ac65bf70c8c6efcda28eecc3013983fc386e0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136150"
---
# <span data-ttu-id="9cba0-103">Surface 장치에 대한 Wi-Fi 연결 최적화</span><span class="sxs-lookup"><span data-stu-id="9cba0-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="9cba0-104">종일 배터리 수명과 연결 된 상태를 유지 하기 위해 Surface 디바이스는 성능 및 전원 보존을 조정 하는 무선 연결 설정을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="9cba0-105">가장 까다로운 이동성 시나리오 외에도 사용자는 기본 네트워크 어댑터나 관련 설정을 수정 하지 않고 충분 한 무선 연결을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> <span data-ttu-id="9cba0-106">이 페이지에서는 Surface Pro 7, Surface Pro X, Surface 랩톱 3, surface Book 3, surface Go 2 및 Surface 랩톱 이동을 비롯 한 모바일 시나리오에서 주요 무선 연결 고려 사항을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-106">This page highlights key wireless connectivity considerations in mobile scenarios using the latest Surface devices including Surface Pro 7, Surface Pro X, Surface Laptop 3, Surface Book 3,  Surface Go 2, and Surface Laptop Go.</span></span>  

## <span data-ttu-id="9cba0-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9cba0-107">Prerequisites</span></span>

<span data-ttu-id="9cba0-108">이 문서에서는 선두적인 장비 공급 업체의 모범 사례 권장 사항에 따라 802.11 n (Wi-fi 4) 이상을 지 원하는 무선 네트워크를 배포 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-108">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="9cba0-109">최적의 로밍 기능을 위한 액세스 지점 구성</span><span class="sxs-lookup"><span data-stu-id="9cba0-109">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="9cba0-110">일반적으로 여러 다른 유형의 클라이언트 장치에서 액세스 하는 무선 네트워크를 관리 하는 경우 [802.11 k, 802.11 v 및 802.11 r을 사용 하 여 빠른 로밍](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)에서 설명한 대로 WLAN의 ap (액세스 지점)에 특정 프로토콜을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-110">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="9cba0-111">Surface 디바이스는 다음 무선 프로토콜을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-111">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="9cba0-112">802.11 r.</span><span class="sxs-lookup"><span data-stu-id="9cba0-112">802.11r.</span></span>** <span data-ttu-id="9cba0-113">"**빠른 BSS 전환"** 장치에서 다른 AP에 액세스 하는 데 필요한 프레임 수를 줄임으로써 새 무선 액세스 지점에 대 한 연결 속도를 가속화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-113">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span> <span data-ttu-id="9cba0-114">2019 이후 출시 된 새로운 Surface 디바이스에서는 최종 사용자가 자신의 장치에서 로밍 강도와 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-114">In the new generation of Surface devices released since 2019, end users may gain access to roaming aggressiveness settings on their device.</span></span> <span data-ttu-id="9cba0-115">기본 설정을 수정 하는 것은 권장 되지 않지만 사용자는이 기능을 인식 하 고 특정 설정이 연결 된 상태를 유지 하는 데 어떤 영향을 미칠 수 있는지 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-115">Although modifying default settings is not recommended, users should be aware of this capability and understand how specific settings can impact their ability to remain connected.</span></span>
- **<span data-ttu-id="9cba0-116">802.11 k.</span><span class="sxs-lookup"><span data-stu-id="9cba0-116">802.11k.</span></span>** <span data-ttu-id="9cba0-117">**"인접 라우터 보고서"** 는 주변 액세스 포인트에서 현재 조건에 대 한 정보를 장치에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-117">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="9cba0-118">이는 Surface 장치에서 AP 사용률과 같이 신호 강도가 다른 조건을 사용 하 여 최적의 AP를 선택 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-118">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="9cba0-119">또한 특정 Surface 디바이스는 802.11 v "BSS 전환 관리 프레임"을 사용 하 여 가까운 후보 Ap에 대 한 정보를 제공할 때 802.11 k와 거의 비슷한 기능을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-119">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="9cba0-120">여기에는 서피스 이동, Surface Pro 7, Surface Pro X 및 Surface 노트북 3이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-120">These include Surface Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="9cba0-121">사용자 설정 관리</span><span class="sxs-lookup"><span data-stu-id="9cba0-121">Managing user settings</span></span>

<span data-ttu-id="9cba0-122">모든 액세스 포인트에서 802.11 r 및 802.11 k를 지 원하는 잘 디자인 된 네트워크를 통해 최적의 로밍 기능을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-122">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="9cba0-123">사용자에 게 최상의 무선 환경을 제공 하도록 네트워크가 적절 하 게 구성 되었는지 확인 하는 것은 개별 장치에서 사용자 설정을 관리 하는 것과 대 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-123">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> 

### <span data-ttu-id="9cba0-124">권장 되는 사용자 설정 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="9cba0-124">Recommended user settings and best practices</span></span>

<span data-ttu-id="9cba0-125">특정 상황에서 Surface 디바이스에 기본 제공 되는 고급 네트워크 어댑터 설정을 수정 하는 것이 더 안정적인 연결을 용이 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-125">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="9cba0-126">액세스 지점의 문제, 네트워킹 디자인 결함 또는 환경 사이트 문제 때문에 무선 리소스에 연결 되지 않는 것이 더 빈번 하다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cba0-126">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="9cba0-127">Surface Pro 또는 Surface Go를 보유 하는 방법 또한 신호 강도에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-127">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="9cba0-128">대역폭이 손실 되는 경우 디스플레이의 위쪽을 보유 하 고 있지 않은 경우 Wi-Fi 라디오 수신기가 위치 해 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-128">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="9cba0-129">디스플레이의 위쪽을 누르고 있으면 무선 신호가 차단 되지 않지만 장치 드라이버를 트리거하여 연결을 줄일 수 있는 변경 사항을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-129">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="9cba0-130">이중 대역폭 기능에 대 한 기본 자동 설정 유지</span><span class="sxs-lookup"><span data-stu-id="9cba0-130">Keep default Auto setting for dual bandwidth capability</span></span>

<span data-ttu-id="9cba0-131">대부분의 Surface 장치에서 클라이언트 네트워크 어댑터 설정을 5Ghz (GHz) 이상의 무선 Ap에만 연결 하도록 구성 하거나, 2.4 GHz 이상에 연결 하거나, 운영 체제에서 가장 적합 한 옵션 (기본 자동 설정)을 선택 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-131">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="9cba0-132">네트워크 어댑터 설정에 액세스 하려면 다음으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-132">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="9cba0-133">**시작**  >  **제어판**  >  **네트워크 및 공유 센터**  >  **Wi-Fi 어댑터**  >  **속성**  >  **구성**  >  **고급**.</span><span class="sxs-lookup"><span data-stu-id="9cba0-133">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi 밴드 설정 \*](images/wifi-band.png) <br>

<span data-ttu-id="9cba0-135">2.4 GHz에는 5 GHz 이상에 대 한 몇 가지 장점이 있습니다 .이는 벽 이나 다른 솔리드 개체를 통과 하 여 더 penetrates 더욱 쉽게 확장할 수 있다는 것을 기억 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cba0-135">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="9cba0-136">5 GHz에 연결을 유지 하는 명확한 사용 사례가 있는 경우가 아니면 기본 상태로 밴드 설정을 사용 하 여 부정적인 영향을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-136">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="9cba0-137">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-137">For example:</span></span>


- <span data-ttu-id="9cba0-138">호텔, 커피숍, 공항에 있는 많은 핫스팟은 여전히 2.4 GHz만 사용 하 고 대역이 5ghz로 설정 된 경우 장치에 대 한 액세스를 효과적으로 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-138">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="9cba0-139">Miracast 무선 디스플레이 연결에는 2.4 GHz 채널을 통해 초기 핸드셰이크가 완료 되므로 디바이스는 5ghz 에서만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-139">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="9cba0-140">기본적으로 Surface 디바이스는 사용 가능한 경우 5ghz에 연결 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-140">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="9cba0-141">그러나 배터리 부족 상태에서 전원을 유지 하기 위해 Surface에서는 먼저 2.4 GHz 연결을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-141">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="9cba0-142">또한 필요에 따라 환경에 맞게 밴드 설정을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-142">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="9cba0-143">예를 들어, 여러 Wi-Fi 핫스팟이 있는 고밀도 아파트 건물에 살고 있는 사용자 (2.4 GHz를 통한 소비자 디바이스의 현재 브로드캐스트)는 Surface device를 5ghz 에서만 연결 하도록 설정한 다음 필요할 때 자동으로 되돌리기 하 여 이익을 amid 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-143">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="9cba0-144">Intel 어댑터를 사용 하는 Surface 장치에 대 한 로밍 강도 설정</span><span class="sxs-lookup"><span data-stu-id="9cba0-144">Roaming aggressiveness settings on Surface devices with Intel adapters</span></span> 

<span data-ttu-id="9cba0-145">사용자는 신호가 떨어질 때 새 액세스 지점을 검색 하도록 장치에 요청 하는 신호 강도 임계값 (로밍 강도)을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-145">Users may wish to select a signal strength threshold that prompts the device to search for a new access point when the signal drops (roaming aggressiveness).</span></span> <span data-ttu-id="9cba0-146">기본적으로 Intel 어댑터를 사용 하는 Surface 장치는 신호 강도가 **중간** (72% 신호 강도) 미만이 되 면 새 액세스 포인트로 로밍 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-146">By default, Surface devices with Intel adapters attempt to roam to a new access point if the signal strength drops below **Medium** (72 percent signal strength).</span></span> <span data-ttu-id="9cba0-147">또한 조직에서는이 페이지의 앞부분에서 설명한 대로 여러 네트워크 액세스 지점에서 목적으로 빌드된 무선 프로토콜을 구현 하 여 혼잡 한 네트워크 환경을 쉽게 로밍 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-147">Note also that organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming congested network environments, as explained earlier on this page.</span></span> 

<span data-ttu-id="9cba0-148">로밍 강도와 **Medium (보통** 이상)을 늘리면 매우 혼잡 한 사무실 또는 주거 환경에서 향상 된 연결을 만들 수 있지만, 이러한 환경에서 외부로 스테핑을 할 때 연결이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-148">While increasing roaming aggressiveness above **Medium** may yield improved connectivity in highly congested office or residential environments, it can result in degraded connectivity when stepping outside of these environments.</span></span> 

<span data-ttu-id="9cba0-149">컨퍼런스 모임 중에도 음성 및 비디오 연결을 유지 하면서 환경 사이트 검사를 수행 하는 것과 같은 특정 모바일 시나리오에서 연결 문제가 발생 하지 않는 한 기본 상태에서 로밍 강도와 설정을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-149">It’s recommended to leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="9cba0-150">개선 사항이 없는 경우 기본 보통 상태로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-150">If you don’t notice any improvement, revert to the default Medium state.</span></span> <span data-ttu-id="9cba0-151">로밍 강도를 늘리면 배터리 전원 소모도 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-151">Note that if you increase roaming aggressiveness, you also accelerate battery power consumption.</span></span> 

**<span data-ttu-id="9cba0-152">Surface에서 로밍 강도를 사용 하려면:</span><span class="sxs-lookup"><span data-stu-id="9cba0-152">To enable roaming aggressiveness on Surface:</span></span>**

1. <span data-ttu-id="9cba0-153">**Start**  >  **장치 관리자**시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-153">Go to **Start** > **Device Manager**.</span></span>
2. <span data-ttu-id="9cba0-154">**네트워크 어댑터** 에서 **Intel Wi-Fi 6** 을 선택한 다음 **속성**을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-154">Under **Network adapters** select **Intel Wi-Fi 6** and then right click **Properties**.</span></span>
3. <span data-ttu-id="9cba0-155">**고급** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-155">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="9cba0-156">**로밍 강도** 를 선택 하 고 드롭다운 메뉴에서 원하는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-156">Select **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 로밍 강도 설정-Intel \*](images/wifi-roaming-int.png) <br>

### <span data-ttu-id="9cba0-158">서피스 이동 및 Surface Pro X의 로밍 강도 설정</span><span class="sxs-lookup"><span data-stu-id="9cba0-158">Roaming aggressiveness settings on Surface Go and Surface Pro X</span></span>

<span data-ttu-id="9cba0-159">Surface Go를 사용 하는 프런트 엔드 작업자는 신호 강도가 떨어질 때 새 액세스 지점을 검색 하도록 장치에 요청 하는 신호 강도 임계값을 선택할 수 있습니다 (로밍 강도).</span><span class="sxs-lookup"><span data-stu-id="9cba0-159">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="9cba0-160">기본적으로 Surface 디바이스는 신호 강도가 **중간** (50% 신호 강도) 미만으로 떨어지면 새 액세스 포인트로 로밍 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-160">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="9cba0-161">로밍 강도를 늘릴 때마다 배터리 전원 소비량을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-161">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="9cba0-162">컨퍼런스 모임 중에도 음성 및 비디오 연결을 유지 하면서 환경 사이트 검사를 수행 하는 것과 같은 특정 모바일 시나리오에서 연결 문제가 발생 하지 않는 한 기본 상태에서 로밍 강도와 설정을 그대로 유지 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cba0-162">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="9cba0-163">개선 사항이 없는 경우 기본 **보통** 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-163">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="9cba0-164">Surface Go에서 로밍 강도를 사용 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-164">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="9cba0-165">제어판의 **Start > Control Panel**  >  **네트워크 및 인터넷**  >  **네트워크 및 공유 센터** 시작 > 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-165">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="9cba0-166">**연결** 에서 **wi-fi** 를 선택한 다음 속성을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="9cba0-166">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="9cba0-167">**Microsoft 네트워크용 클라이언트** 를 선택한 다음 **구성을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-167">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="9cba0-168">**고급**  >  **로밍 강도** 를 선택 하 고 드롭다운 메뉴에서 원하는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-168">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 로밍 강도 설정-QualComm \*](images/wifi-roaming.png) <br>


## <span data-ttu-id="9cba0-170">결론</span><span class="sxs-lookup"><span data-stu-id="9cba0-170">Conclusion</span></span>

<span data-ttu-id="9cba0-171">Surface 디바이스는 배터리 수명 유지와 함께 최적의 무선 연결을 조정 하는 기본 설정으로 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-171">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="9cba0-172">Surface 장치에 대 한 안정적인 연결을 사용 하도록 설정 하는 가장 효과적인 방법은 802.11 r 및 802.11 k를 지 원하는 잘 디자인 된 네트워크를 통하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-172">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="9cba0-173">사용자는 네트워크 어댑터 설정 또는 로밍 강도를 조정할 수 있지만, 눈에 띄는 개선 사항이 없다면 특정 환경 요인에 대 한 응답으로이를 수행 하 고 기본 상태로 되돌려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cba0-173">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>
