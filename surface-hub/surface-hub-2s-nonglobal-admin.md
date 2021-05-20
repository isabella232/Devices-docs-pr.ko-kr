---
title: Surface Hub에서 전역이 아닌 관리자 계정 구성
description: 이 문서에서는 전역이 아닌 관리자 계정을 구성하여 2S 및 Surface Hub Surface Hub 설명합니다.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/22/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 03359a7d8ea028a8094c064c1fcb82cc9a53fe6a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576768"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a><span data-ttu-id="93c05-104">Surface Hub에서 전역이 아닌 관리자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="93c05-104">Configure non Global admin accounts on Surface Hub</span></span>

<span data-ttu-id="93c05-105">Windows 10 Team 2020 업데이트는 Azure AD 도메인에 가입된 Surface Hub 장치에서 설정 앱 관리 권한을 제한하는 전역이 아닌 관리자 계정을 구성하기 위한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-105">The Windows 10 Team 2020 Update adds support for configuring non Global admin accounts that limit permissions to management of the Settings app on Surface Hub devices joined to an Azure AD domain.</span></span> <span data-ttu-id="93c05-106">이렇게 하면 전체 Azure AD 도메인에서 사용자 Surface Hub 관리자 액세스 권한을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-106">This enables you to scope admin permissions for Surface Hub only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="93c05-107">시작하기 전에 Azure AD에 Surface Hub Intune이 자동으로 등록되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="93c05-107">Before you begin, make sure your Surface Hub is joined to Azure AD and Intune auto-enrolled.</span></span> <span data-ttu-id="93c05-108">그렇지 않은 경우 Azure AD에 Surface Hub 옵션을 선택하여 OOBE(첫 실행) 설치 프로그램을 다시 설정하고 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-108">If not, you will need to reset Surface Hub and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="93c05-109">요약</span><span class="sxs-lookup"><span data-stu-id="93c05-109">Summary</span></span> 

<span data-ttu-id="93c05-110">전역이 아닌 관리자 계정을 만드는 프로세스는 다음 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="93c05-111">Microsoft Intune 관리하기 위해 지정된 관리자가 포함된 보안 그룹을 Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="93c05-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub.</span></span>
2. <span data-ttu-id="93c05-112">PowerShell을 사용하여 Azure AD 그룹 SID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="93c05-113">Azure AD 그룹 SID를 포함하는 XML 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="93c05-114">전역 관리자가 아닌 Surface Hub 관리되는 디바이스가 포함된 보안 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-114">Create a Security Group containing the Surface Hub devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="93c05-115">사용자 지정 디바이스가 포함된 보안 그룹을 대상으로 하는 사용자 지정 구성 프로필을 Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="93c05-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="93c05-116">Azure AD 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="93c05-116">Create Azure AD security groups</span></span>

<span data-ttu-id="93c05-117">먼저 관리자 계정이 포함된 보안 그룹을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="93c05-118">그런 다음 장치용 다른 보안 Surface Hub 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="93c05-119">관리자 계정에 대한 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="93c05-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="93c05-120">Microsoft Endpoint Manager 관리 [센터를](https://go.microsoft.com/fwlink/?linkid=2109431)통해 Intune에 로그인하고 그룹 새 그룹 > 선택하고 그룹 \*\*\*\*  >  \*\*\*\* 유형에서 보안을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="93c05-121">로컬 관리자와 같은 그룹 \*\*\*\* Surface Hub 입력한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![허브 관리자용 보안 그룹 만들기](images/sh-create-sec-group.png)

3. <span data-ttu-id="93c05-123">그룹을 열고 \*\*\*\* 구성원 을 \*\*\*\* 선택한 다음 구성원 추가를 선택하여 전역 관리자가 아닌 관리자로 지정하고자 하는 관리자 계정을 Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="93c05-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub.</span></span> <span data-ttu-id="93c05-124">Intune에서 그룹을 만드는 데 대한 자세한 내용은 사용자 및 장치를 구성하는 그룹 [추가를 참조합니다.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="93c05-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-devices"></a><span data-ttu-id="93c05-125">장치용 보안 Surface Hub 만들기</span><span class="sxs-lookup"><span data-stu-id="93c05-125">Create security group for Surface Hub devices</span></span>

