---
title: Surface Hub 복구 도구 사용
description: Surface Hub 복구 도구를 사용하여 SSD를 다시 이미지로 하는 방법
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/18/2020
ms.localizationpriority: medium
ms.openlocfilehash: 9df9de731ac5c8f8acb393db3d4b16e9d1c98a9e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312034"
---
# <span data-ttu-id="9e0c5-104">Surface Hub 복구 도구 사용</span><span class="sxs-lookup"><span data-stu-id="9e0c5-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="9e0c5-105">[Microsoft Surface Hub 복구 도구를](https://www.microsoft.com/download/details.aspx?id=52210) 사용하면 지원을 호출하거나 SSD를 교체하지 않고 Windows 10 데스크톱 장치를 사용하여 Surface Hub SSD(Solid State Drive)를 다시 이미지로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="9e0c5-106">이 도구를 사용하면 알 수 없는 관리자 암호, 부팅 오류, 클라우드 복구를 완료할 수 없는 SSD 또는 이전 버전의 운영 체제가 있는 장치의 경우 SSD를 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="9e0c5-107">이 도구는 물리적으로 손상된 SSD를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="9e0c5-108">복구 도구를 사용하여 Surface Hub SSD를 다시 이미지화하려면 Surface Hub에서 SSD를 제거하고 드라이브를 USB-SATA 케이블에 연결한 다음 복구 도구가 설치된 데스크톱 PC에 케이블을 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="9e0c5-109">Surface Hub에서 기존 드라이브를 제거하는 방법에 대한 자세한 내용은 [Surface Hub SSD 교체를 참조하세요.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="9e0c5-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e0c5-110">디바이스가 절전 또는 이미지 파일 다운로드를 중단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="9e0c5-111">이 도구가 드라이브를 다시 이미징하지 못하면 Surface Hub 지원에 [문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="9e0c5-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="9e0c5-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9e0c5-112">Prerequisites</span></span>

### <span data-ttu-id="9e0c5-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="9e0c5-113">Mandatory</span></span>

- <span data-ttu-id="9e0c5-114">64비트 버전의 Windows 10 버전 1607 이상을 실행하는 호스트 PC</span><span class="sxs-lookup"><span data-stu-id="9e0c5-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="9e0c5-115">인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="9e0c5-115">Internet access</span></span>
- <span data-ttu-id="9e0c5-116">USB 2.0 이상 포트 열기</span><span class="sxs-lookup"><span data-stu-id="9e0c5-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="9e0c5-117">USB-SATA 케이블</span><span class="sxs-lookup"><span data-stu-id="9e0c5-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="9e0c5-118">호스트 컴퓨터의 10GB의 사용성 있는 디스크 공간</span><span class="sxs-lookup"><span data-stu-id="9e0c5-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="9e0c5-119">Surface Hub 또는 지원 서비스에서 대체로 제공하는 SSD와 함께 제공되는 SSD입니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="9e0c5-120">Microsoft에서 제공하지 않는 SSD는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="9e0c5-121">권장 사항</span><span class="sxs-lookup"><span data-stu-id="9e0c5-121">Recommended</span></span>

- <span data-ttu-id="9e0c5-122">고속 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="9e0c5-122">High-speed Internet connection</span></span>
- <span data-ttu-id="9e0c5-123">USB 3.0 포트 열기</span><span class="sxs-lookup"><span data-stu-id="9e0c5-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="9e0c5-124">USB 3.0 이상 USB-SATA 케이블</span><span class="sxs-lookup"><span data-stu-id="9e0c5-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="9e0c5-125">이미징 도구는 다음과 같은 케이블 만들기 및 모델을 사용하여 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="9e0c5-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="9e0c5-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="9e0c5-127">일광 RCUC16001</span><span class="sxs-lookup"><span data-stu-id="9e0c5-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="9e0c5-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="9e0c5-128">Ugreen 20231</span></span>

## <span data-ttu-id="9e0c5-129">Surface Hub 복구 도구 다운로드</span><span class="sxs-lookup"><span data-stu-id="9e0c5-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="9e0c5-130">Surface Hub 복구 도구는 [IT용 Surface Hub 도구의](https://www.microsoft.com/download/details.aspx?id=52210) 파일 이름 아래에서 다운로드할 수 \*\*SurfaceHub_Recovery_v2.0.139.0.msi. \*\*</span><span class="sxs-lookup"><span data-stu-id="9e0c5-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.0.139.0.msi**.</span></span>

<span data-ttu-id="9e0c5-131">다운로드를 시작하려면 **다운로드를**클릭하고 **목록에서**SurfaceHub_Recovery_v2.0.139.0.msi선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e0c5-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.0.139.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="9e0c5-132">팝업에서 다음 중 하나를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="9e0c5-133">**실행을** 클릭하여 설치를 즉시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="9e0c5-134">나중에 **설치할** 수 있도록 저장을 클릭하여 컴퓨터에 다운로드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="9e0c5-135">호스트 PC에 Surface Hub 복구 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="9e0c5-136">Surface Hub 복구 도구 실행</span><span class="sxs-lookup"><span data-stu-id="9e0c5-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="9e0c5-137">호스트 PC에서 시작 \*\*\*\* 단추를 선택하고 왼쪽의 사전순 목록을 스크롤한 다음 복구 도구 바로 가기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 복구 도구 바로 가기](images/shrt-shortcut.png)

2. <span data-ttu-id="9e0c5-139">**시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-139">Click **Start**.</span></span>

    ![복구 도구 시작 단추](images/shrt-start.png)


