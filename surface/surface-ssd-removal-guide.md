---
title: 호환되는 Surface 디바이스에서 SSD 제거
description: 자격을 갖춘 IT 기술자를 위한 이 문서에서는 Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X 및 Surface Laptop Go에서 SDSD 제거 및 교체에 권장되는 모범 사례에 대해 설명하고 있습니다.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576908"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="39d78-103">호환되는 Surface 디바이스에서 SSD 제거 모범 사례</span><span class="sxs-lookup"><span data-stu-id="39d78-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39d78-104">이 문서는 엔터프라이즈 조직의 적격 IT 기술자가 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="39d78-105">다음 호환되는 Surface 디바이스에서 SSD를 제거하고 교체할 때 적격 IT 기술자가 사용하기 위한 권장 모범 사례에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="39d78-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="39d78-106">Surface Pro 7+</span></span>
- <span data-ttu-id="39d78-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="39d78-107">Surface Pro X</span></span>
- <span data-ttu-id="39d78-108">Surface Laptop 이동</span><span class="sxs-lookup"><span data-stu-id="39d78-108">Surface Laptop Go</span></span>
- <span data-ttu-id="39d78-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="39d78-109">Surface Laptop 3</span></span>
- <span data-ttu-id="39d78-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="39d78-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="39d78-111">장치를 열고 장치 구성 요소를 교체하면 감전, 장치 손상, 화재 및 개인 상해 위험 및 기타 위험을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="39d78-112">이러한 활동을 진행할 때는 항상 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="39d78-113">에 대한 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에서 식별된 안전 예방 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="39d78-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="39d78-114">"rSSD 제거 가이드 for Enterprise"에 지정된 안전 예방조치 및 절차를 따를 수 없는 경우 전문 지원을 받을 것을 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="39d78-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39d78-115">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="39d78-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39d78-116">이 문서에서는 "rSSD 제거 가이드 for Enterprise"에 설명된 일반 안전 주의 및 안전 정책 및 절차를 이해하고 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="39d78-117">SSD 제거 준비</span><span class="sxs-lookup"><span data-stu-id="39d78-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="39d78-118">최신 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="39d78-118">Install the latest updates</span></span> 

