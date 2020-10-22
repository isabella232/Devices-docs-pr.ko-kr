---
title: 호환 가능한 Surface 장치에서 SSD 제거
description: 이 문서에서는 자격 있는 IT 기술자를 대상으로 하 여 SSDs의 Ssd 및 surface Pro X 및 Surface 노트북 이동에 대 한 제거 및 교체에 대 한 권장 모범 사례에 대해 설명 합니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133173"
---
# <span data-ttu-id="d662f-103">호환 가능한 Surface 장치에서 SSD 제거에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="d662f-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d662f-104">이 문서는 엔터프라이즈 조직의 정식 IT 기술자만 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="d662f-105">다음 호환 가능한 Surface 장치에서 SSDs를 제거 하 고 바꾸기 위해 정식 IT 기술 지원에 사용 하는 권장 모범 사례에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="d662f-106">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="d662f-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="d662f-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="d662f-107">Surface Pro X</span></span> 
- <span data-ttu-id="d662f-108">Surface 랩톱 이동</span><span class="sxs-lookup"><span data-stu-id="d662f-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="d662f-109">장치 열기 및 장치 구성 요소 교체는 감전, 장치 손상, 화재, 개인 부상이 위험 및 기타 위험성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="d662f-110">이러한 활동을 수행할 때는 항상 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="d662f-111">[엔터프라이즈에 대 한 Rssd 제거 가이드](https://www.microsoft.com/download/100440)에서 식별 된 보안 예방 조치 및 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="d662f-112">"RSSD 제거 가이드" 엔터프라이즈에 대해 지정 된 안전 예방 조치 및 절차를 따를 수 없는 경우에는 전문가의 지원을 받는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="d662f-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d662f-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d662f-114">이 문서에서는 "엔터프라이즈 용 rSSD 제거 가이드"에서 설명 하는 일반 안전 주의 사항 및 안전 정책 및 절차를 이해 하 고 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="d662f-115">SSD 제거 준비</span><span class="sxs-lookup"><span data-stu-id="d662f-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="d662f-116">최신 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="d662f-116">Install the latest updates</span></span> 

<span data-ttu-id="d662f-117">시작 하기 전에 Windows 버전에 최신 업데이트가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="d662f-118">**시작**  >  **설정**  >  **업데이트 & 보안**으로 이동 하 고 **업데이트 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="d662f-119">사용 가능한 모든 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-119">Install all available updates.</span></span>
3. <span data-ttu-id="d662f-120">장치에 액세스 하는 데 필요한 암호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="d662f-121">BitLocker 관리</span><span class="sxs-lookup"><span data-stu-id="d662f-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="d662f-122">이 섹션에는 하드 디스크에 대해 BitLocker 암호화를 사용 하도록 설정한 조직에 대 한 권장 사항이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="d662f-123">자세한 내용은  [BitLocker 복구 가이드](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d662f-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="d662f-124">SSD 제거 및 바꾸기 중에 BitLocker 암호화를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d662f-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="d662f-125">SSD 제거 및 바꾸기 전에 장치를 암호화 하지 않으면 다음 단계에 따라 BitLocker를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="d662f-126">**설정**에서 **bitlocker** 를 입력 한 다음 **bitlocker 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="d662f-127">**BitLocker 해제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="d662f-128">장치 전원을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-128">Power down the device.</span></span> 

### <span data-ttu-id="d662f-129">SSD 제거 및 교체 중에 BitLocker 암호화가 사용 하도록 설정 된 경우</span><span class="sxs-lookup"><span data-stu-id="d662f-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="d662f-130">장치를 SSD 제거 및 바꾸기 전에 암호화 된 경우 다음 단계에 따라 BitLocker 복구 키를 생성 하 고 USB 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="d662f-131">**설정**에서 **BitLocker**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="d662f-132">**Bitlocker**  > **생성 bitlocker 복구 키**관리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="d662f-133">USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="d662f-134">복구 키를 USB 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="d662f-135">USB 드라이브를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="d662f-136">장치 전원을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-136">Power down the device.</span></span> 

