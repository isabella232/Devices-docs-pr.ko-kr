---
title: 802.1x 유선 인증 사용
description: Surface Hub 디바이스에 802.1x 유선 인증 MDM 정책이 활성화되었습니다.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836252"
---
# 802.1 x 유선 인증 사용

[Windows 10 2017년 11월 14일 업데이트](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954)(빌드 15063.726)는 Surface Hub 디바이스에서 802.1x 유선 인증 MDM 정책을 사용합니다. 이 기능은 조직이 [IEEE 802.1x 인증 프로토콜](http://www.ieee802.org/1/pages/802.1x-2010.html)을 사용해 표준화된 유선 네트워크 인증을 적용할 수 있게 해줍니다. 이미 MDM을 통해 WLAN 프로필을 사용하는 무선 인증에 이 기능을 사용할 수 있습니다. 이 항목에서는 Surface Hub를 유선 인증에서 사용하도록 구성하는 방법을 설명합니다. 

Surface Hub에서 802.1x 유선 인증 적용 및 구현은 MDM [OMA-URI 정의](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings)를 통해 수행할 수 있습니다. 

설정할 기본 구성은 **LanProfile** 정책입니다. 선택한 인증 방법에 따라 사용자 또는 컴퓨터 인증서(예: 사용자/디바이스 인증서의 경우 [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) 또는 디바이스 인증서의 경우 [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp))를 추가하기 위해 **EapUserData** 정책이나 MDM 정책 등 다른 정책이 필요할 수 있습니다. 

## LanProfile 정책 요소

지원되는 802.1x 인증 방법 중 하나를 사용하여 Surface Hub를 구성하려면 다음 OMA URI를 활용합니다. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

이 OMA URI 노드는 XML의 텍스트 문자열을 매개 변수로 사용합니다. 매개 변수로 제공되는 XML은 [802.1X 스키마](https://msdn.microsoft.com/library/cc233003.aspx)의 요소를 포함하여 [유선 LAN 프로필 스키마](https://msdn.microsoft.com/library/cc233002.aspx)를 준수해야 합니다. 

대부분의 경우, 관리자 또는 사용자가 다음 NETSH 명령을 사용하여 이미 802.1X용 네트워크에서 구성된 기존 PC로부터 LanProfile XML을 내보낼 수 있습니다. 

```
netsh lan export profile folder=.
```

이 명령을 사용하면 다음 출력이 반환되고 현재 디렉터리에 **Ethernet.xml**이라는 파일이 배치됩니다. 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## EapUserData 정책 요소

선택한 인증 방법이 인증서가 아니라 사용자 이름 및 암호를 요구하는 경우 **EapUserData** 요소를 사용하여 네트워크를 인증하는 데 사용할 디바이스에 대한 자격 증명을 지정할 수 있습니다. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

이 OMA URI 노드는 XML의 텍스트 문자열을 매개 변수로 사용합니다. 매개 변수로 제공된 XML은 [PEAP MS-CHAPv2 사용자 속성 예시](https://msdn.microsoft.com/library/windows/desktop/bb891979)를 준수해야 합니다. 예시에서 모든 *test* 및 *ias-domain*을 사용자의 정보로 교체해야 합니다.



## 인증서 추가

선택한 인증 방법이 인증서 기반 인 경우에는 [프로비저닝 패키지를 만들거나](provisioning-packages-for-surface-hub.md), [MDM을 활용](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)하거나, 설정 (**설정**  >  **업데이트 및 보안**  >  **인증서**)에서 인증서를 가져와 적절 한 인증서 저장소의 Surface Hub 장치에 해당 인증서를 배포 해야 합니다. 인증서를 추가할 때 각 PFX가 인증서를 하나만 포함해야 합니다(PFX는 여러 인증서를 포함할 수 없음).