<span data-ttu-id="39d78-119">시작하기 전에 버전에 최신 Windows 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="39d78-120">시작 **설정**보안 & 로 이동하고 업데이트  >  \*\*\*\*  >  \*\*\*\* **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39d78-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="39d78-121">사용 가능한 모든 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-121">Install all available updates.</span></span>
3. <span data-ttu-id="39d78-122">장치에 액세스하는 데 필요한 암호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="39d78-123">BitLocker 관리</span><span class="sxs-lookup"><span data-stu-id="39d78-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="39d78-124">이 섹션에는 하드 디스크에 대한 암호화를 사용하도록 BitLocker 조직에 대한 권장 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="39d78-125">자세한 내용은 BitLocker [복구 가이드를 참조하세요.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="39d78-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="39d78-126">SSD BitLocker 교체 중에 암호화를 사용하지 않도록 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="39d78-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="39d78-127">SSD를 제거하고 교체하기 전에 디바이스를 암호화 해제할 수 있는 경우 다음 단계에 따라 장치를 BitLocker.</span><span class="sxs-lookup"><span data-stu-id="39d78-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="39d78-128">에서 **설정**를 **입력하고 BitLocker** 를 입력한 다음 관리 **BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="39d78-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="39d78-129">에서 **끄기 를 BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="39d78-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="39d78-130">디바이스 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="39d78-131">SSD를 BitLocker 교체하는 동안 암호화를 사용할 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="39d78-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="39d78-132">SSD 제거 및 교체 전에 장치가 암호화된 경우 다음 단계에 따라 BitLocker 복구 키를 생성하고 USB 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="39d78-133">에서 **설정**를 **BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="39d78-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="39d78-134">Manage **BitLocker**  > **Generate BitLocker Recovery Key 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39d78-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="39d78-135">USB 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="39d78-136">복구 키를 USB 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="39d78-137">USB 드라이브를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="39d78-138">디바이스 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="39d78-139">SSD 제거 및 바꾸기</span><span class="sxs-lookup"><span data-stu-id="39d78-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="39d78-140">에 대한 [rSSD](https://www.microsoft.com/download/100440)제거 가이드에 포함된 장치에 적절한 지침을 사용하여 SSD를 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="39d78-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="39d78-141">원래 SSD를 새 장치에 추가하고 새 장치를 유선 인터넷 연결에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="39d78-142">새 디바이스에서 전원을 니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-142">Power on the new device.</span></span> <span data-ttu-id="39d78-143">디바이스가 시작 중에 펌웨어 업데이트를 거치게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="39d78-144">SSD 제거 및 교체 후</span><span class="sxs-lookup"><span data-stu-id="39d78-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="39d78-145">암호화되지 않은 SDS 관리</span><span class="sxs-lookup"><span data-stu-id="39d78-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="39d78-146">전송 중에 SSD가 암호화되지 않은 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="39d78-147">로그인 **옵션**암호(왼쪽의 키 아이콘으로  >  \*\*\*\* 표시)로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="39d78-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="39d78-148">암호를 입력하고 2단계 인증 완료 보류 중으로 로그인합니다(해당하는 경우).</span><span class="sxs-lookup"><span data-stu-id="39d78-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="39d78-149">완전히 로그인한 후 계정 시작 \*\*\*\*  >  \*\*\*\*  >  **로그인으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="39d78-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="39d78-150">메시지가 표시될 때 암호를 사용하여 Windows Hello 및 PIN을 설정하여 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="39d78-151">SSD 제거 및 교체를 BitLocker 위해 장치가 사용되지 않도록 설정되어 있으며 교체 후 BitLocker 사용하려면 \*\*\*\* manage  >  **BitLocker Manage BitLocker**Resume BitLocker  >  **.**</span><span class="sxs-lookup"><span data-stu-id="39d78-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="39d78-152">Microsoft [Surface Diagnostic Toolkit(비즈니스용](surface-diagnostic-toolkit-for-business-intro.md) SDT)를 실행하여 전체 장치 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="39d78-153">정품 인증으로 Windows 정품 **인증을**설정  >  **확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="39d78-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="39d78-154">오류 메시지가 표시되어 있는 경우 문제 해결 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39d78-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="39d78-155">Office 앱 을 열고 \*\*\*\* Office 계정으로 이동한 \*\*\*\* 다음 오류 메시지를  >  \*\*\*\* 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="39d78-156">암호화된 SDS 관리</span><span class="sxs-lookup"><span data-stu-id="39d78-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="39d78-157">USB 드라이브에 저장된 복구 BitLocker 읽기 위해 두 번째 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="39d78-158">전송 중에 SSD가 암호화된 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="39d78-159">두 번째 장치에 BitLocker 복구 키가 포함된 USB 드라이브를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="39d78-160">Bitlocker .txt 포함된 파일 파일을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="39d78-161">원래 SSD가 BitLocker 디바이스에서 복구 키를 수동으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="39d78-162">BitLocker 복구 키를 성공적으로 입력한 후 로그인 옵션 \*\*\*\* 암호(왼쪽의 키 아이콘으로 표시)로  >  \*\*\*\* 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="39d78-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="39d78-163">암호를 입력하고 로그인하고 2단계 인증 완료를 보류하고 있습니다(해당하는 경우).</span><span class="sxs-lookup"><span data-stu-id="39d78-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="39d78-164">완전히 로그인한 후 계정 시작 \*\*\*\*  >  \*\*\*\*  >  **로그인으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="39d78-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="39d78-165">암호를 사용하여 다시 로그인한 다음 Hello를 Windows PIN을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="39d78-166">SSD 제거 및 BitLocker 쉽게 사용할 수 있도록 장치를 사용하지 않도록 설정한 경우 교체 후 BitLocker 사용하려면 설정 \*\*\*\*  >  **BitLocker**  >  **Manage BitLocker**Resume BitLocker  >  **.**</span><span class="sxs-lookup"><span data-stu-id="39d78-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="39d78-167">**[SDT를 실행하여](surface-diagnostic-toolkit-for-business-intro.md)** 전체 장치 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="39d78-168">정품 인증을 Windows **활성화를 설정**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39d78-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="39d78-169">오류 메시지가 표시되어 있는 경우 문제 해결 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="39d78-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="39d78-170">Office 계정의 상태를 확인하려면 Office 앱 을 열고 파일 \*\*\*\* **계정으로**이동하여 오류 메시지를  >  \*\*\*\* 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="39d78-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="39d78-171">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="39d78-171">Learn more</span></span>

- [<span data-ttu-id="39d78-172">rSSD Enterprise</span><span class="sxs-lookup"><span data-stu-id="39d78-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="39d78-173">BitLocker 복구 가이드</span><span class="sxs-lookup"><span data-stu-id="39d78-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="39d78-174">그래도 문제가 해결되지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="39d78-174">Still need help?</span></span> <span data-ttu-id="39d78-175">[으로 이동하여 Microsoft Community.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="39d78-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>