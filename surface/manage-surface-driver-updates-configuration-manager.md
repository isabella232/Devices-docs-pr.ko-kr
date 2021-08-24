---
title: Configuration Manager에서 구성 관리자 관리
description: 이 문서에서는 Surface 디바이스의 펌웨어 및 드라이버 업데이트를 관리하고 배포하는 데 사용할 수 있는 옵션에 대해 설명하고 있습니다.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, 펌웨어, 업데이트, 디바이스, 관리, 배포, 드라이버, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: da90a0481052d06c2108c8fd096d088bfacdcb87
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911003"
---
# <a name="manage-surface-driver-updates-in-configuration-manager"></a>Configuration Manager에서 구성 관리자 관리

## <a name="summary"></a>요약

Microsoft System Center Configuration Manager [버전 1710부터](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)Configuration Manager 클라이언트를 통해 Microsoft Surface 펌웨어 및 드라이버 업데이트를 직접 동기화하고 배포할 수 있습니다. 이 프로세스는 정기적인 업데이트 배포와 입니다. 그러나 Surface 드라이버 업데이트를 카탈로그로 다운로드하려면 몇 가지 추가 구성이 필요합니다.

## <a name="prerequisites"></a>필수 구성 요소

Surface 드라이버 업데이트를 관리하려면 다음의 선행 구성을 충족해야 합니다.

- Configuration Manager 버전 1710 이상을 사용해야 합니다.
- 모든 SUP(소프트웨어 업데이트 지점)는 Windows Server 2016 이상 버전으로 실행해야 합니다. 그렇지 않으면 Configuration Manager에서 이 설정을 무시하고 Surface 드라이버를 동기화하지 않습니다.

