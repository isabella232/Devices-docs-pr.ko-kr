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
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894114"
---
# <span data-ttu-id="5451c-104">Windows 10 Team 2020 업데이트 Preview 빌드 설치</span><span class="sxs-lookup"><span data-stu-id="5451c-104">Install Windows 10 Team 2020 Update Preview Build</span></span> 

<span data-ttu-id="5451c-105">Surface hub 운영 체제, **windows 10 Team 2020 업데이트**의 최신 업데이트는 [windows 참가자 프로그램](https://insider.windows.com)에서 surface hub 50-인치 및 surface hub 2S 55-인치 장치에 대 한 추가 비용 없이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-105">The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com).</span></span> <span data-ttu-id="5451c-106">Surface Hub 84 인치 모델은 Windows 10 Team 2020 업데이트의 최종 릴리스에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-106">The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

<span data-ttu-id="5451c-107">Windows 10 Team 2020 업데이트는 Windows 10의 최신 기능과 함께 장치 배포 및 관리 효율성을 대폭 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-107">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="5451c-108">새로운 기능에 대해 자세히 알아보려면 다음 블로그 게시물을 참조 하세요. [공개 미리 보기에 대 한 새 Surface HUB OS 업데이트를 해제 했습니다.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span><span class="sxs-lookup"><span data-stu-id="5451c-108">To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span></span> <span data-ttu-id="5451c-109">알려진 문제점은 아래의 "알려진 문제" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5451c-109">For known issues, refer to the "Known issues" section below.</span></span>
 
## <span data-ttu-id="5451c-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5451c-110">Prerequisites</span></span>

- <span data-ttu-id="5451c-111">[Windows 참가자 프로그램](https://insider.windows.com/)을 사용 하 여 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-111">Register with the [Windows Insider Program](https://insider.windows.com/).</span></span>
- <span data-ttu-id="5451c-112">Windows 참가자 프로그램의 빠른 채널에서 Windows 10 Team 2020 업데이트 Preview 빌드를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-112">Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.</span></span>
- <span data-ttu-id="5451c-113">Preview 빌드를 설치한 후 필요한 펌웨어 업데이트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-113">After you install the Preview build, download the required firmware updates.</span></span> <span data-ttu-id="5451c-114">참고: Windows 참가자 프로그램을 종료 하기로 결정 한 경우에도 펌웨어 업데이트를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-114">Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.</span></span>

## <span data-ttu-id="5451c-115">Surface Hub 준비</span><span class="sxs-lookup"><span data-stu-id="5451c-115">Prepare your Surface Hub</span></span>

<span data-ttu-id="5451c-116">시작 하기 전에 Surface Hub에 Windows 업데이트에서 최신 업데이트가 있는지 확인 하 고 장치와 연결 된 BitLocker 키를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-116">Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.</span></span>

**<span data-ttu-id="5451c-117">수동으로 업데이트를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-117">To manually check for updates:</span></span>**

1. <span data-ttu-id="5451c-118">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-118">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="5451c-119">**업데이트 & 보안**  >  **Windows 업데이트** 를 탐색 한 다음 **업데이트 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-119">Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.</span></span>

<span data-ttu-id="5451c-120">자세한 내용은 [Surface Hub에서 Windows 업데이트 관리](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5451c-120">For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).</span></span>

**<span data-ttu-id="5451c-121">BitLocker 키를 수동으로 저장 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-121">To manually save your BitLocker key:</span></span>**

1. <span data-ttu-id="5451c-122">Surface Hub에 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-122">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="5451c-123">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-123">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="5451c-124">**& 보안**  >  **복구**업데이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-124">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="5451c-125">**BitLocker**에서 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-125">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="5451c-126">BitLocker 키가 USB 드라이브의 텍스트 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-126">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="5451c-127">자세한 내용은 [BitLocker 키 저장](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5451c-127">For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).</span></span>
 
## <span data-ttu-id="5451c-128">Windows 10 Team 2020 업데이트 Preview 빌드 설치</span><span class="sxs-lookup"><span data-stu-id="5451c-128">Install the Windows 10 Team 2020 Update Preview Build</span></span>

1. <span data-ttu-id="5451c-129">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-129">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="5451c-130">**& 보안**  >  **Windows 참가자 프로그램** 업데이트로 이동한 다음 **시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-130">Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started**.</span></span>
3. <span data-ttu-id="5451c-131">메시지에 따라 회사 계정 (권장) 또는 개인 Microsoft 계정을 사용 하 여 Windows 참가자에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-131">Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account.</span></span> <span data-ttu-id="5451c-132">회사 계정으로 등록 하는 이점에 대 한 자세한 내용은 [비즈니스용 Windows 참가자 프로그램 등록](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5451c-132">For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).</span></span>
4. <span data-ttu-id="5451c-133">**참가자 설정 선택**에서 **빠른**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-133">Under **Pick your Insider settings**, select **Fast**.</span></span>
5. <span data-ttu-id="5451c-134">Surface Hub에서 미리 보기 빌드와 필요한 펌웨어 업데이트를 다음 3 ~ 4 일 동안 자동으로 설치 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-134">Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days.</span></span> <span data-ttu-id="5451c-135">이 장치는 일상적인 [유지 관리 창](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)에서 자동으로 업데이트를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-135">The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).</span></span> <span data-ttu-id="5451c-136">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-136">For example:</span></span>

