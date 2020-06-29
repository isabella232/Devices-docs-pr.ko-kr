---
title: Surface Pro X 앱 호환성
description: 이 문서에서는 Surface Pro X ARM 기반 Pc에 대 한 소개 앱 호환성 정보를 제공 합니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835567"
---
# <span data-ttu-id="a70ba-103">Surface Pro X 앱 호환성</span><span class="sxs-lookup"><span data-stu-id="a70ba-103">Surface Pro X app compatibility</span></span>

<span data-ttu-id="a70ba-104">Surface Pro X와 같은 ARM 기반 Windows 10 Pc에서는 응용 프로그램이 다르게 실행 됩니다. 제한 사항에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-104">Applications run differently on ARM-based Windows 10 PCs such as Surface Pro X. Limitations include the following:</span></span>

- <span data-ttu-id="a70ba-105">**하드웨어, 게임 및 앱에 대 한 드라이버는 Windows 10 ARM 기반 PC 용으로 디자인 된 경우에만 작동**합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-105">**Drivers for hardware, games and apps will only work if they're designed for a Windows 10 ARM-based PC**.</span></span> <span data-ttu-id="a70ba-106">자세한 내용은 하드웨어 제조업체나 드라이버를 개발한 조직을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a70ba-106">For more info, check with the hardware manufacturer or the organization that developed the driver.</span></span> <span data-ttu-id="a70ba-107">드라이버는 하드웨어 장치와 통신 하는 소프트웨어 프로그램으로, 일반적으로 바이러스 백신 및 맬웨어 방지 소프트웨어, 인쇄, PDF 소프트웨어, 보조 기술, CD 및 DVD 유틸리티, 가상화 소프트웨어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-107">Drivers are software programs that communicate with hardware devices—they're commonly used for antivirus and antimalware software, printing or PDF software, assistive technologies, CD and DVD utilities, and virtualization software.</span></span> <span data-ttu-id="a70ba-108">드라이버를 사용할 수 없는 경우에는이를 사용 하는 앱 또는 하드웨어가 작동 하지 않습니다 (최소한 완전히 완료 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="a70ba-108">If a driver doesn’t work, the app or hardware that relies on it won’t work either (at least not fully).</span></span> <span data-ttu-id="a70ba-109">주변 기기 및 장치는 해당 드라이버를 Windows 10에 기본으로 제공 하거나 하드웨어 개발자가 장치에 대 한 ARM64 드라이버를 해제 한 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-109">Peripherals and devices only work if the drivers they depend on are built into Windows 10, or if the hardware developer has released ARM64 drivers for the device.</span></span>
- <span data-ttu-id="a70ba-110">**64 비트 (x64) 앱이 작동 하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="a70ba-110">**64-bit (x64) apps won’t work**.</span></span> <span data-ttu-id="a70ba-111">64 비트 (ARM64) 앱, 32 비트 (ARM32) 앱 또는 32 비트 (x86) 앱이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-111">You'll need 64-bit (ARM64) apps, 32-bit (ARM32) apps, or 32-bit (x86) apps.</span></span> <span data-ttu-id="a70ba-112">일반적으로 32 비트 (x86) 버전의 앱을 찾을 수 있지만 일부 앱 개발자는 64 비트 (x64) 앱만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-112">You can usually find 32-bit (x86) versions of apps, but some app developers only offer 64-bit (x64) apps.</span></span>
- <span data-ttu-id="a70ba-113">**특정 게임이 작동 하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="a70ba-113">**Certain games won’t work**.</span></span> <span data-ttu-id="a70ba-114">게임 및 앱은 1.1 보다 큰 OpenGL 버전을 사용 하거나 Windows 10 ARM 기반 Pc에 대해 만들어지지 않은 "치트" 드라이버에 의존 하는 경우에는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-114">Games and apps won't work if they use a version of OpenGL greater than 1.1, or if they rely on "anti-cheat" drivers that haven't been made for Windows 10 ARM-based PCs.</span></span> <span data-ttu-id="a70ba-115">게임 게시자와 상의 하 여 게임이 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-115">Check with your game publisher to see if a game will work.</span></span>
- <span data-ttu-id="a70ba-116">**Windows 환경을 사용자 지정 하는 앱에 문제가 있을 수 있습니다**.</span><span class="sxs-lookup"><span data-stu-id="a70ba-116">**Apps that customize the Windows experience might have problems**.</span></span> <span data-ttu-id="a70ba-117">여기에는 Ime (입력기), 보조 기술, 클라우드 저장소 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-117">This includes some input method editors (IMEs), assistive technologies, and cloud storage apps.</span></span> <span data-ttu-id="a70ba-118">앱을 개발 하는 조직은 Windows 10 ARM 기반 PC에서 앱이 작동 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-118">The organization that develops the app determines whether their app will work on a Windows 10 ARM-based PC.</span></span>
- <span data-ttu-id="a70ba-119">**일부 타사 바이러스 백신 소프트웨어를 설치할 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="a70ba-119">**Some third-party antivirus software can’t be installed**.</span></span> <span data-ttu-id="a70ba-120">Windows 10 ARM 기반 PC에 일부 타사 바이러스 백신 소프트웨어를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-120">You won't be able to install some third-party antivirus software on a Windows 10 ARM-based PC.</span></span> <span data-ttu-id="a70ba-121">그러나 Windows 보안은 Windows 10 장치의 지원 되는 수명에 대해 안전을 유지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-121">However, Windows Security will help keep you safe for the supported lifetime of your Windows 10 device.</span></span>
- <span data-ttu-id="a70ba-122">**Windows 팩스 및 스캔을 사용할 수**없습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-122">**Windows Fax and Scan isn’t available**.</span></span> <span data-ttu-id="a70ba-123">Windows 10 ARM 기반 PC에서는이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a70ba-123">This feature isn’t available on a Windows 10 ARM-based PC.</span></span>

<span data-ttu-id="a70ba-124">앱 호환성에 대 한 자세한 내용은 [Windows 10 ARM 기반 PC FAQ](https://support.microsoft.com/en-us/help/4521606) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a70ba-124">For more information about app compatibility, refer to [Windows 10 ARM-based PCs FAQ](https://support.microsoft.com/en-us/help/4521606)</span></span>
