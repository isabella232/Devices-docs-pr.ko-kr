---
title: Microsoft Surface Dock 1 펌웨어 업데이트
description: 이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용하여 원래 Surface Dock 1에 펌웨어를 설치하고 관리하는 방법을 설명합니다. Surface 디바이스에 설치하면 Surface 디바이스에 연결된 Surface Dock 1 디바이스가 업데이트됩니다.
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319212"
---
# <span data-ttu-id="a7e6d-104">Microsoft Surface Dock 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e6d-105">이 문서에는 IT 관리자를 위한 기술 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="a7e6d-106">가정적 사용자인 경우 Microsoft 지원 사이트에서 [Surface Dock 펌웨어를](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)업데이트하는   방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="a7e6d-107">지원 사이트의 지침은 아래 일반 설치 단계와 동일하지만 이 문서에는 네트워크의 여러 장치에 업데이트를 모니터링, 확인 및 배포하기 위한 추가 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="a7e6d-108">이 문서에서는 Microsoft Surface Dock 펌웨어 업데이트를 사용하여 원래 Surface Dock 1에 펌웨어를 설치하고 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="a7e6d-109">Surface 디바이스에 설치하면 Surface 디바이스에 연결된 Surface Dock 1 디바이스가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="a7e6d-110">이 문서는 Windows 업데이트 또는 Microsoft Endpoint Configuration Manager 또는 기타 MSI 배포 도구를 사용하여 자동으로 업데이트를 받는 Surface Dock 2에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="a7e6d-111">자세한 내용은 Surface Dock의 새로운 내용을 [참조합니다.](surface-dock-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="a7e6d-112">이 도구는 이전에 IT용 Surface Tools의 일부로 다운로드할 수 있는 이전 Microsoft Surface Dock Updater 도구를 능가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="a7e6d-113">이전 도구의 이름이 Surface_Dock_Updater_vx.xx.xxx.x.msi(여기서 x는 버전 번호를 나타임)로 이름이 지정되어 있으며 더 이상 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="a7e6d-114">Surface Dock 펌웨어 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="a7e6d-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="a7e6d-115">이 섹션에서는 펌웨어 업데이트를 수동으로 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="a7e6d-116">Microsoft는 주기적으로 새로운 버전의 Surface Dock 펌웨어 업데이트를 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="a7e6d-117">MSI 파일이 자체 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="a7e6d-118">Surface 디바이스에 MSI를 배포한 경우 새 버전의 펌웨어가 릴리스된 경우 새 버전을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="a7e6d-119">[Microsoft Surface Dock 펌웨어 업데이트를 다운로드하여 설치합니다.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="a7e6d-120">업데이트에는 Windows 10 버전 1803 이상을 실행하는 Surface 디바이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="a7e6d-121">MSI 파일을 설치하면 Surface를 다시 시작하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="a7e6d-122">그러나 업데이트를 수행하는 데는 다시 시작할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="a7e6d-123">Surface Dock에서 Surface 디바이스를 분리하고 ~5초간 기다렸다가 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="a7e6d-124">Surface Dock 펌웨어 업데이트는 백그라운드에서 도킹을 자동으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="a7e6d-125">프로세스가 완료되는 데 몇 분 정도 걸릴 수 있으며 중단된 경우에도 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="a7e6d-126">Surface Dock 펌웨어 업데이트 모니터링</span><span class="sxs-lookup"><span data-stu-id="a7e6d-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="a7e6d-127">이 섹션은 선택 사항이며 펌웨어 업데이트 설치를 모니터링하는 방법에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="a7e6d-128">업데이트를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-128">To monitor the update:</span></span>

