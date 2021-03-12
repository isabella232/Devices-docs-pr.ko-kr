---
title: Surface Hub 초기화 또는 복구
description: Surface Hub의 초기화 및 복구 프로세스를 설명하고 지침을 제공합니다.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 초기화, 복구
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406646"
---
# <a name="reset-or-recover-a-surface-hub"></a><span data-ttu-id="420e8-104">Surface Hub 초기화 또는 복구</span><span class="sxs-lookup"><span data-stu-id="420e8-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="420e8-105">이 문서에서는 Microsoft Surface Hub를 초기화하거나 복구하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="420e8-106">[Surface Hub를](#reset-a-surface-hub) 초기화하면 운영 체제가 마지막 누적 Windows 업데이트로 돌아가고 모든 로컬 사용자 파일 및 구성 정보가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="420e8-107">제거되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="420e8-108">디바이스 계정</span><span class="sxs-lookup"><span data-stu-id="420e8-108">The device account</span></span>
- <span data-ttu-id="420e8-109">디바이스의 로컬 관리자에 대한 계정 정보</span><span class="sxs-lookup"><span data-stu-id="420e8-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="420e8-110">도메인 가입 또는 Azure AD 가입 정보</span><span class="sxs-lookup"><span data-stu-id="420e8-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="420e8-111">MDM(모바일 장치 관리) 등록 정보</span><span class="sxs-lookup"><span data-stu-id="420e8-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="420e8-112">MDM 또는 설정 앱을 사용하여 설정한 구성 정보</span><span class="sxs-lookup"><span data-stu-id="420e8-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="420e8-113">[클라우드에서 Surface Hub를 복구하면](#recover-a-surface-hub-from-the-cloud) 이 정보도 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="420e8-114">또한 Surface Hub는 새 운영 체제 이미지를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="420e8-115">복구 프로세스에서 Surface Hub에 저장된 다른 정보를 보존할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="420e8-116">이러한 옵션을 모두 사용할 수 없는 [Surface Hub를](surface-hub-recovery-tool.md) 복구해야 하는 경우 Surface Hub 복구 도구에서 동일한 운영 체제 이미지가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <a name="reset-a-surface-hub"></a><span data-ttu-id="420e8-117">Surface Hub 초기화</span><span class="sxs-lookup"><span data-stu-id="420e8-117">Reset a Surface Hub</span></span>

<span data-ttu-id="420e8-118">다음과 같은 이유로 Surface Hub를 초기화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="420e8-119">새 모임 공간에 대해 장치를 다시 비우고 다시 구성하려는 경우</span><span class="sxs-lookup"><span data-stu-id="420e8-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="420e8-120">로컬에서 디바이스를 관리하는 방법을 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="420e8-121">장치 계정 또는 관리자 계정의 사용자 이름 또는 암호가 손실된 경우</span><span class="sxs-lookup"><span data-stu-id="420e8-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="420e8-122">업데이트를 설치하면 장치의 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="420e8-123">초기화 프로세스 동안 오랜 시간 동안 빈 화면이 표시되면 기다렸다가 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="420e8-124">장치 초기화 프로세스는 최대 6시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="420e8-125">프로세스가 완료될 때까지 Surface Hub를 끄거나 끄지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="420e8-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="420e8-126">프로세스를 중단하면 디바이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="420e8-127">장치를 다시 작동하려면 보증 서비스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="420e8-128">Surface Hub에서 **설정**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-128">On your Surface Hub, open **Settings**.</span></span>

   ![Surface Hub에 대한 설정 앱을 보여 주는 이미지입니다.](images/sh-settings.png)

2. <span data-ttu-id="420e8-130">보안 **및 & 업데이트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-130">Select **Update & Security**.</span></span>

   ![Surface Hub용 설정 & 보안 그룹 업데이트 표시 이미지.](images/sh-settings-update-security.png)

3. <span data-ttu-id="420e8-132">**복구를**선택하고 장치 **초기화에서** **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="420e8-133">디바이스를 초기화하기 전에 BitLocker 키를 사용할 수 있도록 하세요. 나중에 다시하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="420e8-134">자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="420e8-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="420e8-135">허브가 복구 파티션으로 다시 시작하면 BitLocker 키를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="420e8-136">이 프롬프트를 건너뛰면 재설정이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Surface Hub용 설정 앱의 디바이스 초기화 옵션을 보여 주는 이미지입니다.](images/sh-settings-reset-device.png)

   <span data-ttu-id="420e8-138">초기화 프로세스가 완료되면 Surface Hub가 첫 번째 실행 [프로그램을 다시](first-run-program-surface-hub.md) 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="420e8-139">초기화 프로세스에서 문제가 발생하면 Surface Hub를 다시 기존 운영 체제 이미지로 롤백한 다음 시작 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a><span data-ttu-id="420e8-140">클라우드에서 Surface Hub 복구</span><span class="sxs-lookup"><span data-stu-id="420e8-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="420e8-141">어떤 이유로 Surface Hub를 사용할 수 없는 경우 Microsoft 지원의 도움 없이 클라우드에서 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="420e8-142">Surface Hub는 클라우드에서 새 운영 체제 이미지를 다운로드하고 해당 이미지를 사용하여 운영 체제를 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="420e8-143">다음과 같은 상황에서는 이 유형의 복구 프로세스를 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="420e8-144">Surface Hub 또는 관련 계정이 불안정한 상태로 들어오고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="420e8-145">Surface Hub가 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="420e8-146">클라우드에서 **복구를** 사용하려면 개방형 인터넷 연결을 제공하는 유선 연결이 필요합니다(프록시 또는 기타 인증 프롬프트 없음).</span><span class="sxs-lookup"><span data-stu-id="420e8-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <a name="recover-a-surface-hub-in-a-bad-state"></a><span data-ttu-id="420e8-147">잘못된 상태의 Surface Hub 복구</span><span class="sxs-lookup"><span data-stu-id="420e8-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="420e8-148">장치 계정이 불안정한 상태가 되거나 관리자 계정에 문제가 발생하는 경우 설정 앱을 사용하여 클라우드 복구 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="420e8-149">장치 초기화 프로세스로 문제가 [](#reset-a-surface-hub) 해결되지 않는 경우 클라우드 복구 프로세스만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="420e8-150">Surface Hub에서 설정 **업데이트** 및 &gt; **보안 &** &gt; **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="420e8-151">클라우드에서 **복구에서**지금 다시 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![클라우드에서 복구](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a><span data-ttu-id="420e8-153">잠긴 Surface Hub 복구</span><span class="sxs-lookup"><span data-stu-id="420e8-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="420e8-154">드물지만 Surface Hub에서 세션 종료 시 사용자 및 앱 데이터를 정리하는 동안 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="420e8-155">이 경우 장치가 자동으로 다시 시작되고 작업을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="420e8-156">그러나 이 작업이 반복적으로 실패하면 장치가 자동으로 잠겨 사용자 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="420e8-157">잠금을 해제하려면 [](#reset-a-surface-hub) 디바이스를 초기화해야 합니다. 그렇지 않은 경우 클라우드에서 복구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="420e8-158">Surface Hub 아래쪽에서 전원 스위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="420e8-159">전원 스위치는 전원 코드 연결 옆에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="420e8-160">전원 스위치에 대한 자세한 내용은 Surface Hub 사이트 준비 [가이드(PDF)를 참조하세요.](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="420e8-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="420e8-161">Surface Hub가 시작 화면을 표시하는 동안 전원 스위치를 사용하여 Surface Hub를 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="420e8-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="420e8-162">전원 스위치를 사용하여 Surface Hub를 다시 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="420e8-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="420e8-163">디바이스가 시작하고 Surface Hub 로고 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="420e8-164">Surface Hub 로고 아래에 회전하는 점이 표시하면 전원 스위치를 사용하여 Surface Hub를 다시 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="420e8-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="420e8-165">3단계를 세 번 반복하거나 Surface Hub에 "자동 복구 준비" 메시지가 표시될 때까지 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="420e8-166">이 메시지를 표시하면 Surface Hub에 Windows RE 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

 
5. <span data-ttu-id="420e8-167">초기화 **를 선택하여 Windows를 다시 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-167">Select **Reset to re-install Windows**.</span></span> 
![다시 설치로 재설정](images/recover-from-cloud.png)

8. <span data-ttu-id="420e8-169">클라우드 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-169">Select **Cloud download.**</span></span> 

   ![클라우드 다운로드](images/recover-cloud-download.png)

>[!IMPORTANT]
><span data-ttu-id="420e8-171">다운로드할 수 **없습니다.를**나타내는 오류 메시지가 표시되면 **취소를** 선택하고 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="420e8-171">If you get an error message indicating **Unable to Download**, select **Cancel** and try again.</span></span>

9. <span data-ttu-id="420e8-172">드라이브 **완전 정리를 선택합니다.**  
![ 복구 및 완전히 정리된 드라이브</span><span class="sxs-lookup"><span data-stu-id="420e8-172">Select **Fully clean the drive.** 
![recover and fully clean drive</span></span>](images/recover-fully-clean-drive.png)

10. <span data-ttu-id="420e8-173">이 장치를 초기화할 준비가 **되나요?를 묻는 질문이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-173">You will be asked **Are you ready to reset this device?**.</span></span> <span data-ttu-id="420e8-174">**다시 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="420e8-174">Select **Reset**.</span></span> 
![복구 및 재설정 확인](images/recover-confirm-reset.png)

11. <span data-ttu-id="420e8-176">다운로드가 시작되면 복구 프로세스가 이 장치 **초기화 를 나타냅니다.**</span><span class="sxs-lookup"><span data-stu-id="420e8-176">The download begins and the recovery process indicates **Resetting this device**.</span></span> 
![진행 중으로 표시된 복구](images/recover-in-progress.png)

## <a name="contact-support"></a><span data-ttu-id="420e8-178">고객 지원</span><span class="sxs-lookup"><span data-stu-id="420e8-178">Contact Support</span></span>

<span data-ttu-id="420e8-179">질문이 있는 경우 또는 도움이 필요한 경우 지원 [요청을 만들 수 있습니다.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="420e8-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <a name="related-topics"></a><span data-ttu-id="420e8-180">관련 항목</span><span class="sxs-lookup"><span data-stu-id="420e8-180">Related topics</span></span>

[<span data-ttu-id="420e8-181">Microsoft Surface Hub 관리</span><span class="sxs-lookup"><span data-stu-id="420e8-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="420e8-182">Microsoft Surface Hub 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="420e8-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
