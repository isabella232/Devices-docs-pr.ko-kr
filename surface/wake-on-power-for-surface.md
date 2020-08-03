---
title: 화면 전원을 켤 때 절전 모드 해제를 사용 하는 방법
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Surface 장치에서 절전 모드 해제 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 설명 합니다.
keywords: 업데이트, 배포, 드라이버, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903021"
---
# <span data-ttu-id="9f48f-104">Surface 장치에서 절전 모드 해제</span><span class="sxs-lookup"><span data-stu-id="9f48f-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="9f48f-105">배터리를 절약 하기 위해 화면 장치를 책상 밖으로 끄거나 최대 절전 모드로 설정 하 여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="9f48f-106">이러한 디바이스의 관리 효율성을 높이기 위해 절전 모드 해제 기능을 사용 하면 전원에 다시 연결 되었을 때 호환 가능한 표면 장치가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="9f48f-107">전원을 켤 때 절전 모드를 사용 하려면 Surface UEFI 구성자 또는 UEFI 관리자를 통해 Surface MM (Surface Enterprise Management Mode)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="9f48f-108">Wake on 전원은 다음 장치에서 사용할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="9f48f-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="9f48f-109">Surface Book 3</span></span>
- <span data-ttu-id="9f48f-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="9f48f-110">Surface Pro 7</span></span>
- <span data-ttu-id="9f48f-111">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="9f48f-111">Surface Laptop 3</span></span>
- <span data-ttu-id="9f48f-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="9f48f-112">Surface Pro X</span></span> 

## <span data-ttu-id="9f48f-113">개요 및 전제 조건</span><span class="sxs-lookup"><span data-stu-id="9f48f-113">Overview and prerequisites</span></span>

<span data-ttu-id="9f48f-114">Surface UEFI 구성자를 사용 하 여 대상 장치에 배포 하기 위해 Windows Installer. msi 패키지에 저장 되는 개별 UEFI 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="9f48f-115">이 문서에서는 사용자가 SEMM 사용을 잘 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="9f48f-116">자세한 내용은 [Surface Enterprise 관리 모드 (SEMM)](surface-enterprise-management-mode.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f48f-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="9f48f-117">절전 모드 해제 기능을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9f48f-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="9f48f-118">[SURFACE UEFI 구성자](https://www.microsoft.com/download/confirmation.aspx?id=46703)의 최신 버전을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="9f48f-119">Surface device에 관리자로 로그인 하 고, **SURFACE UEFI Configurator**를 열고, **surface Devices**를 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Surface 장치를 선택 하 고 다음을 선택 합니다.":::
3.  <span data-ttu-id="9f48f-121">**시작** 을 선택 하 고 **구성 패키지** 에서 **만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="구성 패키지 만들기를 선택 합니다.":::
4.  <span data-ttu-id="9f48f-123">**인증서 보호** 를 선택 하 고 인증서 pfx 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="9f48f-124">비밀 번호를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="9f48f-125">적절 하 게 **암호 보호**를 추가 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="9f48f-126">**대상으로 지정할 표면 유형 선택** 페이지에서 대상 장치를 적절 하 게 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="9f48f-127">예를 들어 **Surface Pro 7**이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="9f48f-128">**고급 기능** 페이지에서 **절전 모드 해제** 를 선택 하 고 켜기 ( **on**)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="9f48f-129">**다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="전원을 켠 후 절전 모드 해제를 선택 합니다."::: 
7.  <span data-ttu-id="9f48f-131">**성공** 페이지에서 **종료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="9f48f-132">장치에 대 한 설정을 처음 제공 하는 경우 인증서 손도장의 마지막 두 문자를 제공 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="9f48f-133">.Msi 패키지를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-133">Save the .msi package.</span></span> 

## <span data-ttu-id="9f48f-134">MSI 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="9f48f-134">Apply the MSI package</span></span> 

<span data-ttu-id="9f48f-135">Microsoft 끝점 구성 관리자와 같은 소프트웨어 배포 도구를 사용 하 여 네트워크를 통해 장치에 MSI 패키지를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="9f48f-136">이 절차에는 로컬 컴퓨터에 패키지를 설치 하는 단계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="9f48f-137">관리자 권한 명령 프롬프트를 열고 .msi 파일의 전체 경로를 입력 하 여 .msi 패키지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="9f48f-138">**경고** 대화 상자에서 **확인** 또는 필요에 따라 Bitlocker 사용 안 함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="확인 또는 필요에 따라 Bitlocker 사용 안 함을 선택 합니다.":::
3.  <span data-ttu-id="9f48f-140">시작 페이지에서 **다음** 을 선택 하 여 패키지를 실행 하 고 새로 구성 된 UEFI 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="시작 페이지에서 다음을 선택 합니다.":::
4.  <span data-ttu-id="9f48f-142">장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-142">Restart your device.</span></span> 

<span data-ttu-id="9f48f-143">이제 Wake on 전원이 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-143">Wake on Power is now configured.</span></span> <span data-ttu-id="9f48f-144">설정을 테스트 하려면 장치를 끄고 전원 케이블을 뽑은 다음 전원을 다시 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="9f48f-145">장치가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f48f-145">The device will start automatically.</span></span> 

## <span data-ttu-id="9f48f-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9f48f-146">More information</span></span>

<span data-ttu-id="9f48f-147">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f48f-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="9f48f-148">Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="9f48f-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="9f48f-149">Surface 장치에 대 한 Wake on LAN</span><span class="sxs-lookup"><span data-stu-id="9f48f-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="9f48f-150">그래도 문제가 해결되지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="9f48f-150">Still need help?</span></span> <span data-ttu-id="9f48f-151">[Microsoft 커뮤니티](https://answers.microsoft.com/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f48f-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>