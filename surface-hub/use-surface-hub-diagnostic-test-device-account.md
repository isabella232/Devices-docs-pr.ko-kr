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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834884"
---
# <span data-ttu-id="d2b15-104">Surface Hub 하드웨어 진단 도구를 사용하여 디바이스 계정 테스트</span><span class="sxs-lookup"><span data-stu-id="d2b15-104">Using the Surface Hub Hardware Diagnostic Tool to test a device account</span></span>

## <span data-ttu-id="d2b15-105">소개</span><span class="sxs-lookup"><span data-stu-id="d2b15-105">Introduction</span></span>

> [!NOTE]
> <span data-ttu-id="d2b15-106">Surface Hub 하드웨어 진단 도구의 "계정 설정" 섹션에서 정보를 수집 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-106">The "Account Settings" section of the Surface Hub Hardware Diagnostic tool doesn’t collect any information.</span></span> <span data-ttu-id="d2b15-107">입력으로 입력 된 전자 메일 및 암호는 사용자 환경 에서만 사용할 수 있으며, 수집 하거나 다른 사람에 게 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-107">The email and password that are entered as input are used only directly on your environment and not collected or transferred to anyone.</span></span> <span data-ttu-id="d2b15-108">로그인 정보는 응용 프로그램이 닫히거나 Surface Hub의 현재 세션을 종료할 때까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-108">The login information persists only until the application is closed or you end the current session on the Surface Hub.</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="d2b15-109">이 응용 프로그램을 실행 하는 데 관리자 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-109">Administrator privileges are not required to run this application.</span></span>
> * <span data-ttu-id="d2b15-110">Microsoft에서 서비스 통화를 열기 전에 진단 결과를 로컬 관리자와 논의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-110">The results of the diagnostic should be discussed with your local administrator before you open a service call with Microsoft.</span></span>

### <span data-ttu-id="d2b15-111">Surface Hub 하드웨어 진단</span><span class="sxs-lookup"><span data-stu-id="d2b15-111">Surface Hub Hardware Diagnostic</span></span>

