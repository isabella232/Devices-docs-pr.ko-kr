---
title: Surface Hub에서 전역이 아닌 관리자 계정 구성
description: 이 문서에서는 전역이 아닌 관리자 계정을 구성하여 Surface Hub 및 Surface Hub 2S를 관리하는 방법을 설명합니다.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: be6a6c75155b3c45ae9dda9dd2726033411100c4
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497703"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Surface Hub에서 전역이 아닌 관리자 계정 구성

Windows 10 Team 2020 업데이트는 Azure AD 도메인에 가입된 Surface Hub 디바이스에서 설정 앱의 관리 권한을 제한하는 비 전역 관리자 계정을 구성하는 지원을 추가합니다. 이렇게 하면 Surface Hub 대한 관리자 권한의 범위만 지정하고 전체 Azure AD 도메인에서 원치 않는 관리자 액세스를 방지할 수 있습니다. 시작하기 전에 Surface Hub Azure AD 조인되어 있는지 확인하고 자동 등록을 Intune. 그렇지 않은 경우 Surface Hub 다시 설정하고 처음 OOBE(기본 제공) 설치 프로그램을 완료하고 Azure AD 조인 옵션을 선택해야 합니다.

Windows 10 Team 2020 업데이트 2는 [LocalUsersAndGroups 구성 서비스 공급자](/windows/client-management/mdm/policy-csp-localusersandgroups)에 대한 지원을 추가합니다. 이렇게 하면 사용 가능한 상태로 유지되지만 더 이상 권장되지 않는 [RestrictedGroups CSP](/windows/client-management/mdm/policy-csp-restrictedgroups)가 아래 설명된 대로 대체됩니다.

## <a name="summary"></a>요약

전역이 아닌 관리자 계정을 만드는 프로세스에는 다음 단계가 포함됩니다.

1. Microsoft Intune Surface Hub 관리하도록 지정된 관리자가 포함된 보안 그룹을 만듭니다.
2. PowerShell을 사용하여 Azure AD 그룹 SID를 가져옵니다.
3. Azure AD 그룹 SID를 포함하는 XML 파일을 만듭니다.
4. 비 전역 관리자 보안 그룹이 관리할 Surface Hub 디바이스를 포함하는 보안 그룹을 만듭니다. 
5. Surface Hub 디바이스를 포함하는 보안 그룹을 대상으로 하는 사용자 지정 구성 프로필을 만듭니다.

## <a name="create-azure-ad-security-groups"></a>Azure AD 보안 그룹 만들기

먼저 관리자 계정을 포함하는 보안 그룹을 만듭니다. 그런 다음 Surface Hub 디바이스에 대한 다른 보안 그룹을 만듭니다.  

### <a name="create-security-group-for-admin-accounts"></a>관리자 계정에 대한 보안 그룹 만들기