1. <span data-ttu-id="93c05-126">이전 절차를 반복하여 허브 장치에 대해 별도의 보안 그룹을 만들 수 있습니다. 예를 들어 **Surface Hub.**</span><span class="sxs-lookup"><span data-stu-id="93c05-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![허브 장치에 대한 보안 그룹 만들기](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="93c05-128">PowerShell을 사용하여 Azure AD 그룹 SID 얻기</span><span class="sxs-lookup"><span data-stu-id="93c05-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="93c05-129">관리자 권한(관리자 권한으로 실행)을 사용하여 PowerShell을 시작하고 시스템이 PowerShell 스크립트를 실행하도록 구성되어 있는지 확인\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="93c05-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="93c05-130">자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)</span><span class="sxs-lookup"><span data-stu-id="93c05-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="93c05-131">[모듈 Azure PowerShell 설치합니다.](https://docs.microsoft.com/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="93c05-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="93c05-132">Azure AD 테넌트에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="93c05-133">테넌트에 로그인하면 다음 commandlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="93c05-134">"Azure AD 그룹의 개체 ID를 입력하세요."라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="93c05-135">Intune에서 앞에서 만든 그룹을 선택하고 다음 그림과 같이 개체 ID를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![보안 그룹의 개체 ID 복사](images/sh-objectid.png)

6. <span data-ttu-id="93c05-137">다음 commandlet을 실행하여 보안 그룹의 SID를 얻게 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="93c05-138">PowerShell 명령줄에 개체 ID를 붙여넣고 **Enter**를 누르고 **Azure AD 그룹 SID를** 텍스트 편집기로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="93c05-139">Azure AD 그룹 SID를 포함하는 XML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="93c05-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="93c05-140">텍스트 편집기로 다음을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > <span data-ttu-id="93c05-141">XML 파일에서 기본 Administrator 구성원을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-141">Do not remove the default Administrator member from the XML file.</span></span>

2. <span data-ttu-id="93c05-142">자리 보기 SID(S-1-12-1로 시작)를 **Azure AD 그룹 SID로** 바꾸고 파일을 XML로 저장합니다. 예를 들어 \*\*aad-local-admin.xml. \*\*</span><span class="sxs-lookup"><span data-stu-id="93c05-142">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="93c05-143">사용자 지정 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="93c05-143">Create Custom configuration profile</span></span>

1. <span data-ttu-id="93c05-144">다음 Endpoint Manager 장치 **구성**  >  **프로필**  >  **프로필 만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-144">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="93c05-145">플랫폼에서 추가 **Windows 10 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-145">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="93c05-146">프로필에서 사용자 지정 **을**선택한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-146">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="93c05-147">이름과 설명을 추가하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-147">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="93c05-148">구성 **설정**  >  **OMA-URI**설정 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-148">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="93c05-149">행 추가 창에서 이름을 추가하고     **OMA-URI 아래에**다음 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-149">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="93c05-150">데이터 형식에서 **문자열 XML을 선택하고** 이전 단계에서 만든 XML 파일을 열습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-150">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![로컬 관리자 xml 구성 파일 업로드](images/sh-local-admin-config.png)

7. <span data-ttu-id="93c05-152">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-152">Click **Save**.</span></span>
8. <span data-ttu-id="93c05-153">그룹 **선택을 클릭하여** 앞서 [](#create-security-group-for-surface-hub-devices) 만든 보안 그룹(장치)을**Surface Hub 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-153">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="93c05-154">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-154">Click **Next.**</span></span>
9. <span data-ttu-id="93c05-155">적용 가능성 규칙에서 원하는 경우 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-155">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="93c05-156">그렇지 않으면 **다음을 선택하고** 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93c05-156">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="93c05-157">OMA-URI 문자열을 사용하는 사용자 지정 구성 프로필에 대한 자세한 내용은 [Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)Windows 10 사용자 지정 설정 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93c05-157">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub"></a><span data-ttu-id="93c05-158">전역 관리자를 관리하지 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="93c05-158">Non Global admins managing Surface Hub</span></span>

<span data-ttu-id="93c05-159">이제 **Surface Hub 로컬** 관리자 보안 그룹의 구성원이 관리자의 설정 앱에 로그인하고 설정을 Surface Hub 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c05-159">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub and manage settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93c05-160">설정 앱에 대한 전역 관리자의 기본 액세스는 제거됩니다(이 새 보안 그룹의 구성원이 아는 경우).</span><span class="sxs-lookup"><span data-stu-id="93c05-160">The default access of global admins to the Settings app is removed (unless they are also members of this new security group).</span></span>
