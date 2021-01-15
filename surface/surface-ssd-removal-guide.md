---
title: 호환되는 Surface 디바이스에서 SSD 제거
description: 적격 IT 기술자를 위한 이 문서에서는 Surface Laptop 3, Surface Pro X 및 Surface Laptop Go에서 SSD를 제거하고 교체하는 데 권장되는 모범 사례에 대해 설명하고 있습니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270633"
---
# <span data-ttu-id="10048-103">호환되는 Surface 디바이스에서 SSD 제거 모범 사례</span><span class="sxs-lookup"><span data-stu-id="10048-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10048-104">이 문서는 엔터프라이즈 조직의 적격 IT 기술자만 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="10048-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="10048-105">다음 호환되는 Surface 디바이스에서 SSD를 제거하고 교체할 때 적격 IT 기술자가 사용할 수 있는 권장 모범 사례에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10048-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="10048-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="10048-106">Surface Pro 7+</span></span>
- <span data-ttu-id="10048-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="10048-107">Surface Pro X</span></span>
- <span data-ttu-id="10048-108">Surface 노트북 이동</span><span class="sxs-lookup"><span data-stu-id="10048-108">Surface Laptop Go</span></span>
- <span data-ttu-id="10048-109">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="10048-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="10048-110">장치를 열고 장치 구성 요소를 교체하면 감전, 장치 손상, 화재 및 개인 상해 위험 및 기타 위험을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10048-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="10048-111">이러한 활동을 진행할 때는 항상 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="10048-112">엔터프라이즈용 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에 식별된 안전 예방조치 및 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="10048-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="10048-113">"엔터프라이즈용 rSSD 제거 가이드"에 지정된 안전 예방조치 및 절차를 따를 수 없는 경우 전문 지원을 받을 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="10048-114">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="10048-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10048-115">이 문서에서는 "엔터프라이즈용 rSSD 제거 가이드"에 설명된 일반 안전 예방조치 및 안전 정책 및 절차를 이해하고 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="10048-116">SSD 제거 준비</span><span class="sxs-lookup"><span data-stu-id="10048-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="10048-117">최신 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="10048-117">Install the latest updates</span></span> 

<span data-ttu-id="10048-118">시작하기 전에 Windows 버전에 최신 업데이트가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="10048-119">Go to **Start**  >  **Settings**  >  **Update & Security,** and select **Check for updates.**</span><span class="sxs-lookup"><span data-stu-id="10048-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="10048-120">사용 가능한 모든 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-120">Install all available updates.</span></span>
3. <span data-ttu-id="10048-121">장치에 액세스하는 데 필요한 암호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="10048-122">BitLocker 관리</span><span class="sxs-lookup"><span data-stu-id="10048-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="10048-123">이 섹션에는 하드 디스크에 대해 BitLocker 암호화를 사용하도록 설정한 조직에 대한 권장 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10048-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="10048-124">자세한 내용은 [BitLocker 복구 가이드를 참조하세요.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="10048-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="10048-125">SSD 제거 및 교체 중에 BitLocker 암호화를 사용하지 않도록 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="10048-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="10048-126">SSD 제거 및 교체 전에 디바이스를 암호화 해제할 수 있는 경우 다음 단계에 따라 BitLocker를 끄세요.</span><span class="sxs-lookup"><span data-stu-id="10048-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="10048-127">**설정에서** **BitLocker를 입력한** 다음 **BitLocker 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="10048-128">**BitLocker 끄기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="10048-129">디바이스 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="10048-129">Power down the device.</span></span> 

### <span data-ttu-id="10048-130">SSD 제거 및 교체 중에 BitLocker 암호화를 사용하도록 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="10048-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="10048-131">SSD 제거 및 교체 전에 장치가 암호화된 경우 다음 단계에 따라 BitLocker 복구 키를 생성하고 USB 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="10048-132">**설정에서** **BitLocker를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="10048-133">Select **Manage BitLocker**  > **Generate BitLocker Recovery Key.**</span><span class="sxs-lookup"><span data-stu-id="10048-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="10048-134">USB 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="10048-135">복구 키를 USB 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="10048-136">USB 드라이브를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="10048-137">디바이스 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="10048-137">Power down the device.</span></span> 

