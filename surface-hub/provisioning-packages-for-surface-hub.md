---
title: 프로비전 패키지 만들기
description: Windows 10 또는 Windows 11 경우 프로비전 패키지를 사용하여 레지스트리 또는 CSP(구성 서비스 공급자)를 사용하는 설정을 구성할 수 있습니다.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 인증서 추가, 프로비저닝 패키지
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/20/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 1f1e084b8be0ab44c853fe003236ba7f25b4ff4c
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497641"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>Surface Hub용 프로비전 패키지 만들기

프로비전 패키지를 사용하면 주요 기능의 배포를 자동화하여 조직의 모든 Surface Hub에서 일관된 환경을 제공할 수 있습니다.  별도의 PC에서 Windows WCD(구성 디자이너)를 사용하여 다음 작업을 완료할 수 있습니다.

- Active Directory 또는 Azure Active Directory 등록
- 디바이스 관리자 계정 만들기
- 응용 프로그램 및 인증서 추가
- 프록시 설정 구성
- Surface Hub 구성 파일 추가
- [CSP(구성 서비스 공급자) 설정](/windows/client-management/mdm/surfacehub-csp) 구성

## <a name="overview"></a>개요

1. Windows 10 또는 Windows 11 실행되는 별도의 PC에서 [Microsoft Store Windows 구성 디자이너](https://www.microsoft.com/store/apps/9nblggh4tx22)를 설치합니다.
1. 마법사를 사용하여 일반 설정을 구성하려면 [**Surface Hub 디바이스 프로비저닝**](#use-surface-hub-provisioning-wizard)을 선택합니다. 또는 [고급 프로비저닝을](#use-advanced-provisioning) 선택하여 가능한 모든 설정을 보고 구성합니다.
1. 프로비전 패키지를 만들고 USB 드라이브에 저장합니다.
1. 처음 실행하는 동안 또는 설정 앱을 통해 Surface Hub 패키지를 배포합니다. 자세한 내용은 [프로비저닝 패키지 만들기를](/windows/configuration/provisioning-packages/provisioning-create-package) 참조하세요.

## <a name="use-surface-hub-provisioning-wizard"></a>Surface Hub 프로비저닝 마법사 사용

1. Windows 구성 디자이너를 열고 **Surface Hub 디바이스 프로비저닝**을 선택합니다.<br>
    ![Surface Hub 프로비저닝 마법사를 사용합니다.](images/sh-prov-start.png)
    
2. 프로젝트 이름을 지정하고 **다음**을 선택합니다.

### <a name="add-certificates"></a>인증서 추가

> [!div class="mx-imgBorder"]
> ![인증서를 추가합니다.](images/sh-prov-cert.png)

인증서를 사용하여 디바이스를 프로비전하려면 **인증서 추가를** 선택합니다. 인증서의 이름을 입력한 다음 사용할 인증서를 찾습니다.  고급 프로비저닝 옵션은 [패키지에 인증서 추가](#add-a-certificate-to-your-package) 아래 섹션을 참조하세요.

### <a name="configure-proxy-settings"></a>프록시 설정 구성

> [!div class="mx-imgBorder"]
> ![프록시 설정을 구성합니다.](images/sh-prov-proxy.png)

1. 프록시 설정에서 **예** 또는 **아니오**를 선택합니다. 기본적으로 Surface Hub 프록시 설정을 자동으로 검색합니다. 단, 기존에 프록시 서버가 요구되었다가 프록시 서버를 요구하지 않도록 변경된 인프라의 경우 프로비저닝 패키지를 사용하여 **예s**를 선택하고 **설정 자동 검색**을 선택하여 Surface Hub 장치를 기본 설정으로 되돌릴 수 있습니다.
2. **예를** 토글하는 경우 다음 중 하나를 입력하여 프록시 설정을 자동으로 검색하거나 설정을 수동으로 구성하도록 선택할 수 있습니다.

    - 설치 스크립트의 URL입니다.
    - 정적 프록시 서버 주소 및 포트 정보입니다.

3. 설치 스크립트 또는 프록시 서버를 사용하려는 경우 **자동으로 설정 검색**을 해제합니다. 설치 스크립트 *또는* 프록시 서버를 모두 사용할 수 없습니다.
4. 예외(Surface Hub 프록시 서버를 사용하지 않고 직접 연결해야 하는 주소)를 입력합니다. **예:** *.office365.com
5. 로컬 주소에 프록시 서버를 사용할지 여부를 식별합니다.

### <a name="set-up-device-admins"></a>디바이스 관리자 설정

 > [!div class="mx-imgBorder"]
 > ![Active Directory에 가입하거나, Azure AD, 로컬 관리자 계정을 만듭니다.](images/sh2-wcd.png)

Active Directory에 장치를 등록하고 설정 앱을 사용할 보안 그룹을 지정할 수 있으며 전역 관리자가 설정 앱을 사용할 수 있도록 Azure Active Directory에 등록하거나 장치에 로컬 관리자 계정을 만들 수 있습니다.

1. Active Directory에 장치를 등록하려면 권한이 가장 낮은 사용자 계정의 자격 증명을 입력하여 장치를 도메인에 추가하고 Surface Hub에서 관리자 자격 증명을 보유할 보안 그룹을 지정합니다. 다시 설정된 Surface Hub 패키지를 적용하는 경우 처음에 Surface Hub 설정한 동일한 계정인 경우 동일한 도메인 계정을 사용할 수 있습니다. 그렇지 않은 경우 프로비저닝 패키지에 다른 도메인의 계정을 사용해야 합니다.
2. Windows 구성 디자이너를 사용하여 대량 Azure AD 등록을 구성하기 전에 [Azure AD 조인 구현을 계획합니다](/azure/active-directory/devices/azureadjoin-plan). Azure AD 테넌트의 **사용자당 최대 장치 수**는 마법사에서 얻은 대량 토큰을 사용할 수 있는 횟수를 결정합니다.
3. Azure AD에 디바이스를 등록하려면 해당 옵션을 선택하고 마법사를 사용하여 가져올 대량 토큰의 이름을 입력합니다. 토큰의 만료 날짜를 설정합니다(토큰을 가져온 날로부터 최대 30일). **대량 토큰 가져오기를** 선택합니다. **로그인** 창에서 디바이스를 Azure AD에 가입할 권한이 있는 계정을 입력한 다음 암호를 입력합니다. **수락**을 선택하여 Windows 구성 디자이너에 필요한 권한을 부여합니다.
4. 로컬 관리자 계정을 만들려면 해당 옵션을 선택하고 사용자 이름 및 암호를 입력합니다.

> [!IMPORTANT]
> 프로비저닝 패키지에서 로컬 계정을 생성하는 경우 42일마다 **설정** 앱을 사용하여 암호를 변경해야 합니다. 기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.

### <a name="enroll-in-third-party-mdm-provider"></a>타사 MDM 공급자에 등록

> [!div class="mx-imgBorder"]
> ![타사 모바일 디바이스 관리에 등록합니다.](images/sh-prov-mdm.png)

타사 MDM(모바일 디바이스 관리) 공급자를 사용하는 경우 이 섹션을 사용하여 Surface Hub 등록할 수 있습니다. Intune 등록하려면 먼저 이전 섹션에 설명된 대로 Azure AD 조인을 설정하고 다음 Intune 설명서의 지침을 따릅니다. [빠른 시작: Windows 10/11 디바이스에 대한 자동 등록 설정](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

1. 타사 MDM의 등록에 대해 **예** 또는 **아니요** 를 토글합니다.
2. **예를** 토글하는 경우 디바이스를 등록하고 인증 유형을 지정할 권한이 있는 서비스 계정 및 암호 또는 인증서 지문을 제공합니다.
3. MDM 공급자가 요구하는 경우 검색 서비스, 등록 서비스 및 정책 서비스에 대한 URL을 입력합니다.

 자세한 내용은 [MDM 공급자를 사용하여 Surface Hub 관리를](manage-settings-with-mdm-for-surface-hub.md) 참조하세요.

### <a name="add-applications"></a>응용 프로그램 추가

> [!div class="mx-imgBorder"]
> ![애플리케이션을 추가합니다.](images/sh-prov-apps.png)

단일 프로비저닝 패키지로 다수의 UWP(유니버설 Windows 플랫폼)를 설치할 수 있습니다. 자세한 내용은 [앱을 사용하여 PC 프로비저닝](/windows/configuration/provisioning-packages/provision-pcs-with-apps)을 참조하세요.

> [!NOTE]
> Windows 구성 디자이너를 사용하면 프로비전 패키지에 클래식 Win32 앱을 추가할 수 있지만 Surface Hub UWP 앱만 허용합니다. 클래식 Win32 앱을 포함하면 프로비저닝을 수행할 수 없습니다.

### <a name="add-a-configuration-file"></a>구성 파일 추가

이 프로비저닝 패키지 외에도 Surface Hub 구성 파일을 사용하여 디바이스를 더욱 쉽게 설정할 수 있습니다. Surface Hub 구성 파일에는 무선 프로젝션의 "이름"뿐만 아니라 Exchange, Microsoft Teams 또는 비즈니스용 Skype 연결하기 위한 디바이스 계정 목록이 포함되어 있습니다.

**Surface Hub 구성 파일을 만들려면 다음을 수행합니다.**

1. Microsoft Excel(또는 다른 .csv 편집기)를 열고 _SurfaceHubConfiguration.csv.csv 파일을 _만듭니다.

2. 디바이스 계정 목록과 친숙한 이름을 다음 형식으로 입력합니다.

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > 구성 파일은 열 머리글을 포함하지 않아야 합니다. Surface Hub 적용된 프로비저닝 패키지에 포함된 경우 파일에서 디바이스의 계정 및 친숙한 이름을 선택할 수 있습니다. .csv 파일을 만들려면 UPN 주소 형식(rainier@contoso.com) 또는 하위 수준 로그온 이름 형식(contoso\rainier)을 사용합니다.

    rainier@contoso.com, 암호, 레이니어 Surface Hub

3. 파일을 프로젝트 폴더에 저장하고 프로비전 패키지를 사용하여 USB 키에 복사합니다.

> [!NOTE]
> 구성 파일은 첫 번째 실행 설정 중에만 적용할 수 있습니다.

### <a name="password-protect-provisioning-package"></a>암호 보호 프로비전 패키지

암호를 사용하도록 선택하는 경우 프로비전 패키지를 디바이스에 적용할 때마다 암호를 입력해야 합니다.

### <a name="complete-provisioning-wizard"></a>프로비전 완료 마법사

일반 설정만 구성해야 하는 경우 **FinishCreate** **** >  를 선택하고 [패키지 빌드](#build-your-package) 섹션으로 건너뜁니다. 또는 고급 프로비저닝으로 전환하여 설정을 계속 구성합니다.

## <a name="use-advanced-provisioning"></a>고급 프로비저닝 사용

> [!TIP]
> 마법사를 사용하여 일반 설정이 포함된 패키지를 만든 후 기타 설정을 추가하려면 고급 편집기로 전환합니다.<br><br> ![고급 편집기로 전환합니다.](images/icd-simple-edit.png)

1. 이전 섹션에서 계속 진행하는 경우 **고급 편집기로 전환을** 선택합니다. 그렇지 않으면 **Windows 구성 디자이너****를 열고 고급 프로비저닝을** 선택합니다.

   ![고급 프로비저닝을 사용합니다.](images/sh-prov-adv.png)

2. 프로젝트 이름을 지정하고 **다음**을 선택합니다.

3. **공통을 선택하여 Windows 10 Team** **다음**을 선택한 다음 **마침**을 선택합니다.

   ![WCD 새 프로젝트.](images/icd-new-project.png)

4. 프로젝트의 **사용 가능한 사용자 지정** 아래에서 **공통 팀 설정을** 선택합니다.

   :::image type="content" alt-text="WCD 일반 설정입니다." source="images/icd-common-settings.png":::

### <a name="add-a-certificate-to-your-package"></a>패키지에 인증서 추가

프로비저닝 패키지를 사용하여 디바이스가 Microsoft Exchange에 인증할 수 있는 인증서를 설치할 수 있습니다.

> [!NOTE]
> 프로비저닝 패키지를 사용할 경우 디바이스(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있고 사용자 저장소에는 설치할 수 없습니다. 조직에서 인증서를 사용자 저장소에 설치해야 하는 경우 Hub **설정** 앱인 **SecurityCertificatesImport** >  **인증서** **업데이트 &** >  사용합니다.
또는  [**MDM 정책을**](manage-settings-with-mdm-for-surface-hub.md) 사용하여 디바이스 저장소 또는 사용자 저장소에 인증서를 배포할 수 있습니다.

> [!TIP]
> **ClientCertificates** 섹션은 프라이빗 키가 있는 .pfx 파일에 대한 것입니다. 루트 CA에 대한 .cer 파일은 **RootCertificates** 섹션 및 **CACertificates** 섹션의 중간 CA에 배치되어야 합니다.

1. **Windows Configuration** **DesignerAvailable** >  사용자 지정에서 **런타임 설정** > **CertificatesClientCertificates** > 로 이동합니다.****
2. **CertificateName**에 대한 레이블을 입력한 다음 **추가**를 선택합니다.
3. **CertificatePassword**를 입력합니다.
4. **CertificatePath**의 경우 인증서를 찾아보고 선택합니다.
5. **ExportCertificate**를 **False**로 설정합니다.
6. **KeyLocation**의 경우 **소프트웨어만**을 선택합니다.

### <a name="add-a-uwp-app-to-your-package"></a>패키지에 UWP 앱 추가

프로비전 패키지에 UWP 앱을 추가하려면 앱 패키지(.appx 또는 .appxbundle 파일) 및 모든 종속성 파일이 필요합니다. 비즈니스용 Microsoft Store에서 앱을 구매한 경우 *인코드되지 않은* 앱 라이선스도 필요합니다. 비즈니스용 Microsoft Store에서 이러한 항목을 다운로드하는 방법에 대한 자세한 내용은 [오프라인 앱 배포](/microsoft-store/distribute-offline-apps)를 참조하세요.

**UWP 앱을 추가하려면 다음을 수행합니다.**

1. **사용 가능한 사용자 지정** 창에서 **런타임 설정** > **UniversalAppInstall** > **DeviceContextApp**으로 이동합니다.

2. 앱에 대한 **PackageFamilyName** 을 입력한 다음 **추가**를 선택합니다. 일관성을 위해 앱의 패키지 패밀리 이름을 사용합니다. 비즈니스용 Microsoft Store에서 앱을 구매한 경우 앱 라이선스에서 패키지 패밀리 이름을 찾을 수 있습니다. 텍스트 편집기를 사용하여 라이선스 파일을 열고 PFM 태그 사이의 값을 사용합니다.

3. **ApplicationFile**의 경우 **찾아보기를** 선택하여 대상 앱(.appx 또는 .appxbundle)을 찾아 선택합니다.

4. **DependencyAppxFiles의** 경우 **찾아보기를** 선택하여 앱에 대한 종속성을 찾아 추가합니다. Surface Hub에는 이러한 종속성의 64비트 버전만 필요합니다.

비즈니스용 Microsoft Store 앱을 획득한 경우 프로비전 패키지에 앱 라이선스를 추가해야 합니다.

**앱 라이선스를 추가하려면 다음을 수행합니다.**

1. 앱 라이선스의 복사본을 만들고 **.ms-windows-store-license** 확장명을 사용하도록 이름을 바꿉니다. 예를 들어 "example.xml"의 이름을 "example.ms-windows-store-license"로 바꿉니다.

2. Windows 구성 디자이너에서 **사용 가능한 customizationsRuntime** >  **설정** > **UniversalAppInstallDeviceContextAppLicense** > **로** 이동합니다.

3. **LicenseProductId**를 입력한 다음 **추가**를 선택합니다. 일관성을 위해 앱 라이선스에 있는 앱의 라이선스 ID를 사용합니다. 텍스트 편집기를 사용하여 라이선스 파일을 엽니다. 그런 다음 **라이선스** 태그에서 **LicenseID** 특성의 값을 사용합니다.

4. 새 **LicenseProductId** 노드를 선택합니다. **LicenseInstall의** 경우 **찾아보기를** 선택하여 이름이 바뀐 라이선스 파일(example.ms-windows-store-license)을 찾아 선택합니다.

### <a name="add-a-policy-to-your-package"></a>패키지에 정책 추가

Surface Hub에서는 [정책 구성 서비스 공급자](/windows/client-management/mdm/policy-configuration-service-provider)의 정책 하위 집합을 지원합니다. 이러한 정책 중 일부는 Windows 구성 디자이너를 사용하여 구성할 수 있습니다.

 **[CSP 정책을](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub) 추가하려면 다음을 수행합니다.**

1. **사용 가능한 customizationsRuntime** >  **settingsPolicies****** > 로 이동합니다.
2. 적절하게 관리하려는 구성 요소를 선택하고 정책 설정을 구성합니다. 예를 들어 직원이 Surface Hub InPrivate 웹 사이트를 검색하지 못하도록 하려면 **AllowInPrivate**를 선택한 다음 **사용 안 함을** 선택합니다.  

   :::image type="content" alt-text="정책 설정을 구성합니다." source="images/sh-prov-policies.png" lightbox="images/sh-prov-policies.png":::

### <a name="add-surface-hub-settings-to-your-package"></a>패키지에 Surface Hub 설정 추가

[SurfaceHub 구성 서비스 공급자](/windows/client-management/mdm/surfacehub-csp)의 설정을 프로비저닝 패키지에 추가할 수 있습니다.

1. **사용 가능한 customizationsCommon** >  **Team Edition 설정** 이동합니다.
1. 적절하게 관리하려는 구성 요소를 선택하고 정책 설정을 구성합니다.
1. 프로비전 패키지 구성이 완료되면 **FileSave****** > 를 선택합니다.
1. 프로젝트 파일에 중요한 정보가 포함될 수 있다는 경고를 읽고 **확인을** 선택합니다.

### <a name="build-your-package"></a>패키지 빌드

프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다.  프로젝트 파일을 안전한 위치에 저장하거나 더 이상 필요하지 않은 경우 삭제합니다.

1. **Windows Configuration** **DesignerExportProvisioning** >  >  **패키지를** 엽니다.

2. **소유자**를 **IT 관리자**로 변경합니다.  

3. **패키지 버전**에 대한 값을 설정하고 **다음**을 선택합니다.

   > [!TIP]
   > 소유자를 IT 관리자로 설정하면 패키지 설정이 적절한 "우선 순위 속성"을 유지하고 다른 프로비전 패키지가 이후에 다른 원본에서 적용되는 경우 Surface Hub 적용됩니다.

   > [!TIP]
   > 기존 패키지를 수정하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

4. 선택 사항: 패키지를 암호화하고 패키지 서명을 사용하도록 선택할 수 있습니다.

    1. **패키지 암호화**를 선택한 다음 암호를 입력합니다.
    1. **packageBrowse** >  **서명**을 선택하고 인증서를 적절하게 선택합니다.

    > [!IMPORTANT]
    > 프로비전 패키지에 신뢰할 수 있는 프로비저닝 인증서를 포함하는 것이 좋습니다. 패키지가 디바이스에 적용되면 인증서가 시스템 저장소에 추가되어 후속 패키지를 자동으로 적용할 수 있습니다.

5. **다음**을 선택하여 출력 위치를 지정합니다. 기본적으로 Windows 구성 디자이너는 프로젝트 폴더를 출력 위치로 사용합니다. 또는 **찾아보기를** 선택하여 기본 출력 위치를 변경합니다. **다음**을 선택합니다.

6. **빌드**를 선택하여 패키지 빌드를 시작합니다. 프로젝트 정보가 빌드 페이지에 표시됩니다.

7. 빌드에 실패하면 프로젝트 폴더에 대한 링크와 함께 오류 메시지가 나타납니다. 로그를 검토하여 오류를 진단하고 패키지를 다시 빌드해 보세요.

8. 빌드에 성공하면 프로비전 패키지, 출력 디렉터리 및 프로젝트 디렉터리의 이름이 표시됩니다. **마침**을 선택하여 마법사를 닫고 사용자 지정 페이지로 돌아갑니다.

9. **출력 위치를** 선택하여 패키지의 위치로 이동합니다. .ppkg를 빈 USB 플래시 드라이브에 복사합니다.

## <a name="apply-a-provisioning-package-to-surface-hub"></a>Surface Hub에 프로비저닝 패키지 적용

프로비저닝 패키지를 Surface Hub 배포하는 방법에는 두 가지가 있습니다.

- [먼저 설치 프로그램을 실행합니다.](#apply-a-provisioning-package-during-first-run) 프로비전 패키지를 적용하여 Wi-Fi 설정, 프록시 설정, 디바이스 계정 세부 정보, Azure AD 조인 및 관련 설정을 비롯한 여러 옵션을 사용자 지정할 수 있습니다.  
- [설정 앱.](#apply-a-provisioning-package-using-settings-app) 처음 설치 프로그램을 실행한 후에는 설정 앱을 통해 프로비저닝 패키지를 적용할 수 있습니다. 

### <a name="apply-a-provisioning-package-during-first-run"></a>첫 실행 중에 프로비저닝 패키지 적용

1. 처음으로 Surface Hub 켜면 첫 실행 프로그램이 [**Hi there 페이지를**](first-run-program-surface-hub.md) 표시합니다. 계속하기 전에 설정이 제대로 구성되었는지 확인합니다.

2. .ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다. 패키지가 드라이브의 루트 디렉터리에 있으면 첫 실행 프로그램이 이를 인식하고 디바이스를 설정할지 묻는 메시지를 표시합니다. **설정**을 선택합니다.

3. 다음 화면에서 프로비전 소스를 선택하라는 메시지가 표시됩니다. **이동식 미디어** 탭을 선택하고 **다음**을 탭합니다.

4. 적용할 프로비저닝 패키지(*.ppkg)를 선택하고 다음을 탭 **합니다**. 첫 실행  중에는 패키지 한 개만 설치할 수 있습니다.

5. 첫 실행 프로그램은 프로비저닝 패키지가 적용될 변경 내용의 요약을 보여 줍니다. **예, 추가**를 선택합니다.

6. 구성 파일이 USB 플래시 드라이브의 루트 디렉터리에 저장된 경우 **구성 선택** 옵션이 표시됩니다. 구성 파일의 첫 장치 계정과 Surface Hub에 적용될 해당 계정의 정보 요약이 함께 표시됩니다.

7. **구성 선택**에서 적용할 디바이스 이름을 선택한 다음, **다음**을 선택합니다.

프로비저닝 패키지의 설정이 장치에 적용되고 OOBE 작업이 완료됩니다. 장치를 다시 시작하면 USB 플래시 드라이브를 제거할 수 있습니다.

### <a name="apply-a-provisioning-package-using-settings-app"></a>설정 앱을 사용하여 프로비저닝 패키지 적용

1. .ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다.
2. Surface Hub **설정** 시작하고 메시지가 표시되면 관리자 자격 증명을 입력합니다.
3. **Surface Hub** > **장치 관리**로 이동합니다. **프로비저닝 패키지에서 프로비전 패키지** >  **추가 또는 제거**를 **선택합니다.**
4. 프로비저닝 패키지를 선택하고 **추가**를 선택합니다.  메시지가 표시되면 관리자 자격 증명을 다시 입력합니다.
5. 적용할 변경 내용에 대한 요약이 표시됩니다. **예, 추가**를 선택합니다.

## <a name="learn-more"></a>세부 정보

- [Windows 구성 디자이너 다운로드](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [프로비저닝 패키지 만들기](/windows/configuration/provisioning-packages/provisioning-create-package)
- [MDM 공급자를 사용하여 Surface Hub 관리](manage-settings-with-mdm-for-surface-hub.md)
