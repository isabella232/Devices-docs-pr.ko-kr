---
title: 관리자 그룹 관리(Surface Hub)
description: 장치에서 설정 앱을 열어 각 Microsoft Surface Hub를 개별적으로 구성할 수 있습니다.
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: 관리자 그룹 관리, 설정 앱, Surface Hub 구성
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 716e409bf988e7178ec45e21165aad070d027eee
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836343"
---
# <span data-ttu-id="f06e8-104">관리자 그룹 관리(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="f06e8-104">Admin group management (Surface Hub)</span></span>


<span data-ttu-id="f06e8-105">장치에서 설정 앱을 사용하여 각 Surface Hub를 개별적으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-105">Every Surface Hub can be configured locally using the Settings app on the device.</span></span> <span data-ttu-id="f06e8-106">권한이 없는 사용자가 설정을 변경하지 못하도록 설정 앱에서는 관리자 자격 증명을 사용하여 앱을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-106">To prevent unauthorized users from changing settings, the Settings app requires admin credentials to open the app.</span></span>


## <span data-ttu-id="f06e8-107">관리자 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f06e8-107">Admin Group Management</span></span>

<span data-ttu-id="f06e8-108">다음 세 가지 방법 중 하나로 장치에 대한 관리자 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-108">You can set up administrator accounts for the device in one of three ways:</span></span>

-   <span data-ttu-id="f06e8-109">로컬 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f06e8-109">Create a local admin account</span></span>
-   <span data-ttu-id="f06e8-110">장치를 AD(Active Directory) 도메인에 가입</span><span class="sxs-lookup"><span data-stu-id="f06e8-110">Domain join the device to Active Directory (AD)</span></span>
-   <span data-ttu-id="f06e8-111">Azure AD(Active Directory)에 장치 가입</span><span class="sxs-lookup"><span data-stu-id="f06e8-111">Azure Active Directory (Azure AD) join the device</span></span>


### <span data-ttu-id="f06e8-112">로컬 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f06e8-112">Create a local admin account</span></span>

