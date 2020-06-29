---
title: Configuration Manager에서 화면 드라이버 업데이트 관리
description: 이 문서에서는 Surface 장치에 대 한 펌웨어 및 드라이버 업데이트를 관리 하 고 배포 하는 데 사용할 수 있는 옵션을 설명 합니다.
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
ms.openlocfilehash: 1a9c8c64bd524de58696c73a28795b69cc70a7b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835868"
---
# Configuration Manager에서 화면 드라이버 업데이트 관리

## 요약

[Microsoft System Center Configuration Manager 버전 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)에서 시작 하 여 Configuration manager 클라이언트를 통해 microsoft Surface 펌웨어와 드라이버 업데이트를 직접 동기화 하 고 배포할 수 있습니다. 프로세스는 정기 업데이트 배포와 유사 합니다. 그러나 화면 드라이버 업데이트를 카탈로그로 가져오려면 몇 가지 추가 구성이 필요 합니다.

## 필수 구성 요소

화면 드라이버 업데이트를 관리 하려면 다음 필수 구성 요소를 충족 해야 합니다.

- Configuration Manager 버전 1710 이상 버전을 사용 해야 합니다.
- 모든 소프트웨어 업데이트 지점 (SUPs)은 Windows Server 2016 이상 버전을 실행 해야 합니다. 그렇지 않으면 구성 관리자가이 설정을 무시 하 고 Surface drivers가 동기화 되지 않습니다.

