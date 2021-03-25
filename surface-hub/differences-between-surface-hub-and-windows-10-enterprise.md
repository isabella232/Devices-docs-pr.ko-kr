---
title: 운영 체제 필수 항목(Surface Hub)
description: 이 항목에서는 Windows 10 Team 운영 체제의 고유한 측면과 Windows 10 Enterprise와 어떻게 다른지 설명합니다.
keywords: 변경 내용
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/23/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 9c76f9405146c5cda4afe6b46ce7e1cce0062682
ms.sourcegitcommit: 88ce9e77afdc3d09984edc05286cd0f1eb054223
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448302"
---
# <a name="operating-system-essentials-surface-hub"></a><span data-ttu-id="a265e-104">운영 체제 필수 항목(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="a265e-104">Operating system essentials (Surface Hub)</span></span>

<span data-ttu-id="a265e-105">Surface Hub 운영 체제인 Windows 10 Team은 Windows 10 Enterprise를 기반으로 하며 엔터프라이즈 관리, 보안 및 기타 기능에 대한 풍부한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-105">The Surface Hub operating system, Windows 10 Team, is based on Windows 10 Enterprise, providing rich support for enterprise management, security, and other features.</span></span> <span data-ttu-id="a265e-106">그러나 둘 간에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-106">However, there are important differences between them.</span></span> <span data-ttu-id="a265e-107">Enterprise 버전은 PC용으로 설계되었지만 Windows 10 Team은 처음부터 큰 화면과 회의실용으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-107">While the Enterprise edition is designed for PCs, Windows 10 Team is designed from the ground up for large screens and meeting rooms.</span></span> <span data-ttu-id="a265e-108">Surface Hub에 대한 보안 및 관리 요구 사항을 평가하는 경우 새 운영 체제로 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-108">When you evaluate security and management requirements for Surface Hub, it's best to consider it as a new operating system.</span></span> <span data-ttu-id="a265e-109">이 문서는 Surface Hub의 Windows 10 Team과 Windows 10 Enterprise 간의 주요 차이점과 이러한 차이가 조직에 어떤 의미가 있는지를 설명하기 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-109">This article is designed to help highlight the key differences between Windows 10 Team on Surface Hub and Windows 10 Enterprise, and what the differences mean for your organization.</span></span>

<span data-ttu-id="a265e-110">2020년 9월부터 고객은 Surface Hub 2S에서 Windows 10 Pro 또는 Enterprise로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-110">Beginning in September 2020, customers have the option of migrating to Windows 10 Pro or Enterprise on Surface Hub 2S.</span></span> <span data-ttu-id="a265e-111">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a265e-111">To learn more, see the following:</span></span>

- <span data-ttu-id="a265e-112">[Surface Hub 2에서 Windows 10 Pro 및 Enterprise의 가용성 발표](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107)</span><span class="sxs-lookup"><span data-stu-id="a265e-112">[Announcing the availability of Windows 10 Pro and Enterprise on Surface Hub 2](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107).</span></span>

