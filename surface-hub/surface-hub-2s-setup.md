---
title: Surface Hub 2S를 처음 설정할 때
description: Surface Hub 2S에 대해 처음 설정을 완료 하는 방법에 대해 알아봅니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836124"
---
# Surface Hub 2S를 처음 설정할 때

Surface Hub 2S를 처음 시작 하면 장치에서 자동으로 계정 구성 및 관련 설정을 안내 하는 첫 번째 설정 모드를 입력 합니다.

## Surface Hub 2S 계정 구성

1. **로케일을 구성 합니다.** 지역, 언어, 키보드 레이아웃 및 표준 시간대 정보를 입력 합니다. **다음**을 선택합니다.

   ![* 로캘 구성 *](images/sh2-run1.png) <br>
1. **무선 네트워크에 연결 합니다.** 기본 설정 무선 네트워크를 선택 하 고 다음을 선택 **합니다.**

- 이더넷 케이블을 사용 하 여 연결 된 경우이 옵션이 표시 되지 않습니다.
- 로그인 요청을 공급자의 웹 사이트로 리디렉션하는 핫스팟 (조임 포털)의 무선 네트워크에 연결할 수 없습니다.

3. **장치 계정 정보를 입력 합니다.** 온라인 환경에 대 한 온-프레미스 및 하이브리드 환경 및 **사용자 \ @example** 에 대해 **domain\user** 를 사용 합니다. **다음을 선택 합니다.**

   ![* 디바이스 계정 정보 입력 *](images/sh2-run2.png) <br>
1. **추가 정보를 입력 합니다.** 요청 되는 경우 Exchange 서버 주소를 입력 하 고 **다음을 선택 합니다.**

    ![* 추가 정보를 입력 합니다. 예를 들어 Exchange server 이름 *](images/sh2-run3.png) <br>

1. **이 장치를 이름으로 합니다.** 디바이스의 이름을 입력 하거나 계정 표시 이름과 사용자 원칙 이름 [UPN]을 기준으로 제안 된 항목을 사용 합니다. **다음을 선택**합니다.

- **식별 이름은** Surface Hub 2S의 왼쪽 아래 모서리에 표시 되며 장치로 투영할 때 표시 됩니다.

- **디바이스 이름은** Active Directory 또는 Azure active directory와 관련 된 경우와 Intune을 사용 하 여 장치를 등록할 때 장치를 식별 합니다.

  ![*이 디바이스 이름 *](images/sh2-run4.png) <br>
 
## 장치 관리자 계정 구성

처음 설치할 때만 장치 관리자를 설정할 수 있습니다. 자세한 내용은 [Surface Hub 2S 디바이스 소속](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation)을 참조 하세요.

 **이 장치에 대 한 설정 관리자** 창에서 Active Directory 도메인 서비스, Azure Active Directory 또는 로컬 관리자 중에서 다음 옵션을 선택 합니다.

   ![*이 장치에 대 한 관리자 설정 *](images/sh2-run5.png) <br>

### Active Directory Domain Services

1. Active Directory에 디바이스에 가입할 수 있는 권한이 있는 사용자의 자격 증명을 입력 합니다.

    ![* 도메인 가입을 사용 하 여 관리자 설정](images/sh2-run6.png) <br>

2. Surface Hub 2S에서 설정 앱에 로그온 할 수 있는 구성원이 포함 된 Active Directory 보안 그룹을 선택 합니다.

    ![* 보안 그룹 입력 *](images/sh2-run7.png) <br>
1. **마침을**선택 합니다. 장치가 다시 시작 됩니다.

### Azure Active Directory

Azure Active Directory를 사용 하 여 디바이스를 계열사로 선택할 때 디바이스는 즉시 다시 시작 되 고 다음 페이지가 표시 됩니다. **다음**을 선택합니다.

![* 조직에서 Office 365 또는 Microsoft의 다른 비즈니스 서비스를 사용 하는 경우 조직에서이 디바이스를 enrolll 수 있습니다 *](images/sh2-run8.png) <br>

1. **Intune 요금제 1 이상을 사용 하** 는 계정의 전자 메일 주소 또는 UPN을 입력 하 고 다음을 선택 **합니다.**

    ![* 회사 또는 학교 계정 입력 *](images/sh2-run9.png) <br>

2. 리디렉션되는 경우 조직의 로그인 페이지를 사용 하 여 인증 하 고 요청 시 추가 로그온 정보를 제공 합니다. 장치가 다시 시작 됩니다.

## 로컬 관리자 계정

- 로컬 관리자의 사용자 이름 및 암호를 입력 합니다. 장치가 다시 시작 됩니다.

     ![* 관리자 계정 설정 *](images/sh2-run10.png) <br>
 
## 배포 패키지 사용

Surface Hub 2S를 시작할 때 제공 패키지가 있는 USB 엄지 드라이브를 USB 포트 중 하나에 삽입 하면 장치에 다음 페이지가 표시 됩니다.

1. 요청 된 설정을 입력 하 고 **설치**를 선택 합니다.

    ![* 프로비저닝 패키지에 대 한 국가별 설정 입력 *](images/sh2-run11.png) <br>

    ![* 이동식 미디어에서이 디바이스 프로 비전 *](images/sh2-run12.png) <br>
2. 사용할 프로비저닝 패키지를 선택 합니다.

   ![* 사용할 프로비저닝 패키지 선택 *](images/sh2-run13.png) <br>

3. 여러 장치 CSV 파일을 만든 경우에는 장치 구성을 선택할 수 있습니다. 자세한 내용은 [Surface Hub 2S 용 프로비저닝 패키지 만들기](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)를 참조 하세요.


    ![* 구성 파일에서 장치 계정 및 이름 선택 *](images/sh2-run14.png) <br>

4. 지침에 따라 처음 설치를 완료 합니다.