> [!NOTE]
> 환경이 전제 조건을 충족 하지 않는 경우 [FAQ](#frequently-asked-questions-faq) 섹션에서 화면 드라이버 및 펌웨어 업데이트를 배포 하는 [대체 방법을](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) 참조 하세요.

## 유용한 로그 파일

다음 로그는 화면 드라이버 업데이트를 관리 하는 경우 특히 유용 합니다.

|로그 이름|설명|
|---|---|
|WCM. 로그|소프트웨어 업데이트 지점의 구성에 대 한 세부 정보와 구독 하는 업데이트 범주, 분류 및 언어에 대 한 WSUS 서버로의 연결을 기록 합니다.|
|WsyncMgr .log|소프트웨어 업데이트 동기화 프로세스에 대 한 세부 정보를 기록 합니다.|

이러한 로그는 SUP를 관리 하는 사이트 서버 (사이트 서버에 직접 설치 된 경우 SUP)에 있습니다.
Configuration Manager 로그의 전체 목록은 [System Center Configuration manager에서 로그 파일](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)을 참조 하세요.

## 화면 드라이버 업데이트 관리 사용

Configuration Manager에서 화면 드라이버 업데이트 관리를 사용 하도록 설정 하려면 다음 단계를 따릅니다.

1. Configuration Manager 콘솔에서 **관리**  >  **개요**  >  **사이트 구성**  >  **사이트로**이동 합니다.
1. 환경에 대 한 최상위 수준의 SUP 서버가 포함 된 사이트를 선택 합니다.
1. 리본 메뉴에서 **사이트 구성 요소 구성을**선택한 다음 **소프트웨어 업데이트 지점을**선택 합니다. 또는 사이트를 마우스 오른쪽 단추로 클릭 한 다음 **사이트 구성 요소**  >  **소프트웨어 업데이트 지점을**구성 합니다 .를 선택 합니다.
1. **분류** 탭에서 **Microsoft Surface drivers 및 펌웨어 업데이트 포함** 확인란을 선택 합니다.

   ![소프트웨어 업데이트 지점의 구성 요소 속성](images/manage-surface-driver-updates-1.png)

1. 다음 경고 메시지가 표시 되 면 **확인**을 선택 합니다.

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. Products (제품) 탭에서 업데이트 하려는 제품을 선택 하 고 **확인**을 선택 합니다.

   대부분의 드라이버는 다음 제품 그룹에 속합니다.

   - Windows 10 이상 버전 드라이버
   - Windows 10 이상 업그레이드 & 서비스 드라이버
   - Windows 10 기념일 업데이트 및 이후 서비스 드라이버
   - Windows 10 기념 업데이트 이상 업그레이드 & 서비스 드라이버
   - Windows 10 크리에이터 업데이트 및 이후 서비스 드라이버
   - Windows 10 크리에이터 업데이트 및 이후 업그레이드 & 서비스 드라이버
   - Windows 10 낙하 작성자 업데이트 및 이후 서비스 드라이버
   - Windows 10 낙하 작성자 업데이트 및 최신 업그레이드 & 서비스 드라이버
   - Windows 10 S 이상 서비스 드라이버
   - 테스트를 위한 Windows 10 S 버전 1709 이상 서비스 드라이버
   - Windows 10 S 버전 1709 이상 업그레이드 & 테스트를 위한 드라이버 서비스

   > [!NOTE]
   > 대부분의 Surface 드라이버는 여러 Windows 10 제품 그룹에 속합니다. 여기에 나열 된 모든 제품을 선택 해야 할 수 있습니다. 업데이트 카탈로그를 채우는 제품의 수를 줄이려면 동기화를 위해 환경에 필요한 제품만 선택 하는 것이 좋습니다.

## 구성 확인

SUP가 올바르게 구성 되어 있는지 확인 하려면 다음 단계를 따르세요.

1. WsyncMgr .log를 열고 다음 항목을 찾습니다.

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   다음 항목 중 하나가 ' w Syngr. 로그 '에 기록 되 면 이전 섹션의 4 단계를 다시 검사 합니다.

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. WCM를 열고 다음과 유사한 항목을 찾습니다.

   ![WCM. 로그 설정](images/manage-surface-driver-updates-3.png)

   이 항목은 현재 SUP 서버에서 동기화 하는 모든 제품 그룹과 분류를 나열 하는 XML 요소입니다. 예를 들어 다음과 같은 항목이 표시 될 수 있습니다.

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   이전 섹션의 6 단계에서 선택한 제품을 찾을 수 없는 경우 SUP 설정이 저장 되었는지 두 번 확인 합니다.

   다음 동기화가 완료 될 때까지 기다린 다음 Surface driver 및 펌웨어 업데이트가 Configuration Manager 콘솔의 소프트웨어 업데이트에 나열 되는지 확인 합니다. 예를 들어 콘솔에는 다음 정보가 표시 될 것입니다.

   ![모든 소프트웨어 업데이트 검색 결과](images/manage-surface-driver-updates-4.png)

## 수동 동기화

다음 동기화가 끝날 때까지 기다리지 않으려는 경우 다음 단계에 따라 동기화를 시작 합니다.

1. Configuration Manager 콘솔에서 소프트웨어 **라이브러리로**이동  >  **개요**  >  **소프트웨어**는  >  **모든 소프트웨어 업데이트**를 업데이트 합니다.
1. 리본 메뉴에서 **소프트웨어 업데이트 동기화**를 선택 합니다. 또는 **모든 소프트웨어 업데이트**를 마우스 오른쪽 단추로 클릭 한 다음 **소프트웨어 업데이트 동기화**를 선택 합니다.
1. WsyncMgr. 로그에서 다음 항목을 찾아 동기화 진행 상태를 모니터링 합니다.

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

## Surface 펌웨어와 드라이버 업데이트 배포

다른 업데이트를 배포 하는 것과 동일한 방식으로 Surface 펌웨어와 드라이버 업데이트를 배포할 수 있습니다.

배포에 대 한 자세한 내용은 [System Center 2012 구성 관리자 – Part7: 소프트웨어 업데이트 (배포)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)를 참조 하세요.

## 질문과 대답(FAQ)

**이 문서의 단계를 수행한 후에도 Surface 드라이버도 동기화 되지 않습니다. 왜 그럴까요?**

Microsoft 업데이트 대신 업스트림 WSUS (Windows Server Update Services) 서버에서 동기화 하는 경우에는 업스트림 WSUS 서버가 Surface driver 업데이트를 지원 하 고 동기화 하도록 구성 되어 있는지 확인 합니다. 모든 다운스트림 서버는 업스트림 WSUS 서버 데이터베이스에 있는 업데이트로 제한 됩니다.

WSUS의 드라이버로 분류 되는 68000 업데이트가 있습니다. 비 Surface 관련 드라이버를 구성 관리자와 동기화 하는 것을 방지 하기 위해 Microsoft는 허용 목록에 대해 드라이버 동기화를 필터링 합니다. 새 허용 목록이 게시 되 고 구성 관리자에 통합 되 면 다음 동기화 이후 새 드라이버가 콘솔에 추가 됩니다. Microsoft는 Configuration Manager와 동기화 하는 데 사용할 수 있도록 각 월에 허용 목록에 추가 된 화면 드라이버를 다운로드 하는 것을 목표로 합니다.

구성 관리자 환경이 오프 라인 상태인 경우에는 Configuration Manager에 대 한 [서비스 업데이트](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 를 가져올 때마다 새 허용 목록을 가져옵니다. 또한 업데이트가 Configuration Manager 콘솔에 표시 되기 전에 해당 드라이버를 포함 하는 [새 WSUS 카탈로그](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) 를 가져와야 합니다. 독립 실행형 WSUS 환경에는 구성 관리자 SUP 보다 더 많은 드라이버가 포함 되어 있으므로 온라인 기능이 있는 Configuration Manager 환경을 설정 하 고 화면 드라이버를 동기화 하도록 구성 하는 것이 좋습니다. 이것은 오프 라인 환경과 비슷하게 WSUS 내보내기의 크기를 줄입니다.

Configuration Manager 환경이 온라인 상태이 고 새 업데이트를 검색할 수 있는 경우 목록에 대 한 업데이트를 자동으로 받게 됩니다. 예상 되는 드라이버가 표시 되지 않으면 모든 동기화 오류에 대해 WCM 및 WsyncMgr. 로그를 검토 하세요.

**내 구성 관리자 환경이 오프 라인 상태 이므로 수동으로 Surface drivers를 WSUS로 가져올 수 있나요?**

아니요. 업데이트를 WSUS에 가져오면 해당 업데이트가 허용 목록에 나열 되어 있지 않은 경우 배포를 위해 Configuration Manager 콘솔로 가져오지 않습니다. [서비스 연결 도구](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 를 사용 하 여 구성 관리자에 대 한 서비스 업데이트를 가져와 허용 목록을 업데이트 해야 합니다.

**화면 드라이버와 펌웨어 업데이트를 배포 하는 데는 어떤 대체 방법이 필요 한가요?**

대체 채널을 통해 Surface driver 및 펌웨어 업데이트를 배포 하는 방법에 대 한 자세한 내용은 [surface driver 및 펌웨어 업데이트 관리](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates)를 참조 하세요. .Msi 또는 .exe 파일을 다운로드 한 다음 기존 소프트웨어 배포 채널을 통해 배포 하려는 경우에는 [구성 관리자를 사용 하 여 Surface 펌웨어를 업데이트 상태로 유지](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)를 참조 하세요.

## 추가 정보

Surface driver 및 펌웨어 업데이트에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [Surface 장치의 최신 펌웨어 및 드라이버 다운로드](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)
- [Surface 드라이버 및 펌웨어 업데이트 관리](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)
- [Surface 및 System Center Configuration Manager에 대한 고려 사항](https://docs.microsoft.com/surface/considerations-for-surface-and-system-center-configuration-manager)
