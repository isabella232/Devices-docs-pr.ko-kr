---
title: 관리자 그룹 관리
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
ms.date: 02/01/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: c76ac577c1560020bf865a25d4a812343089013a
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314441"
---
# <span data-ttu-id="9374e-104">Surface Hub에 대한 관리자 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="9374e-104">Admin group management for Surface Hub</span></span>


<span data-ttu-id="9374e-105">디바이스에서 설정 앱을 사용하여 각 Surface Hub를 개별적으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-105">Every Surface Hub can be configured locally using the Settings app on the device.</span></span> <span data-ttu-id="9374e-106">권한이 없는 사용자가 설정을 변경하지 못하도록 설정 앱에서는 관리자 자격 증명을 사용하여 앱을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-106">To prevent unauthorized users from changing settings, the Settings app requires admin credentials to open the app.</span></span>


## <span data-ttu-id="9374e-107">관리자 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="9374e-107">Admin Group Management</span></span>

<span data-ttu-id="9374e-108">다음과 같은 방법으로 디바이스에 대한 관리자 계정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-108">You can set up administrator accounts for the device in the following ways:</span></span>

- [<span data-ttu-id="9374e-109">로컬 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="9374e-109">Create a local admin account</span></span>](#create-a-local-admin-account)
- [<span data-ttu-id="9374e-110">디바이스를 Active Directory에 도메인 가입</span><span class="sxs-lookup"><span data-stu-id="9374e-110">Domain join the device to Active Directory</span></span>](#domain-join-the-device-to-active-directory)
- [<span data-ttu-id="9374e-111">디바이스에 Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="9374e-111">Azure AD join the device</span></span>](#azure-ad-join-the-device)
- [<span data-ttu-id="9374e-112">Azure AD 가입 장치에서 전역이 아닌 관리자 계정 구성(Surface Hub 2S)</span><span class="sxs-lookup"><span data-stu-id="9374e-112">Configure non Global admin accounts on Azure AD joined devices (Surface Hub 2S)</span></span>](#configure-non-global-admin-accounts-on-azure-ad-joined-devices)


### <span data-ttu-id="9374e-113">로컬 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="9374e-113">Create a local admin account</span></span>

<span data-ttu-id="9374e-114">로컬 관리자를 만들려면 [첫 실행 중에 로컬 관리자를 사용하도록 선택합니다](first-run-program-surface-hub.md#use-a-local-admin).</span><span class="sxs-lookup"><span data-stu-id="9374e-114">To create a local admin, [choose to use a local admin during first run](first-run-program-surface-hub.md#use-a-local-admin).</span></span> <span data-ttu-id="9374e-115">이렇게 하면 선택한 사용자 이름과 암호를 사용하여 Surface Hub에 단일 로컬 관리자 계정이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-115">This will create a single local admin account on the Surface Hub with the username and password of your choice.</span></span> <span data-ttu-id="9374e-116">이러한 자격 증명을 사용하여 설정 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-116">Use these credentials to open the Settings app.</span></span>

<span data-ttu-id="9374e-117">관리 계정 정보는 디렉터리 서비스에서 백업하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-117">Note that the local admin account information is not backed by any directory service.</span></span> <span data-ttu-id="9374e-118">장치가 AD(Active Directory) 또는 Azure AD(Active Directory)에 액세스할 수 없는 경우에만 로컬 관리자를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-118">We recommend you only choose a local admin if the device does not have access to Active Directory (AD) or Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9374e-119">로컬 관리자의 암호를 변경하려는 경우 설정에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-119">If you decide to change the local admin’s password, you can do so in Settings.</span></span> <span data-ttu-id="9374e-120">그러나 로컬 관리자 계정 사용에서 도메인 또는 Azure AD 테넌트의 그룹 사용으로 변경하려는 경우 [장치를 초기화](device-reset-surface-hub.md)하고 처음 프로그램을 다시 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-120">However, if you want to change from using the local admin account to using a group from your domain or Azure AD tenant, then you’ll need to [reset the device](device-reset-surface-hub.md) and go through the first-time program again.</span></span>

### <span data-ttu-id="9374e-121">디바이스를 Active Directory에 도메인 가입</span><span class="sxs-lookup"><span data-stu-id="9374e-121">Domain join the device to Active Directory</span></span>

<span data-ttu-id="9374e-122">Surface Hub를 AD 도메인에 가입시켜 지정된 보안 그룹의 사용자가 설정을 구성하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-122">You can domain join the Surface Hub to your AD domain to allow users from a specified security group to configure settings.</span></span> <span data-ttu-id="9374e-123">첫 실행 중에 [Active Directory 도메인 서비스](first-run-program-surface-hub.md#use-active-directory-domain-services)를 사용하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-123">During first run, choose to use [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services).</span></span> <span data-ttu-id="9374e-124">선택한 도메인에 가입할 수 있는 자격 증명과 기존 보안 그룹의 이름을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-124">You'll need to provide credentials that are capable of joining the domain of your choice, and the name of an existing security group.</span></span> <span data-ttu-id="9374e-125">해당 보안 그룹의 구성원인 사용자가 자격 증명을 입력하고 설정을 잠금 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-125">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>

#### <span data-ttu-id="9374e-126">Surface Hub를 도메인에 가입시키면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="9374e-126">What happens when you domain join your Surface Hub?</span></span>
<span data-ttu-id="9374e-127">Surface Hub에서는 도메인 가입을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-127">Surface Hubs use domain join to:</span></span>
- <span data-ttu-id="9374e-128">AD에서 지정된 보안 그룹의 구성원에게 관리자 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-128">Grant admin rights to members of a specified security group in AD.</span></span>
- <span data-ttu-id="9374e-129">장치의 BitLocker 복구 키를 AD의 컴퓨터 개체 아래에 저장하여 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-129">Backup the device's BitLocker recovery key by storing it under the computer object in AD.</span></span> <span data-ttu-id="9374e-130">자세한 내용은 [BitLocker 키 저장(Surface Hub)](save-bitlocker-key-surface-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9374e-130">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>
- <span data-ttu-id="9374e-131">암호화된 통신을 위해 시스템 시계를 도메인 컨트롤러와 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-131">Synchronize the system clock with the domain controller for encrypted communication</span></span>

<span data-ttu-id="9374e-132">Surface Hub는 도메인 컨트롤러의 그룹 정책 또는 인증서 적용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-132">Surface Hub does not support applying Group Policy or certificates from the domain controller.</span></span>

> [!NOTE]
> <span data-ttu-id="9374e-133">Surface Hub가 도메인과의 신뢰를 읽을 경우(예: 도메인에 가입된 후 도메인에서 Surface Hub를 제거하는 경우) 장치에 인증하여 설정을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-133">If your Surface Hub loses trust with the domain (for example, if you remove the Surface Hub from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="9374e-134">도메인과 Surface Hub의 트러스트 관계를 제거하려는 경우 먼저 [장치를 초기화](device-reset-surface-hub.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-134">If you decide to remove the trust relationship of the Surface Hub with your domain, [reset the device](device-reset-surface-hub.md) first.</span></span>


### <span data-ttu-id="9374e-135">디바이스에 Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="9374e-135">Azure AD join the device</span></span>

<span data-ttu-id="9374e-136">Azure AD(Azure Active Directory)에서 Surface Hub에 가입하여 Azure AD 테넌트의 IT 프로시저가 설정을 구성할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-136">You can Azure Active Directory (Azure AD) to join the Surface Hub to allow IT pros from your Azure AD tenant to configure settings.</span></span> <span data-ttu-id="9374e-137">첫 실행 중에 [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory)를 사용하도록 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-137">During first run, choose to use [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory).</span></span> <span data-ttu-id="9374e-138">선택한 Azure AD 테넌트에 조인할 수 있는 자격 증명을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-138">You will need to provide credentials that are capable of joining the Azure AD tenant of your choice.</span></span> <span data-ttu-id="9374e-139">Azure AD에 성공적으로 조인한 후 장치에서 해당 사용자에게 관리자 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-139">After you successfully Azure AD join, the appropriate people will be granted admin rights on the device.</span></span>

<span data-ttu-id="9374e-140">기본적으로 모든 **전역 관리자**에게 Azure AD에 조인된 Surface Hub에 대한 관리자 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-140">By default, all **global administrators** will be given admin rights on an Azure AD joined Surface Hub.</span></span> <span data-ttu-id="9374e-141">**Azure AD Premium** 또는 **EMS(Enterprise Mobility Suite)** 를 통해 다른 관리자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-141">With **Azure AD Premium** or **Enterprise Mobility Suite (EMS)**, you can add additional administrators:</span></span>
1.  <span data-ttu-id="9374e-142">[Azure 클래식 포털](https://manage.windowsazure.com/)에서 **Active Directory**를 클릭하고 조직 디렉터리의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-142">In the [Azure classic portal](https://manage.windowsazure.com/), click **Active Directory**, and then click the name of your organization's directory.</span></span>
2.  <span data-ttu-id="9374e-143">**구성** 페이지의 **장치** > **Azure AD 조인 장치의 추가 관리자**에서 **선택됨**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-143">On the **Configure** page, under **Devices** > **Additional administrators on Azure AD joined devices**, click **Selected**.</span></span>
3.  <span data-ttu-id="9374e-144">**추가**를 클릭하고 Surface Hub 및 기타 Azure AD 조인 장치에서 관리자로 추가할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-144">Click **Add**, and select the users you want to add as administrators on your Surface Hub and other Azure AD joined devices.</span></span>
4.  <span data-ttu-id="9374e-145">작업을 마치면 확인 표시 단추를 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-145">When you have finished, click the checkmark button to save your change.</span></span>

#### <span data-ttu-id="9374e-146">Surface Hub를 Azure AD에 조인하면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="9374e-146">What happens when you Azure AD join your Surface Hub?</span></span>
<span data-ttu-id="9374e-147">Surface Hub에서는 Azure AD 조인을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-147">Surface Hubs use Azure AD join to:</span></span>
- <span data-ttu-id="9374e-148">Azure AD 테넌트의 적절한 사용자에게 관리자 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-148">Grant admin rights to the appropriate users in your Azure AD tenant.</span></span>
- <span data-ttu-id="9374e-149">장치를 Azure AD에 조인하는 데 사용된 계정으로 장치의 BitLocker 복구 키를 저장하여 해당 키를 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-149">Backup the device's BitLocker recovery key by storing it under the account that was used to Azure AD join the device.</span></span> <span data-ttu-id="9374e-150">자세한 내용은 [BitLocker 키 저장(Surface Hub)](save-bitlocker-key-surface-hub.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9374e-150">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>

#### <span data-ttu-id="9374e-151">Azure Active Directory 가입을 통한 자동 등록</span><span class="sxs-lookup"><span data-stu-id="9374e-151">Automatic enrollment via Azure Active Directory join</span></span>

<span data-ttu-id="9374e-152">Surface Hub는 이제 디바이스를 Azure Active Directory에 가입하여 Intune에 자동으로 등록하는 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-152">Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory.</span></span> 

<span data-ttu-id="9374e-153">자세한 내용은 [Windows 10 자동 등록 사용을 참조하세요.](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="9374e-153">For more information, see [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

#### <span data-ttu-id="9374e-154">무엇을 선택해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="9374e-154">Which should I choose?</span></span>

<span data-ttu-id="9374e-155">조직에서 AD 또는 Azure AD를 사용하는 경우 주로 보안상의 이유로 도메인에 가입하거나 Azure AD에 조인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-155">If your organization is using AD or Azure AD, we recommend you either domain join or Azure AD join, primarily for security reasons.</span></span> <span data-ttu-id="9374e-156">사용자는 고유한 자격 증명을 사용하여 인증하고 설정을 잠금 해제할 수 있으며, 도메인과 관련된 보안 그룹에 추가되거나 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-156">People will be able to authenticate and unlock Settings with their own credentials, and can be moved in or out of the security groups associated with your domain.</span></span>

| <span data-ttu-id="9374e-157">옵션</span><span class="sxs-lookup"><span data-stu-id="9374e-157">Option</span></span>                                            | <span data-ttu-id="9374e-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9374e-158">Requirements</span></span>                            | <span data-ttu-id="9374e-159">설정 앱에 액세스하는 데 사용할 수 있는 자격 증명은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="9374e-159">Which credentials can be used to access the Settings app?</span></span>  |
|---------------------------------------------------|-----------------------------------------|-------|
| <span data-ttu-id="9374e-160">로컬 관리자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="9374e-160">Create a local admin account</span></span>                      | <span data-ttu-id="9374e-161">없음</span><span class="sxs-lookup"><span data-stu-id="9374e-161">None</span></span>                                    | <span data-ttu-id="9374e-162">첫 실행 중에 지정된 사용자 이름 및 암호</span><span class="sxs-lookup"><span data-stu-id="9374e-162">The user name and password specified during first run</span></span> |
| <span data-ttu-id="9374e-163">AD(Active Directory)에 대한 도메인 가입</span><span class="sxs-lookup"><span data-stu-id="9374e-163">Domain join to Active Directory (AD)</span></span>              | <span data-ttu-id="9374e-164">조직에서 AD를 사용함</span><span class="sxs-lookup"><span data-stu-id="9374e-164">Your organization uses AD</span></span>               | <span data-ttu-id="9374e-165">도메인에 있는 특정 보안 그룹의 임의 AD 사용자</span><span class="sxs-lookup"><span data-stu-id="9374e-165">Any AD user from a specific security group in your domain</span></span> |
| <span data-ttu-id="9374e-166">Azure AD(Active Directory)에 장치 가입</span><span class="sxs-lookup"><span data-stu-id="9374e-166">Azure Active Directory (Azure AD) join the device</span></span> | <span data-ttu-id="9374e-167">조직에서 Azure AD Basic을 사용함</span><span class="sxs-lookup"><span data-stu-id="9374e-167">Your organization uses Azure AD Basic</span></span>   | <span data-ttu-id="9374e-168">전역 관리자만</span><span class="sxs-lookup"><span data-stu-id="9374e-168">Global administrators only</span></span> |
| &nbsp;                                            | <span data-ttu-id="9374e-169">조직에서 Azure AD Premium 또는 EMS(Enterprise Mobility Suite)를 사용함</span><span class="sxs-lookup"><span data-stu-id="9374e-169">Your organization uses Azure AD Premium or Enterprise Mobility Suite (EMS)</span></span> | <span data-ttu-id="9374e-170">전역 관리자 및 추가 관리자</span><span class="sxs-lookup"><span data-stu-id="9374e-170">Global administrators and additional administrators</span></span> |


### <span data-ttu-id="9374e-171">Azure AD 가입 장치에서 전역이 아닌 관리자 계정 구성</span><span class="sxs-lookup"><span data-stu-id="9374e-171">Configure non Global admin accounts on Azure AD-joined devices</span></span>

<span data-ttu-id="9374e-172">Azure AD에 가입된 Surface Hub 2S 장치의 경우 Windows 10 Team 2020 업데이트를 통해 Surface Hub 2S의 설정 앱 관리에 대한 관리자 권한을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-172">For Surface Hub 2S devices joined to Azure AD, Windows 10 Team 2020 Update lets you limit admin permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="9374e-173">이렇게 하면 Surface Hub 2S에 대한 관리자 권한의 범위를 지정하고 잠재적으로 원치 않는 관리자가 전체 Azure AD 도메인에 액세스하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9374e-173">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="9374e-174">자세한 내용은 Surface Hub 2S에서 전역이 아닌 관리자 [계정 구성을 참조하세요.](surface-hub-2s-nonglobal-admin.md)</span><span class="sxs-lookup"><span data-stu-id="9374e-174">To learn more, see [Configure non Global admin accounts on Surface Hub 2S](surface-hub-2s-nonglobal-admin.md).</span></span>