---
title: Surface 디바이스에서 PEAP, EAP-FAST 및 Cisco LEAP 사용(Surface)
description: Surface 디바이스에서 PEAP, EAP-FAST 또는 Cisco LEAP 프로토콜을 지원하도록 설정하는 방법에 대해 알아보세요.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: 네트워크, 무선, 디바이스, 배포, 인증 프로토콜
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835972"
---
# <span data-ttu-id="2c374-104">Surface 디바이스에서 PEAP, EAP-FAST 및 Cisco LEAP 사용</span><span class="sxs-lookup"><span data-stu-id="2c374-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="2c374-105">Surface 디바이스에서 PEAP, EAP-FAST 또는 Cisco LEAP 프로토콜을 지원하도록 설정하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2c374-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="2c374-106">엔터프라이즈 네트워크에서 PEAP, EAP-FAST 또는 Cisco LEAP를 사용하는 경우 이러한 세 가지 무선 인증 프로토콜이 기본 제공되는 Surface 디바이스에서 지원되지 않음을 이미 알고 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="2c374-107">무선 네트워크에 연결하려고 할 때 또는 파일 공유와 내부 사이트와 같이 네트워크 내부 리소스에 대한 액세스 권한을 얻지 못할 때 알 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="2c374-108">자세한 내용은 [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147)(확장할 수 있는 인증 프로토콜)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c374-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="2c374-109">USB 스틱 또는 파일 공유에서 작은 MSI 패키지를 실행하여 각 프로토콜에 대한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="2c374-110">해당 Surface 장치에서 EAP 지원을 사용 하려는 조직의 경우 MSI 패키지 형식은 MDT (Microsoft 배포 도구 키트) 및 Microsoft 끝점 구성 관리자와 같은 다양 한 관리 및 배포 도구를 사용 하 여 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="2c374-111">PEAP, EAP-FAST 또는 Cisco LEAP 설치 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="2c374-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="2c374-112">EAP, EAP-FAST 또는 Cisco LEAP에 대한 MSI 설치 파일을 Microsoft 다운로드 센터에서 하나의 zip 보관 파일로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="2c374-113">이 파일을 다운로드하려면 Microsoft 다운로드 센터에서 [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)(IT용 Surface 도구) 페이지로 이동하여 **Download**(다운로드)를 클릭한 다음 **Cisco EAP-Supplicant Installer.zip** 파일을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2c374-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="2c374-114">MDT로 PEAP, EAP-FAST 또는 Cisco LEAP 배포</span><span class="sxs-lookup"><span data-stu-id="2c374-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="2c374-115">조직에서 Surface 디바이스에 Windows 배포를 이미 수행 중인 경우 빠르고 쉽게 각 프로토콜에 대한 설치 파일을 배포 공유에 추가하고 배포 중 자동 설치를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="2c374-116">업데이트에서 이전에 Surface 디바이스를 배포한 작업 순서를 구성하여 동일한 프로세스로 이러한 프로토콜에 대한 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="2c374-117">새로 배포된 Surface 디바이스에서 PEAP, EAP-FAST 또는 Cisco LEAP에 대한 지원을 사용하도록 설정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2c374-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="2c374-118">각 프로토콜에 대한 설치 파일을 다운로드하고 추출하여 쉽게 액세스할 수 있는 위치에 폴더를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="2c374-119">MDT Deployment Workbench를 열고 배포 공유를 **Applications**(응용 프로그램) 폴더로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="2c374-120">**Action**(동작) 창에서 **New Application**(새 응용 프로그램)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="2c374-121">**Application with source files**(응용 프로그램 및 원본 파일)를 선택하여 배포 공유에 MSI 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="2c374-122">원하는 프로토콜에 대해 1단계에서 만든 폴더를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="2c374-123">배포 공유에서 설치 파일을 저장할 폴더의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="2c374-124">명령줄을 지정하여 응용 프로그램을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="2c374-125">PEAP: **EAP PEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="2c374-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="2c374-126">LEAP: **EAP LEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="2c374-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="2c374-127">EAP-FAST: **EAP FAST.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="2c374-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="2c374-128">기본 옵션을 사용하여 새 응용 프로그램 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="2c374-129">원하는 각 프로토콜에 대해 3-8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="2c374-130">위의 단계를 수행하여 응용 프로그램으로 세 가지 MSI 패키지를 MDT로 가져오면 Windows 배포 마법사의 Applications(응용 프로그램) 페이지에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="2c374-131">일부 간단한 배포 시나리오에서는 관리자가 배포 시 각 패키지를 선택하도록 해도 충분하지만 권장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="2c374-132">이 사례에서는 관리자가 Surface 디바이스가 아닌 컴퓨터에 이 패키지를 적용하려고 하거나, 휴먼 오류로 인해 EAP 지원 없이 Surface 디바이스를 배포할 수 있는 가능성에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="2c374-133">Install Applications page(응용 프로그램 설치) 페이지에서 이러한 응용 프로그램을 숨기려면 각 응용 프로그램의 속성에서 **Hide this application in the Deployment Wizard**(배포 마법사에서 이 응용 프로그램 숨기기) 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="2c374-134">응용 프로그램이 숨겨지면 배포 중에는 선택적 응용 프로그램으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="2c374-135">Surface 배포 작업 순서에서 배포하려면 작업 순서에서 별도의 단계를 통해 설치할 수 있도록 명시적으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="2c374-136">프로토콜을 명시적으로 지정하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2c374-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="2c374-137">MDT Deployment Workbench에서 Surface 배포 작업 순서 속성을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="2c374-138">**Task Sequence**(작업 순서) 탭에서 **State Restore**(상태 복원) 아래의 **Install Applications**(응용 프로그램 설치)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="2c374-139">일반적으로 사전 응용 프로그램 및 사후 응용 프로그램의 Windows 업데이트 단계 사이에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="2c374-140">**Add**(추가) 단추를 사용하여 **General**(일반) 범주 아래에서 새 **Install Application**(응용 프로그램 설치) 단계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="2c374-141">**속성** 탭에서 **Install a single application**(단일 응용 프로그램 설치) 단계를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="2c374-142">목록에서 원하는 EAP 프로토콜을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="2c374-143">원하는 각 프로토콜에 대해 2-5단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="2c374-144">Configuration Manager를 사용하여 PEAP, EAP-FAST 또는 Cisco LEAP 배포</span><span class="sxs-lookup"><span data-stu-id="2c374-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="2c374-145">Configuration Manager를 사용하여 Surface 디바이스를 관리하는 조직의 경우 PEAP, EAP-FAST 또는 Cisco LEAP 지원을 Surface 디바이스에 배포하는 것이 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="2c374-146">소프트웨어 라이브러리에서 각 MSI 파일을 응용 프로그램으로 가져와 Surface 디바이스 컬렉션에 배포를 구성하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c374-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="2c374-147">Configuration Manager를 사용하여 응용 프로그램을 배포하는 방법에 대한 자세한 내용은 [Configuration Manager에서 응용 프로그램을 만드는 방법](https://technet.microsoft.com/library/gg682159.aspx) 및 [Configuration Manager에서 응용 프로그램을 배포하는 방법](https://technet.microsoft.com/library/gg682082.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c374-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 