- <span data-ttu-id="5451c-137">첫 번째 유지 관리 창에서 Surface Hub는 Windows 업데이트에서 Preview 빌드를 다운로드 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-137">During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.</span></span>
- <span data-ttu-id="5451c-138">두 번째 유지 관리 기간 동안 장치가 다시 시작 되어 업데이트를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-138">During a second maintenance window, the device restarts to complete the update.</span></span>
- <span data-ttu-id="5451c-139">세 번째 유지 관리 창에서 장치는 필요한 펌웨어 업데이트를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-139">During a third maintenance window, the device downloads and installs the required firmware updates.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5451c-140">Microsoft는 장치에서 미리 보기 빌드와 필요한 펌웨어 업데이트 설치를 완료할 수 있도록 3-4 일간 Surface Hub를 예약 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-140">Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates.</span></span> <span data-ttu-id="5451c-141">이 과정 중 장치를 사용 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-141">You may experience graphics, audio, and user interface issues if you use the device during this process.</span></span>

### <span data-ttu-id="5451c-142">Preview 빌드 및 필수 펌웨어 업데이트를 수동으로 설치 하도록 선택 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="5451c-142">If you choose to manually install the Preview Build and required firmware updates:</span></span>

1. <span data-ttu-id="5451c-143">Windows 참가자 프로그램에 등록 한 후에는 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로** 이동한 다음 **업데이트 확인** 을 선택 하 여 Preview 빌드를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-143">After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.</span></span>
2. <span data-ttu-id="5451c-144">Preview 빌드를 설치한 후 (최대 14 시간까지 소요 될 수 있음) **지금 다시 시작** 을 선택 하 여 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-144">Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.</span></span>
3. <span data-ttu-id="5451c-145">장치가 다시 시작 되 면 **설정**  >  **업데이트 & 보안**  >  **Windows 업데이트로**이동한 다음 **업데이트 확인을 선택 하 여 필요한 펌웨어 업데이트를 설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-145">After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.</span></span>
4. <span data-ttu-id="5451c-146">펌웨어가 설치 되 면 **지금 다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-146">Once the firmware installs, select **Restart now**.</span></span>

> [!WARNING]
> <span data-ttu-id="5451c-147">필요한 펌웨어 업데이트를 설치 하지 않고 Preview 빌드를 설치 하는 경우 그래픽, 오디오 및 사용자 인터페이스 문제가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-147">You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.</span></span>

