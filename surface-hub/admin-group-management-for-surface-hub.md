---
title: 관리자 그룹 관리
description: 장치에서 설정 앱을 열어 각 Microsoft Surface Hub를 개별적으로 구성할 수 있습니다.
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: 관리자 그룹 관리, 설정 앱, Surface Hub 구성
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 496e99523e211499aa18d701a6258cef995d9c4c
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497321"
---
# <a name="admin-group-management-for-surface-hub"></a>Surface Hub 대한 관리 그룹 관리

디바이스에서 설정 앱을 사용하여 각 Surface Hub를 개별적으로 구성할 수 있습니다. 권한이 없는 사용자가 설정을 변경하지 못하도록 설정 앱에서는 관리자 자격 증명을 사용하여 앱을 열어야 합니다.

## <a name="admin-group-management"></a>관리자 그룹 관리

다음과 같은 방법으로 디바이스에 대한 관리자 계정을 설정할 수 있습니다.

- [로컬 관리자 계정 만들기](#create-a-local-admin-account)
- [Active Directory에 디바이스 도메인 가입](#domain-join-the-device-to-active-directory)
- [디바이스 조인 Azure AD](#azure-ad-join-the-device)
- [Azure AD 조인된 디바이스에서 전역이 아닌 관리자 계정 구성(Surface Hub 2S)](#configure-non-global-admin-accounts-on-azure-ad-joined-devices)

### <a name="create-a-local-admin-account"></a>로컬 관리자 계정 만들기

로컬 관리자를 만들려면 [첫 실행 중에 로컬 관리자를 사용하도록 선택합니다](first-run-program-surface-hub.md). 이렇게 하면 선택한 사용자 이름과 암호를 사용하여 Surface Hub에 단일 로컬 관리자 계정이 만들어집니다. 이러한 자격 증명을 사용하여 설정 앱을 엽니다.

관리 계정 정보는 디렉터리 서비스에서 백업하지 않습니다. 장치가 AD(Active Directory) 또는 Azure AD(Active Directory)에 액세스할 수 없는 경우에만 로컬 관리자를 선택하는 것이 좋습니다. 로컬 관리자의 암호를 변경하려는 경우 설정에서 변경할 수 있습니다. 그러나 로컬 관리자 계정 사용에서 도메인 또는 Azure AD 테넌트의 그룹 사용으로 변경하려는 경우 [장치를 초기화](device-reset-surface-hub.md)하고 처음 프로그램을 다시 수행해야 합니다.

### <a name="domain-join-the-device-to-active-directory"></a>Active Directory에 디바이스 도메인 가입

Surface Hub를 AD 도메인에 가입시켜 지정된 보안 그룹의 사용자가 설정을 구성하도록 할 수 있습니다. 첫 실행 중에 [Active Directory 도메인 서비스](first-run-program-surface-hub.md#active-directory-domain-services)를 사용하도록 선택합니다. 선택한 도메인에 가입할 수 있는 자격 증명과 기존 보안 그룹의 이름을 제공해야 합니다. 해당 보안 그룹의 구성원인 사용자가 자격 증명을 입력하고 설정을 잠금 해제할 수 있습니다.

#### <a name="what-happens-when-you-domain-join-your-surface-hub"></a>Surface Hub를 도메인에 가입시키면 어떻게 되나요?

Surface Hub에서는 도메인 가입을 사용하여 다음을 수행합니다.

- AD에서 지정된 보안 그룹의 구성원에게 관리자 권한을 부여합니다.
- 장치의 BitLocker 복구 키를 AD의 컴퓨터 개체 아래에 저장하여 백업합니다. 자세한 내용은 [BitLocker 키 저장(Surface Hub)](save-bitlocker-key-surface-hub.md)을 참조하세요.
- 암호화된 통신을 위해 시스템 시계를 도메인 컨트롤러와 동기화합니다.

Surface Hub 도메인 컨트롤러에서 그룹 정책 또는 인증서를 적용하는 것을 지원하지 않습니다.

> [!NOTE]
> Surface Hub가 도메인과의 신뢰를 읽을 경우(예: 도메인에 가입된 후 도메인에서 Surface Hub를 제거하는 경우) 장치에 인증하여 설정을 열 수 없습니다. 도메인과 Surface Hub의 트러스트 관계를 제거하려는 경우 먼저 [장치를 초기화](device-reset-surface-hub.md)합니다.

### <a name="azure-ad-join-the-device"></a>디바이스 조인 Azure AD

Azure AD 테넌트에서 IT 전문가가 설정을 구성할 수 있도록 Surface Hub 조인하도록 Azure Active Directory(Azure AD)할 수 있습니다. 첫 실행 중에 [Microsoft Azure Active Directory](first-run-program-surface-hub.md#microsoft-azure-active-directory)를 사용하도록 선택합니다. 선택한 Azure AD 테넌트에 조인할 수 있는 자격 증명을 제공해야 합니다. Azure AD에 성공적으로 조인한 후 장치에서 해당 사용자에게 관리자 권한이 부여됩니다.

기본적으로 모든 **전역 관리자**에게 Azure AD에 조인된 Surface Hub에 대한 관리자 권한이 부여됩니다. **Azure AD Premium** 또는 **EMS(Enterprise Mobility Suite)** 를 통해 다른 관리자를 추가할 수 있습니다.

1. [Azure 클래식 포털](https://portal.azure.com/)에서 **Active Directory**를 클릭하고 조직 디렉터리의 이름을 클릭합니다.
2. **구성** 페이지의 **장치** > **Azure AD 조인 장치의 추가 관리자**에서 **선택됨**을 클릭합니다.
3. **추가**를 클릭하고 Surface Hub 및 기타 Azure AD 조인 장치에서 관리자로 추가할 사용자를 선택합니다.
4. 작업을 마치면 확인 표시 단추를 클릭하여 변경 내용을 저장합니다.

#### <a name="what-happens-when-you-azure-ad-join-your-surface-hub"></a>Surface Hub를 Azure AD에 조인하면 어떻게 되나요?

Surface Hub에서는 Azure AD 조인을 사용하여 다음을 수행합니다.

- Azure AD 테넌트의 적절한 사용자에게 관리자 권한을 부여합니다.
- 장치를 Azure AD에 조인하는 데 사용된 계정으로 장치의 BitLocker 복구 키를 저장하여 해당 키를 백업합니다. 자세한 내용은 [BitLocker 키 저장(Surface Hub)](save-bitlocker-key-surface-hub.md)을 참조하세요.

#### <a name="automatic-enrollment-via-azure-active-directory-join"></a>Azure Active Directory 조인을 통한 자동 등록

이제 Surface Hub 디바이스를 Azure Active Directory 조인하여 Intune 자동으로 등록하는 기능을 지원합니다.

자세한 내용은 [Windows 디바이스에 대한 등록 설정을 참조하세요](/intune/windows-enroll#enable-windows-10-automatic-enrollment).

#### <a name="which-should-i-choose"></a>무엇을 선택해야 할까요?

조직에서 AD 또는 Azure AD를 사용하는 경우 주로 보안상의 이유로 도메인에 가입하거나 Azure AD에 조인하는 것이 좋습니다. 사용자는 고유한 자격 증명을 사용하여 인증하고 설정을 잠금 해제할 수 있으며, 도메인과 관련된 보안 그룹에 추가되거나 제거될 수 있습니다.

| 옵션                                            | 요구 사항                            | 설정 앱에 액세스하는 데 사용할 수 있는 자격 증명은 무엇인가요?  |
|---------------------------------------------------|-----------------------------------------|-------|
| 로컬 관리자 계정 만들기                      | 없음                                    | 첫 실행 중에 지정된 사용자 이름 및 암호 |
| AD(Active Directory)에 대한 도메인 가입              | 조직에서 AD를 사용함               | 도메인에 있는 특정 보안 그룹의 임의 AD 사용자 |
| Azure AD(Active Directory)에 장치 가입 | 조직에서 Azure AD Basic을 사용함   | 전역 관리자만 |
| &nbsp;                                            | 조직에서 Azure AD Premium 또는 EMS(Enterprise Mobility Suite)를 사용함 | 전역 관리자 및 추가 관리자 |

### <a name="configure-non-global-admin-accounts-on-azure-ad-joined-devices"></a>Azure AD 조인된 디바이스에서 전역이 아닌 관리자 계정 구성

Azure AD 조인된 Surface Hub v1 및 Surface Hub 2S 디바이스의 경우 Windows 10 Team 2020 업데이트를 사용하면 관리자 권한을 Surface Hub 설정 앱 관리로 제한할 수 있습니다. 이렇게 하면 Surface Hub 대한 관리자 권한의 범위를 지정하고 잠재적으로 원치 않는 관리자가 전체 Azure AD 도메인에 액세스하지 못하도록 방지할 수 있습니다. 자세한 내용은 [Surface Hub 전역이 아닌 관리자 계정 구성을 참조](surface-hub-2s-nonglobal-admin.md)하세요.
