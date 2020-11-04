---
title: Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성
description: 이 문서에는 개인 설정 된 대형 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 유지 하기 위한 권장 사항이 포함 되어 있습니다.
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
ms.date: 11/03/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: b86776b56e892c34ea8b5abbc55d5c48723a5f9e
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154130"
---
# <span data-ttu-id="0bd4b-104">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise 구성</span><span class="sxs-lookup"><span data-stu-id="0bd4b-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="0bd4b-105">Windows 10 Pro 또는 Enterprise로 마이그레이션하는 설치 프로세스를 완료 한 후 다음 단계를 수행 하 여 Surface Hub 2에서 앱 및 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="0bd4b-106">이 단계는 개인 설정 된 대형 화면 터치 및 펜 컴퓨터를 사용할 때 최상의 환경을 유지 하기 위해 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="0bd4b-107">이 단계를 수행 하는 경우 유선 또는 무선 키보드와 마우스를 사용 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="0bd4b-108">시스템 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0bd4b-108">Configure system settings</span></span>

1. <span data-ttu-id="0bd4b-109">장치에서 로컬 관리자 권한이 있는 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="0bd4b-110">Azure AD 참가 디바이스에서 Azure AD 조인을 수행 하는 사용자가 로컬 관리자 그룹에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="0bd4b-111">Azure AD 전역 관리자 및 Azure AD 장치 관리자는 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 로컬 관리자 이기도 </a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="0bd4b-112">명령 프롬프트에서 **net localgroup 관리자** 를 입력 하 여 로컬 관리자 권한이 있는 계정을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="0bd4b-113">이름 (예: **username-SHub-데스크톱)** 을 사용 하 여 디바이스의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="0bd4b-114">**시작**  >  **설정**  >  **계정**선택  >  **설정을 동기화** 하 고 **동기화 설정을** 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="0bd4b-115">여기서 사용 되는 설정은 최상의 대형 화면 터치 환경을 사용 하기 위한 것 이므로 다른 장치를 동기화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="0bd4b-116">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-116">Restart the device.</span></span>

## <span data-ttu-id="0bd4b-117">터치 키보드 및 터치 패드 사용</span><span class="sxs-lookup"><span data-stu-id="0bd4b-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="0bd4b-118">작업 표시줄을 길게 누르거나 마우스 오른쪽 단추로 클릭 한 다음 **터치 키보드 단추 표시** 및 **터치 패드 단추**표시를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="0bd4b-119">터치 키보드는 직접 사용자 입력에 유용 하며, 가상 터치 패드는 정확한 선택, 화면 팁 또는 오른쪽 클릭을 위해 길게 탭 하 여 사용 하는 방법에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="0bd4b-120">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-120">See the following example.</span></span>

      ![터치 설정](images/touch.png)

2. <span data-ttu-id="0bd4b-122">터치 키보드를 QWERTY 및 부동으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="0bd4b-123">작업 표시줄에서 **키보드** 아이콘을 선택 하 여 터치 키보드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="0bd4b-124">터치 키보드에서 왼쪽 위 모서리에 있는 키보드 아이콘을 선택 하 여 키보드 설정을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="0bd4b-125">첫 행의 마지막 키보드 입력 옆에 있는을 선택 하 여 QWERTY을 사용 하도록 설정 하 고 두 번째 행의 마지막 옵션은이 큰 화면에서 매우 유용한 부동을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="0bd4b-126">다음 예를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-126">See the following examples.</span></span>

       ![키보드 설정](images/kbd.png)
 
