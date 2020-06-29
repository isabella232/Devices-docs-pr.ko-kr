---
title: Surface Hub SSD 교체
ms.reviewer: ''
manager: laurawi
description: Surface Hub의 고체 상태 드라이브를 바꾸는 방법에 대해 알아봅니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 17e6018478b608b34c47ce0acd602deb70035474
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835127"
---
# <span data-ttu-id="1db1d-103">Surface Hub SSD 교체</span><span class="sxs-lookup"><span data-stu-id="1db1d-103">Surface Hub SSD replacement</span></span>

<span data-ttu-id="1db1d-104">[Surface Hub 복구 도구](surface-hub-recovery-tool.md) 를 사용 하 여 해당 SSD (고체 스테이트 드라이브)를 제거 하 고 대체 드라이브를 전송 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-104">You might need to remove the solid state drive (SSD) from your Surface Hub so that you can reimage it using the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) or because you've been sent a replacement drive.</span></span> <span data-ttu-id="1db1d-105">Windows 업데이트 실패, BitLocker 문제, 리셋 오류 또는 하드웨어 오류 등의 운영 체제를 부팅할 수 없는 경우에 SSD를 다시 이미지로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-105">You would reimage your SSD when the operating system is no longer bootable, such as from a Windows update failure, BitLocker issues, reset failure, or hardware failure.</span></span> 


>[!WARNING]
><span data-ttu-id="1db1d-106">AC 스위치에서 Surface Hub가 꺼져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-106">Make sure the Surface Hub is turned off at the AC switch.</span></span>

1. <span data-ttu-id="1db1d-107">아래 설명 된 위치에 있는 Surface Hub의 뒤쪽 부분에서 SSD 구획 도어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-107">Locate the SSD compartment door on the rear, upper portion of the Surface Hub in the locations illustrated below.</span></span> <span data-ttu-id="1db1d-108">문이 열려 있는 환기 슬롯이 없기 때문에 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-108">The door is identifiable as it doesn't have open ventilation slots.</span></span>

    ![SSD 구획 도어](images/ssd-location.png)

    *<span data-ttu-id="1db1d-110">Surface Hub 하드 드라이브 위치</span><span class="sxs-lookup"><span data-stu-id="1db1d-110">Surface Hub hard drive locations</span></span>*

2. <span data-ttu-id="1db1d-111">하드 드라이브의 구획 도어에서 잠금 탭을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-111">Locate the locking tab on the hard drive compartment door.</span></span> <span data-ttu-id="1db1d-112">Surface Hub 55에서 잠금 탭은 도어의 왼쪽에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-112">On the Surface Hub 55, the locking tab will be located on the left-hand side of the door.</span></span> <span data-ttu-id="1db1d-113">Surface Hub 84에는 그림과 같이 오른쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-113">On the Surface Hub 84, it will be on the right-hand side as shown in the illustration.</span></span>

    ![SSD 구획 잠금 탭](images/ssd-lock-tab.png)

    *<span data-ttu-id="1db1d-115">하드 드라이브 컴파트먼트 도어의 잠금 탭</span><span class="sxs-lookup"><span data-stu-id="1db1d-115">Locking tab on hard drive compartment door</span></span>*

3. <span data-ttu-id="1db1d-116">들어올리기 구획 도어를 열어 하드 드라이브에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-116">Lift open the compartment door to access the hard drive.</span></span>

    ![올립니다](images/ssd-lift-door.png)

    *<span data-ttu-id="1db1d-118">구획 도어 들어올리기</span><span class="sxs-lookup"><span data-stu-id="1db1d-118">Lift compartment door</span></span>*

4. <span data-ttu-id="1db1d-119">후면 덮개 아래에 부분적으로 가려져 있을 수 있는 당기기 탭을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-119">Locate the pull tab, which may be partially hidden under the rear cover.</span></span> <span data-ttu-id="1db1d-120">탭을 당겨 구획에서 하드 드라이브를 꺼냅니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-120">Pull on the tab to eject the hard drive from the compartment.</span></span>

    ![풀](images/ssd-pull-tab.png)

    *<span data-ttu-id="1db1d-122">당기기 탭</span><span class="sxs-lookup"><span data-stu-id="1db1d-122">Pull tab</span></span>*

5. <span data-ttu-id="1db1d-123">딸깍 소리가 들릴 때까지 대체 드라이브를 제자리에 밉니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-123">Slide the replacement drive into place until you hear it click.</span></span>

    ![드라이브의 슬라이드](images/ssd-click.png)
    
    *<span data-ttu-id="1db1d-125">교체 드라이브를 제자리에 밀기</span><span class="sxs-lookup"><span data-stu-id="1db1d-125">Slide replacement drive into place</span></span>*

6. <span data-ttu-id="1db1d-126">구획 도어를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-126">Close the compartment door.</span></span>

7. <span data-ttu-id="1db1d-127">Surface Hub에 전기를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db1d-127">Apply power to the Surface Hub.</span></span>
