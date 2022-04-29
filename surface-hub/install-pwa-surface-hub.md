---
title: Surface Hub 프로그레시브 Web Apps 설치
description: 관리자가 Intune 또는 프로비저닝 패키지를 통해 Surface Hub PWA(프로그레시브 Web Apps)를 설치하는 방법을 설명합니다.
keywords: Surface Hub, PWA, 앱
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/27/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 687dd85d3490d420133edc5b7de3b2af0c0433ef
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497580"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Surface Hub 프로그레시브 Web Apps 설치

프로그레시브 웹앱(PWA) 지원은 Suface Hub에서 실행할 수 있는 사용 가능한 앱의 라이브러리를 크게 확장하는 풍부한 새 앱 원본을 엽니다.  사용자는 Microsoft Store 외부에서 다양한 애플리케이션에 액세스하고 앱 메뉴에서 직접 실행할 수 있습니다.  웹 페이지에 비해 PWA는 오프라인 기능, 백그라운드에서 업데이트하는 기능 및 기타 고유한 기능이 있는 네이티브 앱처럼 동작합니다. 대부분의 웹 사이트는 PWA로 설치할 수 있으며 웹 개발자가 사용하도록 설정된 추가 기능을 활용할 수 있습니다.

관리자는 Microsoft Intune 같은 MDM(모바일 디바이스 관리) 공급자를 통해 Surface Hubs에 PWA를 원격으로 설치할 수 있습니다. 또는 프로비전 팩을 사용할 수 있습니다. 이 문서에서는 YouTube, WebEx, Zoom 및 Uber를 설치하기 위한 샘플 코드와 사용자 고유의 PWA를 설치하기 위한 지침을 모두 설명합니다. 자세한 내용은 [프로그레시브 Web Apps 개요](/microsoft-edge/progressive-web-apps-chromium/)를 참조하세요.

