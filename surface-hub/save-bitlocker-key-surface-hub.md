---
title: BitLocker 키 저장(Surface Hub)
description: 모든 Microsoft Surface Hub가 BitLocker 드라이브 암호화 소프트웨어를 사용하여 자동으로 설정됩니다. BitLocker 복구 키를 백업하는 것이 좋습니다.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, Bitlocker 복구 키
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836463"
---
# <span data-ttu-id="00fa0-105">BitLocker 키 저장(Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="00fa0-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="00fa0-106">모든 Microsoft Surface Hub가 BitLocker 드라이브 암호화 소프트웨어를 사용하여 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="00fa0-107">BitLocker 복구 키를 백업하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="00fa0-108">Surface Hub에서 BitLocker 키를 관리하는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="00fa0-109">Surface Hub를 도메인에 가입한 경우 장치가 도메인에 키를 백업하고 컴퓨터 개체 아래에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="00fa0-110">장치를 도메인에 가입한 후 BitLocker 키를 찾을 수 없는 경우 Active Directory 스키마에서 BitLocker 키 백업을 지원하지 않을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="00fa0-111">스키마를 변경하지 않으려면 설정으로 이동한 다음 로컬 관리자 계정을 사용하는 절차에 따라 BitLocker 키를 저장할 수 있습니다. 해당 절차는 이 목록의 뒷부분에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="00fa0-112">Surface Hub를 Azure AD(Active Directory)에 가입한 경우 장치를 가입하는 데 사용된 계정 아래에 BitLocker 키가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="00fa0-113">로컬 관리자 계정을 사용 하 여 장치를 관리 하는 경우 **설정** 앱으로 이동 하 여 BitLocker 키를 저장 하 고 **& 보안** 복구를 업데이트 하도록 탐색할 수 있습니다 &gt; **Recovery**.</span><span class="sxs-lookup"><span data-stu-id="00fa0-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="00fa0-114">USB 드라이브를 삽입하고 BitLocker 키를 저장하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="00fa0-115">키는 USB 드라이브의 텍스트 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa0-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="00fa0-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="00fa0-116">Related topics</span></span>

[<span data-ttu-id="00fa0-117">Microsoft Surface Hub 관리</span><span class="sxs-lookup"><span data-stu-id="00fa0-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="00fa0-118">Microsoft Surface Hub 관리자 가이드</span><span class="sxs-lookup"><span data-stu-id="00fa0-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





