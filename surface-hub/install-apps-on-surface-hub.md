---
title: Microsoft Surface Hub에 앱 설치
description: 관리자는 Microsoft Store 또는 비즈니스용 Microsoft Store에서 앱을 설치할 수 있습니다.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: 앱 설치, Microsoft Store, 비즈니스용 Microsoft Store
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a6e791defed4970b9a1940580b5f80bbe4f006a4
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470476"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a>Microsoft Surface Hub에 앱 설치

팀 또는 조직의 요구 사항에 맞게 Surface Hub에 추가 앱을 설치할 수 있습니다. 앱을 개발 및 테스트하거나 릴리스된 앱을 배포할지에 따라 다양한 방법으로 앱을 설치할 수 있습니다. 이 항목에서는 각 시나리오에 대한 앱을 설치하는 방법을 설명합니다.

Surface Hub의 앱에 대해 알아야 하는 몇 가지 사항:
- Surface Hub에서는 [UWP(유니버설 Windows 플랫폼) 앱](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)만 실행합니다. [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter)를 사용하여 만든 앱은 Surface Hub에서 실행되지 않습니다.
- 앱은 [유니버설 장치 패밀리](https://msdn.microsoft.com/library/windows/apps/dn894631) 또는 Windows Team 장치 패밀리를 대상으로 해야 합니다.
- Surface Hub는 [](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 비즈니스용 Microsoft Store의 오프라인 라이선스 [앱만 지원합니다.](https://businessstore.microsoft.com/store)
- 기본적으로 앱은 설치할 스토어 서명되어야 합니다. 테스트 및 개발 중에 디바이스를 개발자 모드로 전환하여 개발자 서명된 UWP 앱을 실행할 수도 있습니다.
- Microsoft Store에 앱을 제출할 때 개발자는 Surface Hub에서 앱을 실행할 수 있도록 디바이스 패밀리 가용성 및 조직 라이선스 옵션을 설정해야 합니다.
- Surface Hub에 앱을 설치하려면 관리자 자격 증명이 필요합니다. 디바이스가 회의실 같은 공용 공간에서 사용하도록 설계되므로 사용자는 앱을 다운로드하고 설치하기 위해 Microsoft Store에 액세스할 수 없습니다.


## <a name="develop-and-test-apps"></a>앱 개발 및 테스트
자체 앱을 개발하는 동안 Surface Hub에서 앱을 테스트할 수 있는 몇 가지 옵션이 있습니다.

### <a name="developer-mode"></a>개발자 모드
기본적으로 Surface Hub는 Microsoft Store에 게시되고 여기에서 서명된 UWP 앱만 실행합니다. Microsoft Store에 제출된 앱은 [앱 인증 프로세스](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process)의 일부로 보안 및 준수 테스트를 통과하므로, 이를 통해 악성 앱으로부터 Surface Hub를 보호할 수 있습니다.
 
개발자 모드를 사용하도록 설정하여 개발자 서명된 UWP 앱을 설치할 수도 있습니다.
 
> [!IMPORTANT]
> 개발자 모드를 사용하도록 설정한 후 사용하지 않도록 설정하려면 Surface Hub를 초기화해야 합니다. 디바이스를 초기화하면 모든 로컬 사용자 파일과 구성이 제거되고 Windows가 다시 설치됩니다.

**개발자 모드를 켜려면** 
1. Surface Hub에서 **설정**을 시작합니다.
2. 메시지가 표시되면 디바이스 관리자 자격 증명을 입력합니다.
3. **업데이트 및 보안** > **개발자용**으로 이동합니다.
4. **개발자 모드**를 선택하고 경고 프롬프트를 수락합니다.

### <a name="visual-studio"></a>Visual Studio
개발하는 동안 Surface Hub에서 앱을 테스트하는 가장 간편한 방법은 Visual Studio를 사용하는 것입니다. Visual Studio의 원격 디버깅 기능을 통해 앱을 광범위하게 배포하기 전에 앱에서 문제를 발견할 수 있습니다. 자세한 내용은 [Visual Studio를 사용하여 Surface Hub 앱 테스트](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)를 참조하세요.

### <a name="provisioning-package"></a>프로비저닝 패키지
Visual Studio를 사용하여 테스트 인증서를 사용하여 서명된 UWP 앱에 대한 [앱 패키지를 만듭니다](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx). 그런 다음 Windows ICD(이미징 및 구성 디자이너)를 사용하여 앱 패키지가 포함된 프로비저닝 패키지를 만듭니다. 자세한 내용은 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.


## <a name="submit-apps-to-the-microsoft-store"></a>Microsoft Store에 앱 제출
앱을 릴리스할 수 있게 되면 개발자는 앱을 Microsoft Store에 제출하여 게시해야 합니다. 자세한 내용은 [Windows 앱 게시](https://developer.microsoft.com/store/publish-apps)를 참조하세요.

앱을 제출하는 동안 개발자는 **디바이스 패밀리 가용성** 및 **조직 라이선스** 옵션을 설정하여 Surface Hub에서 앱을 사용할 수 있는지 확인해야 합니다.

**디바이스 패밀리 가용성을 설정하려면**

1. [Windows 개발자 센터](https://developer.microsoft.com)에서 앱 제출 페이지로 이동합니다.

2. **패키지**를 선택합니다.
3. **Device family availability**(디바이스 패밀리 가용성)에서 다음 옵션을 선택합니다.
    
    - **Windows 10 Team**
    - **Microsoft에서 이후 디바이스 패밀리에 앱을 제공할지 여부를 결정하도록 허용**
  
   ![디바이스 패밀리 가용성 페이지를 보여 주는 이미지 - Microsoft Store 앱 제출 프로세스의 일부](images/device-family.png)  
    
   자세한 내용은 [디바이스 패밀리 가용성](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability)을 참조하세요.

**조직 라이선스를 설정하려면**

1. [Windows 개발자 센터](https://developer.microsoft.com)에서 앱 제출 페이지로 이동합니다.

2. **가격 책정 및 가용성**을 선택합니다.

3. 조직 라이선스에서 **Allow disconnected (offline) licensing for organizations**(조직에 연결이 끊어진 (오프라인) 라이선스 허용)를 선택합니다.

   ![조직 라이선스 페이지를 보여 주는 이미지 - Microsoft Store 앱 제출 프로세스의 일부](images/sh-org-licensing.png)

   > [!NOTE]
   > **Make my app available to organizations with Store-managed (online) licensing and distribution**(스토어에서 관리하는 (온라인) 라이선싱 및 배포를 보유한 조직이 내 앱을 사용할 수 있도록 설정)이 기본적으로 선택됩니다.

   > [!NOTE]
   > 개발자는 스토어에서 앱을 광범위하게 사용할 수 있도록 설정하지 않고 기간 업무 앱을 엔터프라이즈에 직접 게시할 수도 있습니다. 자세한 내용은 [엔터프라이즈에 LOB 앱 배포](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)를 참조하세요.

   자세한 내용은 [조직 라이선스 옵션](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing)을 참조하세요.


## <a name="deploy-released-apps"></a>릴리스된 앱 배포

Microsoft Store에 릴리스된 앱을 몇 대의 디바이스에서 평가할지, 아니면 조직에 광범위하게 배포할지 여부에 따라 해당 앱을 설치할 수 있는 여러 가지 옵션이 있습니다.

릴리스된 앱을 설치하려면
- Microsoft Store 앱을 사용하여 앱을 다운로드하거나,
- 비즈니스용 Microsoft Store에서 앱 패키지를 다운로드하고 프로비저닝 패키지 또는 지원되는 MDM 공급자를 사용하여 배포합니다.

### <a name="microsoft-store-app"></a>Microsoft Store 앱
Microsoft Store에 릴리스된 앱을 평가하려면 Surface Hub의 Microsoft Store 앱을 사용하여 앱을 찾고 다운로드합니다.

> [!NOTE]
> 조직에 앱을 대규모로 배포하는 방법으로는 Microsoft Store 앱을 사용하지 않는 것이 좋습니다.
> - 앱을 다운로드하려면 Microsoft 계정 또는 조직 계정으로 Microsoft Store 앱에 로그인해야 합니다. 그러나 한 번에 최대 10대의 디바이스에만 한 계정을 연결할 수 있습니다. Surface Hub 수가 10대를 초과할 경우에는 여러 계정을 만들거나 앱 설치 과정 사이에 계정에서 디바이스를 제거해야 합니다.
> - 앱을 설치하려면 소유한 각 Surface Hub에서 Microsoft Store 앱에 수동으로 로그인해야 합니다.

**Surface Hub에서 Microsoft Store를 찾으려면** 
1. Surface Hub에서 **설정**을 시작합니다.
2. 메시지가 표시되면 디바이스 관리자 자격 증명을 입력합니다.
3. **이 장치** > **앱 및 기능**으로 이동합니다.
4. **스토어 열기**를 선택합니다.

### <a name="download-app-packages-from-microsoft-store-for-business"></a>비즈니스용 Microsoft Store에서 앱 패키지 다운로드
앱 패키지를 다운로드하려면 Surface Hub에 앱을 설치하고 [비즈니스용 Microsoft Store](https://www.microsoft.com/business-store)를 방문해야 합니다. 비즈니스용 Store에서는 Surface Hub를 포함하여 조직의 Windows10 디바이스용 앱을 찾고 구매하고 관리할 수 있습니다.
 
> [!NOTE]
> 현재 Surface Hub는 비즈니스용 Store를 통해 제공되는 오프라인 사용이 허가된 앱만 지원합니다. 앱 개발자는 앱을 제출할 때 오프라인 라이선스 가용성을 설정합니다.

원하는 앱을 찾아서 구매하고 다음을 다운로드합니다.
- 오프라인 사용이 허가된 앱 패키지(.appx 또는 .appxbundle)
- *인코드되지 않은* 라이선스 파일(프로비저닝 패키지를 사용하여 앱을 설치하는 경우)
- *인코드된* 라이선스 파일(MDM을 사용하여 앱을 배포하는 경우)
- 필요한 모든 종속성 파일

자세한 내용은 [오프라인 사용이 허가된 앱 다운로드](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)를 참조하세요.

### <a name="provisioning-package"></a>프로비저닝 패키지
프로비저닝 패키지를 사용하여 비즈니스용 Store에서 다운로드한 오프라인 사용이 허가된 앱을 몇몇 Surface Hub에 수동으로 설치할 수 있습니다. Windows ICD(이미징 및 구성 디자이너)를 사용하여 비즈니스용 Store에서 다운로드한 앱 패키지와 *인코드되지 않은* 라이선스 파일이 포함된 프로비저닝 패키지를 만듭니다. 자세한 내용은 [프로비저닝 패키지 만들기](provisioning-packages-for-certificates-surface-hub.md)를 참조하세요.

### <a name="supported-mdm-provider"></a>지원되는 MDM 공급자
조직에서 많은 Surface Hub에 앱을 배포하려면 지원되는 MDM 공급자를 사용합니다. 아래 표는 오프라인 사용이 허가된 앱 패키지 배포를 지원하는 MDM 공급자를 보여 줍니다.

| MDM 공급자                | 오프라인 사용이 허가된 앱 패키지 지원 |
|-----------------------------|----------------------------------------|
| Configuration Manager가 있는 사내 MDM(버전 1602부터) | 예 |
|
| 타사 MDM 공급자    | MDM 공급자가 오프라인 사용이 허가된 앱 패키지 배포를 지원하는지 확인합니다. |

**Microsoft Endpoint Configuration Manager를 사용하여 원격으로 앱을 배포하려면**

> [!NOTE]
> 이러한 지침은 Microsoft Endpoint Configuration Manager의 현재 분기를 기반으로 합니다.

1. MDM 관리에 Surface Hub를 등록합니다. 자세한 내용은 [MDM 공급자를 사용하여 Surface Hub 관리를 참조하세요.](manage-settings-with-mdm-for-surface-hub.md)

2. 비즈니스용 Store에서 오프라인 사용이 허가된 앱 패키지, *인코드된* 라이선스 파일 및 필요한 모든 종속성 파일을 다운로드합니다. 자세한 내용은 [오프라인 사용이 허가된 앱 다운로드](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)를 참조하세요. 다운로드한 파일을 네트워크 공유의 동일한 폴더에 저장합니다.

3. Configuration Manager 콘솔의 **소프트웨어 라이브러리** 작업 영역에서 **개요** > **응용 프로그램 관리** > **응용 프로그램**을 클릭합니다.

4. **홈** 탭의 **만들기** 그룹에서 **응용 프로그램 만들기**를 클릭합니다.

5. **응용 프로그램 만들기 마법사**의 **일반** 페이지에서 **설치 파일에서 이 응용 프로그램에 대한 정보 자동 검색** 확인란을 선택합니다.

6. **형식** 드롭다운 목록에서 **Windows 앱 패키지(\*.appx, \*.appxbundle)** 를 선택합니다.

7. **위치** 필드에서, 비즈니스용 Store에서 다운로드한 오프라인 사용이 허가된 앱 패키지에 대한 UNC 경로를 \\server\share\\filename 형식으로 지정합니다. 또는 **찾아보기**를 클릭하여 앱 패키지로 이동합니다.

8. **정보 가져오기** 페이지에서 가져온 정보를 검토하고 **다음**을 클릭합니다. 필요한 경우 **이전**을 클릭하여 돌아가서 오류를 수정할 수 있습니다.

9. **일반 정보** 페이지에서 앱에 대한 추가 세부 정보를 입력합니다. 이 정보의 일부는 앱 패키지에서 자동으로 가져온 경우 미리 채워져 있을 수 있습니다.

10. **다음**을 클릭하고, 요약 페이지에서 응용 프로그램 정보를 검토하고 나서, 응용 프로그램 만들기 마법사를 완료합니다. 

11. 응용 프로그램에 대한 배포 유형을 만듭니다. 자세한 내용은 [Create deployment types for the application](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application)(응용 프로그램에 대한 배포 유형 만들기)을 참조하세요.

12. Surface Hub에 응용 프로그램을 배포합니다. 자세한 내용은 [Microsoft Endpoint Configuration Manager를 통해 응용 프로그램 배포를 참조하세요.](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)

13. 필요한 경우 비즈니스용 Store에서 새 패키지를 다운로드하고 Configuration Manager에 응용 프로그램 버전을 게시하여 앱을 업데이트합니다. 자세한 내용은 Microsoft Endpoint Configuration Manager를 통해 응용 프로그램 업데이트 및 [사용 중지를 참조하세요.](https://technet.microsoft.com/library/mt595704.aspx) 

> [!NOTE] 
> Microsoft Endpoint Configuration Manager(현재 분기)를 사용하는 경우 비즈니스용 스토어를 Configuration Manager에 연결하여 위의 단계를 무시할 수 있습니다. 이렇게 하면 구입한 앱 목록을 Configuration Manager와 동기화하고, Configuration Manager 콘솔에서 이러한 앱을 보고, 다른 앱처럼 배포할 수 있습니다. 자세한 내용은 Configuration Manager를 사용하여 비즈니스용 [Microsoft Store에서 앱 관리를 참조하세요.](https://technet.microsoft.com/library/mt740630.aspx)


## <a name="summary"></a>요약

앱을 개발하는지, 소수의 디바이스에서 앱을 평가하는지 또는 조직에 광범위하게 앱을 배포하는지 여부에 따라 Surface Hub에 앱을 설치할 수 있는 몇 가지 방법이 있습니다. 이 표에는 지원되는 방법이 요약되어 있습니다.

| 설치 방법             | 앱 개발 | 몇 개의 디바이스에서 <br> 앱 평가 | 조직에 광범위하게 <br> 앱 배포 |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| 프로비저닝 패키지       | X | X |   |
| Microsoft Store 앱          |   | X |   |
| 지원되는 MDM 공급자     |   |   | X |

## <a name="more-information"></a>자세한 정보

- [블로그 게시물: Intune를 사용하여 Surface Hub에 Windows 스토어 앱을 배포](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## <a name="related-topics"></a>관련 항목

[Microsoft Surface Hub 관리](manage-surface-hub.md)

[Microsoft Surface Hub 관리자 가이드](surface-hub-administrators-guide.md)

 

 





