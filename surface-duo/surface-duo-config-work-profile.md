---
title: Surface Duo에 대한 Android 엔터프라이즈 작업 프로필 구성
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
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326229"
---
# Surface Duo에 대한 Android 엔터프라이즈 작업 프로필 구성

BYOD 배포를 대상으로 하는 작업 프로필은 Duo에 회사 앱 및 데이터에 대해 별도의 공간을 제공하여 조직은 직원이 개인 앱 및 데이터에 장치를 사용하지 못하게 하여 데이터, 앱 및 보안 정책을 완전하게 제어할 수 있도록 합니다.

### Android 엔터프라이즈 작업 프로필 설정

회사 프로필을 사용하여 사용자 소유 Android 장치에서 회사 데이터 및 앱을 관리합니다. 기본적으로 개인 소유의 작업 프로필 장치를 등록할 수 있으며 추가 관리자 구성이 필요 없습니다.  

**엔터프라이즈 작업 프로필을 사용하도록 설정하려면**

- 끝점 관리자에서 **장치**Android Android 등록을 선택한 다음 직장 프로필이 있는  >  ****  >  **** 개인 **장치를 선택합니다.**
<br><br>
 ![엔터프라이즈 작업 프로필 사용](images/enroll-start.png)

 
**Android 엔터프라이즈 작업 프로필을 사용하여 Surface Duo에 로그인**

1. Google Play 스토어에서 회사 포털 앱을 설치하고 Microsoft 회사 또는 학교 계정으로 로그인합니다.<br><br>
![Surface Duo에 로그인](images/duo-wp-1.png)
 
2. 액세스 설정 페이지에서 시작을 **선택합니다.**<br><br>
![Begin](images/duo-wp-2.png)

3. 개인 정보 페이지의 정보를 검토하고 계속을 **선택합니다.**<br><br>
 ![계속](images/duo-wp-3.png)
<br><br>
 ![계속 선택](images/duo-wp-4.png)
 
4. 작업 프로필 설정이 완료되면 **계속을** 선택하여 장치를 활성화하고 등록합니다.<br><br>
 ![디바이스 활성화 및 등록을 계속 선택합니다.](images/duo-wp-5.png)

5. **계속**을 선택합니다.<br><br>
 ![다시 계속 선택](images/duo-wp-6.png)

6. 작업 프로필을 활성화한 경우 **** 장치 설정을 업데이트하려면 계속을 선택합니다. 이 예제에서 작업 프로필은 더 강력한 6자리 영문 암호를 요구하기 위해 MDM 설정을 적용합니다. <br><br>

     ![영문 암호 예](images/duo-wp-7.png)<br><br>
7. **확인을** 선택하여 필요한 인증을 입력한 다음 **계속하여** 작업 프로필 설정을 완료합니다. <br><br>
     ![설치를 계속 완료 선택](images/duo-wp-8.png)<br><br>
     ![전체 설정](images/duo-wp-9.png)<br><br>

## 자세히 알아보기

- [Android Enterprise 작업 프로필 장치 등록 설정](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