## <span data-ttu-id="d662f-137">SSD 제거 및 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d662f-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="d662f-138">[Rssd 제거 가이드의 엔터프라이즈에 대 한](https://www.microsoft.com/download/100440)지침을 사용 하 여 SSD를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="d662f-139">원본 SSD를 새 장치에 넣고 새 장치를 유선 인터넷 연결에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="d662f-140">새 장치를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-140">Power on the new device.</span></span> <span data-ttu-id="d662f-141">장치는 시작 하는 동안 펌웨어 업데이트를 거쳐야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="d662f-142">SSD 제거 및 바꾸기 이후</span><span class="sxs-lookup"><span data-stu-id="d662f-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="d662f-143">암호화 되지 않은 SSDs 관리</span><span class="sxs-lookup"><span data-stu-id="d662f-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="d662f-144">전송 하는 동안 SSD를 암호화 하지 않은 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d662f-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="d662f-145">**Sign-In Options**  >  왼쪽에 있는 열쇠 아이콘으로 표시 되는 로그인 옵션**암호로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="d662f-146">비밀 번호를 입력 하 고 해당 하는 경우 2 단계 인증 완료 대기 중에 로그인 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="d662f-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="d662f-147">완전히 로그인 한 후에는 **Start**  >  **계정**  >  **로그**시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="d662f-148">암호를 사용 하 여 다시 로그인 하 고 메시지가 표시 되 면 Windows Hello 및 PIN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="d662f-149">장치가 SSD 제거 및 교체를 용이 하 게 하기 위해 bitlocker를 사용 하지 않도록 설정 되어 있는 경우, 대체 한 후 bitlocker를 사용 하도록 설정 **하려면 bitlocker 용**bitlocker  >  **Manage BitLocker**  >  **다시 시작 bitlocker**관리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d662f-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="d662f-150">[Microsoft Surface (비즈니스 용 진단 도구 키트](surface-diagnostic-toolkit-for-business-intro.md) ) (sdt)를 실행 하 여 전체 장치 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="d662f-151">**설정**활성화로 이동 하 여 Windows 정품 인증을 확인  >  **Activation**합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="d662f-152">오류 메시지가 표시 되는 경우 **문제 해결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="d662f-153">Office **앱**을 열고 **파일**  >  **계정** 으로 이동한 다음 오류 메시지를 확인 하 여 office 계정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="d662f-154">암호화 된 SSDs 관리</span><span class="sxs-lookup"><span data-stu-id="d662f-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="d662f-155">USB 드라이브에 저장 된 BitLocker 복구 키를 읽으려면 두 번째 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="d662f-156">전송 하는 동안 SSD를 암호화 하는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="d662f-157">BitLocker 복구 키가 포함 된 USB 드라이브를 두 번째 장치에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="d662f-158">Bitlocker 복구 키가 포함 된 .txt 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="d662f-159">원본 SSD를 포함 하는 새 장치에 BitLocker 복구 키를 수동으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="d662f-160">BitLocker 복구 키를 입력 한 후 **Sign-In Options**  >  왼쪽에 있는 열쇠 아이콘으로 표시 되는 로그인 옵션**암호로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="d662f-161">암호를 입력 하 고 로그인 하 여 2 단계 인증 완료를 보류 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="d662f-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="d662f-162">완전히 로그인 한 후에는 **Start**  >  **계정**  >  **로그**시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="d662f-163">암호를 사용 하 여 다시 로그인 한 다음 Windows Hello를 설정 하 고 PIN을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="d662f-164">장치에서 SSD 제거 및 교체를 용이 하 게 하기 위해 bitlocker를 사용 하지 않도록 설정 된 경우, 바꾼 후 bitlocker를 사용 하도록 **Settings**설정 하려면 bitlocker로 bitlocker  >  **BitLocker**  >  **Manage BitLocker**  >  **다시 시작**bitlocker를 관리 하세요를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="d662f-165">**[Sdt](surface-diagnostic-toolkit-for-business-intro.md)** 를 실행 하 여 전체 장치 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="d662f-166">Windows 정품 인증을 확인 하려면 **설정**  >  **활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="d662f-167">오류 메시지가 표시 되는 경우 **문제 해결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="d662f-168">Office 계정의 상태를 확인 하려면 **office 앱**을 연 다음 **파일**계정으로 이동 하 여  >  **Account** 오류 메시지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d662f-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="d662f-169">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="d662f-169">Learn more</span></span>

- [<span data-ttu-id="d662f-170">엔터프라이즈 용 rSSD 제거 가이드</span><span class="sxs-lookup"><span data-stu-id="d662f-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="d662f-171">BitLocker 복구 가이드</span><span class="sxs-lookup"><span data-stu-id="d662f-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="d662f-172">그래도 문제가 해결되지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="d662f-172">Still need help?</span></span> <span data-ttu-id="d662f-173">[Microsoft 커뮤니티](https://answers.microsoft.com/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d662f-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>