<span data-ttu-id="f06e8-113">로컬 관리자를 만들려면 [첫 실행 중에 로컬 관리자를 사용하도록 선택합니다](first-run-program-surface-hub.md#use-a-local-admin).</span><span class="sxs-lookup"><span data-stu-id="f06e8-113">To create a local admin, [choose to use a local admin during first run](first-run-program-surface-hub.md#use-a-local-admin).</span></span> <span data-ttu-id="f06e8-114">이렇게 하면 선택한 사용자 이름과 암호를 사용하여 Surface Hub에 단일 로컬 관리자 계정이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-114">This will create a single local admin account on the Surface Hub with the username and password of your choice.</span></span> <span data-ttu-id="f06e8-115">이러한 자격 증명을 사용하여 설정 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-115">Use these credentials to open the Settings app.</span></span>

<span data-ttu-id="f06e8-116">관리 계정 정보는 디렉터리 서비스에서 백업하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-116">Note that the local admin account information is not backed by any directory service.</span></span> <span data-ttu-id="f06e8-117">장치가 AD(Active Directory) 또는 Azure AD(Active Directory)에 액세스할 수 없는 경우에만 로컬 관리자를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-117">We recommend you only choose a local admin if the device does not have access to Active Directory (AD) or Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f06e8-118">로컬 관리자의 암호를 변경하려는 경우 설정에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-118">If you decide to change the local admin’s password, you can do so in Settings.</span></span> <span data-ttu-id="f06e8-119">그러나 로컬 관리자 계정 사용에서 도메인 또는 Azure AD 테넌트의 그룹 사용으로 변경하려는 경우 [장치를 초기화](device-reset-surface-hub.md)하고 처음 프로그램을 다시 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-119">However, if you want to change from using the local admin account to using a group from your domain or Azure AD tenant, then you’ll need to [reset the device](device-reset-surface-hub.md) and go through the first-time program again.</span></span>

### <span data-ttu-id="f06e8-120">장치를 AD(Active Directory) 도메인에 가입</span><span class="sxs-lookup"><span data-stu-id="f06e8-120">Domain join the device to Active Directory (AD)</span></span>

<span data-ttu-id="f06e8-121">Surface Hub를 AD 도메인에 가입시켜 지정된 보안 그룹의 사용자가 설정을 구성하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-121">You can domain join the Surface Hub to your AD domain to allow users from a specified security group to configure settings.</span></span> <span data-ttu-id="f06e8-122">첫 실행 중에 [Active Directory 도메인 서비스](first-run-program-surface-hub.md#use-active-directory-domain-services)를 사용하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-122">During first run, choose to use [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services).</span></span> <span data-ttu-id="f06e8-123">선택한 도메인에 가입할 수 있는 자격 증명과 기존 보안 그룹의 이름을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-123">You'll need to provide credentials that are capable of joining the domain of your choice, and the name of an existing security group.</span></span> <span data-ttu-id="f06e8-124">해당 보안 그룹의 구성원인 사용자가 자격 증명을 입력하고 설정을 잠금 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-124">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>

#### <span data-ttu-id="f06e8-125">Surface Hub를 도메인에 가입시키면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="f06e8-125">What happens when you domain join your Surface Hub?</span></span>
<span data-ttu-id="f06e8-126">Surface Hub에서는 도메인 가입을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-126">Surface Hubs use domain join to:</span></span>
- <span data-ttu-id="f06e8-127">AD에서 지정된 보안 그룹의 구성원에게 관리자 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-127">Grant admin rights to members of a specified security group in AD.</span></span>
- <span data-ttu-id="f06e8-128">장치의 BitLocker 복구 키를 AD의 컴퓨터 개체 아래에 저장하여 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-128">Backup the device's BitLocker recovery key by storing it under the computer object in AD.</span></span> <span data-ttu-id="f06e8-129">자세한 내용은 [BitLocker 키 저장(Surface Hub)](save-bitlocker-key-surface-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06e8-129">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>
- <span data-ttu-id="f06e8-130">암호화된 통신을 위해 시스템 시계를 도메인 컨트롤러와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-130">Synchronize the system clock with the domain controller for encrypted communication</span></span>

<span data-ttu-id="f06e8-131">Surface Hub는 도메인 컨트롤러의 그룹 정책 또는 인증서 적용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-131">Surface Hub does not support applying group policies or certificates from the domain controller.</span></span>

> [!NOTE]
> <span data-ttu-id="f06e8-132">Surface Hub가 도메인과의 신뢰를 읽을 경우(예: 도메인에 가입된 후 도메인에서 Surface Hub를 제거하는 경우) 장치에 인증하여 설정을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-132">If your Surface Hub loses trust with the domain (for example, if you remove the Surface Hub from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="f06e8-133">도메인과 Surface Hub의 트러스트 관계를 제거하려는 경우 먼저 [장치를 초기화](device-reset-surface-hub.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-133">If you decide to remove the trust relationship of the Surface Hub with your domain, [reset the device](device-reset-surface-hub.md) first.</span></span>


### <span data-ttu-id="f06e8-134">Azure AD(Active Directory)에 장치 가입</span><span class="sxs-lookup"><span data-stu-id="f06e8-134">Azure Active Directory (Azure AD) join the device</span></span>

<span data-ttu-id="f06e8-135">Surface Hub를 Azure AD에 조인하여 Azure AD 테넌트의 IT 전문가가 설정을 구성하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-135">You can Azure AD join the Surface Hub to allow IT pros from your Azure AD tenant to configure settings.</span></span> <span data-ttu-id="f06e8-136">첫 실행 중에 [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory)를 사용하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-136">During first run, choose to use [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory).</span></span> <span data-ttu-id="f06e8-137">선택한 Azure AD 테넌트에 조인할 수 있는 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-137">You will need to provide credentials that are capable of joining the Azure AD tenant of your choice.</span></span> <span data-ttu-id="f06e8-138">Azure AD에 성공적으로 조인한 후 장치에서 해당 사용자에게 관리자 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-138">After you successfully Azure AD join, the appropriate people will be granted admin rights on the device.</span></span>

<span data-ttu-id="f06e8-139">기본적으로 모든 **전역 관리자**에게 Azure AD에 조인된 Surface Hub에 대한 관리자 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-139">By default, all **global administrators** will be given admin rights on an Azure AD joined Surface Hub.</span></span> <span data-ttu-id="f06e8-140">**Azure AD Premium** 또는 **EMS(Enterprise Mobility Suite)** 를 통해 다른 관리자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-140">With **Azure AD Premium** or **Enterprise Mobility Suite (EMS)**, you can add additional administrators:</span></span>
1.  <span data-ttu-id="f06e8-141">[Azure 클래식 포털](https://manage.windowsazure.com/)에서 **Active Directory**를 클릭하고 조직 디렉터리의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-141">In the [Azure classic portal](https://manage.windowsazure.com/), click **Active Directory**, and then click the name of your organization's directory.</span></span>
2.  <span data-ttu-id="f06e8-142">**구성** 페이지의 **장치** > **Azure AD 조인 장치의 추가 관리자**에서 **선택됨**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-142">On the **Configure** page, under **Devices** > **Additional administrators on Azure AD joined devices**, click **Selected**.</span></span>
3.  <span data-ttu-id="f06e8-143">**추가**를 클릭하고 Surface Hub 및 기타 Azure AD 조인 장치에서 관리자로 추가할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-143">Click **Add**, and select the users you want to add as administrators on your Surface Hub and other Azure AD joined devices.</span></span>
4.  <span data-ttu-id="f06e8-144">작업을 마치면 확인 표시 단추를 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-144">When you have finished, click the checkmark button to save your change.</span></span>

#### <span data-ttu-id="f06e8-145">Surface Hub를 Azure AD에 조인하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="f06e8-145">What happens when you Azure AD join your Surface Hub?</span></span>
<span data-ttu-id="f06e8-146">Surface Hub에서는 Azure AD 조인을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-146">Surface Hubs use Azure AD join to:</span></span>
- <span data-ttu-id="f06e8-147">Azure AD 테넌트의 적절한 사용자에게 관리자 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-147">Grant admin rights to the appropriate users in your Azure AD tenant.</span></span>
- <span data-ttu-id="f06e8-148">장치를 Azure AD에 조인하는 데 사용된 계정으로 장치의 BitLocker 복구 키를 저장하여 해당 키를 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-148">Backup the device's BitLocker recovery key by storing it under the account that was used to Azure AD join the device.</span></span> <span data-ttu-id="f06e8-149">자세한 내용은 [BitLocker 키 저장(Surface Hub)](save-bitlocker-key-surface-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f06e8-149">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>

### <span data-ttu-id="f06e8-150">Azure Active Directory join을 통한 자동 등록</span><span class="sxs-lookup"><span data-stu-id="f06e8-150">Automatic enrollment via Azure Active Directory join</span></span>

<span data-ttu-id="f06e8-151">Surface Hub는 이제 디바이스를 Azure Active Directory에 가입 하 여 Intune에 자동으로 등록 하는 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-151">Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory.</span></span> 

<span data-ttu-id="f06e8-152">자세한 내용은 [Windows 10 자동 등록 사용](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f06e8-152">For more information, see [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

### <span data-ttu-id="f06e8-153">무엇을 선택해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="f06e8-153">Which should I choose?</span></span>

<span data-ttu-id="f06e8-154">조직에서 AD 또는 Azure AD를 사용하는 경우 주로 보안상의 이유로 도메인에 가입하거나 Azure AD에 조인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-154">If your organization is using AD or Azure AD, we recommend you either domain join or Azure AD join, primarily for security reasons.</span></span> <span data-ttu-id="f06e8-155">사용자는 고유한 자격 증명을 사용하여 인증하고 설정을 잠금 해제할 수 있으며, 도메인과 관련된 보안 그룹에 추가되거나 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06e8-155">People will be able to authenticate and unlock Settings with their own credentials, and can be moved in or out of the security groups associated with your domain.</span></span>

| <span data-ttu-id="f06e8-156">옵션</span><span class="sxs-lookup"><span data-stu-id="f06e8-156">Option</span></span>                                            | <span data-ttu-id="f06e8-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f06e8-157">Requirements</span></span>                            | <span data-ttu-id="f06e8-158">설정 앱에 액세스하는 데 사용할 수 있는 자격 증명은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f06e8-158">Which credentials can be used to access the Settings app?</span></span>  |
|---------------------------------------------------|-----------------------------------------|-------|
| <span data-ttu-id="f06e8-159">로컬 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f06e8-159">Create a local admin account</span></span>                      | <span data-ttu-id="f06e8-160">없음</span><span class="sxs-lookup"><span data-stu-id="f06e8-160">None</span></span>                                    | <span data-ttu-id="f06e8-161">첫 실행 중에 지정된 사용자 이름 및 암호</span><span class="sxs-lookup"><span data-stu-id="f06e8-161">The user name and password specified during first run</span></span> |
| <span data-ttu-id="f06e8-162">AD(Active Directory)에 대한 도메인 가입</span><span class="sxs-lookup"><span data-stu-id="f06e8-162">Domain join to Active Directory (AD)</span></span>              | <span data-ttu-id="f06e8-163">조직에서 AD를 사용함</span><span class="sxs-lookup"><span data-stu-id="f06e8-163">Your organization uses AD</span></span>               | <span data-ttu-id="f06e8-164">도메인에 있는 특정 보안 그룹의 임의 AD 사용자</span><span class="sxs-lookup"><span data-stu-id="f06e8-164">Any AD user from a specific security group in your domain</span></span> |
| <span data-ttu-id="f06e8-165">Azure AD(Active Directory)에 장치 가입</span><span class="sxs-lookup"><span data-stu-id="f06e8-165">Azure Active Directory (Azure AD) join the device</span></span> | <span data-ttu-id="f06e8-166">조직에서 Azure AD Basic을 사용함</span><span class="sxs-lookup"><span data-stu-id="f06e8-166">Your organization uses Azure AD Basic</span></span>   | <span data-ttu-id="f06e8-167">전역 관리자만</span><span class="sxs-lookup"><span data-stu-id="f06e8-167">Global administrators only</span></span> |
| &nbsp;                                            | <span data-ttu-id="f06e8-168">조직에서 Azure AD Premium 또는 EMS(Enterprise Mobility Suite)를 사용함</span><span class="sxs-lookup"><span data-stu-id="f06e8-168">Your organization uses Azure AD Premium or Enterprise Mobility Suite (EMS)</span></span> | <span data-ttu-id="f06e8-169">전역 관리자 및 추가 관리자</span><span class="sxs-lookup"><span data-stu-id="f06e8-169">Global administrators and additional administrators</span></span> |


