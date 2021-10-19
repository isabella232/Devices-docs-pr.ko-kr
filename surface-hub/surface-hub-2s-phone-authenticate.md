---
title: Surface Hub에서 암호 없는 로그인 구성
description: 로그인을 단순화하는 방법을 Surface Hub.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 5449a3a168821c61b7c8969bfe445db91f357a2b
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101182"
---
# <a name="configure-passwordless-sign-in-on-surface-hub"></a>Surface Hub에서 암호 없는 로그인 구성

 
암호 없는 로그인을 사용하면 앱, 모임 및 파일에 쉽게 액세스할 수 있습니다. Surface Hub 조직에서 제공하는 Microsoft Authenticator 및 FIDO2 보안 키를 사용하여 로그인할 수 있습니다.

**중요:** 이 콘텐츠는 사용자를 위한 것입니다. 암호 없는 로그인을 사용하려면 IT 관리자가 조직에 대해 암호 없는 인증을 사용하도록 설정해야 합니다. 자세한 내용은 다음을 참조하세요.

- [암호 없는 전화 로그인 사용](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [암호 없는 보안 키 로그인 사용](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <a name="configure-sign-in-using-microsoft-authenticator-app"></a>앱으로 로그인 Microsoft Authenticator 구성

**참고:** Windows 10 Team 2020 업데이트부터 사용자는 Azure AD에서 기본 설정 전자 메일 별칭과 UPN(사용자 계정 이름)을 사용하여 기본 설정 전자 메일 별칭을 사용하여 로그인할 수 Microsoft Authenticator. 예를 들어 사용자는 기본 설정 별칭(John.Doe@contoso.com) 또는 UPN(jdoe@contoso.com)을 사용하여 로그인할 수 있습니다.
 
이 Microsoft Authenticator 앱을 사용하면 모바일 장치를 사용하여 Surface Hub 로그인할 수 있습니다. 다음을 사용하여 로그인을 Microsoft Authenticator.


1. 모바일 장치에서 앱 앱을 Microsoft Authenticator 다운로드합니다.
    - Google Android: Android 장치에서 Google Play로 이동하여 앱 앱을 [다운로드하고 Microsoft Authenticator 설치합니다.](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)
    - Apple iOS: Apple iOS 장치에서 앱 스토어로 이동하여 앱 앱을 [다운로드하고 Microsoft Authenticator 설치합니다.](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)
2. PC에서 직장 또는 [Microsoft Authenticator](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) 계정의 보안 정보 페이지에서 앱 앱을 설치합니다.
3. 모바일 Microsoft Authenticator 앱에서 직장 또는 학교 [](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) 계정에 대해 전화 로그인을 켜고 사용합니다.

 
## <a name="configure-sign-in-using-fido2-security-keys"></a>FIDO2 보안 키를 사용하여 로그인 구성

> [!NOTE]
>  FIDO2 보안 키를 Surface Hub 암호 없는 로그인하려면 2020 Windows 10 Team 필요합니다.

> [!IMPORTANT]
> Surface Hub USB 보안 키만 지원됩니다.
 
조직에서 제공하는 FIDO2 Surface Hub 사용하여 로그인할 수도 있습니다. 

### <a name="to-configure-sign-in-using-a-security-key"></a>보안 키를 사용하여 로그인을 구성합니다.


1. PC에서 페이지로 이동하여 직장 또는 학교 계정에 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 로그인합니다.
2. 왼쪽 **탐색 창** 또는 보안 정보 블록의 링크에서 보안 **정보를** **** 선택한 다음 보안 정보 페이지에서 메서드 **추가를** 선택합니다.
3. 메서드 **추가 페이지의** 드롭다운 **** 목록에서 보안 키를 선택한 다음 추가 를 **선택합니다.**
4. 보안 키 **페이지에서** **USB 장치 를 선택합니다.**
5. 보안 키를 준비하고 다음 을 **선택합니다.**
6. 나타나는 대화 상자에서 지침에 따라 보안 키를 삽입하고, PIN을 만들거나 입력하고, 필요한 제스처(생체 인식 또는 터치)를 수행하세요.
7. 보안 **키 페이지에서** 보안 키에 이름을 지정하고 다음 을 **선택합니다.**
8. **완료를** 선택하여 프로세스를 완료합니다.

## <a name="sign-in-to-surface-hub"></a>로그인하여 Surface Hub

암호 없는 로그인을 구성한 후 암호 없는 로그인을 사용하여 다음의 앱, 모임 및 파일에 더 쉽게 액세스할 수 Surface Hub.

- 모임에 빠르게 참가하고 최근 파일로 Microsoft 365 를 습니다. 자세한 내용은 [**로그인을 참조하여 모임 및 파일 보기를 참조하세요.**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)
- 화이트보드, PowerPoint, Word, Excel, OneDrive 및 앱과 같은 Microsoft Power BI.
- 즐겨찾기 및 검색 기본 Microsoft Edge 액세스하기 위해 새 앱에 빠르게 로그인합니다. 자세한 내용은 새 서버 설치 및 구성을 [Microsoft Edge.](surface-hub-install-chromium-edge.md)
- 로그인한 Surface Hub 세션 종료를 선택할 때까지 다시 로그인하지 않고도 다른 앱을 **사용할 수 있습니다.** 세션 **종료를 선택하면** 장치에서 자격 증명, 파일 및 개인 데이터가 삭제됩니다. 자세한 내용은 세션 [종료를 참조하세요.](finishing-your-surface-hub-meeting.md)


## <a name="learn-more"></a>자세히 알아보기

- [사용자에 대한 암호 없는 인증 Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [Microsoft Authenticator 암호 없는 로그인](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [FIDO2 보안 키를 사용하는 암호 없는 로그인](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

