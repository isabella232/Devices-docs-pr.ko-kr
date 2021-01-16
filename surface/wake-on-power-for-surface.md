---
title: Surface용 절전 모드 해제를 사용하도록 설정하는 방법
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Surface 디바이스의 전원 절전 모드 해제 및 해제 방법을 설명하는 문서입니다.
keywords: 업데이트, 배포, 드라이버, wol, 절전 모드 해제
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271562"
---
# <span data-ttu-id="a3615-104">Surface 디바이스에 대한 Wake On Power</span><span class="sxs-lookup"><span data-stu-id="a3615-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="a3615-105">책상에 있는 동안 Surface 디바이스를 꺼지거나 최대 절전 모드로 설정하여 배터리 사용 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="a3615-106">이러한 디바이스의 관리 성능을 향상하기 위해 절전 모드 해제를 사용하면 호환되는 Surface 디바이스가 전원에 다시 연결될 때 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="a3615-107">전원 절전 모드 해제를 구성하기 위해 Surface UEFI 구성기 또는 UEFI 관리자를 통해 SURFACE SEMM(엔터프라이즈 관리 모드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="a3615-108">절전 모드 해제 기능은 다음 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="a3615-109">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="a3615-109">Surface Pro 7+</span></span>
- <span data-ttu-id="a3615-110">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="a3615-110">Surface Book 3</span></span>
- <span data-ttu-id="a3615-111">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a3615-111">Surface Pro 7</span></span>
- <span data-ttu-id="a3615-112">Surface 노트북 3</span><span class="sxs-lookup"><span data-stu-id="a3615-112">Surface Laptop 3</span></span>
- <span data-ttu-id="a3615-113">Surface 노트북 이동</span><span class="sxs-lookup"><span data-stu-id="a3615-113">Surface Laptop Go</span></span>
- <span data-ttu-id="a3615-114">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="a3615-114">Surface Pro X</span></span> 


## <span data-ttu-id="a3615-115">개요 및 선행 사항</span><span class="sxs-lookup"><span data-stu-id="a3615-115">Overview and prerequisites</span></span>

<span data-ttu-id="a3615-116">Surface UEFI 구성 도구를 사용하면 대상 장치에 배포하기 위해 개별 UEFI 설정을 Windows Installer .msi 패키지에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3615-117">이 문서에서는 SEMM 사용 방법을 알고 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="a3615-118">자세한 내용은 [SURFACE SEMM(엔터프라이즈 관리 모드) 설명서를 참조하세요.](surface-enterprise-management-mode.md)</span><span class="sxs-lookup"><span data-stu-id="a3615-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="a3615-119">절전 모드 해제를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a3615-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="a3615-120">최신 버전의 [Surface UEFI 구성기 다운로드](https://www.microsoft.com/download/confirmation.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="a3615-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="a3615-121">관리자 권한으로 Surface 디바이스에 로그인하고 **Surface UEFI 구성**관리자를 열고 **Surface 디바이스를**선택한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3615-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Surface 디바이스를 선택하고 다음을 선택합니다.":::
3.  <span data-ttu-id="a3615-123">시작을 선택한 다음 **구성 패키지에서** \*\*\*\* **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3615-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="구성 패키지 만들기를 선택합니다.":::
4.  <span data-ttu-id="a3615-125">인증서 **보호를 선택하고**인증서 .pfx 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="a3615-126">Enter your password, select **Next,** add **Password Protection**, as appropriate, and then select **Next.**</span><span class="sxs-lookup"><span data-stu-id="a3615-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="a3615-127">대상으로 **지정하려는 Surface** 유형 선택 페이지에서 대상 디바이스를 적절하게 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="a3615-128">예를 들어 **Surface Pro 7을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3615-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="a3615-129">고급 기능 **페이지에서** 전원 \*\*\*\* 절전 모드 해제를 선택하고 기능을 **On으로**설정한 후 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3615-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="전원 절전 모드 해제를 선택하고 설정으로 설정"::: 
8.  <span data-ttu-id="a3615-131">성공 **페이지에서** 종료를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3615-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3615-132">장치에 설정을 처음 제공하는 경우 인증서 지문의 마지막 두 문자도 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="a3615-133">.msi 패키지를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-133">Save the .msi package.</span></span> 

## <span data-ttu-id="a3615-134">MSI 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="a3615-134">Apply the MSI package</span></span> 

<span data-ttu-id="a3615-135">Microsoft Endpoint Configuration Manager와 같은 소프트웨어 배포 도구를 사용하여 네트워크의 장치에 MSI 패키지를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a3615-136">이 절차에는 로컬 컴퓨터에 패키지를 설치하는 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="a3615-137">승격된 명령 프롬프트에서 .msi 파일의 전체 경로를 입력하여 .msi 패키지를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="a3615-138">경고 **대화** 상자에서 확인을 **선택하거나** BitLocker를 사용하지 않도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3615-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="확인을 선택하거나 BitLocker를 적절하게 사용하지 않도록 설정하십시오.":::
3.  <span data-ttu-id="a3615-140">시작 페이지에서 다음을 **선택하여** 패키지를 실행하고 새로 구성된 UEFI 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="시작 페이지 중 하나에서 다음을 선택합니다.":::
4.  <span data-ttu-id="a3615-142">장치를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-142">Restart your device.</span></span> 

<span data-ttu-id="a3615-143">전원 절전 모드 해제가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-143">Wake on Power is now configured.</span></span> <span data-ttu-id="a3615-144">설정을 테스트하려면 디바이스를 끄고 전원을 끊은 다음 전원을 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="a3615-145">장치가 자동으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3615-145">The device should start automatically.</span></span> 

## <span data-ttu-id="a3615-146">참조</span><span class="sxs-lookup"><span data-stu-id="a3615-146">References</span></span>

<span data-ttu-id="a3615-147">자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3615-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="a3615-148">Surface Enterprise 관리 모드</span><span class="sxs-lookup"><span data-stu-id="a3615-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="a3615-149">Surface 디바이스용 LAN 절전 모드 해제</span><span class="sxs-lookup"><span data-stu-id="a3615-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="a3615-150">그래도 문제가 해결되지 않을 경우</span><span class="sxs-lookup"><span data-stu-id="a3615-150">Still need help?</span></span> <span data-ttu-id="a3615-151">Microsoft [커뮤니티로 이동](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a3615-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>