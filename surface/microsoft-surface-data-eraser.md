---
title: Microsoft Surface 데이터 지우개(Surface)
description: Microsoft Surface 데이터 지우개 도구를 사용하여 Surface 디바이스에서 데이터를 안전하게 지우는 방법에 대해 알아보세요.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 도구, USB, 데이터, 지우기
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 05/17/2021
ms.openlocfilehash: 292c20c9999d9f226f28daed87069c78b43fd4bf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911193"
---
# <a name="microsoft-surface-data-eraser"></a>Microsoft Surface 데이터 지우개

Microsoft Surface 데이터 지우개 도구를 사용하여 Surface 디바이스에서 데이터를 안전하게 지우는 방법에 대해 알아보세요.

[Microsoft Surface 데이터 지우개](https://www.microsoft.com/download/details.aspx?id=46703)는 USB 스틱에서 부팅되는 도구로, 이 도구를 사용하면 호환되는 Surface 디바이스의 모든 데이터를 안전하게 지울 수 있습니다. Microsoft Surface 데이터 지우개 USB 스틱을 사용하려면 USB에서 부팅할 수 있기만 하면 됩니다. USB 스틱은 제공되는 마법사인 Microsoft Surface Data Eraser 래퍼를 사용하여 쉽게 만들고, 명령줄이 필요하지 않고 단순한 그래픽 인터페이스로 간편하게 사용할 수 있습니다. Surface에 대한 서비스 프로세스 중 Microsoft에서 사용하는 데이터 지우기 기능과 사례에 대해 자세히 알아보려면 [서비스를 받기 위해 Surface를 발송하는 경우의 데이터 보호](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy)를 참조하세요.

>[!IMPORTANT]
>Microsoft Surface 데이터 지우개는 [NIST 특별 간행물 800-88 수정 버전 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)을 통해 승인된 방식으로 NVMe(NVM Express) 형식의 명령을 사용하여 데이터를 지웁니다.

호환되는 Surface 장치는 다음과 같습니다.

- Surface Book(모든 버전)
- Surface Go(모든 버전)
- Surface Pro X(모든 버전)
- Surface Laptop(모든 버전)
- Surface Laptop 이동
- Surface Studio(모든 버전)
- Surface Pro 2 이상
- Surface 3
- Windows 10 Pro Enterprise 및 Surface Hub 2

Microsoft Surface 데이터 지우개가 도움이 되는 몇 가지 시나리오는 다음과 같습니다.

- 복구를 위해 보낼 Surface 디바이스를 준비합니다.
- 제거할 Surface 디바이스를 해제합니다. 회사 또는 조직 사용에서
- 새 부서에서 또는 새 사용자가 사용할 수 있도록 Surface 디바이스를 다시 제안합니다.
- 중요한 데이터와 함께 사용되는 디바이스에 대해 다시 이미징을 수행할 때의 표준 사례입니다.

>[!NOTE]
>타사 디바이스, Windows RT를 실행하는 Surface 디바이스(Surface, Surface 2 포함) 및 Surface Pro는 Microsoft Surface 데이터 지우개와 호환되지 않습니다.

>[!NOTE]
>Microsoft Surface 데이터 지우개를 실행하려면 USB에 부팅 기능이 필요하므로 디바이스가 USB에서 부팅되도록 구성되지 않았거나, 디바이스가 부팅 또는 POST를 수행하지 못할 경우 Microsoft Surface 데이터 지우개 도구는 작동하지 않습니다.

>[!NOTE]
>Surface Studio 및 Surface Studio 2의 Surface 데이터 지우개는 디스크 지우개가 발생하기 전에 WinPE로 부팅하는 데 최대 6분이 걸릴 수 있습니다.

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>Microsoft Surface 데이터 지우개 USB 스틱을 만드는 방법

Microsoft Surface 데이터 지우개 USB 스틱을 만들려면 먼저 이 문서 시작 부분에 제공된 링크를 사용하여 Microsoft 다운로드 센터에서 Microsoft Surface 데이터 지우개 설치 도구를 설치합니다. USB 스틱을 *만들 경우* Surface 디바이스는 필요하지 않습니다. 설치 파일을 컴퓨터에 다운로드한 후 다음 단계에 따라 Microsoft Surface 데이터 지우개 만들기 도구를 설치하세요.

1. Microsoft DataEraserSetup.msi 다운로드한 설치 파일을 [실행합니다.](https://www.microsoft.com/download/details.aspx?id=46703)

2. 확인란을 선택하여 사용권 계약에 동의한 다음 **Install**(설치)을 클릭합니다.

3. **Finish**(마침)를 클릭하여 Microsoft Surface 데이터 지우개 설치 창을 닫습니다.

만들기 도구를 설치한 후 다음 단계에 따라 Microsoft Surface 데이터 지우개 USB 스틱을 만드세요. 이 단계를 시작하려면 먼저 4GB 이상의 USB 3.0 스틱이 컴퓨터에 연결되어 있어야 합니다.

1. 시작 메뉴 또는 시작 화면에서 Microsoft Surface 데이터 지우개를 시작합니다.

2. **Build**(빌드)를 클릭하여 Microsoft Surface 데이터 지우개 USB 만들기 프로세스를 시작합니다.

3. 그림 1에서와 같이 **Start**(시작)를 클릭하여 4GB 이상의 USB 스틱이 연결되어 있음을 확인합니다.

   ![Microsoft Surface 데이터 지우개 도구를 시작하십시오.](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *그림 1. Microsoft Surface 데이터 지우개 도구 시작*
4. 그림 **** **2와** 같이 아키텍처 선택 페이지에서 대부분의 Surface 디바이스에 x64를, 아키텍처 선택 페이지에서 Surface Pro X용 **ARM64를** 선택합니다. **계속**을 선택합니다.

    ![아키텍처 선택.](images/dataeraser-arch.png "Architecture Selection")<br>
       *그림 2. 디바이스 아키텍처 선택*

5. 그림 3에 표시된 USB **Thumb Drive 선택** 페이지에서 원하는 USB 드라이브를 **** 선택한 다음 시작을 클릭하여 USB 만들기 프로세스를 시작합니다. 선택한 드라이브가 포맷되고 이 드라이브의 기존 데이터는 손실됩니다.

   >[!TIP]
   >시작 단추가 사용되지 않도록 설정되어 있으면 이동식 드라이브의 총 용량이 4GB 이상인지 확인하세요.
  
   ![USB 썸 드라이브 선택](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *그림 3. USB 썸 드라이브(thumb drive) 선택*

6. 만들기 프로세스가 완료되면 USB 드라이브가 포맷되고 모든 이진이 USB 드라이브에 복사됩니다. **Success**(성공)를 클릭합니다.

7. **Congratulations**(축하합니다.) 화면이 표시되면 썸 드라이브(thumb drive)를 꺼내어 제거할 수 있습니다. 이제 이 썸 드라이브(thumb drive)를 Surface 디바이스에 삽입하고, 부팅하여 디바이스에 있는 데이터를 지울 수 있습니다. 그림 **** 4에 표시된 같이 완료를 클릭하여 USB 만들기 프로세스를 완료합니다.

   ![Surface 데이터 지우개 USB 만들기 프로세스입니다.](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *그림 4. Microsoft Surface 데이터 지우개 USB 만들기 프로세스 완료*

8. **X**를 클릭하여 Microsoft Surface 데이터 지우개를 닫습니다.

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>Microsoft Surface 데이터 지우개 USB 스틱을 사용하는 방법

Microsoft Surface 데이터 지우개 USB 스틱을 만들고 나면 다음 절차에 따라 지원되는 Surface 디바이스를 USB 스틱에서 부팅할 수 있습니다.

1. 지원되는 Surface 장치에 부팅 가능한 Microsoft Surface 데이터 지우개 USB 스틱을 삽입합니다.

2. Microsoft Surface 데이터 지우개 USB 스틱에서 Surface 장치를 부팅합니다. USB 스틱에서 장치를 부팅하려면 다음 단계를 따릅니다.

   a. Surface 장치를 끕니다.
   b. **볼륨 작게** 단추를 길게 누릅니다.
   c. **전원** 단추를 눌렀다 놓습니다.
   d. **볼륨 작게** 단추를 놓습니다.

   >[!TIP]
   >장치가 이 단계에 따라 USB를 부팅하지 않는 경우 Surface UEFI에서 **Enable Alternate Boot Sequence**(대체 부팅 시퀀스 사용) 옵션을 켜야 할 수 있습니다. [Surface UEFI 설정 관리](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)에서 Surface UEFI 부팅 구성에 대해 자세히 읽어 볼 수 있습니다.

3. Surface 디바이스가 부팅되면 그림 5와 같이 **SoftwareLicenseTerms** 텍스트 파일이 표시됩니다.

   ![Microsoft Surface 데이터 지우개 USB 스틱 부팅](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *그림 5. Microsoft Surface 데이터 지우개 USB 스틱 부팅*

4. 소프트웨어 사용 조건을 읽고 메모장 파일을 닫습니다.

5. **Accept** 또는 **Decline**을 입력하여 소프트웨어 사용 조건에 동의하거나 거부합니다. 계속하려면 사용 조건에 동의해야 합니다.

6. Microsoft Surface 데이터 지우개 스크립트는 Surface 장치에 있는 저장 장치를 감지하고 기본 저장 장치의 세부 정보를 표시합니다. 계속하려면**Y**(Microsoft Surface 데이터 지우개를 실행하고 저장 장치의 데이터를 모두 제거함)를 누르거나 **N**(데이터를 제거하지 않고 장치를 종료함)을 누릅니다.

   >[!CAUTION]
   >Microsoft Surface 데이터 지우개 도구는 장치를 부팅하는 데 필요한 Windows 운영 체제 파일을 비롯하여 안전하고 복구할 수 없는 방식으로 모든 데이터를 삭제합니다. Microsoft Surface 데이터 지우개로 지운 Surface 장치를 부팅하려면 먼저 Windows 운영 체제를 다시 설치해야 합니다. Windows 운영 체제를 제거하지 않고 Surface 장치에서 데이터를 제거하려면 **PC 초기화** 기능을 사용할 수 있습니다. 그러나 이 기능은 포렌식 또는 데이터 복구 기능으로 데이터가 복구되지 않도록 방지합니다. 자세한 내용은 [Windows 10의 복구 옵션](https://support.microsoft.com/help/12415/windows-10-recovery-options)을 참조하세요.

   ![지울 파티션이 표시됩니다.](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *그림 6. Microsoft Surface 데이터 지우개에 지울 파티션이 표시됨*

7. 6단계에서 **Y**를 누르면 데이터 지우기 프로세스의 파괴적인 특성으로 인해 선택을 확인하는 추가 대화 상자가 표시됩니다.

8. **예** 단추를 클릭하여 Surface 디바이스에서 데이터 지우기를 계속 진행합니다.

   >[!TIP]
   >Surface 데이터 지우개 USB 드라이브에서 Surface 데이터 지우개를 실행하면 **SurfaceDataEraserLogs** 폴더에 로그 파일이 생성됩니다.

## <a name="changes-and-updates"></a>변경 및 업데이트

Microsoft Surface 데이터 지우개는 Microsoft에서 정기적으로 업데이트됩니다. 각각의 새 버전에 제공된 변경 사항에 대한 정보는 다음을 참조하세요.

### <a name="3391390"></a>3.39.139.0

*릴리스 날짜: 2021년 4월 13일*

이 버전의 Surface 데이터 지우개에는 다음이 포함됩니다.

- 4 Surface Laptop 지원

### <a name="2341390"></a>2.34.139.0

*릴리스 날짜: 2021년 1월 15일*

이 버전의 Surface 데이터 지우개:

- 버그 수정 포함

### <a name="333139"></a>3.33.139

*릴리스 날짜: 2020년 9월 9일*

이 버전의 Surface 데이터 지우개에는 버그 수정이 포함되어 있으며 다음에 대한 지원이 추가되었습니다. 

- 아키텍처를 다시 디자인하여 새 제품 릴리스로 업데이트할 필요가 없습니다.
- 새 도구 업데이트에 사용할 수 있는 알림
- 원격 분석 추가
- Windows 10 Pro Enterprise 및 Surface Hub 2

### <a name="330139"></a>3.30.139

*릴리스 날짜: 2020년 5월 11일*

이 버전의 Surface 데이터 지우개는 다음에 대한 지원을 추가합니다.

- Surface Book 3
- Surface Go 2
- Surface Go의 새로운 SSD

### <a name="328137"></a>3.28.137

*릴리스 날짜: 2019년 11월 11일*

이 버전의 Surface 데이터 지우개:

- 버그 수정 포함

### <a name="version-321137"></a>버전 3.21.137

*릴리스 날짜: 2019년 10월 21일*

이 버전의 Surface 데이터 지우개는 x86에 대해 컴파일된 후 다음 장치에 대한 지원을 추가합니다.

- Surface Pro 7, Surface Pro X 및 Surface Laptop 3

### <a name="version-32780"></a>버전 3.2.78.0

*릴리스 날짜: 2018년 12월 4일*

이 버전의 Surface 데이터 지우개:

- 버그 수정 포함

### <a name="version-32750"></a>버전 3.2.75.0

*릴리스 날짜: 2018년 11월 12일*

이 버전의 Surface 데이터 지우개:

- 2에 지원 Surface Studio 추가
- SD 카드 관련 문제 해결

### <a name="version-32690"></a>버전 3.2.69.0

*릴리스 날짜: 2018년 10월 12일*

이 버전의 Surface 데이터 지우개는 다음에 대한 지원을 추가합니다.

- Surface Pro 6
- Surface Laptop 2

### <a name="version-32680"></a>버전 3.2.68.0

이 버전의 Microsoft Surface 데이터 지우개에서는 다음에 대한 지원이 추가되었습니다.

- Surface Go

### <a name="version-32580"></a>버전 3.2.58.0

이 버전의 Microsoft Surface 데이터 지우개에서는 다음에 대한 지원이 추가되었습니다.

- 장치 및 장치용 추가 Surface Pro Surface Laptop 장치

### <a name="version-32460"></a>버전 3.2.46.0

이 버전의 Microsoft Surface 데이터 지우개에서는 다음에 대한 지원이 추가되었습니다.

- Surface Pro LTE Advanced

### <a name="version-32450"></a>버전 3.2.45.0

이 버전의 Microsoft Surface 데이터 지우개에서는 다음에 대한 지원이 추가되었습니다.

- Surface Book 2
- Surface Pro 1TB

   >[!NOTE]
   >장치에 두 개의 개별 512GB 볼륨이 표시되거나 Windows 10 배포 또는 설치를 시도할 때 오류가 발생한 경우에는 v3.2.45.0 이상의 Surface 데이터 지우개를 사용하여 1TB 저장소 옵션으로 Surface Pro 또는 Surface Laptop 디바이스를 복구할 수 있습니다. 자세한 내용은 [Surface Pro 모델 1796 및 Surface Laptop 1TB에 두 개의 드라이브 표시](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives)를 참조하세요.

### <a name="version-32360"></a>버전 3.2.36.0

이 버전의 Microsoft Surface 데이터 지우개에서는 다음에 대한 지원이 추가되었습니다.

- Surface Pro
- Surface 노트북

>[!NOTE]
>Microsoft Surface 데이터 지우개 USB 드라이브 생성 도구는 Windows 10 S에서 실행할 수 없습니다. Windows 10 S를 실행 중인 Surface 노트북을 지우려면 먼저 Windows 10 Pro 또는 Windows 10 Enterprise를 사용하는 다른 컴퓨터에 Microsoft Surface 데이터 지우개 USB 드라이브를 만들어야 합니다.
