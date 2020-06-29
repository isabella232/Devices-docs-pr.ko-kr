---
title: SEMM (Surface)에서 화면 디바이스의 등록을 해제 합니다.
description: Surface UEFI reset 패키지 또는 복구 요청 옵션을 사용 하 여 디바이스를 SEMM에서 등록 해제 하는 방법에 대해 알아봅니다.
keywords: surface enterprise 관리
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834607"
---
# <span data-ttu-id="d2a06-104">SEMM에서 Surface 장치 등록 해제</span><span class="sxs-lookup"><span data-stu-id="d2a06-104">Unenroll Surface devices from SEMM</span></span>

<span data-ttu-id="d2a06-105">Surface device가 Surface Enterprise 관리 모드 (SEMM)에 등록 되어 있는 경우 인증서는 해당 디바이스의 펌웨어에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-105">When a Surface device is enrolled in Surface Enterprise Management Mode (SEMM), a certificate is stored in the firmware of that device.</span></span> <span data-ttu-id="d2a06-106">해당 인증서와 SEMM의 등록은 디바이스가 SEMM에 등록 되어 있는 동안 서피스 UEFI 설정 또는 옵션에 대 한 무단 변경을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-106">The presence of that certificate and the enrollment in SEMM prevent any unauthorized changes to Surface UEFI settings or options while the device is enrolled in SEMM.</span></span> <span data-ttu-id="d2a06-107">Surface UEFI 설정의 제어권을 사용자에 게 복원 하려면 Surface 디바이스를 unenrolled에서 다시 설정 또는 복구로 설명 하는 프로세스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-107">To restore control of Surface UEFI settings to the user, the Surface device must be unenrolled from SEMM, a process sometimes described as reset or recovery.</span></span> <span data-ttu-id="d2a06-108">디바이스의 등록을 해제 하는 데 사용할 수 있는 방법에는 서피스 UEFI 재설정 패키지 및 복구 요청과 같은 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-108">There are two methods you can use to unenroll a device from SEMM—a Surface UEFI reset package and a Recovery Request.</span></span>

>[!WARNING]
><span data-ttu-id="d2a06-109">디바이스의 등록을 해제 하 고 Surface UEFI 설정의 사용자 정의 컨트롤을 복원 하려면 디바이스를 사용 하는 데 사용한 semm 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-109">To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate that was used to enroll the device in SEMM.</span></span> <span data-ttu-id="d2a06-110">이 인증서가 손실 되거나 손상 되 면 SEMM에서 등록을 취소 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-110">If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM.</span></span> <span data-ttu-id="d2a06-111">그에 따라 SEMM 인증서를 백업 하 고 보호 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a06-111">Back up and protect your SEMM certificate accordingly.</span></span>

