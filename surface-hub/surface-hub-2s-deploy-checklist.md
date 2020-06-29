---
title: Surface Hub 2S 배포 검사 목록
description: 배포 전 및 사후 검사를 사용 하 여 Surface Hub 2S 배포를 확인 합니다.
keywords: 쉼표로 값 구분
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 3c30892a3ae4f534006aa32ad6d969b42a52cbf2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836367"
---
# Surface Hub 2S 배포 검사 목록

## Surface Hub 2S 배포 전 검사 목록

|**항목**|**응답**|
|:------ |:------ |
|**디바이스 계정 이름**| |
|**디바이스 계정 UPN**| |
|**ActiveSync 정책**| |
|**일정 처리 구성이 완료 되었습니다.**| ☐ 예 <br>  ☐ 없음 |
|**장치에 친근 한 이름**| |
|**장치 호스트 이름**| |
|**가입**| ☐ 없음 <br> Active Directory 소속 ☐ <br> Azure Active Directory ☐ |
|**Microsoft 팀 모드**| ☐ 모드 0 <br> ☐ 모드 1 <br> ☐ 모드 2 |
|**장치 관리**| ☐ 예, Microsoft Intune <br> ☐ 예, 기타 모바일 장치 관리자 [MDM] <br> ☐ 없음 |  
|**프록시**| 자동 구성 ☐ <br> ☐ 프록시 서버 <br> PAC (프록시 자동 구성) 파일 ☐ |
|**프록시 인증**| ☐ 디바이스 계정 자격 증명 <br> 자격 증명을 묻는 메시지 ☐ |
|**암호 순환**| ☐ <br> ☐ 끄기 |
|**비즈니스용 Skype 추가 도메인 이름 (온-프레미스에만 해당)**| |
|**세션 시간 제한 시간**| |
|**세션 시간 제한 작업**| 세션 종료 ☐ <br> 이력서 허용 ☐ |
|**내 모임 및 파일**| ☐ 사용 <br> ☐ 사용 안 함 |
|**잠금 화면 시간 제한**| |
|**절전 유휴 시간 제한**| |
|**Bluetooth**| ☐ <br> ☐ 끄기 |
|**BitLocker USB 드라이브만 사용**| ☐ <br> ☐ 끄기 |
|**추가 인증서 설치 (온-프레미스에만 해당)**| |
|**Windows 업데이트**| 비즈니스용 Windows 업데이트 ☐ <br> ☐ Windows Server Update Services [WSUS] |
|**Surface app 연사 설정**| ☐ 롤링 스탠드 <br> 벽 장착식 ☐ |
|**IP 주소**| ☐ 유선-DHCP <br> ☐ 유선-DHCP 예약 <br> ☐ Wireless-DHCP <br> ☐ Wireless-DHCP 예약 |

## 배포 후 검사 목록 2S Surface Hub

|**확인**|**응답**|
|:------|:---------|
|**디바이스 계정 동기화**| ☐ 예 <br> ☐ 없음 |
|**Bitlocker 키**| ☐ 파일에 저장 됨 (소속 없음) <br> Active Directory에 저장 된 ☐ (광고 소속) <br>☐ Azure AD (Azure AD 소속)에 저장 됩니다. |
|**장치 OS 업데이트**| ☐ 완료 |
|**Windows 스토어 업데이트**| 자동 ☐ <br> ☐ 수동 |
|**Microsoft 팀이 예약한 모임**| ☐ 확인 이메일 수신 <br> 시작 화면에 ☐ 모임이 표시 됩니다. <br>  원터치 조인 함수 ☐ <br> 오디오에 참가할 수 ☐ <br> 비디오에 참가할 수 ☐ <br> ☐ 화면을 공유할 수 있습니다. ||
|**비즈니스용 Skype 예약 된 모임**| ☐ 확인 이메일 수신 <br> 시작 화면에 ☐ 모임이 표시 됩니다. <br> 한 터치 조인 함수를 올바르게 ☐ <br> 오디오에 참가할 수 ☐ <br> 비디오에 참가할 수 ☐ <br> ☐ 화면을 공유할 수 있습니다. <br> 메신저 대화를 보내고 받을 수 ☐ |
|**이미 초대 된 모임**| ☐ 모임 거절 |
|**Microsoft 팀원 임시 회의**| 다른 사용자의 작업을 ☐ 초대 <br> 오디오에 참가할 수 ☐ <br> 비디오에 참가할 수 ☐ <br> ☐ 화면을 공유할 수 있습니다. |
|**비즈니스용 Skype 예약 된 모임**| 다른 사용자의 작업을 ☐ 초대 <br> 오디오에 참가할 수 ☐ <br> 비디오에 참가할 수 ☐ <br> ☐ 화면을 공유할 수 있습니다. <br> 메신저 대화를 보내고 받을 수 ☐ |
|**Microsoft Whiteboard**| 시작/시작 화면에서 ☐ 시작 <br> Microsoft 팀에서 ☐ 시작 | 
|**받는 Skype/팀 전화**| 오디오에 참가할 수 ☐<br>비디오에 참가할 수 ☐ <br> ☐ 화면을 공유할 수 있습니다. <br> 메신저 대화를 보내고 받을 수 ☐ (비즈니스용 Skype만 해당) |
|**들어오는 라이브 비디오 스트림**| ☐ 최대 2 (비즈니스용 Skype) <br> ☐ 최대 4 (Microsoft 팀) |
|**Microsoft 팀 모드 0 동작**| 시작/시작 화면의 비즈니스용 Skype 타일 ☐ <br> 예정 된 비즈니스용 Skype 모임에 참가할 수 ☐ (Skype UI) <br> ☐ 예약 된 팀 모임에 참가할 수 있습니다 (팀 UI). |
|**Microsoft 팀 모드 1 동작**| 시작/시작 화면에서 팀 ☐ 타일 <br> 예정 된 비즈니스용 Skype 모임에 참가할 수 ☐ (Skype UI) <br> ☐ 예약 된 팀 모임에 참가할 수 있습니다 (팀 UI). |
|**Microsoft 팀 모드 2 동작**| 시작/시작 화면에서 팀 ☐ 타일 <br> 예약 된 팀 모임에 참가할 수 ☐ <br> 비즈니스용 Skype 모임에 참가 하지 ☐ |
