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
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203565"
---
# <span data-ttu-id="3d221-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성</span><span class="sxs-lookup"><span data-stu-id="3d221-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="3d221-105">Windows 10 Pro 또는 Enterprise로 마이그레이션하는 설치 프로세스를 완료한 후 다음 단계를 수행하여 Surface Hub 2에서 앱 및 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="3d221-106">이러한 단계는 개인 설정 큰 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 보장하는 데 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="3d221-107">이러한 단계를 수행할 때 유선 또는 무선 키보드와 마우스를 사용하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="3d221-108">시스템 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3d221-108">Configure system settings</span></span>

1. <span data-ttu-id="3d221-109">디바이스에서 로컬 관리자 권한이 있는 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="3d221-110">Azure AD 가입 장치에서 Azure AD 가입을 수행하는 사용자가 로컬 관리자 그룹에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="3d221-111">Azure AD 전역 관리자 및 Azure AD 장치 관리자도 로컬 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> </a> 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="3d221-112">명령 프롬프트에 **net localgroup 관리자를** 입력하여 로컬 관리자 권한이 있는 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="3d221-113">이름(예: **username-SHub-Desktop)을**사용하여 디바이스 이름을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="3d221-114">시작 **설정**계정을 선택하여 설정을  >  **Settings**  >  **Accounts**  >  **동기화하고** 동기화 설정을 **끄면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="3d221-115">여기에 사용된 설정은 최상의 큰 화면 터치 환경을 사용하도록 설정되어 있으므로 다른 디바이스를 동기화하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="3d221-116">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-116">Restart the device.</span></span>

## <span data-ttu-id="3d221-117">터치 키보드 및 터치 패드 사용</span><span class="sxs-lookup"><span data-stu-id="3d221-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="3d221-118">작업 표시줄을 탭하고 누르거나 마우스 **Show touch keyboard button** 오른쪽 단추를 클릭한 다음 터치 키보드 단추 표시 및 터치 패드 단추 **표시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="3d221-119">터치 키보드는 직접 사용자 입력에 유용하며, 가상 터치 패드는 정확한 선택, 화면 팁 마우스 오른쪽 단추 누르기 또는 마우스 오른쪽 단추로 누르기 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="3d221-120">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-120">See the following example.</span></span>

      ![터치 설정](images/touch.png)

2. <span data-ttu-id="3d221-122">터치 키보드를 QWERTY 및 부동 키보드로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="3d221-123">작업 **표시줄에서 키보드** 아이콘을 선택하여 터치 키보드를 표시하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="3d221-124">터치 키보드의 왼쪽 위 모서리에 있는 키보드 아이콘을 선택하여 키보드 설정을 니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="3d221-125">QWERTY를 사용하도록 설정하려면 위쪽 행의 마지막 키보드 유형 옆에 있는 마지막 옵션을 선택하고 부동 기능을 사용하도록 설정하려면 두 번째 행의 마지막 옵션을 선택합니다. 이 큰 화면에서 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="3d221-126">다음 예를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-126">See the following examples.</span></span>

       ![키보드 설정](images/kbd.png)
 