> [!IMPORTANT]
> PWA를 설치하기 전에 Surface Hub [KB5011543](https://support.microsoft.com/help/5011543)(또는 후속 Windows 업데이트)이 설치되어 있는지 확인합니다. 최신 Windows 10 Team 업데이트에 대한 자세한 내용은 [Surface Hub 업데이트 기록을](surface-hub-update-history.md) 참조하세요.

- [Intune 통해 Surface Hub PWA 설치](#install-pwas-via-intune)
- [프로비저닝 패키지를 통해 Surface Hub PWA 설치](#install-pwas-via-provisioning-package)

사용자는 허브 세션 중에 사용할 PWA를 설치할 수도 있습니다. 세션이 종료되면 PWA가 제거됩니다. 자세한 내용은 [Microsoft Edge 앱 설치, 관리 또는 제거를](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113) 참조하세요.

## <a name="install-pwas-via-intune"></a>Intune 통해 PWA 설치

Intune 또는 다른 MDM 공급자를 사용하여 Surface Hubs에 PWA를 설치합니다. 자세한 내용은 [MDM 공급자를 사용하여 설정 관리를](manage-settings-with-mdm-for-surface-hub.md) 참조하세요.

### <a name="get-started"></a>시작

1. Microsoft Endpoint Manager [**관리 센터에서**](https://endpoint.microsoft.com/) Intune 포털에 로그인합니다.

2. **DevicesConfiguration** **** > **PoliciesCreate****** >  프로필로 이동합니다.

3. 플랫폼 아래에서 **Windows 10 이상을** 선택합니다. 프로필 유형에서 **템플릿을** 선택합니다. 템플릿 이름에서 **관리 템플릿을 선택합니다.**

4. 만들기를 선택합니다 **.**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Intune 구성 프로필 만들기" lightbox="images/pwa-hubpwainstall.png":::

5. 프로필 이름을 지정하고, 선택적 설명을 입력하고, **다음**을 선택합니다.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="이름 프로필" lightbox="images/pwa-hubwebappscreateprofile.png":::

### <a name="configure-force-installed-web-apps-policy-intune"></a>강제 설치 Web Apps 정책 구성(Intune)

1. **모든 설정** > **Computer 구성**에서 **Microsoft Edge** 선택하고 검색 상자에서 **강제 설치를** 입력하고 **강제 설치 Web Apps** 선택한 다음 **[사용]** 을 선택합니다.

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="강제 설치 웹앱 사용" lightbox="images/pwa-enable-force-install.png":::

2. **자동으로 설치될 Web Apps URL** 아래에서 다음 코드 조각을 복사하여 입력하여 YouTube, Webex, Zoom 및 Uber용 PWA를 설치합니다. 또는 다른 PWA를 설치하려면 다음 단계로 건너뜁니다.

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="강제 설치된 웹앱 목록 입력" lightbox="images/hub-pwa-install-enable.png":::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. 또는 다음 구문에서 JSON 코드 조각을 만들어 다른 PWA를 설치할 수 있습니다.

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  } ]
    ```

4. 범위 태그 페이지에서 **다음** 을 선택하여 건너뜁니다.

5. [할당] 페이지의 **[포함된 그룹]** 아래에서 **[그룹 추가]** 를 선택합니다.

    :::image type="content" source="images/pwa-add-groups.png" alt-text="그룹 추가" lightbox="images/pwa-add-groups.png" :::

6. **포함할 그룹 선택**에서 대상으로 지정할 Surface Hub가 포함된 그룹의 이름을 입력하고 **선택을** 선택한 다음 **다음**을 클릭합니다. 그룹에 구성 프로필을 할당하는 방법에 대한 자세한 내용은 [그룹 추가를 참조하여 사용자 및 디바이스를 구성합니다](/mem/intune/fundamentals/groups-add).

    :::image type="content" source="images/pwa-select-groups.png" alt-text="그룹 선택" lightbox="images/pwa-select-groups.png":::

7. 검토한 다음 **만들기**를 선택합니다.

    :::image type="content" source="images/pwa-create-profile.png" alt-text="프로필 만들기" lightbox="images/pwa-create-profile.png" :::

8. 구성 프로필을 수정형으로 적용하려면 **DevicesAll** >  **디바이스**를 선택하고 대상으로 지정한 디바이스를 찾습니다. 개요 창을 열고 **동기화**를 선택합니다.

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="동기화 테넌트" lightbox="images/pwa-select-groups.png":::

 > [!IMPORTANT]
 > PWA 설치를 완료하려면 Surface Hub 이동하여 Edge를 시작합니다. PWA가 설치되어 시작 메뉴 모든 앱 목록에 표시됩니다.

 ### <a name="troubleshooting-intune-managed-pwas"></a>Intune 관리되는 PWA 문제 해결
 
**모든 앱**에 나열된 PWA가 표시되지 않는 경우:

- Surface Hub 최신 업데이트, 특히 [KB5011543](https://support.microsoft.com/help/5011543)(또는 후속 Windows 업데이트)이 있는지 확인합니다. 최신 Windows 10 Team 업데이트에 대한 자세한 내용은 [Surface Hub 업데이트 기록을](surface-hub-update-history.md) 참조하세요.
- 구성 프로필이 성공적으로 적용되었고 다른 설정과 충돌하지 않았는지 확인합니다. 
- 구성 프로필이 Surface Hub 포함된 보안 그룹을 대상으로 했는지 확인합니다. 
- Intune 관리되는 PWA를 성공적으로 설치하는 데 필요한 Surface Hub Edge를 한 번 시작해야 합니다.

## <a name="install-pwas-via-provisioning-package"></a>프로비저닝 패키지를 통해 PWA 설치

USB 드라이브를 사용하여 Surface Hubs에 프로비저닝 패키지를 적용하여 PWA를 설치할 수 있습니다. 자세한 내용은 [프로비저닝 패키지 만들기를 참조하세요](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>프로비저닝을 사용하여 시작

1. Windows 10 또는 Windows 11 실행되는 별도의 PC에서 Microsoft Store Windows WCD([구성 디자이너](https://www.microsoft.com/store/apps/9nblggh4tx22))를 설치합니다.

2. WCD에서 새 Project 만듭니다. **데스크톱 디바이스 프로비저닝을 선택하고,** 프로젝트의 이름을 입력하고, **마침**을 선택합니다.

3. **고급 편집기로 전환을** 선택하고 **예를** 선택하여 확인합니다.

### <a name="configure-msedgepolicy"></a>MSEdgePolicy 구성

1. WCD의 사용 가능한 사용자 지정 창에서 **\Runtime 설정\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**으로 이동합니다.

2. 사용자 지정 편집 창에서 앱 이름을 **MSEdgePolicy** 로 입력하고 **추가**를 선택합니다.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="앱 이름을 MSEdgePolicy로 입력" lightbox="images/pwa-add-edge-policy.png" :::

3. 사용 가능한 사용자 지정 창에서 **AppName: MSEdgePolicy** 를 선택하고 편집 창에서 **SettingType** 을 **정책** 으로 변경하고 **추가**를 선택합니다.

4. 사용 가능한 사용자 지정 창에서 **SettingType: Policy** 를 선택하고 편집 창에서 **AdmxFileUid** 를 **MSEdgePolicy** 로 설정하고 **추가**를 선택합니다.

5. 사용 가능한 사용자 지정 창에서 **AdmxFileUid: MSEdgePolicy** 를 선택하고 편집 창에서 다음 코드를 텍스트 한 줄로 입력하여 **MSEdgePolicy** 를 설정합니다.

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="MSEdgePolicy에 대한 코드 입력" lightbox="images/pwa-enter-edge-policy.png" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>강제 설치 Web Apps 정책 구성(프로비전 패키지)

1. WCD의 사용 가능한 사용자 지정 창에서 **\Runtime 설정\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**으로 이동합니다.

2. 사용자 지정 편집 창에서 Areaname을 **MSEdgePolicy~Policy~microsoft_edge** 입력하고 **추가**를 선택합니다.

3. 사용 가능한 사용자 지정 창에서 **AreaName: MSEdgePolicy~Policy~microsoft_edge** 선택하고 편집 창에서 **정책 이름을** **WebAppInstallForceList** 로 설정하고 **추가**를 선택합니다.

4. 사용 가능한 사용자 지정 창에서 **PolicyName: WebAppInstallForceList를 선택하고 WebAppInstallForceList** 편집 창 **** 에서 [PWA 코드를](#ppkg-code-samples) 텍스트 한 줄로 입력합니다.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="강제 설치 Web Apps 정책에 대한 코드 입력" lightbox="images/pwa-force-web-app-install.png":::

### <a name="ppkg-code-samples"></a>PPKG 코드 샘플

- YouTube PWA:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- YouTube, Webex, Zoom 및 Uber를 포함한 여러 PWA:

    ```xml
     <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.signin.webex.com/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://zoom.us/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.uber.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- 또는 다음 구문에서 JSON 코드 조각을 만들어 다른 PWA를 설치할 수 있습니다.

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.contoso.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>프로비저닝 패키지 내보내기 및 Surface Hub에 적용

1. 메뉴 모음에서 **내보내기를** 선택하고, **패키지 프로비저닝을** 선택하고, 프롬프트에 따라 .ppkg 파일을 생성합니다.

2. 빈 USB 플래시 드라이브를 삽입합니다. 출력 위치를 선택하여 패키지의 위치로 이동합니다. .ppkg 파일을 USB 드라이브에 복사합니다.

3. 설정 앱을 통해 또는 처음 실행하는 동안 프로비저닝 패키지를 적용합니다. 자세한 내용은 [프로비저닝 패키지 만들기를 참조하세요.](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

 ### <a name="troubleshooting-provisioning-package-pwas"></a>프로비저닝 패키지 PWA 문제 해결
 
**모든 앱**에 나열된 PWA가 표시되지 않는 경우:

- Surface Hub 최신 업데이트, 특히 [KB5011543](https://support.microsoft.com/help/5011543)(또는 후속 Windows 업데이트)이 있는지 확인합니다. 최신 Windows 10 Team 업데이트에 대한 자세한 내용은 [Surface Hub 업데이트 기록을](surface-hub-update-history.md) 참조하세요.

## <a name="learn-more"></a>세부 정보

- [WCD 참조: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [PWA(프로그레시브 Web Apps) 개요](/microsoft-edge/progressive-web-apps-chromium/)
