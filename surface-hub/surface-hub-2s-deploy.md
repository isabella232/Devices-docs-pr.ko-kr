---
title: Surface Hub 2S용 프로비전 패키지 만들기
description: 이 페이지에서는 프로비저닝 패키지 및 기타 Surface Hub 사용하여 2S를 배포하는 방법을 설명합니다.
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576868"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="37a31-104">Surface Hub 2S용 프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="37a31-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="37a31-105">WCD(구성 Windows)를 사용하여 프로비저닝 패키지를 만들어 2S 배포를 자동화할 Surface Hub 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="37a31-106">프로비저닝 패키지를 사용하여 인증서를 추가하고, proxies를 구성하고, 장치 관리자 및 장치 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="37a31-107">구성 파일과 함께 프로비저닝 패키지를 사용하여 단일 USB 썸 드라이브를 사용하여 여러 Surface Hub를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="37a31-108">Windows 구성 디자이너 설치</span><span class="sxs-lookup"><span data-stu-id="37a31-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="37a31-109">WINDOWS ADK(Assessment and Deployment Kit)에서 Windows 구성 디자이너를 Windows 10.</span><span class="sxs-lookup"><span data-stu-id="37a31-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="37a31-110">[1703 버전 Windows 10 ADK를 다운로드하여 설치합니다.](https://go.microsoft.com/fwlink/p/?LinkId=845542)</span><span class="sxs-lookup"><span data-stu-id="37a31-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="37a31-111">자세한 내용은 [Windows ADK 다운로드 및 설치](https://docs.microsoft.com/windows-hardware/get-started/adk-install)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37a31-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="37a31-112">인증서 추가</span><span class="sxs-lookup"><span data-stu-id="37a31-112">Add certificates</span></span>

<span data-ttu-id="37a31-113">인증 기관 인증서를 2S로 Surface Hub 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="37a31-114">인증서를 Surface Hub 2S에 추가하려면 .cer 형식의 X.509로 각 인증서의 복사본이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="37a31-115">.crt, .pfx 또는 기타 컨테이너 형식은 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="37a31-116">인증서를 구성 디자이너의 Windows 계층 구조로 정렬해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![인증서 추가](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="37a31-118">OOBE 중에 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="37a31-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="37a31-119">구성 Windows 구성 디자이너에서 프록시 설정 구성 탭으로 이동하여 아래와 같이 적절한 설정을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![프록시 설정 구성](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="37a31-121">프록시 설정을 구성할 때 \*\*\*\* 설치 스크립트 또는 프록시 서버를 사용하려는 경우 자동으로 설정 검색을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="37a31-122">설치 스크립트나 프록시 \*\* 서버는 둘 다 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="37a31-123">계열사 Surface Hub 2S Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="37a31-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="37a31-124">프로비저닝 패키지를 사용하여 Surface Hub 2S와 제휴할 수 Azure Active Directory: Azure Active Directory 전역 관리자로서 대량 토큰을 사용하여 많은 Windows 디바이스를 Azure Active Directory Intune에 가입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="37a31-125">대량 토큰을 만들 수 있도록 이름을 지정하고 만료 날짜(최대 30일)를 구성하고 관리자 자격 증명을 사용하여 아래 표시된 토큰을 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![장치 관리자 설정 예제 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![장치 관리자 설정 예제 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![장치 관리자 설정 예제 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="37a31-129">여러 장치 프로비전(.csv 파일)</span><span class="sxs-lookup"><span data-stu-id="37a31-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="37a31-130">프로비저닝 패키지 외에도 Surface Hub 구성 파일을 사용하여 디바이스를 보다 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="37a31-131">Surface Hub 구성 파일에는 무선 투영을 위한 장치 계정 및 이름 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="37a31-132">첫 실행 중에는 구성 파일에서 장치 계정과 이름을 선택할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="37a31-133">구성 파일을 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="37a31-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="37a31-134">Microsoft Excel 또는 다른 CSV 편집기를 사용하여 다음의 CSV 파일을 **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="37a31-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="37a31-135">디바이스 계정 및 이름 목록을 다음 형식으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="37a31-136">PPKG 파일을 복사한 USB 썸 드라이브의 루트에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="37a31-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![구성 파일 예제](images/sh2-config-file.png)
