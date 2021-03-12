---
title: Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트
description: Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: 접근성 설정, 설정 앱, 접근성
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 6661f2347d2f411ed11fe6057ede8ca2bab07c33
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406671"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a><span data-ttu-id="1f186-104">Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트</span><span class="sxs-lookup"><span data-stu-id="1f186-104">Using the Surface Hub Hardware Diagnostic Tool to test a device account</span></span>

## <a name="introduction"></a><span data-ttu-id="1f186-105">소개</span><span class="sxs-lookup"><span data-stu-id="1f186-105">Introduction</span></span>

> [!NOTE]
> <span data-ttu-id="1f186-106">Surface Hub 하드웨어 진단 도구의 "계정 설정" 섹션은 정보를 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-106">The "Account Settings" section of the Surface Hub Hardware Diagnostic tool doesn’t collect any information.</span></span> <span data-ttu-id="1f186-107">입력으로 입력된 전자 메일 및 암호는 사용자 환경에서 직접만 사용되고 수집되거나 다른 누구에게도 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-107">The email and password that are entered as input are used only directly on your environment and not collected or transferred to anyone.</span></span> <span data-ttu-id="1f186-108">로그인 정보는 응용 프로그램이 닫히거나 Surface Hub에서 현재 세션을 종료할 때까지만 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-108">The login information persists only until the application is closed or you end the current session on the Surface Hub.</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="1f186-109">이 응용 프로그램을 실행하려면 관리자 권한이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-109">Administrator privileges are not required to run this application.</span></span>
> * <span data-ttu-id="1f186-110">Microsoft에서 서비스 호출을 열기 전에 진단 결과를 로컬 관리자와 논의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-110">The results of the diagnostic should be discussed with your local administrator before you open a service call with Microsoft.</span></span>

### <a name="surface-hub-hardware-diagnostic"></a><span data-ttu-id="1f186-111">Surface Hub 하드웨어 진단</span><span class="sxs-lookup"><span data-stu-id="1f186-111">Surface Hub Hardware Diagnostic</span></span>

