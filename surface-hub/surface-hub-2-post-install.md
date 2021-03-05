---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성
description: 이 문서에는 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하기 위한 권장 사항이 포함되어 있습니다.
keywords: Surface Hub, Windows 10, 데스크톱, 설치, 구성
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393593"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="94dfb-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성</span><span class="sxs-lookup"><span data-stu-id="94dfb-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="94dfb-105">Windows 10 Pro 또는 Enterprise로 마이그레이션하는 설치 프로세스를 완료한 후 다음 단계를 수행하여 Surface Hub 2에서 앱 및 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="94dfb-106">이 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하려면 이러한 단계를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="94dfb-107">이러한 단계를 수행할 때 유선 또는 무선 키보드와 마우스를 사용하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="94dfb-108">시스템 설정 구성</span><span class="sxs-lookup"><span data-stu-id="94dfb-108">Configure system settings</span></span>

1. <span data-ttu-id="94dfb-109">디바이스에서 로컬 관리자 권한이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="94dfb-110">Azure AD 가입 장치에서 Azure AD 조인을 수행하는 사용자가 로컬 관리자 그룹에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="94dfb-111">Azure AD 전역 관리자 및 Azure AD 장치 관리자도 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 로컬 </a> 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="94dfb-112">명령 프롬프트에 **net localgroup 관리자를** 입력하여 로컬 관리자 권한이 있는 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="94dfb-113">이름(예: **username-SHub-Desktop)을**사용하여 디바이스 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="94dfb-114">시작 \*\*\*\*  >  **설정 계정**설정  >  \*\*\*\*  >  **동기화를 선택하고** 설정 동기화를 **끄면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="94dfb-115">여기에 사용된 설정은 최상의 큰 화면 터치 환경을 사용하도록 설정되어 있으므로 다른 장치를 동기화하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="94dfb-116">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="94dfb-117">터치 키보드 및 터치 패드 사용</span><span class="sxs-lookup"><span data-stu-id="94dfb-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="94dfb-118">시작 **설정**장치 입력을 선택하고 태블릿 모드가 아니고 키보드가 연결되어 있지 않은 경우 터치 키보드  >  \*\*\*\*  >  \*\*\*\*  >  \*\*\*\* **표시를** 니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="94dfb-119">작업 표시줄을 누르거나 마우스 오른쪽 단추로 클릭한 다음 **터치** 키보드 단추 표시 및 터치 패드 단추 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="94dfb-120">터치 키보드는 직접 사용자 입력에 유용하며, 가상 터치 패드는 정확한 선택, 화면 팁 마우스로 누르기 또는 마우스 오른쪽 단추 클릭을 위한 누르기 대신 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="94dfb-121">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-121">See the following example.</span></span>

      ![터치 설정](images/touch.png)

3. <span data-ttu-id="94dfb-123">터치 키보드를 QWERTY 및 부동으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="94dfb-124">터치 **키보드를** 표시하려면 작업 표시줄에서 키보드 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="94dfb-125">터치 키보드에서 왼쪽 위 모서리에 있는 키보드 아이콘을 선택하여 키보드 설정을 니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="94dfb-126">QWERTY를 사용하도록 설정하려면 위쪽 행의 마지막 키보드 유형 옆에 있는 마지막 옵션을 선택하고 두 번째 행의 마지막 옵션을 선택하여 부동을 사용하도록 설정하면 이 큰 화면에서 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="94dfb-127">다음 예를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-127">See the following examples.</span></span>

       ![키보드 설정](images/kbd.png)
 
