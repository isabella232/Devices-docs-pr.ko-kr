---
title: '알려진 문제: Surface Hub'
description: 이 페이지에서는 Surface Hubs의 알려진 문제 목록을 제공합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
ms.openlocfilehash: a9435db1de48b33d062d5e79d0d622f1d17815f0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497488"
---
# <a name="known-issues-surface-hub"></a>알려진 문제: Surface Hub

이 문서에서는 2020 업데이트를 Windows 10 Team 현재 운영 체제를 실행하는 Surface Hubs의 알려진 문제를 나열합니다.

Surface Hub 최신 업데이트를 받도록 하려면 관리자 계정으로 로그인하고 **모든 앱** > **설정** > **업데이트 및 보안** > **Windows 업데이트**을 선택한 다음 모든 업데이트를 설치합니다.

| 문제               | 설명           | 해결 방법                 |
|---------------------|-----------------------|------------------------|
| Surface Hub 디바이스에서 Whiteboard 애플리케이션을 사용하는 경우 전자 메일을 통해 콘텐츠를 공유할 수 없습니다. | "간편한 공유" 기능이 새 버전의 Whiteboard 앱에서 제거되었습니다. | Whiteboard 콘텐츠를 저장하는 권장 방법은 앱에 로그인하는 것입니다. 로그인이 불가능한 경우 이미지 파일을 로컬 스토리지에 저장한 다음 Edge 브라우저를 통해 사용자 기본 설정 서비스를 통해 공유할 수 있습니다. "간편한 공유" 기능은 이후 버전의 Whiteboard에서 반환됩니다. [화이트보드 공유 시나리오에 대해 자세히 알아봅니다.](https://support.microsoft.com/office/enable-microsoft-whiteboard-for-your-organization-1caaa2e2-5c18-4bdf-b878-2d98f1da4b24) |
| 사용자가 '세션 종료'를 선택하면 일부 Surface Hub가 다시 시작됩니다.  | Surface Hub 디바이스 사용자가 사용자 데이터를 지우기 위해 '세션 종료' 기능을 선택하면 Surface Hub 디바이스가 정리 실패를 잘못 감지하여 정리가 성공적으로 수행되도록 Windows 강제로 다시 시작할 수 있습니다.  | Microsoft는 이 문제를 인식하고 적극적으로 조사하고 있습니다.  Microsoft는 가능한 한 빨리 해결 방법에 대한 추가 정보를 제공합니다.|
| GCC High 환경에서 Surface Hub를 사용하는 경우 시작 화면 일정에서 한 번 클릭으로 모임 참가가 작동하지 않습니다. | GCC High 환경에서 Teams 모임에 대한 Surface Hub 일정에서 "참가"를 클릭하면 모임이 자동으로 시작되지 않습니다. | 모임에 참가하려면 Teams 시작하고 Teams 클라이언트의 표시 안건 내에서 참가합니다. <br></br>또한 Microsoft는 이 문제를 적극적으로 조사하고 있으며 가능한 한 빨리 해결 방법에 대한 추가 정보를 제공할 것입니다. |
| QoS(서비스 품질) 설정이 예상대로 작동하지 않음 | MDM 정책 또는 프로비저닝 패키지를 통해 QoS 설정을 구성한 후에는 DSCP 표시가 Teams 또는 SfB(비즈니스용 Skype) 미디어 트래픽에 적용되지 않습니다. | Microsoft는 이 문제를 인식하고 적극적으로 조사하고 있습니다.  Microsoft는 가능한 한 빨리 해결 방법에 대한 추가 정보를 제공합니다. |
| 온-프레미스 사서함과 하이브리드 디바이스 계정의 일정 동기화가 실패합니다. | Surface Hub 디바이스는 하이브리드 최신 인증을 사용하도록 설정하지 않은 온-프레미스 환경에 사서함이 있더라도 기본적으로 Azure AD 있는 계정에 [최신 인증](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)을 사용합니다. 이 시나리오에서는 Exchange 디바이스에 대한 모임 동기화를 중지합니다. 따라서 디바이스는 새 모임을 받거나 표시하지 않습니다. | [KB4598291](https://support.microsoft.com/help/4598291)(또는 후속 Windows CU)이 설치된 후 [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)에는 최신 인증 사용을 토글하는 데 사용할 수 있는 새로운 ExchangeModernAuthEnabled 매개 변수가 있습니다. 허브가 최신 인증을 사용하지 못하도록 MDM 정책 또는 [프로비저닝 패키지를](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg) 통해 false로 설정할 수 있습니다. |
| v1 Surface Hub 디바이스의 작은 하위 집합은 Windows 10 Team 2020 업데이트로 자동으로 업그레이드할 수 없습니다. | v1 Surface Hub 디바이스의 이 작은 하위 집합은 Windows 업데이트 통해 직접 업그레이드와의 호환성을 방지하는 상태입니다. | Surface Hub [복구 도구를 사용하여](surface-hub-recovery-tool.md) 수동으로 디바이스를 Windows 10 Team 2020 업데이트로 다시 이미지화합니다. |
| Surface Hub Windows 10 Team 2020 업데이트를 설치하려고 시도한 후 "부팅 가능한 디바이스 없음" 메시지가 표시됩니다. | Windows 10 Team 2020에 대한 Windows 업데이트 프로세스 중에 일부 Hub v1 디바이스는 부팅할 수 없는 상태로 전환됩니다. | Surface Hub [복구 도구를 사용하여](surface-hub-recovery-tool.md) 수동으로 디바이스를 Windows 10 Team 2020 업데이트로 다시 이미지화합니다. |
| 허브 2S 디바이스는 WSUS를 사용하여 드라이버 업데이트를 받을 수 없습니다. | Surface Hub 2S는 비즈니스용 Windows 업데이트 및 Windows 업데이트 드라이버를 배포하도록 지원합니다. WSUS(Windows Server Update Services)를 통한 배포는 지원되지 않습니다. | WSUS를 사용하는 경우 비즈니스용 Windows 업데이트 마이그레이션합니다.<br> <br>**자세한 정보**: [비즈니스용 Windows 업데이트란?](/windows/deployment/update/waas-manage-updates-wufb) |
| Action Center에는 클릭할 수 없는 설정 링크가 있습니다. | 이 링크는 Windows 10 Team 표시되지 않아야 하며 혼동을 일으킬 수 있습니다. | 이 기능은 2020년 업데이트 이전과 동일합니다. 시작 메뉴 앱 섹션을 사용하여 설정 앱을 시작해야 합니다.  |
| 일부 액세스 용이성 설정은 세션이 종료된 후에도 유지됩니다.| 사용자가 빠른 작업 메뉴 또는 설정 앱에서 고대비 토글을 켜면 사용자 세션이 종료된 후에도 이 토글이 유지됩니다. 마찬가지로 사용자가 알림 표시를 변경하여 관리자가 정의한 5초와 7초를 나타내는 경우 다른 설정이 관리자 정의 값으로 다시 설정되더라도 7초로 유지됩니다. | 사용자는 허브에서 세션을 시작한 직후 작업 표시줄에서 액세스할 수 있는 빠른 작업(캐럿) 메뉴에서 고대비 토글을 해제할 수 있습니다. 알림 표시 기간은 다음 사용자가 설정 앱을 통해 다른 값으로 설정할 수 있습니다. 이 설정은 모든 사용자가 액세스할 수 있습니다. Microsoft는 이 문제에 대한 해결 방법을 적극적으로 찾고 있습니다.| 
