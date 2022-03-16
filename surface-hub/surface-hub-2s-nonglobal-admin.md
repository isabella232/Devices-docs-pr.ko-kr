---
title: Surface Hub에서 전역이 아닌 관리자 계정 구성
description: 이 문서에서는 전역이 아닌 관리자 계정을 구성하여 2S 및 전역 관리자 Surface Hub Surface Hub 설명합니다.
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
ms.openlocfilehash: 429a7c84605167aa5129999f516c18d17ee30e65
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449301"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Surface Hub에서 전역이 아닌 관리자 계정 구성

Windows 10 Team 2020 업데이트는 Azure AD 도메인에 가입된 설정 장치에서 설정 Surface Hub 앱 관리 권한을 제한하는 전역이 아닌 관리자 계정을 구성하기 위한 지원을 추가합니다. 이렇게 하면 전체 Azure AD 도메인에서 사용자 Surface Hub 관리자 권한의 범위를 지정하고 관리자 액세스 권한을 차단할 수 있습니다. 시작하기 전에 Azure AD에 Surface Hub Intune이 자동으로 등록되어 있는지 확인하세요. 그렇지 않은 경우 Azure AD에 Surface Hub 옵션을 선택하여 OOBE(첫 실행) 설치 프로그램을 완료해야 합니다.

Windows 10 Team 2020 업데이트 2에서는 [LocalUsersAndGroups 구성 서비스 공급자에 대한 지원이 추가되었습니다](/windows/client-management/mdm/policy-csp-localusersandgroups). 이 [CSP](/windows/client-management/mdm/policy-csp-restrictedgroups)는 아래 설명된 그대로 사용 가능하지만 더 이상 권장되지 않습니다.

## <a name="summary"></a>요약

전역이 아닌 관리자 계정을 만드는 프로세스는 다음 단계로 진행됩니다.

1. 이 Microsoft Intune 관리하기 위해 지정된 관리자가 포함된 보안 그룹을 Surface Hub.
2. PowerShell을 사용하여 Azure AD 그룹 SID를 얻습니다.
3. Azure AD 그룹 SID를 포함하는 XML 파일을 생성합니다.
4. 전역 관리자가 아닌 Surface Hub 관리자가 관리할 디바이스가 포함된 보안 그룹을 만들 수 있습니다. 
5. 사용자 지정 디바이스가 포함된 보안 그룹을 대상으로 하는 사용자 지정 구성 프로필을 Surface Hub.

## <a name="create-azure-ad-security-groups"></a>Azure AD 보안 그룹 만들기

먼저 관리자 계정이 포함된 보안 그룹을 만들어야 합니다. 그런 다음 장치용 다른 보안 Surface Hub 만들 수 있습니다.  

### <a name="create-security-group-for-admin-accounts"></a>관리자 계정에 대한 보안 그룹 만들기

