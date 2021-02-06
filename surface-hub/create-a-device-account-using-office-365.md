---
title: UI를 사용하여 디바이스 계정 만들기(Surface Hub v1)
description: 그래픽 사용자 인터페이스를 사용하려는 경우 Office 365 UI 또는 Exchange 관리 센터를 사용하여 Microsoft Surface Hub에 대한 디바이스 계정을 만들 수 있습니다.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: 장치 계정 만들기, Office 365 UI, Exchange 관리 센터, Microsoft 365 관리 센터, 비즈니스용 Skype, 모바일 장치 사서함 정책
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: 9e6d72dc2b36bb149ee09c2edab885c80e60ac14
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314471"
---
# <span data-ttu-id="3faf8-104">UI를 사용하여 디바이스 계정 만들기(Surface Hub v1)</span><span class="sxs-lookup"><span data-stu-id="3faf8-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="3faf8-105">이 페이지에는 원래 Surface Hub(v1)에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="3faf8-106">Surface Hub 2S의 경우 [Surface Hub 2S 디바이스 계정 만들기를 참조하세요.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="3faf8-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="3faf8-107">그래픽 사용자 인터페이스를 사용하려는 경우 [Office 365 UI](#create-device-acct-o365) 또는 [Exchange 관리 센터](#create-device-acct-eac)를 사용하여 Microsoft Surface Hub에 대한 디바이스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="3faf8-108">Office 365를 사용하여 디바이스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="3faf8-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="3faf8-109">[Microsoft 365 관리 센터에서 계정을 만드시다.](#create-device-acct-o365-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="3faf8-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="3faf8-110">[Microsoft Exchange 관리 센터에서 모바일 디바이스 사서함(ActiveSync) 정책 만들기](#create-device-acct-o365-mbx-policy)</span><span class="sxs-lookup"><span data-stu-id="3faf8-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="3faf8-111">[PowerShell을 사용하여 디바이스 계정 만들기 완료](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="3faf8-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="3faf8-112">[PowerShell을 사용하여 계정의 Exchange 속성 구성](#create-device-acct-o365-configure-exch-prop)</span><span class="sxs-lookup"><span data-stu-id="3faf8-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="3faf8-113">[비즈니스용 Skype와 함께 계정을 사용하도록 설정](#create-device-acct-o365-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="3faf8-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="3faf8-114">관리 센터에서 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="3faf8-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="3faf8-115">방문하여 Office 365에 로그인 https://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="3faf8-115">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="3faf8-116">Office 365 테넌트에 대한 관리자 자격 증명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="3faf8-117">이렇게 하면 Microsoft 365 관리 센터로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Microsoft 365 관리 센터.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="3faf8-119">관리 센터에서 왼쪽 패널의 **리소스로** 이동한 다음 장비가 있는 회의실을 **& 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3faf8-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![관리 & 회의실 및 장비 옵션](images/room-equipment.png)

4. <span data-ttu-id="3faf8-121">**추가**를 클릭하여 새 회의실 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="3faf8-122">계정에 대한 표시 이름 및 이메일 주소를 입력한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![새 회의실 계정 창 만들기](images/room-add.png)

