---
title: 세션 종료 - Surface Hub 모임 종료
description: Surface Hub 모임을 종료하려면 세션 종료를 탭합니다. Surface Hub가 응용 프로그램 상태, 운영 체제 상태 및 사용자 인터페이스를 정리하므로 Surface Hub에서 다음 모임을 준비할 수 있습니다.
keywords: 완료, Surface Hub 모임 종료, Surface Hub 모임 마침, Surface Hub 모임 정리
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836236"
---
# <span data-ttu-id="89914-105">세션 종료를 사용하여 Surface Hub 모임 종료</span><span class="sxs-lookup"><span data-stu-id="89914-105">End a Surface Hub meeting with End session</span></span>
<span data-ttu-id="89914-106">Surface Hub는 여러 사용자 그룹이 모임 공간에서 사용하도록 설계된 공동 작업 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="89914-106">Surface Hub is a collaboration device designed to be used in meeting spaces by different groups of people.</span></span> <span data-ttu-id="89914-107">모임이 끝나면 사용자가 **세션 종료**를 탭하여 중요한 데이터를 정리하고 다음 모임을 위해 장치를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-107">At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting.</span></span> <span data-ttu-id="89914-108">Surface Hub는 다음 상태를 정리 또는 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-108">Surface Hub will clean up, or reset, the following states:</span></span>
- <span data-ttu-id="89914-109">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="89914-109">Applications</span></span>
- <span data-ttu-id="89914-110">운영 체제</span><span class="sxs-lookup"><span data-stu-id="89914-110">Operating system</span></span>
- <span data-ttu-id="89914-111">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89914-111">User interface</span></span>

<span data-ttu-id="89914-112">이 항목에서는 **세션 종료** 기능이 이러한 각각의 상태에 대해 초기화하는 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-112">This topic explains what **End session** resets for each of these states.</span></span>

## <span data-ttu-id="89914-113">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="89914-113">Applications</span></span>
<span data-ttu-id="89914-114">Surface Hub에서 앱을 시작하면 해당 앱은 메모리에 저장되며 데이터는 응용 프로그램 수준에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89914-114">When you start apps on Surface Hub, they are stored in memory and data is stored at the application level.</span></span> <span data-ttu-id="89914-115">이때 데이터가 제거되거나 덮어쓰일 때까지 해당 세션(또는 모임) 중에 모든 사용자가 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-115">Data is available to all users during that session (or meeting) until date is removed or overwritten.</span></span> <span data-ttu-id="89914-116">**세션 종료**를 선택하면 Surface Hub에서 응용 프로그램을 닫고 브라우저 기록을 삭제하고 응용 프로그램을 초기화하고 Skype 기록을 제거하여 응용 프로그램 상태를 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-116">When **End session** is selected, Surface Hub application state is cleared out by closing applications, deleting browser history, resetting applications, and removing Skype logs.</span></span>

### <span data-ttu-id="89914-117">응용 프로그램 닫기</span><span class="sxs-lookup"><span data-stu-id="89914-117">Close applications</span></span>
<span data-ttu-id="89914-118">Surface Hub는 Win32 및 UWP(유니버설 Windows 플랫폼) 응용 프로그램을 비롯하여 표시된 모든 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-118">Surface Hub closes all visible windows, including Win32 and Universal Windows Platform (UWP) applications.</span></span> <span data-ttu-id="89914-119">응용 프로그램 닫기 단계에서는 표시된 창에 쿼리하는 데 멀티태스킹 보기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-119">The application close stage uses the multitasking view to query the visible windows.</span></span> <span data-ttu-id="89914-120">특정 시간 내에 닫히지 않는 Win32 창은 **TerminateProcess**를 사용하여 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-120">Win32 windows that do not close within a certain timeframe are closed using **TerminateProcess**.</span></span> 
   
