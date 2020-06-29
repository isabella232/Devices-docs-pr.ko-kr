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
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834391"
---
# <span data-ttu-id="c06c3-104">Microsoft Surface 배포 가속기</span><span class="sxs-lookup"><span data-stu-id="c06c3-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="c06c3-105">SDA (microsoft Surface Deployment Accelerator)는 무료 Microsoft 배포 도구를 사용 하 여 Microsoft 권장 배포 환경의 작성과 구성을 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="c06c3-106">2020 년 4 월에 다시 디자인 됨 기업 환경에서 화면 이미지 배포를 간소화 하 고 자동화 하기 위해 SDA 도구를 사용 하 여 조직의 요구 사항에 맞게 사용자 지정할 수 있는 "팩토리" Windows 이미지를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="c06c3-107">오픈 소스, 스크립트 기반 SDA 도구는 Windows 10 용 Windows ADK (평가 및 배포 키트)를 활용 하 여 테스트 또는 프로덕션 환경에서 WIM (Windows 이미지) 만들기를 촉진 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="c06c3-108">최신 ADK가 아직 설치 되지 않은 경우, SDA 도구를 실행할 때 다운로드 및 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="c06c3-109">결과 이미지는 Microsoft Office 또는 Surface UWP 응용 프로그램과 같이 사전 설치 된 응용 프로그램 없이도 완전 복구 (BMR) 이미지의 구성과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="c06c3-110">SDA를 실행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-110">To run SDA:</span></span>**

1. <span data-ttu-id="c06c3-111">GitHub에서 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="c06c3-112">**복제 또는 다운로드** 를 선택 하 고 Readme 파일을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="c06c3-113">추가 정보에 명시 된 환경에 적합 한 변수를 사용 하 여 스크립트를 편집 하 고 테스트 환경에서 실행 하기 전에 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06c3-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![Surface Deployment Accelerator 도구 실행](images/surface-deployment-accelerator.png)

## <span data-ttu-id="c06c3-115">관련 링크</span><span class="sxs-lookup"><span data-stu-id="c06c3-115">Related links</span></span>

 - [<span data-ttu-id="c06c3-116">GitHub에서 릴리스된 소스 이미지 배포 도구 열기</span><span class="sxs-lookup"><span data-stu-id="c06c3-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="c06c3-117">Windows ADK 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="c06c3-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