3. <span data-ttu-id="9e0c5-141">지침 **창에서** 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e0c5-141">In the **Guidance** window, click **Next**.</span></span>

    ![컴퓨터 절전 지침으로 이동하지 않습니다.](images/shrt-guidance.png)

4. <span data-ttu-id="9e0c5-143">이미지 선택 창에서 **RS2** 또는 후속 **20H2를** \*\*\*\* 클릭하고 계속을 선택한 다음 이미지 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e0c5-143">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="9e0c5-144">![복구 도구 이미지 복구 ](images/shrt-select-image.png) ![ 도구 다운로드 이미지 선택](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="9e0c5-144">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="9e0c5-145">복구 이미지를 다운로드하는 시간은 인터넷 연결 속도에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-145">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="9e0c5-146">평균 회사 연결에서 8GB 이미지 파일을 다운로드하는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-146">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![이미지 다운로드](images/shrt-download.png)



5. <span data-ttu-id="9e0c5-148">다운로드가 완료되면 이 도구는 SSD 드라이브를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-148">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="9e0c5-149">도구가 연결된 드라이브를 찾을 수 없는 경우 사용되는 케이블이 SSD의 이름을 Windows에 보고하지 않을 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-149">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="9e0c5-150">이미징 도구는 드라이브 이름을 "LITEON L CH-128V2S USB Device"로 찾아야 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-150">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="9e0c5-151">Surface Hub에서 기존 드라이브를 제거하는 방법에 대한 자세한 내용은 [Surface Hub SSD 교체를 참조하세요.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="9e0c5-151">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![SSD 연결](images/shrt-drive.png)

6. <span data-ttu-id="9e0c5-153">드라이브가 인식되면 **시작을** 클릭하여 다시 이미징 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-153">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="9e0c5-154">드라이브의 모든 데이터가 지워지리라 경고하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9e0c5-154">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="9e0c5-155">드라이브에 시스템 이미지를 적용하기 전에 SSD가 다시 지정되어 포맷됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="9e0c5-156">시스템 이진 파일을 복사하는 데는 약 30분이 소요되지만 USB 버스의 속도, 사용되는 케이블 또는 시스템에 설치된 바이러스 백신 소프트웨어에 따라 시간이 더 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="9e0c5-157">문제 해결 및 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="9e0c5-157">Troubleshooting and common problems</span></span>

<span data-ttu-id="9e0c5-158">문제</span><span class="sxs-lookup"><span data-stu-id="9e0c5-158">Issue</span></span> | <span data-ttu-id="9e0c5-159">참고</span><span class="sxs-lookup"><span data-stu-id="9e0c5-159">Notes</span></span>
--- | ---
<span data-ttu-id="9e0c5-160">도구가 SSD 이미지에 실패</span><span class="sxs-lookup"><span data-stu-id="9e0c5-160">The tool fails to image the SSD</span></span> | <span data-ttu-id="9e0c5-161">팩터리 제공 SSD와 테스트된 케이블 중 하나를 사용하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="9e0c5-161">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="9e0c5-162">다시imaging 프로세스가 중단/고정된 것으로 표시</span><span class="sxs-lookup"><span data-stu-id="9e0c5-162">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="9e0c5-163">SSD에 영향을 주지 않는 Surface Hub 복구 도구를 닫았다가 다시 시작하는 것이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-163">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="9e0c5-164">도구에서 드라이브를 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-164">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="9e0c5-165">Surface Hub SSD가 "LITEON L CH-128V2S USB 장치Lite-On 드라이브로 열에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-165">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="9e0c5-166">드라이브가 다른 명명된 장치로 인식되는 경우 현재 케이블이 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-166">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="9e0c5-167">위에 나열된 다른 케이블 또는 테스트된 케이블 중 하나를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-167">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="9e0c5-168">오류: -2147024809</span><span class="sxs-lookup"><span data-stu-id="9e0c5-168">Error: -2147024809</span></span> | <span data-ttu-id="9e0c5-169">디스크 관리자를 열고 Surface Hub 드라이브에서 파티션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-169">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="9e0c5-170">드라이브 연결을 끊고 호스트 컴퓨터로 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-170">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="9e0c5-171">이미징 도구를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-171">Restart the imaging tool again.</span></span>

<span data-ttu-id="9e0c5-172">이 도구가 드라이브를 다시 이미징하지 못하면 Surface Hub 지원에 [문의하세요.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="9e0c5-172">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="9e0c5-173">버전 기록</span><span class="sxs-lookup"><span data-stu-id="9e0c5-173">Version history</span></span>

### <span data-ttu-id="9e0c5-174">버전 v2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="9e0c5-174">Version v2.0.139.0</span></span>

*<span data-ttu-id="9e0c5-175">릴리스 날짜: 2020년 12월 18일</span><span class="sxs-lookup"><span data-stu-id="9e0c5-175">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="9e0c5-176">이 버전의 Surface Hub 복구 도구는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e0c5-176">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="9e0c5-177">Windows 10 Team 2020 업데이트(20H2)를 지원하기 위해 업데이트</span><span class="sxs-lookup"><span data-stu-id="9e0c5-177">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="9e0c5-178">사용자 환경 개선</span><span class="sxs-lookup"><span data-stu-id="9e0c5-178">User experience improvements</span></span>
- <span data-ttu-id="9e0c5-179">아키텍처 변경 사항</span><span class="sxs-lookup"><span data-stu-id="9e0c5-179">Architectural changes</span></span>
- <span data-ttu-id="9e0c5-180">원격 분석 추가</span><span class="sxs-lookup"><span data-stu-id="9e0c5-180">Telemetry additions</span></span>

