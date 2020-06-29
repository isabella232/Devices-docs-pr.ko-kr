---
title: Surface Hub에서 정규화된 도메인 이름 사용
description: 설치 문제, Exchange ActiveSync 오류를 포함하여 일반적인 문제를 해결합니다.
keywords:
- 일반적인 문제 해결
- 설치 문제
- Exchange ActiveSync 오류
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834852"
---
# <span data-ttu-id="7a022-106">비즈니스용 Skype에 대한 도메인 이름 구성</span><span class="sxs-lookup"><span data-stu-id="7a022-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="7a022-107">몇 가지 시나리오에서는 비즈니스용 Skype 서버의 도메인 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="7a022-108">**DNS 접미사가 여러 개임** - 비즈니스용 Skype 인프라에 비연속 네임스페이스가 있는 경우(예: 하나 이상의 서버에 Skype 비즈니스용 SIP(로그인 주소)의 접미사와 일치하지 않는 DNS 접미사가 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="7a022-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="7a022-109">**비즈니스용 Skype와 Exchange 접미사가 서로 다름** - 비즈니스용 Skype에 대한 로그인 주소의 접미사가 디바이스 계정에 사용되는 Exchange 주소 접미사와 다른 경우</span><span class="sxs-lookup"><span data-stu-id="7a022-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="7a022-110">**인증서 작업** -온-프레미스 비즈니스용 Skype 서버를 사용 하는 대규모 조직은 일반적으로 자체 루트 CA (인증 기관)와 함께 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="7a022-111">일반적으로 CA 도메인은 비즈니스용 Skype 서버 도메인과 다르며 이로 인해 인증서를 신뢰할 수 없어 로그인에 실패하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="7a022-112">Skype에서는 트러스트 관계 설정을 위해 인증서의 도메인 이름에 대해 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="7a022-113">일반적으로 기업에서는 그룹 정책을 사용하여 Skype 바탕 화면으로 이 FQDN을 푸시하지만 Surface Hub에서는 그룹 정책이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="7a022-114">비즈니스용 Skype 서버에 대한 도메인 이름을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="7a022-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="7a022-115">Surface Hub에서 **설정**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="7a022-116">**Surface Hub**, **전화 및 오디오**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="7a022-117">**비즈니스용 Skype 구성**에서 **도메인 이름 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="7a022-118">비즈니스용 Skype 서버의 도메인 이름을 입력하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="7a022-119">여러 도메인 이름을 쉼표로 구분하여 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="7a022-120">예를 들면 lync.com, outlook.com, lync.glbdns.microsoft.com입니다.</span><span class="sxs-lookup"><span data-stu-id="7a022-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![설정에 비즈니스용 Skype FQDN 추가](images/system-settings-add-fqdn.png)
