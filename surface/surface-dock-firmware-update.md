---
title: Microsoft Surface Dock 펌웨어 업데이트-IT 관리자를 위한 기술 정보
description: 이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용 하 여 Surface Dock 펌웨어를 업데이트 하는 방법을 설명 합니다. Surface 디바이스에 설치 되 면 surface 디바이스에 연결 된 모든 표면 도크가 업데이트 됩니다.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 8/07/2020
ms.openlocfilehash: 9069903421d6e621dfbc31cd1cfaffb045fa9f19
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114556"
---
# <span data-ttu-id="0452e-104">Microsoft Surface Dock 펌웨어 업데이트: IT 관리자를 위한 기술 정보</span><span class="sxs-lookup"><span data-stu-id="0452e-104">Microsoft Surface Dock Firmware Update: Technical information for IT admins</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0452e-105">이 문서에는 IT 관리자를 위한 기술 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="0452e-106">가정용 사용자 인 경우 Microsoft 지원 사이트에서 [Surface Dock 펌웨어를 업데이트 하는 방법을](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)참조 하세요   .</span><span class="sxs-lookup"><span data-stu-id="0452e-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="0452e-107">지원 사이트의 지침은 아래의 일반적인 설치 단계와 동일 하지만이 문서에는 네트워크의 여러 장치에 대 한 업데이트 모니터링, 확인 및 배포에 대 한 추가 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="0452e-108">이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용 하 여 원래 Surface Dock 1에서 펌웨어를 업데이트 하는 방법을 설명 하 고 Surface Dock 2에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-108">This article explains how to use Microsoft Surface Dock Firmware Update to update firmware on the original Surface Dock 1 and does not apply to Surface Dock 2.</span></span> <span data-ttu-id="0452e-109">Surface 디바이스에 설치 되 면 surface 디바이스에 연결 된 모든 표면 도크가 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="0452e-110">이 도구는 이전 Microsoft Surface Dock 업데이트 도구를 대체 합니다. 이전에는이를 위해 Surface 도구의 일부로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="0452e-111">앞의 도구에는 Surface_Dock_Updater_vx.xx.xxx.x.msi 이름이 지정 되어 있으며 (여기서 x는 버전 번호를 나타냄) 더 이상 다운로드할 수 없으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="0452e-112">Surface Dock 펌웨어 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="0452e-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="0452e-113">이 섹션에서는 펌웨어 업데이트를 수동으로 설치 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="0452e-114">Microsoft는 Surface Dock 펌웨어 업데이트의 새 버전을 정기적으로 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="0452e-115">MSI 파일이 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="0452e-116">MSI를 Surface 디바이스에 배포한 경우 펌웨어의 새 버전이 릴리스되면 새 버전을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="0452e-117">[Microsoft Surface Dock 펌웨어 업데이트](https://www.microsoft.com/download/details.aspx?id=46703)를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="0452e-118">업데이트에는 Windows 10 버전 1803 이상을 실행 하는 Surface 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="0452e-119">MSI 파일을 설치 하면 Surface를 다시 시작 하 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="0452e-120">그러나 업데이트를 수행 하는 데는 다시 시작이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="0452e-121">Surface Dock에서 Surface device의 연결을 끊고 ~ 5 초간 기다린 다음 다시 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-121">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="0452e-122">Surface Dock 펌웨어 업데이트는 백그라운드에서 자동으로 도크를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="0452e-123">이 프로세스는 완료 하는 데 몇 분 정도 소요 될 수 있으며 중단 된 경우에도 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="0452e-124">Surface Dock 펌웨어 업데이트 모니터링</span><span class="sxs-lookup"><span data-stu-id="0452e-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="0452e-125">이 섹션은 선택 사항이 며 펌웨어 업데이트 설치를 모니터링 하는 방법에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="0452e-126">업데이트를 모니터링 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-126">To monitor the update:</span></span>

