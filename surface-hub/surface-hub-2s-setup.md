---
title: Surface Hub 2S 설치
description: Surface Hub 2S 설치를 처음 완료하는 방법을 알아보십시오.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442196"
---
# <a name="first-time-setup-for-surface-hub-2s"></a>Surface Hub 2S 설치

Surface Hub 2S를 처음 시작하면 디바이스가 처음 설정 모드로 전환되어 계정 구성 및 관련 설정을 안내합니다.

## <a name="configuring-surface-hub-2s-account"></a>Surface Hub 2S 계정 구성

1. **로 로컬을 구성합니다.** 지역, 언어, 키보드 레이아웃 및 표준 시간대 정보를 입력합니다. **다음**을 선택합니다.

   ![* 로 지역의 구성 *](images/sh2-run1.png)

1. **무선 네트워크에 연결합니다.** 원하는 무선 네트워크를 선택하고 다음을 **선택합니다.**

   - 이더넷 케이블을 사용하여 연결된 경우 이 옵션이 표시되지 않습니다.

   - 로그인 요청을 공급자의 웹 사이트로 리디렉션하는 핫스팟(캡션 포털)의 무선 네트워크에 연결할 수 없습니다.

3. **디바이스 계정 정보를 입력합니다.** 온라인 **환경에는 도메인\사용자를,** 온라인 환경에는 **user\@example.com** 사용합니다. 다음을 **선택합니다.**

   ![* 장치 계정 정보 입력 *](images/sh2-run2.png)

1. **추가 정보를 입력합니다.** 요청한 경우 Exchange 서버 주소를 입력하고 다음을 **선택합니다.**

   ![* 추가 정보를 입력합니다. 예: Exchange 서버 이름*](images/sh2-run3.png)

1. **이 디바이스의 이름을 지정합니다.** 장치의 이름을 입력하거나 계정의 표시 이름 및 사용자 원칙 이름 [UPN]에 따라 제안된 이름을 사용합니다. **다음 을 선택합니다.**

   - 친숙한 **이름은** Surface Hub 2S의 왼쪽 아래 모서리에 표시하며 디바이스에 투영할 때 표시됩니다.

   - 장치 **이름은** Active Directory 또는 Azure Active Directory와 연결되는 경우와 Intune으로 장치를 등록할 때 장치를 식별합니다.

   ![* 이 장치 이름 지정*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a>장치 관리자 계정 구성

처음 설치하는 동안에만 장치 관리자를 설정할 수 있습니다. 자세한 내용은 Surface [Hub 2S](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)장치 관련 을 참조하세요.

이 장치에 대한 설치 관리자 **창에서** Active Directory 도메인 서비스, Azure Active Directory 또는 로컬 관리자 옵션 중 하나를 선택합니다.

![* 이 장치에 대한 설치 관리자 *](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. 장치를 Active Directory에 가입할 수 있는 권한이 있는 사용자의 자격 증명을 입력합니다.

    ![* 도메인 가입을 사용하여 관리자 설정 *](images/sh2-run6.png)

2. Surface Hub 2S의 설정 앱에 로그온할 수 있는 구성원이 포함된 Active Directory 보안 그룹을 선택합니다.

   ![* 보안 그룹 입력 *](images/sh2-run7.png)

1. 마친 **을 선택합니다.** 장치가 다시 시작됩니다.

### <a name="azure-active-directory"></a>Azure Active Directory

장치를 Azure Active Directory와 연결하기로 선택하면 디바이스가 즉시 다시 시작된 후 다음 페이지가 표시됩니다.

![* 조직에서 Office 365 또는 Microsoft의 다른 비즈니스 서비스를 사용하는 경우 조직에 이 장치를 등록합니다*](images/sh2-run8.png)

1. **다음**을 선택합니다.

1. **Intune** 계획 1 이상이 있는 계정의 전자 메일 주소 또는 UPN을 입력하고 다음을 **선택합니다.**

   ![* Enter work or school account*](images/sh2-run9.png)

1. 리디렉션된 경우 조직의 로그인 페이지를 사용하여 인증하고 요청 시 추가 로그온 정보를 제공합니다. 장치가 다시 시작됩니다.

## <a name="local-administrator-account"></a>로컬 관리자 계정

- 로컬 관리자의 사용자 이름과 암호를 입력합니다. 장치가 다시 시작됩니다.

  ![* 관리자 계정 설정*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a>프로비저닝 패키지 사용

Surface Hub 2S를 시작할 때 프로비저닝 패키지가 있는 USB 썸 드라이브를 USB 포트 중 하나에 삽입하면 장치에 다음 페이지가 표시됩니다.

1. 요청한 설정을 입력하고 **설정을 선택합니다.**

   ![* 프로비저닝 패키지에 대한 국가별 설정 입력*](images/sh2-run11.png)

   ![* 이동식 미디어에서 이 디바이스 프로비전*](images/sh2-run12.png)

2. 사용할 프로비저닝 패키지를 선택하십시오.

   ![* 사용할 프로비저닝 패키지 선택*](images/sh2-run13.png)

3. 여러 장치 CSV 파일을 만든 경우 장치 구성을 선택할 수 있습니다. 자세한 내용은 Surface [Hub 2S용](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)프로비저닝 패키지 만들기를 참조하세요.

   ![* 구성 파일에서 장치 계정 및 이름 선택*](images/sh2-run14.png)

4. 지침에 따라 처음 설치를 완료합니다.
