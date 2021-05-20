---
title: 장애를 위한 디자인 함수 이해
description: 포괄 기술 랩의 Microsoft 포괄 디자인 참조
ms.localizationpriority: medium
ms.sitesec: library
author: InclusiveTechLab
ms.author: brycejo
ms.topic: article
ms.date: 05/20/2021
manager: krhunter
ms.prod: surface
ms.technology: windows
ms.openlocfilehash: d423fb3e4aa6f87ae0d6686607cd30920ecad5b8
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "11578294"
---
# <a name="understanding-function-to-design-for-disabilities"></a><span data-ttu-id="7add2-103">장애를 위한 디자인 함수 이해</span><span class="sxs-lookup"><span data-stu-id="7add2-103">Understanding Function to Design for Disabilities</span></span>
**<span data-ttu-id="7add2-104">포괄 기술 랩의 Microsoft 포괄 디자인 참조</span><span class="sxs-lookup"><span data-stu-id="7add2-104">A Microsoft Inclusive Design reference from the Inclusive Tech Lab</span></span>**

<span data-ttu-id="7add2-105">Microsoft의 포괄 디자인 관행에서 Microsoft는 당사가 없는 Microsoft에 대해 &ldquo; 아무것도 생각하지 않습니다. &rdquo; 장애가 있는 사람들이 더 많은 성과를 달성할 수 있도록 하는 제품 및 서비스를 만들 수 있도록 장애 커뮤니티를 사용하여 디자인합니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-105">In our Inclusive Design practice at Microsoft, we believe in &ldquo;Nothing About Us, Without Us.&rdquo; We design with the disability community to create products and services that empower people with disabilities to achieve more.</span></span> 

<span data-ttu-id="7add2-106">이 연습에서는 엔지니어와 디자이너가 작업하는 사용자에 대해 기능의 측면을 전달하기 위해 고심하는 경우를 관찰했습니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-106">In our practice we have observed that engineers and designers sometimes struggle to communicate the aspects of function for the people they are working with.</span></span> <span data-ttu-id="7add2-107">진단 또는 조건을 이해하려고 시도하면 생산성이 아날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-107">Trying to understand diagnosis or conditions can be counter productive.</span></span> <span data-ttu-id="7add2-108">대부분의 경우 의료 전문가가 아니기 때문에 어휘가 부족합니다. 또한 의료 용어가 항상 적절하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-108">Most of us aren’t medical professionals so we lack the vocabulary; also medical terminology isn’t always appropriate.</span></span>

<span data-ttu-id="7add2-109">이 참조를 작성하여 엔지니어와 디자이너가 상호 작용의 장벽으로 이어질 수 있는 기능의 측면과 이러한 장벽을 극복하는 데 필요한 촉진자에 대해 이해하고 논의할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-109">We created this reference to provide engineers and designers a way to understand and discuss the aspects of function that can lead to barriers in interaction, and the facilitators needed to overcome these barriers.</span></span> <span data-ttu-id="7add2-110">포괄 디자인 관행의 목표는 구현하기 전에 장벽을 인식하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-110">The goal of our inclusive design practice is to recognize the barriers before we implement them.</span></span> <span data-ttu-id="7add2-111">인간 다양성의 기능을 용이하게 하는 양식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-111">To create forms that facilitate the function of human diversity.</span></span>