<span data-ttu-id="d2a06-112">SEMM에 대 한 자세한 내용은 [Microsoft Surface Enterprise 관리 모드](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a06-112">For more information about SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="d2a06-113">Surface UEFI reset 패키지를 사용 하 여 Surface device를 SEMM에서 등록 해제</span><span class="sxs-lookup"><span data-stu-id="d2a06-113">Unenroll a Surface device from SEMM with a Surface UEFI reset package</span></span>

<span data-ttu-id="d2a06-114">Surface UEFI reset 패키지는 Surface device를 SEMM에서 등록 해제 하는 데 사용 하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-114">The Surface UEFI reset package is the primary method you use to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="d2a06-115">Surface UEFI 구성 패키지와 마찬가지로, 재설정 패키지는 디바이스에서 SEMM을 구성 하는 Windows Installer (.msi) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-115">Like a Surface UEFI configuration package, the reset package is a Windows Installer (.msi) file that configures SEMM on the device.</span></span> <span data-ttu-id="d2a06-116">구성 패키지와 달리 reset 패키지는 Surface 디바이스의 Surface UEFI 구성을 기본 설정으로 초기화 하 고, SEMM 인증서를 제거 하 고, 디바이스를 SEMM에서 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-116">Unlike the configuration package, the reset package will reset the Surface UEFI configuration on a Surface device to its default settings, remove the SEMM certificate, and unenroll the device from SEMM.</span></span>

<span data-ttu-id="d2a06-117">재설정 패키지는 개별 서피스 장치에 맞게 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-117">Reset packages are created specifically for an individual Surface device.</span></span> <span data-ttu-id="d2a06-118">다시 설정 패키지를 만드는 프로세스를 시작 하려면 등록을 해제 하려는 디바이스의 일련 번호와 디바이스를 등록 하는 데 사용 되는 SEMM 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-118">To begin the process of creating a reset package, you will need the serial number of the device you want to unenroll, as well as the SEMM certificate used to enroll the device.</span></span> <span data-ttu-id="d2a06-119">그림 1과 같이 Surface UEFI의 **PC 정보** 페이지에서 surface device의 일련 번호를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-119">You can find the serial number of your Surface device on the **PC information** page of Surface UEFI, as shown in Figure 1.</span></span> <span data-ttu-id="d2a06-120">Surface UEFI가 암호로 보호 되 고 잘못 된 암호가 입력 된 경우에도이 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-120">This page is displayed even if Surface UEFI is password protected and the incorrect password is entered.</span></span>

![Surface device의 일련 번호가 표시 됩니다.](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*<span data-ttu-id="d2a06-122">그림 1.</span><span class="sxs-lookup"><span data-stu-id="d2a06-122">Figure 1.</span></span> <span data-ttu-id="d2a06-123">Surface device의 일련 번호가 Surface UEFI PC 정보 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-123">The serial number of the Surface device is displayed on the Surface UEFI PC information page</span></span>*

>[!NOTE]
><span data-ttu-id="d2a06-124">Surface UEFI로 부팅 하려면 장치를 끄는 동안 **볼륨을 위아래로** 누르고 동시에 **전원을 켭니다** .</span><span class="sxs-lookup"><span data-stu-id="d2a06-124">To boot to Surface UEFI, press **Volume Up** and **Power** simultaneously while the device is off.</span></span> <span data-ttu-id="d2a06-125">Surface 로고가 표시 되 고 장치가 부팅 되기 시작할 때까지 **볼륨을** 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-125">Hold **Volume Up** until the Surface logo is displayed and the device begins to boot.</span></span>

<span data-ttu-id="d2a06-126">Surface UEFI 다시 설정 패키지를 만들려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-126">To create a Surface UEFI reset package, follow these steps:</span></span>

1. <span data-ttu-id="d2a06-127">시작 메뉴에서 Microsoft Surface UEFI 구성자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-127">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="d2a06-128">**시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-128">Click **Start**.</span></span>
3. <span data-ttu-id="d2a06-129">그림 2에 표시 된 대로 **패키지 다시 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-129">Click **Reset Package**, as shown in Figure 2.</span></span>

   ![패키지 다시 설정을 선택 하 여 패키지를 등록 해제 Surface device (SEMM)로 만듭니다.](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *<span data-ttu-id="d2a06-131">그림 2.</span><span class="sxs-lookup"><span data-stu-id="d2a06-131">Figure 2.</span></span> <span data-ttu-id="d2a06-132">패키지 재설정을 클릭 하 여 Surface 디바이스의 등록을 취소 하는 패키지 만들기 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="d2a06-132">Click Reset Package to create a package to unenroll a Surface device from SEMM</span></span>*

4. <span data-ttu-id="d2a06-133">그림 3과 같이 개인 키 (.pfx)를 사용 하 여 SEMM 인증서 파일을 추가 하려면 **인증서 보호** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-133">Click **Certificate Protection** to add your SEMM certificate file with private key (.pfx), as shown in Figure 3.</span></span> <span data-ttu-id="d2a06-134">인증서 파일의 위치로 이동 하 여 파일을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-134">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![Surface UEFI 다시 설정 패키지에 SEMM 인증서 추가](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *<span data-ttu-id="d2a06-136">그림 3.</span><span class="sxs-lookup"><span data-stu-id="d2a06-136">Figure 3.</span></span> <span data-ttu-id="d2a06-137">Surface UEFI 다시 설정 패키지에 SEMM 인증서 추가</span><span class="sxs-lookup"><span data-stu-id="d2a06-137">Add the SEMM certificate to a Surface UEFI reset package</span></span>*

5. <span data-ttu-id="d2a06-138">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-138">Click **Next**.</span></span>
6. <span data-ttu-id="d2a06-139">(그림 4)에서 등록을 취소 하려는 장치의 일련 번호를 입력 한 다음 **빌드** 를 클릭 하 여 Surface UEFI 다시 설정 패키지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-139">Type the serial number of the device you want to unenroll from SEMM (as shown in Figure 4), and then click **Build** to generate the Surface UEFI reset package.</span></span>

   ![Surface 디바이스의 일련 번호를 사용 하 여 Surface UEFI 다시 설정 패키지 만들기](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *<span data-ttu-id="d2a06-141">그림 4.</span><span class="sxs-lookup"><span data-stu-id="d2a06-141">Figure 4.</span></span> <span data-ttu-id="d2a06-142">Surface device의 일련 번호를 사용 하 여 Surface UEFI 다시 설정 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="d2a06-142">Use the serial number of your Surface device to create a Surface UEFI reset package</span></span>*

7. <span data-ttu-id="d2a06-143">다른 이름 **으로 저장** 대화 상자에서 Surface UEFI 다시 설정 패키지의 이름을 지정 하 고 파일을 저장할 위치로 이동한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-143">In the **Save As** dialog box, specify a name for the Surface UEFI reset package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
8. <span data-ttu-id="d2a06-144">패키지 생성이 완료 되 면 **성공** 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-144">When the package generation has completed, the **Successful** page is displayed.</span></span> <span data-ttu-id="d2a06-145">**끝내기** 를 클릭 하 여 패키지 만들기를 완료 하 고 MICROSOFT Surface UEFI 구성자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-145">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

<span data-ttu-id="d2a06-146">Surface 장치에서 Surface UEFI 다시 설정 패키지 Windows Installer (.msi) 파일을 실행 하 여 디바이스를 SEMM에서 등록 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-146">Run the Surface UEFI reset package Windows Installer (.msi) file on the Surface device to unenroll the device from SEMM.</span></span> <span data-ttu-id="d2a06-147">다시 설정 패키지는 등록 해제 작업을 수행 하기 위해 다시 부팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-147">The reset package will require a reboot to perform the unenroll operation.</span></span> <span data-ttu-id="d2a06-148">장치가 unenrolled 된 후에는 **프로그램 및 기능** (그림 5)에서 **Microsoft Surface 구성 패키지** 항목이 더 이상 표시 되지 않도록 하 여 제거를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-148">After the device has been unenrolled, you can verify the successful removal by ensuring that the **Microsoft Surface Configuration Package** item in **Programs and Features** (shown in Figure 5) is no longer present.</span></span>

![장치가 표시 되는 화면은 SEMM로 등록 되어 있습니다.](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*<span data-ttu-id="d2a06-150">그림 5.</span><span class="sxs-lookup"><span data-stu-id="d2a06-150">Figure 5.</span></span> <span data-ttu-id="d2a06-151">프로그램 및 기능에 Microsoft Surface Configuration Package 항목이 있는 경우 장치가 SEMM에 등록 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-151">The presence of the Microsoft Surface Configuration Package item in Programs and Features indicates that the device is enrolled in SEMM</span></span>*

## <span data-ttu-id="d2a06-152">복구 요청과 함께 Surface device의 등록을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-152">Unenroll a Surface device from SEMM with a Recovery Request</span></span>

<span data-ttu-id="d2a06-153">일부 시나리오에서 Surface UEFI reset 패키지는 Surface device (예: Windows를 사용할 수 없게 되는 경우)를 등록 하는 데 사용할 수 없는 옵션이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-153">In some scenarios, a Surface UEFI reset package may not be a viable option to unenroll a Surface device from SEMM (for example, where Windows has become unusable).</span></span> <span data-ttu-id="d2a06-154">이러한 시나리오에서는 Surface UEFI 내에서 생성 된 복구 요청을 사용 하 여 디바이스의 등록을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-154">In these scenarios you can unenroll the device by using a Recovery Request generated from within Surface UEFI.</span></span> <span data-ttu-id="d2a06-155">Surface UEFI 암호가 없는 장치 에서도 복구 요청 프로세스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-155">The Recovery Request process can be initiated even on devices where you do not have the Surface UEFI password.</span></span>

<span data-ttu-id="d2a06-156">복구 요청 프로세스는 Surface device의 Surface UEFI에서 시작 되 고, 다른 컴퓨터에서 Microsoft Surface UEFI 구성자을 승인 하 고, Surface UEFI에 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-156">The Recovery Request process is initiated from Surface UEFI on the Surface device, approved with Microsoft Surface UEFI Configurator on another computer, and then completed in Surface UEFI.</span></span> <span data-ttu-id="d2a06-157">다시 설정 패키지와 마찬가지로, Microsoft Surface UEFI 구성자를 사용 하 여 복구 요청을 승인 하려면 Surface 디바이스를 등록 하는 데 사용 된 SEMM 인증서에 대 한 액세스 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-157">Like the reset package, approving a Recovery Request with Microsoft Surface UEFI Configurator requires access to the SEMM certificate that was used to enroll the Surface device.</span></span>

<span data-ttu-id="d2a06-158">복구 요청을 시작 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-158">To initiate a Recovery Request, follow these steps:</span></span>

1. <span data-ttu-id="d2a06-159">Unenrolled에서 Surface UEFI로 연결할 Surface 디바이스를 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-159">Boot the Surface device that is to be unenrolled from SEMM to Surface UEFI.</span></span>
2. <span data-ttu-id="d2a06-160">서피스 UEFI 비밀 번호를 입력 하 라는 메시지가 표시 되 면 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-160">Type the Surface UEFI password if you are prompted to do so.</span></span>
3. <span data-ttu-id="d2a06-161">그림 6에 표시 된 대로 **엔터프라이즈 관리** 페이지를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-161">Click the **Enterprise management** page, as shown in Figure 6.</span></span>

   ![엔터프라이즈 관리 페이지](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *<span data-ttu-id="d2a06-163">그림 6.</span><span class="sxs-lookup"><span data-stu-id="d2a06-163">Figure 6.</span></span> <span data-ttu-id="d2a06-164">엔터프라이즈 관리 페이지는 SEMM로 등록 된 디바이스의 Surface UEFI에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-164">The Enterprise management page is displayed in Surface UEFI on devices enrolled in SEMM</span></span>*

4. <span data-ttu-id="d2a06-165">**시작**을 클릭 하거나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-165">Click or press **Get Started**.</span></span>
5. <span data-ttu-id="d2a06-166">복구 요청 프로세스를 시작 하려면 **다음** 을 클릭 하거나을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-166">Click or press **Next** to begin the Recovery Request process.</span></span>
   >[!NOTE]
   ><span data-ttu-id="d2a06-167">복구 요청은 만든 후 두 시간에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-167">A Recovery Request expires two hours after it is created.</span></span> <span data-ttu-id="d2a06-168">복구 요청이 지금 완료 되지 않은 경우 복구 요청 프로세스를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-168">If a Recovery Request is not completed in this time, you will have to restart the Recovery Request process.</span></span>
6. <span data-ttu-id="d2a06-169">**Semm 키 재설정** 페이지 (그림 7에 표시 됨)에 표시 된 인증서 목록에서 **semm 인증서** 를 선택 하 고 다음을 클릭 하거나 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-169">Select **SEMM Certificate** from the list of certificates displayed on the **Choose a SEMM reset key** page (shown in Figure 7), and then click or press **Next**.</span></span>

   ![복구 요청에 대해 SEMM 인증서 선택](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *<span data-ttu-id="d2a06-171">그림 7.</span><span class="sxs-lookup"><span data-stu-id="d2a06-171">Figure 7.</span></span> <span data-ttu-id="d2a06-172">복구 요청에 대해 SEMM 인증서 선택 (재설정 요청)</span><span class="sxs-lookup"><span data-stu-id="d2a06-172">Choose SEMM Certificate for your Recovery Request (Reset Request)</span></span>*

7. <span data-ttu-id="d2a06-173">(으)로 **설정 된 확인 코드 입력** 페이지에서 **QR 코드** 또는 **텍스트** 단추를 클릭 하 여 복구 요청 (다시 설정 요청)을 그림 8과 같이 표시 하거나, **usb** 단추로 복구 요청 (재설정 요청)을 Usb 드라이브에 파일로 저장할 수 있습니다 (그림 9).</span><span class="sxs-lookup"><span data-stu-id="d2a06-173">On the **Enter SEMM reset verification code** page you can click the **QR Code** or **Text** buttons to display your Recovery Request (Reset Request) as shown in Figure 8, or the **USB** button to save your Recovery Request (Reset Request) as a file to a USB drive, as shown in Figure 9.</span></span>

   ![QR 코드로 표시 된 복구 요청](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *<span data-ttu-id="d2a06-175">그림 8.</span><span class="sxs-lookup"><span data-stu-id="d2a06-175">Figure 8.</span></span> <span data-ttu-id="d2a06-176">QR 코드로 표시 되는 복구 요청 (재설정 요청)</span><span class="sxs-lookup"><span data-stu-id="d2a06-176">A Recovery Request (Reset Request) displayed as a QR Code</span></span>*

   ![USB 드라이브에 복구 요청 저장](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *<span data-ttu-id="d2a06-178">그림 9.</span><span class="sxs-lookup"><span data-stu-id="d2a06-178">Figure 9.</span></span> <span data-ttu-id="d2a06-179">복구 요청 (재설정 요청)을 USB 드라이브에 저장</span><span class="sxs-lookup"><span data-stu-id="d2a06-179">Save a Recovery Request (Reset Request) to a USB drive</span></span>*

   * <span data-ttu-id="d2a06-180">QR 코드 복구 요청 (재설정 요청)을 사용 하려면 모바일 장치에서 QR 읽기 프로그램을 사용 하 여 코드를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-180">To use a QR Code Recovery Request (Reset Request), use a QR reader app on a mobile device to read the code.</span></span> <span data-ttu-id="d2a06-181">QR 리더 앱은 QR 코드를 영숫자 문자열로 번역 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-181">The QR reader app will translate the QR code into an alphanumeric string.</span></span> <span data-ttu-id="d2a06-182">그런 다음 Microsoft Surface UEFI Configurator를 사용 하 여 재설정 확인 코드를 생성 하는 관리자에 게 해당 문자열을 전자 메일로 보내거나 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-182">You can then email or message that string to the administrator that will produce the reset verification code with Microsoft Surface UEFI Configurator.</span></span>
   * <span data-ttu-id="d2a06-183">USB 드라이브에 파일로 저장 된 복구 요청 (재설정 요청)을 사용 하려면 USB 드라이브를 사용 하 여 Microsoft Surface UEFI Configurator를 사용 하 여 초기화 확인 코드를 생성 하는 컴퓨터로 파일을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-183">To use a Recovery Request (Reset Request) saved to a USB drive as a file, use the USB drive to transfer the file to the computer where Microsoft Surface UEFI Configurator will be used to produce the Reset Verification Code.</span></span> <span data-ttu-id="d2a06-184">또한 다른 장치의 USB 드라이브에서 파일을 복사 하 여 네트워크를 통해 전자 메일로 보내거나 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-184">The file can also be copied from the USB drive on another device to be emailed or transferred over the network.</span></span>
   * <span data-ttu-id="d2a06-185">복구 요청 (다시 설정 요청)을 텍스트로 사용 하려면 Microsoft Surface UEFI 구성자에 직접 텍스트를 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-185">To use the Recovery Request (Reset Request) as text, simply type the text directly into Microsoft Surface UEFI Configurator.</span></span>

8. <span data-ttu-id="d2a06-186">다른 컴퓨터의 시작 메뉴에서 Microsoft Surface UEFI 구성자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-186">Open Microsoft Surface UEFI Configurator from the Start menu on another computer.</span></span>
    >[!NOTE]
    ><span data-ttu-id="d2a06-187">Microsoft Surface UEFI 구성자은 SEMM 인증서의 인증서 체인을 인증할 수 있는 환경에서 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-187">Microsoft Surface UEFI Configurator must run in an environment that is able to authenticate the certificate chain for the SEMM certificate.</span></span>
9. <span data-ttu-id="d2a06-188">**시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-188">Click **Start**.</span></span>
10. <span data-ttu-id="d2a06-189">그림 10에 나와 있는 것 처럼 **복구 요청**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-189">Click **Recovery Request**, as shown in Figure 10.</span></span>

    ![프로세스를 시작 하 여 복구 요청 승인](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *<span data-ttu-id="d2a06-191">그림 10.</span><span class="sxs-lookup"><span data-stu-id="d2a06-191">Figure 10.</span></span> <span data-ttu-id="d2a06-192">복구 요청을 클릭 하 여 복구 요청 승인 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="d2a06-192">Click Recovery Request to begin the process to approve a Recovery Request</span></span>*

11. <span data-ttu-id="d2a06-193">**인증서 보호** 를 클릭 하 여 semm 인증서로 복구 요청을 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-193">Click **Certificate Protection** to authenticate the Recovery Request with the SEMM certificate.</span></span>
12. <span data-ttu-id="d2a06-194">SEMM 인증서 파일을 찾아 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-194">Browse to and select your SEMM certificate file, and then click **OK**.</span></span>
13. <span data-ttu-id="d2a06-195">그림 11과 같이 인증서 암호를 입력 하 라는 메시지가 나타나면 인증서 파일에 대 한 암호를 입력 하 고 확인 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-195">When you are prompted to enter the certificate password as shown in Figure 11, type and confirm the password for the certificate file, and then click **OK**.</span></span>

    ![SEMM 인증서 비밀 번호 입력](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *<span data-ttu-id="d2a06-197">그림 11.</span><span class="sxs-lookup"><span data-stu-id="d2a06-197">Figure 11.</span></span> <span data-ttu-id="d2a06-198">SEMM 인증서의 비밀 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-198">Type the password for the SEMM certificate</span></span>*

14. <span data-ttu-id="d2a06-199">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-199">Click **Next**.</span></span>
15. <span data-ttu-id="d2a06-200">복구 요청 (다시 설정 요청)을 입력 한 다음 **생성** 을 클릭 하 여 재설정 된 확인 코드를 만듭니다 (그림 12).</span><span class="sxs-lookup"><span data-stu-id="d2a06-200">Enter the Recovery Request (Reset Request), and then click **Generate** to create a reset verification code (as shown in Figure 12).</span></span>

    ![복구 요청 입력](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *<span data-ttu-id="d2a06-202">그림 12.</span><span class="sxs-lookup"><span data-stu-id="d2a06-202">Figure 12.</span></span> <span data-ttu-id="d2a06-203">복구 요청 (다시 설정 요청) 입력</span><span class="sxs-lookup"><span data-stu-id="d2a06-203">Enter the Recovery Request (Reset Request)</span></span>*

    * <span data-ttu-id="d2a06-204">복구 요청 (재설정 요청)을 재설정 되는 Surface 디바이스의 텍스트로 표시 한 경우 키보드를 사용 하 여 제공 된 필드에 복구 요청 (재설정 요청)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-204">If you displayed the Recovery Request (Reset Request) as text on the Surface device being reset, use the keyboard to type the Recovery Request (Reset Request)  in the provided field.</span></span>
    * <span data-ttu-id="d2a06-205">복구 요청 (재설정 요청)을 QR 코드로 표시 한 후 메시지 또는 전자 메일 응용 프로그램을 사용 하 여 Microsoft Surface UEFI Configurator를 사용 하 여 컴퓨터에 코드를 보내는 경우 제공 된 필드에 해당 코드를 복사 하 여 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-205">If you displayed the Recovery Request (Reset Request) as a QR Code and then used a messaging or email application to send the code to the computer with Microsoft Surface UEFI Configurator, copy and paste the code into the provided field.</span></span>
    * <span data-ttu-id="d2a06-206">복구 요청 (재설정 요청)을 USB 드라이브에 파일로 저장 한 경우, **가져오기** 단추를 클릭 하 고 복구 요청 (재설정 요청) 파일을 찾아 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-206">If you saved the Recovery Request (Reset Request) as a file to a USB drive, click the **Import** button, browse to and select the Recovery Request (Reset Request) file, and then click **OK**.</span></span>

16. <span data-ttu-id="d2a06-207">다시 설정 확인 코드는 그림 13과 같이 Microsoft Surface UEFI 구성자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-207">The reset verification code is displayed in Microsoft Surface UEFI Configurator, as shown in Figure 13.</span></span>

    ![다시 설정 확인 코드 표시](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *<span data-ttu-id="d2a06-209">그림 13.</span><span class="sxs-lookup"><span data-stu-id="d2a06-209">Figure 13.</span></span> <span data-ttu-id="d2a06-210">Microsoft Surface UEFI 구성자에 표시 되는 다시 설정 확인 코드</span><span class="sxs-lookup"><span data-stu-id="d2a06-210">The reset verification code displayed in Microsoft Surface UEFI Configurator</span></span>*

    * <span data-ttu-id="d2a06-211">**공유** 단추를 클릭 하 여 다시 설정 확인 코드를 전자 메일로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-211">Click the **Share** button to send the reset verification code by email.</span></span>

17. <span data-ttu-id="d2a06-212">Surface 디바이스의 제공 된 필드에 다시 설정 된 확인 코드 (그림 8)를 입력 한 다음 **확인** 을 클릭 하거나 눌러 장치를 초기화 하 고 디바이스를 semm에서 등록 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-212">Enter the reset verification code in the provided field on the Surface device (shown in Figure 8), and then click or press **Verify** to reset the device and unenroll the device from SEMM.</span></span>
18. <span data-ttu-id="d2a06-213">그림 14와 같이 semm **reset 성공** 페이지에서 **지금 다시 시작** 을 클릭 하거나 눌러 unenrollment를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-213">Click or press **Restart now** on the **SEMM reset successful** page to complete the unenrollment from SEMM, as shown in Figure 14.</span></span>

    ![SEMM에서 성공한 unenrollment 표시 하는 예제](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *<span data-ttu-id="d2a06-215">그림 14.</span><span class="sxs-lookup"><span data-stu-id="d2a06-215">Figure 14.</span></span> <span data-ttu-id="d2a06-216">Unenrollment에서 성공한 시작</span><span class="sxs-lookup"><span data-stu-id="d2a06-216">Successful unenrollment from SEMM</span></span>*

19. <span data-ttu-id="d2a06-217">Microsoft Surface UEFI 구성자에서 **End** 를 클릭 하 여 복구 요청 (초기화 요청) 프로세스를 완료 하 고 MICROSOFT Surface UEFI 구성자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a06-217">Click **End** in Microsoft Surface UEFI Configurator to complete the Recovery Request (Reset Request) process and close Microsoft Surface UEFI Configurator.</span></span>


