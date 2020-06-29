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
ms.openlocfilehash: c5b6a083d543649eab899d2fea36327d08f8bc29
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834516"
---
# <span data-ttu-id="c51e8-103">Surface Hub 시작 메뉴 구성</span><span class="sxs-lookup"><span data-stu-id="c51e8-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="c51e8-104">[2018년 1월 17일 Windows 10 업데이트](https://support.microsoft.com/help/4057144)(빌드 15063.877)를 통해 Surface Hub 디바이스에서 시작 메뉴를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="c51e8-105">모바일 디바이스 관리(MDM)를 사용하여 사용자 지정 시작 메뉴 레이아웃을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="c51e8-106">Surface Hub에 사용자 지정 시작 메뉴 레이아웃을 적용할 때 사용자는 시작 메뉴에서 앱을 고정, 고정 해제 또는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <span data-ttu-id="c51e8-107">Surface Hub에 사용자 지정 시작 메뉴를 적용하는 방법</span><span class="sxs-lookup"><span data-stu-id="c51e8-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="c51e8-108">사용자 지정 시작 메뉴는 시작 화면 레이아웃 XML 파일에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="c51e8-109">시작 화면 레이아웃 XML 파일을 만들기 위한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="c51e8-110">[기본 Surface Hub 시작 화면 XML](#default)을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="c51e8-111">-또는-</span><span class="sxs-lookup"><span data-stu-id="c51e8-111">-or-</span></span>

- <span data-ttu-id="c51e8-112">바탕 화면에서 원하는 시작 메뉴를 구성(Surface Hub에서 사용할 수 있는 앱만 고정)하고 [레이아웃을 내보냅니다](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span><span class="sxs-lookup"><span data-stu-id="c51e8-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="c51e8-113">바탕 화면 시작 메뉴에 대한 웹 링크에서 타일을 추가하려면 Microsoft Edge의 링크로 이동하여 오른쪽 상단의 `...`을 선택하고 **이 페이지를 시작에 고정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="c51e8-114">XML에서 링크가 어떻게 나타나는지에 대한 예제는 [Microsoft Edge 링크를 포함하여 시작 화면 레이아웃](#edge)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c51e8-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="c51e8-115">기본 XML이나 내보낸 레이아웃을 편집하려면 [시작 화면 레이아웃 XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop)을 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="c51e8-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="c51e8-116">[바탕 화면의 시작 레이아웃과 Surface Hub 간에 몇 가지 차이점](#differences)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="c51e8-117">시작 화면 레이아웃 XML에 시작 메뉴를 정의할 때 [레이아웃에 적용할 MDM 정책 만들기](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />
## <span data-ttu-id="c51e8-118">Surface Hub와 바탕 화면 시작 메뉴 간의 차이</span><span class="sxs-lookup"><span data-stu-id="c51e8-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="c51e8-119">Surface Hub를 위한 시작 메뉴 사용자 지정과 Windows 10 바탕 화면 간에는 몇 가지 중요한 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="c51e8-120">**Desktopapplicationtile** ( https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) Windows 데스크톱 응용 프로그램 (Win32)은 Surface Hub에서 지원 되지 않으므로 시작 레이아웃 XML에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="c51e8-121">시작 화면 레이아웃 XML을 사용하여 Surface Hub를 위한 작업 표시줄이나 시작 화면을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="c51e8-122">Surface Hub는 최대 6개 열(6개의 1x1 타일)을 지원하지만, Surface Hub가 열 6과 7이 아닌 0 ~ 5 열에만 타일을 표시하는 경우라 하더라도 **반드시** `GroupCellWidth=8`을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-122">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="c51e8-123">Surface Hub는 최대 6개 행(6개 1x1 타일)을 지원하며,</span><span class="sxs-lookup"><span data-stu-id="c51e8-123">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="c51e8-124">이들은 링크에 사용됩니다. Microsoft Edge에서 링크를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-124">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />
## <span data-ttu-id="c51e8-125">예제: 기본 Surface Hub 시작 화면 레이아웃</span><span class="sxs-lookup"><span data-stu-id="c51e8-125">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
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
## <span data-ttu-id="c51e8-126">예제: Microsoft Edge 링크가 포함된 시작 화면 레이아웃</span><span class="sxs-lookup"><span data-stu-id="c51e8-126">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="c51e8-127">이 예제는 웹 사이트에 대한 링크와 .pdf 파일에 대한 링크를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-127">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="c51e8-128">Microsoft Edge 용 보조 타일은 150 x 150 픽셀 아이콘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-128">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

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
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
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
><span data-ttu-id="c51e8-129">`ForegroundText` `ForegroundText` 값이 어둡게 변경 되지 않는 경우에는 기본값을 value로 지정 하지 않는 한 해당 값을 XML에 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c51e8-129">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>
