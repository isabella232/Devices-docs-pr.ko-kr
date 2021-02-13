---
title: 명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행
description: 명령 콘솔에서 Surface 진단 Toolkit 실행 방법
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327332"
---
# 명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행

명령 프롬프트에서 SDT(Surface Diagnostic Toolkit)를 실행하려면 SDT 앱 콘솔을 다운로드해야 합니다. 설치 후 Windows 명령 콘솔(cmd.exe)을 통해 명령 프롬프트에서 또는 명령, 복사/붙여넣기 및 기타 기능의 자동 Windows PowerShell 기능을 제공하는 PowerShell ISE(통합 스크립팅 환경)를 포함하여 SDT를 실행할 수 있습니다.  SDT에서 지원되는 Surface 디바이스 목록은 비즈니스용 Surface 진단 Toolkit [참조하세요.](surface-diagnostic-toolkit-business.md)

>[!NOTE]
>명령을 사용하여 SDT를 실행하려면 관리자 계정에 로그인하거나 Surface 디바이스에서 Administrator 그룹의 구성원인 계정에 로그인해야 합니다.

## SDT 앱 콘솔 실행

Surface Tools for IT 다운로드 페이지에서 SDT 앱 [콘솔을 다운로드하여 설치합니다.](https://www.microsoft.com/download/details.aspx?id=46703) Windows 명령 프롬프트(cmd.exe)를 사용하여 다음을 Windows PowerShell 있습니다. 

- 모든 로그 파일을 수집합니다.
- 모범 사례 분석기를 사용하여 상태 진단을 실행합니다.
- 펌웨어 또는 드라이버 업데이트가 누락되어 있는지 업데이트를 확인합니다.

>[!NOTE]
>이 릴리스에서 SDT 앱 콘솔은 단일 명령만 지원합니다. 여러 명령줄 옵션을 실행하려면 각 명령에 대해 콘솔 exe를 별도로 실행해야 합니다. 

기본적으로 출력 파일은 콘솔 앱과 동일한 위치에 저장됩니다. 전체 명령 목록은 다음 표를 참조하세요.

명령 | 참고
--- | ---
-DataCollector "출력 파일" | 시스템 세부 정보를 zip 파일로 수집합니다. "출력 파일"은 시스템 세부 정보 zip 파일을 만드는 파일 경로입니다.<br><br>**예**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "출력 파일" | 디바이스의 여러 설정 및 상태 표시기를 확인합니다. "출력 파일"은 HTML 보고서를 만드는 파일 경로입니다.<br><br>**예**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Windows 업데이트 온라인 서버에서 펌웨어 및/또는 드라이버 업데이트가 누락되어 있는지 확인합니다.<br><br>**예**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | 장치에서 보증 정보를 확인합니다(유효하거나 잘못). 선택적 "출력 파일"은 xml 파일을 만드는 파일 경로입니다. <br><br>**예**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –보증 "warranty.xml"


>[!NOTE]
>대상 디바이스에서 원격으로 SDT 앱 콘솔을 실행하려면 Microsoft Endpoint Configuration Manager와 같은 구성 관리 도구를 사용할 수 있습니다. 또는 콘솔 앱 및 적절한 콘솔 명령을 포함하는 .zip 파일을 만들고 조직의 소프트웨어 배포 프로세스에 따라 배포할 수 있습니다. 

## 모범 사례 분석기 실행 

BitLocker, 보안 부팅 및 TPM(신뢰할 수 있는 플랫폼 모듈)과 같은 주요 구성 요소에서 BPA 테스트를 실행한 다음 공유 가능한 파일에 결과를 출력할 수 있습니다. 이 도구는 색으로 코딩된 제목과 조건 설명자가 있는 일련의 표를 생성하고 문제 해결 방법에 대한 지침을 제공합니다. 

- 녹색은 구성 요소가 최적의 조건(최적)에서 실행되고 있는 상태를 나타냅니다.
- 주황색은 구성 요소가 최적의 조건(최적화되지 않은)에서 실행되고 있지 않다는 것입니다.
- 빨간색은 구성 요소가 비정상 상태인 것을 나타냅니다. 

### 샘플 BPA 결과 출력

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>설명:</strong></td><td>시스템 드라이브에서 BitLocker가 활성화되어 있는지 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>보호 기능</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>BitLocker를 사용하여 데이터를 보호하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">보안 부팅</font></th></tr>
<tr><td><strong>설명:</strong></td><td>보안 부팅이 사용하도록 설정되어 있는지 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>True</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>PC를 보호하기 위해 보안 부팅을 사용하도록 설정하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">신뢰할 수 있는 플랫폼 모듈</font></th></tr>
<tr><td><strong>설명:</strong></td><td>TPM이 작동하도록 합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>True</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>기능 TPM이 없는 경우 BitLocker와 같은 보안 기반 기능이 제대로 작동하지 않을 수 있습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">연결된 대기</font></th></tr>
<tr><td><strong>설명:</strong></td><td>연결된 대기실이 활성화되어 있는지 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>True</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>연결된 대기를 통해 Surface 디바이스는 사용되지 않는 동안 업데이트 및 알림을 받을 수 있습니다. 최상의 환경을 위해 연결된 대기 환경을 사용하도록 설정해야 합니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>설명:</strong></td><td>사용 가능한 Bluetooth 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>설정됨</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">디버그 모드</font></th></tr>
<tr><td><strong>설명:</strong></td><td>운영 체제가 디버그 모드에 있는지 검사합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>중</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>디버그 부팅 옵션은 Windows 운영 체제의 커널 디버깅을 활성화 또는 비활성화합니다. 이 옵션을 사용하도록 설정하면 시스템 문제가 발생할 수 있으며 DRM(디지털 권한 관리 권한)으로 보호된 미디어가 재생되지 않도록 할 수 있습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">테스트 서명</font></th></tr>
<tr><td><strong>설명:</strong></td><td>테스트 서명이 사용하도록 설정되어 있는지 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>중</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>테스트 서명은 시험판 드라이버를 테스트하는 데만 사용할 수 있는 Windows 시작 설정입니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">활성 전원 계획</font></th></tr>
<tr><td><strong>설명:</strong></td><td>올바른 전원 계획이 활성 상태인지 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>균형 조정</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>생산성과 배터리 수명을 최대화하기 위해 "균형 조정된" 전원 계획을 사용하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows 업데이트</font></th></tr>
<tr><td><strong>설명:</strong></td><td>디바이스가 Windows 업데이트를 사용하여 최신 버전이면 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>Microsoft Silverlight(KB4023307), Windows Defender 바이러스 백신에 대한 정의 업데이트 - KB2267602(정의 1.279.1433.0)</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="ff9500">최적화되지 않습니다.</font></td></tr>
<tr><td><strong>지침:</strong></td><td>최신 창으로 업데이트하면 최신 펌웨어 및 드라이버를 사용할 수 있습니다. 장치를 항상 최신으로 유지하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">무료 하드 드라이브 공간</font></th></tr>
<tr><td><strong>설명:</strong></td><td>사용이 없는 하드 드라이브 공간이 부족한지 검사합니다.</td></tr>
<tr><td><strong>값:</strong></td><td>66%</td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>최상의 성능을 위해 하드 드라이브 용량의 10% 이상을 사용 가능 공간으로 설정해야 합니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">작동하지 않는 장치</font></th></tr>
<tr><td><strong>설명:</strong></td><td>장치 관리자의 작동하지 않는 장치 목록입니다.</td></tr>
<tr><td><strong>값:</strong></td><td></td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>장치 관리자에서 작동하지 않는 장치는 각 하드웨어 구성 요소의 절전과 같이 Surface 디바이스에서 예측할 수 없는 문제가 발생할 수 있습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">외부 모니터</font></th></tr>
<tr><td><strong>설명:</strong></td><td>호환성 문제가 있을 수 있는 외부 모니터를 확인합니다.</td></tr>
<tr><td><strong>값:</strong></td><td></td></tr>
<tr><td><strong>조건:</strong></td><td><font color="00ff00">최적</font></td></tr>
<tr><td><strong>지침:</strong></td><td>Surface 디바이스와 호환되는지 원래 장비 제조업체에 문의하십시오.</td></tr>
</table>
