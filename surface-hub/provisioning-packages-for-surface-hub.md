---
title: 프로비저닝 패키지 만들기(Surface Hub)
description: Windows 10의 경우 프로비저닝 패키지를 통해 레지스트리 또는 CSP(콘텐츠 서비스 제공자)를 사용하는 설정을 구성할 수 있습니다.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: 인증서 추가, 프로비저닝 패키지
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: 5e0714d284cc5c8207633719ec8fb52cec9f95cb
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576988"
---
# <a name="create-provisioning-packages-surface-hub"></a>프로비저닝 패키지 만들기(Surface Hub)

이 항목에서는 Windows 구성 디자이너를 사용하여 프로비저닝 패키지를 만들고 Surface Hub 디바이스에 적용하는 방법을 설명합니다. Surface Hub의 경우 프로비저닝 패키지를 사용하여 인증서를 추가하고 UWP(유니버설 Windows 플랫폼) 앱을 설치하고 정책과 설정을 사용자 지정할 수 있습니다.

첫 실행 설정 중에 USB 메모리를 사용하거나 **설정** 앱을 통해 프로비저닝 패키지를 적용할 수 있습니다. 


## <a name="advantages"></a>장점
-   MDM(모바일 장치 관리) 제공자를 사용하지 않고 빠르게 장치를 구성합니다.

-   네트워크 연결이 필요하지 않습니다.

-   적용이 간단합니다.