### <span data-ttu-id="89914-121">브라우저 기록 삭제</span><span class="sxs-lookup"><span data-stu-id="89914-121">Delete browser history</span></span>
<span data-ttu-id="89914-122">Surface Hub는 Edge의 DBH(브라우저 기록 삭제)를 사용하여 Edge 기록 및 캐시된 데이터를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="89914-122">Surface Hub uses Delete Browser History (DBH) in Edge to clear Edge history and cached data.</span></span> <span data-ttu-id="89914-123">이는 사용자가 해당 브라우저 기록을 수동으로 정리하는 방법과 유사하지만, **세션 종료**도 다음 세션 또는 모임이 시작되기 전에 응용 프로그램 상태를 정리하고 데이터를 제거하는 확실한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="89914-123">This is similar to how a user can clear out their browser history manually, but **End session** also ensures that application states are cleared and data is removed before the next session, or meeting, starts.</span></span> 
 
### <span data-ttu-id="89914-124">응용 프로그램 초기화</span><span class="sxs-lookup"><span data-stu-id="89914-124">Reset applications</span></span>
<span data-ttu-id="89914-125">**세션 종료**는 Surface Hub에 설치된 각 응용 프로그램의 상태를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-125">**End session** resets the state of each application that is installed on the Surface Hub.</span></span> <span data-ttu-id="89914-126">응용 프로그램을 초기화하면 모든 백그라운드 작업, 응용 프로그램 데이터, 알림 및 사용자 동의 대화 상자가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="89914-126">Resetting an application clears all background tasks, application data, notifications, and user consent dialogs.</span></span> <span data-ttu-id="89914-127">응용 프로그램이 Surface Hub를 사용하는 다음 사람을 위해 첫 실행 상태로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="89914-127">Applications are returned to their first-run state for the next people that use Surface Hub.</span></span>  
 
### <span data-ttu-id="89914-128">Skype 로그 제거</span><span class="sxs-lookup"><span data-stu-id="89914-128">Remove Skype logs</span></span>
<span data-ttu-id="89914-129">Skype는 Surface Hub에 개인 식별 정보를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-129">Skype does not store personally-identifiable information on Surface Hub.</span></span> <span data-ttu-id="89914-130">정보는 기존 비즈니스용 Skype 지침에 부합되게 Skype 서비스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89914-130">Information is stored in the Skype service to meet existing Skype for Business guidance.</span></span> <span data-ttu-id="89914-131">로컬 Skype 로깅 정보가 **세션 종료** 선택 시 제거되는 유일한 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="89914-131">Local Skype logging information is the only data removed when **End session** is selected.</span></span> <span data-ttu-id="89914-132">여기에는 UCCP(Unified Communications Client Platform) 로그 및 미디어 로그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="89914-132">This includes Unified Communications Client Platform (UCCP) logs and media logs.</span></span>   

## <span data-ttu-id="89914-133">운영 체제</span><span class="sxs-lookup"><span data-stu-id="89914-133">Operating System</span></span>
<span data-ttu-id="89914-134">운영 체제는 각각의 Surface Hub 모임 이후 정리해야 하는 세션의 상태에 대한 다양한 정보를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-134">The operating system hosts a variety of information about the state of the sessions that needs to be cleared after each Surface Hub meeting.</span></span> 

### <span data-ttu-id="89914-135">파일 시스템</span><span class="sxs-lookup"><span data-stu-id="89914-135">File System</span></span>
<span data-ttu-id="89914-136">모임 참석자가 Surface Hub에서 제한된 디렉터리 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-136">Meeting attendees have access to a limited set of directories on the Surface Hub.</span></span> <span data-ttu-id="89914-137">**세션 종료**를 선택하면 Surface Hub가 다음 디렉터리를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="89914-137">When **End session** is selected, Surface Hub clears these directories:</span></span><br>
- <span data-ttu-id="89914-138">음악</span><span class="sxs-lookup"><span data-stu-id="89914-138">Music</span></span>
- <span data-ttu-id="89914-139">비디오</span><span class="sxs-lookup"><span data-stu-id="89914-139">Videos</span></span>
- <span data-ttu-id="89914-140">문서</span><span class="sxs-lookup"><span data-stu-id="89914-140">Documents</span></span>
- <span data-ttu-id="89914-141">사진</span><span class="sxs-lookup"><span data-stu-id="89914-141">Pictures</span></span>
- <span data-ttu-id="89914-142">다운로드</span><span class="sxs-lookup"><span data-stu-id="89914-142">Downloads</span></span>