> [!NOTE]
> <span data-ttu-id="5451c-148">Windows 참가자 프로그램을 종료 하 고 Surface Hub를 이전 버전의 운영 체제로 되돌리려는 경우 먼저 [장치를 재설정](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-148">If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub).</span></span> <span data-ttu-id="5451c-149">나중에 장치를 다시 구성 하려면 [첫 번째 실행 프로그램](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 을 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-149">Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.</span></span>
 
## <span data-ttu-id="5451c-150">알려진 문제점: Windows 10 Team 2020 업데이트 Preview 빌드</span><span class="sxs-lookup"><span data-stu-id="5451c-150">Known issues: Windows 10 Team 2020 Update Preview Build</span></span>

### <span data-ttu-id="5451c-151">그래픽, 오디오 및 사용자 인터페이스 문제</span><span class="sxs-lookup"><span data-stu-id="5451c-151">Graphics, audio, and user interface issues</span></span> 

<span data-ttu-id="5451c-152">미리 보기 빌드를 설치 하 고 나중에 필요한 펌웨어 업데이트를 즉시 설치 하지 않는 경우 다양 한 그래픽 및 사용자 인터페이스 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-152">You may experience various graphics and user interface issues if you install the Preview Build, but do not immediately install the required firmware updates afterward.</span></span> <span data-ttu-id="5451c-153">Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서 이러한 문제를 해결 하는 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-153">Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="5451c-154">Surface Hub 84-인치: 그래픽 및 사용자 인터페이스 문제</span><span class="sxs-lookup"><span data-stu-id="5451c-154">Surface Hub 84-inch: graphics and user interface issues</span></span>

<span data-ttu-id="5451c-155">첫 번째 세대 Surface Hub 84 인치 장치에서 Preview 빌드를 설치 하는 경우 다양 한 그래픽 및 사용자 인터페이스 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-155">You may experience various graphics and user interface issues if you install the Preview Build on a first-generation Surface Hub 84-inch device.</span></span> <span data-ttu-id="5451c-156">Surface Hub 84-인치는 Windows 10 Team 2020 업데이트의 최종 릴리스에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-156">The Surface Hub 84-inch will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="5451c-157">조건부 액세스 정책이 적용 되는 경우 로그인에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-157">Sign in is impacted when Conditional Access policies are applied</span></span>

- <span data-ttu-id="5451c-158">Microsoft 화이트 보드와 같은 앱에 로그인 하려고 하면 로그인이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-158">Sign in fails when attempting to sign into apps such as Microsoft Whiteboard.</span></span> <span data-ttu-id="5451c-159">사용자는 먼저 시작 메뉴에서 [내 모임 및 파일](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) 에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-159">Users must first sign in from [My meetings and files](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) from the Start menu.</span></span>

- <span data-ttu-id="5451c-160">사용자 계정이 Surface Hub에서 Azure AD 조인에 사용 하는 것과 다른 Azure AD 테 넌 트에 등록 되어 있으면 로그인이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-160">Sign in fails if your user account is registered to a different Azure AD tenant than the one used by Surface Hub to Azure AD join.</span></span>

<span data-ttu-id="5451c-161">Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서 이러한 문제를 해결 하는 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-161">Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="5451c-162">사용할 수 없는 경우 Windows 업데이트에서 새 드라이버를 설치 하 라는 메시지가 표시 됨</span><span class="sxs-lookup"><span data-stu-id="5451c-162">Windows Update prompts to install new drivers when none are available</span></span>

<span data-ttu-id="5451c-163">**Settings**  >  **Update & Security**  >  Windows 10 Team 2020 업데이트와 필요한 펌웨어 업데이트를 설치한 후 설정 업데이트 & 보안**Windows 업데이트로** 이동 하면 다음 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-163">When you go to **Settings** > **Update & Security** > **Windows Update** after you’ve installed Windows 10 Team 2020 Update and the required firmware updates, you may see the following error:</span></span> 

- <span data-ttu-id="5451c-164">"PC의 현재 드라이버가 설치 하려고 하는 드라이버 보다 더 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-164">“A current driver on your PC may be better than the driver we’re trying to install.</span></span> <span data-ttu-id="5451c-165">설치를 계속 시도 합니다. "</span><span class="sxs-lookup"><span data-stu-id="5451c-165">We’ll keep trying to install.”</span></span> 

<span data-ttu-id="5451c-166">이 오류는 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-166">This error can be safely ignored.</span></span> <span data-ttu-id="5451c-167">Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-167">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="5451c-168">프로비저닝 패키지를 사용 하 여 Surface Hub 정책을 설치할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5451c-168">Unable to install Surface Hub policies using provisioning packages</span></span>

<span data-ttu-id="5451c-169">Surface Hub CSP (구성 서비스 공급자)의 정책을 사용 하는 배포 패키지를 설치 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-169">Provisioning packages that use policies from the Surface Hub Configuration Service Provider (CSP) fail to install.</span></span> <span data-ttu-id="5451c-170">지금은 Microsoft Intune 또는 다른 MDM (모바일 디바이스 관리) 공급자를 사용 하 여 Surface Hub 정책을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-170">For now, use Microsoft Intune or another mobile device management (MDM) provider to apply Surface Hub policies.</span></span> <span data-ttu-id="5451c-171">Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서이 문제를 해결 하기 위한 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-171">Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="5451c-172">처음 실행할 때 USB 드라이브를 중간에 제거 하 라는 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="5451c-172">Prompt to remove USB drive prematurely during first run</span></span>

<span data-ttu-id="5451c-173">처음 실행 하는 동안 배포 패키지를 사용 하 여 Surface Hub를 설정 하는 경우 장치가 Surface Hub 구성 파일을 읽을 수 있으려면 먼저 USB 드라이브를 제거 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-173">When using a provisioning package to setup Surface Hub during first run, you’re prompted to remove the USB drive before the device is able to read the Surface Hub configuration file.</span></span> <span data-ttu-id="5451c-174">구성 파일을 사용 하 여 장치 계정을 설정 하는 경우에는 메시지를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-174">Ignore the message if you’re using a configure file to setup your device account.</span></span> <span data-ttu-id="5451c-175">Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-175">Microsoft is actively investigating this issue.</span></span>
 
### <span data-ttu-id="5451c-176">처음 실행 하는 동안 프록시 설정을 설정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5451c-176">Unable to set up proxy settings during first run</span></span>

<span data-ttu-id="5451c-177">프록시를 사용 하 여 인터넷에 연결 하는 경우 첫 번째 실행 프로그램에서 인터넷 연결이 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-177">If you use a proxy to connect to the Internet, you may have limited Internet connectivity during the first run program.</span></span> <span data-ttu-id="5451c-178">Microsoft는 Windows 10 Team 2020 업데이트의 릴리스 빌드에서이 문제를 해결 하기 위한 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-178">Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.</span></span>
 
### <span data-ttu-id="5451c-179">Microsoft Store에서 앱을 다운로드 하면 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-179">An error appears when you download apps from Microsoft Store</span></span>

<span data-ttu-id="5451c-180">Microsoft Store에서 앱을 다운로드 하려면 로그인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-180">To download an app from the Microsoft Store, you will see a prompt to sign in.</span></span> <span data-ttu-id="5451c-181">알려진 문제로 인해 로그인 중 오류가 표시 되지만 앱을 다운로드 하는 기능에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-181">A known issue causes an error to appear during sign-in, but this doesn't affect your ability to download apps.</span></span> <span data-ttu-id="5451c-182">Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-182">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="5451c-183">Surface Hub 2S가 Wi-fi 연결을 일시적으로 잃는 경우</span><span class="sxs-lookup"><span data-stu-id="5451c-183">Surface Hub 2S intermittently loses Wi-Fi connection</span></span>

<span data-ttu-id="5451c-184">장치를 분리 하 여 다시 연결 하거나 이더넷 케이블을 사용 하 여 인터넷에 연결 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-184">Try unplugging your device and plugging it back in, or using an Ethernet cable to connect to the Internet.</span></span> <span data-ttu-id="5451c-185">Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-185">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="5451c-186">Surface Hub 2S 일시적으로 절전 모드에서 다시 시작 되지 않음</span><span class="sxs-lookup"><span data-stu-id="5451c-186">Surface Hub 2S intermittently fails to resume from sleep</span></span>

<span data-ttu-id="5451c-187">Surface Hub 2S 일시적으로 절전 모드에서 완전히 다시 시작 되지 않고 Microsoft 로고를 표시 하는 화면에서 응답 하지 않는 것 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-187">Surface Hub 2S may intermittently fail to fully resume from sleep and appear to stop responding on a screen showing the Microsoft logo.</span></span> <span data-ttu-id="5451c-188">장치를 분리 하 고 다시 연결 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5451c-188">Try unplugging your device and plugging it back in.</span></span> 

<span data-ttu-id="5451c-189">이 문제가 발생 하지 않도록 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-189">To prevent this issue:</span></span>

1. <span data-ttu-id="5451c-190">Surface Hub에서 **설정을** 열고 메시지가 표시 되 면 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-190">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="5451c-191">**Surface Hub**  >  **세션 & 전원을**탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-191">Navigate to **Surface Hub** > **Session & power**.</span></span> 
3. <span data-ttu-id="5451c-192">**장치가 절전 모드로 전환 되는 경우 다음 전원 설정을 사용 하 여** **연결 된 대기 모드를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5451c-192">Under **When the device goes to sleep, use this power setting**, select **Connected Standby.**</span></span>
4. <span data-ttu-id="5451c-193">아무도 없는 경우에는 **장치를 다음으로 절전 모드로 전환 하**고 사용 **안 함을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5451c-193">Under **When no one is present, put the device to sleep after**, select **Never.**</span></span>

<span data-ttu-id="5451c-194">Microsoft는 Windows 10 Team 2020 업데이트의 최종 릴리스 이전에 펌웨어 업데이트로이 문제를 해결 하기 위한 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-194">Microsoft plans to fix this issue in a firmware update prior to the final release of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="5451c-195">연결 앱이 보기에 없는 경우의 프로젝션 문제</span><span class="sxs-lookup"><span data-stu-id="5451c-195">Projection issues when the Connect app is not in view</span></span>

- <span data-ttu-id="5451c-196">케이블을 사용 하 여 Surface Hub에 프로젝션 할 때 연결 앱에서 다른 위치로 이동 하면 touchback 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-196">When you use a cable to project to Surface Hub, touchback stops working if you navigate away from the Connect app.</span></span>
- <span data-ttu-id="5451c-197">Miracast를 사용 하 여 허브에 투영할 때 연결 앱에서 다른 위치로 이동 하면 무선 연결이 곧 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-197">When you project to Surface Hub using Miracast, the wireless connection drops soon after you navigate away from the Connect app.</span></span>

<span data-ttu-id="5451c-198">Microsoft는 이러한 문제를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-198">Microsoft is actively investigating these issues.</span></span>

### <span data-ttu-id="5451c-199">비즈니스용 Skype가 미디어 트래픽에 대 한 프록시를 사용 하 고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-199">Skype for Business isn't using proxy for media traffic</span></span>

<span data-ttu-id="5451c-200">프록시를 사용 하는 일부 장치에서는 비즈니스용 Skype가 로그인 할 수 있지만, 미디어 트래픽에 대 한 프록시 서버는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-200">For some devices that use a proxy, Skype for Business can sign in, but will not use the proxy server for media traffic.</span></span> <span data-ttu-id="5451c-201">Microsoft는이 문제를 적극적으로 조사 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-201">Microsoft is actively investigating this issue.</span></span>

<span data-ttu-id="5451c-202">Microsoft 지원으로 사용자의 의견 및 제안을 공유 하도록 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-202">We invite you to share your insights and suggestions with Microsoft Support.</span></span>

## <span data-ttu-id="5451c-203">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="5451c-203">Learn more</span></span>

- [<span data-ttu-id="5451c-204">공개 미리 보기에 대 한 새로운 Surface Hub OS 업데이트를 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-204">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [<span data-ttu-id="5451c-205">비즈니스용 Windows 참가자 프로그램 시작하기</span><span class="sxs-lookup"><span data-stu-id="5451c-205">Getting started with the Windows Insider Program for Business</span></span>](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)