<span data-ttu-id="d2b15-112">[Surface Hub 하드웨어 진단](https://www.microsoft.com/store/apps/9nblggh51f2g) 응용 프로그램은 기본적으로 이전 버전의 surface hub 시스템에 설치 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-112">By default, the [Surface Hub Hardware Diagnostic](https://www.microsoft.com/store/apps/9nblggh51f2g) application isn’t installed in earlier versions of the Surface Hub system.</span></span> <span data-ttu-id="d2b15-113">Microsoft Store에서 응용 프로그램을 무료로 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-113">The application is available for free from the Microsoft Store.</span></span> <span data-ttu-id="d2b15-114">응용 프로그램을 설치 하려면 관리자 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-114">Administrator privileges are required to install the application.</span></span>

   ![하드웨어 진단 스크린샷](images/01-diagnostic.png)

## <span data-ttu-id="d2b15-116">Surface Hub 하드웨어 진단 도구 정보</span><span class="sxs-lookup"><span data-stu-id="d2b15-116">About the Surface Hub Hardware Diagnostic Tool</span></span>

<span data-ttu-id="d2b15-117">Surface Hub 하드웨어 진단 도구는 사용자가 Surface Hub 장치 내의 많은 하드웨어 구성 요소를 테스트할 수 있는 탐색 하기 쉬운 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-117">The Surface Hub Hardware Diagnostic tool is an easy-to-navigate tool that lets the user test many of the hardware components within the Surface Hub device.</span></span> <span data-ttu-id="d2b15-118">이 도구는 Surface Hub 디바이스 계정도 테스트 하 고 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-118">This tool can also test and verify a Surface Hub device account.</span></span> <span data-ttu-id="d2b15-119">이 문서에서는 Surface Hub 하드웨어 진단 도구 내에서 계정 설정 테스트를 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-119">This article describes how to use the Account Settings test within the Surface Hub Hardware Diagnostic tool.</span></span>

> [!NOTE]
> <span data-ttu-id="d2b15-120">Surface Hub에 대 한 디바이스 계정은 테스트를 완료 하기 전에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-120">The device account for the Surface Hub should be created before any testing is done.</span></span> <span data-ttu-id="d2b15-121">Surface Hub 관리자 가이드는 온-프레미스, 온라인 (Office365) 또는 하이브리드 디바이스 계정을 만드는 데 도움이 되는 지침 및 PowerShell 스크립트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-121">The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises, online (Office365), or hybrid device accounts.</span></span> <span data-ttu-id="d2b15-122">자세한 내용은 가이드의 [디바이스 계정 만들기 및 테스트 (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2b15-122">For more information, go to the [Create and test a device account (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) topic in the guide.</span></span>

### <span data-ttu-id="d2b15-123">디바이스 계정 테스트 프로세스</span><span class="sxs-lookup"><span data-stu-id="d2b15-123">Device account testing process</span></span>

1. <span data-ttu-id="d2b15-124">**모든 앱**으로 이동한 다음 Surface Hub 하드웨어 진단 응용 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-124">Navigate to **All Apps**, and then locate the Surface Hub Hardware Diagnostic application.</span></span>

    ![모든 앱 스크린샷](images/02-all-apps.png)

1. <span data-ttu-id="d2b15-126">응용 프로그램이 시작 되 면 **시작** 페이지에서 허브를 테스트 하는 이유를 설명 하는 텍스트 창을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-126">When the application starts, the **Welcome** page provides a text window to document the reason why you are testing the Hub.</span></span> <span data-ttu-id="d2b15-127">이 노트는 테스트를 끝맺을 때 진단 결과와 함께 USB에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-127">This note can be saved to USB together with the diagnostic results at the conclusion of testing.</span></span> <span data-ttu-id="d2b15-128">메모를 모두 입력 했으면 **계속** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-128">After you finish entering a note, select the **Continue** button.</span></span>

    ![시작 스크린샷](images/03-welcome.png)

1. <span data-ttu-id="d2b15-130">다음 화면에는 Surface Hub 구성 요소의 전체 또는 일부를 테스트 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-130">The next screen provides you the option to test all or some of the Surface Hub components.</span></span> <span data-ttu-id="d2b15-131">장치 계정 테스트를 시작 하려면 **테스트 결과** 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-131">To begin testing the device account, select the **Test Results** icon.</span></span>

    ![테스트 결과 스크린샷](images/04-test-results-1.png)

    ![테스트 결과 스크린샷](images/05-test-results-2.png)

1. <span data-ttu-id="d2b15-134">**계정 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-134">Select **Account Settings**.</span></span>  

    ![계정 설정 스크린샷](images/06-account-settings.png)

    <span data-ttu-id="d2b15-136">계정 설정 화면은 장치 계정을 테스트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-136">The Account Settings screen is used to test your device account.</span></span>

    ![계정 설정 세부 정보 스크린샷](images/07-account-settings-details.png)

1. <span data-ttu-id="d2b15-138">장치 계정의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-138">Enter the email address of your device account.</span></span> <span data-ttu-id="d2b15-139">비밀 번호는 선택 사항 이지만 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-139">The password is optional but is recommended.</span></span> <span data-ttu-id="d2b15-140">계속할 준비가 되 면 **테스트 계정** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-140">Select the **Test Account** button when you are ready to continue.</span></span>

    ![테스트 계정 스크린샷](images/08-test-account.png)

1. <span data-ttu-id="d2b15-142">테스트가 완료 되 면 4 개의 테스트 영역에 대 한 결과를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-142">After testing is finished, review the results for the four areas of testing.</span></span> <span data-ttu-id="d2b15-143">각 항목 옆에 있는 더하기 또는 빼기 기호를 선택 하 여 각 구역을 확장 하거나 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-143">Each section can be expanded or collapsed by selecting the Plus or Minus sign next to each topic.</span></span>

    **<span data-ttu-id="d2b15-144">네트워크</span><span class="sxs-lookup"><span data-stu-id="d2b15-144">Network</span></span>**

    ![네트워크 스크린샷](images/09-network.png)

    **<span data-ttu-id="d2b15-146">환경</span><span class="sxs-lookup"><span data-stu-id="d2b15-146">Environment</span></span>**

    ![환경 스크린샷](images/10-environment.png)

    **<span data-ttu-id="d2b15-148">인증서</span><span class="sxs-lookup"><span data-stu-id="d2b15-148">Certificates</span></span>**

    ![인증서 스크린샷](images/11-certificates.png)

    **<span data-ttu-id="d2b15-150">신뢰 모델</span><span class="sxs-lookup"><span data-stu-id="d2b15-150">Trust Model</span></span>**

    ![신뢰 모델 스크린샷](images/12-trust-model.png)

## <span data-ttu-id="d2b15-152">부록</span><span class="sxs-lookup"><span data-stu-id="d2b15-152">Appendix</span></span>

### <span data-ttu-id="d2b15-153">필드 메시지 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d2b15-153">Field messages and resolution</span></span>

#### <span data-ttu-id="d2b15-154">네트워크</span><span class="sxs-lookup"><span data-stu-id="d2b15-154">Network</span></span>

<span data-ttu-id="d2b15-155">필드</span><span class="sxs-lookup"><span data-stu-id="d2b15-155">Field</span></span> |<span data-ttu-id="d2b15-156">성공</span><span class="sxs-lookup"><span data-stu-id="d2b15-156">Success</span></span> |<span data-ttu-id="d2b15-157">실패</span><span class="sxs-lookup"><span data-stu-id="d2b15-157">Failure</span></span> |<span data-ttu-id="d2b15-158">설명</span><span class="sxs-lookup"><span data-stu-id="d2b15-158">Comment</span></span> |<span data-ttu-id="d2b15-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2b15-159">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="d2b15-160">인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="d2b15-160">Internet Connectivity</span></span> |<span data-ttu-id="d2b15-161">장치에 인터넷 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-161">Device does have Internet connectivity</span></span> |<span data-ttu-id="d2b15-162">장치에 인터넷이 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-162">Device does not have Internet connectivity</span></span> |<span data-ttu-id="d2b15-163">프록시 연결을 포함 하 여 인터넷 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-163">Verifies internet connectivity, including proxy connection</span></span> |
<span data-ttu-id="d2b15-164">HTTP 버전</span><span class="sxs-lookup"><span data-stu-id="d2b15-164">HTTP Version</span></span> |<span data-ttu-id="d2b15-165">1.1</span><span class="sxs-lookup"><span data-stu-id="d2b15-165">1.1</span></span> |<span data-ttu-id="d2b15-166">1.0</span><span class="sxs-lookup"><span data-stu-id="d2b15-166">1.0</span></span> |<span data-ttu-id="d2b15-167">HTTP 1.0이 발견 되 면 WU 및 스토어에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-167">If HTTP 1.0 found, it will cause issue with WU and Store</span></span> |
<span data-ttu-id="d2b15-168">직접 인터넷 연결</span><span class="sxs-lookup"><span data-stu-id="d2b15-168">Direct Internet Connectivity</span></span> |<span data-ttu-id="d2b15-169">디바이스에 프록시 구성 디바이스에 프록시가 구성 되어 있지 않음</span><span class="sxs-lookup"><span data-stu-id="d2b15-169">Device has a Proxy configured Device has no Proxy configured</span></span> |<span data-ttu-id="d2b15-170">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d2b15-170">N/A</span></span> |<span data-ttu-id="d2b15-171">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-171">Informational.</span></span> <span data-ttu-id="d2b15-172">디바이스가 프록시 뒤에 있습니까?</span><span class="sxs-lookup"><span data-stu-id="d2b15-172">Is your device behind a proxy?</span></span> |
<span data-ttu-id="d2b15-173">프록시 주소</span><span class="sxs-lookup"><span data-stu-id="d2b15-173">Proxy Address</span></span> | | |<span data-ttu-id="d2b15-174">구성 된 경우 프록시 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-174">If configured, returns proxy address.</span></span> |
<span data-ttu-id="d2b15-175">프록시 인증</span><span class="sxs-lookup"><span data-stu-id="d2b15-175">Proxy Authentication</span></span> |<span data-ttu-id="d2b15-176">프록시에는 인증이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-176">Proxy does not require Authentication</span></span> |<span data-ttu-id="d2b15-177">프록시에 프록시 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-177">Proxy requires Proxy Auth</span></span> |<span data-ttu-id="d2b15-178">사용자가 Edge에서 열려 있는 세션을 이미 사용 중이 고 프록시를 통해 인증 된 경우 결과가 가양성 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-178">Result may be a false positive if a user already has an open session in Edge and has authenticated through the proxy.</span></span> |
<span data-ttu-id="d2b15-179">프록시 인증 형식</span><span class="sxs-lookup"><span data-stu-id="d2b15-179">Proxy Auth Types</span></span> | | |<span data-ttu-id="d2b15-180">프록시 인증을 사용 하는 경우 프록시에서 알린 인증 방법을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-180">If proxy authentication is used, return the Authentication methods advertised by the proxy.</span></span>  |

#### <span data-ttu-id="d2b15-181">환경</span><span class="sxs-lookup"><span data-stu-id="d2b15-181">Environment</span></span>

<span data-ttu-id="d2b15-182">필드</span><span class="sxs-lookup"><span data-stu-id="d2b15-182">Field</span></span> |<span data-ttu-id="d2b15-183">성공</span><span class="sxs-lookup"><span data-stu-id="d2b15-183">Success</span></span> |<span data-ttu-id="d2b15-184">실패</span><span class="sxs-lookup"><span data-stu-id="d2b15-184">Failure</span></span> |<span data-ttu-id="d2b15-185">설명</span><span class="sxs-lookup"><span data-stu-id="d2b15-185">Comment</span></span> |<span data-ttu-id="d2b15-186">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2b15-186">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="d2b15-187">SIP 도메인</span><span class="sxs-lookup"><span data-stu-id="d2b15-187">SIP Domain</span></span> | | |<span data-ttu-id="d2b15-188">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-188">Informational.</span></span>  |
<span data-ttu-id="d2b15-189">Skype 환경</span><span class="sxs-lookup"><span data-stu-id="d2b15-189">Skype Environment</span></span> |<span data-ttu-id="d2b15-190">비즈니스용 skype Online, 비즈니스용 Skype OnPrem, 비즈니스용 Skype 하이브리드</span><span class="sxs-lookup"><span data-stu-id="d2b15-190">Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid</span></span> |<span data-ttu-id="d2b15-191">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-191">Informational.</span></span> |<span data-ttu-id="d2b15-192">검색 된 환경 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-192">What type of environment was detected.</span></span> <span data-ttu-id="d2b15-193">참고: 하이브리드은 암호를 입력 한 경우에만 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-193">Note: Hybrid can only be detected if the password is entered.</span></span>
<span data-ttu-id="d2b15-194">LyncDiscover 검색</span><span class="sxs-lookup"><span data-stu-id="d2b15-194">LyncDiscover FQDN</span></span> | | |<span data-ttu-id="d2b15-195">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-195">Informational.</span></span> <span data-ttu-id="d2b15-196">DNS 결과를 표시 하는 ldisc</span><span class="sxs-lookup"><span data-stu-id="d2b15-196">Displays the LyncDiscover DNS result</span></span> |
<span data-ttu-id="d2b15-197">LyncDiscover 검색</span><span class="sxs-lookup"><span data-stu-id="d2b15-197">LyncDiscover URI</span></span> | | |<span data-ttu-id="d2b15-198">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-198">Informational.</span></span> <span data-ttu-id="d2b15-199">환경에서 LyncDiscover을 수행 하는 데 사용 되는 URL을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-199">Displays the URL used to perform a LyncDiscover on your environment.</span></span>|
<span data-ttu-id="d2b15-200">LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="d2b15-200">LyncDiscover</span></span> |<span data-ttu-id="d2b15-201">연결 성공</span><span class="sxs-lookup"><span data-stu-id="d2b15-201">Connection Successful</span></span> |<span data-ttu-id="d2b15-202">연결 실패</span><span class="sxs-lookup"><span data-stu-id="d2b15-202">Connection Failed</span></span> |<span data-ttu-id="d2b15-203">웹 서비스에서 받은 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-203">Response from LyncDiscover web service.</span></span> |
<span data-ttu-id="d2b15-204">SIP 풀 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="d2b15-204">SIP Pool Hostname</span></span> | | |<span data-ttu-id="d2b15-205">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-205">Informational.</span></span> <span data-ttu-id="d2b15-206">LyncDiscover에서 검색 된 SIP 풀 이름 표시</span><span class="sxs-lookup"><span data-stu-id="d2b15-206">Display the SIP pool name discovered from LyncDiscover</span></span> |

#### <span data-ttu-id="d2b15-207">인증서 (온-프레미스 하이브리드에만 해당)</span><span class="sxs-lookup"><span data-stu-id="d2b15-207">Certificates (in-premises hybrid only)</span></span>

<span data-ttu-id="d2b15-208">인증서 검색</span><span class="sxs-lookup"><span data-stu-id="d2b15-208">LyncDiscover Certificate</span></span>

<span data-ttu-id="d2b15-209">필드</span><span class="sxs-lookup"><span data-stu-id="d2b15-209">Field</span></span> |<span data-ttu-id="d2b15-210">성공</span><span class="sxs-lookup"><span data-stu-id="d2b15-210">Success</span></span> |<span data-ttu-id="d2b15-211">실패</span><span class="sxs-lookup"><span data-stu-id="d2b15-211">Failure</span></span> |<span data-ttu-id="d2b15-212">설명</span><span class="sxs-lookup"><span data-stu-id="d2b15-212">Comment</span></span> |<span data-ttu-id="d2b15-213">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2b15-213">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="d2b15-214">인증서 CN 검색</span><span class="sxs-lookup"><span data-stu-id="d2b15-214">LyncDiscover Cert CN</span></span> | | |<span data-ttu-id="d2b15-215">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-215">Informational.</span></span> <span data-ttu-id="d2b15-216">LD cert 일반 이름 표시</span><span class="sxs-lookup"><span data-stu-id="d2b15-216">Displays the LD cert Common name</span></span> |
<span data-ttu-id="d2b15-217">인증서 CA를 확인 하는 ldisc</span><span class="sxs-lookup"><span data-stu-id="d2b15-217">LyncDiscover Cert CA</span></span> | | |<span data-ttu-id="d2b15-218">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-218">Informational.</span></span> <span data-ttu-id="d2b15-219">LD Cert CA를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-219">Displays the LD Cert CA</span></span> |
<span data-ttu-id="d2b15-220">인증서 루트 CA를 확인 하는 LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="d2b15-220">LyncDiscover Cert Root CA</span></span> | | |<span data-ttu-id="d2b15-221">나타낼.</span><span class="sxs-lookup"><span data-stu-id="d2b15-221">Informational.</span></span> <span data-ttu-id="d2b15-222">사용 가능한 경우 LD Cert 루트 CA를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-222">Displays the LD Cert Root CA, if available.</span></span> |
<span data-ttu-id="d2b15-223">LD 개 신뢰 상태</span><span class="sxs-lookup"><span data-stu-id="d2b15-223">LD Trust Status</span></span> |<span data-ttu-id="d2b15-224">인증서를 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-224">Certificate is Trusted.</span></span> |<span data-ttu-id="d2b15-225">인증서를 신뢰할 수 없습니다. 루트 CA를 추가 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2b15-225">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="d2b15-226">로컬 인증서 저장소에 대해 인증서를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-226">Verify the certificate against the local cert store.</span></span> <span data-ttu-id="d2b15-227">컴퓨터에서 인증서를 신뢰 하는 경우 양수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-227">Returns positive if the machine trusts the certificate.</span></span>|<span data-ttu-id="d2b15-228">[PowerShell을 사용 하 여 비즈니스용 Skype 인증서 다운로드 및 배포](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Surface Hub 프로비저닝 패키지에 지원 되는 항목](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="d2b15-228">[Download and deploy Skype for Business certificates using PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/)/[Supported items for Surface Hub provisioning packages](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span></span>

<span data-ttu-id="d2b15-229">SIP 풀 인증</span><span class="sxs-lookup"><span data-stu-id="d2b15-229">SIP Pool Certification</span></span>

<span data-ttu-id="d2b15-230">필드</span><span class="sxs-lookup"><span data-stu-id="d2b15-230">Field</span></span> |<span data-ttu-id="d2b15-231">성공</span><span class="sxs-lookup"><span data-stu-id="d2b15-231">Success</span></span> |<span data-ttu-id="d2b15-232">실패</span><span class="sxs-lookup"><span data-stu-id="d2b15-232">Failure</span></span> |<span data-ttu-id="d2b15-233">설명</span><span class="sxs-lookup"><span data-stu-id="d2b15-233">Comment</span></span> |<span data-ttu-id="d2b15-234">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2b15-234">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="d2b15-235">SIP 풀 Cert CN</span><span class="sxs-lookup"><span data-stu-id="d2b15-235">SIP Pool Cert CN</span></span> | | |<span data-ttu-id="d2b15-236">콘텐츠의</span><span class="sxs-lookup"><span data-stu-id="d2b15-236">(CONTENTS)</span></span> |
<span data-ttu-id="d2b15-237">SIP 풀 Cert CA</span><span class="sxs-lookup"><span data-stu-id="d2b15-237">SIP Pool Cert CA</span></span> | | |<span data-ttu-id="d2b15-238">콘텐츠의</span><span class="sxs-lookup"><span data-stu-id="d2b15-238">(CONTENTS)</span></span> |
<span data-ttu-id="d2b15-239">SIP 풀 신뢰 상태</span><span class="sxs-lookup"><span data-stu-id="d2b15-239">SIP Pool Trust Status</span></span> |<span data-ttu-id="d2b15-240">인증서를 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-240">Certificate is Trusted.</span></span> |<span data-ttu-id="d2b15-241">인증서를 신뢰할 수 없습니다. 루트 CA를 추가 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2b15-241">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="d2b15-242">로컬 인증서 저장소에 대해 인증서를 확인 하 고 장치가 인증서를 신뢰 하는 경우 양수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-242">Verify the certificate against the local cert store and return a positive if the devices trusts the certificate.</span></span> |
<span data-ttu-id="d2b15-243">SIP 풀 인증서 루트 CA</span><span class="sxs-lookup"><span data-stu-id="d2b15-243">SIP Pool Cert Root CA</span></span> | | |<span data-ttu-id="d2b15-244">방법.</span><span class="sxs-lookup"><span data-stu-id="d2b15-244">Information.</span></span> <span data-ttu-id="d2b15-245">가능한 경우 SIP 풀 인증서 루트 CA를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-245">Display the SIP Pool Cert Root CA, if available.</span></span> |

#### <span data-ttu-id="d2b15-246">신뢰 모델 (온-프레미스 하이브리드에만 해당)</span><span class="sxs-lookup"><span data-stu-id="d2b15-246">Trust Model (on-premises hybrid only)</span></span>

<span data-ttu-id="d2b15-247">필드</span><span class="sxs-lookup"><span data-stu-id="d2b15-247">Field</span></span> |<span data-ttu-id="d2b15-248">성공</span><span class="sxs-lookup"><span data-stu-id="d2b15-248">Success</span></span> |<span data-ttu-id="d2b15-249">실패</span><span class="sxs-lookup"><span data-stu-id="d2b15-249">Failure</span></span> |<span data-ttu-id="d2b15-250">설명</span><span class="sxs-lookup"><span data-stu-id="d2b15-250">Comment</span></span> |<span data-ttu-id="d2b15-251">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2b15-251">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="d2b15-252">신뢰 모델 상태</span><span class="sxs-lookup"><span data-stu-id="d2b15-252">Trust Model Status</span></span> |<span data-ttu-id="d2b15-253">신뢰 모델 문제가 감지 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-253">No Trust Model Issue Detected.</span></span> |<span data-ttu-id="d2b15-254">SIP 도메인 및 서버 도메인이 다름 다음 도메인을 추가 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2b15-254">SIP Domain and server domain are different please add the following domains.</span></span> |<span data-ttu-id="d2b15-255">보안 모델 문제에 대 한 LD FQDN/LD 서버 이름/풀 서버 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-255">Check the LD FQDN/ LD Server Name/ Pool Server name for Trust model issue.</span></span> 
<span data-ttu-id="d2b15-256">도메인 이름</span><span class="sxs-lookup"><span data-stu-id="d2b15-256">Domain Name(s)</span></span> | | |<span data-ttu-id="d2b15-257">SFB에 연결 하기 위해 추가 해야 하는 도메인 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b15-257">Return the list of domains that should be added for SFB to connect.</span></span> |
