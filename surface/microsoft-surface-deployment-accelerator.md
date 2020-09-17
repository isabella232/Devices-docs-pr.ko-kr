---
title: Microsoft Surface 배포 가속기(Surface)
description: Microsoft Surface 배포 가속기는 조직에서 Surface 디바이스의 이미지를 다시 작성하기 위한 빠르고 간편한 배포 메커니즘을 제공합니다.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 배포, 설치, 도구
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016559"
---
# <span data-ttu-id="952de-104">Microsoft Surface 배포 가속기</span><span class="sxs-lookup"><span data-stu-id="952de-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="952de-105">SDA (microsoft Surface Deployment Accelerator)는 무료 Microsoft 배포 도구를 사용 하 여 Microsoft 권장 배포 환경의 작성과 구성을 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="952de-106">2020 년 4 월에 다시 디자인 됨 기업 환경에서 화면 이미지 배포를 간소화 하 고 자동화 하기 위해 SDA 도구를 사용 하 여 조직의 요구 사항에 맞게 사용자 지정할 수 있는 "팩토리" Windows 이미지를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952de-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="952de-107">오픈 소스, 스크립트 기반 SDA 도구는 Windows 10 용 Windows ADK (평가 및 배포 키트)를 활용 하 여 테스트 또는 프로덕션 환경에서 WIM (Windows 이미지) 만들기를 촉진 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="952de-108">최신 ADK가 아직 설치 되지 않은 경우, SDA 도구를 실행할 때 다운로드 및 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="952de-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="952de-109">결과 이미지는 Microsoft Office 또는 Surface UWP 응용 프로그램과 같이 사전 설치 된 응용 프로그램 없이도 완전 복구 (BMR) 이미지의 구성과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="952de-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="952de-110">Requirements</span></span>

1. <span data-ttu-id="952de-111">USB 엄지 드라이브의 크기는 16gb 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="952de-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="952de-112">USB 드라이브의 포맷이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="952de-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="952de-113">Windows 10 Pro 또는 Windows 10 Enterprise를 사용 하는 .iso 파일</span><span class="sxs-lookup"><span data-stu-id="952de-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="952de-114">미디어 만들기 도구를 사용 하 여 Windows 10을 다운로드 하 고 .iso 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952de-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="952de-115">자세한 내용은 [Windows 10 다운로드](https://www.microsoft.com/software-download/windows10)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952de-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="952de-116">Windows 10 버전 2004 이상을 실행 하는 장치가 인터넷에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="952de-117">요구 사항에 대 한 자세한 내용은 추가 정보 문서의 [필수 구성 요소](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952de-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="952de-118">SDA를 실행 하는 방법</span><span class="sxs-lookup"><span data-stu-id="952de-118">How to run the SDA</span></span>

**<span data-ttu-id="952de-119">SDA를 실행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-119">To run SDA:</span></span>**

1. <span data-ttu-id="952de-120">GitHub에서 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="952de-121">[추가 정보](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 문서를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="952de-122">[SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 페이지에서 **코드** 단추를 클릭 한 다음 **ZIP 다운로드** 를 선택 하 여 파일을 컴퓨터에 로컬로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="952de-123">.Zip 파일을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="952de-124">**일반** 탭에서 **차단 해제** 확인란을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="952de-125">하드 드라이브의 위치 (예: C:\SDA)에 .zip 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="952de-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="952de-126">관리자 권한 Windows PowerShell 프롬프트를 열고 현재 세션에 대 한 ExecutionPolicy를 무제한으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="952de-127">사용자 환경에 대 한 매개 변수를 지정 하는 SDA 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="952de-128">이 스크립트를 사용 하 여 다양 한 Surface 장치에 Windows 10을 설치 하기 위한 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952de-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="952de-129">지원 되는 디바이스의 전체 목록은 SDA README 문서의 [장치 매개 변수 설명을](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952de-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="952de-130">예를 들어 다음 명령어는 [Surface Hub 2에 Windows 10을 설치](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)하는 데 사용할 수 있는 부팅 가능 USB 드라이브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="952de-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="952de-131">예제 스크립트 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="952de-131">Sample script output is below.</span></span>

   ![Surface Deployment Accelerator 도구 실행](images/sda1.png)

    <span data-ttu-id="952de-133">스크립트를 실행 하는 데 약 45 분이 필요 하지만 사용 가능한 CPU 및 디스크 리소스에 따라 시간이 더 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952de-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="952de-134">Windows 이미지를 만든 후 스크립트는 USB 드라이브의 드라이브 문자를 삽입 하 고 확인 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="952de-135">그런 다음 USB 드라이브는 부팅 가능으로 구성 되 고 화면 장치에 대 한 사용자 지정 Windows 10 이미지의 설치를 위해 복사 된 파일을 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="952de-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="952de-136">Windows 10을 설치할 장치에 USB 드라이브를 삽입 하 고 다시 부팅 하 여 Windows 10 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="952de-137">BIOS에서 USB 부팅을 사용 하도록 설정 해야 하며, 보안 부팅을 일시적으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952de-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="952de-138">USB 드라이브에서 부팅 하는 즉시 Windows 10 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="952de-139">USB를 삽입 하 고 다시 시작 하기 전에 장치가 준비 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="952de-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="952de-140">관련 링크</span><span class="sxs-lookup"><span data-stu-id="952de-140">Related links</span></span>

 - [<span data-ttu-id="952de-141">GitHub에서 릴리스된 소스 이미지 배포 도구 열기</span><span class="sxs-lookup"><span data-stu-id="952de-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="952de-142">Windows ADK 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="952de-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