5. <span data-ttu-id="3faf8-124">활성 사용자 목록에서 방금 만든 회의실 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="3faf8-125">오른쪽 패널에서 계정 속성과 여러 개의 선택적 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="3faf8-126">Surface Hub 로그인 과정에서 암호를 변경할 수 없기 때문에 **암호 재설정**을 클릭하여 암호를 변경하고 **이 사용자가 처음 로그인할 때 암호를 변경하도록 설정**을 선택 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="3faf8-127">**할당된 라이선스** 섹션에서 **편집**을 클릭한 다음 적합한 라이선스 옆에 있는 드롭다운 화살표를 클릭하여 세부 정보를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="3faf8-128">사용자 위치를 선택하고 라이선스 목록에서 **비즈니스용 Skype Online(플랜 2)** 을 전환하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="3faf8-129">라이선스는 조직에 따라 다를 수 있습니다(예: 사용자의 플랜이 플랜 2 또는 플랜 3일 수 있음).</span><span class="sxs-lookup"><span data-stu-id="3faf8-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="3faf8-130">Exchange 관리 센터에서 모바일 디바이스 사서함(ActiveSync) 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3faf8-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="3faf8-131">관리 센터의 왼쪽 패널에서 **ADMIN을**클릭한 다음 **Exchange를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3faf8-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![exchange 활성 사용자를 표시하는 관리 센터](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="3faf8-133">이렇게 하면 Surface Hub에 대한 사서함 설정을 만들고 설정할 수 있는 Exchange 관리 센터로 이동하는 다른 탭이 브라우저에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Exchange 관리 센터](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="3faf8-135">모바일 디바이스 사서함 정책을 만들려면 왼쪽 패널에서 **모바일**을 클릭한 다음 **모바일 디바이스 사서함 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="3faf8-136">Surface Hub에는 암호를 요구하지 않는 모바일 디바이스 사서함 정책을 가진 계정이 필요하므로 이 요구 사항에 맞는 기존 정책이 이미 있는 경우 해당 정책을 계정에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="3faf8-137">그렇지 않으면 다음 단계에 따라 Surface Hub 디바이스 계정에만 사용할 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Exchange 관리 센터 - 모바일 디바이스 사서함 정책 만들기](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="3faf8-139">새 Surface Hub 모바일 디바이스 사서함 정책을 만들려면 새 정책을 추가할 정책 목록 위에 있는 컨트롤에서 **+** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="3faf8-140">이름에는 이 정책을 다른 디바이스 계정과 구분하는 데 도움이 되는 이름을 입력합니다(예: *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="3faf8-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="3faf8-141">정책에서 디바이스의 암호 할당을 요구하지 않도록 **암호 필요**를 선택 취소된 상태로 유지하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![새 모바일 디바이스 정책을 보여 주는 이미지.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="3faf8-143">새 모바일 디바이스 사서함 정책을 만든 후 **Exchange 관리 센터**로 돌아가면 새 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Exchange 관리 센터의 새 모바일 디바이스 사서함 정책을 보여 주는 이미지](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="3faf8-145">PowerShell을 사용하여 디바이스 계정 만들기 완료</span><span class="sxs-lookup"><span data-stu-id="3faf8-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="3faf8-146">여기서 PowerShell을 통해 일부 구성을 설정하여 계정 만들기 프로세스를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="3faf8-147">이러한 PowerShell 스크립트에서 사용되는 cmdlet을 실행하려면 관리자 PowerShell 콘솔에 대해 다음을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="3faf8-148">Microsoft Online Services Sign-In IT 전문가용 도우미 RTW</span><span class="sxs-lookup"><span data-stu-id="3faf8-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="3faf8-149">Windows PowerShell용 Microsoft Azure Active Directory 모듈</span><span class="sxs-lookup"><span data-stu-id="3faf8-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="3faf8-150">비즈니스용 Skype Online, Windows PowerShell 모듈</span><span class="sxs-lookup"><span data-stu-id="3faf8-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="3faf8-151">Powershell에서 다음 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="3faf8-151">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="3faf8-152">온라인 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="3faf8-152">Connecting to online services</span></span>

1.  <span data-ttu-id="3faf8-153">관리자 권한으로 Windows PowerShell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-153">Run Windows PowerShell as Administrator.</span></span>

    ![Windows PowerShell을 시작하고 관리자 권한으로 실행하는 방법을 보여 주는 이미지](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="3faf8-155">자격 증명 개체를 만들고 비즈니스용 Skype Online에 연결하는 새 세션을 만든 다음 전역 테넌트 관리자 계정을 제공하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Windows PowerShell 자격 증명 요청 이미지](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="3faf8-157">Microsoft Online Services에 연결하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-157">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="3faf8-159">비즈니스용 Skype Online Services에 연결하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="3faf8-161">마지막으로, Exchange Online Services에 연결하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="3faf8-163">이제 방금 만든 비즈니스용 Skype Online 세션과 Exchange Online 세션을 가져와야 합니다. 그러면 로컬에서 사용할 수 있도록 Exchange 및 Skype 명령을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="3faf8-164">이 작업을 완료하는 데 시간이 좀 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-164">Note that this could take a while to complete.</span></span>

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="3faf8-166">온라인 서비스에 연결된 후 몇 개의 cmdlet을 더 실행하여 이 계정을 Surface Hub 디바이스 계정으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="3faf8-167">PowerShell을 사용하여 계정의 Exchange 속성 구성</span><span class="sxs-lookup"><span data-stu-id="3faf8-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="3faf8-168">이제 온라인 서비스에 연결되었으므로 디바이스 계정 설정을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="3faf8-169">디바이스 계정 메일 주소를 사용하여 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="3faf8-170">사서함 유형을 일반에서 회의실로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="3faf8-171">암호를 설정하고 회의실 사서함 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="3faf8-172">다양한 Exchange 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="3faf8-173">사용자 계정 암호의 사용 기간 제한이 없도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="3faf8-174">계정의 메일 주소를 입력하고 해당 값을 가진 변수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="3faf8-175">값을 저장하고 사서함에서 가져오려면</span><span class="sxs-lookup"><span data-stu-id="3faf8-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="3faf8-176">값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="3faf8-177">올바른 메일 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-177">You will see the correct email address.</span></span>

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="3faf8-179">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="3faf8-180">디바이스 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="3faf8-181">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![PowerShell cmdlet을 보여 주는 이미지](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="3faf8-183">암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="3faf8-184">자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3faf8-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="3faf8-185">비즈니스용 Skype와 함께 계정을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3faf8-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="3faf8-186">비즈니스용 Skype와 함께 디바이스 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="3faf8-187">비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 다음 필수 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="3faf8-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span><span class="sxs-lookup"><span data-stu-id="3faf8-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="3faf8-189">계획이 회의 기능을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="3faf8-190">Surface Hub에 Enterprise Voice 서비스 공급자를 사용하여 PSTN 전화 통신(PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online 독립 실행형 계획 3이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="3faf8-191">테넌트 사용자에게 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="3faf8-192">Surface Hub 계정에는 비즈니스용 Skype Online 독립 실행형 계획 2 또는 비즈니스용 Skype Online 독립 실행형 계획 3 라이선스가 필요하지만 Exchange Online 라이선스는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="3faf8-193">먼저 PC에서 원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="3faf8-194">비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="3faf8-195">사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="3faf8-196">Exchange 관리 센터를 사용하여 디바이스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="3faf8-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="3faf8-197">이 메서드는 On-프레미스 Active Directory에서 동기화하는 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="3faf8-198">Exchange 관리 센터를 사용하여 디바이스 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="3faf8-199">[Exchange 관리 센터를 사용하여 계정 및 사서함 만들기](#create-device-acct-exch-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="3faf8-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="3faf8-200">[Exchange 관리 센터에서 모바일 디바이스 사서함 정책 만들기](#create-device-acct-exch-mbx-policy)</span><span class="sxs-lookup"><span data-stu-id="3faf8-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="3faf8-201">[PowerShell을 사용하여 계정 구성](#create-device-acct-exch-powershell-conf)</span><span class="sxs-lookup"><span data-stu-id="3faf8-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="3faf8-202">[비즈니스용 Skype와 함께 계정을 사용하도록 설정](#create-device-acct-exch-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="3faf8-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="3faf8-203">Exchange 관리 센터를 사용하여 계정 및 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="3faf8-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="3faf8-204">Exchange 관리자 자격 증명을 사용하여 Exchange 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="3faf8-205">EAC(Exchange 관리 센터)에 있는 경우 왼쪽 패널에서 **받는 사람**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Exchange 관리 센터의 사서함을 보여 주는 이미지](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="3faf8-207">사서함 목록 위에 있는 컨트롤에서 **+** 를 선택하여 새 사서함을 만들고 **표시 이름**, **이름** 및 **사용자 로그온 이름**을 입력한 다음 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![새 사서함 만들기를 보여 주는 이미지](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="3faf8-209">Exchange 관리 센터에서 모바일 디바이스 사서함 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3faf8-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="3faf8-210">만든 계정에 정책을 만들고 할당하고 Exchange 2010을 사용하려면 EMC(Exchange 관리 콘솔)를 사용할 때 정책 만들기 및 정책 할당과 관련한 해당 정보를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="3faf8-211">Exchange 관리 센터로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-211">Go to the Exchange Admin Center.</span></span>

    ![Exchange 관리 센터를 보여 주는 이미지](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="3faf8-213">모바일 디바이스 사서함 정책을 만들려면 왼쪽 패널에서 **모바일**을 클릭한 다음 **모바일 디바이스 사서함 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="3faf8-214">Surface Hub에는 암호를 요구하지 않는 모바일 디바이스 사서함 정책을 가진 계정이 필요하므로 이 요구 사항에 맞는 기존 정책이 이미 있는 경우 해당 정책을 계정에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="3faf8-215">그렇지 않으면 다음 단계에 따라 Surface Hub 디바이스 계정에만 사용할 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Exchange 관리 센터를 사용하여 모바일 디바이스 사서함 정책 만들기를 보여 주는 이미지](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="3faf8-217">새 모바일 디바이스 계정 사서함 정책을 만들려면 새 정책을 추가할 정책 목록 위에 있는 컨트롤에서 **+** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="3faf8-218">이름에는 이 정책을 다른 디바이스 계정과 구분하는 데 도움이 되는 이름을 입력합니다(예: *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="3faf8-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="3faf8-219">정책이 암호로 보호되지 않아야 하므로 **암호 필요**를 선택 취소된 상태로 유지하고 **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![새 모바일 디바이스 사서함 정책을 보여 주는 이미지](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="3faf8-221">새 모바일 디바이스 사서함 정책을 만든 후 Exchange 관리 센터로 돌아가면 새 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Exchange 관리 센터의 새 모바일 디바이스 사서함 정책을 보여 주는 이미지](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="3faf8-223">PowerShell을 사용하지 않고 ActiveSync 정책을 적용하기 위해 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="3faf8-224">EAC에서 **받는 사람** &gt; **사서함**을 클릭하고 사서함을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Exchange 관리 센터를 보여 주는 이미지.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="3faf8-226">**세부 정보** 창에서 **전화 및 음성 기능**으로 스크롤한 다음 **세부 정보 보기**를 클릭하여 **모바일 디바이스 정보** 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![사서함 세부 정보를 보여 주는 이미지.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="3faf8-228">현재 할당된 모바일 디바이스 사서함 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="3faf8-229">모바일 디바이스 사서함 정책을 변경하려면 **찾아보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![현재 할당된 모바일 디바이스 사서함 정책을 보여 주는 이미지.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="3faf8-231">목록에서 적절한 모바일 디바이스 사서함 정책을 선택하고 **확인**, **저장**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![모바일 디바이스 사서함 정책 목록을 보여 주는 이미지.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="3faf8-233">PowerShell을 사용하여 계정 구성</span><span class="sxs-lookup"><span data-stu-id="3faf8-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="3faf8-234">이제 온라인 서비스에 연결되었으므로 디바이스 계정 설정을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="3faf8-235">디바이스 계정 메일 주소를 사용하여 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="3faf8-236">사서함 유형을 일반에서 회의실로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="3faf8-237">다양한 Exchange 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="3faf8-238">사용자 계정 암호의 사용 기간 제한이 없도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="3faf8-239">계정의 메일 주소를 입력하고 해당 값을 가진 변수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="3faf8-240">사서함에서 가져온 값을 저장하려면</span><span class="sxs-lookup"><span data-stu-id="3faf8-240">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="3faf8-241">다음을 실행하여 값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-241">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="3faf8-242">올바른 메일 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="3faf8-243">계정을 방 사서함으로 변환해야 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-243">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="3faf8-244">Surface Hub에서 디바이스 계정을 인증하려면 디바이스가 계정을 사용하여 ActiveSync를 통해 모임 정보를 가져오고 비즈니스용 Skype에 로그인할 수 있도록 회의실 사서함 계정을 사용하도록 설정하고 암호를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="3faf8-245">디바이스 계정에서 다양한 Exchange 속성을 설정하여 모임 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="3faf8-246">[Exchange 속성](exchange-properties-for-surface-hub-device-accounts.md) 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="3faf8-247">이제 AD에서 몇 가지 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="3faf8-248">이렇게 하려면 계정 별칭이 필요합니다("@" 앞에 오는 UPN의 일부).</span><span class="sxs-lookup"><span data-stu-id="3faf8-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="3faf8-249">먼저 AD에서 사용자를 사용하도록 설정해야 Surface Hub에서 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="3faf8-250">다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-250">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="3faf8-251">암호가 만료되지 않도록 하려는 경우 PowerShell cmdlet을 통해서도 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="3faf8-252">자세한 내용은 [암호 관리](password-management-for-surface-hub-device-accounts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3faf8-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="3faf8-253">비즈니스용 Skype와 함께 계정을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3faf8-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="3faf8-254">비즈니스용 Skype와 함께 디바이스 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="3faf8-255">비즈니스용 Skype를 사용하도록 설정하려면 사용자 환경이 다음 필수 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="3faf8-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span><span class="sxs-lookup"><span data-stu-id="3faf8-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="3faf8-257">계획이 회의 기능을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="3faf8-258">Surface Hub에 Enterprise Voice 서비스 공급자를 사용하여 PSTN 전화 통신(PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online 독립 실행형 계획 3이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="3faf8-259">테넌트 사용자에게 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="3faf8-260">Surface Hub 계정에는 비즈니스용 Skype Online 독립 실행형 계획 2 또는 비즈니스용 Skype Online 독립 실행형 계획 3 라이선스가 필요하지만 Exchange Online 라이선스는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="3faf8-261">먼저 PC에서 원격 PowerShell 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="3faf8-262">Surface Hub 계정 등록자 풀 검색</span><span class="sxs-lookup"><span data-stu-id="3faf8-262">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="3faf8-263">사용자 환경의 `RegistrarPool` 매개 변수에 사용할 값이 확실하지 않은 경우 다음 cmdlet을 사용하여 기존 비즈니스용 Skype 사용자에서 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. <span data-ttu-id="3faf8-264">비즈니스용 Skype 서버에 Surface Hub 계정을 사용하도록 설정하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3faf8-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```