<span data-ttu-id="89914-143">또한 여러 응용 프로그램에서 대개 다음 디렉터리에 쓰기 때문에 Surface Hub는 다음 디렉터리도 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="89914-143">Surface Hub also clears these directories, since many applications often write to them:</span></span>
- <span data-ttu-id="89914-144">데스크톱</span><span class="sxs-lookup"><span data-stu-id="89914-144">Desktop</span></span>
- <span data-ttu-id="89914-145">즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="89914-145">Favorites</span></span>
- <span data-ttu-id="89914-146">최근 항목</span><span class="sxs-lookup"><span data-stu-id="89914-146">Recent</span></span>
- <span data-ttu-id="89914-147">공용 문서</span><span class="sxs-lookup"><span data-stu-id="89914-147">Public Documents</span></span>
- <span data-ttu-id="89914-148">공용 음악</span><span class="sxs-lookup"><span data-stu-id="89914-148">Public Music</span></span>
- <span data-ttu-id="89914-149">공용 비디오</span><span class="sxs-lookup"><span data-stu-id="89914-149">Public Videos</span></span>
- <span data-ttu-id="89914-150">공용 다운로드</span><span class="sxs-lookup"><span data-stu-id="89914-150">Public Downloads</span></span>

### <span data-ttu-id="89914-151">자격 증명</span><span class="sxs-lookup"><span data-stu-id="89914-151">Credentials</span></span>
<span data-ttu-id="89914-152">**세션 종료**를 탭하면 **TokenBroker**, **PasswordVault** 또는 **자격 증명 관리자**에 저장된 사용자 자격 증명이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="89914-152">User credentials that are stored in **TokenBroker**, **PasswordVault**, or **Credential Manager** are cleared when you tap **End session**.</span></span>

## <span data-ttu-id="89914-153">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89914-153">User interface</span></span>
<span data-ttu-id="89914-154">**세션 종료**를 선택하면 UI(사용자 인터페이스) 설정이 기본값으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="89914-154">User interface (UI) settings are returned to their default values when **End session** is selected.</span></span> 

### <span data-ttu-id="89914-155">UI 항목</span><span class="sxs-lookup"><span data-stu-id="89914-155">UI items</span></span>
- <span data-ttu-id="89914-156">기본 상태로 바로 가기 초기화</span><span class="sxs-lookup"><span data-stu-id="89914-156">Reset Quick Actions to default state</span></span>
- <span data-ttu-id="89914-157">알림 메시지 삭제</span><span class="sxs-lookup"><span data-stu-id="89914-157">Clear Toast notifications</span></span>
- <span data-ttu-id="89914-158">볼륨 수준 초기화</span><span class="sxs-lookup"><span data-stu-id="89914-158">Reset volume levels</span></span>
- <span data-ttu-id="89914-159">사이드바 너비 초기화</span><span class="sxs-lookup"><span data-stu-id="89914-159">Reset sidebar width</span></span>
- <span data-ttu-id="89914-160">태블릿 모드 레이아웃 초기화</span><span class="sxs-lookup"><span data-stu-id="89914-160">Reset tablet mode layout</span></span>
- <span data-ttu-id="89914-161">Office 365 모임 및 파일에서 사용자 로그아웃</span><span class="sxs-lookup"><span data-stu-id="89914-161">Sign user out of Office 365 meetings and files</span></span>

### <span data-ttu-id="89914-162">접근성</span><span class="sxs-lookup"><span data-stu-id="89914-162">Accessibility</span></span>
<span data-ttu-id="89914-163">**세션 종료**를 선택하면 접근성 기능 및 앱이 기본 설정으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="89914-163">Accessibility features and apps are returned to default settings when **End session** is selected.</span></span>
- <span data-ttu-id="89914-164">필터 키</span><span class="sxs-lookup"><span data-stu-id="89914-164">Filter keys</span></span>
- <span data-ttu-id="89914-165">고대비</span><span class="sxs-lookup"><span data-stu-id="89914-165">High contrast</span></span>
- <span data-ttu-id="89914-166">고정 키</span><span class="sxs-lookup"><span data-stu-id="89914-166">Sticky keys</span></span>
- <span data-ttu-id="89914-167">토글 키</span><span class="sxs-lookup"><span data-stu-id="89914-167">Toggle keys</span></span>
- <span data-ttu-id="89914-168">마우스 키</span><span class="sxs-lookup"><span data-stu-id="89914-168">Mouse keys</span></span>
- <span data-ttu-id="89914-169">돋보기</span><span class="sxs-lookup"><span data-stu-id="89914-169">Magnifier</span></span>
- <span data-ttu-id="89914-170">내레이터</span><span class="sxs-lookup"><span data-stu-id="89914-170">Narrator</span></span>