<span data-ttu-id="1f186-112">기본적으로 Surface [Hub](https://www.microsoft.com/store/apps/9nblggh51f2g) 하드웨어 진단 응용 프로그램은 이전 버전의 Surface Hub 시스템에 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-112">By default, the [Surface Hub Hardware Diagnostic](https://www.microsoft.com/store/apps/9nblggh51f2g) application isn’t installed in earlier versions of the Surface Hub system.</span></span> <span data-ttu-id="1f186-113">이 응용 프로그램은 Microsoft Store에서 무료로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-113">The application is available for free from the Microsoft Store.</span></span> <span data-ttu-id="1f186-114">응용 프로그램을 설치하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-114">Administrator privileges are required to install the application.</span></span>

   ![하드웨어 진단 스크린샷](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="1f186-116">Surface Hub 하드웨어 진단 도구 정보</span><span class="sxs-lookup"><span data-stu-id="1f186-116">About the Surface Hub Hardware Diagnostic Tool</span></span>

<span data-ttu-id="1f186-117">Surface Hub 하드웨어 진단 도구는 사용자가 Surface Hub 장치 내에서 많은 하드웨어 구성 요소를 테스트할 수 있는 탐색하기 쉬운 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-117">The Surface Hub Hardware Diagnostic tool is an easy-to-navigate tool that lets the user test many of the hardware components within the Surface Hub device.</span></span> <span data-ttu-id="1f186-118">이 도구는 Surface Hub 장치 계정을 테스트하고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-118">This tool can also test and verify a Surface Hub device account.</span></span> <span data-ttu-id="1f186-119">이 문서에서는 Surface Hub 하드웨어 진단 도구 내에서 계정 설정 테스트를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-119">This article describes how to use the Account Settings test within the Surface Hub Hardware Diagnostic tool.</span></span>

> [!NOTE]
> <span data-ttu-id="1f186-120">테스트가 완료되기 전에 Surface Hub에 대한 디바이스 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-120">The device account for the Surface Hub should be created before any testing is done.</span></span> <span data-ttu-id="1f186-121">Surface Hub 관리자 가이드는 온라인(Office365) 또는 하이브리드 장치 계정을 만드는 데 도움이 되는 지침 및 PowerShell 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-121">The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises, online (Office365), or hybrid device accounts.</span></span> <span data-ttu-id="1f186-122">자세한 내용은 가이드의 디바이스 계정 만들기 및 [테스트(Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) 항목으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="1f186-122">For more information, go to the [Create and test a device account (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) topic in the guide.</span></span>

### <a name="device-account-testing-process"></a><span data-ttu-id="1f186-123">디바이스 계정 테스트 프로세스</span><span class="sxs-lookup"><span data-stu-id="1f186-123">Device account testing process</span></span>

1. <span data-ttu-id="1f186-124">모든 **앱으로 이동한**다음 Surface Hub 하드웨어 진단 응용 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-124">Navigate to **All Apps**, and then locate the Surface Hub Hardware Diagnostic application.</span></span>

    ![모든 앱 스크린샷](images/02-all-apps.png)

1. <span data-ttu-id="1f186-126">응용 프로그램이 시작되면 시작 **페이지에서는** 허브를 테스트하는 이유를 문서화하는 텍스트 창을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-126">When the application starts, the **Welcome** page provides a text window to document the reason why you are testing the Hub.</span></span> <span data-ttu-id="1f186-127">이 메모는 테스트가 끝날 때 진단 결과와 함께 USB에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-127">This note can be saved to USB together with the diagnostic results at the conclusion of testing.</span></span> <span data-ttu-id="1f186-128">메모 입력을 마친 후 계속 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-128">After you finish entering a note, select the **Continue** button.</span></span>

    >[!NOTE]
    ><span data-ttu-id="1f186-129">진단 결과를 저장하는 경우 기본 경로를 변경하거나 하위 경로를 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-129">When saving diagnostic results, do not change the default path or select a subdirectory.</span></span> <span data-ttu-id="1f186-130">파일은 나중에 파일 탐색기 앱을 통해 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-130">The files can be copied later via the File Explorer app.</span></span>

    ![환영 스크린샷](images/03-welcome.png)

1. <span data-ttu-id="1f186-132">다음 화면에서는 Surface Hub 구성 요소 전체 또는 일부를 테스트하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-132">The next screen provides you the option to test all or some of the Surface Hub components.</span></span> <span data-ttu-id="1f186-133">장치 계정 테스트를 시작하려면 테스트 결과 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-133">To begin testing the device account, select the **Test Results** icon.</span></span>

    ![테스트 옵션 스크린샷](images/04-test-results-1.png)

    ![테스트 결과 스크린샷](images/05-test-results-2.png)

1. <span data-ttu-id="1f186-136">계정 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1f186-136">Select **Account Settings**.</span></span>  

    ![계정 설정 스크린샷](images/06-account-settings.png)

    <span data-ttu-id="1f186-138">계정 설정 화면은 디바이스 계정을 테스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-138">The Account Settings screen is used to test your device account.</span></span>

    ![계정 설정 세부 정보 스크린샷](images/07-account-settings-details.png)

1. <span data-ttu-id="1f186-140">디바이스 계정의 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-140">Enter the email address of your device account.</span></span> <span data-ttu-id="1f186-141">암호는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-141">The password is optional but is recommended.</span></span> <span data-ttu-id="1f186-142">계속할 준비가 **되면** 계정 테스트 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-142">Select the **Test Account** button when you are ready to continue.</span></span>

    ![테스트 계정의 스크린샷](images/08-test-account.png)

1. <span data-ttu-id="1f186-144">테스트가 완료되면 네 가지 테스트 영역에 대한 결과를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-144">After testing is finished, review the results for the four areas of testing.</span></span> <span data-ttu-id="1f186-145">각 항목 옆에 있는 Plus 또는 Minus 기호를 선택하여 각 섹션을 확장하거나 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-145">Each section can be expanded or collapsed by selecting the Plus or Minus sign next to each topic.</span></span>

    **<span data-ttu-id="1f186-146">네트워크</span><span class="sxs-lookup"><span data-stu-id="1f186-146">Network</span></span>**

    ![네트워크 스크린샷](images/09-network.png)

    **<span data-ttu-id="1f186-148">환경</span><span class="sxs-lookup"><span data-stu-id="1f186-148">Environment</span></span>**

    ![환경 스크린샷](images/10-environment.png)

    **<span data-ttu-id="1f186-150">인증서</span><span class="sxs-lookup"><span data-stu-id="1f186-150">Certificates</span></span>**

    ![인증서 스크린샷](images/11-certificates.png)

    **<span data-ttu-id="1f186-152">트러스트 모델</span><span class="sxs-lookup"><span data-stu-id="1f186-152">Trust Model</span></span>**

    ![신뢰 모델 스크린샷](images/12-trust-model.png)

## <a name="appendix"></a><span data-ttu-id="1f186-154">부록</span><span class="sxs-lookup"><span data-stu-id="1f186-154">Appendix</span></span>

### <a name="field-messages-and-resolution"></a><span data-ttu-id="1f186-155">필드 메시지 및 확인</span><span class="sxs-lookup"><span data-stu-id="1f186-155">Field messages and resolution</span></span>

#### <a name="network"></a><span data-ttu-id="1f186-156">네트워크</span><span class="sxs-lookup"><span data-stu-id="1f186-156">Network</span></span>

<span data-ttu-id="1f186-157">필드</span><span class="sxs-lookup"><span data-stu-id="1f186-157">Field</span></span> |<span data-ttu-id="1f186-158">성공</span><span class="sxs-lookup"><span data-stu-id="1f186-158">Success</span></span> |<span data-ttu-id="1f186-159">실패</span><span class="sxs-lookup"><span data-stu-id="1f186-159">Failure</span></span> |<span data-ttu-id="1f186-160">설명</span><span class="sxs-lookup"><span data-stu-id="1f186-160">Comment</span></span> |<span data-ttu-id="1f186-161">참조</span><span class="sxs-lookup"><span data-stu-id="1f186-161">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f186-162">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="1f186-162">Internet Connectivity</span></span> |<span data-ttu-id="1f186-163">디바이스에 인터넷 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-163">Device does have Internet connectivity</span></span> |<span data-ttu-id="1f186-164">장치가 인터넷에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-164">Device does not have Internet connectivity</span></span> |<span data-ttu-id="1f186-165">프록시 연결을 비롯한 인터넷 연결 확인</span><span class="sxs-lookup"><span data-stu-id="1f186-165">Verifies internet connectivity, including proxy connection</span></span> |
<span data-ttu-id="1f186-166">HTTP 버전</span><span class="sxs-lookup"><span data-stu-id="1f186-166">HTTP Version</span></span> |<span data-ttu-id="1f186-167">1.1</span><span class="sxs-lookup"><span data-stu-id="1f186-167">1.1</span></span> |<span data-ttu-id="1f186-168">1.0</span><span class="sxs-lookup"><span data-stu-id="1f186-168">1.0</span></span> |<span data-ttu-id="1f186-169">HTTP 1.0이 발견된 경우 WU 및 스토어에서 문제가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-169">If HTTP 1.0 found, it will cause issue with WU and Store</span></span> |
<span data-ttu-id="1f186-170">직접 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="1f186-170">Direct Internet Connectivity</span></span> |<span data-ttu-id="1f186-171">장치에 프록시가 구성되어 있는 장치에 프록시가 구성되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="1f186-171">Device has a Proxy configured Device has no Proxy configured</span></span> |<span data-ttu-id="1f186-172">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1f186-172">N/A</span></span> |<span data-ttu-id="1f186-173">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-173">Informational.</span></span> <span data-ttu-id="1f186-174">장치가 프록시 뒤에 있나요?</span><span class="sxs-lookup"><span data-stu-id="1f186-174">Is your device behind a proxy?</span></span> |
<span data-ttu-id="1f186-175">프록시 주소</span><span class="sxs-lookup"><span data-stu-id="1f186-175">Proxy Address</span></span> | | |<span data-ttu-id="1f186-176">구성된 경우 프록시 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-176">If configured, returns proxy address.</span></span> |
<span data-ttu-id="1f186-177">프록시 인증</span><span class="sxs-lookup"><span data-stu-id="1f186-177">Proxy Authentication</span></span> |<span data-ttu-id="1f186-178">프록시에는 인증이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-178">Proxy does not require Authentication</span></span> |<span data-ttu-id="1f186-179">프록시를 사용하려면 프록시 인증 필요</span><span class="sxs-lookup"><span data-stu-id="1f186-179">Proxy requires Proxy Auth</span></span> |<span data-ttu-id="1f186-180">사용자가 Edge에서 이미 열려 있는 세션을 이미 있으며 프록시를 통해 인증한 경우 가극적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-180">Result may be a false positive if a user already has an open session in Edge and has authenticated through the proxy.</span></span> |
<span data-ttu-id="1f186-181">프록시 인증 유형</span><span class="sxs-lookup"><span data-stu-id="1f186-181">Proxy Auth Types</span></span> | | |<span data-ttu-id="1f186-182">프록시 인증을 사용하는 경우 프록시에서 보급하는 인증 방법을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-182">If proxy authentication is used, return the Authentication methods advertised by the proxy.</span></span>  |

#### <a name="environment"></a><span data-ttu-id="1f186-183">환경</span><span class="sxs-lookup"><span data-stu-id="1f186-183">Environment</span></span>

<span data-ttu-id="1f186-184">필드</span><span class="sxs-lookup"><span data-stu-id="1f186-184">Field</span></span> |<span data-ttu-id="1f186-185">성공</span><span class="sxs-lookup"><span data-stu-id="1f186-185">Success</span></span> |<span data-ttu-id="1f186-186">실패</span><span class="sxs-lookup"><span data-stu-id="1f186-186">Failure</span></span> |<span data-ttu-id="1f186-187">설명</span><span class="sxs-lookup"><span data-stu-id="1f186-187">Comment</span></span> |<span data-ttu-id="1f186-188">참조</span><span class="sxs-lookup"><span data-stu-id="1f186-188">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f186-189">SIP 도메인</span><span class="sxs-lookup"><span data-stu-id="1f186-189">SIP Domain</span></span> | | |<span data-ttu-id="1f186-190">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-190">Informational.</span></span>  |
<span data-ttu-id="1f186-191">Skype 환경</span><span class="sxs-lookup"><span data-stu-id="1f186-191">Skype Environment</span></span> |<span data-ttu-id="1f186-192">비즈니스용 Skype Online, 비즈니스용 Skype OnPrem, 비즈니스용 Skype 하이브리드</span><span class="sxs-lookup"><span data-stu-id="1f186-192">Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid</span></span> |<span data-ttu-id="1f186-193">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-193">Informational.</span></span> |<span data-ttu-id="1f186-194">검색된 환경 유형</span><span class="sxs-lookup"><span data-stu-id="1f186-194">What type of environment was detected.</span></span> <span data-ttu-id="1f186-195">참고: 암호를 입력한 경우 하이브리드만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-195">Note: Hybrid can only be detected if the password is entered.</span></span>
<span data-ttu-id="1f186-196">LyncDiscover FQDN</span><span class="sxs-lookup"><span data-stu-id="1f186-196">LyncDiscover FQDN</span></span> | | |<span data-ttu-id="1f186-197">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-197">Informational.</span></span> <span data-ttu-id="1f186-198">LyncDiscover DNS 결과 표시</span><span class="sxs-lookup"><span data-stu-id="1f186-198">Displays the LyncDiscover DNS result</span></span> |
<span data-ttu-id="1f186-199">LyncDiscover URI</span><span class="sxs-lookup"><span data-stu-id="1f186-199">LyncDiscover URI</span></span> | | |<span data-ttu-id="1f186-200">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-200">Informational.</span></span> <span data-ttu-id="1f186-201">환경에서 LyncDiscover를 수행하는 데 사용되는 URL을 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-201">Displays the URL used to perform a LyncDiscover on your environment.</span></span>|
<span data-ttu-id="1f186-202">LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="1f186-202">LyncDiscover</span></span> |<span data-ttu-id="1f186-203">연결 성공</span><span class="sxs-lookup"><span data-stu-id="1f186-203">Connection Successful</span></span> |<span data-ttu-id="1f186-204">연결이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-204">Connection Failed</span></span> |<span data-ttu-id="1f186-205">LyncDiscover 웹 서비스의 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-205">Response from LyncDiscover web service.</span></span> |
<span data-ttu-id="1f186-206">SIP 풀 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="1f186-206">SIP Pool Hostname</span></span> | | |<span data-ttu-id="1f186-207">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-207">Informational.</span></span> <span data-ttu-id="1f186-208">LyncDiscover에서 검색된 SIP 풀 이름 표시</span><span class="sxs-lookup"><span data-stu-id="1f186-208">Display the SIP pool name discovered from LyncDiscover</span></span> |

#### <a name="certificates-in-premises-hybrid-only"></a><span data-ttu-id="1f186-209">인증서(프레미스 하이브리드에만 해당)</span><span class="sxs-lookup"><span data-stu-id="1f186-209">Certificates (in-premises hybrid only)</span></span>

<span data-ttu-id="1f186-210">LyncDiscover 인증서</span><span class="sxs-lookup"><span data-stu-id="1f186-210">LyncDiscover Certificate</span></span>

<span data-ttu-id="1f186-211">필드</span><span class="sxs-lookup"><span data-stu-id="1f186-211">Field</span></span> |<span data-ttu-id="1f186-212">성공</span><span class="sxs-lookup"><span data-stu-id="1f186-212">Success</span></span> |<span data-ttu-id="1f186-213">실패</span><span class="sxs-lookup"><span data-stu-id="1f186-213">Failure</span></span> |<span data-ttu-id="1f186-214">설명</span><span class="sxs-lookup"><span data-stu-id="1f186-214">Comment</span></span> |<span data-ttu-id="1f186-215">참조</span><span class="sxs-lookup"><span data-stu-id="1f186-215">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f186-216">LyncDiscover Cert CN</span><span class="sxs-lookup"><span data-stu-id="1f186-216">LyncDiscover Cert CN</span></span> | | |<span data-ttu-id="1f186-217">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-217">Informational.</span></span> <span data-ttu-id="1f186-218">LD 인증 일반 이름 표시</span><span class="sxs-lookup"><span data-stu-id="1f186-218">Displays the LD cert Common name</span></span> |
<span data-ttu-id="1f186-219">LyncDiscover Cert CA</span><span class="sxs-lookup"><span data-stu-id="1f186-219">LyncDiscover Cert CA</span></span> | | |<span data-ttu-id="1f186-220">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-220">Informational.</span></span> <span data-ttu-id="1f186-221">LD Cert CA 표시</span><span class="sxs-lookup"><span data-stu-id="1f186-221">Displays the LD Cert CA</span></span> |
<span data-ttu-id="1f186-222">LyncDiscover Cert Root CA</span><span class="sxs-lookup"><span data-stu-id="1f186-222">LyncDiscover Cert Root CA</span></span> | | |<span data-ttu-id="1f186-223">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-223">Informational.</span></span> <span data-ttu-id="1f186-224">사용 가능한 경우 LD Cert Root CA를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-224">Displays the LD Cert Root CA, if available.</span></span> |
<span data-ttu-id="1f186-225">LD 트러스트 상태</span><span class="sxs-lookup"><span data-stu-id="1f186-225">LD Trust Status</span></span> |<span data-ttu-id="1f186-226">인증서가 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-226">Certificate is Trusted.</span></span> |<span data-ttu-id="1f186-227">인증서를 신뢰할 수 없습니다. 루트 CA를 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f186-227">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="1f186-228">로컬 인증서 저장소에 대해 인증서를 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-228">Verify the certificate against the local cert store.</span></span> <span data-ttu-id="1f186-229">컴퓨터는 인증서를 신뢰하는 경우 양수입니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-229">Returns positive if the machine trusts the certificate.</span></span>|<span data-ttu-id="1f186-230">[PowerShell을 사용하여 비즈니스용 Skype 인증서 다운로드 및 배포](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Surface Hub 프로비저닝 패키지에 지원되는 항목](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="1f186-230">[Download and deploy Skype for Business certificates using PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/)/[Supported items for Surface Hub provisioning packages](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span></span>

<span data-ttu-id="1f186-231">SIP 풀 인증</span><span class="sxs-lookup"><span data-stu-id="1f186-231">SIP Pool Certification</span></span>

<span data-ttu-id="1f186-232">필드</span><span class="sxs-lookup"><span data-stu-id="1f186-232">Field</span></span> |<span data-ttu-id="1f186-233">성공</span><span class="sxs-lookup"><span data-stu-id="1f186-233">Success</span></span> |<span data-ttu-id="1f186-234">실패</span><span class="sxs-lookup"><span data-stu-id="1f186-234">Failure</span></span> |<span data-ttu-id="1f186-235">설명</span><span class="sxs-lookup"><span data-stu-id="1f186-235">Comment</span></span> |<span data-ttu-id="1f186-236">참조</span><span class="sxs-lookup"><span data-stu-id="1f186-236">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f186-237">SIP 풀 Cert CN</span><span class="sxs-lookup"><span data-stu-id="1f186-237">SIP Pool Cert CN</span></span> | | |<span data-ttu-id="1f186-238">(콘텐츠)</span><span class="sxs-lookup"><span data-stu-id="1f186-238">(CONTENTS)</span></span> |
<span data-ttu-id="1f186-239">SIP 풀 Cert CA</span><span class="sxs-lookup"><span data-stu-id="1f186-239">SIP Pool Cert CA</span></span> | | |<span data-ttu-id="1f186-240">(콘텐츠)</span><span class="sxs-lookup"><span data-stu-id="1f186-240">(CONTENTS)</span></span> |
<span data-ttu-id="1f186-241">SIP 풀 트러스트 상태</span><span class="sxs-lookup"><span data-stu-id="1f186-241">SIP Pool Trust Status</span></span> |<span data-ttu-id="1f186-242">인증서가 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-242">Certificate is Trusted.</span></span> |<span data-ttu-id="1f186-243">인증서를 신뢰할 수 없습니다. 루트 CA를 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f186-243">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="1f186-244">로컬 인증서 저장소에 대해 인증서를 확인하고 장치가 인증서를 신뢰하는 경우 양의 인증서를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-244">Verify the certificate against the local cert store and return a positive if the devices trusts the certificate.</span></span> |
<span data-ttu-id="1f186-245">SIP 풀 인증 루트 CA</span><span class="sxs-lookup"><span data-stu-id="1f186-245">SIP Pool Cert Root CA</span></span> | | |<span data-ttu-id="1f186-246">정보.</span><span class="sxs-lookup"><span data-stu-id="1f186-246">Information.</span></span> <span data-ttu-id="1f186-247">SIP 풀 인증 루트 CA(사용 가능한 경우)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-247">Display the SIP Pool Cert Root CA, if available.</span></span> |

#### <a name="trust-model-on-premises-hybrid-only"></a><span data-ttu-id="1f186-248">트러스트 모델(사내 하이브리드에만 해당)</span><span class="sxs-lookup"><span data-stu-id="1f186-248">Trust Model (on-premises hybrid only)</span></span>

<span data-ttu-id="1f186-249">필드</span><span class="sxs-lookup"><span data-stu-id="1f186-249">Field</span></span> |<span data-ttu-id="1f186-250">성공</span><span class="sxs-lookup"><span data-stu-id="1f186-250">Success</span></span> |<span data-ttu-id="1f186-251">실패</span><span class="sxs-lookup"><span data-stu-id="1f186-251">Failure</span></span> |<span data-ttu-id="1f186-252">설명</span><span class="sxs-lookup"><span data-stu-id="1f186-252">Comment</span></span> |<span data-ttu-id="1f186-253">참조</span><span class="sxs-lookup"><span data-stu-id="1f186-253">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f186-254">트러스트 모델 상태</span><span class="sxs-lookup"><span data-stu-id="1f186-254">Trust Model Status</span></span> |<span data-ttu-id="1f186-255">신뢰 모델 문제가 검색되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-255">No Trust Model Issue Detected.</span></span> |<span data-ttu-id="1f186-256">SIP 도메인과 서버 도메인이 서로 다르면 다음 도메인을 추가하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f186-256">SIP Domain and server domain are different please add the following domains.</span></span> |<span data-ttu-id="1f186-257">신뢰 모델 문제의 LD FQDN/ LD 서버 이름/ 풀 서버 이름을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-257">Check the LD FQDN/ LD Server Name/ Pool Server name for Trust model issue.</span></span> 
<span data-ttu-id="1f186-258">Domain Name(s)</span><span class="sxs-lookup"><span data-stu-id="1f186-258">Domain Name(s)</span></span> | | |<span data-ttu-id="1f186-259">SFB에서 연결할 수 있는 도메인 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f186-259">Return the list of domains that should be added for SFB to connect.</span></span> |