> [!NOTE]
> 환경이 선행 요구 사항을 충족하지 않는 경우 FAQ 섹션에서 Surface 드라이버 및 펌웨어 업데이트를 배포하는 다른 방법을 [참조하세요.](#frequently-asked-questions-faq) [](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1)

## <a name="useful-log-files"></a>유용한 로그 파일

다음 로그는 Surface 드라이버 업데이트를 관리할 때 특히 유용합니다.

|로그 이름|설명|
|---|---|
|WCM.log|구독된 업데이트 범주, 분류 및 언어에 대한 WSUS 서버에 대한 연결 및 소프트웨어 업데이트 지점 구성에 대한 세부 정보를 기록합니다.|
|WsyncMgr.log|소프트웨어 업데이트 동기화 프로세스에 대한 세부 정보를 기록합니다.|

이러한 로그는 SUP를 관리하는 사이트 서버 또는 사이트 서버에 직접 설치된 경우 SUP 자체에 있습니다.
Configuration Manager 로그의 전체 목록은 에서 [로그 파일을 System Center Configuration Manager.](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)

## <a name="enabling-surface-driver-updates-management"></a>Surface 드라이버 업데이트 관리 사용

Configuration Manager에서 Surface 드라이버 업데이트 관리를 사용하도록 설정하려면 다음 단계를 수행합니다.

1. Configuration Manager 콘솔에서 관리 **** 개요 사이트 구성  >  ****  >  **사이트로**  >  **이동하십시오.**
1. 해당 환경에 대한 최상위 SUP 서버가 포함된 사이트를 선택합니다.
1. 리본 메뉴에서 사이트 구성 **요소 구성을 선택한**다음 소프트웨어 업데이트 지점 **을 선택합니다.** 또는 사이트를 마우스 오른쪽 단추로 클릭한 다음 **사이트**구성 요소 소프트웨어 업데이트 지점  >  **구성 을 선택합니다.**
1. 분류 **탭에서** Microsoft Surface 드라이버 및 펌웨어 업데이트 **포함 확인란을** 선택합니다.

   ![소프트웨어 업데이트 지점 구성 요소 속성](images/manage-surface-driver-updates-1.png)

1. 다음 경고 메시지가 표시될 때 확인 을 **선택합니다.**

   ![Configuration Manager.](images/manage-surface-driver-updates-2.png)

1. 제품 탭에서 업데이트할 제품을 선택하고 확인 을 **선택합니다.**

   대부분의 드라이버는 다음 제품 그룹에 속합니다.

   - Windows 10 이상 버전 드라이버
   - Windows 10 이상으로 업그레이드 & 드라이버 업그레이드
   - Windows 10 1주년 업데이트 및 이후 서비스 드라이버
   - Windows 10 1주년 업데이트 및 이후 업그레이드 & 드라이버
   - Windows 10 크리에이터스 업데이트 이상 서비스 드라이버
   - Windows 10 크리에이터스 업데이트 및 이후 업그레이드 & 드라이버
   - Windows 10 Fall Creators Update 이상 서비스 드라이버
   - Windows 10 Fall Creators Update 및 이후 업그레이드 & 드라이버
   - Windows 10 S 및 이후 서비스 드라이버
   - Windows 10 테스트를 위한 S 버전 1709 이상 서비스 드라이버
   - Windows 10 S 버전 1709 이상 업그레이드 & 서비스 드라이버를 테스트합니다.

   > [!NOTE]
   > 대부분의 Surface 드라이버는 여러 Windows 10 그룹에 속합니다. 여기에 나열된 모든 제품을 선택하지 않을 수도 있습니다. 업데이트 카탈로그를 채우는 제품 수를 줄일 수 있도록 동기화에 필요한 제품만 선택하는 것이 좋습니다.

## <a name="verifying-the-configuration"></a>구성 확인

SUP가 올바르게 구성되어 있는지 확인하려면 다음 단계를 수행합니다.

1. WsyncMgr.log를 열고 다음 항목을 찾아 봐야 합니다.

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   다음 항목 중 하나에 WsyncMgr.log에 기록되어 있는 경우 이전 섹션의 4단계를 다시 확인하십시오.

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. WCM.log를 열고 다음과 같은 항목을 찾아야 합니다.

   ![WCM.log 설정.](images/manage-surface-driver-updates-3.png)

   이 항목은 현재 SUP 서버에 의해 동기화된 모든 제품 그룹 및 분류를 나열하는 XML 요소입니다. 예를 들어 다음과 같은 항목이 표시될 수 있습니다.

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   이전 섹션의 6단계에서 선택한 제품을 찾을 수 없는 경우 SUP 설정이 저장되어 있는지 다시 확인합니다.

   다음 동기화가 완료될 때까지 기다렸다가 Surface 드라이버 및 펌웨어 업데이트가 Configuration Manager 콘솔의 소프트웨어 업데이트에 나열되어 있는지 확인할 수도 있습니다. 예를 들어 콘솔에 다음 정보가 표시될 수 있습니다.

   ![모든 소프트웨어 업데이트 검색 결과.](images/manage-surface-driver-updates-4.png)

## <a name="manual-synchronization"></a>수동 동기화

다음 동기화가 될 때까지 기다리지 않는 경우 다음 단계에 따라 동기화를 시작하세요.

1. Configuration Manager 콘솔에서 소프트웨어 **라이브러리**개요 소프트웨어  >  ****  >  **업데이트 모든**  >  **소프트웨어 업데이트 로 이동하십시오.**
1. 리본 메뉴에서 소프트웨어 업데이트 **동기화를 선택합니다.** 또는 모든 소프트웨어 업데이트를 마우스 오른쪽 **단추로 클릭한**다음 소프트웨어 업데이트 동기화 **를 선택합니다.**
1. WsyncMgr.log에서 다음 항목을 확인하여 동기화 진행률을 모니터링합니다.

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <a name="deploying-surface-firmware-and-driver-updates"></a>Surface 펌웨어 및 드라이버 업데이트 배포

다른 업데이트를 배포하는 방법과 동일한 방식으로 Surface 펌웨어 및 드라이버 업데이트를 배포할 수 있습니다.

배포에 대한 자세한 내용은 System Center [Configuration Manager–Part7: Software Updates (Deploy)를 참조하십시오.](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)

## <a name="frequently-asked-questions-faq"></a>질문과 대답(FAQ)

**이 문서의 단계를 수행한 후에도 Surface 드라이버는 여전히 동기화되지 않습니다. 왜 그런가요?**

Microsoft 업데이트가 아닌 WSUS(업스트림 Windows Server Update Services) 서버에서 동기화하는 경우 업스트림 WSUS 서버가 Surface 드라이버 업데이트를 지원하고 동기화하도록 구성되어 있는지 확인합니다. 모든 다운스트림 서버는 업스트림 WSUS 서버 데이터베이스에 있는 업데이트로 제한됩니다.

WSUS에서 드라이버로 분류된 업데이트는 68,000개 이상입니다. Surface가 아닌 관련 드라이버가 Configuration Manager와 동기화되지 않도록 Microsoft는 허용 목록에 대해 드라이버 동기화를 필터합니다. 새 허용 목록이 게시되어 Configuration Manager에 통합된 후 다음 동기화 후에 새 드라이버가 콘솔에 추가됩니다. Microsoft는 매월 월별 업데이트 릴리스에 맞춰 Surface 드라이버를 허용 목록에 추가하여 Configuration Manager와 동기화할 수 있도록 합니다.

Configuration Manager 환경이 오프라인 상태이면 서비스 업데이트를 Configuration Manager로 가져올 때마다 새 허용 목록을 가져오게 됩니다. [](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 또한 Configuration Manager 콘솔에 업데이트가 표시되기 전에 드라이버가 포함된 [새 WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) 카탈로그를 가져와야 합니다. 독립 실행형 WSUS 환경에는 Configuration Manager SUP보다 많은 드라이버가 포함되어 있기 때문에 온라인 기능이 있는 Configuration Manager 환경을 설정하고 Surface 드라이버를 동기화하도록 구성하는 것이 좋습니다. 이렇게 하면 오프라인 환경과 매우 같은 작은 WSUS 내보내기 기능을 사용할 수 있습니다.

Configuration Manager 환경이 온라인에 있으며 새 업데이트를 검색할 수 있는 경우 목록에 대한 업데이트가 자동으로 수신됩니다. 예상된 드라이버가 없는 경우 WCM.log 및 WsyncMgr.log 파일에서 동기화 실패를 검토하십시오.

**내 Configuration Manager 환경이 오프라인 상태입니다. Surface 드라이버를 WSUS로 수동으로 가져올 수 있나요?**

아니요. 업데이트를 WSUS로 가져오는 경우에도 업데이트가 허용 목록에 나열되지 않은 경우 배포를 위해 Configuration Manager 콘솔로 가져오지 않습니다. 서비스 연결 [](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 도구를 사용하여 서비스 업데이트를 Configuration Manager로 가져와 허용 목록을 업데이트해야 합니다.

**Surface 드라이버 및 펌웨어 업데이트를 배포해야 하는 대체 방법은 무엇입니까?**

대체 채널을 통해 Surface 드라이버 및 펌웨어 업데이트를 배포하는 방법에 대한 자세한 내용은 Surface 드라이버 및 펌웨어 업데이트 [관리를 참조하세요.](manage-surface-driver-and-firmware-updates.md) .msi 또는 .exe 다운로드한 다음 기존 소프트웨어 배포 채널을 통해 배포하려면 Configuration Manager를 사용하여 Surface 펌웨어 업데이트 유지를 [참조하세요.](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)

## <a name="additional-information"></a>추가 정보

Surface 드라이버 및 펌웨어 업데이트에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Surface 드라이버 및 펌웨어 업데이트 관리](manage-surface-driver-and-firmware-updates.md)
- [Surface 및 System Center Configuration Manager에 대한 고려 사항](considerations-for-surface-and-system-center-configuration-manager.md)
