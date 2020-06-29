---
title: 명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행
description: 명령 콘솔에서 Surface 진단 도구 키트를 실행 하는 방법
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
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834295"
---
# 명령을 사용하여 비즈니스용 Surface 진단 도구 키트 실행

명령 프롬프트에서 SDT (Surface 진단 도구 키트)를 실행 하려면 STD 앱 콘솔을 다운로드 해야 합니다. 설치 된 후에는 명령 프롬프트에서 Windows 명령 콘솔 (cmd.exe) 또는 windows PowerShell을 사용 하 여 명령에 대 한 자동 완성, 복사/붙여넣기 및 기타 기능에 대 한 지원을 제공 하는 ISE (PowerShell 통합 스크립팅 환경)를 통해 SDT를 실행할 수 있습니다.  SDT의 지원 되는 Surface 디바이스 목록은 [비즈니스용 배포 Surface 진단 툴킷](surface-diagnostic-toolkit-business.md)을 참조 하세요.

>[!NOTE]
>명령을 사용 하 여 SDT를 실행 하려면 관리자 계정에 로그인 하거나 Surface device의 관리자 그룹 구성원 인 계정에 로그인 해야 합니다.

## SDT 앱 콘솔 실행

[IT 다운로드 화면 도구](https://www.microsoft.com/download/details.aspx?id=46703)에서 sdt 앱 콘솔을 다운로드 하 여 설치 합니다. Windows 명령 프롬프트 (cmd.exe) 또는 Windows PowerShell을 사용 하 여 다음을 수행할 수 있습니다. 

- 모든 로그 파일을 수집 합니다.
- 모범 사례 분석기를 사용 하 여 상태 진단을 실행 합니다.
- 누락 된 펌웨어 또는 드라이버 업데이트에 대 한 업데이트를 확인 합니다.

>[!NOTE]
>이 릴리스에서는 SDT 앱 콘솔에서 단일 명령만 지원 합니다. 명령줄 옵션을 여러 개 실행 하려면 각 명령에 대해 개별적으로 콘솔 exe를 실행 해야 합니다. 

기본적으로 출력 파일은 콘솔 앱과 같은 위치에 저장 됩니다. 명령에 대 한 전체 목록은 다음 표를 참조 하세요.

명령 | 참고
--- | ---
-DataCollector "출력 파일" | 시스템 세부 정보를 zip 파일로 수집 합니다. "출력 파일"은 시스템 정보 zip 파일을 만들기 위한 파일 경로입니다.<br><br>**예**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "출력 파일" | 장치에서 여러 설정 및 상태 표시기를 확인 합니다. "출력 파일"은 HTML 보고서를 만들기 위한 파일 경로입니다.<br><br>**예**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windows | Windows Update online 서버에 누락 된 펌웨어 및/또는 드라이버 업데이트가 있는지 확인 합니다.<br><br>**예**:<br>Microsoft.Surface.Diagnostics.App.Console.exe-windows
-무상 수리 "출력 파일" | 장치에 대 한 무상 수리 정보를 확인 합니다 (유효 하거나 유효 하지 않음). 선택적 "출력 파일"은 xml 파일을 만들기 위한 파일 경로입니다. <br><br>**예**: <br>Microsoft.Surface.Diagnostics.App.Console.exe – 무상 수리 "warranty.xml"


>[!NOTE]
>대상 장치에서 원격으로 SDT 앱 콘솔을 실행 하려면 Microsoft 끝점 구성 관리자와 같은 구성 관리 도구를 사용할 수 있습니다. 또는 콘솔 앱과 적절 한 콘솔 명령을 포함 하는 .zip 파일을 만들고 조직의 소프트웨어 배포 프로세스에 따라 배포할 수 있습니다. 

## 모범 사례 분석기 실행 

BitLocker, 보안 부팅, TPM (신뢰할 수 있는 플랫폼 모듈) 등의 주요 구성 요소에 대해 BPA 테스트를 실행 한 다음 해당 결과를 공유 가능한 파일에 출력할 수 있습니다. 이 도구는 색으로 구분 된 제목 및 조건 설명자와 문제 해결 방법에 대 한 지침과 함께 일련의 표를 생성 합니다. 

- 녹색은 구성 요소가 최적의 조건으로 실행 중임을 나타냅니다 (최적).
- 주황색은 구성 요소가 최적의 조건으로 실행 되 고 있지 않음을 나타냅니다 (최적화 되지 않음).
- 빨간색은 구성 요소가 비정상 상태임을 나타냅니다. 

### 샘플 BPA 결과 출력

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>설명:</strong></td><td>시스템 드라이브에서 BitLocker를 사용할 수 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>보호 설정</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>BitLocker를 사용 하 여 데이터를 보호할 것을 적극 권장 합니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">보안 부팅</font></th></tr>
<tr><td><strong>설명:</strong></td><td>보안 부팅이 활성화 되어 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>True</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>PC를 보호 하기 위해 보안 부팅을 사용 하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">신뢰할 수 있는 플랫폼 모듈</font></th></tr>
<tr><td><strong>설명:</strong></td><td>TPM이 제대로 작동 하는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>True</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>기능적 TPM이 없으면 BitLocker와 같은 보안 기반 기능이 제대로 작동 하지 않을 수 있습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">연결 된 대기 상태</font></th></tr>
<tr><td><strong>설명:</strong></td><td>연결 된 대기 모드가 사용 하도록 설정 되어 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>True</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>연결 된 대기 모드에서는 Surface 장치에서 사용 하지 않는 동안 업데이트 및 알림을 받을 수 있습니다. 최상의 환경을 위해서는 연결 된 대기 모드를 사용 하도록 설정 해야 합니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>설명:</strong></td><td>Bluetooth를 사용할 수 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>설정됨</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">디버그 모드</font></th></tr>
<tr><td><strong>설명:</strong></td><td>운영 체제가 디버그 모드 인지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>중</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>디버그 부팅 옵션은 Windows 운영 체제의 커널 디버깅을 사용 하거나 사용 하지 않도록 설정 합니다. 이 옵션을 사용 하도록 설정 하면 시스템이 불안정 해질 수 있으며 DRM (디지털 권한 managemend)이 재생 되지 않을 수 있습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">서명 테스트</font></th></tr>
<tr><td><strong>설명:</strong></td><td>테스트 서명이 활성화 되어 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>중</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>서명 테스트는 시험판 드라이버를 테스트 하는 데만 사용 해야 하는 Windows 시작 설정입니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">현재 전원 관리 옵션</font></th></tr>
<tr><td><strong>설명:</strong></td><td>올바른 전원 계획이 활성화 되어 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>적절</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>"균형" 전원 관리 옵션을 사용 하 여 생산성과 배터리 수명을 최대화 하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows 업데이트</font></th></tr>
<tr><td><strong>설명:</strong></td><td>장치가 Windows 업데이트를 사용 하 여 최신 상태 인지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>Microsoft Silverlight (KB4023307), Windows Defender Antivirus 용 정의 업데이트-KB2267602 (정의 1.279.1433.0)</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="ff9500">최적이 아님</font></td></tr>
<tr><td><strong>지침</strong></td><td>최신 windows로 업데이트 하면 최신 펌웨어와 드라이버를 사용 해야 합니다. 장치를 항상 최신 상태로 유지 하는 것이 좋습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">무료 하드 드라이브 공간</font></th></tr>
<tr><td><strong>설명:</strong></td><td>사용 가능한 하드 드라이브 공간이 부족 한지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td>66%</td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>최상의 성능을 위해 하드 드라이브에는 사용 가능한 공간으로 최소한 10%의 용량이 있어야 합니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">작동 하지 않는 장치</font></th></tr>
<tr><td><strong>설명:</strong></td><td>장치 관리자에서 작동 하지 않는 디바이스의 목록입니다.</td></tr>
<tr><td><strong>값</strong></td><td></td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>장치 관리자에서 작동 하지 않는 장치는 해당 하드웨어 구성 요소에 대 한 절전 기능을 제외한 화면 장치에서 예기치 않은 문제가 발생할 수 있습니다.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">외부 모니터</font></th></tr>
<tr><td><strong>설명:</strong></td><td>호환성 문제가 있을 수 있는 외부 모니터가 있는지 확인 합니다.</td></tr>
<tr><td><strong>값</strong></td><td></td></tr>
<tr><td><strong>상황이</strong></td><td><font color="00ff00">위해</font></td></tr>
<tr><td><strong>지침</strong></td><td>원본 장비 제조업체에 문의 하 여 Surface 디바이스와의 호환성을 확인 하세요.</td></tr>
</table>
