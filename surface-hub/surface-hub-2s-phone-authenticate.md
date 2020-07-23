---
title: Surface Hub에서 비밀 번호 더 적은 로그인 구성
description: Surface Hub에 간편 하 게 로그인 하는 방법을 알아보세요.
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
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893050"
---
# Surface Hub에서 암호를 더 적게 로그인 구성

 
암호를 사용 하지 않는 로그인은 앱, 모임 및 파일에 대 한 액세스를 간소화 합니다. Surface Hub는 조직에서 제공 하는 Microsoft Authenticator 앱 및 FIDO2 보안 키를 사용 하 여 로그인을 지원 합니다.

**중요:** 이 콘텐츠는 사용자를 위한 것입니다. Passwordless 로그인을 사용 하려면 IT 관리자가 조직에 대해 passwordless 인증을 사용 하도록 설정 해야 합니다. 자세한 내용은 다음을 참조하세요.

- [Passwordless 휴대폰 로그인 사용](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Passwordless 보안 키 로그인 사용](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## Microsoft Authenticator 앱을 사용 하 여 로그인 구성

**참고:** Windows 10 팀 2020 업데이트로 시작 하는 사용자는 Azure AD의 기본 전자 메일 별칭, UPN (사용자 계정 이름)을 사용 하 여 Microsoft 인증자를 사용 하 여 로그인 할 수 있습니다. 예를 들어 사용자는 기본 별칭 (John.Doe@contoso.com) 또는 UPN (jdoe@contoso.com) 중 하나를 사용 하 여 로그인 할 수 있습니다.
 
Microsoft Authenticator 앱은 모바일 장치를 사용 하 여 Surface Hub에 로그인 하는 데 도움이 됩니다. Microsoft Authenticator를 사용 하 여 로그인을 구성 하려면 다음을 수행 합니다.


1. 모바일 장치에서 Microsoft Authenticator 앱을 다운로드 합니다.
    - Google Android: Android 장치에서 Google Play로 이동 하 여 [Microsoft Authenticator 앱을 다운로드 하 고 설치](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)합니다.
    - Apple ios: Apple iOS 장치에서 App Store로 이동 하 여 [Microsoft Authenticator 앱을 다운로드 하 고 설치](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)합니다.
2. PC 또는 학교 계정에 대 한 [보안 정보 페이지에서 Microsoft Authenticator 앱](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) 을 사용 하도록 설정 합니다.
3. 모바일 장치의 Microsoft Authenticator 앱에서 회사 또는 학교 계정에 대해 [휴대폰 로그인을 켜고 사용](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) 합니다.

 
## FIDO2 보안 키를 사용 하 여 로그인 구성

> [!NOTE]
>  FIDO2 보안 키를 사용 하 여 Surface Hub에 로그인 하는 것이 더 적은 Windows 10 팀 2020 업데이트가 필요 합니다.

> [!IMPORTANT]
> Surface Hub는 USB 보안 키만 지원 합니다.
 
조직에서 제공 하는 FIDO2 보안 키를 사용 하 여 Surface Hub에 로그인 할 수도 있습니다. 

### 보안 키를 사용 하 여 로그인을 구성 하려면 다음을 수행 합니다.


1. PC에서 페이지로 이동 하 여 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 회사 또는 학교 계정에 로그인 합니다.
2. 왼쪽 탐색 창 또는 **보안 정보** 블록의 링크에서 **보안 정보** 를 선택 하 고 **보안 정보** 페이지에서 **메서드 추가** 를 선택 합니다.
3. **메서드 추가** 페이지의 드롭다운 목록에서 **보안 키** 를 선택한 다음 **추가**를 선택 합니다.
4. **보안 키** 페이지에서 **USB 장치**를 선택 합니다.
5. 보안 키를 준비 하 고 **다음**을 선택 합니다.
6. 나타나는 대화 상자에서 지침에 따라 보안 키를 삽입 하 고, PIN을 만들거나 입력 하 고, 필요한 제스처 (생체 인식 또는 터치)를 수행 합니다.
7. **보안 키** 페이지에서 보안 키에 이름을 지정한 후 **다음**을 선택 합니다.
8. **완료** 를 선택 하 여 프로세스를 완료 합니다.

## Surface Hub에 로그인

Passwordless 로그인을 구성한 후에는이를 사용 하 여 Surface Hub의 앱, 모임 및 파일에 쉽게 액세스할 수 있습니다.

- 모임에 빠르게 참가 하 고 최근 Microsoft 365 파일을 엽니다. 자세한 내용은 [**로그인 하 여 모임 및 파일 보기**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)를 참조 하세요.
- 화이트 보드, PowerPoint, Word, Excel, OneDrive, Power BI 등의 Microsoft 앱에 빠르게 로그인 합니다.
- 새 Microsoft Edge에 빠르게 로그인 하 여 즐겨찾기 및 검색 환경 설정에 액세스 합니다. 자세한 내용은 [새 Microsoft Edge 설치 및 구성을](surface-hub-install-chromium-edge.md)참조 하세요.
- Surface Hub에 로그인 한 후 **세션 종료**를 선택할 때까지 다시 로그인 하지 않아도 다른 앱을 사용할 수 있습니다. **세션 종료** 를 선택 하면 장치에서 자격 증명, 파일 및 개인 데이터가 삭제 됩니다. 자세한 내용은 [세션 종료](finishing-your-surface-hub-meeting.md)를 참조 하세요.


## 자세히 알아보기

- [Azure Active Directory에 대 한 암호 인증 옵션을 간단히 합니다.](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [Microsoft Authenticator 앱을 사용 하 여 암호 보다 적은 로그인](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [FIDO2 보안 키를 사용 하 여 암호를 덜 로그인 합니다.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

