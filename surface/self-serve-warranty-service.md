---
title: Surface Self Serve 보증 및 서비스
description: Microsoft 365 비즈니스 고객은 Microsoft 관리 센터에서 베타 Surface Self Serve 보증 및 서비스 노드를 사용하여 서비스 주문을 만들고 관리할 수 있습니다.
ms.prod: w10
ms.mktglfcycl: support
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2021
ms.reviewer: louannh
manager: laurawi
audience: itpro
ms.openlocfilehash: a6021a58c85ac6ee4c039959dcde9bab632ea1bb
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614125"
---
# <a name="surface-self-serve-warranty-and-service"></a>Surface 셀프 서비스 보증 및 서비스

Microsoft 365 비즈니스 고객은 Microsoft 365 관리 센터에서 Surface Self Serve 보증 및 서비스 노드를 사용하여 서비스 주문을 만들고 관리할 수 있습니다. 베타 프로그램으로 사용할 수 있는 이 새로운 기능을 통해 전역 관리자는 다음을 비롯한 보증 및 서비스 클레임 지원 책임이 있는 회사 내의 개인에게 사용 권한을 지정할 수 있습니다.

- 업로드 필요한 장치에 대한 일련 번호를 입력합니다.
- 여러 배송 주소를 추가합니다.
- 하나 또는 여러 장치 및 유형 커버에 대한 단일 서비스 주문을 만들 수 있습니다.
- 실시간 서비스 주문 상태를 참조합니다.
- 디바이스가 연장 보증 또는 고급 Exchange 포함된 경우 대량으로 선적 및 수신 고급 Exchange 장치 구매의 일부로 포함되어 있습니다.

## <a name="join-beta-program"></a>베타 프로그램 참가

Microsoft 고객 성공 계정 관리자 또는 고객 성공 관리자에게 문의하여 환경 및 베타 프로그램에 참여하는 방법에 대해 자세히 알아보하세요.

## <a name="role-based-permissions"></a>역할 기반 사용 권한

Surface Self-Serve 보증 및 서비스를 사용하면 Microsoft 365 전역 관리자가 사용자에게 역할을 할당하여 서비스 주문을 만들고 관리하기 위한 다양한 권한을 부여할 수 있습니다.

베타 Microsoft 365 테넌트가 추가되는 경우 다음 관리자 역할에 추가 권한이 부여됩니다.

| 역할                  | 사용 권한                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| 전역 관리자          | 복구 요청 보기<br>복구 요청 만들기/관리<br>주소로 배송 추가/편집/삭제(es)<br>사용자 및 해당 역할 만들기/관리 |
| 서비스 지원 관리자 | 복구 요청 보기<br>복구 요청 만들기/관리                                                                               |
| 청구 관리자         | 복구 요청 보기<br>복구 요청 만들기/관리<br>주소할 배송 추가/편집/삭제(es)                                        |

사용자 및 사용 권한에 대한 자세한 내용은 [Microsoft Admin Center Overview를 참조하세요.](/microsoft-365/admin/admin-overview/about-the-admin-center)

## <a name="create-and-manage-a-service-order"></a>서비스 주문 만들기 및 관리

