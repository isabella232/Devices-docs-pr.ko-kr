---
title: Surface Hub 시작 메뉴 구성
description: MDM를 사용하여 Surface Hub에 대한 시작 메뉴를 사용자 지정합니다.
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: ff08b8ab6e59af77761fb365980af261c47030a9
ms.sourcegitcommit: 09a47921ec2e565a92ba2baa61e181d218706ad9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2021
ms.locfileid: "11921827"
---
# <a name="configure-surface-hub-start-menu"></a>Surface Hub 시작 메뉴 구성

[2018년 1월 17일 Windows 10 업데이트](https://support.microsoft.com/help/4057144)(빌드 15063.877)를 통해 Surface Hub 디바이스에서 시작 메뉴를 사용자 지정할 수 있습니다. 모바일 디바이스 관리(MDM)를 사용하여 사용자 지정 시작 메뉴 레이아웃을 적용할 수 있습니다.

Surface Hub에 사용자 지정 시작 메뉴 레이아웃을 적용할 때 사용자는 시작 메뉴에서 앱을 고정, 고정 해제 또는 제거할 수 없습니다. 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a>Surface Hub에 사용자 지정 시작 메뉴를 적용하는 방법

사용자 지정 시작 메뉴는 시작 화면 레이아웃 XML 파일에 정의되어 있습니다. 시작 화면 레이아웃 XML 파일을 만들기 위한 두 가지 옵션이 있습니다.

- [기본 Surface Hub 시작 화면 XML](#default)을 편집합니다.

    -또는-

- 바탕 화면에서 원하는 시작 메뉴를 구성(Surface Hub에서 사용할 수 있는 앱만 고정)하고 [레이아웃을 내보냅니다](/windows/configuration/customize-and-export-start-layout#export-the-start-layout).

>[!TIP]
>바탕 화면 시작 메뉴에 대한 웹 링크에서 타일을 추가하려면 Microsoft Edge의 링크로 이동하여 오른쪽 상단의 `...`을 선택하고 **이 페이지를 시작에 고정**을 선택합니다. XML에서 링크가 어떻게 나타나는지에 대한 예제는 [Microsoft Edge 링크를 포함하여 시작 화면 레이아웃](#edge)을 참조하세요.

기본 XML이나 내보낸 레이아웃을 편집하려면 [시작 화면 레이아웃 XML](/windows/configuration/start-layout-xml-desktop)을 숙지하세요. [바탕 화면의 시작 레이아웃과 Surface Hub 간에 몇 가지 차이점](#differences)이 있습니다.

시작 화면 레이아웃 XML에 시작 메뉴를 정의할 때 [레이아웃에 적용할 MDM 정책 만들기](/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)를 수행합니다.

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a>Surface Hub와 바탕 화면 시작 메뉴 간의 차이

Surface Hub를 위한 시작 메뉴 사용자 지정과 Windows 10 바탕 화면 간에는 몇 가지 중요한 차이가 있습니다.

- 데스크톱 응용 프로그램(Win32)에서 지원되지 Windows 시작 화면 레이아웃 XML에서 **[DesktopApplicationTile을](/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile)** 사용할 Surface Hub.
- 시작 화면 레이아웃 XML을 사용하여 Surface Hub를 위한 작업 표시줄이나 시작 화면을 구성할 수 없습니다.  
- 시작 화면 레이아웃 정책은 사용자가 아닌 디바이스에만 할당해야 합니다.
- 정책에 사용할 OMA-URI 설정은 `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- Surface Hub는 최대 6개 열(6개의 1x1 타일)을 지원하지만, Surface Hub가 열 6과 7이 아닌 0 ~ 5 열에만 타일을 표시하는 경우라 하더라도 **반드시** `GroupCellWidth=8`을 정의해야 합니다.
- Surface Hub는 최대 6개 행(6개 1x1 타일)을 지원하며,
- `SecondaryTile`이들은 링크에 사용됩니다. Microsoft Edge에서 링크를 엽니다.


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a>예제: 기본 Surface Hub 시작 화면 레이아웃

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:DesktopApplicationTile
            DesktopApplicationID="MSEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a>예제: Microsoft Edge 링크가 포함된 시작 화면 레이아웃

이 예제는 웹 사이트에 대한 링크와 .pdf 파일에 대한 링크를 보여줍니다. 150 x Microsoft Edge 아이콘을 사용하는 기본 타일입니다.

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
          <start:DesktopApplicationTile
              DesktopApplicationID="MSEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
>기본값은 밝습니다. 값을 어둡게 변경하지 않는 한 `ForegroundText` `ForegroundText` XML에 포함할 필요가 없습니다.