4. <span data-ttu-id="94dfb-129">소프트 키보드 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="94dfb-130">터치 **키보드에서** 설정 아이콘을 선택하거나 입력 설정을 검색하여 **를 니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![소프트 키보드 설정](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="94dfb-132">맞춤법 검사, 입력 및 터치 키보드의 모든 옵션을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="94dfb-133">다음 예제에서는 옵션을 탐색하고 선택하는 데 유용한 트랙 패드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="94dfb-134">화면 키보드를 사용하여 Microsoft Store를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![트랙 패드 사용](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="94dfb-136">키보드 Bluetooth 마우스 구성(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="94dfb-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="94dfb-137">디바이스를 기본 Windows 장치로 사용하거나 입력 또는 정밀도 작업을 위해 자주 사용하는 경우 키보드와 마우스를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="94dfb-138">Surface Hub 디바이스가 PC에 가까운 경우 테두리 없이 마우스를 사용하여 Surface Hub와 PC 간에 원활하게 이동할 <a href="https://aka.ms/mm" target="_blank"> </a> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="94dfb-139">자세한 내용은 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Garage: Mouse without Borders에서 Microsoft 다운로드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="94dfb-140">작업 표시줄 레이아웃의 예</span><span class="sxs-lookup"><span data-stu-id="94dfb-140">Example of Taskbar layout</span></span>

<span data-ttu-id="94dfb-141">아래 단계를 완료하여 Windows 10 Professional 또는 Enterprise용 Surface Hub 2를 설정/구성한 후, 각 응용 프로그램의 빠른 원터치 시작을 위해 가장 많이 사용하는 응용 프로그램을 작업 표시줄에 고정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="94dfb-142">다음은 작업 표시줄이 어떻게 표시될 수 있는지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-142">Below is an example of what your taskbar could look like:</span></span>

 ![작업 표시줄 레이아웃](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="94dfb-144">설치된 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="94dfb-144">Update installed apps</span></span>

<span data-ttu-id="94dfb-145">설치된 모든 스토어 앱을 업데이트하는 경우:</span><span class="sxs-lookup"><span data-stu-id="94dfb-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="94dfb-146">Microsoft Store 앱을 열고 오른쪽 위 모서리에서 더 많은 타원 보기를 선택합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="94dfb-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="94dfb-147">다운로드 **및 업데이트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="94dfb-148">업데이트 **다운로드 선택**</span><span class="sxs-lookup"><span data-stu-id="94dfb-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="94dfb-149">모든 Windows 업데이트 검색 및 설치</span><span class="sxs-lookup"><span data-stu-id="94dfb-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="94dfb-150">Windows 10 Professional 또는 Windows 10 Enterprise로 마이그레이션한 후 설치할 수 있는 서비스 및 기능 업데이트가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="94dfb-151">설정 업데이트 **&** 보안 >  >  **이동한** 다음 업데이트 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="94dfb-152">업데이트가 있는 경우 업데이트를 설치하고 다시 시작한 후 다음 알림이 표시될 때까지 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Windows 업데이트 '최신 정보' 알림](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="94dfb-154">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="94dfb-154">OneDrive for Business</span></span>

<span data-ttu-id="94dfb-155">비즈니스용 OneDrive를 사용하여 모든 작업 장치 간에 도구, 로그 및 기타 파일을 쉽게 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="94dfb-156">OneDrive를 사용하면 랩톱, Surface Hub 데스크톱 및 Intune에서 관리하는 모바일 장치 간에 작업 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="94dfb-157">모든 장치에서 파일을 편집할 수 있으며 모든 네트워크 연결 장치가 변경 내용으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="94dfb-158">Surface Hub SSD(128GB)의 크기를 고려하여 Surface Hub 데스크톱 디바이스에서 OneDrive를 구성하는 경우 기본 구성은 파일을 온라인에서 유지하고 파일을 사용할 때 파일을 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="94dfb-159">필요한 경우만 파일을 다운로드하도록 OneDrive를 \*\*\*\* 구성하려면 파일 필요 시 파일 관리 설정을 공간을 절약하고 파일을 사용할 때 파일을 **다운로드하도록 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="94dfb-160">자세한 내용은 Windows에서 쿼리 및 필요한 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 파일 제공 상태 설정 을 참조하세요. </a></span><span class="sxs-lookup"><span data-stu-id="94dfb-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive 설정](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="94dfb-162">이러한 단계를 반복하여 개인 OneDrive를 구성할 수도 있지만 드라이브 공간을 절약하고 필요할 때만 파일을 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="94dfb-163">SharePoint 및 Teams</span><span class="sxs-lookup"><span data-stu-id="94dfb-163">SharePoint and Teams</span></span>

<span data-ttu-id="94dfb-164">SharePoint 및 Teams 채널 파일은 OneDrive 동기화 엔진을 사용하여 랩톱 및 Surface Hub와 같은 데스크톱 장치와 로컬로 동기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="94dfb-165">OneDrive 동기화 앱을 사용하여 내부 회사 파일을 로컬 드라이브에 동기화하려면</span><span class="sxs-lookup"><span data-stu-id="94dfb-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="94dfb-166">SharePoint 사이트로 이동하여 로컬 장치에서 보거나 편집하는 데 관심이 있는 파일의 최상위 문서 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="94dfb-167">SharePoint **리본 메뉴** 위쪽의 동기화 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="94dfb-168">팝업에서 \*\*\*\* 열기에서 선택 **이 사이트가 Microsoft OneDrive를 열려고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="94dfb-169">작업 표시줄 오른쪽 아래에 있는 OneDrive 아이콘을 선택하여 SharePoint 파일이 로컬 드라이브와 동기화하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="94dfb-170">파일을 온라인에서 유지하고 파일을 사용할 때만 다운로드할 수 있는 구성이 설정되어 있는지 확인:</span><span class="sxs-lookup"><span data-stu-id="94dfb-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="94dfb-171">파일 탐색기를 니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="94dfb-172">SharePoint 이름을 찾아 마우스 오른쪽 단추로 클릭합니다. 예: \*\*Contoso \<SharePoint Document Folder Name\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="94dfb-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="94dfb-173">공간을 **비우기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="94dfb-174">상태 열에는 파일 및 폴더의 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="94dfb-175">자세한 내용은 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> OneDrive 동기화 클라이언트와 SharePoint 파일 동기화를 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="94dfb-176">Teams 채널 파일은 버전 기록 및 로컬 데스크톱 장치와 동기화를 포함하여 동일한 SharePoint 문서 기능을 모두 사용하여 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="94dfb-177">Teams 채널 파일을 동기화하려면</span><span class="sxs-lookup"><span data-stu-id="94dfb-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="94dfb-178">관심 있는 Teams 채널로 이동하여 맨 위에 있는 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="94dfb-179">그런 다음 **동기화를 선택합니다.** 파일이 동기화를 시작하고 Desktop \ Contoso \ 의 파일 \*\*탐색기에서 \<name of the Teams Channel\> 표시됩니다. \*\*</span><span class="sxs-lookup"><span data-stu-id="94dfb-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="94dfb-180">SharePoint 사이트를 동기화하는 데 사용한 절차와 동일한 절차를 사용하여 파일을 클라우드에 보관하고 파일을 사용할 때만 다운로드하고 Teams 채널 이름의 파일 탐색기를 \*\*\*\* 탭하거나 마우스 오른쪽 단추로 클릭한 다음 공간을 비우기 를 선택하여 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="94dfb-181">Surface Hub 펜 설정</span><span class="sxs-lookup"><span data-stu-id="94dfb-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="94dfb-182">Surface Hub Bluetooth 페어링</span><span class="sxs-lookup"><span data-stu-id="94dfb-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="94dfb-183">펜을 페어링하여 펜 펌웨어를 최신으로 유지하고, 펜 바로 가기를 설정하고, Bluetooth 장치 설정 페이지 또는 Surface 앱에서 배터리 충전 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="94dfb-184">설정 **장치**  >  **시작을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="94dfb-185">추가 **Bluetooth 또는 기타 장치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="94dfb-186">를 **Bluetooth.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="94dfb-187">펜 tail 단추를 제거하고 흔들어 배터리 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="94dfb-188">캡을 다시 넣은 다음 페어링 LED가 깜박일 때까지 캡을 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="94dfb-189">Surface Hub Bluetooth **Surface Hub 2 펜을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="94dfb-190">페어링 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="94dfb-191">페어링에 실패하면 펜을 다시 페어링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="94dfb-192">그래도 문제가 해결되지 않는 경우 펜이 화이트보드 응용 프로그램에서 작동하는지 확인하여 배터리가 충전되어 있는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="94dfb-193">그렇지 않은 경우 배터리를 교체한 다음 펜을 다시 페어링해 니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="94dfb-194">필요한 경우 장치를 다시 시작한 다음 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="94dfb-195">**펜 바로 가기 설정** Surface Hub 펜에는 "tail click"이라고도 하는 바로 가기 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="94dfb-196">바로 가기를 구성하려면 앞에서 설명한 대로 펜을 먼저 페어링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="94dfb-197">펜을 검색하고 **Windows ink & 펜을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="94dfb-198">페이지 아래쪽에서 다음과 같이 대화 상자를 여는 펜 바로 가기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![펜 바로 가기](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="94dfb-200">카메라 구성</span><span class="sxs-lookup"><span data-stu-id="94dfb-200">Camera configuration</span></span>

<span data-ttu-id="94dfb-201">디바이스의 위쪽 또는 어느 쪽에나 카메라를 탑재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="94dfb-202">카트 대신 데스크톱 독립형 허브를 사용하거나 허브와 가까운 위치에 카메라를 탑재하여 카메라 각도를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="94dfb-203">카메라가 자동 회전하지 않습니다. 따라서 카메라를 수동으로 회전하려면 2mm 16진수 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="94dfb-204">카메라를 사이드 마운트하고 카메라를 수동으로 회전하는 방법에 대한 자세한 내용은 Surface Hub 2S 카메라 렌즈 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 방향을 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="94dfb-205">Windows Hello 구성</span><span class="sxs-lookup"><span data-stu-id="94dfb-205">Windows Hello configuration</span></span>

<span data-ttu-id="94dfb-206">Windows 10 Enterprise를 실행하는 Surface Hub 2S는 생체 인식 Windows Hello 옵션뿐만 아니라 Win32 데스크톱 응용 프로그램의 전체 제품군을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="94dfb-207">Surface Hub 2 지문 판독기 액세서리를 장치의 모든 USB-C 포트에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="94dfb-208">Surface Hub 2 지문 판독기를 주문하거나 기술 사양을 보기 위해서는 (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2를 </a> 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="94dfb-209">지문 판독기를 삽입한 \*\*\*\* 후 시작 설정 계정 로그인  >  \*\*\*\*  >  \*\*\*\*  >  **옵션**Windows  >  **Hello Fingerprint를** 선택하여 지문을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="94dfb-210">얼굴 인식에 Windows Hello 인증 장치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="94dfb-211">Surface Hub 2S 카메라는 Windows Hello 얼굴 인식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="94dfb-212">작업 표시줄에서 잠금 화면 바로 가기 아이콘 사용</span><span class="sxs-lookup"><span data-stu-id="94dfb-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="94dfb-213">작업 표시줄에 Windows-L 바로 가기 키와 비슷한 원터치 화면 잠금을 사용할 수 있는 아이콘을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="94dfb-214">바탕 화면을 탭하고 누르거나 마우스 \*\*\*\* 오른쪽 단추로 클릭하고 새 바로 가기  >  \*\*\*\*  >  **찾아보기**  >  **데스크톱**  >  **확인 다음을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="94dfb-215">내 **PC**잠금과 같은 바로 가기 이름을 입력한 다음 마친 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="94dfb-216">바탕 화면에서 새로 만든 바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="94dfb-217">바로 **가기 탭의** 대상 \*\*\*\* 필드에 **Rundll32.exe User32.dll,LockWorkStation을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="94dfb-218">아이콘 **변경 단추를** 선택하고C:\Windows\System32\imageres.dll찾아 \*\* 사용할 \*\* 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="94dfb-219">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-219">See the following example:</span></span>

    ![아이콘 선택](images/lock.png)
    
1.  <span data-ttu-id="94dfb-221">확인을 **선택하여** 바로 가기를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="94dfb-222">바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 작업 표시줄에 **고정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="94dfb-223">잠금 바로 가기를 작업 표시줄에 고정한 후 바탕 화면에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="94dfb-224">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="94dfb-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="94dfb-225">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="94dfb-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="94dfb-226">Microsoft Whiteboard를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="94dfb-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="94dfb-227">작업 **표시줄 오른쪽** 아래에서 Windows Ink 작업 영역 아이콘을 선택하고 **화이트보드를 다운로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Ink 작업 영역](images/ink.png) 

<span data-ttu-id="94dfb-229">또는 Microsoft Store에서 화이트보드를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="94dfb-230">Microsoft Store 앱을 열고 **화이트보드를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="94dfb-231">여러 **장치에서 로그인하고** 사용 하여 감사합니다.를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="94dfb-232">화이트보드를 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="94dfb-233">Surface 앱</span><span class="sxs-lookup"><span data-stu-id="94dfb-233">Surface app</span></span>

1. <span data-ttu-id="94dfb-234">Microsoft Store에서 Surface 를 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="94dfb-235">필터에서 **사용 가능을** 모든 **장치로 설정**</span><span class="sxs-lookup"><span data-stu-id="94dfb-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="94dfb-236">Surface 앱을 **설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-236">Install the **Surface** app.</span></span> <span data-ttu-id="94dfb-237">나열된 첫 번째 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-237">This should be the first app listed.</span></span> <span data-ttu-id="94dfb-238">앱을 설치하려면 MSA를 스토어에 연결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="94dfb-239">Surface 앱을 **작업** 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="94dfb-240">캡처 및 스케치</span><span class="sxs-lookup"><span data-stu-id="94dfb-240">Snip & Sketch</span></span>

1. <span data-ttu-id="94dfb-241">스케치 **앱을 & Snip** 앱을 열고 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="94dfb-242">오른쪽 위 모서리에서 타원을 선택한 다음 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="94dfb-243">**설정에서**클립보드에 **자동**복사, 스니프 저장 및 여러 창(선택 사항)을 **니다.** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="94dfb-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="94dfb-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="94dfb-244">Microsoft Office</span></span>

1. <span data-ttu-id="94dfb-245">Office <a href="https://portal.office.com/account#installs" target="_blank"> 포털을 </a> 열고 원하는 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="94dfb-246">원하는 Office 응용 프로그램을 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="94dfb-247">Outlook이 설치된 경우 Outlook OST를 설정하여 지난 2주 동안의 캐시만 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="94dfb-248">이렇게 하면 디스크 사용량 및 설정 시간이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="94dfb-249">파일 \*\*\*\*  >  **계정 설정을 선택하고** 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="94dfb-250">**변경을** 선택하고 캐시된 **Exchange** 모드 사용 슬라이더를 14일로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="94dfb-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94dfb-251">Microsoft Teams</span></span>

1. <span data-ttu-id="94dfb-252"><a href="https://teams.microsoft.com/downloads" target="_blank">Microsoft Teams를 다운로드하여 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="94dfb-253">응용 프로그램을 자동으로 시작하도록 설정을 구성합니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="94dfb-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="94dfb-254">작업 표시줄에 Teams를 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="94dfb-255">방해를 방지하기 위해 디바이스에서 Teams 알림을 줄이는 것이 좋습니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="94dfb-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams 알림](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="94dfb-257">앱 연결</span><span class="sxs-lookup"><span data-stu-id="94dfb-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94dfb-258">Windows 10 버전 2004 이상에서는 Miracast를 사용하여 무선으로 투영하기 위한 연결 앱이 기본적으로 설치되지 않지만 선택적 기능으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="94dfb-259">Windows 버전 2004 이상을 설치(또는 업데이트)한 경우 설정에서 이 PC에 투영 화면에 다음이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![이 PC에 프로젝트](images/sh2-project.png) 


1. <span data-ttu-id="94dfb-261">"이 PC에 투영" 설정 페이지에서 앱을 설치하려면 선택적 기능 추가 기능을 선택한 다음 무선 디스플레이 앱을 \*\*\*\*  >  \*\*\*\* **설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="94dfb-262">확인이면 일부 Windows 및 Android 장치에서 이 PC에 프로젝트할 수 **있습니다.** 아래에서 다음을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="94dfb-263">**장치가 회사** 네트워크에 없는 경우 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="94dfb-264">그렇지 않은 경우 보안 **네트워크의 모든 곳에서 사용 가능을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="94dfb-265">이 **PC에 프로젝트 요청에서**첫 **번째 시간만 을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="94dfb-266">**페어링을 위해 PIN 필요에서**사용 안 **을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="94dfb-267">그런 다음 앱을 시작하고 작업 표시줄에 고정하기 위해 연결을 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="94dfb-268">앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-268">Open the app.</span></span> <span data-ttu-id="94dfb-269">앱이 열려 있는 동안 작업 표시줄에서 앱 연결 아이콘을 마우스 오른쪽 단추로 클릭하고 작업 표시줄에 **고정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="94dfb-270">그런 다음 연결 앱을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-270">Then close the Connect app.</span></span> <span data-ttu-id="94dfb-271">앱이 한 번 이상 실행되지 않으면 이 **PC에** 대한 Project가 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="94dfb-272">회사 네트워크에 없는 경우 권장되는 구성:</span><span class="sxs-lookup"><span data-stu-id="94dfb-272">Recommended configuration when not on the corporate network:</span></span>

![가정의 설정](images/project1.png)

<span data-ttu-id="94dfb-274">회사 네트워크에서 권장되는 구성:</span><span class="sxs-lookup"><span data-stu-id="94dfb-274">Recommended configuration on the corporate network:</span></span>

![직장의 설정](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="94dfb-276">사용자 휴대폰</span><span class="sxs-lookup"><span data-stu-id="94dfb-276">Your Phone</span></span>

<span data-ttu-id="94dfb-277">휴대폰 **앱은** 기본적으로 Windows 10에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="94dfb-278">이 패키지가 없는 경우 Windows 스토어에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="94dfb-279">앱을 설정하는 방법에 대한 자세한 내용은 Windows 10에서 휴대폰을 설정하고 PC와 휴대폰 간에 데이터를 동기화하는 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 방법을 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="94dfb-280">Windows 10에서 휴대폰 앱의 일반적인 문제를 해결하는 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 방법도 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94dfb-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="94dfb-281">멋진 영역</span><span class="sxs-lookup"><span data-stu-id="94dfb-281">Fancy Zones</span></span>


<span data-ttu-id="94dfb-282">**멋진 영역은** <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub의 PowerToys라는 도구 </a> 모음의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="94dfb-283">디스플레이에서 고정 레이아웃("영역")을 정의한 다음 각 영역에서 실행할 앱을 선택하여 Surface Hub 2의 화면 공간 활용에 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="94dfb-284">[PowerToys Wiki에는](https://github.com/microsoft/PowerToys/wiki) [FancyZones를](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)포함하여 각 도구를 사용 및 사용자 지정하는 방법에 대한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="94dfb-285">고급 수준 – PowerToys를 설치한 후 사용자 지정 레이아웃을 선택하거나 만든 다음 Shift 키를 아래로 놓고 키보드 키를 끌어서 실행 중인 앱을 특정 영역으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="94dfb-286">이 Bluetooth 또는 USB 키보드와 마우스를 사용하면 도움이 되거나 화면 터치 키보드와 터치 패드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="94dfb-287">전원 토이 팁</span><span class="sxs-lookup"><span data-stu-id="94dfb-287">Power toys tips</span></span>**
- <span data-ttu-id="94dfb-288">GitHub에서 PowerToys 릴리스 업데이트의 전자 메일 알림을 받으려면 페이지 맨 위에 있는 "등록" 단추를 [클릭합니다.](https://github.com/microsoft/PowerToys/releases)</span><span class="sxs-lookup"><span data-stu-id="94dfb-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="94dfb-289">PowerToys가 설치되면 PowerToys 설정 자동으로 업데이트 다운로드를 구성하여 Windows 알림을 수신하거나 \*\*\*\* 최신 업데이트를 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="94dfb-290">PowerToys 설정으로 이동하려면 작업 표시줄에서 캐래트 실행 앱을 선택한 다음 메뉴가 나타날 때까지 PowerToys 아이콘을 마우스 오른쪽 단추로 클릭하거나 누르고 있습니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="94dfb-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="94dfb-291">"설정"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-291">Select “Settings”.</span></span>
- <span data-ttu-id="94dfb-292">PowerToys 설정 페이지의 맨 아래에서 자동으로 업데이트 **다운로드를 켜십시오.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="94dfb-293">업데이트가 릴리스된 경우 업데이트를 설치할 때의 옵션을 표시하는 Windows 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="94dfb-294">Edge Chromium 브라우저</span><span class="sxs-lookup"><span data-stu-id="94dfb-294">Edge Chromium browser</span></span>

<span data-ttu-id="94dfb-295">새 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 브라우저를 다운로드하여 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="94dfb-296">Surface Hub 하드웨어 진단 도구</span><span class="sxs-lookup"><span data-stu-id="94dfb-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="94dfb-297"><a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank">Surface Hub 하드웨어 진단 </a> 도구는 Microsoft Store에서 무료로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="94dfb-298">이 도구는 Surface Hub가 최상의 기능을 수행하는지 확인하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="94dfb-299">펌웨어가 최신 버전인지와 올바르게 구성된지 확인하는 테스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="94dfb-300">대화형 테스트를 통해 필수 기능이 예상대로 작동하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="94dfb-301">문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="94dfb-302">링크를 클릭하여 Microsoft Store에서 설치한 다음 응용 프로그램을 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="94dfb-303">추가 설정</span><span class="sxs-lookup"><span data-stu-id="94dfb-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="94dfb-304">펜 tail을 선택하여 화이트보드 시작</span><span class="sxs-lookup"><span data-stu-id="94dfb-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="94dfb-305">펜을 **검색하고** **Windows & 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="94dfb-306">페이지 아래쪽의 펜 바로 \*\*\*\* 가기에서 \*\*\*\* 한 번 선택을 **Microsoft Whiteboard로 설정**</span><span class="sxs-lookup"><span data-stu-id="94dfb-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="94dfb-307">전원 관리</span><span class="sxs-lookup"><span data-stu-id="94dfb-307">Power management</span></span>

<span data-ttu-id="94dfb-308">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise를 사용하여 최상의 환경을 얻을 수 있는 몇 가지 전원 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="94dfb-309">여기에는 화면 및 PC 시간 제한과 기본 제공 Doppler(휴먼 현재 상태 감지), 화면 보호기 및 암호 보호와 상호 작용하는 방법, 랩톱/데스크톱 사용자를 위한 그룹 정책 전원 설정을 전달하는 방법에 대한 적절한 방법도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="94dfb-310">Surface Hub 2의 Windows 10 Pro 또는 Enterprise는 터치, 마우스 및 키보드 동작뿐만 아니라 기본 제공 Doppler(휴먼 점유 감지)로 화면이 절전되지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="94dfb-311">휴먼 점유 검색은 기본적으로 사용하도록 설정되어 있지만, 원하는 경우 초기 마이그레이션의 일부로 Surface UEFI 구성 도구에서 장치 옵션을 전환하거나 이후 UEFI 구성 패키지를 구축 및 적용하여 UEFI에서 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="94dfb-312">전원 관리: 화면 및 PC 절전 설정</span><span class="sxs-lookup"><span data-stu-id="94dfb-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="94dfb-313">시작 \*\*\*\*  >  **설정**  >  **시스템**  >  **전원 & 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="94dfb-314">전원 모드 슬라이더를 최상의 **성능으로 설정**</span><span class="sxs-lookup"><span data-stu-id="94dfb-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="94dfb-315">화면 및 절전 모드 값을 기본 설정으로 구성하고 움직임이 감지될 때 디바이스를 깨우는 Doppler 현재 상태 검색을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="94dfb-316">따라서 모범 사례로 화면이 **2시간** 후에 꺼지기로 설정하고 PC에서 4시간 후에 꺼지기로 **설정하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="94dfb-317">전원 관리: 화면 보호기</span><span class="sxs-lookup"><span data-stu-id="94dfb-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="94dfb-318">잠금 화면 **및** 잠금 화면 **설정을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="94dfb-319">화면 **시간 제한 설정 및** 화면 **보호기** 설정을 기본 설정으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="94dfb-320">권장되는 기본값은:</span><span class="sxs-lookup"><span data-stu-id="94dfb-320">Recommended default values are:</span></span>

   - <span data-ttu-id="94dfb-321">화면 보호기에서 (없음) 또는 선택한 화면 보호기입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="94dfb-322">15분까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="94dfb-323">다시 시작 시 로그온 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="94dfb-324">전원 관리: 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="94dfb-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="94dfb-325">다음 절차를 수행하기 전에 IT 부서에 승인을 요청하여 전역 전원 관리 정책에서 Surface Hub 2S 장치를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="94dfb-326">일부 전원 관리 설정은 현재 상태 검색 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="94dfb-327">소프트웨어 **센터를 검색한** 후 을 .</span><span class="sxs-lookup"><span data-stu-id="94dfb-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="94dfb-328">옵션을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-328">Select **Options**.</span></span>

3. <span data-ttu-id="94dfb-329">전원 관리를 **확장하고** 이 컴퓨터에 IT 부서의 전원 설정 **적용 안 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![소프트웨어 설정](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="94dfb-331">저장소 센스</span><span class="sxs-lookup"><span data-stu-id="94dfb-331">Storage Sense</span></span>

<span data-ttu-id="94dfb-332">Surface Hub 2에는 로컬 저장소용 128GB SSD가 있으므로 일반 사용 중에 저장소 저장 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="94dfb-333">저장소 센스를 구성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="94dfb-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="94dfb-334">시스템 설정 **에서**저장소 설정 **을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="94dfb-335">**설정에서**저장소 **센스 켜기 를** 선택하여 저장소 설정 페이지를 **열** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="94dfb-336">저장소 센스를 **켜기**</span><span class="sxs-lookup"><span data-stu-id="94dfb-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="94dfb-337">저장소 **센스** 구성을 선택하거나 지금 실행하고 제한된 드라이브 공간으로 인해 파일을 가능한 한 많이 온라인으로 유지하도록 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="94dfb-338">권장 설정:</span><span class="sxs-lookup"><span data-stu-id="94dfb-338">Recommended settings:</span></span>

- <span data-ttu-id="94dfb-339">저장소 센스 = 매일 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="94dfb-340">앱에서 사용하지 않는 임시 파일 삭제 = 최소 14일마다 삭제</span><span class="sxs-lookup"><span data-stu-id="94dfb-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="94dfb-341">30일 넘게 다운로드한 경우 내 다운로드 폴더에서 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="94dfb-342">OneDrive: = 30일 이상 열지 않은 경우 콘텐츠가 온라인 전용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="94dfb-343">태블릿 모드</span><span class="sxs-lookup"><span data-stu-id="94dfb-343">Tablet mode</span></span>

<span data-ttu-id="94dfb-344">접근성 요구에 필요한 경우 태블릿 모드를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="94dfb-345">소리 설정</span><span class="sxs-lookup"><span data-stu-id="94dfb-345">Sound settings</span></span>

1. <span data-ttu-id="94dfb-346">소리 설정을 **검색하고** 이 페이지를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="94dfb-347">오른쪽의 소리 **제어판을** 선택하고 소리 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="94dfb-348">프로그램 **이벤트에서** **장치 연결** 및 장치 연결 **끊기를** 없음으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="94dfb-349">침묵 알림</span><span class="sxs-lookup"><span data-stu-id="94dfb-349">Silence notifications</span></span>

1. <span data-ttu-id="94dfb-350">**포커스 도우미를 검색하고** 이 페이지를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="94dfb-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="94dfb-351">알람만 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-351">Select **Alarms Only**.</span></span> <span data-ttu-id="94dfb-352">이렇게 하면 상수 알림 플라이아웃이 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="94dfb-353">디스크 정리</span><span class="sxs-lookup"><span data-stu-id="94dfb-353">Disk Cleanup</span></span>

1. <span data-ttu-id="94dfb-354">디스크 **정리를 검색하고** 이 앱을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="94dfb-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="94dfb-355">삭제할 **파일에서**삭제할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="94dfb-356">또한 **시스템 파일 정리 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="94dfb-357">완료 및 확인</span><span class="sxs-lookup"><span data-stu-id="94dfb-357">Complete and verify</span></span>

1. <span data-ttu-id="94dfb-358">모든 Windows 업데이트를 검색하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="94dfb-359">그룹 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="94dfb-360">승강된 명령 프롬프트에 **gpupdate /force /boot /wait:0 을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="94dfb-361">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-361">Restart the device.</span></span>

4. <span data-ttu-id="94dfb-362">작업 표시줄 앱을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="94dfb-363">앱 연결</span><span class="sxs-lookup"><span data-stu-id="94dfb-363">Connect App</span></span>
   - <span data-ttu-id="94dfb-364">잠금 아이콘</span><span class="sxs-lookup"><span data-stu-id="94dfb-364">Lock Icon</span></span>
   - <span data-ttu-id="94dfb-365">캡처 및 스케치</span><span class="sxs-lookup"><span data-stu-id="94dfb-365">Snip & Sketch</span></span>
   - <span data-ttu-id="94dfb-366">Teams(해당되는 경우)</span><span class="sxs-lookup"><span data-stu-id="94dfb-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="94dfb-367">Office 앱(해당하는 경우)</span><span class="sxs-lookup"><span data-stu-id="94dfb-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="94dfb-368">Surface 앱</span><span class="sxs-lookup"><span data-stu-id="94dfb-368">Surface App</span></span>
   - <span data-ttu-id="94dfb-369">화이트보드</span><span class="sxs-lookup"><span data-stu-id="94dfb-369">Whiteboard</span></span>
    
5. <span data-ttu-id="94dfb-370">현재 상태 검색을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-370">Verify presence detection.</span></span>

   - <span data-ttu-id="94dfb-371">현재 상태 검색은 시스템 트레이의 녹색 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="94dfb-372">Connect App을 사용하여 이 PC에 대한 투영이 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="94dfb-373">Project를 이  **PC 설정으로 구성한** 후 적어도 한 번 이상 연결 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="94dfb-374">(이후에 Surface Hub에 프로젝트하기 위해 Connect 앱을 실행하지 필요는 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="94dfb-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="94dfb-375">전원 및 절전 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="94dfb-376">화면 보호기: 15분, (없음), Mystify 또는 Blank; 암호 요구 확인란이 선택되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="94dfb-377">화면: **2시간 후에 끄기**</span><span class="sxs-lookup"><span data-stu-id="94dfb-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="94dfb-378">PC: **4시간 후에 꺼집니다.**</span><span class="sxs-lookup"><span data-stu-id="94dfb-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="94dfb-379">Windows Hello가 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="94dfb-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="94dfb-380">설정 동기화가 사용되지 않도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="94dfb-381">시작 앱을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="94dfb-382">Windows 10을 설치 및 구성한 후 Surface Hub 2S는 다른 Windows 10 장치와 마찬가지로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94dfb-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94dfb-383">관련 항목</span><span class="sxs-lookup"><span data-stu-id="94dfb-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="94dfb-384">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="94dfb-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
