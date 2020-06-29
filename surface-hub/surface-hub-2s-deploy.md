---
title: Surface Hub 2S용 프로비전 패키지 만들기
description: 이 페이지에서는 프로비저닝 패키지 및 기타 도구를 사용 하 여 Surface Hub 2S를 배포 하는 방법을 설명 합니다.
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836939"
---
# <span data-ttu-id="bd79a-104">Surface Hub 2S용 프로비전 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="bd79a-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="bd79a-105">Windows 구성 디자이너 (WCD)를 사용 하 여 Surface Hub 2S 배포 프로세스를 자동화 하는 프로비저닝 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="bd79a-106">배포 패키지를 사용 하 여 인증서를 추가 하 고 프록시를 구성 하 고 디바이스 관리자 및 장치 계정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="bd79a-107">구성 파일과 함께 프로비저닝 패키지를 사용 하 여 단일 USB 엄지 드라이브로 여러 Surface Hub를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="bd79a-108">Windows 구성 디자이너 설치</span><span class="sxs-lookup"><span data-stu-id="bd79a-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="bd79a-109">Windows 10 용 Windows ADK (평가 및 배포 키트)에서 Windows 구성 디자이너를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="bd79a-110">[Windows 10 버전 1703 용 ADK](https://go.microsoft.com/fwlink/p/?LinkId=845542)를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="bd79a-111">자세한 내용은 [WINDOWS ADK 다운로드 및 설치](https://docs.microsoft.com/windows-hardware/get-started/adk-install)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd79a-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="bd79a-112">인증서 추가</span><span class="sxs-lookup"><span data-stu-id="bd79a-112">Add certificates</span></span>

<span data-ttu-id="bd79a-113">Surface Hub 2S 인증 기관 인증서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="bd79a-114">Surface Hub 2S에 인증서를 추가 하려면 각 인증서의 복사본이 .cer 형식의 x.509로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="bd79a-115">.Crt, .pfx 또는 기타 컨테이너 형식을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="bd79a-116">인증서를 Windows 구성 디자이너로 가져오고 계층 구조로 정렬 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![인증서 추가](images/sh2-wcd.png)

### <span data-ttu-id="bd79a-118">OOBE 중 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="bd79a-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="bd79a-119">Windows 구성 디자이너에서 프록시 설정 구성 탭으로 이동 하 여 아래와 같이 적절 한 설정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![프록시 설정 구성](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="bd79a-121">프록시 설정을 구성할 때 설정 스크립트 또는 프록시 서버를 사용 하려는 경우 **자동으로 설정 검색** 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="bd79a-122">설치 *스크립트나 프록시 서버는 둘* 다 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="bd79a-123">Azure Active Directory를 사용 하는 계열사 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="bd79a-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="bd79a-124">프로 비전 패키지를 사용 하 여 Azure Active directory와의 계열사 Surface Hub 2S를 사용할 수 있습니다. Azure Active Directory 전역 관리자는 대량 토큰을 사용 하 여 많은 수의 새 Windows 장치를 Azure Active Directory 및 Intune에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="bd79a-125">대량 토큰을 만들려면 이름을 지정 하 고 만료 날짜 (최대 30 일)를 구성 하 고 관리자 자격 증명을 사용 하 여 아래와 같이 토큰을 취득 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![장치 관리자 설정](images/sh2-token.png) <br><br>
 ![장치 관리자 설정](images/sh2-token2.png) <br><br>
 ![장치 관리자 설정](images/sh2-token3.png) <br><br>

### <span data-ttu-id="bd79a-129">여러 장치 프로 비전 (.csv 파일)</span><span class="sxs-lookup"><span data-stu-id="bd79a-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="bd79a-130">배포 패키지 외에도 Surface Hub 구성 파일을 사용 하 여 디바이스를 더 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="bd79a-131">Surface Hub 구성 파일에는 디바이스 계정 목록과 무선 프로젝션에 대 한 친숙 한 이름이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="bd79a-132">처음 실행 하는 동안 구성 파일에서 디바이스 계정과 이름을 선택 하는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="bd79a-133">Surface Hub 구성 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bd79a-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="bd79a-134">Microsoft Excel 또는 다른 CSV 편집기를 사용 하 여 다음 이름의 CSV 파일을 만듭니다. **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="bd79a-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="bd79a-135">다음과 같은 형식으로 디바이스 계정과 이름 목록을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="bd79a-136">PPKG 파일을 복사한 USB 엄지 드라이브의 루트에 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd79a-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![구성 파일 예제](images/sh2-config-file.png)