1. <span data-ttu-id="0452e-127">이벤트 뷰어를 열고 **Windows 로그 > 응용 프로그램**으로 이동한 다음 오른쪽 창의 **작업** 에서 **현재 로그 필터링**을 클릭 하 고 **이벤트 원본**옆에 **SurfaceDockFwUpdate** 를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="0452e-128">관리자 권한 명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="0452e-129">이 문서의 [다음 섹션](#install-the-surface-dock-firmware-update) 에 설명 된 대로 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="0452e-130">다음 텍스트를 포함 하는 이벤트 2007에 업데이트 **완료 됨 펌웨어가 업데이트 되었습니다. hr = 0 Driverementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="0452e-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="0452e-131">업데이트가 실패 하면 이벤트 ID 2007이 **정보가**아닌 **오류** 이벤트로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="0452e-132">또한 Windows 레지스트리에 보고 된 버전은 최신 상태가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="0452e-133">업데이트가 완료 되 면 최신 버전의 도구에 해당 하는 업데이트 된 DWORD 값이 Windows 레지스트리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="0452e-134">자세한 내용은이 문서의 [버전 참조](#versions-reference) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0452e-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="0452e-135">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-135">For example:</span></span>
    - <span data-ttu-id="0452e-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="0452e-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="0452e-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="0452e-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="0452e-138">이벤트 텍스트에서 "SurfaceDockFwUpdate에서 이벤트 ID xxxx에 대 한 설명을 찾을 수 없음"이 표시 되는 경우이는 예상 되는 것으로, 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="0452e-139">또한이 문서의 다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0452e-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="0452e-140">펌웨어 업데이트가 완료 되었는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="0452e-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="0452e-141">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="0452e-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="0452e-142">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="0452e-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="0452e-143">버전 참조</span><span class="sxs-lookup"><span data-stu-id="0452e-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="0452e-144">네트워크 배포</span><span class="sxs-lookup"><span data-stu-id="0452e-144">Network deployment</span></span>

<span data-ttu-id="0452e-145">Windows Installer 명령 (Msiexec.exe)을 사용 하 여 네트워크를 통해 여러 장치에 Surface Dock 펌웨어 업데이트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="0452e-146">Microsoft 끝점 구성 관리자 또는 기타 배포 도구를 사용 하는 경우 설치가 자동으로 수행 되도록 다음 구문을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="0452e-147">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="0452e-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="0452e-148">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="0452e-149">로그 파일은 기본적으로 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-149">A log file is not created by default.</span></span> <span data-ttu-id="0452e-150">로그 파일을 만들기 위해서는 "/l*v [path]"를 추가 해야 합니다. 예: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI "</span><span class="sxs-lookup"><span data-stu-id="0452e-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="0452e-151">자세한 내용은 명령줄 [옵션](https://docs.microsoft.com/windows/win32/msi/command-line-options) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0452e-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0452e-152">다른 방법을 사용 하 여 화면 도크를 업데이트 된 상태로 유지 하려는 경우에는 [Surface Dock 업데이트](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 에 대 한 자세한 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0452e-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="0452e-153">Intune 배포</span><span class="sxs-lookup"><span data-stu-id="0452e-153">Intune deployment</span></span>

<span data-ttu-id="0452e-154">Intune을 사용 하 여 Surface Dock 펌웨어 업데이트를 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="0452e-155">먼저, 다음 설명서의 설명에 따라 MSI 파일을 intunewin 형식으로 변환 해야 합니다. [Intune 독립 실행형-Win32 앱 관리](https://docs.microsoft.com/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="0452e-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="0452e-156">다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-156">Use the following command:</span></span>
  - **<span data-ttu-id="0452e-157">msiexec/i \<path to msi file\> /quiet/q</span><span class="sxs-lookup"><span data-stu-id="0452e-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="0452e-158">펌웨어 업데이트가 완료 되었는지 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="0452e-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="0452e-159">서피스 도크 펌웨어는 다음 두 가지 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="0452e-160">**Component10:** 마이크로 장치 컨트롤러 단위 (MCU) 펌웨어</span><span class="sxs-lookup"><span data-stu-id="0452e-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="0452e-161">**Component20:** 디스플레이 포트 (DP) 펌웨어.</span><span class="sxs-lookup"><span data-stu-id="0452e-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="0452e-162">Surface Dock 펌웨어 업데이트가 성공적으로 완료 되 면 이러한 펌웨어 구성 요소에 대 한 새 레지스트리 키 값이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="0452e-163">업데이트를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-163">To verify updates:</span></span>**

1. <span data-ttu-id="0452e-164">Regedit를 열고 다음 레지스트리 경로로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="0452e-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="0452e-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="0452e-166">현재 디바이스에 있는 펌웨어를 참조 하는 **Component10CurrentFwVersion 및 Component20CurrentFwVersion**레지스트리 키를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Surface Dock 펌웨어 업데이트 설치 프로세스](images/regeditDock.png)

3. <span data-ttu-id="0452e-168">새 레지스트리 키 값이이 문서 뒷부분의 버전 참조에 나열 된 업데이트 된 레지스트리 키 값과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="0452e-169">값이 일치 하는 경우 펌웨어가 성공적으로 업데이트 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="0452e-170">확인할 수 없는 경우 다음 섹션에서 이벤트 로깅 및 문제 해결 팁을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="0452e-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="0452e-171">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="0452e-171">Event logging</span></span>

**<span data-ttu-id="0452e-172">표 1.</span><span class="sxs-lookup"><span data-stu-id="0452e-172">Table 1.</span></span> <span data-ttu-id="0452e-173">Surface Dock 펌웨어 업데이트에 대 한 로그 파일</span><span class="sxs-lookup"><span data-stu-id="0452e-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="0452e-174">Log</span><span class="sxs-lookup"><span data-stu-id="0452e-174">Log</span></span>                              | <span data-ttu-id="0452e-175">위치</span><span class="sxs-lookup"><span data-stu-id="0452e-175">Location</span></span>                               | <span data-ttu-id="0452e-176">참고</span><span class="sxs-lookup"><span data-stu-id="0452e-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0452e-177">Surface Dock 펌웨어 업데이트 로그</span><span class="sxs-lookup"><span data-stu-id="0452e-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="0452e-178">경로를 지정 해야 합니다 (참고 참조).</span><span class="sxs-lookup"><span data-stu-id="0452e-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="0452e-179">이전 버전의이 도구는 응용 프로그램 및 서비스 Logs\Microsoft Surface Dock 업데이트에 이벤트를 기록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="0452e-180">Windows 장치 설치 로그</span><span class="sxs-lookup"><span data-stu-id="0452e-180">Windows Device Install log</span></span>       | <span data-ttu-id="0452e-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="0452e-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="0452e-182">장치 설치 로그 사용에 대 한 자세한 내용은 [SetupAPI 로깅](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0452e-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="0452e-183">표 2.</span><span class="sxs-lookup"><span data-stu-id="0452e-183">Table 2.</span></span> <span data-ttu-id="0452e-184">Surface Dock 펌웨어 업데이트에 대 한 이벤트 로그 Id</span><span class="sxs-lookup"><span data-stu-id="0452e-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="0452e-185">이벤트는 응용 프로그램 이벤트 로그에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="0452e-186">참고: 이전 버전의이 도구는 응용 프로그램 및 서비스 Logs\Microsoft Surface Dock 업데이트에 이벤트를 기록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="0452e-187">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="0452e-187">Event ID</span></span> | <span data-ttu-id="0452e-188">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="0452e-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="0452e-189">2001</span><span class="sxs-lookup"><span data-stu-id="0452e-189">2001</span></span>     | <span data-ttu-id="0452e-190">Dock 펌웨어 업데이트가 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="0452e-191">2002</span><span class="sxs-lookup"><span data-stu-id="0452e-191">2002</span></span>     | <span data-ttu-id="0452e-192">Dock 펌웨어 업데이트는 연결이 최신으로 알려져 있으므로 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="0452e-193">2003</span><span class="sxs-lookup"><span data-stu-id="0452e-193">2003</span></span>     | <span data-ttu-id="0452e-194">Dock 펌웨어 업데이트에서 펌웨어 버전을 가져오지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="0452e-195">2004</span><span class="sxs-lookup"><span data-stu-id="0452e-195">2004</span></span>     | <span data-ttu-id="0452e-196">펌웨어 버전을 쿼리 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="0452e-197">2005</span><span class="sxs-lookup"><span data-stu-id="0452e-197">2005</span></span>     | <span data-ttu-id="0452e-198">도킹 펌웨어에서 업데이트를 시작 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="0452e-199">2006</span><span class="sxs-lookup"><span data-stu-id="0452e-199">2006</span></span>     | <span data-ttu-id="0452e-200">제공/페이로드 쌍을 보내지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="0452e-201">2007</span><span class="sxs-lookup"><span data-stu-id="0452e-201">2007</span></span>     | <span data-ttu-id="0452e-202">펌웨어 업데이트가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="0452e-203">2008</span><span class="sxs-lookup"><span data-stu-id="0452e-203">2008</span></span>     | <span data-ttu-id="0452e-204">원격 분석을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="0452e-205">2011</span><span class="sxs-lookup"><span data-stu-id="0452e-205">2011</span></span>     | <span data-ttu-id="0452e-206">Dock 원격 분석 종료.</span><span class="sxs-lookup"><span data-stu-id="0452e-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="0452e-207">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="0452e-207">Troubleshooting tips</span></span>

- <span data-ttu-id="0452e-208">화면 도크를 재설정 하기 위해 AC 전원에서 Surface dock의 전원을 완전히 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="0452e-209">Surface Dock을 제외한 모든 주변 장치를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="0452e-210">현재 Surface Dock 펌웨어 업데이트를 제거 하 고 최신 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="0452e-211">Surface Dock의 연결이 해제 되었는지 확인 한 다음 도크의 이더넷 포트에서 LED를 통해 모니터 한 대로 업데이트가 완료 될 때까지 충분히 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="0452e-212">전원에서 Surface Dock을 분리 하기 전에 LED가 깜박임을 멈출 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="0452e-213">화면 도크를 다른 장치에 연결 하 여 도크를 업데이트할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="0452e-214">버전 참조</span><span class="sxs-lookup"><span data-stu-id="0452e-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="0452e-215">**Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (예: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 인 설치 파일은 기본적으로 C:\Program Files\SurfaceUpdate.에 설치 되 고 다음과 같은 이름 지정 형식으로 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="0452e-216">버전 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="0452e-216">Version 1.53.139.0</span></span>
*<span data-ttu-id="0452e-217">릴리스 날짜: 2020 년 8 월 4 일</span><span class="sxs-lookup"><span data-stu-id="0452e-217">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="0452e-218">이 버전의 Surface Dock 펌웨어 업데이트에는 다음에 대 한 버그 수정 및 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-218">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="0452e-219">Surface Pro X를 사용 하 여 Surface Dock 1을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-219">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="0452e-220">Surface Pro X를 실행 하는 경우을 다운로드 합니다. ARM64 빌드.</span><span class="sxs-lookup"><span data-stu-id="0452e-220">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="0452e-221">다른 모든 장치에는 AMD64 빌드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-221">For all other devices, use the AMD64 build.</span></span> 
 


### <span data-ttu-id="0452e-222">버전 1.42.139</span><span class="sxs-lookup"><span data-stu-id="0452e-222">Version 1.42.139</span></span> 
*<span data-ttu-id="0452e-223">릴리스 날짜: 18 2019 년 9 월</span><span class="sxs-lookup"><span data-stu-id="0452e-223">Release Date: September 18 2019</span></span>*

<span data-ttu-id="0452e-224">이 버전은 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI에 포함 되어 있으며, 백그라운드에서 펌웨어를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-224">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="0452e-225">업데이트 된 레지스트리 키 값:</span><span class="sxs-lookup"><span data-stu-id="0452e-225">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="0452e-226">Component10CurrentFwVersion가 **4ac3970**으로 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="0452e-227">Component20CurrentFwVersion가 **4a1d570**로 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="0452e-228">Surface Pro 7 및 Surface 노트북 3에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-228">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="0452e-229">레거시 버전</span><span class="sxs-lookup"><span data-stu-id="0452e-229">Legacy versions</span></span>

### <span data-ttu-id="0452e-230">버전 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="0452e-230">Version 2.23.139.0</span></span>
*<span data-ttu-id="0452e-231">릴리스 날짜: 2018 년 10 월 11 일</span><span class="sxs-lookup"><span data-stu-id="0452e-231">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="0452e-232">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-232">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="0452e-233">Surface Pro 6에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="0452e-233">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="0452e-234">Surface 노트북 2에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="0452e-234">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="0452e-235">버전 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="0452e-235">Version 2.22.139.0</span></span>
*<span data-ttu-id="0452e-236">릴리스 날짜: 26 7 월 2018</span><span class="sxs-lookup"><span data-stu-id="0452e-236">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="0452e-237">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-237">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="0452e-238">업데이트 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="0452e-238">Increase update reliability</span></span>
- <span data-ttu-id="0452e-239">Surface Go에 대 한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="0452e-239">Add support for Surface Go</span></span>

### <span data-ttu-id="0452e-240">버전 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="0452e-240">Version 2.12.136.0</span></span>
*<span data-ttu-id="0452e-241">릴리스 날짜: 2018년 1월 29일</span><span class="sxs-lookup"><span data-stu-id="0452e-241">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="0452e-242">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-242">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="0452e-243">Surface Dock 메인 칩 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-243">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="0452e-244">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-244">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="0452e-245">Surface Book 또는 Surface Book 2와 함께 사용하는 경우 외부 디스플레이의 디스플레이 안정성이 개선</span><span class="sxs-lookup"><span data-stu-id="0452e-245">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="0452e-246">또한, 이 버전의 Surface Dock 업데이트 프로그램을 Surface Book 디바이스에 설치하면 다음이 함께 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-246">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="0452e-247">Surface Book 본체 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-247">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="0452e-248">Surface Book 디바이스를 대상으로 하는 개선 기능이 포함된 Surface Dock 펌웨어 업데이트에 대한 지원이 추가</span><span class="sxs-lookup"><span data-stu-id="0452e-248">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="0452e-249">버전 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="0452e-249">Version 2.9.136.0</span></span>
*<span data-ttu-id="0452e-250">릴리스 날짜: 2017년 11월 3일</span><span class="sxs-lookup"><span data-stu-id="0452e-250">Release date: November 3, 2017</span></span>*

<span data-ttu-id="0452e-251">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-251">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="0452e-252">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-252">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="0452e-253">패시브 디스플레이 포트 어댑터의 오디오 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-253">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="0452e-254">버전 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="0452e-254">Version 2.1.15.0</span></span>
*<span data-ttu-id="0452e-255">출시 날짜: 2017년 6월 19일</span><span class="sxs-lookup"><span data-stu-id="0452e-255">Release date: June 19, 2017</span></span>*

<span data-ttu-id="0452e-256">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-256">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="0452e-257">Surface 노트북</span><span class="sxs-lookup"><span data-stu-id="0452e-257">Surface Laptop</span></span>
* <span data-ttu-id="0452e-258">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="0452e-258">Surface Pro</span></span>

### <span data-ttu-id="0452e-259">버전 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="0452e-259">Version 2.1.6.0</span></span>
*<span data-ttu-id="0452e-260">릴리스 날짜: 2017년 4월 7일</span><span class="sxs-lookup"><span data-stu-id="0452e-260">Release date: April 7, 2017</span></span>*

<span data-ttu-id="0452e-261">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-261">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="0452e-262">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-262">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="0452e-263">Windows 10 필요</span><span class="sxs-lookup"><span data-stu-id="0452e-263">Requires Windows 10</span></span>

### <span data-ttu-id="0452e-264">버전 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="0452e-264">Version 2.0.22.0</span></span>
*<span data-ttu-id="0452e-265">릴리스 날짜: 2016년 10월 21일</span><span class="sxs-lookup"><span data-stu-id="0452e-265">Release date: October 21, 2016</span></span>*

<span data-ttu-id="0452e-266">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-266">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="0452e-267">Surface Dock USB 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-267">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="0452e-268">이더넷, 오디오 및 USB 포트의 안전성 개선</span><span class="sxs-lookup"><span data-stu-id="0452e-268">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="0452e-269">버전 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="0452e-269">Version 1.0.8.0</span></span>
*<span data-ttu-id="0452e-270">릴리스 날짜: 2016년 4월 26일</span><span class="sxs-lookup"><span data-stu-id="0452e-270">Release date: April 26, 2016</span></span>*

<span data-ttu-id="0452e-271">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0452e-271">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="0452e-272">Surface Dock Main Chipset 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-272">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="0452e-273">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="0452e-273">Update for Surface Dock DisplayPort firmware</span></span>

