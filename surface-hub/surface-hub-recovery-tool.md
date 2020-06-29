---
title: Surface Hub 복구 도구 사용
description: Surface Hub 복구 도구를 사용 하 여 SSD를 다시 이미지 하는 방법을 설명 합니다.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 관리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836896"
---
# <span data-ttu-id="3e42d-104">Surface Hub 복구 도구 사용</span><span class="sxs-lookup"><span data-stu-id="3e42d-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="3e42d-105">[Microsoft Surface Hub 복구 도구](https://www.microsoft.com/download/details.aspx?id=52210) 는 지원 또는 ssd 교체 없이 Windows 10 데스크톱 장치를 사용 하 여 SURFACE hub Ssd (고체 상태 드라이브)를 다시 이미지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="3e42d-106">이 도구를 사용 하 여 알 수 없는 관리자 암호를 가진 SSD, 부팅 오류, 클라우드 복구를 완료할 수 없거나 이전 버전의 운영 체제가 있는 장치에 대 한 목록을 이미지로 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="3e42d-107">도구가 물리적으로 손상 된 SSDs를 수정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="3e42d-108">복구 도구를 사용 하 여 Surface Hub SSD를 다시 이미지 하려면 Surface Hub에서 SSD를 제거 하 고 드라이브를 USB에서 SATA 케이블로 연결한 다음 복구 도구가 설치 된 데스크톱 PC에 케이블을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="3e42d-109">Surface Hub에서 기존 드라이브를 제거 하는 방법에 대 한 자세한 내용은 [Surface HUB SSD 대체](surface-hub-ssd-replacement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e42d-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e42d-110">장치를 절전 모드로 전환 하거나 이미지 파일의 다운로드를 중단 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3e42d-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="3e42d-111">도구가 드라이브 reimaging에 실패 하는 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e42d-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="3e42d-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3e42d-112">Prerequisites</span></span>

### <span data-ttu-id="3e42d-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="3e42d-113">Mandatory</span></span>

- <span data-ttu-id="3e42d-114">64 비트 버전의 Windows 10, 버전 1607 이상에서 실행 되는 호스트 PC</span><span class="sxs-lookup"><span data-stu-id="3e42d-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="3e42d-115">인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="3e42d-115">Internet access</span></span>
- <span data-ttu-id="3e42d-116">USB 2.0 이상 포트 열기</span><span class="sxs-lookup"><span data-stu-id="3e42d-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="3e42d-117">USB 대 SATA 케이블</span><span class="sxs-lookup"><span data-stu-id="3e42d-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="3e42d-118">호스트 컴퓨터에서 10gb의 사용 가능한 디스크 공간</span><span class="sxs-lookup"><span data-stu-id="3e42d-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="3e42d-119">SSDs는 Surface Hub 또는 지원 자가 제공 하는 SSD (대체)와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="3e42d-120">Microsoft에서 제공 하지 않은 SSDs는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="3e42d-121">권장 사항</span><span class="sxs-lookup"><span data-stu-id="3e42d-121">Recommended</span></span>

- <span data-ttu-id="3e42d-122">고속 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="3e42d-122">High-speed Internet connection</span></span>
- <span data-ttu-id="3e42d-123">USB 3.0 포트 열기</span><span class="sxs-lookup"><span data-stu-id="3e42d-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="3e42d-124">USB 3.0 이상 USB-SATA 케이블</span><span class="sxs-lookup"><span data-stu-id="3e42d-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="3e42d-125">이미징 도구는 다음 케이블의 제조업체와 모델로 테스트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="3e42d-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="3e42d-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="3e42d-127">RCUC16001 예정</span><span class="sxs-lookup"><span data-stu-id="3e42d-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="3e42d-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="3e42d-128">Ugreen 20231</span></span>

## <span data-ttu-id="3e42d-129">Surface Hub 복구 도구 다운로드</span><span class="sxs-lookup"><span data-stu-id="3e42d-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="3e42d-130">Surface Hub 복구 도구는 [Surface Hub 도구](https://www.microsoft.com/download/details.aspx?id=52210) 에서 다운로드할 수 있는 파일 이름 **SurfaceHub_Recovery_v1.14.137.0.msi**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="3e42d-131">다운로드를 시작 하려면 **다운로드**를 클릭 하 고 목록에서 **SurfaceHub_Recovery_v1.14.137.0.msi** 를 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="3e42d-132">팝업 창에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="3e42d-133">**실행** 을 클릭 하 여 바로 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="3e42d-134">**저장** 을 클릭 하 여 나중에 설치 하기 위해 다운로드를 컴퓨터에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="3e42d-135">호스트 PC에 Surface Hub 복구 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="3e42d-136">Surface Hub 복구 도구 실행</span><span class="sxs-lookup"><span data-stu-id="3e42d-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="3e42d-137">호스트 PC에서 **시작** 단추를 선택 하 고 왼쪽에 있는 알파벳순 목록을 스크롤한 다음 복구 도구 바로 가기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 복구 도구 바로 가기](images/shrt-shortcut.png)