1. <span data-ttu-id="a7e6d-129">이벤트 뷰어를 열고 **Windows Logs > 응용**프로그램으로 이동한 다음 오른쪽 \*\*\*\* 창의 작업 아래에서 현재 로그 필터링을 \*\*\*\* 클릭하고 이벤트 원본 옆에 **SurfaceDockFwUpdate를** 입력한 후 **확인을**클릭합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a7e6d-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="a7e6d-130">상승된 명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="a7e6d-131">이 문서의 다음 섹션에 설명된 [바와 같이 업데이트를](#install-the-surface-dock-firmware-update) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="a7e6d-132">다음 텍스트가 있는 이벤트 2007은 성공적인 업데이트가 **완료되었습니다. hr=0 DriverTelementry EventCode = 2007.**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="a7e6d-133">업데이트가 성공하지 못하면 이벤트 ID 2007이 정보 대신 **오류** 이벤트로 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="a7e6d-134">또한 Windows 레지스트리에 보고된 버전은 최신 버전이 아니게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="a7e6d-135">업데이트가 완료되면 업데이트된 DWORD 값이 현재 버전의 도구에 해당하는 Windows 레지스트리에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="a7e6d-136">자세한 [내용은](#versions-reference) 이 문서의 버전 참조 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="a7e6d-137">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-137">For example:</span></span>

    - <span data-ttu-id="a7e6d-138">Component10CurrentFwVersion 0x04ac3970(78395760)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="a7e6d-139">Component20CurrentFwVersion 0x04915a70(76634736)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="a7e6d-140">이벤트 텍스트에서 "원본 SurfaceDockFwUpdate의 이벤트 ID xxxx에 대한 설명을 찾을 수 없습니다."가 표시될 경우 이 설명은 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="a7e6d-141">또한 이 문서의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="a7e6d-142">펌웨어 업데이트 완료를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="a7e6d-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="a7e6d-143">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="a7e6d-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="a7e6d-144">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="a7e6d-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="a7e6d-145">버전 참조</span><span class="sxs-lookup"><span data-stu-id="a7e6d-145">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="a7e6d-146">네트워크 배포</span><span class="sxs-lookup"><span data-stu-id="a7e6d-146">Network deployment</span></span>

<span data-ttu-id="a7e6d-147">Windows Installer 명령(Msiexec.exe)을 사용하여 네트워크에서 여러 디바이스에 Surface Dock 펌웨어 업데이트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="a7e6d-148">Microsoft Endpoint Configuration Manager 또는 기타 배포 도구를 사용할 때 다음 구문을 입력하여 설치가 자동으로 진행되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="a7e6d-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="a7e6d-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="a7e6d-150">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="a7e6d-151">로그 파일은 기본적으로 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-151">A log file is not created by default.</span></span> <span data-ttu-id="a7e6d-152">로그 파일을 만들하려면 "/l*v [path]"를 추가해야 합니다. 예: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span><span class="sxs-lookup"><span data-stu-id="a7e6d-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="a7e6d-153">자세한 내용은 명령줄 옵션 [설명서를 참조하십시오.](https://docs.microsoft.com/windows/win32/msi/command-line-options)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e6d-154">다른 방법을 사용하여 Surface Dock를 업데이트된 것으로 유지하려는 경우 자세한 내용은 [Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 업데이트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="a7e6d-155">Intune 배포</span><span class="sxs-lookup"><span data-stu-id="a7e6d-155">Intune deployment</span></span>

<span data-ttu-id="a7e6d-156">Intune을 사용하여 디바이스에 Surface Dock 펌웨어 업데이트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="a7e6d-157">먼저 다음 설명서에 설명된 바와 같이 MSI 파일을 .intunewin 형식으로 변환해야 [합니다. Intune 독립 실행형 - Win32 앱 관리.](https://docs.microsoft.com/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="a7e6d-158">다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-158">Use the following command:</span></span>
  - **<span data-ttu-id="a7e6d-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="a7e6d-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="a7e6d-160">펌웨어 업데이트 완료를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="a7e6d-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="a7e6d-161">Surface Dock 펌웨어는 다음 두 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="a7e6d-162">**Component10:** MCU(마이크로 컨트롤러 단위) 펌웨어</span><span class="sxs-lookup"><span data-stu-id="a7e6d-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="a7e6d-163">**Component20:** 디스플레이 포트(DP) 펌웨어.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="a7e6d-164">Surface Dock 펌웨어 업데이트가 성공적으로 완료되어 이러한 펌웨어 구성 요소에 대한 새 레지스트리 키 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="a7e6d-165">업데이트를 확인:</span><span class="sxs-lookup"><span data-stu-id="a7e6d-165">To verify updates:</span></span>**

1. <span data-ttu-id="a7e6d-166">Regedit를 열고 다음 레지스트리 경로로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="a7e6d-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="a7e6d-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="a7e6d-168">레지스트리 키를 확인합니다. **Component10CurrentFwVersion and Component20CurrentFwVersion**- 현재 장치에 있는 펌웨어를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Surface Dock 펌웨어 업데이트 설치 프로세스](images/regeditDock.png)

3. <span data-ttu-id="a7e6d-170">새 레지스트리 키 값이 이 문서 끝부분의 버전 참조에 나열된 업데이트된 레지스트리 키 값과 일치하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="a7e6d-171">값이 일치하면 펌웨어가 성공적으로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="a7e6d-172">확인할 수 없는 경우 다음 섹션의 이벤트 로깅 및 문제 해결 팁을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="a7e6d-173">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="a7e6d-173">Event logging</span></span>

**<span data-ttu-id="a7e6d-174">표 1.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-174">Table 1.</span></span> <span data-ttu-id="a7e6d-175">Surface Dock 펌웨어 업데이트 로그 파일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="a7e6d-176">Log</span><span class="sxs-lookup"><span data-stu-id="a7e6d-176">Log</span></span>                              | <span data-ttu-id="a7e6d-177">위치</span><span class="sxs-lookup"><span data-stu-id="a7e6d-177">Location</span></span>                               | <span data-ttu-id="a7e6d-178">참고</span><span class="sxs-lookup"><span data-stu-id="a7e6d-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a7e6d-179">Surface Dock 펌웨어 업데이트 로그</span><span class="sxs-lookup"><span data-stu-id="a7e6d-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="a7e6d-180">경로를 지정해야 합니다(참고 참조).</span><span class="sxs-lookup"><span data-stu-id="a7e6d-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="a7e6d-181">이 도구의 이전 버전에서는 응용 프로그램 및 서비스 로그\Microsoft Surface Dock Updater에 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="a7e6d-182">Windows 장치 설치 로그</span><span class="sxs-lookup"><span data-stu-id="a7e6d-182">Windows Device Install log</span></span>       | <span data-ttu-id="a7e6d-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="a7e6d-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="a7e6d-184">장치 설치 로그 사용에 대한 자세한 내용은 [SetupAPI 로깅 설명서를 참조하십시오.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)</span><span class="sxs-lookup"><span data-stu-id="a7e6d-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="a7e6d-185">표 2.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-185">Table 2.</span></span> <span data-ttu-id="a7e6d-186">Surface Dock 펌웨어 업데이트에 대한 이벤트 로그 ID</span><span class="sxs-lookup"><span data-stu-id="a7e6d-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="a7e6d-187">이벤트는 응용 프로그램 이벤트 로그에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="a7e6d-188">참고: 이 도구의 이전 버전은 응용 프로그램 및 서비스 로그\Microsoft Surface Dock Updater에 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="a7e6d-189">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a7e6d-189">Event ID</span></span> | <span data-ttu-id="a7e6d-190">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="a7e6d-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="a7e6d-191">2001</span><span class="sxs-lookup"><span data-stu-id="a7e6d-191">2001</span></span>     | <span data-ttu-id="a7e6d-192">Dock 펌웨어 업데이트가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="a7e6d-193">2002</span><span class="sxs-lookup"><span data-stu-id="a7e6d-193">2002</span></span>     | <span data-ttu-id="a7e6d-194">Dock 펌웨어 업데이트는 도킹이 최신 버전으로 알려져 있기 때문에 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="a7e6d-195">2003</span><span class="sxs-lookup"><span data-stu-id="a7e6d-195">2003</span></span>     | <span data-ttu-id="a7e6d-196">Dock 펌웨어 업데이트가 펌웨어 버전을 다운로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="a7e6d-197">2004</span><span class="sxs-lookup"><span data-stu-id="a7e6d-197">2004</span></span>     | <span data-ttu-id="a7e6d-198">펌웨어 버전 쿼리</span><span class="sxs-lookup"><span data-stu-id="a7e6d-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="a7e6d-199">2005</span><span class="sxs-lookup"><span data-stu-id="a7e6d-199">2005</span></span>     | <span data-ttu-id="a7e6d-200">Dock 펌웨어가 업데이트를 시작하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="a7e6d-201">2006</span><span class="sxs-lookup"><span data-stu-id="a7e6d-201">2006</span></span>     | <span data-ttu-id="a7e6d-202">제품/페이로드 쌍을 보내지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="a7e6d-203">2007</span><span class="sxs-lookup"><span data-stu-id="a7e6d-203">2007</span></span>     | <span data-ttu-id="a7e6d-204">펌웨어 업데이트가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="a7e6d-205">2008</span><span class="sxs-lookup"><span data-stu-id="a7e6d-205">2008</span></span>     | <span data-ttu-id="a7e6d-206">BEGIN dock 원격 분석.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="a7e6d-207">2011</span><span class="sxs-lookup"><span data-stu-id="a7e6d-207">2011</span></span>     | <span data-ttu-id="a7e6d-208">끝 도크 원격 분석.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-208">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="a7e6d-209">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="a7e6d-209">Troubleshooting tips</span></span>

- <span data-ttu-id="a7e6d-210">AC 전원에서 Surface Dock의 전원을 완전히 분리하여 Surface Dock를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="a7e6d-211">Surface Dock를 제외한 모든 주변 장치를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="a7e6d-212">현재 Surface Dock 펌웨어 업데이트를 제거한 다음 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="a7e6d-213">Surface Dock가 분리되어 있는지 확인한 다음 도크의 이더넷 포트에 있는 LED를 통해 모니터링되는 업데이트가 완료될 수 있도록 충분한 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="a7e6d-214">LED가 깜박이지 않는 동안 기다렸다가 Surface Dock의 전원을 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="a7e6d-215">Surface Dock를 다른 장치에 연결하여 Dock를 업데이트할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="a7e6d-216">버전 참조</span><span class="sxs-lookup"><span data-stu-id="a7e6d-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="a7e6d-217">설치 파일은 다음 이름 지정 \*\* 형식으로 \*\* 릴리스됩니다.Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI(예: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 기본적으로 C:\Program Files\SurfaceUpdate로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="a7e6d-218">버전 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="a7e6d-219">릴리스 날짜: 2020년 8월 4일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="a7e6d-220">이 버전의 Surface Dock 펌웨어 업데이트에는 버그 수정 및 다음에 대한 지원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="a7e6d-221">Surface Pro X를 사용하여 Surface Dock 1 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="a7e6d-222">Surface Pro X를 실행하는 경우 . ARM64 빌드.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="a7e6d-223">다른 모든 디바이스의 경우 AMD64 빌드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="a7e6d-224">레지스트리 키 값</span><span class="sxs-lookup"><span data-stu-id="a7e6d-224">Registry key values</span></span>

<span data-ttu-id="a7e6d-225">펌웨어 업데이트 상태를 나타내는 레지스트리 값은 이 도구의 이전 버전에서 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="a7e6d-226">Component10CurrentFwVersion이 **4ac3970으로 업데이트되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="a7e6d-227">Component20CurrentFwVersion이 **4a1d570으로 업데이트되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <span data-ttu-id="a7e6d-228">버전 1.42.139</span><span class="sxs-lookup"><span data-stu-id="a7e6d-228">Version 1.42.139</span></span> 
*<span data-ttu-id="a7e6d-229">릴리스 날짜: 2019년 9월 18일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="a7e6d-230">이 버전은 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 펌웨어를 백그라운드에서 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="a7e6d-231">레지스트리 키 값 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-231">Updated registry key values</span></span>

- <span data-ttu-id="a7e6d-232">Component10CurrentFwVersion이 **4ac3970으로 업데이트되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="a7e6d-233">Component20CurrentFwVersion이 **4a1d570으로 업데이트되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="a7e6d-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="a7e6d-234">Surface Pro 7 및 Surface Laptop 3에 대한 지원이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="a7e6d-235">레거시 버전</span><span class="sxs-lookup"><span data-stu-id="a7e6d-235">Legacy versions</span></span>

### <span data-ttu-id="a7e6d-236">버전 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="a7e6d-237">릴리스 날짜: 2018년 10월 10일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="a7e6d-238">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="a7e6d-239">Surface Pro 6에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="a7e6d-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="a7e6d-240">Surface Laptop 2에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="a7e6d-240">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="a7e6d-241">버전 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="a7e6d-242">릴리스 날짜: 2018년 7월 26일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="a7e6d-243">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="a7e6d-244">업데이트 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="a7e6d-244">Increase update reliability</span></span>
- <span data-ttu-id="a7e6d-245">Surface Go에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="a7e6d-245">Add support for Surface Go</span></span>

### <span data-ttu-id="a7e6d-246">버전 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="a7e6d-247">릴리스 날짜: 2018년 1월 29일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="a7e6d-248">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="a7e6d-249">Surface Dock 메인 칩 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="a7e6d-250">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="a7e6d-251">Surface Book 또는 Surface Book 2와 함께 사용하는 경우 외부 디스플레이의 디스플레이 안정성이 개선</span><span class="sxs-lookup"><span data-stu-id="a7e6d-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="a7e6d-252">또한, 이 버전의 Surface Dock 업데이트 프로그램을 Surface Book 디바이스에 설치하면 다음이 함께 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="a7e6d-253">Surface Book 본체 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="a7e6d-254">Surface Book 디바이스를 대상으로 하는 개선 기능이 포함된 Surface Dock 펌웨어 업데이트에 대한 지원이 추가</span><span class="sxs-lookup"><span data-stu-id="a7e6d-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="a7e6d-255">버전 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="a7e6d-256">릴리스 날짜: 2017년 11월 3일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="a7e6d-257">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a7e6d-258">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="a7e6d-259">패시브 디스플레이 포트 어댑터의 오디오 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-259">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="a7e6d-260">버전 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="a7e6d-261">출시 날짜: 2017년 6월 19일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="a7e6d-262">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a7e6d-263">Surface 노트북</span><span class="sxs-lookup"><span data-stu-id="a7e6d-263">Surface Laptop</span></span>
* <span data-ttu-id="a7e6d-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="a7e6d-264">Surface Pro</span></span>

### <span data-ttu-id="a7e6d-265">버전 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="a7e6d-266">릴리스 날짜: 2017년 4월 7일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="a7e6d-267">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a7e6d-268">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="a7e6d-269">Windows 10 필요</span><span class="sxs-lookup"><span data-stu-id="a7e6d-269">Requires Windows 10</span></span>

### <span data-ttu-id="a7e6d-270">버전 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="a7e6d-271">릴리스 날짜: 2016년 10월 21일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="a7e6d-272">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a7e6d-273">Surface Dock USB 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="a7e6d-274">이더넷, 오디오 및 USB 포트의 안전성 개선</span><span class="sxs-lookup"><span data-stu-id="a7e6d-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="a7e6d-275">버전 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="a7e6d-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="a7e6d-276">릴리스 날짜: 2016년 4월 26일</span><span class="sxs-lookup"><span data-stu-id="a7e6d-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="a7e6d-277">이 버전의 Surface Dock Update는 다음에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e6d-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="a7e6d-278">Surface Dock Main Chipset 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="a7e6d-279">Surface Dock DisplayPort 펌웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="a7e6d-279">Update for Surface Dock DisplayPort firmware</span></span>