3. <span data-ttu-id="0bd4b-128">소프트 키보드 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="0bd4b-129">터치 키보드에서 **설정** 아이콘을 선택 하거나 **입력 설정을**검색 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![소프트 키보드 설정](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="0bd4b-131">맞춤법 검사, 입력 및 터치 키보드의 모든 옵션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="0bd4b-132">다음 예제에서는 옵션을 탐색 하 고 선택 하는 데 유용한 트랙 패드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="0bd4b-133">화상 키보드는 Microsoft Store를 검색 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![트랙 패드 사용](images/store.png)

## <span data-ttu-id="0bd4b-135">Bluetooth 키보드 및 마우스 구성 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="0bd4b-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="0bd4b-136">장치를 기본 Windows 장치로 사용 하는 경우 키보드와 마우스를 연결 하 고, 입력 하거나 전체 작업을 수행 하는 데 자주 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="0bd4b-137">Surface Hub 장치가 PC 근처에 있는 경우 <a href="https://aka.ms/mm" target="_blank"> 경계 없이 마우스 </a> 를 사용 하 여 surface HUB와 PC 간에 매끄럽게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="0bd4b-138">자세한 내용은 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 경계 없이 마우스를 사용 하 여 중고품의 Microsoft 다운로드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="0bd4b-139">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="0bd4b-139">OneDrive for Business</span></span>

<span data-ttu-id="0bd4b-140"><a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank">비즈니스용 OneDrive를 사용 </a> 하 여 모든 작업 디바이스 간에 도구, 로그, 기타 파일을 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-140">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="0bd4b-141">OneDrive를 사용 하면 랩톱, Surface Hub 데스크톱, Intune으로 관리 되는 모바일 장치 간에 작업 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="0bd4b-142">모든 장치에서 파일을 편집할 수 있으며, 모든 네트워크 연결 장치가 변경 내용으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="0bd4b-143">Surface hub 데스크톱 장치에서 OneDrive를 구성 하는 경우 Surface Hub SSD (128GB)의 크기를 고려 하 여 기본 구성이 파일을 온라인 상태로 유지 하 고 파일을 사용 하는 동안 다운로드 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="0bd4b-144">필요할 때만 파일을 다운로드 하도록 OneDrive를 구성 하려면 **필요 시 파일** 설정을 사용 하는 **동안 공간을 절약 하 고 파일을 다운로드**하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="0bd4b-145">자세한 내용은 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Windows에서 파일 주문형 상태 쿼리 및 설정을 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-145">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive 설정](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="0bd4b-147">또한이 단계를 반복 하 여 개인 OneDrive를 구성할 수 있지만 드라이브 공간을 절약 하 고 필요할 때만 파일을 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="0bd4b-148">SharePoint 및 팀</span><span class="sxs-lookup"><span data-stu-id="0bd4b-148">SharePoint and Teams</span></span>

<span data-ttu-id="0bd4b-149">SharePoint 및 팀 채널 파일은 OneDrive 동기화 엔진을 사용 하 여 랩톱 및 Surface Hub와 같은 데스크톱 장치에 로컬로 동기화 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="0bd4b-150">OneDrive 동기화 앱을 사용 하 여 내부 회사 파일을 로컬 드라이브에 동기화 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="0bd4b-151">SharePoint 사이트로 이동 하 고 로컬 장치에서 보거나 편집 하는 데 관심이 있는 파일에 대 한 최상위 문서 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="0bd4b-152">SharePoint 리본의 위쪽에 있는 **동기화** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="0bd4b-153">**이 사이트에서 Microsoft OneDrive를 열려고 하**고 있습니다 팝업에서 **열기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="0bd4b-154">작업 표시줄의 오른쪽 아래에 있는 OneDrive 아이콘을 선택 하 여 SharePoint 파일이 로컬 드라이브와 동기화 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="0bd4b-155">파일이 온라인 상태를 유지 하도록 설정 되어 있는지 확인 하 고 사용 하는 동안에만 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="0bd4b-156">파일 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-156">Open file explorer.</span></span>
    
    2. <span data-ttu-id="0bd4b-157">SharePoint 이름을 탐색 하 고 마우스 오른쪽 단추를 클릭 합니다. 예를 들어 \*\*Contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-157">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="0bd4b-158">**공간 확보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-158">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="0bd4b-159">상태 열에 파일 및 폴더 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="0bd4b-160">자세한 내용은 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> OneDrive 동기화 클라이언트를 사용 하 여 SharePoint 파일 동기화를 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-160">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="0bd4b-161">팀 채널 파일은 버전 기록을 비롯 하 여 동일한 모든 SharePoint 문서 기능을 사용 하 여 SharePoint 사이트에 저장 되며 로컬 데스크톱 장치와 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="0bd4b-162">팀 채널 파일을 동기화 하려면:</span><span class="sxs-lookup"><span data-stu-id="0bd4b-162">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="0bd4b-163">관심 있는 팀 채널로 이동 하 고 맨 위에 있는 **파일** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-163">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="0bd4b-164">그런 다음 **동기화**를 선택 합니다. 파일이 동기화가 시작 되 고 \*\*데스크톱 \ Contoso \ \<name of the Teams Channel\> \*\*의 파일 탐색기에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="0bd4b-165">SharePoint 사이트를 동기화 하는 데 사용한 것과 동일한 절차를 사용 하 여 클라우드에 파일을 보관 하 고, 팀 채널 이름의 파일 탐색기를 탭 하 고 마우스 오른쪽 단추로 클릭 한 다음 **공간 확보**를 선택 하 여 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="0bd4b-166">Surface Hub 펜 설정</span><span class="sxs-lookup"><span data-stu-id="0bd4b-166">Surface Hub pen settings</span></span>

**<span data-ttu-id="0bd4b-167">Bluetooth Surface Hub 펜 페어링</span><span class="sxs-lookup"><span data-stu-id="0bd4b-167">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="0bd4b-168">펜 펌웨어를 최신 버전으로 유지 하 고 Bluetooth 장치 설정 페이지 또는 Surface app에서 배터리 충전 정보를 얻으려면 펜을 쌍으로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-168">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="0bd4b-169">**시작**  >  **설정**  >  **장치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-169">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="0bd4b-170">**Bluetooth 또는 기타 장치 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-170">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="0bd4b-171">**블루투스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-171">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="0bd4b-172">펜 꼬리 단추와 흔들기를 제거 하 여 배터리 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-172">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="0bd4b-173">뚜껑을 다시 연결 하 고, 연결 LED가 깜박이는 위치에 있는 뚜껑을 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-173">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="0bd4b-174">Surface Hub Bluetooth 설정에서 **Surface hub 2 펜**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-174">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="0bd4b-175">페어링 연산을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-175">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="0bd4b-176">페어링에 실패 한 경우에는 펜을 다시 연결 해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-176">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="0bd4b-177">그래도 작동 하지 않는 경우 화이트 보드 응용 프로그램에서 펜이 작동 하는지 확인 하 여 배터리가 충전 되었는지 테스트해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-177">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="0bd4b-178">그렇지 않은 경우 배터리를 교체한 다음 펜을 다시 페어링 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-178">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="0bd4b-179">필요한 경우 장치를 다시 시작한 다음 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-179">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="0bd4b-180">**펜 바로 가기 설정** Surface Hub 펜에는 "꼬리 클릭"이 라고도 하는 바로 가기 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-180">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="0bd4b-181">바로 가기를 구성 하려면 앞에서 설명한 대로 먼저 펜을 쌍으로 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-181">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="0bd4b-182">펜을 검색 하 고 **펜 & Windows Ink 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-182">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="0bd4b-183">페이지 아래쪽에서 다음과 같이 대화 상자를 여는 펜 바로 가기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-183">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![펜 바로 가기](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="0bd4b-185">카메라 구성</span><span class="sxs-lookup"><span data-stu-id="0bd4b-185">Camera configuration</span></span>

<span data-ttu-id="0bd4b-186">디바이스의 위쪽 또는 양쪽에 카메라를 탑재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-186">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="0bd4b-187">카메라를 사용 하는 경우, 카트 대신 데스크탑이 스탠드에 있거나 허브에 가까운 위치에 있는 경우 카메라 각도를 최적화할 수 있는 한 눈에 카메라를 마운트합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-187">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="0bd4b-188">카메라가 자동으로 회전 하지 않으므로 수동으로 카메라를 회전 하려면 2mm 16 진수 키를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-188">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="0bd4b-189">카메라를 직접 탑재 하 고 카메라를 수동으로 회전 하는 방법에 대 한 자세한 내용은 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S 카메라 렌즈 방향을 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-189">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="0bd4b-190">Windows Hello 구성</span><span class="sxs-lookup"><span data-stu-id="0bd4b-190">Windows Hello configuration</span></span>

<span data-ttu-id="0bd4b-191">Windows 10 Enterprise를 실행 하는 Surface Hub 2S는 Win32 데스크톱 응용 프로그램의 전체 제품군과 생체 인식 Windows Hello 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-191">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="0bd4b-192">Surface Hub 2 지문 인식기 액세서리는 장치의 USB-C 포트에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-192">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="0bd4b-193">Surface Hub 2 지문 인식기를 주문 하거나 기술 사양을 보려면 Windows 10 Pro 및 Surface Hub 2에서 엔터프라이즈의 surface-hub-2-essential-add-ons.md "target =" _blank ">필수 추가 기능을 참조 </a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-193">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="0bd4b-194">지문 판독기를 삽입 한 후에 **Start**는  >  **설정**시작  >  **계정**  >  **로그인 옵션**  >  **Windows Hello 지문을** 선택 하 여 지문을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-194">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="0bd4b-195">얼굴 인식을 위해 Windows Hello 인증 디바이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-195">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="0bd4b-196">Surface Hub 2S 카메라는 Windows Hello 얼굴 인식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-196">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="0bd4b-197">작업 표시줄에서 잠금 화면 바로 가기 아이콘 사용</span><span class="sxs-lookup"><span data-stu-id="0bd4b-197">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="0bd4b-198">Windows-L 바로 가기 키와 비슷한 터치 스크린 잠금 기능을 사용할 수 있도록 하는 아이콘을 작업 표시줄에 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-198">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="0bd4b-199">바탕 화면을 길게 누르거나 마우스 오른쪽 단추로 클릭 하 고 **새**  >  **바로 가기**  >  **찾아보기**  >  **바탕 화면**  >  **확인**  >  **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-199">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="0bd4b-200">바로 가기의 이름 (예: **내 PC 잠금**)을 입력 한 다음 **마침을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-200">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="0bd4b-201">바탕 화면에서 새로 만든 바로 가기를 마우스 오른쪽 단추로 클릭 하거나 길게 탭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-201">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="0bd4b-202">**바로 가기** 탭에서 **대상** 필드에 다음을 입력 합니다: **Rundll32.exe User32.dll, lockworkstation**</span><span class="sxs-lookup"><span data-stu-id="0bd4b-202">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="0bd4b-203">**아이콘 변경** 단추를 선택 하 고 **C:\Windows\System32\imageres.dll** 으로 이동 하 여 사용할 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-203">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="0bd4b-204">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-204">See the following example:</span></span>

    ![아이콘 선택](images/lock.png)
    
1.  <span data-ttu-id="0bd4b-206">**확인** 을 선택 하 여 바로 가기를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-206">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="0bd4b-207">바로 가기를 마우스 오른쪽 단추로 클릭 하거나 길게 탭 하 고 **작업 표시줄에 고정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-207">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="0bd4b-208">작업 표시줄에 대 한 잠금 바로 가기를 고정 한 후에는 바탕 화면에서 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-208">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="0bd4b-209">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="0bd4b-209">Applications</span></span>

### <span data-ttu-id="0bd4b-210">설치 된 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="0bd4b-210">Update installed apps</span></span>

<span data-ttu-id="0bd4b-211">설치 된 모든 스토어 앱을 업데이트 하려면:</span><span class="sxs-lookup"><span data-stu-id="0bd4b-211">To update all installed Store apps:</span></span>

1. <span data-ttu-id="0bd4b-212">Microsoft Store 앱을 열고 오른쪽 위 모서리에 있는 **더 많은 줄임표 참조** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-212">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>

2. <span data-ttu-id="0bd4b-213">**다운로드 및 업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-213">Select **Downloads and updates**.</span></span>

2. <span data-ttu-id="0bd4b-214">**업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-214">Select **Get updates**.</span></span>

### <span data-ttu-id="0bd4b-215">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="0bd4b-215">Microsoft Whiteboard</span></span>

<span data-ttu-id="0bd4b-216">Microsoft 화이트 보드를 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-216">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="0bd4b-217">작업 표시줄의 오른쪽 아래에 있는 **Windows Ink 작업 영역** 아이콘을 선택 하 고 **화이트 보드**를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-217">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![잉크 작업 영역](images/ink.png) 

<span data-ttu-id="0bd4b-219">또는 Microsoft Store에서 화이트 보드를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-219">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="0bd4b-220">Microsoft Store 앱을 열고 **화이트 보드**를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-220">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="0bd4b-221">장치에서 로그인 하 여 사용 하도록 **아니요 감사** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-221">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="0bd4b-222">화이트 보드를 작업 표시줄에 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-222">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="0bd4b-223">Surface app</span><span class="sxs-lookup"><span data-stu-id="0bd4b-223">Surface app</span></span>

1. <span data-ttu-id="0bd4b-224">Microsoft Store에서 **Surface**를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-224">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="0bd4b-225">**모든 장치**에 **사용 가능** 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-225">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="0bd4b-226">**Surface** 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-226">Install the **Surface** app.</span></span> <span data-ttu-id="0bd4b-227">나열 된 첫 번째 앱 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-227">This should be the first app listed.</span></span> <span data-ttu-id="0bd4b-228">앱을 설치 하기 위해 MSA를 스토어에 연결 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-228">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="0bd4b-229">**Surface** 앱을 작업 표시줄에 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-229">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="0bd4b-230">캡처 및 스케치</span><span class="sxs-lookup"><span data-stu-id="0bd4b-230">Snip & Sketch</span></span>

1. <span data-ttu-id="0bd4b-231">**캡처 & 스케치** 앱을 열고 작업 표시줄에 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-231">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="0bd4b-232">오른쪽 위 모서리에 있는 줄임표를 선택 하 고 **설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-232">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="0bd4b-233">**설정**에서 **클립보드에 자동 복사**, **캡처**및 **여러 창** (선택 사항)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-233">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="0bd4b-234">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="0bd4b-234">Microsoft Office</span></span>

1. <span data-ttu-id="0bd4b-235"><a href="https://portal.office.com/account#installs" target="_blank">Office 포털을 열고 </a> 원하는 응용 프로그램을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-235">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="0bd4b-236">원하는 Office 응용 프로그램을 작업 표시줄에 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-236">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="0bd4b-237">Outlook이 설치 되어 있는 경우 마지막 2 주 캐시만 저장 하도록 Outlook OST를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-237">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="0bd4b-238">이렇게 하면 디스크 사용량 및 설정 시간이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-238">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="0bd4b-239">**파일**  >  **계정 설정을** 선택 하 고 계정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-239">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="0bd4b-240">**변경을** 선택 하 고 **캐시 된 Exchange 모드 사용** 에 대 한 슬라이더를 14 일로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-240">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="0bd4b-241">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0bd4b-241">Microsoft Teams</span></span>

1. <span data-ttu-id="0bd4b-242">Microsoft 팀을 다운로드 하 고 설치 <a href="https://teams.microsoft.com/downloads" target="_blank"> </a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-242">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="0bd4b-243">응용 프로그램 자동 시작에 대 한 설정을 구성 합니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="0bd4b-243">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="0bd4b-244">팀을 작업 표시줄에 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-244">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="0bd4b-245">혼란을 방지 하기 위해 장치에서 팀 알림을 줄이는 것이 좋습니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="0bd4b-245">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![팀 알림](images/teams.png)

### <span data-ttu-id="0bd4b-247">앱 연결</span><span class="sxs-lookup"><span data-stu-id="0bd4b-247">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bd4b-248">Windows 10 버전 2004 이상에서는 Miracast를 사용 하 여 무선 프로젝션 용 연결 앱이 기본적으로 설치 되지 않지만 선택적 기능으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-248">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="0bd4b-249">Windows 버전 2004 이상을 설치 (또는 업데이트) 한 경우 설정에서 다음 PC로 투영 화면에 다음이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-249">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![이 PC에 프로젝트](images/sh2-project.png) 


1. <span data-ttu-id="0bd4b-251">"이 PC에 투영" 설정 페이지에서 앱을 설치 하려면, **선택적 기능**을 선택 하  >  고**기능을 추가한** 다음 **무선 디스플레이** 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-251">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="0bd4b-252">**일부 Windows 및 Android 장치에서이 PC에 프로젝트를 수행할 수 있습니다 (확인**).</span><span class="sxs-lookup"><span data-stu-id="0bd4b-252">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="0bd4b-253">장치가 회사 네트워크에 있지 않은 경우 **어디서 나 사용할 수 있습니다** .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-253">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="0bd4b-254">그렇지 않은 경우 **에는 보안 네트워크에서 어디서 나 사용 가능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-254">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="0bd4b-255">**이 PC에 프로젝트를 요청할** **때 첫 번째 시간만**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-255">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="0bd4b-256">연결 **에 PIN 필요**에서 **안 함을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-256">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="0bd4b-257">그런 다음 앱을 시작 하 고 작업 표시줄에 고정 하 여 **연결**을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-257">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="0bd4b-258">앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-258">Open the app.</span></span> <span data-ttu-id="0bd4b-259">앱이 열려 있는 동안 작업 표시줄에서 앱 연결 아이콘을 마우스 오른쪽 단추로 클릭 하 고 **작업 표시줄에 고정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-259">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="0bd4b-260">그런 다음 연결 앱을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-260">Then close the Connect app.</span></span> <span data-ttu-id="0bd4b-261">앱이 한 번 이상 실행 되지 않으면 **이 PC에 대 한 프로젝트가** 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-261">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="0bd4b-262">회사 네트워크를 사용할 수 없는 경우 권장 되는 구성:</span><span class="sxs-lookup"><span data-stu-id="0bd4b-262">Recommended configuration when not on the corporate network:</span></span>

![집에서 설정](images/project1.png)

<span data-ttu-id="0bd4b-264">회사 네트워크의 권장 구성:</span><span class="sxs-lookup"><span data-stu-id="0bd4b-264">Recommended configuration on the corporate network:</span></span>

![회사의 설정](images/project2.png)

### <span data-ttu-id="0bd4b-266">사용자 휴대폰</span><span class="sxs-lookup"><span data-stu-id="0bd4b-266">Your Phone</span></span>

<span data-ttu-id="0bd4b-267">**휴대폰** 앱은 Windows 10에 기본적으로 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-267">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="0bd4b-268">표시 되지 않는 경우 Windows 스토어에서 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-268">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="0bd4b-269">앱을 설정 하는 방법에 대 한 자세한 내용은 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> Windows 10에서 휴대폰을 설정 하 고 PC와 휴대폰 간에 데이터를 동기화 하는 방법을 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-269">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="0bd4b-270">또한 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Windows 10의 휴대폰 앱에 대 한 일반적인 문제를 해결 하는 방법을 알아봅니다 </a> .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-270">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

### <span data-ttu-id="0bd4b-271">수퍼 팬시 영역</span><span class="sxs-lookup"><span data-stu-id="0bd4b-271">Super Fancy Zones</span></span>

<span data-ttu-id="0bd4b-272">**수퍼 팬시 영역은** 사용자가 화면 공간을 최대화 하도록 창을 정렬 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-272">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="0bd4b-273">이제 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub의 PowerToys에 포함 되어 있습니다 </a> .</span><span class="sxs-lookup"><span data-stu-id="0bd4b-273">It is now included in <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub.</span></span>

### <span data-ttu-id="0bd4b-274">Edge Chromium 브라우저</span><span class="sxs-lookup"><span data-stu-id="0bd4b-274">Edge Chromium browser</span></span>

<span data-ttu-id="0bd4b-275">새 Edge Chromium 브라우저를 다운로드 하 여 설치 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> </a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-275">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="0bd4b-276">Surface Hub 하드웨어 진단 도구</span><span class="sxs-lookup"><span data-stu-id="0bd4b-276">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="0bd4b-277"><a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> </a> Microsoft Store에서 무료로 제공 되는 Surface Hub 하드웨어 진단 도구</span><span class="sxs-lookup"><span data-stu-id="0bd4b-277">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="0bd4b-278">이 도구는 Surface Hub가 가장 적절 하 게 진행 되 고 있는지 확인 하는 데 도움이 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-278">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="0bd4b-279">이 앱에는 펌웨어가 최신 상태 이며 올바르게 구성 되었는지 확인 하는 테스트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-279">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="0bd4b-280">대화형 테스트를 통해 필수 기능이 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-280">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="0bd4b-281">문제가 발생하는 경우, 결과를 저장하고 Surface Hub 지원 팀과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-281">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="0bd4b-282">링크를 클릭 하 여 Microsoft Store에서 설치 하 고 작업 표시줄에 응용 프로그램을 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-282">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="0bd4b-283">추가 설정</span><span class="sxs-lookup"><span data-stu-id="0bd4b-283">Additional settings</span></span>

### <span data-ttu-id="0bd4b-284">펜 꼬리 화이트 보드 시작을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-284">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="0bd4b-285">**펜** 을 검색 하 고 **펜 & Windows Ink 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-285">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="0bd4b-286">페이지 아래쪽의 **펜 바로 가기** 에서 **Microsoft 화이트 보드**에 **한 번 선택을** 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-286">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="0bd4b-287">전원 관리</span><span class="sxs-lookup"><span data-stu-id="0bd4b-287">Power management</span></span>

<span data-ttu-id="0bd4b-288">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise를 사용 하 여 최상의 환경을 얻는 데 사용할 수 있는 여러 가지 전원 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-288">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="0bd4b-289">여기에는 화면 및 pc 시간 제한과 기본 제공 되는 사용자 감지 검사 (도플러), 화면 보호기 및 암호 보호와의 상호 작용 방식, 그리고 랩톱/데스크톱 사용자를 위한 그룹 정책 전원 설정에 대 한 적절 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-289">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="0bd4b-290">Surface Hub 2의 Windows 10 Pro 또는 Enterprise는 터치, 마우스, 키보드 동작, 그리고 기본 제공 되는 사용자 선점 감지 (도플러)를 통해 화면을 절전 모드로 전환 하는 것을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-290">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="0bd4b-291">사용자의 선점 감지 기능은 기본적으로 사용 되지만, 필요한 경우 초기 마이그레이션의 일부로 Surface UEFI 구성자 도구에서 장치 옵션을 전환 하거나, 이후 UEFI 구성 패키지를 빌드하고 적용 하 여 UEFI에서 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-291">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="0bd4b-292">전원 관리: 화면 및 PC 절전 모드 설정</span><span class="sxs-lookup"><span data-stu-id="0bd4b-292">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="0bd4b-293">**시작**  >  **설정**  >  **시스템**  >  **전원 & 절전**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-293">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="0bd4b-294">Power mode 슬라이더를 **최적의 성능**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-294">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="0bd4b-295">화면 및 절전 모드 값을 기본 설정으로 구성 하 고 이동이 감지 되는 경우 장치를 종료 하는 도플러 현재 상태 감지도 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-295">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="0bd4b-296">따라서 최상의 방법으로, **2 시간이 지난 후** PC가 **4 시간 후** 에 꺼지도록 화면을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-296">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="0bd4b-297">전원 관리: 화면 보호기</span><span class="sxs-lookup"><span data-stu-id="0bd4b-297">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="0bd4b-298">**잠금 화면** 을 검색 하 고 **잠금 화면 설정을**엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-298">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="0bd4b-299">**화면 시간 제한 설정** 및 **화면 보호기 설정을** 기본 설정으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-299">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="0bd4b-300">권장 되는 기본 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-300">Recommended default values are:</span></span>

   - <span data-ttu-id="0bd4b-301">화면 보호기를 (없음) 또는 원하는 화면 보호기로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-301">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="0bd4b-302">대기 시간을 15 분으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-302">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="0bd4b-303">다시 시작할 때 로그온 화면을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-303">On resume, display logon screen.</span></span>


**<span data-ttu-id="0bd4b-304">전원 관리: 그룹 정책</span><span class="sxs-lookup"><span data-stu-id="0bd4b-304">Power Management: Group Policy</span></span>**

<span data-ttu-id="0bd4b-305">다음 절차를 수행 하기 전에, 승인에 대 한 IT 부서에 문의 하 여 전역 전원 관리 정책에서 Surface Hub 2S 장치를 제외 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-305">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="0bd4b-306">일부 전원 관리 설정에서는 현재 상태 감지 기능을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-306">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="0bd4b-307">**소프트웨어 센터** 를 검색 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-307">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="0bd4b-308">**옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-308">Select **Options**.</span></span>

3. <span data-ttu-id="0bd4b-309">**전원 관리** 를 확장 하 고 **IT 부서의 전원 설정을이 컴퓨터에 적용 하지 않음을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-309">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![소프트웨어 설정](images/soft-cntr.png)

### <span data-ttu-id="0bd4b-311">저장소 센스</span><span class="sxs-lookup"><span data-stu-id="0bd4b-311">Storage Sense</span></span>

<span data-ttu-id="0bd4b-312">Surface Hub 2는 로컬 저장소에 대 한 128GB SSD를가지고 있으므로 일반적인 사용 중에 저장소 저장 측정값을 사용 하는 것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-312">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="0bd4b-313">저장소 감지를 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-313">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="0bd4b-314">**시스템 설정**에서 찾은 **저장소 설정을**검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-314">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="0bd4b-315">**설정**에서 **저장소 센스 사용** 을 선택 하 여 **저장소** 설정 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-315">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="0bd4b-316">저장소 **감지를 설정으로 전환**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-316">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="0bd4b-317">**저장소 센스 구성 또는 지금 실행** 을 선택 하 고 드라이브 공간 제한으로 인해 파일을 온라인 상태로 유지 하는 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-317">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="0bd4b-318">권장 설정:</span><span class="sxs-lookup"><span data-stu-id="0bd4b-318">Recommended settings:</span></span>

- <span data-ttu-id="0bd4b-319">저장소 센스를 실행 합니다 = 매일</span><span class="sxs-lookup"><span data-stu-id="0bd4b-319">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="0bd4b-320">내 앱에서 사용 하 고 있지 않은 임시 파일을 삭제 합니다. = 14 일 마다 (최소)</span><span class="sxs-lookup"><span data-stu-id="0bd4b-320">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="0bd4b-321">내 다운로드 폴더에 있는 파일을 지난 30 일 동안 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-321">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="0bd4b-322">OneDrive: 최대 30 일 동안 열리지 않으면 콘텐츠가 온라인 전용 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-322">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="0bd4b-323">태블릿 모드</span><span class="sxs-lookup"><span data-stu-id="0bd4b-323">Tablet mode</span></span>

<span data-ttu-id="0bd4b-324">원하는 경우 태블릿 모드를 사용 하 여 접근성을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-324">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="0bd4b-325">소리 설정</span><span class="sxs-lookup"><span data-stu-id="0bd4b-325">Sound settings</span></span>

1. <span data-ttu-id="0bd4b-326">**소리 설정을** 검색 하 고이 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-326">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="0bd4b-327">오른쪽에 있는 **사운드 제어판** 을 선택 하 고 **소리** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-327">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="0bd4b-328">**프로그램 이벤트** 에서 **장치 연결** 및 **장치를 연결 해제** 하도록 설정 합니다. **None**</span><span class="sxs-lookup"><span data-stu-id="0bd4b-328">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="0bd4b-329">침묵 알림</span><span class="sxs-lookup"><span data-stu-id="0bd4b-329">Silence notifications</span></span>

1. <span data-ttu-id="0bd4b-330">**포커스 지원을** 검색 하 고이 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-330">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="0bd4b-331">**알람만**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-331">Select **Alarms Only**.</span></span> <span data-ttu-id="0bd4b-332">이는 일정 한 알림 플라이 아웃을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-332">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="0bd4b-333">디스크 정리</span><span class="sxs-lookup"><span data-stu-id="0bd4b-333">Disk Cleanup</span></span>

1. <span data-ttu-id="0bd4b-334">**디스크 정리** 를 검색 하 고이 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-334">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="0bd4b-335">**삭제할 파일**에서 삭제할 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-335">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="0bd4b-336">또한 **시스템 파일 정리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-336">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="0bd4b-337">완료 및 확인</span><span class="sxs-lookup"><span data-stu-id="0bd4b-337">Complete and verify</span></span>

1. <span data-ttu-id="0bd4b-338">모든 Windows 업데이트를 검색 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-338">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="0bd4b-339">그룹 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="0bd4b-339">Update Group Policy</span></span>

   1. <span data-ttu-id="0bd4b-340">관리자 권한 명령 프롬프트에서 **gpupdate/force/boot/wait: 0**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-340">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="0bd4b-341">디바이스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-341">Restart the device.</span></span>

4. <span data-ttu-id="0bd4b-342">작업 표시줄 앱을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-342">Verify taskbar apps.</span></span>

   - <span data-ttu-id="0bd4b-343">앱 연결</span><span class="sxs-lookup"><span data-stu-id="0bd4b-343">Connect App</span></span>
   - <span data-ttu-id="0bd4b-344">잠금 아이콘</span><span class="sxs-lookup"><span data-stu-id="0bd4b-344">Lock Icon</span></span>
   - <span data-ttu-id="0bd4b-345">캡처 및 스케치</span><span class="sxs-lookup"><span data-stu-id="0bd4b-345">Snip & Sketch</span></span>
   - <span data-ttu-id="0bd4b-346">팀 (해당 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="0bd4b-346">Teams (if applicable)</span></span>
   - <span data-ttu-id="0bd4b-347">Office 앱 (해당 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="0bd4b-347">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="0bd4b-348">Surface App</span><span class="sxs-lookup"><span data-stu-id="0bd4b-348">Surface App</span></span>
   - <span data-ttu-id="0bd4b-349">화이트보드</span><span class="sxs-lookup"><span data-stu-id="0bd4b-349">Whiteboard</span></span>
    
5. <span data-ttu-id="0bd4b-350">현재 상태 감지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-350">Verify presence detection.</span></span>

   - <span data-ttu-id="0bd4b-351">현재 상태 감지는 시스템 트레이에 녹색 아이콘으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-351">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="0bd4b-352">이 PC로의 예측은 Connect 앱에서 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-352">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="0bd4b-353">**Project를이 PC 설정으로** 구성한 후에는 적어도 한 번 연결 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-353">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="0bd4b-354">(따라서 Surface Hub에 투영할 수 있도록 연결 앱을 실행할 필요가 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="0bd4b-354">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="0bd4b-355">전원 및 절전 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-355">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="0bd4b-356">화면 보호기: 15 분, (없음), Mystify 또는 Blank로 설정 암호 요구 확인란을 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-356">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="0bd4b-357">화면: **2 시간 후에 종료**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-357">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="0bd4b-358">PC: **4 시간 후 종료**</span><span class="sxs-lookup"><span data-stu-id="0bd4b-358">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="0bd4b-359">Windows Hello가 작동 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-359">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="0bd4b-360">동기화 설정이 비활성화 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-360">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="0bd4b-361">시작 앱을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-361">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="0bd4b-362">Windows 10을 설치 하 고 구성한 후 Surface Hub 2S는 다른 Windows 10 디바이스와 같은 방식으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd4b-362">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="0bd4b-363">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0bd4b-363">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="0bd4b-364">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0bd4b-364">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