3. <span data-ttu-id="3d221-128">소프트 키보드 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="3d221-129">터치 **키보드에서** 설정 아이콘을 선택하거나 입력 설정을 검색하여 **니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![소프트 키보드 설정](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="3d221-131">맞춤법, 입력 및 터치 키보드에서 모든 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="3d221-132">다음 예제에서는 옵션을 탐색하고 선택하는 데 유용한 트랙 패드를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="3d221-133">화면 키보드를 사용하여 Microsoft Store를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![트랙 패드 사용](images/store.png)

## <span data-ttu-id="3d221-135">키보드 Bluetooth 마우스 구성(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3d221-135">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="3d221-136">장치를 기본 Windows 장치로 사용하는 경우 키보드와 마우스를 연결하거나 입력 또는 정밀도 작업을 위해 자주 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="3d221-137">Surface Hub 디바이스가 PC에 가까운 경우 테두리 없이 마우스를 사용하여 Surface Hub와 PC 간에 원활하게 이동할 <a href="https://aka.ms/mm" target="_blank"> </a> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="3d221-138">자세한 내용은 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 가비지에서 Microsoft 다운로드: 테두리 없는 마우스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="3d221-139">작업 표시줄 레이아웃의 예</span><span class="sxs-lookup"><span data-stu-id="3d221-139">Example of Taskbar layout</span></span>

<span data-ttu-id="3d221-140">아래 단계를 완료하여 Windows 10 Professional 또는 Enterprise용 Surface Hub 2를 설정/구성한 후, 각 응용 프로그램의 빠른 원터치 시작을 위해 가장 많이 사용되는 응용 프로그램을 작업 표시줄에 고정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-140">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="3d221-141">다음은 작업 표시줄이 어떻게 표시될 수 있는지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-141">Below is an example of what your taskbar could look like:</span></span>

 ![작업 표시줄 레이아웃](images/taskblyt.png)
### <span data-ttu-id="3d221-143">설치된 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="3d221-143">Update installed apps</span></span>

<span data-ttu-id="3d221-144">설치된 모든 스토어 앱을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-144">To update all installed Store apps:</span></span>

1. <span data-ttu-id="3d221-145">Microsoft Store 앱을 열고 오른쪽 위 모서리에서 더 많은 타원 보기를 선택합니다. **See more**</span><span class="sxs-lookup"><span data-stu-id="3d221-145">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="3d221-146">다운로드 **및 업데이트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-146">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="3d221-147">업데이트 **다운로드 선택**</span><span class="sxs-lookup"><span data-stu-id="3d221-147">Select **Get updates**</span></span>

### <span data-ttu-id="3d221-148">모든 Windows 업데이트 검색 및 설치</span><span class="sxs-lookup"><span data-stu-id="3d221-148">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="3d221-149">Windows 10 Professional 또는 Windows 10 Enterprise로 마이그레이션한 후 설치할 수 있는 서비스 및 기능 업데이트가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-149">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="3d221-150">Go to **Settings**  >  **Update & Security** > and then select Check for **updates.**</span><span class="sxs-lookup"><span data-stu-id="3d221-150">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="3d221-151">업데이트가 있는 경우 업데이트를 설치하고 다시 시작한 다음 다음 알림이 표시될 때까지 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-151">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Windows 업데이트 '최신 정보' 알림](images/wustatus.png)


## <span data-ttu-id="3d221-153">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="3d221-153">OneDrive for Business</span></span>

<span data-ttu-id="3d221-154">비즈니스용 OneDrive를 사용하여 모든 작업 장치 간에 도구, 로그 및 기타 파일을 쉽게 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="3d221-155">OneDrive를 사용하면 랩톱, Surface Hub 데스크톱 및 Intune에서 관리하는 모바일 장치 간에 작업 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-155">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="3d221-156">모든 장치에서 파일을 편집할 수 있으며 모든 네트워크 연결 장치가 변경 내용으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-156">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="3d221-157">Surface Hub SSD(128GB)의 크기를 고려하여 Surface Hub 데스크톱 디바이스에서 OneDrive를 구성하는 경우 기본 구성은 파일을 온라인으로 유지하고 파일을 사용할 때 다운로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-157">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="3d221-158">필요한 경우만 파일을 다운로드하도록 OneDrive를 **Files On-Demand** 구성하려면 필요한 경우 파일 관리 설정을 설정하여 공간을 절약하고 파일을 다운로드합니다. **Save space and download files as you use them**</span><span class="sxs-lookup"><span data-stu-id="3d221-158">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="3d221-159">자세한 내용은 Windows에서 쿼리 및 필요한 파일 제공 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 상태 설정을 참조하세요. </a></span><span class="sxs-lookup"><span data-stu-id="3d221-159">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive 설정](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="3d221-161">이러한 단계를 반복하여 개인 OneDrive를 구성할 수도 있지만 드라이브 공간을 절약하고 필요할 때만 파일을 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-161">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="3d221-162">SharePoint 및 Teams</span><span class="sxs-lookup"><span data-stu-id="3d221-162">SharePoint and Teams</span></span>

<span data-ttu-id="3d221-163">SharePoint 및 Teams 채널 파일은 OneDrive 동기화 엔진을 사용하여 랩톱 및 Surface Hub와 같은 데스크톱 장치와 로컬로 동기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-163">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="3d221-164">OneDrive 동기화 앱을 사용하여 내부 회사 파일을 로컬 드라이브에 동기화하려면</span><span class="sxs-lookup"><span data-stu-id="3d221-164">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="3d221-165">SharePoint 사이트로 이동하여 로컬 장치에서 보거나 편집하는 데 관심이 있는 파일의 최상위 문서 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-165">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="3d221-166">SharePoint 리본 **메뉴** 위쪽의 동기화 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-166">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="3d221-167">팝업에서 **Open** 열기에서 이 사이트가 **Microsoft OneDrive를 열려고 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-167">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="3d221-168">작업 표시줄 오른쪽 아래에 있는 OneDrive 아이콘을 선택하여 SharePoint 파일이 로컬 드라이브와 동기화하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-168">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="3d221-169">파일을 온라인으로 유지하고 파일을 사용할 때만 다운로드할 수 있는 구성이 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3d221-169">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="3d221-170">파일 탐색기를 니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-170">Open file explorer.</span></span>
    
    2. <span data-ttu-id="3d221-171">SharePoint 이름을 찾아 마우스 오른쪽 단추로 클릭합니다. 예: \*\*Contoso \<SharePoint Document Folder Name\> \ \*\*.</span><span class="sxs-lookup"><span data-stu-id="3d221-171">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="3d221-172">공간을 **비우기 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-172">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="3d221-173">상태 열에는 파일 및 폴더의 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-173">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="3d221-174">자세한 내용은 OneDrive 동기화 클라이언트를 사용하여 SharePoint 파일 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 동기화를 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-174">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="3d221-175">Teams 채널 파일은 버전 기록 및 로컬 데스크톱 장치와 동기화를 포함하여 모든 동일한 SharePoint 문서 기능을 사용하여 SharePoint 사이트에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-175">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="3d221-176">Teams 채널 파일을 동기화하려면</span><span class="sxs-lookup"><span data-stu-id="3d221-176">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="3d221-177">관심 있는 Teams 채널로 이동하고 맨 위에 있는 파일 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-177">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="3d221-178">그런 다음 **동기화를 선택합니다.** 파일이 동기화를 시작하고 Desktop \ Contoso \ 의 파일 \*\*탐색기에서 \<name of the Teams Channel\> 표시됩니다. \*\*</span><span class="sxs-lookup"><span data-stu-id="3d221-178">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="3d221-179">SharePoint 사이트를 동기화하는 데 사용한 절차와 동일한 절차를 사용하여 파일을 클라우드에 보관하고 사용할 때만 다운로드하고, Teams 채널 이름의 파일 탐색기를 탭하고 누르거나 마우스 오른쪽 단추로 클릭한 다음 공간을 비우는 방법을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-179">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="3d221-180">Surface Hub 펜 설정</span><span class="sxs-lookup"><span data-stu-id="3d221-180">Surface Hub pen settings</span></span>

**<span data-ttu-id="3d221-181">Surface Hub Bluetooth 페어링</span><span class="sxs-lookup"><span data-stu-id="3d221-181">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="3d221-182">펜을 페어링하여 펜 펌웨어를 최신으로 유지하고, 펜 바로 가기를 설정하고, Bluetooth 장치 설정 페이지 또는 Surface 앱에서 배터리 충전 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-182">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="3d221-183">설정 **시작**  >  **디바이스를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-183">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="3d221-184">Select **Add Bluetooth or other device.**</span><span class="sxs-lookup"><span data-stu-id="3d221-184">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="3d221-185">를 **Bluetooth.**</span><span class="sxs-lookup"><span data-stu-id="3d221-185">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="3d221-186">펜 tail 단추를 제거하고 흔들어 배터리 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-186">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="3d221-187">캡을 다시 넣고 페어링 LED가 깜박일 때까지 대문자 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-187">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="3d221-188">Surface Hub Bluetooth **Surface Hub 2 펜을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-188">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="3d221-189">페어링 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-189">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="3d221-190">페어링이 실패하면 펜을 다시 페어링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-190">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="3d221-191">그래도 문제가 해결되지 않는 경우 펜이 화이트보드 응용 프로그램에서 작동하는지 확인하여 배터리가 충전되어 있는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-191">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="3d221-192">그렇지 않은 경우 배터리를 교체한 다음 펜을 다시 페어링해 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-192">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="3d221-193">필요한 경우 장치를 다시 시작한 다음 다시 시도하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-193">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="3d221-194">**펜 바로 가기 설정** Surface Hub 펜에는 "tail click"이라고도 하는 바로 가기 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-194">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="3d221-195">바로 가기를 구성하려면 앞에서 설명한 대로 펜을 먼저 페어링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-195">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="3d221-196">펜을 검색하고 Windows ink & **펜을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-196">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="3d221-197">페이지 아래쪽에서 다음과 같이 대화 상자를 여는 펜 바로 가기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-197">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![펜 바로 가기](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="3d221-199">카메라 구성</span><span class="sxs-lookup"><span data-stu-id="3d221-199">Camera configuration</span></span>

<span data-ttu-id="3d221-200">디바이스의 위쪽 또는 어느 쪽에나 카메라를 탑재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-200">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="3d221-201">카트 대신 데스크톱 독립 실행형으로 허브를 사용하거나 허브와 가까운 위치에 카메라 각도를 최적화하기 위해 카메라를 탑재합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-201">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="3d221-202">카메라가 자동 회전하지 않습니다. 따라서 카메라를 수동으로 회전하려면 2mm 16진수 키가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-202">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="3d221-203">카메라를 사이드 마운트하고 카메라를 수동으로 회전하는 방법에 대한 자세한 내용은 Surface Hub 2S 카메라 렌즈 방향을 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-203">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="3d221-204">Windows Hello 구성</span><span class="sxs-lookup"><span data-stu-id="3d221-204">Windows Hello configuration</span></span>

<span data-ttu-id="3d221-205">Windows 10 Enterprise를 실행하는 Surface Hub 2S를 사용하면 Win32 데스크톱 응용 프로그램과 생체 인식 Windows Hello 옵션의 전체 제품군을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-205">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="3d221-206">Surface Hub 2 지문 판독기 액세서리를 장치의 모든 USB-C 포트에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-206">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="3d221-207">Surface Hub 2 지문 판독기를 주문하거나 기술 사양을 시청하기 위해서는 (surface-hub-2-essential-add-ons.md" target="_blank">Essential Add-ons for Windows 10 Pro and Enterprise on Surface Hub 2)를 참조합니다. </a></span><span class="sxs-lookup"><span data-stu-id="3d221-207">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="3d221-208">지문 판독기를 삽입한 **Start**후 시작 설정 계정 로그인 옵션을 선택하여 Windows Hello Fingerprint를 선택하여 지문을  >  **Settings**  >  **Accounts**  >  **Sign-in options**  >  **Windows Hello Fingerprint** 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-208">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="3d221-209">얼굴 인식에 Windows Hello 인증 장치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-209">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="3d221-210">Surface Hub 2S 카메라는 Windows Hello 얼굴 인식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-210">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="3d221-211">작업 표시줄에서 잠금 화면 바로 가기 아이콘 사용</span><span class="sxs-lookup"><span data-stu-id="3d221-211">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="3d221-212">Windows-L 바로 가기 키와 유사한 원터치 화면 잠금을 사용할 수 있는 아이콘을 작업 표시줄에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-212">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="3d221-213">바탕 화면을 탭하고 누르거나 마우스 **New**오른쪽 단추로 클릭하고 새 바로 가기  >  **Shortcut**  >  **Browse**  >  **찾아보기 데스크톱**  >  **확인 다음을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-213">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="3d221-214">내 **PC**잠금과 같은 바로 가기 이름을 입력한 다음 마름을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-214">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="3d221-215">바탕 화면에서 새로 만든 바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-215">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="3d221-216">바로 **가기 탭의** 대상 **Target** 필드에 다음을 입력합니다. **Rundll32.exe User32.dll,LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="3d221-216">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="3d221-217">아이콘 **변경 단추를** 선택하고 아이콘을C:\Windows\System32\imageres.dll\*\* 사용할 \*\* 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-217">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="3d221-218">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-218">See the following example:</span></span>

    ![아이콘 선택](images/lock.png)
    
1.  <span data-ttu-id="3d221-220">확인을 **선택하여** 바로 가기를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-220">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="3d221-221">바로 가기를 마우스 오른쪽 단추로 클릭하거나 탭하고 작업 표시줄에 **고정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-221">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="3d221-222">잠금 바로 가기를 작업 표시줄에 고정한 후 바탕 화면에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-222">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="3d221-223">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3d221-223">Applications</span></span>


### <span data-ttu-id="3d221-224">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="3d221-224">Microsoft Whiteboard</span></span>

<span data-ttu-id="3d221-225">Microsoft Whiteboard를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="3d221-225">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="3d221-226">작업 **표시줄 오른쪽** 아래에서 Windows Ink 작업 영역 아이콘을 선택하고 **화이트보드를 다운로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-226">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Ink 작업 영역](images/ink.png) 

<span data-ttu-id="3d221-228">또는 Microsoft Store에서 화이트보드를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-228">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="3d221-229">Microsoft Store 앱을 열고 **화이트보드를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-229">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="3d221-230">로그인하고 여러 디바이스에서 사용해주신 덕분에 **아니요를** 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-230">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="3d221-231">화이트보드를 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-231">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="3d221-232">Surface 앱</span><span class="sxs-lookup"><span data-stu-id="3d221-232">Surface app</span></span>

1. <span data-ttu-id="3d221-233">Microsoft Store에서 **Surface를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-233">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="3d221-234">필터에서 **사용 가능을** 모든 **장치로 설정**</span><span class="sxs-lookup"><span data-stu-id="3d221-234">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="3d221-235">Surface **앱을 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-235">Install the **Surface** app.</span></span> <span data-ttu-id="3d221-236">이 앱은 나열된 첫 번째 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-236">This should be the first app listed.</span></span> <span data-ttu-id="3d221-237">앱을 설치하려면 MSA를 스토어에 연결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-237">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="3d221-238">Surface 앱을 **작업** 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-238">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="3d221-239">캡처 및 스케치</span><span class="sxs-lookup"><span data-stu-id="3d221-239">Snip & Sketch</span></span>

1. <span data-ttu-id="3d221-240">스케치 & **Snip** 앱을 열고 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-240">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="3d221-241">오른쪽 위 모서리에서 타원을 선택한 다음 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-241">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="3d221-242">설정에서 클립보드에 **자동 복사,** 잘라 내기 **및**여러 창을 **니다(선택** 사항). **Settings**</span><span class="sxs-lookup"><span data-stu-id="3d221-242">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="3d221-243">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="3d221-243">Microsoft Office</span></span>

1. <span data-ttu-id="3d221-244">Office <a href="https://portal.office.com/account#installs" target="_blank"> 포털을 </a> 열고 원하는 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-244">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="3d221-245">원하는 Office 응용 프로그램을 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-245">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="3d221-246">Outlook이 설치된 경우 Outlook OST를 설정하여 지난 2주 동안의 캐시만 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-246">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="3d221-247">이렇게 하면 디스크 사용량 및 설정 시간이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-247">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="3d221-248">파일 **File**  >  **계정 설정을 선택하고** 계정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-248">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="3d221-249">변경을 **선택하고** 캐시된 **Exchange** 모드를 사용할 슬라이더를 14일로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-249">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="3d221-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d221-250">Microsoft Teams</span></span>

1. <span data-ttu-id="3d221-251"><a href="https://teams.microsoft.com/downloads" target="_blank">Microsoft Teams를 다운로드하여 </a> 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-251">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="3d221-252">응용 프로그램을 자동으로 시작하도록 설정을 구성합니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="3d221-252">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="3d221-253">Teams를 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-253">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="3d221-254">방해를 피하기 위해 디바이스에서 Teams 알림을 줄이는 것이 좋습니다(선택 사항).</span><span class="sxs-lookup"><span data-stu-id="3d221-254">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams 알림](images/teams.png)

### <span data-ttu-id="3d221-256">앱 연결</span><span class="sxs-lookup"><span data-stu-id="3d221-256">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d221-257">Windows 10 버전 2004 이상에서는 Miracast를 사용하는 무선 투영용 Connect 앱이 기본적으로 설치되지 않지만 선택적 기능으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-257">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="3d221-258">Windows 버전 2004 이상을 설치(또는 업데이트)한 경우 이 PC 화면에 다음 설정이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-258">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![이 PC에 프로젝트](images/sh2-project.png) 


1. <span data-ttu-id="3d221-260">"이 PC에 투영" 설정 페이지에서 앱을 설치하려면 선택적 기능 추가 기능을 선택한 다음 무선 디스플레이 **Optional features**  >  **Add a feature** **앱을 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-260">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="3d221-261">일부 Windows 및 Android 장치에서 확인이면 이 PC에 프로젝트할 수 **있습니다.** 다음을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-261">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="3d221-262">**장치가 회사** 네트워크에 없는 경우 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-262">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="3d221-263">그렇지 않은 경우 **보안 네트워크의 모든 곳에서 사용 가능을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="3d221-263">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="3d221-264">Under **Ask to project to this PC,** choose First time **only**.</span><span class="sxs-lookup"><span data-stu-id="3d221-264">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="3d221-265">**페어링을 위해 PIN 필요 아래에서**사용 **안 을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-265">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="3d221-266">그런 다음 앱을 시작하고 작업 표시줄에 고정하기 위해 **Connect를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-266">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="3d221-267">앱을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-267">Open the app.</span></span> <span data-ttu-id="3d221-268">앱이 열려 있는 동안 작업 표시줄에서 앱 연결 아이콘을 마우스 오른쪽 단추로 클릭하고 작업 표시줄에 **고정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-268">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="3d221-269">그런 다음 연결 앱을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-269">Then close the Connect app.</span></span> <span data-ttu-id="3d221-270">앱이 한 번 이상 실행되지 않으면 이 **PC에** 대한 Project가 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-270">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="3d221-271">회사 네트워크에 없는 경우 권장되는 구성:</span><span class="sxs-lookup"><span data-stu-id="3d221-271">Recommended configuration when not on the corporate network:</span></span>

![가정의 설정](images/project1.png)

<span data-ttu-id="3d221-273">회사 네트워크에서 권장되는 구성:</span><span class="sxs-lookup"><span data-stu-id="3d221-273">Recommended configuration on the corporate network:</span></span>

![직장의 설정](images/project2.png)

### <span data-ttu-id="3d221-275">사용자 휴대폰</span><span class="sxs-lookup"><span data-stu-id="3d221-275">Your Phone</span></span>

<span data-ttu-id="3d221-276">휴대폰 **앱은** 기본적으로 Windows 10에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-276">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="3d221-277">이 패키지가 없는 경우 Windows 스토어에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-277">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="3d221-278">앱을 설정하는 방법에 대한 자세한 내용은 Windows 10에서 휴대폰을 설정하고 PC와 휴대폰 간에 데이터를 동기화하는 방법을 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-278">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="3d221-279">Windows 10에서 휴대폰 앱의 일반적인 문제를 해결하는 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 방법도 </a> 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d221-279">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <span data-ttu-id="3d221-280">멋진 영역</span><span class="sxs-lookup"><span data-stu-id="3d221-280">Fancy Zones</span></span>


<span data-ttu-id="3d221-281">**멋진 영역은** <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub의 PowerToys라는 도구 </a> 모음의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-281">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="3d221-282">디스플레이에서 고정 레이아웃("영역")을 정의한 다음 각 영역에서 실행할 앱을 선택하여 Surface Hub 2의 화면 부동산을 활용하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-282">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="3d221-283">[PowerToys 위키에는](https://github.com/microsoft/PowerToys/wiki) [FancyZones를](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)포함하여 각 도구를 사용 및 사용자 지정하는 방법에 대한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-283">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="3d221-284">높은 수준에서 - PowerToys를 설치한 후 사용자 지정 레이아웃을 선택하거나 만든 다음 Shift 키를 아래로 놓고 키보드 키를 끌어서 실행 중인 앱을 특정 영역으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-284">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="3d221-285">이 Bluetooth 또는 USB 키보드와 마우스를 사용하면 도움이 되거나 화면 터치 키보드와 터치 패드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-285">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="3d221-286">전원 토이 팁</span><span class="sxs-lookup"><span data-stu-id="3d221-286">Power toys tips</span></span>**
- <span data-ttu-id="3d221-287">GitHub에서 PowerToys 릴리스 업데이트에 대한 전자 메일 알림을 받으려면 페이지 위쪽의 "등록" 단추를 [클릭합니다.](https://github.com/microsoft/PowerToys/releases)</span><span class="sxs-lookup"><span data-stu-id="3d221-287">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="3d221-288">PowerToys가 설치되면 PowerToys 설정 다운로드 업데이트를 자동으로 설정하여 Windows 알림을 받고 최신 업데이트를 다운로드 및 설치할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-288">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="3d221-289">PowerToys 설정에 액세스하려면 작업 표시줄에서 실행 중인 앱을 선택하고 메뉴가 나타날 때까지 PowerToys 아이콘을 마우스 오른쪽 단추로 클릭하거나 누르고 있습니다. **Running apps**</span><span class="sxs-lookup"><span data-stu-id="3d221-289">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="3d221-290">"설정"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-290">Select “Settings”.</span></span>
- <span data-ttu-id="3d221-291">PowerToys 설정 페이지의 맨 아래에서 업데이트를 자동으로 **다운로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-291">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="3d221-292">업데이트가 릴리스된 경우 업데이트를 설치할 수 있는 옵션을 제공 하는 Windows 알림이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-292">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <span data-ttu-id="3d221-293">Edge Chromium 브라우저</span><span class="sxs-lookup"><span data-stu-id="3d221-293">Edge Chromium browser</span></span>

<span data-ttu-id="3d221-294">새 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 브라우저를 다운로드하여 설치합니다. </a></span><span class="sxs-lookup"><span data-stu-id="3d221-294">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="3d221-295">Surface Hub 하드웨어 진단 도구</span><span class="sxs-lookup"><span data-stu-id="3d221-295">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="3d221-296"><a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank">Surface Hub 하드웨어 진단 </a> 도구는 Microsoft Store에서 무료로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-296">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="3d221-297">이 도구는 Surface Hub가 최상의 기능을 수행하는지 확인하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-297">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="3d221-298">펌웨어가 최신 버전인지와 올바르게 구성된지 확인하는 테스트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-298">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="3d221-299">대화형 테스트를 통해 필수 기능이 예상대로 작동하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-299">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="3d221-300">문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-300">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="3d221-301">링크를 클릭하여 Microsoft Store에서 설치한 다음 응용 프로그램을 작업 표시줄에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-301">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="3d221-302">추가 설정</span><span class="sxs-lookup"><span data-stu-id="3d221-302">Additional settings</span></span>

### <span data-ttu-id="3d221-303">Pen tail select to launch Whiteboard</span><span class="sxs-lookup"><span data-stu-id="3d221-303">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="3d221-304">펜을 **검색하고** **Windows & 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-304">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="3d221-305">페이지 아래쪽의 펜 바로 **Pen shortcuts** 가기에서 **Select once를** **Microsoft Whiteboard로 설정**</span><span class="sxs-lookup"><span data-stu-id="3d221-305">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="3d221-306">전원 관리</span><span class="sxs-lookup"><span data-stu-id="3d221-306">Power management</span></span>

<span data-ttu-id="3d221-307">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise를 사용하여 최상의 환경을 얻을 수 있는 몇 가지 전원 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-307">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="3d221-308">여기에는 화면 및 PC 시간 제한 및 기본 제공 Doppler(휴먼 현재 상태 감지), 화면 보호기 및 암호 보호와 상호 작용하는 방법, 그리고 적절한 경우 랩톱/데스크톱 사용자를 위한 그룹 정책 전원 설정을 전달하는 방법을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-308">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="3d221-309">Surface Hub 2의 Windows 10 Pro 또는 Enterprise는 터치, 마우스 및 키보드 동작과 기본 제공 Doppler(휴먼 점유 감지)를 통해 화면이 절전으로 이동하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-309">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="3d221-310">기본적으로 휴먼 점유 검색은 사용하도록 설정되어 있지만, 원하는 경우 초기 마이그레이션의 일부로 Surface UEFI 구성 도구에서 장치 옵션을 전환하거나 이후 UEFI 구성 패키지를 구축 및 적용하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-310">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="3d221-311">전원 관리: 화면 및 PC 절전 설정</span><span class="sxs-lookup"><span data-stu-id="3d221-311">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="3d221-312">**Start**  >  **절전으로 시작 설정**  >  **시스템**전원  >  **& 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-312">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="3d221-313">전원 모드 슬라이더를 최상의 **성능으로 설정**</span><span class="sxs-lookup"><span data-stu-id="3d221-313">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="3d221-314">이동이 감지될 때 디바이스를 깨우는 Doppler 현재 상태 감지를 고려하면서 화면 및 절전 모드 값을 기본 설정에 맞게 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-314">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="3d221-315">따라서 모범 사례로, **2시간** 후에 화면이 꺼지게 설정하고 4시간 후에 PC가 꺼지게 **설정하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-315">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="3d221-316">전원 관리: 화면 보호기</span><span class="sxs-lookup"><span data-stu-id="3d221-316">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="3d221-317">잠금 화면 **및** 잠금 화면 **열기 설정을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-317">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="3d221-318">화면 **시간 제한 설정 및** 화면 **보호기** 설정을 기본 설정으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-318">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="3d221-319">권장되는 기본값은:</span><span class="sxs-lookup"><span data-stu-id="3d221-319">Recommended default values are:</span></span>

   - <span data-ttu-id="3d221-320">화면 보호기에서 선택한 화면 보호기(없음) 또는 화면 보호기입니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-320">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="3d221-321">15분까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-321">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="3d221-322">다시 시작 시 로그온 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-322">On resume, display logon screen.</span></span>


**<span data-ttu-id="3d221-323">전원 관리: 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="3d221-323">Power Management: Group Policy</span></span>**

<span data-ttu-id="3d221-324">다음 절차를 수행하기 전에 IT 부서에 승인을 요청하여 전역 전원 관리 정책에서 Surface Hub 2S 장치를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-324">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="3d221-325">일부 전원 관리 설정은 현재 상태 검색 기능을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-325">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="3d221-326">소프트웨어 **센터를 검색하고** 열어 습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-326">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="3d221-327">옵션을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-327">Select **Options**.</span></span>

3. <span data-ttu-id="3d221-328">전원 관리를 **확장하고** 이 컴퓨터에 IT 부서의 전원 설정 적용 **안 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-328">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![소프트웨어 설정](images/soft-cntr.png)

### <span data-ttu-id="3d221-330">저장소 센스</span><span class="sxs-lookup"><span data-stu-id="3d221-330">Storage Sense</span></span>

<span data-ttu-id="3d221-331">Surface Hub 2에는 로컬 저장소용 128GB SSD가 있으므로 일반적인 사용 중에 저장소 저장 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-331">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="3d221-332">저장소 센스를 구성하는 경우:</span><span class="sxs-lookup"><span data-stu-id="3d221-332">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="3d221-333">시스템 **설정 아래에**있는 저장소 설정을 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-333">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="3d221-334">설정 **아래에서**저장소 설정 켜기 **센스를** 선택하여 저장소 설정 페이지를 **여십시오.**</span><span class="sxs-lookup"><span data-stu-id="3d221-334">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="3d221-335">저장소 센스를 **켜는 경우**</span><span class="sxs-lookup"><span data-stu-id="3d221-335">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="3d221-336">저장소 **센스 구성을** 선택하거나 지금 실행하고 파일을 가능한 한 많이 온라인으로 유지하도록 설정을 구성합니다(드라이브 공간 제한으로 인해).</span><span class="sxs-lookup"><span data-stu-id="3d221-336">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="3d221-337">권장 설정:</span><span class="sxs-lookup"><span data-stu-id="3d221-337">Recommended settings:</span></span>

- <span data-ttu-id="3d221-338">저장소 센스 실행 = 매일.</span><span class="sxs-lookup"><span data-stu-id="3d221-338">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="3d221-339">앱에서 사용하지 않는 임시 파일을 삭제합니다. 최소 14일마다(이상).</span><span class="sxs-lookup"><span data-stu-id="3d221-339">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="3d221-340">30일이 지난 경우 다운로드 폴더에서 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-340">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="3d221-341">OneDrive: 30일 이상 열지 않은 경우 콘텐츠가 온라인 전용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-341">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="3d221-342">태블릿 모드</span><span class="sxs-lookup"><span data-stu-id="3d221-342">Tablet mode</span></span>

<span data-ttu-id="3d221-343">접근성 요구에 필요한 경우 태블릿 모드를 니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-343">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="3d221-344">소리 설정</span><span class="sxs-lookup"><span data-stu-id="3d221-344">Sound settings</span></span>

1. <span data-ttu-id="3d221-345">소리 설정을 **검색하고** 이 페이지를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-345">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="3d221-346">오른쪽의 소리 **제어판을** 선택하고 소리 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-346">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="3d221-347">프로그램 **이벤트에서** **장치 연결** 및 장치 연결 **끊기를** 없음으로 **설정**</span><span class="sxs-lookup"><span data-stu-id="3d221-347">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="3d221-348">침묵 알림</span><span class="sxs-lookup"><span data-stu-id="3d221-348">Silence notifications</span></span>

1. <span data-ttu-id="3d221-349">포커스 **도우미를 검색하고** 이 페이지를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="3d221-349">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="3d221-350">알람만 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-350">Select **Alarms Only**.</span></span> <span data-ttu-id="3d221-351">이렇게 하면 일정한 알림 플라이아웃이 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-351">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="3d221-352">디스크 정리</span><span class="sxs-lookup"><span data-stu-id="3d221-352">Disk Cleanup</span></span>

1. <span data-ttu-id="3d221-353">디스크 **정리를 검색하고** 이 앱을 니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-353">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="3d221-354">삭제할 **파일에서**삭제할 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-354">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="3d221-355">또한 시스템 **파일 정리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-355">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="3d221-356">완료 및 확인</span><span class="sxs-lookup"><span data-stu-id="3d221-356">Complete and verify</span></span>

1. <span data-ttu-id="3d221-357">모든 Windows 업데이트를 검색하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-357">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="3d221-358">그룹 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-358">Update Group Policy.</span></span>

   1. <span data-ttu-id="3d221-359">승강된 명령 프롬프트에 **gpupdate /force /boot /wait:0을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-359">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="3d221-360">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-360">Restart the device.</span></span>

4. <span data-ttu-id="3d221-361">작업 표시줄 앱을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-361">Verify taskbar apps.</span></span>

   - <span data-ttu-id="3d221-362">앱 연결</span><span class="sxs-lookup"><span data-stu-id="3d221-362">Connect App</span></span>
   - <span data-ttu-id="3d221-363">잠금 아이콘</span><span class="sxs-lookup"><span data-stu-id="3d221-363">Lock Icon</span></span>
   - <span data-ttu-id="3d221-364">캡처 및 스케치</span><span class="sxs-lookup"><span data-stu-id="3d221-364">Snip & Sketch</span></span>
   - <span data-ttu-id="3d221-365">Teams(해당되는 경우)</span><span class="sxs-lookup"><span data-stu-id="3d221-365">Teams (if applicable)</span></span>
   - <span data-ttu-id="3d221-366">Office 앱(해당되는 경우)</span><span class="sxs-lookup"><span data-stu-id="3d221-366">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="3d221-367">Surface 앱</span><span class="sxs-lookup"><span data-stu-id="3d221-367">Surface App</span></span>
   - <span data-ttu-id="3d221-368">화이트보드</span><span class="sxs-lookup"><span data-stu-id="3d221-368">Whiteboard</span></span>
    
5. <span data-ttu-id="3d221-369">현재 상태 검색을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-369">Verify presence detection.</span></span>

   - <span data-ttu-id="3d221-370">현재 상태 검색은 시스템 트레이에 녹색 아이콘이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-370">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="3d221-371">연결 앱을 사용하여 이 PC에 대한 투영이 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-371">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="3d221-372">이  **PC 설정으로 Project를 구성한** 후 적어도 한 번 이상 연결 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-372">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="3d221-373">(이후에 Surface Hub에 프로젝트를 진행하기 위해 Connect 앱을 실행하지 않을 필요는 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="3d221-373">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="3d221-374">전원 및 절전 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-374">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="3d221-375">화면 보호기: 15분, 설정(없음), Mystify 또는 Blank 암호 요구 확인란이 선택되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-375">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="3d221-376">화면: **2시간 후에 끄기**</span><span class="sxs-lookup"><span data-stu-id="3d221-376">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="3d221-377">PC: **4시간 후에 꺼집니다.**</span><span class="sxs-lookup"><span data-stu-id="3d221-377">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="3d221-378">Windows Hello가 작동하고 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3d221-378">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="3d221-379">동기화 설정이 사용하지 않도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-379">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="3d221-380">시작 앱을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-380">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="3d221-381">Windows 10을 설치 및 구성한 후 Surface Hub 2S는 다른 Windows 10 장치와 마찬가지로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d221-381">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="3d221-382">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3d221-382">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="3d221-383">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3d221-383">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