<span data-ttu-id="7add2-112">이 작업의 영감은 세계보건 기구의 ICF(International [Classification of Functioning, Disability and](https://www.who.int/standards/classifications/international-classification-of-functioning-disability-and-health) Health)에서 영감을 주었다.</span><span class="sxs-lookup"><span data-stu-id="7add2-112">This work was inspired by the World Health Organization’s – [International Classification of Functioning, Disability and Health](https://www.who.int/standards/classifications/international-classification-of-functioning-disability-and-health) (ICF).</span></span> <span data-ttu-id="7add2-113">이 자료의 가이드를 통해 기술 분야를 가까우고 접근성 및 상황적으로 다가가기 위해 노력합니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-113">We strive in our guide to make this material concise, approachable, and contextual to our field of technology.</span></span> <span data-ttu-id="7add2-114">이 문서는 변화하고 성장할 것으로 예상하는 생생한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-114">This is a living document that we expect will change and grow.</span></span>

<span data-ttu-id="7add2-115">다시 말하기 위해 장애 커뮤니티를 디자인합니다. 이 참조는 상호 작용 문서화, 모집 심사자 및 설문 조사 작성, 사용성 검토 및 버그 작성과 같은 활동의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-115">To reiterate, we design WITH the disability community – we see this reference being part of activities like documenting interactions, creating recruitment screeners and surveys, and writing usability reviews and bugs.</span></span> <span data-ttu-id="7add2-116">제품 생성 프로세스의 일부로 이 자료를 효과적으로 활용하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-116">There are many potential ways that this material can be leveraged effectively as part of our product creation process.</span></span>

## <a name="what-this-is"></a><span data-ttu-id="7add2-117">What is what is</span><span class="sxs-lookup"><span data-stu-id="7add2-117">What this is</span></span>

<span data-ttu-id="7add2-118">이 작업의 목표는 포괄 디자인을 연습할 때 고려해야 할 인간 다양성 요인에 대한 참조를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-118">The goal of this work is to provide a reference of human diversity factors to consider when practicing inclusive design.</span></span> <span data-ttu-id="7add2-119">이 프레임워크는 매일 사용하는 기술에 대한 인지, 이동성, 시각, 청각, 음성 및 감각 요구를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-119">This framework outlines the cognitive, mobility, vision, hearing, speech, and sensory demands of the technology we all use daily.</span></span> <span data-ttu-id="7add2-120">접근성 있는 예를 통해 능력 수준과 제품 디자인 간에 불일치한 상호 작용을 경험할 때 사람이 직면할 수 있는 장벽을 설명하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-120">Through approachable examples, we try to illustrate barriers a person may face when they experience a mismatched interaction between their level of abilities and the design of a product.</span></span>

## <a name="what-this-is-not"></a><span data-ttu-id="7add2-121">해당되지 않는 것</span><span class="sxs-lookup"><span data-stu-id="7add2-121">What this is not</span></span>

<span data-ttu-id="7add2-122">이 참조는 접근성 솔루션을 만들기 위한 징계 지침이 아니며,</span><span class="sxs-lookup"><span data-stu-id="7add2-122">This reference is not a prescriptive guideline for creating accessibility solutions.</span></span> <span data-ttu-id="7add2-123">대신 사람이 발생할 수 있는 잠재적인 장벽을 식별하는 데 사용할 수 있는 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-123">Rather, it’s a resource you can use to identify potential barriers a person may encounter.</span></span> <span data-ttu-id="7add2-124">이 문서는 정적 문서가 아니며 커질 것 같은 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-124">It is important to remember that this document isn’t static and will grow.</span></span> <span data-ttu-id="7add2-125">포괄적이면서도 설명된 많은 인스턴스는 개인에 따라 서로 함께 발생할 수 있으며 서로 다르게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add2-125">While we strive to be comprehensive, many instances described can occur in conjunction with one another (depending on the individual) and may present differently from one person to another.</span></span>

## <a name="contents-of-this-reference"></a><span data-ttu-id="7add2-126">이 참조의 내용</span><span class="sxs-lookup"><span data-stu-id="7add2-126">Contents of this reference</span></span>

**[<span data-ttu-id="7add2-127">어떤 것을 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7add2-127">What is cognition?</span></span>](cognition.md)** <span data-ttu-id="7add2-128">— [주의](cognition-attention.md); [메모리](cognition-memory.md); [판단](cognition-judgment.md); [처리(속도)](cognition-processing-speed.md); [처리(이해)](cognition-processing-comprehension.md);</span><span class="sxs-lookup"><span data-stu-id="7add2-128">— [Attention](cognition-attention.md); [Memory](cognition-memory.md); [Judgment](cognition-judgment.md); [Processing (speed)](cognition-processing-speed.md); [Processing (comprehension)](cognition-processing-comprehension.md);</span></span> 

**[<span data-ttu-id="7add2-129">이동성이란?</span><span class="sxs-lookup"><span data-stu-id="7add2-129">What is mobility?</span></span>](mobility.md)** <span data-ttu-id="7add2-130">— [Grasp](mobility-grasp.md); [미세한 모터 기술](mobility-fine-motor-skills.md); [조정](mobility-coordination.md); [제어(자발적](mobility-control.md)이동과 자발적 이동) ; [속도](mobility-speed.md); [머슬 톤](mobility-muscle-tone.md); [Endurance](mobility-endurance.md); [Posture](mobility-posture.md);</span><span class="sxs-lookup"><span data-stu-id="7add2-130">— [Grasp](mobility-grasp.md); [Fine motor skills](mobility-fine-motor-skills.md); [Coordination](mobility-coordination.md); [Control (voluntary vs. involuntary movement)](mobility-control.md); [Speed](mobility-speed.md); [Muscle tone](mobility-muscle-tone.md); [Endurance](mobility-endurance.md); [Posture](mobility-posture.md);</span></span> 

**[<span data-ttu-id="7add2-131">시각이란?</span><span class="sxs-lookup"><span data-stu-id="7add2-131">What is vision?</span></span>](vision.md)** <span data-ttu-id="7add2-132">— [실명(무정)](vision-blindness-sightlessness.md) [저시력(부분적으로 시야)](vision-low-vision-partially-sighted.md); [감소된 시력](vision-decreased-acuity.md); [시각적 필드 손실](vision-visual-field-loss.md); [색맹](vision-color-blindness.md); [광도(광도)](vision-photophobia-light-sensitivity.md);</span><span class="sxs-lookup"><span data-stu-id="7add2-132">— [Blindness (sightlessness)](vision-blindness-sightlessness.md); [Low vision (partially sighted)](vision-low-vision-partially-sighted.md); [Decreased acuity](vision-decreased-acuity.md); [Visual field loss](vision-visual-field-loss.md); [Color blindness](vision-color-blindness.md); [Photophobia (light sensitivity)](vision-photophobia-light-sensitivity.md);</span></span> 

**[<span data-ttu-id="7add2-133">청각이란?</span><span class="sxs-lookup"><span data-stu-id="7add2-133">What is hearing?</span></span>](hearing.md)** <span data-ttu-id="7add2-134">— [청력 손실(경미한)](hearing-mild.md); [청력 손실(보통/심각)](hearing-moderate-severe.md); [청력 손실(심도 깊은)](hearing-profound.md); [청력 손실(비대칭)](hearing-asymmetrical.md);</span><span class="sxs-lookup"><span data-stu-id="7add2-134">— [Hearing Loss (mild)](hearing-mild.md); [Hearing loss (moderate/severe)](hearing-moderate-severe.md); [Hearing loss (profound)](hearing-profound.md); [Hearing loss (asymmetrical)](hearing-asymmetrical.md);</span></span> 

**[<span data-ttu-id="7add2-135">음성, 음성 및 통신이란?</span><span class="sxs-lookup"><span data-stu-id="7add2-135">What is voice, speech, and communication?</span></span>](voice-speech-communication.md)** <span data-ttu-id="7add2-136">— [Aphasia (receptive)](voice-speech-communication-aphasia-receptive.md); [고아(표현적)](voice-speech-communication-aphasia-expressive.md); [음성 품질](voice-speech-communication-speech-quality.md); [소셜 참여](voice-speech-communication-social-participation.md); [비언어 ;](voice-speech-communication-non-verbal.md)</span><span class="sxs-lookup"><span data-stu-id="7add2-136">— [Aphasia (receptive)](voice-speech-communication-aphasia-receptive.md); [Aphasia (expressive)](voice-speech-communication-aphasia-expressive.md); [Speech quality](voice-speech-communication-speech-quality.md); [Social participation](voice-speech-communication-social-participation.md); [Non-verbal](voice-speech-communication-non-verbal.md);</span></span> 

**[<span data-ttu-id="7add2-137">느낌과 지각이란?</span><span class="sxs-lookup"><span data-stu-id="7add2-137">What is sensation and perception?</span></span>](sensation-perception.md)** <span data-ttu-id="7add2-138">— [Vestibular](sensation-perception-vestibular.md); [치료의 아픈](sensation-perception-chronic-pain.md); [스킨 무결성](sensation-perception-skin-integrity.md); [센타(과민성 및 저감성)](sensation-perception-sensation.md); [Proprioception](sensation-perception-proprioception.md);</span><span class="sxs-lookup"><span data-stu-id="7add2-138">— [Vestibular](sensation-perception-vestibular.md); [Chronic pain](sensation-perception-chronic-pain.md); [Skin integrity](sensation-perception-skin-integrity.md); [Sensation (hypersensitive and hyposensitive)](sensation-perception-sensation.md); [Proprioception](sensation-perception-proprioception.md);</span></span> 

## <a name="created-by"></a><span data-ttu-id="7add2-139">만든 사람</span><span class="sxs-lookup"><span data-stu-id="7add2-139">Created by</span></span>

### <a name="authors"></a><span data-ttu-id="7add2-140">작성자</span><span class="sxs-lookup"><span data-stu-id="7add2-140">Authors</span></span>
<span data-ttu-id="7add2-141">Kaitlyn Jones, Bryce Johnson, Kris Hunter</span><span class="sxs-lookup"><span data-stu-id="7add2-141">Kaitlyn Jones, Bryce Johnson, Kris Hunter</span></span>

### <a name="illustrator"></a><span data-ttu-id="7add2-142">Illustrator</span><span class="sxs-lookup"><span data-stu-id="7add2-142">Illustrator</span></span>
<span data-ttu-id="7add2-143">Lou Patnode</span><span class="sxs-lookup"><span data-stu-id="7add2-143">Lou Patnode</span></span>

### <a name="editors"></a><span data-ttu-id="7add2-144">편집자</span><span class="sxs-lookup"><span data-stu-id="7add2-144">Editors</span></span>
<span data-ttu-id="7add2-145">Cat Jackson, Martina Dalton, Solomon Romney</span><span class="sxs-lookup"><span data-stu-id="7add2-145">Cat Jackson, Martina Dalton, Solomon Romney</span></span>

### <a name="special-thanks"></a><span data-ttu-id="7add2-146">특별 감사</span><span class="sxs-lookup"><span data-stu-id="7add2-146">Special Thanks</span></span>
<span data-ttu-id="7add2-147">Panos Panay, Robin Seiler, Allison Flanigan, Aimee Hayes, Steve Godfrey, John Porter, Tiffany Chen, Jenny Lay-Flurrie, Mary Bellard, David Dzumba, David Dame</span><span class="sxs-lookup"><span data-stu-id="7add2-147">Panos Panay, Robin Seiler, Allison Flanigan, Aimee Hayes, Steve Godfrey, John Porter, Tiffany Chen, Jenny Lay-Flurrie, Mary Bellard, David Dzumba, David Dame</span></span>


[comment]: # (Footer 포함)