[프로비저닝 패키지의 이점 및 사용에 대해 자세히 알아봅니다.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## <a name="requirements"></a>요구 사항 

프로비저닝 패키지를 만들고 Surface Hub에 적용하려면 다음이 필요합니다.

-   Windows 구성 디자이너는 Microsoft Store 또는 Windows 10 ADK(Assessment and Deployment Kit)을 통해 설치할 수 있습니다. [Windows 구성 디자이너를 설치하는 방법을 알아보세요.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   USB 메모리.
-   **설정** 앱을 사용하여 패키지를 적용할 경우 디바이스 관리자 자격 증명이 필요합니다.

Windows 10을 실행하는 PC에서 프로비저닝 패키지를 만들고 해당 패키지를 USB 드라이브에 저장한 다음 Surface Hub에 배포합니다.


## <a name="supported-items-for-surface-hub-provisioning-packages"></a>Surface Hub 프로비저닝 패키지의 지원되는 항목

**Surface Hub 장치 프로비전** 마법사를 사용하여 다음을 수행할 수 있습니다.

- Active Directory, Azure Active Directory 또는 MDM 등록 
- 장치 관리자 계정 만들기 
- 응용 프로그램 및 인증서 추가
- 프록시 설정 구성
- Surface Hub 구성 파일 추가

>[!WARNING]
>마법사를 사용하여 Windows 10에서 Windows 구성 디자이너를 실행해 Azure Active Directory 등록을 구성해야 합니다.

고급 프로비저닝 편집기를 사용하면 Surface Hub에서 프로비저닝 패키지에 다음 항목을 추가할 수 있습니다.

- **정책** - Surface Hub에서는 [정책 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies)의 정책 하위 집합을 지원합니다. 
- **설정** - [SurfaceHub 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)에서 설정을 구성할 수 있습니다.

>[!TIP]
> 마법사를 사용하여 일반 설정이 포함된 패키지를 만든 후 기타 설정을 추가하려면 고급 편집기로 전환합니다.
>
>![고급 편집기 열기](images/icd-simple-edit.png)

## <a name="use-the-surface-hub-provisioning-wizard"></a>Surface Hub 프로비저닝 마법사 사용

[Windows 구성 디자이너를 설치](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)한 다음 이를 사용해 프로비저닝 패키지를 만들 수 있습니다.

### <a name="create-the-provisioning-package"></a>프로비전 패키지 만들기 

1. Windows 구성 디자이너 열기:
   - 시작 화면 또는 시작 메뉴 검색에서 'Windows 구성 디자이너'를 입력하고 Windows 구성 디자이너 바로 가기를 클릭합니다. 
    
     또는
    
   - ADK에서 Windows 구성 디자이너를 설치한 경우 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`(x64 컴퓨터) 또는 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`(x86 컴퓨터)로 이동하여 **ICD.exe**를 두 번 클릭합니다.

2. **Surface Hub 장치 프로비전**을 클릭합니다.

3. 프로젝트 이름을 지정하고 **다음**을 클릭합니다.

### <a name="configure-settings"></a>설정 구성

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>인증서를 사용하여 디바이스를 프로비전하려면 <strong>인증서 추가</strong>를 클릭합니다. 인증서 이름을 입력하고 사용할 인증서를 찾아서 선택합니다.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>프록시 설정에서 <strong>예</strong> 또는 <strong>아니오</strong>를 선택합니다. Surface Hub 기본 구성은 자동으로 프록시 설정을 검색하도록 설정되어 있습니다. 이를 원하지 않는 경우 <strong>아니오</strong>를 선택해야 합니다. 단, 기존에 프록시 서버가 요구되었다가 프록시 서버를 요구하지 않도록 변경된 인프라의 경우 프로비저닝 패키지를 사용하여 <strong>예s</strong>를 선택하고 <strong>설정 자동 검색</strong>을 선택하여 Surface Hub 장치를 기본 설정으로 되돌릴 수 있습니다. </br></br><strong>예</strong>를 선택하면 자동으로 프록시 설정을 검색하거나 초기 설정 스크립트에 URL 또는 고정 프록시 서버 주소를 입력해 수동으로 설정을 구성할 수 있습니다. 또한 로컬 주소에 프록시 서버를 사용할지 여부를 선택하고 제외(Surface Hub에서 프록시 서버 없이 직접 연결해야 하는 주소)를 입력할 수 있습니다.  </td><td><img src="images/proxy-details.png" alt="proxy configuration details"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Active Directory에 장치를 등록하고 설정 앱을 사용할 보안 그룹을 지정할 수 있으며 전역 관리자가 설정 앱을 사용할 수 있도록 Azure Active Directory에 등록하거나 장치에 로컬 관리자 계정을 만들 수 있습니다.</br></br>Active Directory에 장치를 등록하려면 권한이 가장 낮은 사용자 계정의 자격 증명을 입력하여 장치를 도메인에 추가하고 Surface Hub에서 관리자 자격 증명을 보유할 보안 그룹을 지정합니다. Active Directory에 장치를 등록한 프로비저닝 패키지를 초기화된 Surface Hub에 적용하는 경우, 동일한 도메인 계정을 사용하려면 해당 계정이 도메인 관리자로 등록되어 있거나 최초로 Surface Hub을 설정할 때 사용했던 계정이어야 합니다. 그렇지 않은 경우 프로비저닝 패키지에 다른 도메인의 계정을 사용해야 합니다.</br></br>Windows 구성 디자이너 마법사를 사용하여 대량 Azure AD 등록을 구성하려면 먼저 <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">조직에서 Azure AD 가입을 설정</a>합니다. Azure AD 테넌트의 <strong>사용자당 최대 장치 수</strong>는 마법사에서 얻은 대량 토큰을 사용할 수 있는 횟수를 결정합니다. Azure AD에 디바이스를 등록하려면 해당 옵션을 선택하고 마법사를 사용하여 가져올 대량 토큰의 이름을 입력합니다. 토큰의 만료 날짜를 설정합니다(토큰을 가져온 날로부터 최대 30일). <strong>대량 토큰 가져오기</strong>를 클릭합니다. Let <strong>&#39;s get you signed in(로그인할 수 있습니다.) 창에서 디바이스를 Azure AD에 가입할 수 있는 권한이 있는 계정을 입력한 다음 암호를 </strong> 입력합니다. <strong>수락</strong>을 클릭하여 Windows 구성 디자이너에 필요한 권한을 부여합니다.</br></br>로컬 관리자 계정을 만들려면 해당 옵션을 선택하고 사용자 이름 및 암호를 입력합니다. </br></br><strong>중요:</strong> 프로비전 패키지에서 로컬 계정을 생성하는 경우 42일마다 <strong>설정</strong> 앱을 사용하여 암호를 변경해야 합니다. 기간 내에 암호를 변경하지 않는 경우 계정이 잠겨 로그인하지 못하게 될 수 있습니다.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>이 섹션을 사용하여 Intune 외에 MDM 공급자에 등록합니다. Intune 등록의 경우 이전 섹션에서 자동 Intune 등록으로 Azure AD <a href="https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment" data-raw-source="[automatic Intune enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)"> 가입을 </a> 사용하세요.</br></br>MDM 등록 설정에서 <strong>예</strong> 또는 <strong>아니오</strong>를 선택합니다. </br></br><strong>예</strong>를 선택한 경우 장치 등록에 사용할 수 있는 승인된 서비스 계정과 암호 또는 인증서 손도장을 제공해야 하며, 인증 유형 또한 지정해야 합니다. 또한 MDM 제공자가 요구하는 경우 검색 서비스, 등록 서비스, 정책 서비스의 URL을 함께 입력해야 합니다. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">MDM을 사용한 Surface Hub 관리에 대해 자세히 알아보세요.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>단일 프로비저닝 패키지로 다수의 UWP(유니버설 Windows 플랫폼)를 설치할 수 있습니다. 설정에 대한 도움말은 <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">앱을 사용하여 PC 프로비전</a>을 참조하세요. </br></br><strong>중요: 마법사 인터페이스에서 클래식 Win32 앱을 선택할 수 있습니다. 그러나 프로비저닝 패키지에 적용될 UWP 앱만 </strong> Surface Hub. 클래식 Win32 앱을 포함하면 프로비저닝을 수행할 수 없습니다. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>이&#39;설정을 구성하지 않습니다. 장치 계정 목록을 포함된 구성 파일을 비롯한 지침을 제공하빈다. 구성 파일은 열 머리글을 포함하지 않아야 합니다. 프로비저닝 패키지를 Surface Hub에 적용할 때 Surface Hub 구성 파일이 USB 드라이브에 포함된 경우, 파일에서 장치에 사용할 계정과 식별 이름을 선택할 수 있습니다. 예시는 <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">샘플 구성 파일</a>을 확인하세요.</br></br><strong>중요: 구성 파일은 OOBE(첫 실행 설치 환경)에만 적용할 수 있으며 Windows 버전 1703과 함께 릴리스된 Windows 구성 디자이너를 사용하여 만든 프로비저닝 패키지에만 사용할 수 Windows 10 </strong> 있습니다.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish creating your package"/></br></br>프로비전 패키지를 보호하기 위한 암호를 설정할 수 있습니다. 디바이스에 프로비전 패키지를 적용할 때 이 암호를 입력해야 합니다.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

작업을 마쳤으면 **만들기**를 클릭합니다. 몇 초 정도 걸립니다. 패키지가 빌드되면 패키지가 저장된 위치가 페이지 맨 위에 하이퍼링크로 표시됩니다.

## <a name="sample-configuration-file"></a>샘플 구성 파일

Surface Hub 구성 파일에는 장치에서 Exchange 및 비즈니스용 Skype에 연결할 때 사용할 수 있는 계정 목록을 포함되어 있습니다. Surface Hub에 프로비저닝 패키지를 적용할 때 USB 플래시 드라이브의 루트 디렉터리에 구성 파일을 저장한 다음 장치에 적용할 계정을 선택할 수 있습니다. 구성 파일은 OOBE(최초 설정)에만 적용되며 Windows 10 버전 1703과 함께 릴리스된 Windows 구성 디자이너를 사용해 만든 프로비저닝 패키지만 사용할 수 있습니다.

Microsoft Excel 또는 다른 CSV 편집 소프트웨어를 사용해 파일명이 `SurfaceHubConfiguration.csv`인 CSV 파일을 만듭니다. 파일 안에 다음 형식으로 장치 계정 및 식별 이름 목록을 입력합니다.

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>구성 파일에서는 장치 계정의 암호가 일반 텍스트로 저장되기 때문에 프로비저닝 패키지를 장치에 적용한 후 암호를 업데이트하는 것이 좋습니다. [Surface Hub CSP(구성 서비스 제공자)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp)의 [DeviceAccount 노드](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount)를 사용해 MDM에서 암호를 업데이트할 수 있습니다.


다음은 `SurfaceHubConfiguration.csv`를 사용한 예시입니다. 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## <a name="use-advanced-provisioning"></a>고급 프로비저닝 사용

[Windows 구성 디자이너를 설치](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)한 다음 이를 사용해 프로비저닝 패키지를 만들 수 있습니다.

### <a name="create-the-provisioning-package-advanced"></a>프로비저닝 패키지 만들기(고급)

1. Windows 구성 디자이너 열기:
   - 시작 화면 또는 시작 메뉴 검색에서 'Windows 구성 디자이너'를 입력하고 Windows 구성 디자이너 바로 가기를 클릭합니다. 
    
     또는
    
   - ADK에서 Windows 구성 디자이너를 설치한 경우 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86`(x64 컴퓨터) 또는 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe`(x86 컴퓨터)로 이동하여 **ICD.exe**를 두 번 클릭합니다.

2. **Advanced provisioning**(고급 프로비전)을 클릭합니다.
   
3. 프로젝트 이름을 지정하고 **다음**을 클릭합니다.

4. 일반을 **선택하여 Windows 10 Team**를 **클릭하고**마친 을 **클릭합니다.**

    ![ICD 새 프로젝트](images/icd-new-project.png)

5. 프로젝트의 사용 **가능한 사용자 지정에서**공통 팀 **설정을 선택합니다.**

    ![ICD 공통 설정](images/icd-common-settings.png)


### <a name="add-a-certificate-to-your-package"></a>패키지에 인증서 추가
프로비저닝 패키지를 사용하여 디바이스가 Microsoft Exchange에 인증할 수 있는 인증서를 설치할 수 있습니다.

> [!NOTE]
> 프로비저닝 패키지를 사용할 경우 디바이스(로컬 컴퓨터) 저장소에만 인증서를 설치할 수 있고 사용자 저장소에는 설치할 수 없습니다. 조직에서 사용자 저장소에 인증서를 설치해야 하는 경우 **** 허브 & 앱의 업데이트 & 인증서 가져오기 단추를 사용하여 인증서를 설정 ****  >  **** 있습니다. **** 또는 [MDM(모바일](manage-settings-with-mdm-for-surface-hub.md) 장치 관리) 정책을 사용하여 장치 저장소 또는 사용자 저장소에 인증서를 배포할 수 있습니다.

1. **사용 가능한 사용자 지정** 창에서 **런타임 설정** > **인증서** > **ClientCertificates**로 이동합니다.
   > [!NOTE]
   > **ClientCertificates** 섹션은 개인 키가 있는 .pfx 파일용입니다. 루트 CA에 대한 .cer 파일은 **RootCertificates** 섹션에 배치하고 **CACertificates** 섹션의 중간 CA에 배치해야 합니다.

2. **CertificateName에 대한 레이블을 입력한** 다음 추가를 **클릭합니다.** 

2. **CertificatePassword**를 입력합니다. 

3. **CertificatePath**의 경우 인증서를 찾아보고 선택합니다. 

4. **ExportCertificate**를 **False**로 설정합니다.

5. **KeyLocation**의 경우 **소프트웨어만**을 선택합니다.


### <a name="add-a-universal-windows-platform-uwp-app-to-your-package"></a>패키지에 UWP(유니버설 Windows 플랫폼) 앱 추가
UWP 앱을 프로비저닝 패키지에 추가하기 전에 앱 패키지(.appx 또는 .appxbundle)와 임의 종속성 파일이 필요합니다. 비즈니스용 Microsoft Store에서 앱을 구매한 경우 *인코드되지 않은* 앱 라이선스도 필요합니다. 비즈니스용 Microsoft Store에서 이러한 항목을 다운로드하는 방법에 대한 자세한 내용은 [오프라인 앱 배포](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)를 참조하세요.

1. **사용 가능한 사용자 지정** 창에서 **런타임 설정** > **UniversalAppInstall** > **DeviceContextApp**으로 이동합니다.

2. 앱의 **PackageFamilyName**을 입력하고 **추가**를 클릭합니다. 일관성을 위해 앱의 패키지 패밀리 이름을 사용합니다. 비즈니스용 Microsoft Store에서 앱을 구매한 경우 앱 라이선스에서 패키지 패밀리 이름을 찾을 수 있습니다. 텍스트 편집기를 사용하여 라이선스 파일을 열고 ... 태그 사이의 \<PFM\> 값을 \</PFM\> 사용 합니다.

3. **ApplicationFile**의 경우 **찾아보기**를 클릭하여 대상 앱(\*.appx 또는 \*.appxbundle)을 선택합니다.

4. **DependencyAppxFiles**의 경우 **찾아보기**를 클릭하여 앱에 대한 종속성을 추가합니다. Surface Hub에는 이러한 종속성의 64비트 버전만 필요합니다.

비즈니스용 Microsoft Store에서 앱을 구매한 경우 앱 라이선스를 프로비저닝 패키지에도 추가해야 합니다.

1. 앱 라이선스의 복사본을 만들고 **.ms-windows-store-license** 확장명을 사용하도록 이름을 바꿉니다. 예를 들면 "example.xml" becomes "example.ms-windows-store-license"입니다.

2. ICD의 **사용 가능한 사용자 지정** 창에서 **런타임 설정** > **UniversalAppInstall** > **DeviceContextAppLicense**로 이동합니다.

3. **LicenseProductId**를 입력한 후 **추가**를 클릭합니다. 일관성을 위해 앱 라이선스에 있는 앱의 라이선스 ID를 사용합니다. 텍스트 편집기를 사용하여 라이선스 파일을 엽니다. 그런 다음 \<License\> 태그에서 **LicenseID** 특성의 값을 사용 합니다.

4. 새 **LicenseProductId** 노드를 선택합니다. **LicenseInstall**의 경우 **찾아보기**를 클릭하여 1단계에서 이름을 바꾼 라이선스 파일을 찾고 선택합니다.


### <a name="add-a-policy-to-your-package"></a>패키지에 정책 추가
Surface Hub에서는 [정책 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)의 정책 하위 집합을 지원합니다. 해당 정책 중 일부는 ICD를 사용하여 구성할 수 있습니다.

1. **사용 가능한 사용자 지정** 창에서 **런타임 설정** > **Policies**로 이동합니다.

2. 사용 가능한 정책 영역 중 하나를 선택합니다.

3. 프로비저닝 패키지에 추가할 정책을 선택하고 설정합니다.


### <a name="add-surface-hub-settings-to-your-package"></a>패키지에 Surface Hub 설정 추가 

[SurfaceHub 구성 서비스 공급자](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)의 설정을 프로비저닝 패키지에 추가할 수 있습니다. 

1. 사용 가능한 사용자 지정 **창에서** **런타임**설정  >  **SurfaceHub로 이동합니다.**

2. 사용 가능한 설정 영역 중 하나를 선택합니다.

3. 프로비저닝 패키지에 추가할 설정을 선택하고 설정합니다. 


## <a name="build-your-package"></a>패키지 빌드

1. 프로비저닝 패키지 구성을 완료한 경우 **파일** 메뉴에서 **저장**을 클릭합니다.

2. 프로젝트 파일에 중요한 정보가 포함될 수 있다는 경고를 읽고 **확인**을 클릭합니다.

    > [!IMPORTANT]
    > 프로비저닝 패키지를 빌드할 때 프로젝트 파일 및 프로비저닝 패키지(.ppkg) 파일에 중요한 정보를 포함할 수 있습니다. .ppkg 파일을 암호화하는 옵션이 있지만 프로젝트 파일은 암호화되지 않습니다. 안전한 장소에 프로젝트 파일을 저장하고 더 이상 필요하지 않은 경우에는 프로젝트 파일을 삭제해야 합니다.

3. **내보내기** 메뉴에서 **프로비저닝 패키지**를 클릭합니다.

4. **소유자**를 **IT 관리자**로 변경합니다. 이렇게 하면 이 프로비저닝 패키지의 우선 순위가 다른 소스에서 이 디바이스에 적용된 프로비저닝 패키지보다 더 높게 설정됩니다.

5. **패키지 버전**에 대한 값을 설정하고 **다음**을 선택합니다.

    > [!TIP]
    > 기존 패키지에 변경 내용을 적용하고 버전 번호를 변경하여 이전에 적용된 패키지를 업데이트할 수 있습니다.

6. 선택 사항: 패키지 암호화 및 패키지 서명 사용을 선택할 수 있습니다.

    -   **패키지 암호화 사용** - 이 옵션을 선택하는 경우 자동 생성된 암호가 화면에 표시됩니다.

    -   **패키지 서명 사용** - 이 옵션을 선택하는 경우 패키지 서명에 사용할 유효한 인증서를 선택해야 합니다. **찾아보기...** 를 클릭하고 패키지에 서명하는 데 사용할 인증서를 선택하여 인증서를 지정합니다.

        > [!IMPORTANT]
        > 프로비저닝 패키지에 신뢰할 수 있는 프로비저닝 인증서를 포함하는 것이 좋습니다. 패키지를 장치에 적용하면 인증서가 시스템 저장소에 추가되고 그 후에 해당 인증서로 서명된 모든 패키지는 자동으로 적용할 수 있습니다. 

7. **다음**을 클릭하여 빌드가 끝난 프로비저닝 패키지를 저장할 출력 위치를 지정합니다. 기본적으로 Windows ICD에서는 프로젝트 폴더를 출력 위치로 사용합니다.<p>
필요한 경우 **찾아보기**를 클릭하여 기본 출력 위치를 변경할 수 있습니다.

8. **다음**을 클릭합니다.

9. 패키지 빌드를 시작하려면 **빌드**를 클릭합니다. 빌드 페이지에서 프로젝트 정보가 표시되며 진행률 표시줄은 빌드 상태를 나타냅니다.<p>
빌드를 취소해야 하는 경우 **취소**를 클릭합니다. 이렇게 하면 현재 빌드 프로세스를 취소하며 마법사를 닫고 **사용자 지정 페이지**를 다시 가져옵니다.

10. 빌드에 실패하면 프로젝트 폴더에 대한 링크가 포함된 오류 메시지가 표시됩니다. 오류 원인을 파악하기 위해 로그를 스캔할 수 있습니다. 문제를 해결 한 후에 패키지를 다시 빌드 해보세요.<p>
빌드가 성공한 경우 프로비저닝 패키지, 출력 디렉터리 및 프로젝트 디렉터리의 이름이 표시됩니다.

    -   원하는 경우 프로비저닝 패키지를 다시 빌드하고 출력 패키지 경로를 다르게 선택할 수 있습니다. 이렇게 하려면 **뒤로**를 클릭해서 출력 패키지 이름과 경로를 바꾼 다음 **다음**을 클릭해 다른 빌드를 시작합니다.
    
    -   완료되면 **마침**을 클릭해 마법사를 닫고 다시 **사용자 지정 페이지**로 이동합니다.

11. **출력 위치** 링크를 선택하여 패키지 위치로 이동합니다. .ppkg를 빈 USB 플래시 드라이브에 복사합니다.


## <a name="apply-a-provisioning-package-to-surface-hub"></a>Surface Hub에 프로비저닝 패키지 적용

Surface Hub에 프로비저닝 패키지를 배포할 수 있는 두 가지 옵션이 있습니다. 첫 [실행](#apply-a-provisioning-package-during-first-run)마법사 에서 인증서를 설치하는 프로비저닝 패키지를 적용할 수 있습니다. 또는 첫 실행 프로그램이 완료된 후 를 사용하여 설정, 앱 및 인증서를 구성하는 프로비저닝 [패키지를 적용할 설정.](#apply-a-package-using-settings) 


### <a name="apply-a-provisioning-package-during-first-run"></a>첫 실행 중에 프로비저닝 패키지 적용

> [!IMPORTANT]
> 첫 실행 프로그램에서는 프로비저닝 패키지를 사용하여 인증서를 설치할 수만 있습니다. **설정** 앱을 사용하여 앱을 설치하고 다른 설정을 적용할 수 있습니다.

1. 처음으로 Surface Hub를 켜면 첫 실행 프로그램에서 [**안녕하세요 페이지**](first-run-program-surface-hub.md#first-page)를 표시합니다. 계속하기 전에 설정이 제대로 구성되었는지 확인합니다.

2. .ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다. 패키지가 드라이브의 루트 디렉터리에 있으면 첫 실행 프로그램이 이를 인식하고 디바이스를 설정할지 묻는 메시지를 표시합니다. **설정**을 선택합니다.

    ![디바이스를 설정하시겠습니까?](images/provisioningpackageoobe-01.png)

3. 다음 화면에서 프로비전 소스를 선택하라는 메시지가 표시됩니다. **이동식 미디어** 탭을 선택하고 **다음**을 탭합니다.

    ![이 디바이스를 프로비전](images/provisioningpackageoobe-02.png)
    
4. 적용할 프로비저닝 패키지(\*.ppkg)를 선택하고 **다음**을 탭합니다. 첫 실행  중에는 패키지 한 개만 설치할 수 있습니다.

    ![패키지 선택](images/provisioningpackageoobe-03.png)

5. 첫 실행 프로그램은 프로비저닝 패키지가 적용될 변경 내용의 요약을 보여 줍니다. **예, 추가**를 선택합니다.  

    ![이 패키지를 신뢰할 수 있습니까?](images/provisioningpackageoobe-04.png)
    
6. 구성 파일이 USB 플래시 드라이브의 루트 디렉터리에 저장된 경우 **구성 선택** 옵션이 표시됩니다. 구성 파일의 첫 장치 계정과 Surface Hub에 적용될 해당 계정의 정보 요약이 함께 표시됩니다.

    ![구성 선택](images/ppkg-config.png)    

7. **구성 선택**에서 적용할 장치 이름을 선택하고 **다음**을 클릭합니다.

    ![장치 식별 이름 선택](images/ppkg-csv.png)
    
프로비저닝 패키지의 설정이 장치에 적용되고 OOBE 작업이 완료됩니다. 장치를 다시 시작하면 USB 플래시 드라이브를 제거할 수 있습니다.

### <a name="apply-a-package-using-settings"></a>설정을 사용하여 패키지 적용

1. .ppkg 파일이 포함된 USB 플래시 드라이브를 Surface Hub에 넣습니다.

2. Surface Hub에서 **설정**을 시작하고 메시지가 표시되면 관리자 자격 증명을 입력합니다.

3. **Surface Hub** > **장치 관리**로 이동합니다. **프로비저닝 패키지**에서 **프로비저닝 패키지 추가 또는 제거**를 선택합니다.

4. **패키지 추가**를 선택합니다.

5. 프로비저닝 패키지를 선택하고 **추가**를 선택합니다. 메시지가 표시되면 관리자 자격 증명을 다시 입력해야 할 수 있습니다.

6. 프로비저닝 패키지가 적용될 변경 내용의 요약이 표시됩니다. **예, 추가**를 선택합니다.


