---
title: Surface 배포용 OOBE 사용자 지정(Surface)
description: 이 문서에서는 조직에서 Surface 첫 실행 경험을 최종 사용자에게 맞게 사용자 지정하는 과정을 안내합니다.
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: 배포, 사용자 지정, 자동화, 네트워크, 펜, 쌍, 부팅
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835668"
---
# <span data-ttu-id="29cfe-104">Surface 배포용 OOBE 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="29cfe-104">Customize the OOBE for Surface deployments</span></span>

<span data-ttu-id="29cfe-105">이 문서에서는 조직의 최종 사용자에 게 제공 되는 화면 종료 경험을 사용자 지정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-105">This article describes customizing the Surface out-of-box experience for end users in your organization.</span></span>

<span data-ttu-id="29cfe-106">일반적으로 Windows 배포 과정에서 배포된 컴퓨터를 처음 시작하는 사용자 환경, 즉 OOBE(첫 실행 경험)를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-106">It is common practice in a Windows deployment to customize the user experience for the first startup of deployed computers — the out-of-box experience, or OOBE.</span></span>

>[!NOTE]
><span data-ttu-id="29cfe-107">또한 대개 OOBE를 사용하여 사용자 환경이 표시되는 Windows 설치 프로그램의 단계(구성 단계)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-107">OOBE is also often used to describe the phase, or configuration pass, of Windows setup during which the user experience is displayed.</span></span> <span data-ttu-id="29cfe-108">설치 프로그램의 OOBE 단계에 대한 자세한 내용은 [구성 단계 작동 방식](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29cfe-108">For more information about the OOBE phase of setup, see [How Configuration Passes Work](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).</span></span>

<span data-ttu-id="29cfe-109">일부 시나리오에서는 배포가 종료되면 아무런 사용자 조작 없이 컴퓨터를 사용할 준비가 되도록 완전한 자동화 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-109">In some scenarios, you may want to provide complete automation to ensure that at the end of a deployment, computers are ready for use without any interaction from the user.</span></span> <span data-ttu-id="29cfe-110">다른 시나리오에서는 사용자가 필요한 작업을 수행하거나 중요한 옵션 중에서 선택할 수 있도록 주요 환경 요소를 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-110">In other scenarios, you may want to leave key elements of the experience for users to perform necessary actions or select between important choices.</span></span> <span data-ttu-id="29cfe-111">이러한 각 시나리오에서 Surface 디바이스에 배포하는 관리자는 해결해야 할 고유한 과제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-111">For administrators deploying to Surface devices, each of these scenarios presents a unique challenge to overcome.</span></span>

