---
title: Microsoft Teams 룸에 대한 네트워킹 및 서비스 품질 Surface Hub
description: 이 문서에서는 네트워크 및 서비스 품질을 최적화하기 위한 요구 사항 및 권장 사항을 Microsoft Teams 룸 Surface Hub.
keywords: Teams 룸, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d06a69d89d94839c3a9616a29ff1be12badec76e
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "11910000"
---
# <a name="configure-networking-and-quality-of-service-for-microsoft-teams-rooms-on-surface-hub"></a>네트워크 및 서비스 품질에 대한 Microsoft Teams 룸 구성 Surface Hub

이 문서에서는 사용자 환경에서 작업 환경을 최적화하도록 환경을 Microsoft Teams 룸 Surface Hub.

## <a name="create-and-test-a-device-account"></a>디바이스 계정 만들기 및 테스트

장치 계정은 Microsoft Teams 룸 클라이언트가 일정과 같은 Exchange 기능에 액세스하는 데 사용하는 계정으로, 비즈니스용 Skype. [디바이스 계정 만들기 및 테스트 참조](create-and-test-a-device-account-surface-hub.md)

## <a name="check-network-availability"></a>네트워크 가용성 확인

> [!TIP]
> 네트워크 연결 원칙에 나열된 네트워크 구성에 Microsoft 365 [사용하는 것이 좋습니다.](https://aka.ms/pnc)

Teams 룸 Surface Hub 요구 사항을 충족하는 네트워크에 액세스할 수 있어야 합니다.

- Active Directory 또는 Azure AD(Azure Active Directory) 인스턴스에 대한 액세스
- DHCP를 사용하여 IP 주소를 제공할 수 있는 서버에 대한 액세스입니다. Microsoft Teams 룸 IP Surface Hub IP 주소로 구성할 수 없습니다.
- HTTP 포트 80 및 443에 액세스합니다.
- TCP 및 UDP 포트는 포트 및 프로토콜 요구 사항에 설명된 Microsoft 365 및 Office 365 URL 및 [IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) 주소 범위에 Microsoft Teams.

> [!IMPORTANT]
> Microsoft Teams 룸 작업을 방해할 수 있는 프록시 인증을 지원하지 Teams. Surface Hub 장치 또는 Microsoft 365 서비스 끝점이 프로덕션으로 들어오기 전에 프록시 인증에서 제외되어 Teams 룸 Surface Hub.

## <a name="implement-quality-of-service-qos-on-surface-hub"></a>서비스 품질(QoS)을 Surface Hub

QoS(서비스 품질)는 관리자가 실시간 오디오/비디오 및 응용 프로그램 공유 통신 환경을 최적화할 수 있도록 하는 네트워크 기술의 조합입니다.
[MDM(모바일](manage-settings-with-mdm-for-surface-hub.md) Microsoft Teams 관리) Surface Hub 또는 프로비저닝 패키지를 사용하여 앱에 대한 QoS 구성을 완료할 [수 있습니다.](provisioning-packages-for-surface-hub.md)

다음을 사용하여 Surface Hub QoS를 Microsoft Intune.

1. Intune에서 [사용자 지정 정책 을 생성합니다.](/intune/custom-settings-configure)

2. 사용자 **지정 OMA-URI**설정 추가를 **선택합니다.** 추가하는 각 설정에 대해 이름, 설명(선택 사항), 데이터 형식, OMA-URI 및 값을 입력합니다.

3. 비디오 및 오디오 품질을 최적화하려면 Surface Hub 다음 QoS 설정을 장치에 추가합니다.

    | 이름                  | 설명           | OMA-URI                                                                        | 형식    | 값       |
    | --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
    | **오디오 포트**       | 오디오 포트 범위      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition      | 문자열  | 50000-50019 |
    | **오디오 DSCP**        | 오디오 포트 표시   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | 정수 | 46          |
    | **비디오 포트**        | 비디오 포트 범위      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition      | 문자열  | 50020-50039 |
    | **비디오 DSCP**        | 비디오 포트 표시   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | 정수 | 34          |
    | **공유 포트**      | 공유 포트 범위    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortMatchCondition    | 문자열  | 50040-50059 |
    | **DSCP 공유**      | 포트 표시 공유 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | 정수 | 18          |

4. 정책이 만들어지면 정책에 Surface Hub.

## <a name="learn-more"></a>자세히 알아보기

- [서비스 품질(QoS)을 Microsoft Teams](/microsoftteams/qos-in-teams)
