---
title: 호환 가능한 Surface 장치에서 SSD 제거
description: 한 Surface 장치에서 다른 대상으로 SSD를 전송 하는 방법을 설명 합니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 00109e4e1bb3873fc2914b2044f58e6fa3b6c211
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104810"
---
# <span data-ttu-id="76214-103">호환 가능한 Surface 장치에서 SSD 제거에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="76214-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76214-104">이 문서는 엔터프라이즈 조직의 정식 IT 기술자만 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76214-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="76214-105">이 문서에서는 Surface 노트북 3 또는 Surface Pro X 에서만 SSDs를 제거 하 고 바꿀 수 있도록 정식 IT 기술자의 권장 모범 사례에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in Surface Laptop 3 or Surface Pro X only.</span></span> 

> [!WARNING]
> <span data-ttu-id="76214-106">장치 열기 및 장치 구성 요소 교체는 감전, 장치 손상, 화재, 개인 부상이 위험 및 기타 위험성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76214-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="76214-107">이러한 활동을 수행할 때는 항상 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="76214-108">[엔터프라이즈에 대 한 Rssd 제거 가이드](https://www.microsoft.com/download/100440)에서 식별 된 보안 예방 조치 및 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="76214-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="76214-109">"RSSD 제거 가이드" 엔터프라이즈에 대해 지정 된 안전 예방 조치 및 절차를 따를 수 없는 경우에는 전문가의 지원을 받는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76214-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="76214-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="76214-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76214-111">이 문서에서는 "엔터프라이즈 용 rSSD 제거 가이드"에서 설명 하는 일반 안전 주의 사항 및 안전 정책 및 절차를 이해 하 고 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="76214-112">SSD 제거 준비</span><span class="sxs-lookup"><span data-stu-id="76214-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="76214-113">최신 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="76214-113">Install the latest updates</span></span> 

<span data-ttu-id="76214-114">시작 하기 전에 Windows 버전에 최신 업데이트 intalled이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="76214-115">**시작**  >  **설정**  >  **업데이트 & 보안**으로 이동 하 고 **업데이트 확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="76214-116">사용 가능한 모든 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-116">Install all available updates.</span></span> 
2. <span data-ttu-id="76214-117">사용 가능한 모든 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-117">Install all available updates.</span></span>
3. <span data-ttu-id="76214-118">장치에 액세스 하는 데 필요한 암호가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="76214-119">BitLocker 관리</span><span class="sxs-lookup"><span data-stu-id="76214-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="76214-120">이 섹션에는 하드 디스크에 대해 BitLocker 암호화를 사용 하도록 설정한 조직에 대 한 권장 사항이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76214-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="76214-121">자세한 내용은 [BitLocker 복구 가이드](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76214-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="76214-122">SSD 제거 및 바꾸기 중에 BitLocker 암호화를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="76214-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="76214-123">SSD 제거 및 바꾸기 전에 장치를 암호화 하지 않으면 다음 단계에 따라 BitLocker를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="76214-124">**설정**에서 **bitlocker**를 입력 한 다음 **bitlocker 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="76214-125">**Bitlocker 해제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="76214-126">장치 전원을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-126">Power down the device.</span></span> 

### <span data-ttu-id="76214-127">SSD 제거 및 교체 중에 BitLocker 암호화가 사용 하도록 설정 된 경우</span><span class="sxs-lookup"><span data-stu-id="76214-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="76214-128">장치를 SSD 제거 및 바꾸기 전에 암호화 된 경우 다음 단계에 따라 BitLocker 복구 키를 생성 하 고 USB 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="76214-129">**설정**에서 **Bitlocker**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="76214-130">**Bitlocker**  > **생성 bitlocker 복구 키**관리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="76214-131">USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="76214-132">복구 키를 USB 저장소에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="76214-133">USB 드라이브를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="76214-134">장치 전원을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-134">Power down the device.</span></span> 

## <span data-ttu-id="76214-135">SSD 제거 및 바꾸기</span><span class="sxs-lookup"><span data-stu-id="76214-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="76214-136">[Rssd 제거 가이드의 엔터프라이즈에 대 한](https://www.microsoft.com/download/100440)지침을 사용 하 여 SSD를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="76214-137">원본 SSD를 새 장치에 넣고 새 장치를 유선 인터넷 연결에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="76214-138">새 장치를 켭니다.</span><span class="sxs-lookup"><span data-stu-id="76214-138">Power on the new device.</span></span> <span data-ttu-id="76214-139">장치는 시작 하는 동안 펌웨어 업데이트를 거쳐야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76214-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="76214-140">SSD 제거 및 바꾸기 이후</span><span class="sxs-lookup"><span data-stu-id="76214-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="76214-141">암호화 되지 않은 SSDs 관리</span><span class="sxs-lookup"><span data-stu-id="76214-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="76214-142">전송 하는 동안 SSD를 암호화 되지 않은 상태로 유지 하는 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="76214-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="76214-143">**Sign-In Options**  >  왼쪽에 있는 열쇠 아이콘으로 표시 되는 로그인 옵션**암호로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="76214-144">암호를 입력 하 고 해당 하는 경우 2 단계 인증 완료 보류 중에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="76214-145">완전히 로그인 한 후에는 **Start**  >  **계정**  >  **로그**시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="76214-146">암호를 사용 하 여 다시 로그인 하 고 메시지가 표시 되 면 Windows Hello 및 PIN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="76214-147">장치가 SSD 제거 및 교체를 용이 하 게 하기 위해 bitlocker를 사용 하지 않도록 설정 되어 있는 경우, 대체 한 후 bitlocker를 사용 하도록 설정 **하려면 bitlocker 용**bitlocker  >  **Manage Bitlocker**  >  **다시 시작 bitlocker**관리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76214-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="76214-148">Microsoft Surface (비즈니스 용 진단 도구 키트) (SDT)를 실행 하 여 전체 장치 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="76214-149">**설정**활성화로 이동 하 여 Windows 정품 인증을 확인  >  **Activation**합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="76214-150">오류 메시지가 표시 되는 경우 **문제 해결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="76214-151">Office **앱**을 열고 **파일**  >  **계정** 으로 이동한 다음 오류 메시지를 확인 하 여 office 계정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="76214-152">암호화 된 SSDs 관리</span><span class="sxs-lookup"><span data-stu-id="76214-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="76214-153">USB 드라이브에 저장 된 BitLocker 복구 키를 읽으려면 두 번째 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="76214-154">전송 하는 동안 SSD를 암호화 된 상태로 유지 하는 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="76214-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="76214-155">Bitlocker 복구 키가 포함 된 USB 드라이브를 두 번째 장치에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="76214-156">Bitlocker 복구 키가 포함 된 .txt 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="76214-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="76214-157">원본 SSD를 포함 하는 새 장치에 Bitlocker 복구 키를 수동으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="76214-158">BitLocker 복구 키를 입력 한 후 **Sign-In Options**  >  왼쪽에 있는 열쇠 아이콘으로 표시 되는 로그인 옵션**암호로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="76214-159">암호를 입력 하 고 로그인 하 여 2 단계 인증 완료를 보류 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="76214-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="76214-160">완전히 로그인 한 후에는 **Start**  >  **계정**  >  **로그**시작으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="76214-161">암호를 사용 하 여 다시 로그인 한 다음 Windows Hello를 설정 하 고 PIN을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="76214-162">장치에서 SSD 제거 및 교체를 용이 하 게 하기 위해 bitlocker를 사용 하지 않도록 설정 된 경우, 바꾼 후 bitlocker를 사용 하도록 **Settings**설정 하려면 bitlocker로 bitlocker  >  **Bitlocker**  >  **Manage Bitlocker**  >  **다시 시작**bitlocker를 관리 하세요를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="76214-163">**Sdt** 를 실행 하 여 전체 장치 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="76214-164">**설정**활성화로 이동 하 여 Windows 정품 인증을 확인  >  **Activation**합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="76214-165">오류 메시지가 표시 되는 경우 **문제 해결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="76214-166">Office 계정의 상태를 확인 하려면 **office 앱**을 연 다음 **파일**계정으로 이동 하 여  >  **Account** 오류 메시지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="76214-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="76214-167">추가 정보</span><span class="sxs-lookup"><span data-stu-id="76214-167">More information</span></span> 

<span data-ttu-id="76214-168">자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76214-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="76214-169">엔터프라이즈 용 rSSD 제거 가이드</span><span class="sxs-lookup"><span data-stu-id="76214-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="76214-170">BitLocker 복구 가이드</span><span class="sxs-lookup"><span data-stu-id="76214-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="76214-171">그래도 문제가 해결되지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="76214-171">Still need help?</span></span> <span data-ttu-id="76214-172">[Microsoft 커뮤니티](https://answers.microsoft.com/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76214-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>