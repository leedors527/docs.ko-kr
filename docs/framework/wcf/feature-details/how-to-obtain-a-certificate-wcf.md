---
title: '방법: (WCF) 인증서 가져오기'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 21e9e0609ed63c4398f2df7ba718f8af17464b0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683632"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>방법: (WCF) 인증서 가져오기
Windows Communication Foundation (WCF) 중 하나를 사용 하 여 X.509 인증서를 사용 하는 기능의 먼저 인증서를 받습니다.  
  
### <a name="to-obtain-an-x509-certificate"></a>X.509 인증서를 받으려면  
  
1. 다음 중 하나를 선택합니다.  
  
    - VeriSign, Inc, 같은 인증 기관에서 인증서를 구입합니다.  
  
    - 자체 인증서 서비스를 설정하고 인증 기관이 인증서에 서명하도록 합니다. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Server Datacenter 및 Windows 2000 Datacenter Server에는 모두 PKI(공개 키 인프라)를 지원하는 인증서 서비스가 포함되어 있습니다. Windows Server 2008을 사용 합니다 [Active Directory 인증서 서비스](https://go.microsoft.com/fwlink/?LinkID=153483) 인증 기관을 관리 하는 역할입니다.  
  
    - 자체 인증서 서비스를 설정하고 인증서가 서명되지 않도록 합니다.  
  
    > [!NOTE]
    >  어떤 방법을 선택하든 관계없이 X.509 인증서를 포함하는 SOAP 요청의 수신자는 X.509 인증서를 신뢰해야 합니다. 이는 X.509 인증서나 인증서 체인의 발급자가 신뢰된 사용자 인증서에 있고 X.509 인증서가 신뢰되지 않은 인증서 저장소에 없음을 의미합니다.  
  
## <a name="see-also"></a>참고자료

- [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [방법: 개발 중 사용할 임시 인증서 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
