---
title: Surface Pro 3의 고급 UEFI 보안 기능(Surface)
description: 이 문서에서는 v3.11.760.0 UEFI 업데이트를 설치하고 구성하여 Surface Pro 3 디바이스에 대한 추가 보안 옵션을 사용하도록 설정하는 방법에 대해 설명합니다.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: 보안, 기능, 구성, 하드웨어, 디바이스, 사용자 지정, 스크립트, 업데이트
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163183"
---
# Surface Pro 3의 고급 UEFI 보안 기능


이 문서에서는 v3.11.760.0 UEFI 업데이트를 설치하고 구성하여 Surface Pro 3 디바이스에 대한 추가 보안 옵션을 사용하도록 설정하는 방법에 대해 설명합니다.

Surface 디바이스 보안에 대해 좀 더 세부적으로 제어할 수 있도록 v3.11.760.0 UEFI 업데이트에서는 사용자가 특정 하드웨어 디바이스를 사용하지 않도록 설정하거나 이 디바이스에서 시작하지 않게 할 수 있는 추가 보안 옵션을 제공합니다. 디바이스에 UEFI 업데이트를 설치하고 나면 스크립트를 실행하여 수동 또는 자동으로 구성할 수 있습니다.

## 수동으로 UEFI 업데이트 설치


Surface 디바이스의 고급 보안 기능을 구성하려면 먼저 v3.11.760.0 UEFI 업데이트를 설치해야 합니다. 이 업데이트는 Windows 업데이트에서 업데이트를 받을 경우 자동으로 설치됩니다. Windows 업데이트를 사용하여 자동으로 업데이트하도록 Windows를 구성하는 방법에 대한 자세한 내용은 [Windows의 자동 업데이트 구성 및 사용 방법](https://support.microsoft.com/kb/306525)을 참조하세요.

Surface Pro 3에서 UEFI를 업데이트하기 위해 Surface Pro 3 펌웨어 및 드라이버 팩의 일부로 Surface UEFI 업데이트를 다운로드하여 설치할 수 있습니다. 이러한 펌웨어 및 드라이버 팩은 Microsoft 다운로드 센터의 [Surface Pro 3 페이지](https://www.microsoft.com/download/details.aspx?id=38826)에서 사용할 수 있습니다. 펌웨어 및 드라이버 팩에 대한 자세한 내용은 [Surface 디바이스의 최신 펌웨어 및 드라이버 다운로드](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)에서 확인할 수 있습니다. 이러한 펌웨어 및 드라이버 팩은 자체 포함된 Windows Installer(.msi) 및 보관(.zip) 형식으로 모두 사용할 수 있습니다. 이러한 두 가지 형식과, 이 형식을 사용하여 드라이버를 업데이트하는 방법에 대한 자세한 내용은 [Surface 드라이버 및 펌웨어 업데이트 관리](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates)에서 확인할 수 있습니다.

## 수동으로 추가 보안 설정 구성


>[!NOTE]
>Surface 디바이스에서 펌웨어 설정을 시작하려면 먼저 디바이스 전원이 꺼진 상태에서 **볼륨 크게** 단추를 길게 누르고, **전원** 단추를 눌렀다가 놓은 다음 디바이스가 부팅하기 시작하면 **볼륨 크게** 단추를 놓으세요.

Surface 디바이스에 v3.11.760.0 UEFI 업데이트를 설치하고 나면 이름이 **고급 디바이스 보안**으로 지정된 추가 UEFI 메뉴를 사용할 수 있게 됩니다. 이 메뉴를 클릭하면 다음 옵션이 표시됩니다.

| 옵션         | 설명                                                                                                                                                                          | 사용 가능한 설정(기본값은 굵게 표시) |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| 네트워크 부팅   | 네트워크에서 부팅할 수 있는 Surface 디바이스 기능을 사용하거나 사용하지 않도록 설정합니다(PXE 부팅이라고도 함).                                                                            | **사용**,부팅 불가능                   |
| 측면 USB       | Surface 디바이스 측면에 있는 USB 포트를 사용하거나 사용하지 않도록 설정합니다. 또한 부팅은 허용되지 않은 상태로 USB 포트를 사용하도록 설정할 수도 있습니다.                                                | **사용**, 부팅 불가능, 사용 안 함         |
| 도킹 포트   | Surface 도킹 스테이션에서 포트를 사용하거나 사용하지 않도록 설정합니다. 또한 도킹 스테이션의 USB 또는 이더넷 포트에서 부팅은 차단한 상태로 도킹 포트를 사용하도록 설정할 수도 있습니다. | **사용**, 부팅 불가능, 사용 안 함         |
| 전면 카메라   | Surface 디바이스의 앞면 카메라를 사용하거나 사용하지 않도록 설정합니다.                                                                                                                   | **사용**, 사용 안 함                       |
| 후면 카메라    | Surface 디바이스의 후면 카메라를 사용하거나 사용하지 않도록 설정합니다.                                                                                                                    | **사용**, 사용 안 함                       |
| 온보드 오디오 | Surface 디바이스에서 오디오를 사용하거나 사용하지 않도록 설정합니다.                                                                                                                                     | **사용**, 사용 안 함                       |
| microSD        | Surface 디바이스에서 microSD 슬롯을 사용하거나 사용하지 않도록 설정합니다.                                                                                                                          | **사용**, 사용 안 함                       |
| WiFi           | Surface 디바이스에서 기본 제공 Wi-Fi 송수신 디바이스를 사용하거나 사용하지 않도록 설정합니다. 이 옵션을 통해 Bluetooth도 사용하지 않도록 설정됩니다.                                                                              | **사용**, 사용 안 함                       |
| Bluetooth      | Surface 디바이스에서 기본 제공 Bluetooth 송수신 디바이스를 사용하거나 사용하지 않도록 설정합니다.                                                                                                        | **사용**, 사용 안 함                       |

 

## 추가 보안 설정 자동화


관리자 권한이 있는 IT 전문가로서 Microsoft 다운로드 센터에서 사용할 수 있는 [Surface Pro 3 펌웨어 도구(476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038)를 활용하여 UEFI 설정 구성을 자동화할 수 있습니다. 이 도구로 사용자 지정 응용 프로그램 또는 스크립트에서 호출할 수 있는 .NET 어셈블리가 설치됩니다.

**필수 조건**

-   아래 샘플 스크립트는 앞에서 언급한 확장을 활용하며, 관리 중인 디바이스에 도구를 설치했다고 가정합니다.
-   스크립트는 관리자 권한으로 실행해야 합니다.
-   디지털 서명되지 않은 샘플 스크립트를 실행하기 전에 Windows PowerShell 명령 [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx)를 호출해야 합니다.

**샘플 스크립트**

> [!NOTE]
> 아래 샘플 스크립트에서 사용되는 UEFI 암호는 일반 텍스트로 표시됩니다. 보호되는 위치에 스크립트를 저장하고 제어된 환경에서 스크립트를 실행하는 것이 좋습니다.


구성 가능한 옵션을 모두 표시합니다.

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

UEFI 암호를 설정 또는 변경합니다.

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

제안된 변경의 상태를 확인합니다.

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

UEFI를 기본값으로 되돌립니다.

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

상태 코드 해석

-   00 - 제안된 업데이트 성공
-   02 - 제안된 값 중 하나에 잘못된 문자 포함
-   03 - 제안되었으나 인식되지 않게 설정된 값 있음
-   0F - 잠금 해제 암호가 현재 설정된 암호화 일치하지 않음

 
