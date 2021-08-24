---
title: Surface Duo용 Android 엔터프라이즈 작업 프로필 구성
description: 이 문서에서는 Surface Duo에서 작업 프로필을 설정하는 방법을 설명합니다.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 380c5fc625983119a516f5d0e2294af70e0dbd29
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911203"
---
# <a name="configure-android-enterprise-work-profile-for-surface-duo"></a>Surface Duo용 Android 엔터프라이즈 작업 프로필 구성

BYOD 배포를 대상으로 하는 작업 프로필은 Duo에 회사 앱 및 데이터에 대해 별도의 공간을 제공하며, 조직은 직원이 개인 앱 및 데이터에 장치를 사용하지 못하게 하여 데이터, 앱 및 보안 정책을 완전하게 제어할 수 있습니다.

### <a name="set-up-android-enterprise-work-profile"></a>Android Enterprise 프로필 설정

회사 프로필을 사용하여 사용자가 소유한 Android 장치에서 회사 데이터 및 앱을 관리합니다. 기본적으로 개인 소유의 작업 프로필 장치를 등록할 수 있으며 추가 관리자 구성이 필요 없습니다.  

**작업 프로필을 Enterprise 설정하려면**

- 다음 Endpoint Manager ****  >  **Android**  >  **등록을** 선택한 다음 직장 프로필이 있는 개인 장치를 **선택합니다.**
<br><br>
 ![작업 Enterprise 활성화합니다.](images/enroll-start.png)

 
**Android 및 작업 프로필을 사용하여 Surface Duo에 Enterprise 로그인**

1. Google 회사 포털 스토어에서 앱 앱을 설치하고 Microsoft 직장 또는 학교 계정으로 로그인합니다.<br><br>
![Surface Duo에 로그인합니다.](images/duo-wp-1.png)
 
2. 액세스 설정 페이지에서 시작 을 **선택합니다.**<br><br>
![시작.](images/duo-wp-2.png)

3. 개인 정보 페이지에서 정보를 검토하고 계속을 **선택합니다.**<br><br>
 ![계속합니다.](images/duo-wp-3.png)
<br><br>
 ![계속을 선택합니다.](images/duo-wp-4.png)
 
4. 작업 프로필 설정이 완료되면 **계속을** 선택하여 장치를 활성화하고 등록합니다.<br><br>
 ![계속을 선택하여 장치를 활성화하고 등록합니다.](images/duo-wp-5.png)

5. **계속**을 선택합니다.<br><br>
 ![다시 계속을 선택합니다.](images/duo-wp-6.png)

6. 작업 프로필을 활성화한 경우 **계속을** 선택하여 장치 설정을 업데이트합니다. 이 예제에서는 작업 프로필이 MDM 설정을 적용하여 더 강력한 6자리 영문 암호를 요구합니다. <br><br>

     ![영문 암호의 예](images/duo-wp-7.png)<br><br>
7. **확인을** 선택하여 필요한 인증을 입력한 다음 **계속을** 선택하여 작업 프로필 설정을 완료합니다. <br><br>
     ![계속을 선택하여 설정을 완료합니다.](images/duo-wp-8.png)<br><br>
     ![설치를 완료합니다.](images/duo-wp-9.png)<br><br>

## <a name="learn-more"></a>자세히 알아보기

- [Android 및 작업 프로필 Enterprise 등록 설정](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