- [<span data-ttu-id="a265e-113">Surface Hub 2에서 Windows 10 Pro 또는 Enterprise로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a265e-113">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a><span data-ttu-id="a265e-114">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a265e-114">User interface</span></span>

### <a name="shell-os-user-interface"></a><span data-ttu-id="a265e-115">셸(OS 사용자 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="a265e-115">Shell (OS user interface)</span></span>

<span data-ttu-id="a265e-116">Surface Hub의 셸은 처음부터 큰 화면과 터치에 최적화되도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-116">The Surface Hub's shell is designed from the ground up to be large screen and touch optimized.</span></span> <span data-ttu-id="a265e-117">Windows 10 Enterprise와 동일한 셸을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-117">It doesn't use the same shell as Windows 10 Enterprise.</span></span>

*<span data-ttu-id="a265e-118">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-118">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-119">Windows 10 Enterprise 셸의 컨트롤과 관련된 설정은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-119">Settings related to controls in the Windows 10 Enterprise shell don't apply for Surface Hub.</span></span>

### <a name="lock-screen-and-screensaver"></a><span data-ttu-id="a265e-120">잠금 화면 및 화면 보호기</span><span class="sxs-lookup"><span data-stu-id="a265e-120">Lock screen and screensaver</span></span>

<span data-ttu-id="a265e-121">Surface Hub에는 잠금 화면이나 화면 보호기가 없지만 시작 화면이라는 유사한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-121">Surface Hub doesn't have a lock screen or a screen saver, but it has a similar feature called the welcome screen.</span></span> <span data-ttu-id="a265e-122">시작 화면에는 디바이스 계정 일정의 예약된 모임이 표시되며, Surface Hub의 인기 앱인 비즈니스용 Skype, 화이트보드 및 연결에 손쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-122">The welcome screen shows scheduled meetings from the device account's calendar, and easy entry points to the Surface Hub's top apps - Skype for Business, Whiteboard, and Connect.</span></span>

*<span data-ttu-id="a265e-123">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-123">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-124">잠금 화면, 화면 시간 제한 및 화면 보호기에 대한 설정은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-124">Settings for lock screen, screen timeout, and screen saver don't apply for Surface Hub.</span></span>

### <a name="user-sign-in"></a><span data-ttu-id="a265e-125">사용자 로그인</span><span class="sxs-lookup"><span data-stu-id="a265e-125">User sign-in</span></span>

<span data-ttu-id="a265e-126">Surface Hub는 회의실 등의 공용 공간에서 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-126">Surface Hub is designed to be used in communal spaces, such as meeting rooms.</span></span> <span data-ttu-id="a265e-127">Windows PC와 달리 누구든지 로그인하지 않고 Surface Hub를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-127">Unlike Windows PCs, anyone can walk up and use a Surface Hub without requiring a user to sign in.</span></span> <span data-ttu-id="a265e-128">이 공용 기능을 사용하기 위해 Surface Hub에서는 Windows 10 Enterprise와 동일한 방식의 Windows 로그인을 지원하지 않습니다(예: OS에 대한 사용자 로그인 및 OS 전체에 대한 자격 증명 사용).</span><span class="sxs-lookup"><span data-stu-id="a265e-128">To enable this communal functionality, Surface Hub does not support Windows sign-in the same way that Windows 10 Enterprise does (e.g., signing in a user to the OS and using those credentials throughout the OS).</span></span> <span data-ttu-id="a265e-129">대신, 항상 Surface Hub에 자동 로그인한 낮은 권한의 로컬 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-129">Instead, there is always a local, auto signed-in, low-privilege user signed in to the Surface Hub.</span></span> <span data-ttu-id="a265e-130">관리자(예: 관리자가 로그인할 때 OS에 로그인하지 않은 경우)를 포함하여 추가 사용자를 로그인하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-130">It doesn't support signing in any additional users, including admin users (e.g., when an admin signs in, they are not signed in to the OS).</span></span>

<span data-ttu-id="a265e-131">사용자는 Surface Hub에 로그인할 수 있지만 OS에 로그인하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-131">Users can sign in to a Surface Hub, but they will not be signed in to the OS.</span></span> <span data-ttu-id="a265e-132">예를 들어 사용자가 앱 또는 내 모임 및 파일에 로그인하면 사용자는 OS가 아니라 앱 또는 서비스에만 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-132">For example, when a user signs in to Apps or My Meetings and Files, the users is signed in only to the apps or services, not to the OS.</span></span> <span data-ttu-id="a265e-133">결과적으로 로그인한 사용자는 클라우드에 저장된 클라우드 파일과 개인 모임을 검색할 수 있으며 **세션 종료**가 활성화되면 이러한 자격 증명이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-133">As a result, the signed-in user is able to retrieve their cloud files and personal meetings stored in the cloud, and these credentials are discarded when **End session** is activated.</span></span>


*<span data-ttu-id="a265e-134">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-134">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-135">일반적으로 Surface Hub는 보안을 강화하기 위해 사용자 액세스 제어 대신 잠금 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-135">Generally, Surface Hub uses lockdown features rather than user access control to enforce security.</span></span> <span data-ttu-id="a265e-136">암호 요구 사항, 대화형 로그온, 사용자 계정 및 액세스 제어와 관련된 정책은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-136">Policies related to password requirements, interactive logon, user accounts, and access control don't apply for Surface Hub.</span></span>

### <a name="saving-and-browsing-files"></a><span data-ttu-id="a265e-137">파일 저장 및 검색</span><span class="sxs-lookup"><span data-stu-id="a265e-137">Saving and browsing files</span></span>

<span data-ttu-id="a265e-138">사용자는 Surface Hub에서 제한된 디렉터리 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-138">Users have access to a limited set of directories on the Surface Hub:</span></span>
- <span data-ttu-id="a265e-139">음악</span><span class="sxs-lookup"><span data-stu-id="a265e-139">Music</span></span>
- <span data-ttu-id="a265e-140">비디오</span><span class="sxs-lookup"><span data-stu-id="a265e-140">Videos</span></span>
- <span data-ttu-id="a265e-141">문서</span><span class="sxs-lookup"><span data-stu-id="a265e-141">Documents</span></span>
- <span data-ttu-id="a265e-142">사진</span><span class="sxs-lookup"><span data-stu-id="a265e-142">Pictures</span></span>
- <span data-ttu-id="a265e-143">다운로드</span><span class="sxs-lookup"><span data-stu-id="a265e-143">Downloads</span></span>

<span data-ttu-id="a265e-144">사용자가 **세션 종료**를 누르면 이러한 디렉터리에 로컬로 저장된 파일이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-144">Files saved locally in these directories are deleted when users press **End session**.</span></span> <span data-ttu-id="a265e-145">모임 중에 만든 콘텐츠를 저장하려면 USB 드라이브 또는 OneDrive에 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-145">To save content created during a meeting, users should save files to a USB drive or to OneDrive.</span></span>

*<span data-ttu-id="a265e-146">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-146">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-147">파일과 폴더의 액세스 권한 및 소유권과 관련된 정책은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-147">Policies related to access permissions and ownership of files and folders don't apply for Surface Hub.</span></span> <span data-ttu-id="a265e-148">사용자는 시스템 디렉터리 및 네트워크 폴더에서 파일을 찾거나 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-148">Users can't browse and save files to system directories and network folders.</span></span>

## <a name="applications"></a><span data-ttu-id="a265e-149">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a265e-149">Applications</span></span>

### <a name="default-applications"></a><span data-ttu-id="a265e-150">기본 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="a265e-150">Default applications</span></span>

<span data-ttu-id="a265e-151">몇 가지 예외를 제외하고 Surface Hub의 기본 UWP(유니버설 Windows 플랫폼) 앱은 Windows 10 PC에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-151">With few exceptions, the default Universal Windows Platform (UWP) apps on Surface Hub are also available on Windows 10 PCs.</span></span>

<span data-ttu-id="a265e-152">Surface Hub에 미리 설치된 UWP 앱:</span><span class="sxs-lookup"><span data-stu-id="a265e-152">UWP apps pre-installed on Surface Hub:</span></span>

- <span data-ttu-id="a265e-153">알람 및 시계</span><span class="sxs-lookup"><span data-stu-id="a265e-153">Alarms & Clock</span></span>
- <span data-ttu-id="a265e-154">계산기</span><span class="sxs-lookup"><span data-stu-id="a265e-154">Calculator</span></span>
- <span data-ttu-id="a265e-155">연결</span><span class="sxs-lookup"><span data-stu-id="a265e-155">Connect</span></span>
- <span data-ttu-id="a265e-156">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="a265e-156">Excel Mobile</span></span>
- <span data-ttu-id="a265e-157">피드백 허브</span><span class="sxs-lookup"><span data-stu-id="a265e-157">Feedback Hub</span></span>
- <span data-ttu-id="a265e-158">파일 탐색기</span><span class="sxs-lookup"><span data-stu-id="a265e-158">File Explorer</span></span>
- <span data-ttu-id="a265e-159">시작</span><span class="sxs-lookup"><span data-stu-id="a265e-159">Get Started</span></span>
- <span data-ttu-id="a265e-160">지도</span><span class="sxs-lookup"><span data-stu-id="a265e-160">Maps</span></span>
- <span data-ttu-id="a265e-161">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a265e-161">Microsoft Edge</span></span>
- <span data-ttu-id="a265e-162">Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="a265e-162">Microsoft Power BI</span></span>
- <span data-ttu-id="a265e-163">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a265e-163">Microsoft Teams</span></span>
- <span data-ttu-id="a265e-164">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="a265e-164">Microsoft Whiteboard</span></span>
- <span data-ttu-id="a265e-165">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a265e-165">OneDrive</span></span>
- <span data-ttu-id="a265e-166">사진</span><span class="sxs-lookup"><span data-stu-id="a265e-166">Photos</span></span>
- <span data-ttu-id="a265e-167">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="a265e-167">PowerPoint Mobile</span></span>
- <span data-ttu-id="a265e-168">설정</span><span class="sxs-lookup"><span data-stu-id="a265e-168">Settings</span></span>
- <span data-ttu-id="a265e-169">스토어</span><span class="sxs-lookup"><span data-stu-id="a265e-169">Store</span></span>
- <span data-ttu-id="a265e-170">팁</span><span class="sxs-lookup"><span data-stu-id="a265e-170">Tips</span></span>
- <span data-ttu-id="a265e-171">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="a265e-171">Word Mobile</span></span>

*<span data-ttu-id="a265e-172">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-172">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-173">Windows 10 Enterprise용 지침에 따라 Surface Hub의 기본 앱에 대한 기능 및 네트워크 요구 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-173">Use guidelines for Windows 10 Enterprise to determine the features and network requirements for default apps on the Surface Hub.</span></span>

### <a name="installing-apps-drivers-and-services"></a><span data-ttu-id="a265e-174">앱, 드라이버 및 서비스 설치</span><span class="sxs-lookup"><span data-stu-id="a265e-174">Installing apps, drivers, and services</span></span>

<span data-ttu-id="a265e-175">어플라이언스와 유사한 디바이스 특성을 유지하기 위해 Surface Hub는 UWP(유니버설 Windows 플랫폼) 앱의 설치만 지원하고 클래식 Win32 앱, 서비스 및 드라이버 설치는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-175">To help preserve the appliance-like nature of the device, Surface Hub only supports installing Universal Windows Platform (UWP) apps, and does not support installing classic Win32 apps, services and drivers.</span></span> <span data-ttu-id="a265e-176">또한 관리자만 UWP 앱 설치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-176">Furthermore, only admins have access to install UWP apps.</span></span>

*<span data-ttu-id="a265e-177">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-177">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-178">의도하지 않은 사용을 방지하기 위해 직원은 관리자가 설치한 앱만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-178">Employees can only use the apps that have been installed by admins, helping mitigate against unintended use.</span></span> <span data-ttu-id="a265e-179">Surface Hub는 대부분의 기존 PC 관리 및 모니터링 도구에 필요한 Win32 에이전트 설치를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-179">Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools.</span></span>

## <a name="security-and-lockdown"></a><span data-ttu-id="a265e-180">보안 및 잠금</span><span class="sxs-lookup"><span data-stu-id="a265e-180">Security and lockdown</span></span>

<span data-ttu-id="a265e-181">회의실 등의 공용 공간에서 Surface Hub를 사용하기 위해 해당 사용자 지정 OS는 Windows 10에서 사용할 수 있는 많은 보안 및 잠금 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-181">For Surface Hub to be used in communal spaces, such as meeting rooms, its custom OS implements many of the security and lockdown features available in Windows 10.</span></span>

<span data-ttu-id="a265e-182">Surface Hub에서 구현하는 Windows 10 보안 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-182">Surface Hub implements these Windows 10 security features:</span></span>
- [<span data-ttu-id="a265e-183">UEFI 보안 부팅</span><span class="sxs-lookup"><span data-stu-id="a265e-183">UEFI Secure Boot</span></span>](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)
- [<span data-ttu-id="a265e-184">Windows Defender Application Control 및 코드 무결성의 가상화 기반 보호</span><span class="sxs-lookup"><span data-stu-id="a265e-184">Windows Defender Application Control and virtualization-based protection of code integrity</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/introduction-to-device-guard-virtualization-based-security-and-code-integrity-policies)
- [<span data-ttu-id="a265e-185">AppLocker를 사용하는 응용 프로그램 제한 정책</span><span class="sxs-lookup"><span data-stu-id="a265e-185">Application restriction policies using AppLocker</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/applocker-overview)
- [<span data-ttu-id="a265e-186">BitLocker 드라이브 암호화</span><span class="sxs-lookup"><span data-stu-id="a265e-186">BitLocker Drive Encryption</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/bitlocker-overview)
- [<span data-ttu-id="a265e-187">TPM(신뢰할 수 있는 플랫폼 모듈)</span><span class="sxs-lookup"><span data-stu-id="a265e-187">Trusted Platform Module (TPM)</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/trusted-platform-module-overview)
- [<span data-ttu-id="a265e-188">Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a265e-188">Microsoft Defender</span></span>](https://technet.microsoft.com/itpro/windows/keep-secure/windows-defender-in-windows-10)
- <span data-ttu-id="a265e-189">설정 앱 액세스를 위한 [UAC(사용자 계정 컨트롤)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview)</span><span class="sxs-lookup"><span data-stu-id="a265e-189">[User Account Control (UAC)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview) for access to the Settings app</span></span>

<span data-ttu-id="a265e-190">추가 보안을 제공하는 Surface Hub 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-190">These Surface Hub features provide additional security:</span></span>
- <span data-ttu-id="a265e-191">사용자 지정 UEFI 펌웨어</span><span class="sxs-lookup"><span data-stu-id="a265e-191">Custom UEFI firmware</span></span>
- <span data-ttu-id="a265e-192">사용자 지정 셸 및 시작 메뉴에서 디바이스가 회의 기능으로 제한됨</span><span class="sxs-lookup"><span data-stu-id="a265e-192">Custom shell and Start menu limits device to meeting functions</span></span>
- <span data-ttu-id="a265e-193">사용자 지정 파일 탐색기에서 내 문서 아래의 파일 및 폴더에 대한 액세스 권한만 부여됨</span><span class="sxs-lookup"><span data-stu-id="a265e-193">Custom File Explorer only grants access to files and folders under My Documents</span></span>
- <span data-ttu-id="a265e-194">사용자 지정 설정 앱에서 관리자만 디바이스 설정을 수정할 수 있음</span><span class="sxs-lookup"><span data-stu-id="a265e-194">Custom Settings app only allows admins to modify device settings</span></span>
- <span data-ttu-id="a265e-195">고급 플러그 앤 플레이 드라이버를 다운로드할 수 없음</span><span class="sxs-lookup"><span data-stu-id="a265e-195">Downloading advanced Plug and Play drivers is disabled</span></span>

*<span data-ttu-id="a265e-196">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-196">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-197">Surface Hub에 대한 보안 평가를 수행하는 경우 이러한 기능을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="a265e-197">Consider these features when performing your security assessment for Surface Hub.</span></span>

<span data-ttu-id="a265e-198">자세한 내용은 [Surface Hub 보안 개요를 참조하세요.](surface-hub-security.md)</span><span class="sxs-lookup"><span data-stu-id="a265e-198">To learn more, see [Surface Hub Security Overview](surface-hub-security.md)</span></span>

## <a name="management"></a><span data-ttu-id="a265e-199">관리</span><span class="sxs-lookup"><span data-stu-id="a265e-199">Management</span></span>

### <a name="device-settings"></a><span data-ttu-id="a265e-200">디바이스 설정</span><span class="sxs-lookup"><span data-stu-id="a265e-200">Device settings</span></span>

<span data-ttu-id="a265e-201">설정 앱을 통해 디바이스 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-201">Device settings can be configured through the Settings app.</span></span> <span data-ttu-id="a265e-202">설정 앱은 Surface Hub용으로 사용자 지정되었지만 Windows 10 Desktop의 익숙한 설정도 많이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-202">The Settings app is customized for Surface Hub, but also contains many familiar settings from Windows 10 Desktop.</span></span> <span data-ttu-id="a265e-203">설정 앱을 열 때 관리자 자격 증명을 확인하기 위해 UAC(사용자 계정 컨트롤) 프롬프트가 표시되지만 관리자가 로그인되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-203">A User Accounts Control (UAC) prompt appears when opening up the Settings app to verify the admin's credentials, but this does not sign in the admin.</span></span>

*<span data-ttu-id="a265e-204">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-204">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-205">직원은 Surface Hub를 회의에 사용할 수 있지만 디바이스 설정을 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-205">Employees can use the Surface Hub for meetings, but cannot modify any device settings.</span></span> <span data-ttu-id="a265e-206">잠금 기능 외에도 이러한 제한은 직원이 디바이스를 회의 기능에만 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-206">In addition to lockdown features, this ensures that employees only use the device for meeting functions.</span></span>

### <a name="administrative-features"></a><span data-ttu-id="a265e-207">관리 기능</span><span class="sxs-lookup"><span data-stu-id="a265e-207">Administrative features</span></span>

<span data-ttu-id="a265e-208">Microsoft Management Console, 실행, 명령 프롬프트, PowerShell, 레지스트리 편집기, 이벤트 뷰어, 작업 관리자 등의 Windows 10 Enterprise 관리 기능은 Surface Hub에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-208">The administrative features in Windows 10 Enterprise, such as the Microsoft Management Console, Run, Command Prompt, PowerShell, registry editor, event viewer, and task manager are not supported on Surface Hub.</span></span> <span data-ttu-id="a265e-209">설정 앱에는 Surface Hub에서 로컬로 사용할 수 있는 모든 관리 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-209">The Settings app contains all of the administrative features locally available on Surface Hub.</span></span>

### <a name="remote-management-and-monitoring"></a><span data-ttu-id="a265e-210">원격 관리 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="a265e-210">Remote management and monitoring</span></span>

<span data-ttu-id="a265e-211">Surface Hub는 [Microsoft Intune과](https://docs.microsoft.com/intune/) 같은 MDM(모바일 장치 관리) 솔루션을 통한 원격 관리 및 Azure Monitor를 통한 [모니터링을 지원합니다.](https://azure.microsoft.com/services/monitor/)</span><span class="sxs-lookup"><span data-stu-id="a265e-211">Surface Hub supports remote management through mobile device management (MDM) solutions such as [Microsoft Intune](https://docs.microsoft.com/intune/) and monitoring through [Azure Monitor](https://azure.microsoft.com/services/monitor/).</span></span> 

*<span data-ttu-id="a265e-212">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-212">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-213">Surface Hub는 System Center Operations Manager 등 대부분의 기존 PC 관리 및 모니터링 도구에 필요한 Win32 에이전트 설치를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-213">Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools, such as System Center Operations Manager.</span></span>

### <a name="group-policy"></a><span data-ttu-id="a265e-214">그룹 정책</span><span class="sxs-lookup"><span data-stu-id="a265e-214">Group Policy</span></span>

<span data-ttu-id="a265e-215">Surface Hub는 감사를 포함하여 Windows 그룹 정책을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-215">Surface Hub does not support Windows Group Policy, including auditing.</span></span> <span data-ttu-id="a265e-216">대신 MDM을 사용하여 Surface Hub에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-216">Instead, use MDM to apply policies to your Surface Hub.</span></span> <span data-ttu-id="a265e-217">MDM에 대한 자세한 내용은 [MDM 공급자를 사용하여 설정 관리](manage-settings-with-mdm-for-surface-hub.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a265e-217">For more information about MDM, see [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).</span></span>

*<span data-ttu-id="a265e-218">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-218">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-219">그룹 정책 대신 MDM을 사용하여 Surface Hub를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-219">Use MDM to manage Surface Hub rather than group policy.</span></span>

### <a name="remote-assistance"></a><span data-ttu-id="a265e-220">원격 지원</span><span class="sxs-lookup"><span data-stu-id="a265e-220">Remote assistance</span></span>

<span data-ttu-id="a265e-221">Surface Hub는 원격 지원을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-221">Surface Hub does not support remote assistance.</span></span>

*<span data-ttu-id="a265e-222">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-222">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-223">원격 지원과 관련된 정책은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-223">Policies related to remote assistance don't apply for Surface Hub.</span></span>

## <a name="network"></a><span data-ttu-id="a265e-224">네트워크</span><span class="sxs-lookup"><span data-stu-id="a265e-224">Network</span></span>

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a><span data-ttu-id="a265e-225">도메인 가입 및 Azure AD(Azure Active Directory) 가입</span><span class="sxs-lookup"><span data-stu-id="a265e-225">Domain join and Azure Active Directory (Azure AD) join</span></span> 

<span data-ttu-id="a265e-226">Surface Hub는 도메인 가입 및 Azure AD 가입을 사용하여 주로 디렉터리 백업 관리자 그룹을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-226">Surface Hub uses domain join and Azure AD join primarily to provide a directory-backed admin group.</span></span> <span data-ttu-id="a265e-227">사용자는 도메인 계정으로 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-227">Users can't sign in with a domain account.</span></span> <span data-ttu-id="a265e-228">자세한 내용은 [관리자 그룹 관리](admin-group-management-for-surface-hub.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a265e-228">For more information, see [Admin group management](admin-group-management-for-surface-hub.md).</span></span>

*<span data-ttu-id="a265e-229">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-229">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-230">Surface Hub가 도메인에 가입된 경우에는 그룹 정책이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-230">Group policies are not applied when a Surface Hub is joined to your domain.</span></span> <span data-ttu-id="a265e-231">도메인 구성원 자격과 관련된 정책은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-231">Policies related to domain membership don't apply for Surface Hub.</span></span>

### <a name="accessing-domain-resources"></a><span data-ttu-id="a265e-232">도메인 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="a265e-232">Accessing domain resources</span></span>

<span data-ttu-id="a265e-233">사용자는 Microsoft Edge에 로그인하여 인트라넷 사이트 및 온라인 리소스(예: Office 365)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-233">Users can sign in to Microsoft Edge to access intranet sites and online resources (such as Office 365).</span></span> <span data-ttu-id="a265e-234">Surface Hub가 디바이스 계정을 사용하여 구성된 경우 시스템은 이 계정을 사용하여 Exchange 및 비즈니스용 Skype에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-234">If your Surface Hub is configured with a device account, the system uses it to access Exchange and Skype for Business.</span></span> <span data-ttu-id="a265e-235">그러나 Surface Hub는 파일 공유 및 프린터와 같은 도메인 리소스에 대한 액세스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-235">However, Surface Hub doesn't support accessing domain resources such as file shares and printers.</span></span>

*<span data-ttu-id="a265e-236">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-236">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-237">도메인 개체 액세스와 관련된 정책은 Surface Hub에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-237">Policies related to accessing domain objects don't apply for Surface Hub.</span></span>

<!--
### Endpoints



*Organization policies that this may affect:* <br> 
-->

### <a name="diagnostic-data"></a><span data-ttu-id="a265e-238">진단 데이터</span><span class="sxs-lookup"><span data-stu-id="a265e-238">Diagnostic data</span></span>

<span data-ttu-id="a265e-239">Surface Hub OS는 Windows 10에 연결된 사용자 환경 및 원격 분석 구성 요소를 사용하여 진단 데이터를 수집하고 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-239">The Surface Hub OS uses the Windows 10 Connected User Experience and Telemetry component to gather and transmit diagnostic data.</span></span> <span data-ttu-id="a265e-240">자세한 내용은 [조직에서 Windows 진단 데이터 구성](https://technet.microsoft.com/itpro/windows/manage/configure-windows-diagnostic-data-in-your-organization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a265e-240">For more information, see [Configure Windows diagnostic data in your organization](https://technet.microsoft.com/itpro/windows/manage/configure-windows-diagnostic-data-in-your-organization).</span></span>

*<span data-ttu-id="a265e-241">이러한 차이가 영향을 줄 수 있는 조직 정책:</span><span class="sxs-lookup"><span data-stu-id="a265e-241">Organization policies that this may affect:</span></span>* <br> <span data-ttu-id="a265e-242">Windows 10 Enterprise에서와 동일한 방식으로 Surface Hub에 대한 진단 데이터 수준을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a265e-242">Configure diagnostic data levels for Surface Hub in the same way as you do for Windows 10 Enterprise.</span></span>
