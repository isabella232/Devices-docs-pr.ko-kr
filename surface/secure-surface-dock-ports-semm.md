---
title: Surface Enterprise 관리 모드를 사용 하는 보안 Surface Dock 2 포트 (SEMM)
description: 이 문서에서는 Surface Book 3, Surface 랩탑을 3 및 Surface Pro 7을 비롯 한 호환 가능한 Surface 장치에 연결 된 경우 Surface Dock 2에 대 한 UEFI 포트 설정을 구성 하는 지침을 제공 합니다.
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: 일반적인 문제 해결, 설치 문제
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 641d023b59426582130dcfb7e0d86c6f3af456e8
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114696"
---
# <span data-ttu-id="3f0d8-104">Surface Enterprise 관리 모드를 사용 하는 보안 Surface Dock 2 포트 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="3f0d8-104">Secure Surface Dock 2 ports with Surface Enterprise Management Mode (SEMM)</span></span>

## <span data-ttu-id="3f0d8-105">소개</span><span class="sxs-lookup"><span data-stu-id="3f0d8-105">Introduction</span></span>

<span data-ttu-id="3f0d8-106">Surface 엔터프라이즈 관리 모드 (SEMM)를 사용 하면 IT 관리자가 Windows installer 구성 패키지 ()에서 UEFI 설정을 구성 하 여 Surface Dock 2 포트를 보호 하 고 관리할 수 있습니다. MSI 파일)은 회사 환경에서 호환 되는 Surface 장치에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-106">Surface Enterprise Management Mode (SEMM) enables IT admins to secure and manage Surface Dock 2 ports by configuring UEFI settings in a Windows installer configuration package (.MSI file) deployed to compatible Surface devices across a corporate environment.</span></span>

### <span data-ttu-id="3f0d8-107">지원되는 디바이스</span><span class="sxs-lookup"><span data-stu-id="3f0d8-107">Supported devices</span></span>

<span data-ttu-id="3f0d8-108">SEMM이 있는 Surface Dock 2 관리는 Surface Book 3, Surface 노트북 3, Surface 노트북 Go, surface pro X에 연결 된 항구에서 사용할 수 있습니다. 이러한 호환 가능한 서피스 장치를 일반적으로 **호스트 장치**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-108">Managing Surface Dock 2 with SEMM is available for docks connected to Surface Book 3, Surface Laptop 3, Surface Laptop Go, Surface Pro 7, and Surface Pro X. These compatible Surface devices are commonly referred to as **host devices**.</span></span> <span data-ttu-id="3f0d8-109">패키지는 호스트 디바이스의 **인증** **또는 인증 여부에**따라 호스트 디바이스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-109">A package is applied to host devices based on if a host device is **authenticated** or **unauthenticated**.</span></span> <span data-ttu-id="3f0d8-110">구성 된 설정은 카메라와 같은 다른 기본 제공 주변 기기와 마찬가지로 Surface Dock 2를 관리 하기 위해 호스트 디바이스의 UEFI 계층에 있습니다 (IT 관리자).</span><span class="sxs-lookup"><span data-stu-id="3f0d8-110">Configured settings reside in the UEFI layer on host devices enabling you — the IT admin — to manage Surface Dock 2 just like any other built-in peripheral such as the camera.</span></span>

>[!NOTE]
><span data-ttu-id="3f0d8-111">Dock이 호환 되는 다음 장치 중 하나에 연결 된 경우에만 Surface Dock 2 포트를 관리할 수 있습니다: 가이드 3, Surface 랩톱 3 및 Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-111">You can manage Surface Dock 2 ports only when the dock is connected to one of the following compatible devices:  Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="3f0d8-112">UEFI 인증 된 정책 설정을 받지 않는 모든 장치는 본질적으로 인증 되지 않은 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-112">Any device that doesn't receive the UEFI Authenticated policy settings is inherently an unauthenticated device.</span></span>

### <span data-ttu-id="3f0d8-113">시나리오</span><span class="sxs-lookup"><span data-stu-id="3f0d8-113">Scenarios</span></span>

