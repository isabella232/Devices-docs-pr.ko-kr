---
title: Surface Hub 2S 초기화 및 복구
description: Surface Hub 2S를 복구 및 초기화하는 방법을 알아보십시오.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304811"
---
# <span data-ttu-id="ccb41-104">Surface Hub 2S 초기화 및 복구</span><span class="sxs-lookup"><span data-stu-id="ccb41-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="ccb41-105">Surface Hub 2S에 문제가 발생하면 장치를 공장 설정으로 초기화하거나 USB 드라이브를 사용하여 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="ccb41-106">시작하려면 관리자 자격 증명으로 Surface Hub 2S에 \*\*\*\* 로그인하고 \*\*\*\* 설정 앱을 열고 보안 업데이트 & 선택한 다음 **복구를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccb41-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="ccb41-107">장치 초기화</span><span class="sxs-lookup"><span data-stu-id="ccb41-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ccb41-108">디바이스를 초기화하기 전에 BitLocker 키를 사용할 수 있도록 합니다. 나중에 요청이 표시되기 전에 이 키를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="ccb41-109">자세한 내용은 [BitLocker 키 저장을 참조합니다.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="ccb41-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="ccb41-110">디바이스를 초기화하려면 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccb41-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="ccb41-111">이 장치 **초기화 준비 완료 창이** 나타나면 재설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccb41-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="ccb41-112">허브가 복구 파티션에 다시 시작하면 BitLocker 키를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="ccb41-113">이 프롬프트를 건너뛰면 재설정이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="ccb41-114">BitLocker 키를 입력하면 허브가 복구 파티션에서 운영 체제를 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="ccb41-115">완료하는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="ccb41-116">장치를 다시 구성하려면 첫 번째 설치 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="ccb41-117">Microsoft Intune 또는 다른 모바일 장치 관리 솔루션을 사용하여 장치를 관리하는 경우 이전 레코드를 사용 중지하고 삭제한 다음 새 장치를 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="ccb41-118">자세한 내용은 장치 지우기, 사용 중지 또는 수동으로 장치 초기화를 사용하여 장치 [제거를 참조하세요.](https://docs.microsoft.com/intune/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="ccb41-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Surface Hub 2S의 초기화 및 복구*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="ccb41-120">그림 1.</span><span class="sxs-lookup"><span data-stu-id="ccb41-120">Figure 1.</span></span> <span data-ttu-id="ccb41-121">Surface Hub 2S 초기화 및 복구</span><span class="sxs-lookup"><span data-stu-id="ccb41-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="ccb41-122">USB 복구 드라이브를 사용하여 Surface Hub 2S 복구</span><span class="sxs-lookup"><span data-stu-id="ccb41-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="ccb41-123">Surface Hub 2S의 새로운 기능을 통해 복구 이미지를 사용하여 디바이스를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="ccb41-124">USB 드라이브에서 복구</span><span class="sxs-lookup"><span data-stu-id="ccb41-124">Recovery from a USB drive</span></span>

<span data-ttu-id="ccb41-125">Surface Hub 2S를 사용하여 복구 이미지를 사용하여 디바이스를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="ccb41-126">이렇게 하면 BitLocker 키를 분실하거나 설정 앱에 대한 관리자 자격 증명이 더 이상 없는 경우 장치를 공장 설정에 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="ccb41-127">FAT32로 포맷된 8GB 또는 16GB의 저장소가 있는 USB 3.0 드라이브를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="ccb41-128">별도의 PC에서 [Surface 복구](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 웹 사이트에서 .zip 파일 복구 이미지를 다운로드한 다음 다음 지침으로 돌아오세요.</span><span class="sxs-lookup"><span data-stu-id="ccb41-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="ccb41-129">다운로드한 파일의 파일을 USB 드라이브의 루트에 언스파이프합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-129">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="ccb41-130">Usb 드라이브를 Surface Hub 2S의 USB-C 또는 USB-A 포트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-130">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="ccb41-131">디바이스를 끄는 경우:</span><span class="sxs-lookup"><span data-stu-id="ccb41-131">Turn off the device:</span></span>

   1. <span data-ttu-id="ccb41-132">볼륨 아래로 단추를 누를 때 전원 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-132">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="ccb41-133">Windows 로고가 표시될 때까지 두 단추를 계속 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-133">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="ccb41-134">전원 단추를 해제하지만 설치 UI가 시작될 때까지 볼륨 아래로 단추를 계속 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-134">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*볼륨 감소 및 전원 단추를 사용하여 복구 시작*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="ccb41-136">그림 2.</span><span class="sxs-lookup"><span data-stu-id="ccb41-136">Figure 2.</span></span> <span data-ttu-id="ccb41-137">볼륨 및 전원 단추</span><span class="sxs-lookup"><span data-stu-id="ccb41-137">Volume and Power buttons</span></span>*

1. <span data-ttu-id="ccb41-138">언어 선택 화면에서 Surface Hub 2S의 표시 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-138">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="ccb41-139">Select **Recover from a drive** and Fully clean the **drive,** and then select **Recover**.</span><span class="sxs-lookup"><span data-stu-id="ccb41-139">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="ccb41-140">BitLocker 키를 입력하라는 메시지가 표시될 경우 이 드라이브 **건너뛰기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ccb41-140">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="ccb41-141">Surface Hub 2S는 여러 번 다시 시작하며 복구 프로세스를 완료하는 데 약 30분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-141">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="ccb41-142">처음 설치 화면이 나타나면 USB 드라이브를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb41-142">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="ccb41-143">고객 지원</span><span class="sxs-lookup"><span data-stu-id="ccb41-143">Contact Support</span></span>

<span data-ttu-id="ccb41-144">질문이나 도움이 필요한 경우 지원 요청을 [만들 수 있습니다.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="ccb41-144">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
