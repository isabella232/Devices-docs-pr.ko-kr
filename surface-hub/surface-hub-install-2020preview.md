---
title: Windows 10 Team 2020 업데이트 Preview 빌드 설치
description: Surface Hub 운영 체제, Windows 10 Team 2020 업데이트의 최신 업데이트를 지금 사용할 수 있습니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/13/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 51d6b9169b0074eb474ddc89b6fe9b43a921bb07
ms.sourcegitcommit: feb81137d009d9b7c743aabd7d02615e89842200
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929771"
---
# <span data-ttu-id="488a8-104">Windows 10 Team 2020 업데이트 Preview 빌드 설치</span><span class="sxs-lookup"><span data-stu-id="488a8-104">Install Windows 10 Team 2020 Update Preview Build</span></span> 

<span data-ttu-id="488a8-105">Surface hub 운영 체제, **windows 10 Team 2020 업데이트**의 최신 업데이트는 [windows 참가자 프로그램](https://insider.windows.com)에서 surface hub 50-인치 및 surface hub 2S 55-인치 장치에 대 한 추가 비용 없이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-105">The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com).</span></span> <span data-ttu-id="488a8-106">Surface Hub 84 인치 모델은 Windows 10 Team 2020 업데이트의 최종 릴리스에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-106">The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

<span data-ttu-id="488a8-107">Windows 10 Team 2020 업데이트는 Windows 10의 최신 기능과 함께 장치 배포 및 관리 효율성을 대폭 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-107">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="488a8-108">새로운 기능에 대해 자세히 알아보려면 다음 블로그 게시물을 참조 하세요. [공개 미리 보기에 대 한 새 Surface HUB OS 업데이트를 해제 했습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span><span class="sxs-lookup"><span data-stu-id="488a8-108">To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span></span> <span data-ttu-id="488a8-109">알려진 문제점은 아래의 "알려진 문제" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="488a8-109">For known issues, refer to the "Known issues" section below.</span></span>
 
## <span data-ttu-id="488a8-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="488a8-110">Prerequisites</span></span>

- <span data-ttu-id="488a8-111">[Windows 참가자 프로그램](https://insider.windows.com/)을 사용 하 여 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-111">Register with the [Windows Insider Program](https://insider.windows.com/).</span></span>
- <span data-ttu-id="488a8-112">Windows 참가자 프로그램의 빠른 채널에서 Windows 10 Team 2020 업데이트 Preview 빌드를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-112">Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.</span></span>
- <span data-ttu-id="488a8-113">Preview 빌드를 설치한 후 필요한 펌웨어 업데이트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-113">After you install the Preview build, download the required firmware updates.</span></span> <span data-ttu-id="488a8-114">참고: Windows 참가자 프로그램을 종료 하기로 결정 한 경우에도 펌웨어 업데이트를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-114">Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.</span></span>

## <span data-ttu-id="488a8-115">Surface Hub 준비</span><span class="sxs-lookup"><span data-stu-id="488a8-115">Prepare your Surface Hub</span></span>

<span data-ttu-id="488a8-116">시작 하기 전에 Surface Hub에 Windows 업데이트에서 최신 업데이트가 있는지 확인 하 고 장치와 연결 된 BitLocker 키를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-116">Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.</span></span>

**<span data-ttu-id="488a8-117">수동으로 업데이트를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-117">To manually check for updates:</span></span>**

1. <span data-ttu-id="488a8-118">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-118">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="488a8-119">**업데이트 & 보안**  >  **Windows 업데이트** 를 탐색 한 다음 **업데이트 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-119">Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.</span></span>

<span data-ttu-id="488a8-120">자세한 내용은 [Surface Hub에서 Windows 업데이트 관리](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="488a8-120">For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).</span></span>

**<span data-ttu-id="488a8-121">BitLocker 키를 수동으로 저장 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-121">To manually save your BitLocker key:</span></span>**

1. <span data-ttu-id="488a8-122">Surface Hub에 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-122">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="488a8-123">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-123">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="488a8-124">**& 보안**  >  **복구**업데이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-124">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="488a8-125">**BitLocker**에서 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-125">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="488a8-126">BitLocker 키가 USB 드라이브의 텍스트 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-126">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="488a8-127">자세한 내용은 [BitLocker 키 저장](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="488a8-127">For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).</span></span>
 
## <span data-ttu-id="488a8-128">Windows 10 Team 2020 업데이트 Preview 빌드 설치</span><span class="sxs-lookup"><span data-stu-id="488a8-128">Install the Windows 10 Team 2020 Update Preview Build</span></span>

1. <span data-ttu-id="488a8-129">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-129">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="488a8-130">**개인 정보 > 진단 & 피드백** 으로 이동 하 고 진단 데이터를 **전체**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-130">Navigate to **Privacy > Diagnostics & feedback** and set Diagnostic data to **Full**.</span></span> <span data-ttu-id="488a8-131">일부 지역 또는 조직은 MDM 정책 또는 PPKG 파일을 통해이 설정을 적용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-131">Some regions or organizations may need to apply this setting via MDM policy or PPKG file:</span></span>
   - <span data-ttu-id="488a8-132">**MDM:** 다음 정책을 설정 합니다. 정수 값이 3 인 **/Vendor/MSFT/Policy/System/AllowTelemetry** :</span><span class="sxs-lookup"><span data-stu-id="488a8-132">**For MDM:** Set the following policy: .**/Vendor/MSFT/Policy/System/AllowTelemetry** with the integer value of 3:</span></span>
    
        ![AllowTelemetry 분석을 3으로 설정](images/hub-2020-allow-telemetry.png)

    - <span data-ttu-id="488a8-134">**PPKG:** [Ppkg 파일](https://aka.ms/HubTltmtry)을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-134">**For PPKG:** Download the [PPKG file](https://aka.ms/HubTltmtry).</span></span>

3. <span data-ttu-id="488a8-135">**업데이트 & 보안**  >  **Windows 참가자 프로그램** 으로 이동한 다음 등록할 **시작** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-135">Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started** to enroll.</span></span>
4. <span data-ttu-id="488a8-136">메시지에 따라 회사 계정 (권장) 또는 개인 Microsoft 계정을 사용 하 여 Windows 참가자에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-136">Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account.</span></span> <span data-ttu-id="488a8-137">회사 계정으로 등록 하는 이점에 대 한 자세한 내용은 [비즈니스용 Windows 참가자 프로그램 등록](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="488a8-137">For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).</span></span>
5. <span data-ttu-id="488a8-138">**참가자 설정 선택**에서 **빠른**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-138">Under **Pick your Insider settings**, select **Fast**.</span></span>
6. <span data-ttu-id="488a8-139">Surface Hub에서 미리 보기 빌드와 필요한 펌웨어 업데이트를 다음 3 ~ 4 일 동안 자동으로 설치 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-139">Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days.</span></span> <span data-ttu-id="488a8-140">이 장치는 일상적인 [유지 관리 창](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)에서 자동으로 업데이트를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-140">The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).</span></span> <span data-ttu-id="488a8-141">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-141">For example:</span></span>

- <span data-ttu-id="488a8-142">첫 번째 유지 관리 창에서 Surface Hub는 Windows 업데이트에서 Preview 빌드를 다운로드 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-142">During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.</span></span>
- <span data-ttu-id="488a8-143">두 번째 유지 관리 기간 동안 장치가 다시 시작 되어 업데이트를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-143">During a second maintenance window, the device restarts to complete the update.</span></span>
- <span data-ttu-id="488a8-144">세 번째 유지 관리 창에서 장치는 필요한 펌웨어 업데이트를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-144">During a third maintenance window, the device downloads and installs the required firmware updates.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="488a8-145">Microsoft는 장치에서 미리 보기 빌드와 필요한 펌웨어 업데이트 설치를 완료할 수 있도록 3-4 일간 Surface Hub를 예약 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-145">Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates.</span></span> <span data-ttu-id="488a8-146">이 과정 중 장치를 사용 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-146">You may experience graphics, audio, and user interface issues if you use the device during this process.</span></span>

### <span data-ttu-id="488a8-147">Preview 빌드 및 필수 펌웨어 업데이트를 수동으로 설치 하도록 선택 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="488a8-147">If you choose to manually install the Preview Build and required firmware updates:</span></span>

1. <span data-ttu-id="488a8-148">Windows 참가자 프로그램에 등록 한 후에는 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로** 이동한 다음 **업데이트 확인** 을 선택 하 여 Preview 빌드를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-148">After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.</span></span>
2. <span data-ttu-id="488a8-149">Preview 빌드를 설치한 후 (최대 14 시간까지 소요 될 수 있음) **지금 다시 시작** 을 선택 하 여 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-149">Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.</span></span>
3. <span data-ttu-id="488a8-150">장치가 다시 시작 되 면 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로**이동한 다음 **업데이트 확인을 선택 하 여 필요한 펌웨어 업데이트를 설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-150">After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.</span></span>
4. <span data-ttu-id="488a8-151">펌웨어가 설치 되 면 **지금 다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-151">Once the firmware installs, select **Restart now**.</span></span>

> [!WARNING]
> <span data-ttu-id="488a8-152">필요한 펌웨어 업데이트를 설치 하지 않고 Preview 빌드를 설치 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-152">You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.</span></span>

> [!NOTE]
> <span data-ttu-id="488a8-153">Windows 참가자 프로그램을 종료 하 고 Surface Hub를 이전 버전의 운영 체제로 되돌리려는 경우 먼저 [장치를 재설정](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-153">If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub).</span></span> <span data-ttu-id="488a8-154">나중에 장치를 다시 구성 하려면 [첫 번째 실행 프로그램](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 을 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-154">Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.</span></span>
 

## <span data-ttu-id="488a8-155">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="488a8-155">Learn more</span></span>

- [<span data-ttu-id="488a8-156">알려진 문제점: Windows 10 Team 2020 업데이트</span><span class="sxs-lookup"><span data-stu-id="488a8-156">Known issues: Windows 10 Team 2020 Update</span></span>](surface-hub-2020-team-update-known-issues.md)
- [<span data-ttu-id="488a8-157">공개 미리 보기에 대 한 새로운 Surface Hub OS 업데이트를 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="488a8-157">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [<span data-ttu-id="488a8-158">비즈니스용 Windows 참가자 프로그램 시작하기</span><span class="sxs-lookup"><span data-stu-id="488a8-158">Getting started with the Windows Insider Program for Business</span></span>](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)