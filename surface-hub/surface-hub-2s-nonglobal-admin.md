---
title: Surface Hub 2S에서 전역이 아닌 관리자 계정 구성
description: 이 문서에서는 Surface Hub 2S를 관리하도록 전역이 아닌 관리자 계정을 구성하는 방법을 설명합니다.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196822"
---
# Surface Hub 2S에서 전역이 아닌 관리자 계정 구성

Surface Hub 2S를 Azure AD 도메인에 가입할 때 Surface Hub 2S에서 설정 앱 관리 권한을 제한하는 전역이 아닌 관리자 계정을 구성할 수 있습니다. 이렇게 하면 Surface Hub 2S에 대한 관리자 권한의 범위를 지정하고 잠재적으로 원치 않는 관리자가 전체 Azure AD 도메인에 액세스하지 못하게 할 수 있습니다. 시작하기 전에 Surface Hub 2S가 Azure AD에 가입해야 합니다. 그렇지 않은 경우 Surface Hub 2S를 초기화하고 처음 OOBE(첫 실행) 설치 프로그램을 완료하고 Azure AD에 가입하는 옵션을 선택해야 합니다.

## 요약 

전역이 아닌 관리자 계정을 만드는 프로세스에는 다음 단계가 수행됩니다. 

1. Microsoft Intune에서 Surface Hub 2S를 관리하기 위해 지정된 관리자가 포함된 보안 그룹을 만드십시오.
2. PowerShell을 사용하여 Azure AD 그룹 SID를 얻습니다.
3. Azure AD 그룹 SID를 포함하는 XML 파일을 생성합니다.
4. 전역 관리자가 아닌 관리자 보안 그룹에서 관리할 Surface Hub 2S 장치를 포함하는 보안 그룹을 만드십시오.
5. Surface Hub 2S 장치를 포함하는 보안 그룹을 대상으로 하는 사용자 지정 구성 프로필을 만드십시오. 


## Azure AD 보안 그룹 만들기

먼저 관리자 계정을 포함하는 보안 그룹을 생성합니다. 그런 다음 Surface Hub 디바이스에 대한 다른 보안 그룹을 만드십시오.  

### 관리자 계정에 대한 보안 그룹 만들기

1. [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)관리 센터를 통해 Intune에 로그인하고 그룹 새 그룹 > 그룹 **Groups**  >  **New Group** 유형에서 보안을 **선택합니다.** 
2. Surface **Hub** 로컬 관리자와 같은 그룹 이름을 입력한 다음 만들기를 **선택합니다.** 

     ![허브 관리자용 보안 그룹 만들기](images/sh-create-sec-group.png)

3. 그룹을 열고 구성원을 **선택한** **Add members** 다음 구성원 추가를 선택하여 Surface Hub 2S에서 전역 관리자가 아닌 관리자로 지정하고자 하는 관리자 계정을 입력합니다. Intune에서 그룹을 만드는 데 대한 자세한 내용은 사용자 및 장치를 구성할 그룹 [추가를 참조합니다.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### Surface Hub 2S 장치에 대한 보안 그룹 만들기

1. 이전 절차를 반복하여 허브 장치에 대한 별도의 보안 그룹을 만드시다. 예를 들어 **Surface Hub 디바이스를 예로 들 수 있습니다.** 

     ![허브 장치에 대한 보안 그룹 만들기](images/sh-create-sec-group-devices.png) 

## PowerShell을 사용하여 Azure AD 그룹 SID 얻기

1. 관리자 권한(관리자**권한으로**실행)으로 PowerShell을 시작하고 시스템이 PowerShell 스크립트를 실행하도록 구성되도록 합니다. 자세한 내용은 실행 정책 [정보를 참조합니다.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?) 
2. [Azure PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/powershell/azure/install-az-ps)
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

5. Intune에서 다음 그림과 같이 앞에서 만든 그룹을 선택하고 개체 ID를 복사합니다. 

     ![보안 그룹의 개체 ID 복사](images/sh-objectid.png)

6. 다음 commandlet을 실행하여 보안 그룹의 SID를 얻게 합니다.

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. PowerShell 명령let에 개체 ID를 붙여넣고 **Enter를**누를 수 있으며 **Azure AD 그룹 SID를** 텍스트 편집기로 복사합니다. 

## Azure AD 그룹 SID를 포함하는 XML 파일 만들기

1. 다음을 텍스트 편집기로 복사합니다. 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. 자리 보기 SID(S-1-12-1로 시작)를 **Azure AD 그룹 SID로** 바꾸고 파일을 XML로 저장합니다. 예를 들어 **aad-local-admin.xml. ** 

## 사용자 지정 구성 프로필 만들기

1. 끝점 관리자에서 **장치**구성  >  **프로필 만들기**  >  **프로필을 선택합니다.** 
2. 플랫폼에서 **Windows 10 이상을 선택합니다.** 프로필에서 **사용자**지정을 선택한 다음 만들기를 **선택합니다.**
3. 이름과 설명을 추가하고 다음을 **선택합니다.**
4. 구성 **설정**  >  **OMA-URI 설정에서**추가를 **선택합니다.**
5. 행 추가 창에서 이름을 추가하고     **OMA-URI 아래에**다음 문자열을 추가합니다. 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. 데이터 형식에서 **문자열 XML을** 선택하고 이전 단계에서 만든 XML 파일을 열려고 합니다. 

     ![로컬 관리자 xml 구성 파일 업로드](images/sh-local-admin-config.png)

7. **Save**을 클릭합니다.
8. 그룹 **선택을 클릭하여** 앞서 [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) 만든 보안 그룹(Surface Hub 장치)을**포함합니다.** **다음**을 클릭합니다.
9. 적용 가능성 규칙에 따라 원하는 경우 규칙을 추가합니다. 그렇지 않으면 **다음을** 선택하고 만들기를 **선택합니다.**

OMA-URI 문자열을 사용하는 사용자 지정 구성 프로필에 대한 자세한 내용은 [Intune에서 Windows 10](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)장치에 대한 사용자 지정 설정 사용을 참조하세요.


## Surface Hub 2S를 관리하는 전역이 아닌 관리자

**이제 Surface Hub 로컬 관리자** 보안 그룹의 구성원이 Surface Hub 2S의 설정 앱에 로그인하고 설정을 관리할 수 있습니다.