## <span data-ttu-id="10048-138">SSD 제거 및 바꾸기</span><span class="sxs-lookup"><span data-stu-id="10048-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="10048-139">엔터프라이즈용 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에 포함된 장치에 대한 적절한 지침을 사용하여 SSD를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="10048-140">원래 SSD를 새 장치에 저장하고 새 장치를 유선 인터넷 연결에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="10048-141">새 디바이스에서 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="10048-141">Power on the new device.</span></span> <span data-ttu-id="10048-142">디바이스가 시작 중에 펌웨어 업데이트를 거치게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10048-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="10048-143">SSD 제거 및 교체 후</span><span class="sxs-lookup"><span data-stu-id="10048-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="10048-144">암호화되지 않은 SDD 관리</span><span class="sxs-lookup"><span data-stu-id="10048-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="10048-145">전송 중에 SSD가 암호화되지 않은 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="10048-146">Go to **Sign-In Options**  >  **Password** (represented by the key icon on the left side.</span><span class="sxs-lookup"><span data-stu-id="10048-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="10048-147">암호를 입력하고 2단계 인증 완료 대기(해당하는 경우)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="10048-148">완전히 로그인한 후 계정 로그인 \*\*\*\*  >  \*\*\*\*  >  **시작으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="10048-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="10048-149">암호를 사용하여 다시 로그인하고 메시지가 표시될 때 Windows Hello 및 PIN을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="10048-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="10048-150">장치가 SSD 제거 및 교체를 용이하게 하기 위해 BitLocker를 사용하지 않도록 설정한 경우 대체 후 BitLocker를 사용하도록 설정하려면 **BitLocker**  >  **관리 BitLocker**다시 시작  >  **BitLocker로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="10048-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="10048-151">Microsoft [Surface Diagnostic](surface-diagnostic-toolkit-for-business-intro.md) Toolkit(비즈니스용 SDT)를 실행하여 전체 장치 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="10048-152">설정 정품 인증으로 이동하여 Windows 정품 **인증을**  >  **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="10048-153">오류 메시지가 표시되어 있는 경우 문제 해결을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="10048-154">Office 앱을 열고 **파일**계정으로 \*\*\*\* 이동한 다음 오류 메시지를 확인하여 Office  >  \*\*\*\* 계정을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="10048-155">암호화된 SDD 관리</span><span class="sxs-lookup"><span data-stu-id="10048-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="10048-156">USB 드라이브에 저장된 BitLocker 복구 키를 읽으기 위해 두 번째 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="10048-157">SSD가 전송 중에 암호화된 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="10048-158">BitLocker 복구 키가 포함된 USB 드라이브를 두 번째 장치에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="10048-159">Bitlocker 복구 키가 포함된 .txt 파일을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="10048-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="10048-160">원래 SSD가 포함된 새 디바이스에서 BitLocker 복구 키를 수동으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="10048-161">BitLocker 복구 키를 성공적으로 입력한 후 로그인 \*\*\*\* 옵션 암호(왼쪽의 키 아이콘으로  >  \*\*\*\* 표시)로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="10048-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="10048-162">암호를 입력하고 로그인하고 2단계 인증 완료를 보류 중입니다(해당하는 경우).</span><span class="sxs-lookup"><span data-stu-id="10048-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="10048-163">완전히 로그인한 후 계정 로그인 \*\*\*\*  >  \*\*\*\*  >  **시작으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="10048-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="10048-164">암호를 사용하여 다시 로그인한 다음 Windows Hello를 설정하고 PIN을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="10048-165">장치가 SSD 제거 및 교체를 용이하게 하기 위해 BitLocker를 사용하지 않도록 설정한 경우, \*\*\*\* 교체 후 BitLocker를 사용하도록 설정하려면  >  **BitLocker**관리  >  **BitLocker**다시 시작  >  **BitLocker로**이동합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="10048-166">**[SDT를 실행하여](surface-diagnostic-toolkit-for-business-intro.md)** 전체 장치 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="10048-167">Windows 정품 인증을 확인하려면 설정 **활성화를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="10048-168">오류 메시지가 표시되어 있는 경우 문제 해결을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="10048-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="10048-169">Office 계정의 상태를 확인하려면 **Office 앱을**연 다음 \*\*\*\* 파일 계정으로 이동하여 오류 메시지를  >  \*\*\*\* 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="10048-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="10048-170">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="10048-170">Learn more</span></span>

- [<span data-ttu-id="10048-171">엔터프라이즈용 rSSD 제거 가이드</span><span class="sxs-lookup"><span data-stu-id="10048-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="10048-172">BitLocker 복구 가이드</span><span class="sxs-lookup"><span data-stu-id="10048-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="10048-173">그래도 문제가 해결되지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="10048-173">Still need help?</span></span> <span data-ttu-id="10048-174">Microsoft [커뮤니티로 이동](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="10048-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>