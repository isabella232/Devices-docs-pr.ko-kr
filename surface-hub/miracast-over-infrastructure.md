---
title: 기존 무선 네트워크 또는 LAN의 Miracast
description: Windows 10에서는 로컬 네트워크를 통해 Miracast 스트림을 보낼 수 있습니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d63b3de0f76cb70fe86fff246d82cbe166278461
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836976"
---
# <span data-ttu-id="f0f33-103">인프라를 통한 Miracast</span><span class="sxs-lookup"><span data-stu-id="f0f33-103">Miracast over infrastructure</span></span>

<span data-ttu-id="f0f33-104">Windows 10 버전 1703에서 Microsoft는 직접 무선 링크가 아니라 로컬 네트워크를 통해 Miracast 스트림을 보낼 수 있는 기능을 확장했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-104">In the Windows 10, version 1703, Microsoft has extended the ability to send a Miracast stream over a local network rather than over a direct wireless link.</span></span> <span data-ttu-id="f0f33-105">이 기능은 [인프라 연결 설정 프로토콜을 통한 Miracast(MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-105">This functionality is based on the [Miracast over Infrastructure Connection Establishment Protocol (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx).</span></span>

<span data-ttu-id="f0f33-106">인프라를 통한 Miracast는 다양한 혜택을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-106">Miracast over Infrastructure offers a number of benefits:</span></span>

- <span data-ttu-id="f0f33-107">Windows는 비디오 스트림을 전송할 때 자동으로 이 경로가 적용 가능한지 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-107">Windows automatically detects when sending the video stream over this path is applicable.</span></span>
- <span data-ttu-id="f0f33-108">Windows는 연결이 이더넷 또는 보안 Wi-Fi 네트워크를 통한 경우에만 이 경로를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-108">Windows will only choose this route if the connection is over Ethernet or a secure Wi-Fi network.</span></span>
- <span data-ttu-id="f0f33-109">사용자가 Miracast 수신기에 연결하는 방법을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-109">Users do not have to change how they connect to a Miracast receiver.</span></span> <span data-ttu-id="f0f33-110">표준 Miracast 연결과 동일한 UX를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-110">They use the same UX as for standard Miracast connections.</span></span>
- <span data-ttu-id="f0f33-111">현재 무선 드라이버 또는 PC의 하드웨어에 변경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-111">No changes to current wireless drivers or PC hardware are required.</span></span>
- <span data-ttu-id="f0f33-112">Wi-Fi Direct를 통한 Miracast에 최적화되지 않은 오래된 무선 하드웨어에도 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-112">It works well with older wireless hardware that is not optimized for Miracast over Wi-Fi Direct.</span></span>
- <span data-ttu-id="f0f33-113">기존 연결을 활용하여 연결 시간을 줄이며 매우 안정적인 스트림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-113">It leverages an existing connection which both reduces the time to connect and provides a very stable stream.</span></span>


## <span data-ttu-id="f0f33-114">작동 방식</span><span class="sxs-lookup"><span data-stu-id="f0f33-114">How it works</span></span>

<span data-ttu-id="f0f33-115">사용자가 이전에 Wi-fi 어댑터를 통해 Miracast 수신기에 연결 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-115">Users attempt to connect to a Miracast receiver through their Wi-Fi adapter as they did previously.</span></span> <span data-ttu-id="f0f33-116">Miracast 수신기 목록이 채워지면 Windows 10에서 해당 수신기가 인프라에 대한 연결을 지원할 수 있는지 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-116">When the list of Miracast receivers is populated, Windows 10 will identify that the receiver is capable of supporting a connection over the infrastructure.</span></span> <span data-ttu-id="f0f33-117">사용자가 Miracast 수신기를 선택하면 Windows 10은 표준 DNS 및 멀티캐스트 DNS(mDNS)를 통해 장치의 호스트 이름을 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-117">When the user selects a Miracast receiver, Windows 10 will attempt to resolve the device's hostname via standard DNS, as well as via multicast DNS (mDNS).</span></span> <span data-ttu-id="f0f33-118">DNS 방법 중 하나를 통해 이름을 분해할 수 없는 경우 Windows 10은 표준 Wi-Fi Direct 연결을 사용하여 Miracast 세션을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-118">If the name is not resolvable via either DNS method, Windows 10 will fall back to establishing the Miracast session using the standard Wi-Fi direct connection.</span></span>

> [!NOTE]
> <span data-ttu-id="f0f33-119">연결 협상 순서에 대 한 자세한 내용은 [인프라 연결 설정 프로토콜 (MS-마우스)에서 Miracast](https://msdn.microsoft.com/library/mt796768.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0f33-119">For more information on the connection negotiation sequence, see [Miracast over Infrastructure Connection Establishment Protocol (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)</span></span>




## <span data-ttu-id="f0f33-120">인프라에 대해 Miracast 사용</span><span class="sxs-lookup"><span data-stu-id="f0f33-120">Enabling Miracast over Infrastructure</span></span> 

<span data-ttu-id="f0f33-121">Windows 10 버전 1703로 업데이트된 Surface Hub 또는 다른 Windows 10 디바이스가 있으면 자동으로 이 새로운 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-121">If you have a Surface Hub or other Windows 10 device that has been updated to Windows 10, version 1703, then you automatically have this new feature.</span></span> <span data-ttu-id="f0f33-122">귀하의 환경에서 이를 활용하려면 배포 시 다음에 해당하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-122">To take advantage of it in your environment, you need to ensure the following is true within your deployment:</span></span>

- <span data-ttu-id="f0f33-123">Surface Hub 또는 디바이스(Windows PC 또는 휴대폰)에서 Windows 10 버전 1703을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-123">The Surface Hub or device (Windows PC or phone) needs to be running Windows 10, version 1703.</span></span>
- <span data-ttu-id="f0f33-124">TCP 포트를 엽니다. **7250**.</span><span class="sxs-lookup"><span data-stu-id="f0f33-124">Open TCP port: **7250**.</span></span>
- <span data-ttu-id="f0f33-125">Surface Hub 또는 Windows PC가 인프라를 통한 Miracast *수신기* 역할을 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-125">A Surface Hub or Windows PC can act as a Miracast over Infrastructure *receiver*.</span></span> <span data-ttu-id="f0f33-126">Windows PC 또는 휴대폰이 인프라를 통한 Miracast *소스* 역할을 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-126">A Windows PC or phone can act as a Miracast over Infrastructure *source*.</span></span>
    - <span data-ttu-id="f0f33-127">Miracast 수신기로서 Surface Hub 또는 장치는 이더넷 또는 보안 Wi-Fi 연결을 통해(예 WPA2-PSK 또는 WPA2-Enterprise 보안 사용) 회사 네트워크에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-127">As a Miracast receiver, the Surface Hub or device must be connected to your enterprise network via either Ethernet or a secure Wi-Fi connection (e.g. using either WPA2-PSK or WPA2-Enterprise security).</span></span> <span data-ttu-id="f0f33-128">Surface Hub 또는 장치가 열려 있는 Wi-fi 연결에 연결 된 경우에는 인프라를 통해 Miracast가 자체적으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-128">If the Surface Hub or device is connected to an open Wi-Fi connection, Miracast over Infrastructure will disable itself.</span></span>
    - <span data-ttu-id="f0f33-129">Miracast 소스로서 Windows PC 또는 휴대폰은 이더넷 또는 보안 Wi-Fi 연결을 통해 동일한 엔터프라이즈 네트워크에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-129">As a Miracast source, the Windows PC or phone must be connected to the same enterprise network via Ethernet or a secure Wi-Fi connection.</span></span>
- <span data-ttu-id="f0f33-130">DNS 서버를 통해 Surface Hub 또는 장치의 DNS 호스트 이름 (장치 이름)을 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-130">The DNS Hostname (device name) of the Surface Hub or device needs to be resolvable via your DNS servers.</span></span> <span data-ttu-id="f0f33-131">Surface Hub가 동적 DNS를 통해 자동으로 등록하도록 하거나 수동으로 Surface Hub의 호스트 이름에 대한 A 또는 AAAA 레코드를 만들어 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-131">You can achieve this by either allowing your Surface Hub to register automatically via Dynamic DNS, or by manually creating an A or AAAA record for the Surface Hub's hostname.</span></span> 
- <span data-ttu-id="f0f33-132">Windows 10 PC는 이더넷 또는 보안 Wi-Fi 연결을 통해 동일한 엔터프라이즈 네트워크에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-132">Windows 10 PCs must be connected to the same enterprise network via Ethernet or a secure Wi-Fi connection.</span></span> 
-   <span data-ttu-id="f0f33-133">Windows 10 Pc에서는 시스템 설정에서 **이 PC로의 투영** 기능을 사용 하도록 설정 해야 하며 wi-fi 어댑터를 통해서만 발생 하는 검색 요청에 응답 하려면 장치에 wi-fi 인터페이스가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-133">On Windows 10 PCs, the **Projecting to this PC** feature must be enabled in System Settings, and the device must have a Wi-Fi interface enabled in order to respond to discovery requests that only occur through the Wi-Fi adapter.</span></span>


<span data-ttu-id="f0f33-134">인프라를 통한 Miracast는 표준 Miracast를 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-134">It is important to note that Miracast over Infrastructure is not a replacement for standard Miracast.</span></span> <span data-ttu-id="f0f33-135">대신, 이 기능은 보완적이며 엔터프라이즈 네트워크의 일부인 사용자에게 혜택을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-135">Instead, the functionality is complementary, and provides an advantage to users who are part of the enterprise network.</span></span> <span data-ttu-id="f0f33-136">특정 위치의 게스트이며 엔터프라이즈 네트워크에 액세스할 수 없 사용자는 Wi-Fi Direct 연결 방법을 사용하여 계속 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-136">Users who are guests to a particular location and don’t have access to the enterprise network will continue to connect using the Wi-Fi Direct connection method.</span></span>

<span data-ttu-id="f0f33-137">[SurfaceHub 구성 서비스 공급자(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp)의 **InBoxApps/WirelessProjection/PinRequired** 설정은 인프라를 통한 Miracast에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-137">The **InBoxApps/WirelessProjection/PinRequired** setting in the [SurfaceHub configuration service provider (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) is not required for Miracast over Infrastructure.</span></span> <span data-ttu-id="f0f33-138">인프라를 통한 Miracast는 두 디바이스가 같은 엔터프라이즈 네트워크에 연결된 경우에만 작동하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-138">This is because Miracast over Infrastructure only works when both devices are connected to the same enterprise network.</span></span> <span data-ttu-id="f0f33-139">이렇게 하면 이전에 Miracast에서 누락된 보안 제한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-139">This removes the security restriction that was previously missing from Miracast.</span></span> <span data-ttu-id="f0f33-140">인프라 연결이 작동하지 않는 경우 Miracast가 일반 Miracast로 돌아가므로 이 설정을 계속 사용하는 것이 좋습니다(이전에 이를 사용한 경우).</span><span class="sxs-lookup"><span data-stu-id="f0f33-140">We recommend that you continue using this setting (if you used it previously) as Miracast will fall back to regular Miracast if the infrastructure connection does not work.</span></span> 

## <span data-ttu-id="f0f33-141">FAQ</span><span class="sxs-lookup"><span data-stu-id="f0f33-141">FAQ</span></span>
**<span data-ttu-id="f0f33-142">인프라 상에 서 Miracast를 사용 하기 위해 Wi-fi가 필요 하지 않은 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f0f33-142">Why do I still need Wi-Fi to use Miracast over infrastructure?</span></span>**<br>
<span data-ttu-id="f0f33-143">Miracast 수신기를 식별 하는 검색 요청은 Wi-fi 어댑터를 통해서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-143">Discovery requests to identify Miracast receivers can only occur through the Wi-Fi adapter.</span></span> <span data-ttu-id="f0f33-144">수신기를 확인 한 후에는 Windows 10에서 네트워크 연결을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f33-144">Once the receivers have been identified, Windows 10 can then attempt the connection to the network.</span></span>