2. <span data-ttu-id="3e42d-139">**시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-139">Click **Start**.</span></span>

    ![복구 도구 시작 단추](images/shrt-start.png)

3. <span data-ttu-id="3e42d-141">**지침** 창에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-141">In the **Guidance** window, click **Next**.</span></span>

    ![컴퓨터가 절전 지침으로 이동 하지 않도록 합니다.](images/shrt-guidance.png)

4. <span data-ttu-id="3e42d-143">**예** 를 클릭 하 여 이미지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-143">click **Yes** to download the image.</span></span> <span data-ttu-id="3e42d-144">복구 이미지를 다운로드 하는 데 걸리는 시간은 인터넷 연결 속도에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="3e42d-145">평균 기업 연결에서는 8GB 이미지 파일을 다운로드 하는 데 최대 1 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![이미지를 다운로드 하 시겠습니까?](images/shrt-download.png)

5. <span data-ttu-id="3e42d-147">다운로드가 완료 되 면이 도구는 SSD 드라이브에 연결 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="3e42d-148">도구가 연결 된 드라이브를 찾을 수 없는 경우 사용 중인 케이블이 Windows에 SSD의 이름을 보고 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="3e42d-149">계속 하려면 이미징 도구가 "LITEON L CH-128V2S USB Device"로 드라이브의 이름을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="3e42d-150">Surface Hub에서 기존 드라이브를 제거 하는 방법에 대 한 자세한 내용은 [Surface HUB SSD 대체](surface-hub-ssd-replacement.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e42d-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![SSD 연결](images/shrt-drive.png)

6. <span data-ttu-id="3e42d-152">드라이브가 인식 되 면 **시작** 을 클릭 하 여 다시 이미징 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="3e42d-153">드라이브의 모든 데이터가 삭제 된다는 경고 메시지가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![SSD 다시 이미징 시작](images/shrt-drive-start.png)

    <span data-ttu-id="3e42d-155">시스템 이미지를 드라이브에 적용 하기 전에 SSD는 repartitioned이 고 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="3e42d-156">시스템 바이너리 복사에는 약 30 분이 소요 되지만, USB 버스 속도, 사용 하는 케이블 또는 시스템에 설치 된 바이러스 백신 소프트웨어에 따라 시간이 더 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![복사 완료](images/shrt-done.png)

    ![Reimaging 완료](images/shrt-complete.png)

## <span data-ttu-id="3e42d-159">문제 해결 및 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="3e42d-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="3e42d-160">문제</span><span class="sxs-lookup"><span data-stu-id="3e42d-160">Issue</span></span> | <span data-ttu-id="3e42d-161">참고</span><span class="sxs-lookup"><span data-stu-id="3e42d-161">Notes</span></span>
--- | ---
<span data-ttu-id="3e42d-162">도구가 SSD를 이미지 하는 데 실패 함</span><span class="sxs-lookup"><span data-stu-id="3e42d-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="3e42d-163">출하 시 제공 된 SSD와 테스트 된 케이블 중 하나를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="3e42d-164">Reimaging 프로세스가 중지/동결 된 것 처럼 나타남</span><span class="sxs-lookup"><span data-stu-id="3e42d-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="3e42d-165">SSD에 아무런 영향도 주지 않고 Surface Hub 복구 도구를 닫았다가 다시 시작 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="3e42d-166">도구가이 드라이브를 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="3e42d-167">Surface Hub SSD는 Lite 드라이브 "LITEON L CH-128V2S USB 장치"로 열거 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="3e42d-168">드라이브가 다른 명명 된 장치로 인식 되 면 현재 케이블이 호환 되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="3e42d-169">다른 케이블을 사용 하거나 위에 나열 된 테스트 되는 케이블 중 하나를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="3e42d-170">오류:-2147024809</span><span class="sxs-lookup"><span data-stu-id="3e42d-170">Error: -2147024809</span></span> | <span data-ttu-id="3e42d-171">디스크 관리자를 열고 Surface Hub 드라이브에서 파티션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="3e42d-172">호스트 컴퓨터에 드라이브의 연결을 끊었다가 다시 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="3e42d-173">이미징 도구를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e42d-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="3e42d-174">도구가 드라이브 reimaging에 실패 하는 경우 [Surface Hub 지원](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e42d-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>