<span data-ttu-id="3f0d8-114">기업 호스트 장치에 로그인 한 승인 된 사람에 게 Surface Dock 2를 제한 하면 데이터 보호를 위한 다른 계층을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-114">Restricting Surface Dock 2 to authorized persons signed into a corporate host device provides another layer of data protection.</span></span> <span data-ttu-id="3f0d8-115">화면 도크 2를 잠그는 기능은 엄격한 보안 프로토콜과의 호환성을 유지 하면서 Dock의 기능 및 생산성 혜택을 원하는 매우 안전한 환경의 특정 고객에 게 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-115">This ability to lock down Surface Dock 2 is critical for specific customers in highly secure environments who want the functionality and productivity benefits of the dock while maintaining compliance with strict security protocols.</span></span> <span data-ttu-id="3f0d8-116">Surface Dock 2와 함께 사용 되는 SEMM은 특히 보안상의 이유로 USB 포트를 잠그려고 하는 고객을 위해 열려 있는 사무실 및 공유 공간에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-116">We anticipate SEMM used with Surface Dock 2 will be particularly useful in open offices and shared spaces especially for customers who want to lock USB ports for security reasons.</span></span> <span data-ttu-id="3f0d8-117">비디오 데모는 [Surface Dock 2의 경우 Semm](https://youtu.be/VLV19ISvq_s)을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-117">For a video demo, check out [SEMM for Surface Dock 2](https://youtu.be/VLV19ISvq_s).</span></span>

## <span data-ttu-id="3f0d8-118">Surface Dock 2에 대 한 UEFI 설정 구성 및 배포</span><span class="sxs-lookup"><span data-stu-id="3f0d8-118">Configuring and deploying UEFI settings for Surface Dock 2</span></span>

<span data-ttu-id="3f0d8-119">이 섹션에서는 다음 작업에 대 한 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-119">This section provides step-by-step guidance for the following tasks:</span></span>

1. <span data-ttu-id="3f0d8-120">[**SURFACE UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-120">Install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
1. <span data-ttu-id="3f0d8-121">공개 키 인증서를 만들거나 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-121">Create or obtain public key certificates.</span></span>
1. <span data-ttu-id="3f0d8-122">를 만듭니다. MSI 구성 패키지.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-122">Create an .MSI configuration package.</span></span>
   1. <span data-ttu-id="3f0d8-123">인증서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-123">Add your certificates.</span></span>
   1. <span data-ttu-id="3f0d8-124">Surface Dock 2 장치에 대해 16 자리 체크 인 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-124">Enter the 16-digit RN number for your Surface Dock 2 devices.</span></span>
   1. <span data-ttu-id="3f0d8-125">UEFI 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-125">Configure UEFI settings.</span></span>
1. <span data-ttu-id="3f0d8-126">구성 패키지를 빌드하여 대상 Surface 장치 (Surface Book 3, Surface 랩탑을 3 또는 Surface Pro 7)에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-126">Build and apply the configuration package to targeted Surface devices (Surface Book 3, Surface Laptop 3, or Surface Pro 7.)</span></span>

>[!NOTE]
><span data-ttu-id="3f0d8-127">**임의 숫자 (0)** 는 공장에서 프로 비전 되 고 도크 아래쪽에 작은 형식으로 인쇄 되는 고유한 16 자리 16 진수 코드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-127">The **Random Number (RN)** is a unique 16-digit hex code identifier which is provisioned at the factory, and printed in small type on the underside of the dock.</span></span> <span data-ttu-id="3f0d8-128">T e t는 대부분의 일련 번호와 다르므로 전자적으로 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-128">The RN differs from most serial numbers in that it can't be read electronically.</span></span> <span data-ttu-id="3f0d8-129">이는 실제로 장치에 액세스 하는 경우를 읽기만 하 여 소유권 증명을 설정 하는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-129">This ensures proof of ownership is primarily established only by reading the RN when physically accessing the device.</span></span> <span data-ttu-id="3f0d8-130">이 서비스는 구매 거래 중에도 얻을 수 있으며 Microsoft 인벤터리 시스템에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-130">The RN may also be obtained during the purchase transaction and is recorded in Microsoft inventory systems.</span></span>

### <span data-ttu-id="3f0d8-131">SEMM 및 Surface UEFI 구성자 설치</span><span class="sxs-lookup"><span data-stu-id="3f0d8-131">Install SEMM and Surface UEFI Configurator</span></span>

<span data-ttu-id="3f0d8-132">**SurfaceUEFI_Configurator_v2.71.139.0.msi**를 실행 하 여 semm을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-132">Install SEMM by running **SurfaceUEFI_Configurator_v2.71.139.0.msi**.</span></span> <span data-ttu-id="3f0d8-133">독립 실행형 설치 관리자 이며, Surface Dock 2에 대 한 구성 패키지를 만들고 배포 하는 데 필요한 모든 것이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-133">This is a standalone installer and contains everything you need to create and distribute configuration packages for Surface Dock 2.</span></span>

- <span data-ttu-id="3f0d8-134">Surface [Tools](https://www.microsoft.com/en-us/download/details.aspx?id=46703)에서 **surface UEFI 구성자** 을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-134">Download **Surface UEFI Configurator** from [Surface Tools for IT](https://www.microsoft.com/en-us/download/details.aspx?id=46703).</span></span>

## <span data-ttu-id="3f0d8-135">공개 키 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="3f0d8-135">Create public key certificates</span></span>

<span data-ttu-id="3f0d8-136">이 섹션에서는 Surface Dock 2의 포트를 관리 하는 데 필요한 인증서 만들기에 대 한 사양을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-136">This section provides specifications for creating the certificates needed to manage ports for Surface Dock 2.</span></span>

### <span data-ttu-id="3f0d8-137">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3f0d8-137">Prerequisites</span></span>

<span data-ttu-id="3f0d8-138">이 문서에서는 타사 공급자 로부터 인증서를 획득 하거나 이미 PKI 인증서 서비스에 대 한 전문 지식이 있고 사용자가 직접 만드는 방법을 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-138">This article assumes that you either obtain certificates from a third-party provider or you already have expertise in PKI certificate services and know how to create your own.</span></span>  <span data-ttu-id="3f0d8-139">한 가지 예외를 제외 하 고는 [Surface (엔터프라이즈 관리 모드)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 설명서에 설명 된 것 처럼 인증서 만들기에 대 한 일반 권장 사항을 숙지 하 고 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-139">You should be familiar with and follow the general recommendations for creating certificates as described in [Surface Enterprise Management Mode (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation, with one exception.</span></span> <span data-ttu-id="3f0d8-140">이 페이지에서 설명 하는 인증서는 **도크 인증 기관**에 대 한 30 년의 만료 약관이 필요 하며 **호스트**인증서의 경우 20 년입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-140">The certificates documented on this page require expiration terms of 30 years for the **Dock Certificate Authority**, and 20 years for the **Host Authentication Certificate**.</span></span>

<span data-ttu-id="3f0d8-141">자세한 내용은 [인증서 서비스 아키텍처](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) 설명서를 참조 하 고 [Windows Server 2019 내부 출력](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)또는 [Windows Server 2008 PKI 및](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) Microsoft Press에서 제공 하는 인증서 보안에서 해당 장을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-141">For more information, see [Certificate Services Architecture](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) documentation and review the appropriate chapters in [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277), or [Windows Server 2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) available from Microsoft Press.</span></span>

### <span data-ttu-id="3f0d8-142">루트 및 호스트 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f0d8-142">Root and host certificate requirements</span></span>

<span data-ttu-id="3f0d8-143">구성 패키지를 만들기 전에 Surface Dock 2의 소유권을 인증 하는 공개 키 인증서를 준비 하 고 디바이스 수명 주기 동안 소유권에 대 한 이후 변경 내용을 활용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-143">Prior to creating the configuration package, you need to prepare public key certificates that authenticate ownership of Surface Dock 2 and facilitate any subsequent changes in ownership during the device lifecycle.</span></span> <span data-ttu-id="3f0d8-144">호스트 및 프로비저닝 인증서의 경우 **클라이언트 인증 eku (확장 된 키 사용) 개체 식별자 (oid)** 로 알려진 eku id를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-144">The host and provisioning certificates require entering EKU IDs otherwise known as **Client Authentication Enhanced Key Usage (EKU) object identifiers (OIDs)**.</span></span>

<span data-ttu-id="3f0d8-145">필수 EKU 값은 표 1 및 표 2에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-145">The required EKU values are listed in Table 1 and Table 2.</span></span>

#### <span data-ttu-id="3f0d8-146">표 1.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-146">Table 1.</span></span> <span data-ttu-id="3f0d8-147">루트 및 도크 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f0d8-147">Root and Dock Certificate requirements</span></span>

|<span data-ttu-id="3f0d8-148">Certificate</span><span class="sxs-lookup"><span data-stu-id="3f0d8-148">Certificate</span></span>|<span data-ttu-id="3f0d8-149">알고리즘</span><span class="sxs-lookup"><span data-stu-id="3f0d8-149">Algorithm</span></span>|<span data-ttu-id="3f0d8-150">설명</span><span class="sxs-lookup"><span data-stu-id="3f0d8-150">Description</span></span>|<span data-ttu-id="3f0d8-151">만료</span><span class="sxs-lookup"><span data-stu-id="3f0d8-151">Expiration</span></span>|<span data-ttu-id="3f0d8-152">EKU OID</span><span class="sxs-lookup"><span data-stu-id="3f0d8-152">EKU OID</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="3f0d8-153">루트 인증 기관</span><span class="sxs-lookup"><span data-stu-id="3f0d8-153">Root Certificate Authority</span></span>|<span data-ttu-id="3f0d8-154">ECDSA_P384</span><span class="sxs-lookup"><span data-stu-id="3f0d8-154">ECDSA_P384</span></span>|<span data-ttu-id="3f0d8-155">-384 비트 프라임 elliptic 곡선 디지털 서명 알고리즘 (ECDSA)이 있는 루트 인증서</span><span class="sxs-lookup"><span data-stu-id="3f0d8-155">- Root certificate with 384-bit prime elliptic curve digital signature algorithm (ECDSA)</span></span><br><span data-ttu-id="3f0d8-156">-SHA 256 키 사용:</span><span class="sxs-lookup"><span data-stu-id="3f0d8-156">- SHA 256 Key Usage:</span></span><br><span data-ttu-id="3f0d8-157">CERT_DIGITAL_SIGNATURE_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="3f0d8-157">CERT_DIGITAL_SIGNATURE_KEY_USAGE</span></span><br><span data-ttu-id="3f0d8-158">-CERT_KEY_CERT_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="3f0d8-158">- CERT_KEY_CERT_SIGN_KEY_USAGE</span></span><br><span data-ttu-id="3f0d8-159">CERT_CRL_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="3f0d8-159">CERT_CRL_SIGN_KEY_USAGE</span></span>|<span data-ttu-id="3f0d8-160">30 년</span><span class="sxs-lookup"><span data-stu-id="3f0d8-160">30 years</span></span>|<span data-ttu-id="3f0d8-161">해당 없음</span><span class="sxs-lookup"><span data-stu-id="3f0d8-161">N/A</span></span>
|<span data-ttu-id="3f0d8-162">Dock 인증 기관</span><span class="sxs-lookup"><span data-stu-id="3f0d8-162">Dock Certificate Authority</span></span>|<span data-ttu-id="3f0d8-163">ECC P256 곡선</span><span class="sxs-lookup"><span data-stu-id="3f0d8-163">ECC P256 curve</span></span>|<span data-ttu-id="3f0d8-164">-256 비트 elliptic-커브 암호화 (ECC)를 사용 하는 호스트 인증서</span><span class="sxs-lookup"><span data-stu-id="3f0d8-164">- Host certificate with 256-bit elliptic-curve cryptography (ECC)</span></span><br><span data-ttu-id="3f0d8-165">-SHA 256 키 사용:</span><span class="sxs-lookup"><span data-stu-id="3f0d8-165">- SHA 256 Key Usage:</span></span><br><span data-ttu-id="3f0d8-166">CERT_KEY_CERT_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="3f0d8-166">CERT_KEY_CERT_SIGN_KEY_USAGE</span></span><br><span data-ttu-id="3f0d8-167">-Path 길이 제약 조건 = 0</span><span class="sxs-lookup"><span data-stu-id="3f0d8-167">- Path Length Constraint = 0</span></span>|<span data-ttu-id="3f0d8-168">20 년</span><span class="sxs-lookup"><span data-stu-id="3f0d8-168">20 years</span></span>|<span data-ttu-id="3f0d8-169">1.3.6.1.4.1.311.76.9.21.2</span><span class="sxs-lookup"><span data-stu-id="3f0d8-169">1.3.6.1.4.1.311.76.9.21.2</span></span><br><span data-ttu-id="3f0d8-170">1.3.6.1.4.1.311.76.9.21.3</span><span class="sxs-lookup"><span data-stu-id="3f0d8-170">1.3.6.1.4.1.311.76.9.21.3</span></span>|

   >[!NOTE]
   ><span data-ttu-id="3f0d8-171">Dock CA는. p7b 파일로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-171">The dock CA must be exported as a .p7b file.</span></span>

### <span data-ttu-id="3f0d8-172">관리 인증서 요구 사항 프로 비전</span><span class="sxs-lookup"><span data-stu-id="3f0d8-172">Provisioning Administration Certificate requirements</span></span>

<span data-ttu-id="3f0d8-173">각 호스트 장치에는 표 2에 나와 있는 것 처럼 doc CA와 두 개의 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-173">Each host device must have the doc CA and two certificates as shown in Table 2.</span></span>

#### <span data-ttu-id="3f0d8-174">표 2.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-174">Table 2.</span></span> <span data-ttu-id="3f0d8-175">관리 인증서 요구 사항 프로 비전</span><span class="sxs-lookup"><span data-stu-id="3f0d8-175">Provisioning administration certificate requirements</span></span>

|<span data-ttu-id="3f0d8-176">Certificate</span><span class="sxs-lookup"><span data-stu-id="3f0d8-176">Certificate</span></span>|<span data-ttu-id="3f0d8-177">알고리즘</span><span class="sxs-lookup"><span data-stu-id="3f0d8-177">Algorithm</span></span>|<span data-ttu-id="3f0d8-178">설명</span><span class="sxs-lookup"><span data-stu-id="3f0d8-178">Description</span></span>|<span data-ttu-id="3f0d8-179">EKU OID</span><span class="sxs-lookup"><span data-stu-id="3f0d8-179">EKU OID</span></span>|
|---|---|---|---|
|<span data-ttu-id="3f0d8-180">호스트 인증 인증서</span><span class="sxs-lookup"><span data-stu-id="3f0d8-180">Host authentication certificate</span></span>|<span data-ttu-id="3f0d8-181">ECC P256</span><span class="sxs-lookup"><span data-stu-id="3f0d8-181">ECC P256</span></span><br><span data-ttu-id="3f0d8-182">SHA 256</span><span class="sxs-lookup"><span data-stu-id="3f0d8-182">SHA 256</span></span>|<span data-ttu-id="3f0d8-183">호스트 디바이스의 id를 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-183">Proves the identity of the host device.</span></span>|<span data-ttu-id="3f0d8-184">1.3.6.1.4.1.311.76.9.21.2</span><span class="sxs-lookup"><span data-stu-id="3f0d8-184">1.3.6.1.4.1.311.76.9.21.2</span></span>|
|<span data-ttu-id="3f0d8-185">관리 인증서 프로 비전</span><span class="sxs-lookup"><span data-stu-id="3f0d8-185">Provisioning administration certificate</span></span>|<span data-ttu-id="3f0d8-186">ECC P256</span><span class="sxs-lookup"><span data-stu-id="3f0d8-186">ECC P256</span></span><br><span data-ttu-id="3f0d8-187">SHA256</span><span class="sxs-lookup"><span data-stu-id="3f0d8-187">SHA256</span></span>|<span data-ttu-id="3f0d8-188">현재 도크에 설치 되어 있는 CA를 바꿀 수 있도록 허용 하 여 도크 소유권 및/또는 정책 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-188">Enables you to change dock ownership and/or policy settings by allowing you to replace the CA that's currently installed on the dock.</span></span>|<span data-ttu-id="3f0d8-189">1.3.6.1.4.1.311.76.9.21.3</span><span class="sxs-lookup"><span data-stu-id="3f0d8-189">1.3.6.1.4.1.311.76.9.21.3</span></span><br><span data-ttu-id="3f0d8-190">1.3.6.1.4.1.311.76.9.21.4</span><span class="sxs-lookup"><span data-stu-id="3f0d8-190">1.3.6.1.4.1.311.76.9.21.4</span></span>|

   >[!NOTE]
   ><span data-ttu-id="3f0d8-191">호스트 인증 및 프로 비전 인증서는 .pfx 파일로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-191">The host authentication and provisioning certificates must be exported as .pfx files.</span></span>

### <span data-ttu-id="3f0d8-192">구성 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="3f0d8-192">Create configuration package</span></span>

<span data-ttu-id="3f0d8-193">인증서를 얻거나 만들었으면 대상 Surface 장치에 적용 되는 MSI 구성 패키지를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-193">When you have obtained or created the certificates, you’re ready to build the MSI configuration package that will be applied to target Surface devices.</span></span>

1. <span data-ttu-id="3f0d8-194">Surface **UEFI 구성자**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-194">Run Surface **UEFI Configurator**.</span></span>

   ![Surface UEFI 구성자 실행](images/secure-surface-dock-ports-semm-1.png)

1. <span data-ttu-id="3f0d8-196">**서피스 도크**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-196">Select **Surface Dock**.</span></span>

   ![서피스 도크 선택](images/secure-surface-dock-ports-semm-2.png)

1. <span data-ttu-id="3f0d8-198">인증서 페이지에서 적절 한 **인증서**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-198">On the certificate page, enter the appropriate **certificates**.</span></span>

   ![적절 한 인증서 입력](images/secure-surface-dock-ports-semm-3.png)

1. <span data-ttu-id="3f0d8-200">목록에 적절 한 도크 RNs를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-200">Add appropriate dock RNs to the list.</span></span>

   >[!NOTE]
   ><span data-ttu-id="3f0d8-201">여러 Surface Dock 2 장치에 대 한 구성 패키지를 만들 때 각 사용자를 수동으로 입력 하는 대신 RNs 목록을 포함 하는 .csv 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-201">When creating a configuration package for multiple Surface Dock 2 devices, instead of entering each RN manually, you can use a .csv file that contains a list of RNs.</span></span>

1. <span data-ttu-id="3f0d8-202">USB 데이터, 이더넷 및 오디오 포트에 대 한 정책 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-202">Specify your policy settings for USB data, Ethernet, and Audio ports.</span></span> <span data-ttu-id="3f0d8-203">UEFI 구성자를 사용 하 여 인증 된 사용자 (인증 된 정책) 및 인증 되지 않은 사용자 (인증 되지 않은 정책)의 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-203">UEFI Configurator lets you configure policy settings for authenticated users (Authenticated Policy) and unauthenticated users (Unauthenticated Policy).</span></span> <span data-ttu-id="3f0d8-204">다음 그림에서는 인증 된 사용자에 대해 포트 액세스를 설정 하 고 인증 되지 않은 사용자의 경우 해제 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-204">The following figure shows port access turned on for authenticated users and turned off for unauthenticated users.</span></span>

   ![활성화 또는 비활성화 하려는 구성 요소를 선택 합니다.](images/secure-surface-dock-ports-semm-4.png)

   - <span data-ttu-id="3f0d8-206">인증 된 사용자는에서 구성한 대로 적절 한 인증서가 설치 된 Surface 장치를 참조 합니다. 대상 장치에 적용 한 MSI 구성 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-206">Authenticated user refers to a Surface Device that has the appropriate certificates installed, as configured in the .MSI configuration package that you applied to target devices.</span></span> <span data-ttu-id="3f0d8-207">이는 장치에 로그인 하는 모든 사용자 인증 된 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-207">It applies to any user authenticated user who signs into the device.</span></span> 
   - <span data-ttu-id="3f0d8-208">인증 되지 않은 사용자가 다른 장치를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-208">Unauthenticated user refers to any other device.</span></span>
   - <span data-ttu-id="3f0d8-209">' **재설정** '을 선택 하 여 해당 도크가 수락한 이전 구성 패키지를 모두 제거 하는 특별 한 "Reset" 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-209">Select **Reset** to create a special “Reset” package that will remove any previous configuration package that the dock had accepted.</span></span>

1. <span data-ttu-id="3f0d8-210">지정 된 대로 패키지를 만들려면 **빌드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-210">Select **Build** to create the package as specified.</span></span>

### <span data-ttu-id="3f0d8-211">Surface Dock 2에 구성 패키지 적용</span><span class="sxs-lookup"><span data-stu-id="3f0d8-211">Apply the configuration package to a Surface Dock 2</span></span>

1. <span data-ttu-id="3f0d8-212">Surface UEFI 구성자에서 생성 한 MSI 파일을 사용 하 여 Surface host 장치에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-212">Take the MSI file that the Surface UEFI Configurator generated and install it on a Surface host device.</span></span> <span data-ttu-id="3f0d8-213">호환 되는 호스트 장치는 Surface Book 3, Surface 랩톱 3 또는 Surface Pro 7입니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-213">Compatible host devices are Surface Book 3, Surface Laptop 3, or Surface Pro 7.</span></span>
1. <span data-ttu-id="3f0d8-214">호스트 장치를 Surface Dock 2에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-214">Connect the host device to the Surface Dock 2.</span></span> <span data-ttu-id="3f0d8-215">Dock UEFI 정책 설정이 적용 되는 경우 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-215">When you connect the dock UEFI policy settings are applied.</span></span>

## <span data-ttu-id="3f0d8-216">Surface 앱을 사용 하 여 관리 상태 확인</span><span class="sxs-lookup"><span data-stu-id="3f0d8-216">Verify managed state using the Surface App</span></span>

<span data-ttu-id="3f0d8-217">구성 패키지를 적용 한 후에는 모든 Surface 장치에 기본적으로 설치 되는 Surface 앱에서 직접 도크의 결과 정책 상태를 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-217">Once you have applied the configuration package, you can quickly verify the resultant policy state of the dock directly from the Surface App, installed by default on all Surface devices.</span></span> <span data-ttu-id="3f0d8-218">Surface 앱이 장치에 없으면 Microsoft Store에서 다운로드 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-218">If Surface App isn't present on the device, you can download and install it from the Microsoft Store.</span></span>

### <span data-ttu-id="3f0d8-219">테스트 시나리오</span><span class="sxs-lookup"><span data-stu-id="3f0d8-219">Test scenario</span></span>

<span data-ttu-id="3f0d8-220">목적: 인증 된 사용자만 포트에 액세스할 수 있도록 정책 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-220">Objective: Configure policy settings to allow port access by authenticated users only.</span></span>

1. <span data-ttu-id="3f0d8-221">인증 된 사용자에 대 한 모든 포트를 설정 하 고 인증 되지 않은 사용자에 대해 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-221">Turn on all ports for authenticated users and turn them off for unauthenticated users.</span></span>

   ![인증 된 사용자에 대해 포트 사용](images/secure-surface-dock-ports-semm-4.png)

1. <span data-ttu-id="3f0d8-223">대상 장치에 구성 패키지를 적용 한 다음 Surface Dock 2를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-223">Apply the configuration package to your target device and then connect Surface Dock 2.</span></span>

1. <span data-ttu-id="3f0d8-224">Surface **dock을 열고** surface **dock** 을 선택 하 여 표면 도크의 결과 정책 상태를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-224">Open **Surface App** and select **Surface Dock** to view the resultant policy state of your Surface Dock.</span></span> <span data-ttu-id="3f0d8-225">정책 설정이 적용 된 경우 Surface App에서 포트를 사용할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-225">If the policy settings are applied, Surface App will indicate that ports are available.</span></span>

   ![인증 된 사용자가 사용할 수 있는 모든 포트를 표시 하는 Surface 앱](images/secure-surface-dock-ports-semm-5.png)

1. <span data-ttu-id="3f0d8-227">이제 정책 설정이 인증 되지 않은 사용자의 모든 포트를 성공적으로 해제 했는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-227">Now you need to verify that the policy settings have successfully turned off all ports for unauthenticated users.</span></span> <span data-ttu-id="3f0d8-228">생성 된 구성 패키지의 관리 범위 외부에 있는 Surface Dock 2를 관리 되지 않는 디바이스 (예:)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-228">Connect Surface Dock 2 to an unmanaged device, i.e., any Surface device outside the scope of management for the configuration package you created.</span></span>

1. <span data-ttu-id="3f0d8-229">**Surface 앱** 을 열고 **서피스 도크**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-229">Open **Surface App** and select **Surface Dock**.</span></span> <span data-ttu-id="3f0d8-230">결과 정책 상태는 포트가 꺼져 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-230">The resultant policy state will indicate ports are turned off.</span></span>

   ![<span data-ttu-id="3f0d8-231">인증 되지 않은 사용자에 대 한 포트 해제를 보여 주는 Surface 앱</span><span class="sxs-lookup"><span data-stu-id="3f0d8-231">Surface app showing ports turned off for unauthenticated users</span></span> ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
><span data-ttu-id="3f0d8-232">장치의 소유권을 유지 하 되 모든 사용자에 게 모든 권한을 허용 하려는 경우 모든 기능이 설정 된 새 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-232">If you want to keep ownership of the device, but allow all users full access, you can make a new package with everything turned on.</span></span> <span data-ttu-id="3f0d8-233">장치에 대 한 제한 및 소유권을 완전히 제거 하려면 (비관리형으로 만들려면 Surface UEFI 구성자에서 **재설정** 을 선택 하 여 대상 장치에 적용할 패키지를 만듭니다.)</span><span class="sxs-lookup"><span data-stu-id="3f0d8-233">If you wish to completely remove the restrictions and ownership of the device (make it unmanaged), select **Reset** in Surface UEFI Configurator to create a package to apply to target devices.</span></span>

<span data-ttu-id="3f0d8-234">축하합니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-234">Congratulations.</span></span> <span data-ttu-id="3f0d8-235">대상 호스트 디바이스에서 Surface Dock 2 포트를 관리 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3f0d8-235">You have successfully managed Surface Dock 2 ports on targeted host devices.</span></span>

## <span data-ttu-id="3f0d8-236">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="3f0d8-236">Learn more</span></span>

- [<span data-ttu-id="3f0d8-237">Surface 엔터프라이즈 관리 모드 (SEMM) 설명서</span><span class="sxs-lookup"><span data-stu-id="3f0d8-237">Surface Enterprise Management Mode (SEMM) documentation</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [<span data-ttu-id="3f0d8-238">인증서 서비스 아키텍처</span><span class="sxs-lookup"><span data-stu-id="3f0d8-238">Certificate Services Architecture</span></span>](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [<span data-ttu-id="3f0d8-239">Windows Server 2019 내부 출력</span><span class="sxs-lookup"><span data-stu-id="3f0d8-239">Windows Server 2019 Inside Out</span></span>](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [<span data-ttu-id="3f0d8-240">Windows Server 2008 PKI 및 인증서 보안</span><span class="sxs-lookup"><span data-stu-id="3f0d8-240">Windows Server 2008 PKI and Certificate Security</span></span>](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