> [!NOTE]
> <span data-ttu-id="29cfe-112">이 문서는 Surface Pro X에는 적용 되지 않습니다. 자세한 내용은 [Surface Pro X 배포, 관리 및 서비스](surface-pro-arm-app-management.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29cfe-112">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

<span data-ttu-id="29cfe-113">이 문서에서는 배포 시 추가 단계가 필요할 수도 있는 시나리오를 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-113">This article provides a summary of the scenarios where a deployment might require additional steps.</span></span> <span data-ttu-id="29cfe-114">또한 새로 배포된 Surface 디바이스에서 원하는 환경을 구현하는 데 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-114">It also provides the required information to ensure that the desired experience is achieved on any newly deployed Surface device.</span></span> <span data-ttu-id="29cfe-115">이 문서는 배포 프로세스뿐 아니라 응답 파일 및 [참조 이미지](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image)와 같은 개념에 익숙한 관리자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-115">This article is intended for administrators who are familiar with the deployment process, as well as concepts such as answer files and [reference images](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).</span></span>

>[!NOTE]
><span data-ttu-id="29cfe-116">[MDT (Microsoft Deployment Toolkit)](https://go.microsoft.com/fwlink/p/?LinkId=618117) 또는 Microsoft Endpoint Configuration Manager Os (운영 체제 배포)와 같은 자동화 된 배포 솔루션을 사용 하 여 배포 중에도 설치의 OOBE 단계가 실행 되기는 하지만 배포 마법사 및 작업 순서에서 제공 하는 설정에 따라 자동화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-116">Although the OOBE phase of setup is still run during a deployment with an automated deployment solution such as the [Microsoft Deployment Toolkit (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) or Microsoft Endpoint Configuration Manager Operating System Deployment (OSD), it is automated by the settings supplied in the Deployment Wizard and task sequence.</span></span> <span data-ttu-id="29cfe-117">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29cfe-117">For more information see:</span></span><br/>
>- [<span data-ttu-id="29cfe-118">Microsoft Deployment Toolkit을 사용하여 Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="29cfe-118">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [<span data-ttu-id="29cfe-119">System Center 2012 R2 Configuration Manager를 사용하여 Windows 10 배포</span><span class="sxs-lookup"><span data-stu-id="29cfe-119">Deploy Windows 10 with System Center 2012 R2 Configuration Manager</span></span>](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

## <span data-ttu-id="29cfe-120">시나리오 1: MDT 2013을 사용하여 OOBE에서 무선 네트워킹</span><span class="sxs-lookup"><span data-stu-id="29cfe-120">Scenario 1: Wireless networking in OOBE with MDT 2013</span></span>


<span data-ttu-id="29cfe-121">OOBE 중 무선 네트워크 어댑터가 표시되면 **무선 네트워크 연결** 페이지가 나타나 사용자에게 무선 네트워크에 연결하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-121">When a wireless network adapter is present during OOBE, the **Join a wireless network** page is displayed, which prompts a user to connect to a wireless network.</span></span> <span data-ttu-id="29cfe-122">이 페이지는 MDT 2013과 같은 배포 기술에서 자동으로 숨겨지지 않습니다. 따라서 완벽하게 자동화되도록 배포를 구성한 경우에도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-122">This page is not automatically hidden by deployment technologies, including MDT 2013, and therefore will be displayed even when a deployment is configured for complete automation.</span></span>

<span data-ttu-id="29cfe-123">이 페이지에서 자동화된 배포가 중지되지 않도록 응답 파일 **HideWirelessSetupInOOBE**에서 추가 설정을 구성하여 페이지를 숨겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-123">To ensure that an automated deployment is not stopped by this page, the page must be hidden by configuring an additional setting in the answer file, **HideWirelessSetupInOOBE**.</span></span> <span data-ttu-id="29cfe-124">**HideWirelessSetupInOOBE** 설정에 대한 추가 정보는 [Windows 무인 설치 참조](https://technet.microsoft.com/library/ff716213.aspx)에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-124">You can find additional information about the **HideWirelessSetupInOOBE** setting in [Unattended Windows Setup Reference](https://technet.microsoft.com/library/ff716213.aspx).</span></span>

## <span data-ttu-id="29cfe-125">시나리오 2: OOBE에서 Surface 펜 페어링</span><span class="sxs-lookup"><span data-stu-id="29cfe-125">Scenario 2: Surface Pen pairing in OOBE</span></span>


<span data-ttu-id="29cfe-126">Surface Pro 3, Surface Pro 4, Surface Book 또는 Surface Studio의 포장을 뜯고 처음으로 시작하면 포함된 Surface 펜을 디바이스에 페어링하라는 메시지가 출하 시 이미지의 첫 실행 경험에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-126">When you first take a Surface Pro 3, Surface Pro 4, Surface Book, or Surface Studio out of the package and start it up, the first-run experience of the factory image includes a prompt that asks you to pair the included Surface Pen to the device.</span></span> <span data-ttu-id="29cfe-127">이 프롬프트는 디바이스와 함께 제공되는 출하 시 이미지에서만 제공되며, 볼륨 라이선스 서비스 센터에서 다운로드하는 Windows Enterprise 설치 미디어와 같은 배포에 사용되는 다른 이미지에는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-127">This prompt is only provided by the factory image that ships with the device and is not included in other images used for deployment, such as the Windows Enterprise installation media downloaded from the Volume Licensing Service Center.</span></span> <span data-ttu-id="29cfe-128">이 환경이 아닌 상태에서 Bluetooth Surface 펜을 페어링할 경우에는 제어판 또는 PC 설정을 시작하여 Bluetooth 디바이스를 수동으로 페어링해야 하므로 페어링 작업을 수행하기 위해 사용자나 관리자가 이 프롬프트를 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-128">Because pairing the Bluetooth Surface Pen outside of this experience requires that you enter the Control Panel or PC Settings and manually pair a Bluetooth device, you may want to have users or a technician use this prompt to perform the pairing operation.</span></span>

<span data-ttu-id="29cfe-129">OOBE에서 처음 Surface 펜 페어링 환경을 제공하려면 출하 시 Surface 이미지 파일 4개를 참조 이미지로 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-129">To provide the factory Surface Pen pairing experience in OOBE, you must copy four files from the factory Surface image into the reference image.</span></span> <span data-ttu-id="29cfe-130">참조 이미지를 캡처하기 전에 참조 환경으로 이 파일을 복사하거나, DISM(배포 이미지 서비스 및 관리)을 사용해 이미지를 마운팅하여 나중에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-130">You can copy these files into the reference environment before you capture the reference image, or you can add them later by using Deployment Image Servicing and Management (DISM) to mount the image.</span></span> <span data-ttu-id="29cfe-131">필요한 파일 4개는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-131">The four required files are:</span></span>

-   <span data-ttu-id="29cfe-132">%windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml</span><span class="sxs-lookup"><span data-stu-id="29cfe-132">%windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml</span></span>
-   <span data-ttu-id="29cfe-133">%windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="29cfe-133">%windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png</span></span>
-   <span data-ttu-id="29cfe-134">%windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="29cfe-134">%windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png</span></span>
-   <span data-ttu-id="29cfe-135">%windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="29cfe-135">%windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png</span></span>

>[!NOTE]
><span data-ttu-id="29cfe-136">배포하려는 동일한 모델 Surface 디바이스의 출하 시 이미지에서 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-136">You should copy the files from a factory image for the same model Surface device that you intend to deploy to.</span></span> <span data-ttu-id="29cfe-137">예를 들어 surface pro 7의 파일을 사용 하 여 surface Pro 7에 배포 하 고 surface Book 2의 파일을 surface book 2로 배포 하는 경우 surface Pro 7의 파일을 사용 하 여 Surface Book 또는 Surface Pro 6을 배포 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-137">For example, you should use the files from a Surface Pro 7 to deploy to Surface Pro 7, and the files from Surface Book 2 to deploy Surface Book 2, but you should not use the files from a Surface Pro 7 to deploy Surface Book or Surface Pro 6.</span></span>

 

<span data-ttu-id="29cfe-138">이러한 필수 파일을 이미지에 추가하기 위한 단계별 프로세스는 [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/)(Surface Pro 3 펜 및 OneNote 팁 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29cfe-138">The step-by-step process for adding these required files to an image is described in [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/).</span></span> <span data-ttu-id="29cfe-139">이 블로그에는 Surface 펜 빠른 노트 작성 환경에 필요한 업데이트를 설치하여 사용자가 한 번의 클릭으로 노트를 OneNote로 보낼 수 있게 하는 팁도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29cfe-139">This blog post also includes tips to ensure that the necessary updates for the Surface Pen Quick Note-Taking Experience are installed, which allows users to send notes to OneNote with a single click.</span></span>

 

 