1. 의 Microsoft 365 관리 센터로 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) 이동하고 적절한 관리자 권한으로 로그인합니다. 자세한 내용은 Who [관리자 권한이 있나요?를 참조하세요.](/microsoft-365/business-video/admin-center-overview#who-has-admin-permissions-in-my-business)
2. Surface **장치**  >  **복구 지원으로 이동하여** 복구 **요청 만들기를 선택합니다.** (이 복구 옵션이 없는 경우 이 페이지에 액세스할 수 있는 권한이 없습니다.)

    > [!div class="mx-imgBorder"]
    > ![셀프 서비스 복구 요청 시작](images/self-serve-fig1.png)

3. 하나 또는 여러 장치에 대한 복구 요청을 만들 수 있습니다. 한 때 **하나의** 장치 제출 또는 **** 여러 장치 제출을 선택하여 .csv 파일을 사용하여 여러 일련 번호를 업로드하고 다음 을 **선택합니다.**

    > [!NOTE]
    > **여러 장치의 경우:**
    >
    > - 관리 센터 페이지에서 샘플 CSV 템플릿을 다운로드하고 필요한 정보를 추가하고 로컬 드라이브에 저장합니다.
    > - 대량 **업로드 CSV**파일 선택 , 로컬 드라이브에 .csv 파일을 선택하고 열기 **를 선택합니다.**
    > - 장치 일련 번호가 업로드됩니다. **다음을** 선택하여 복구 만들기를 계속합니다.

4. Under **Ship replacement to**에서 배송 주소를 선택합니다. 또는 새 **주소 추가 를 선택합니다.**

    > [!NOTE]
    >
    > - 사용 권한을 통해 특정 관리자는 주소에 새 배송을 추가할 수 있습니다. 권한이 있는 경우 새 > 추가할 수 있습니다. 필요한 정보를 입력한 다음 저장을 **선택합니다.**
    > - 양식은 주소 정보의 유효성을 자동으로 검사하며, 로컬 우편 시스템에서 주소를 인식하지 못하면 변경하기 위해 수정할 수 있습니다. 전자 메일 주소는 복구 요청에 대한 알림 및 통신을 보내는 데 사용됩니다.

    > [!div class="mx-imgBorder"]
    > ![
      새 주소 추가
    ](images/self-serve-fig2a.png)

5. 텍스트 블록에 장치 일련 번호를 입력하여 디바이스를 추가합니다. 자세한 내용은 장치 일련 [번호 를 참조하세요.](https://support.microsoft.com/help/4036293/surface-find-the-serial-number-on-surface) 일련 번호가 유효한 경우 보증 날짜 및 모델 번호를 포함한 이미지 및 제품 정보가 표시됩니다. 정보가 **올바른 경우** 장치 추가를 선택합니다.

    > [!div class="mx-imgBorder"]
    > ![장치 추가](images/self-serve-fig2.png)

6. 1-2단계를 반복하여 요청에 여러 장치(총 20개)를 추가합니다.
7. 드롭다운 메뉴에서 문제를 가장 잘 설명하는 문제 유형을 선택하고 다음을 **선택합니다.**

    > [!div class="mx-imgBorder"]
    > ![문제 범주 선택](images/self-serve-fig3.png)

8. 주문을 검토합니다. 정보가 올바르지 않은 경우 **뒤로를** 선택해 오류를 수정합니다.
9. 조건에 동의합니다.
10. 요청 요약이 올바른 경우 요청 **제출 을 선택합니다.**

    > [!div class="mx-imgBorder"]
    > ![셀프 서비스 복구 요청 제출](images/self-serve-fig4.png)

홈 페이지가 표시될 때 요약 목록에서 서비스 요청을 보고 확인 전자 메일을 받을 수 있습니다.

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="why-am-i-getting-error-code-400-generic-client-service-error-401-unauthorized-service-error-or-error-403-forbidden-service-error"></a>오류 코드 400 "일반 클라이언트 서비스 오류", 401 "권한이 없는 서비스 오류" 또는 오류 403 "서비스 금지 오류"가 발생하는 이유는 무엇입니까?

사용자가 콘텐츠에 액세스할 수 Microsoft 365 권한이 없는 경우 문제가 있을 수 있습니다. 지원이 필요하면 Microsoft 365 전역 관리자에게 문의하세요.

### <a name="when-i-enter-my-shipping-address-and-i-get-an-error-message-that-no-shipping-offers-are-available"></a>When I enter my shipping address and I get an error message that no shipping offers are available?

Surface Self-Serve 및 서비스 베타는 현재 제한된 가용성을 제공합니다. 제품은 주소가 다음 국가 중 하나에 있는 경우만 사용할 수 있습니다.

오스트리아, 바레인, 벨기에, 불가리아, 크로아티아, 키프로스, 체코 공화국, 덴마크, 에스토니아, 핀란드, 프랑스, 독일, 그리스, 헝가리, 아일랜드, 이탈리아, 쿠웨이트, 라트비아, 리투아니아, 룩셈부르크, 몰타, 네덜란드, 오만, 폴란드, 포르투갈, 루마니아, 슬로바키아, 슬로베니아, 남아프리카, 스페인, 스웨덴 및 영국(북아일랜드 제외)

### <a name="where-can-i-see-orders-that-i-have-placed-through-the-microsoft-365-portal"></a>사이트 포털을 통해 주문한 주문은 어디에서 Microsoft 365 있나요?

Microsoft 365 관리 센터 - 서비스 요청으로 [이동하고](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/support/devicerepairs) 사용자 자격 증명으로 Microsoft 365 로그인합니다.

Microsoft 고객 지원을 통해 만든 주문은 보증 및 서비스 관리 모듈의 Self-Serve 표시되지 않습니다.

### <a name="why-am-i-unable-to-add-edit-or-delete-a-shipping-address"></a>Why am I unable to add, edit or delete a shipping address?

배송 주소를 추가, 편집 또는 삭제하는 기능만 Microsoft 365 전역 관리자 또는 대금 청구 관리자만 도움을 받을 수 있습니다. 도움을 요청하세요.  

### <a name="how-can-i-contact-microsoft-support-for-the-surface-self-serve-warranty-and-service-beta"></a>Surface 2013 보증 및 서비스 베타에 대해 Microsoft Self-Serve 어떻게 문의하나요?

Microsoft 관리 센터의 Surface 지원 모듈을 통해 지원에 직접 문의할 수 있습니다.

1. 사용자 자격 증명을 사용하여 Microsoft 관리 센터에 Microsoft 365 로그인합니다.
2. Surface **Device**Repairs >  >  **도움이 필요하세요?를** 선택하고 문제를 설명하세요.
3. 결과가 도움이되지 않는 경우 고객 지원에 **문의를**선택하고 문제 설명을 입력합니다. 연락처 번호와 전자 메일 주소를 확인하고 원하는 연락처 방법을 선택한 다음 문의 **를 선택합니다.**