1. Microsoft Endpoint Manager [관리 센터를 통해 Intune](https://go.microsoft.com/fwlink/?linkid=2109431) 로그인하고 **GroupsNew** **** >  그룹 > 선택하고 그룹 유형에서 **보안을 선택합니다.**
2. 그룹 이름(예: **Surface Hub 로컬 관리자)을** 입력한 다음 만들기를 선택합니다 **.**

     ![허브 관리자를 위한 보안 그룹을 만듭니다.](images/sh-create-sec-group.png)

3. 그룹을 열고 **구성원**을 선택한 다음 **구성원 추가**를 선택하여 Surface Hub 전역이 아닌 관리자로 지정하려는 관리자 계정을 입력합니다. Intune 그룹을 만드는 방법에 대한 자세한 내용은 [사용자 및 디바이스를 구성하는 그룹 추가를 참조하세요](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Surface Hub 디바이스에 대한 보안 그룹 만들기

1. 이전 절차를 반복하여 허브 디바이스에 대한 별도의 보안 그룹을 만듭니다. 예를 들어 **Surface Hub 디바이스**입니다.

     ![허브 디바이스에 대한 보안 그룹을 만듭니다.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>PowerShell을 사용하여 Azure AD 그룹 SID 가져오기

1. 관리자 권한으로 PowerShell을 시작하고(**관리자 권한으로 실행**) 시스템이 PowerShell 스크립트를 실행하도록 구성되어 있는지 확인합니다. 자세한 내용은 [실행 정책 정보(About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies?))를 참조하세요.
2. [Azure PowerShell 모듈을 설치](/powershell/azure/install-az-ps)합니다.
3. Azure AD 테넌트에 로그인합니다.

    ```powershell
    Connect-AzureAD
    ```

4. 테넌트에 로그인하면 다음 commandlet을 실행합니다. "Azure AD 그룹의 개체 ID를 입력하세요."라는 메시지가 표시됩니다.

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. Intune 다음 그림과 같이 앞에서 만든 그룹을 선택하고 개체 ID를 복사합니다.

     ![보안 그룹의 개체 ID를 복사합니다.](images/sh-objectid.png)

6. 다음 commandlet을 실행하여 보안 그룹의 SID를 가져옵니다.

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. 개체 ID를 PowerShell commandlet에 붙여넣고 **Enter 키를 누르**고 **Azure AD 그룹 SID**를 텍스트 편집기에 복사합니다.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Azure AD 그룹 SID를 포함하는 XML 파일 만들기

1. 다음을 텍스트 편집기에 복사합니다.

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. 자리 표시자 SID(S-1-12-1부터 시작)를 **Azure AD 그룹 SID**로 바꾼 다음 파일을 XML로 저장합니다(예: **aad-local-admin.xml**).

      > [!NOTE]
      > 그룹은 SID를 통해 지정해야 하지만 Azure 사용자를 직접 추가하려면 해당 UPN(사용자 계정 이름)을 다음 형식으로 지정합니다. `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>사용자 지정 구성 프로필 만들기

1. Endpoint Manager **DevicesConfiguration****** >  **profilesCreate** >  프로필을 선택합니다.
2. 플랫폼에서 **Windows 10 이상을 선택합니다.** 프로필 아래에서 **TemplatesCustomCreate** > **를** >  선택합니다 **.**
3. 이름 및 설명을 추가한 다음 다음을 선택합니다 **.**
4. **구성 설정** > **OMA-URI 설정** 아래에서 **추가**를 선택합니다.
5. 행 추가 창에서 이름을 추가하고     **OMA-URI** 아래에 다음 문자열을 추가합니다.

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

   > [!NOTE]
   > **또한 RestrictedGroups/ConfigureGroupMembership** 정책 설정을 사용하면 Windows 10 로컬 그룹에 구성원(사용자 또는 AAD 그룹)을 구성할 수 있습니다. 그러나 기존 그룹을 새 멤버로 완전히 대체할 수 있습니다. 멤버를 선택적으로 추가하거나 제거할 수 없습니다.  Windows 10 Team 2020 업데이트 2에서 사용할 수 있는 **RestrictedGroups 정책 설정 대신 LocalUsersandGroups** 정책 설정을 사용하는 것이 좋습니다. Surface Hub 두 정책 설정을 모두 적용하는 것은 지원되지 않으며 예측할 수 없는 결과를 얻을 수 있습니다.

6. 데이터 형식에서 **문자열 XML** 을 선택하고 이전 단계에서 만든 XML 파일을 찾습니다.

     ![로컬 관리자 xml 구성 파일을 업로드합니다.](images/sh-local-admin-config.png)

7. **저장**을 클릭합니다.
8. **그룹 선택을 클릭하여 이전에** [만든 보안 그룹](#create-security-group-for-surface-hub-devices)(**Surface Hub 디바이스**)을 포함하고 선택합니다. **다음**을 클릭합니다.
9. 적용 가능성 규칙에 따라 원하는 경우 규칙을 추가합니다. 그렇지 않으면 **다음** 을 선택한 다음 **만들기**를 선택합니다.

OMA-URI 문자열을 사용하는 사용자 지정 구성 프로필에 대한 자세한 내용은 [Intune Windows 10 디바이스에 대한 사용자 지정 설정 사용을](/mem/intune/configuration/custom-settings-windows-10) 참조하세요.

## <a name="non-global-admins-managing-surface-hub"></a>전역이 아닌 관리자가 Surface Hub 관리

**이제 Surface Hub Local Admins** Security 그룹의 구성원이 Surface Hub 설정 앱에 로그인하고 설정을 관리할 수 있습니다.

> [!IMPORTANT]
> 설정 앱에 대한 전역 관리자의 기본 액세스는 제거됩니다(이 새 보안 그룹의 구성원이 아닌 경우).