### <span data-ttu-id="89914-171">클립보드</span><span class="sxs-lookup"><span data-stu-id="89914-171">Clipboard</span></span>
<span data-ttu-id="89914-172">클립보드는 지워집니다. 즉, 세션 중 클립보드에 복사된 데이터가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="89914-172">The clipboard is cleared to remove data that was copied to the clipboard during the session.</span></span> 

## <span data-ttu-id="89914-173">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="89914-173">Frequently asked questions</span></span>
**<span data-ttu-id="89914-174">모임 종료 시 세션 종료를 탭하는 것을 잊었는데 나중에 다른 사람이 Surface Hub를 사용하는 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="89914-174">What happens if I forget to tap End session at the end of a meeting, and someone else uses the Surface Hub later?</span></span>**<br>
<span data-ttu-id="89914-175">Surface Hub는 사용자가 **세션 종료**를 탭할 경우에만 모임 콘텐츠를 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-175">Surface Hub only cleans up meeting content when users tap **End session**.</span></span> <span data-ttu-id="89914-176">**세션 종료**를 탭하지 않고 모임을 떠나면 잠시 후 장치가 시작 화면으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="89914-176">If you leave the meeting without tapping **End session**, the device will return to the welcome screen after some time.</span></span> <span data-ttu-id="89914-177">시작 화면에서 사용자는 이전 세션을 다시 시작하거나 새 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-177">From the welcome screen, users have the option to resume the previous session or start a new one.</span></span> <span data-ttu-id="89914-178">**세션 종료**를 누르지 않은 경우 세션을 다시 시작하는 기능을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-178">You can also disable the ability to resume a session if **End session** is not pressed.</span></span>

**<span data-ttu-id="89914-179">문서는 복구할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="89914-179">Are documents recoverable?</span></span>**<br> <span data-ttu-id="89914-180">**세션 종료**를 선택한 경우 하드 드라이브에서 파일을 제거하는 것은 하드 디스크 드라이브에서 다른 파일을 삭제하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="89914-180">Removing files from the hard drive when **End session** is selected is just like any other file deletion from a hard disk drive.</span></span> <span data-ttu-id="89914-181">타사 소프트웨어가 하드 디스크 드라이브에서 데이터를 복구할 수 있지만, 파일 복구가 Surface Hub에서 지원되는 기능은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="89914-181">Third-party software might be able to recover data from the hard disk drive, but file recovery is not a supported feature on Surface Hub.</span></span> <span data-ttu-id="89914-182">데이터 손실을 방지하려면 모임을 떠나기 전에 항상 필요한 데이터를 저장하세요.</span><span class="sxs-lookup"><span data-stu-id="89914-182">To prevent data loss, always save the data you need before leaving a meeting.</span></span>

**<span data-ttu-id="89914-183">세션 종료를 통한 정리 작업이 미 국방부의 정리 및 삭제 표준 DoD 5220.22-M을 준수하나요?</span><span class="sxs-lookup"><span data-stu-id="89914-183">Do the clean-up actions from End session comply with the US Department of Defense clearing and sanitizing standard: DoD 5220.22-M?</span></span>**<br>
<span data-ttu-id="89914-184">아니요.</span><span class="sxs-lookup"><span data-stu-id="89914-184">No.</span></span> <span data-ttu-id="89914-185">현재 **세션 종료**를 통한 정리 작업은 이 표준을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89914-185">Currently, the clean-up actions from **End session** do not comply with this standard.</span></span>  
  