1. Microsoft Endpoint Manager 관리 센터를 통해 Intune [](https://go.microsoft.com/fwlink/?linkid=2109431)**** >  에 로그인하고 **GroupsNew Group** > 선택하고 그룹 유형에서 보안을 **선택합니다.**
2. 로컬 관리자와 같은 그룹 Surface Hub 입력한 다음 **** 만들기를 **선택합니다.**

     ![허브 관리자를 위한 보안 그룹을 만들 수 있습니다.](images/sh-create-sec-group.png)

3. 그룹을 열고 **구성원을 선택한** 다음 구성원 추가 **** 를 선택하여 전역 관리자가 아닌 관리자로 지정하고자 하는 관리자 계정을 Surface Hub. Intune에서 그룹을 만드는 데 대한 자세한 내용은 사용자 및 장치를 구성하는 그룹 추가  [를 참조합니다](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>장치용 보안 Surface Hub 만들기

1. 이전 절차를 반복하여 허브 장치에 대해 별도의 보안 그룹을 만들 수 있습니다. 예를 들어 Surface Hub **있습니다**.

     ![허브 장치에 대한 보안 그룹을 만들 수 있습니다.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>PowerShell을 사용하여 Azure AD 그룹 SID 얻기

1. 관리자 권한(관리자 권한으로 실행)을 사용하여 PowerShell을 시작하고 시스템이 PowerShell 스크립트를 실행하도록 구성되어 있는지 확인**** 자세한 내용은 [실행 정책 정보를 참조합니다](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).
2. [모듈 Azure PowerShell 설치합니다](/powershell/azure/install-az-ps).
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

5. Intune에서 앞에서 만든 그룹을 선택하고 다음 그림과 같이 개체 ID를 복사합니다.

     ![보안 그룹의 개체 ID를 복사합니다.](images/sh-objectid.png)

6. 다음 commandlet을 실행하여 보안 그룹의 SID를 얻게 합니다.

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. PowerShell 명령줄에 개체 ID를 붙여넣고 **Enter**를 누르고 **Azure AD 그룹 SID** 를 텍스트 편집기로 복사합니다.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Azure AD 그룹 SID를 포함하는 XML 파일 만들기

1. 텍스트 편집기로 다음을 복사합니다.

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. 자리 보기 SID(S-1-12-1로 시작)를 **Azure AD 그룹 SID** 로 바꾸고 파일을 XML로 저장합니다. 예를 들어 **aad-local-admin.xml**.

      > [!NOTE]
      > 그룹을 SID를 통해 지정해야 하지만 Azure 사용자를 직접 추가하는 경우 다음 형식으로 UPNS(사용자 계정 이름)를 지정합니다. `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>사용자 지정 구성 프로필 만들기

1. 다음 Endpoint Manager **DevicesConfiguration profilesCreate profile(** > **프로필** >  **구성)을 선택합니다**.
2. 플랫폼에서 추가 **Windows 10 선택합니다.** 프로필 **에서 사용자 지정**을 선택한 다음 만들기를 **선택합니다.**
3. 이름과 설명을 추가하고 다음을 **선택합니다.**
4. 구성 **설정** > **OMA-URI 설정** 추가를 **선택합니다**.
5. 행 추가 창에서 이름을 추가하고     **OMA-URI** 아래에 다음 문자열을 추가합니다.

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

> [!NOTE]
> **RestrictedGroups/ConfigureGroupMembership** 정책 설정을 사용하면 구성원(사용자 또는 AAD 그룹)을 로컬 그룹에 Windows 10 수 있습니다. 그러나 기존 그룹을 새 구성원으로 모두 대체할 수만 있습니다. 구성원을 선택적으로 추가하거나 제거할 수는 없습니다.  2020 Windows 10 Team 2020에서 사용할 수 있는 경우 **RestrictedGroups 정책 설정 대신 LocalUsersandGroups** 정책 설정을 사용하는 것이 좋습니다. 두 정책 설정을 Surface Hub 지원되지 않는 경우 예측할 수 없는 결과가 나타날 수 있습니다.

6. 데이터 형식에서 **문자열 XML을 선택하고** 이전 단계에서 만든 XML 파일을 열습니다.

     ![로컬 관리자 xml 구성 파일을 업로드합니다.](images/sh-local-admin-config.png)

7. **저장**을 클릭합니다.
8. 그룹 **선택을 클릭하여 이전** 디바이스에서 만든 [](#create-security-group-for-surface-hub-devices) 보안 그룹을 **Surface Hub 선택합니다**. **다음**을 클릭합니다.
9. 적용 가능성 규칙에서 원하는 경우 규칙을 추가합니다. 그렇지 않으면 다음 **을 선택하고** 만들기를 **선택합니다**.

OMA-URI 문자열을 사용하는 사용자 지정 구성 프로필에 대한 자세한 내용은 Intune에서 사용자 지정 Windows 10 [설정을 참조하세요](/mem/intune/configuration/custom-settings-windows-10).

## <a name="non-global-admins-managing-surface-hub"></a>전역 관리자를 관리하지 Surface Hub

이제 **Surface Hub 로컬** 관리자 보안 그룹의 구성원이 관리자의 설정 앱에 로그인하고 설정을 Surface Hub 수 있습니다.

> [!IMPORTANT]
> 설정 앱에 대한 전역 관리자의 기본 액세스는 제거됩니다(이 새 보안 그룹의 구성원이 아는 경우 제외).
