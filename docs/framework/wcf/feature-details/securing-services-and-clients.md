---
title: 서비스 및 클라이언트에 보안 설정
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 719ab26198bd7b83310025e03e541fa11b109612
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746411"
---
# <a name="securing-services-and-clients"></a>서비스 및 클라이언트에 보안 설정
本部分中的信息重点介绍 Windows Communication Foundation （WCF）中的编程安全性。 일반적으로 여기에는 적절한 시스템 제공 바인딩 선택, 보안 요소의 속성 설정 및 서비스나 클라이언트에서 사용할 자격 증명을 검색하는 방법을 제어하는 서비스 동작의 속성 설정이 포함됩니다. 这些技术涵盖大多数用户在大多数情况下的安全要求，如[常见安全方案](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)中所示。 如果你的方案需要更多功能，请首先查看[具有自定义绑定的安全功能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md);如果解决方案不明显，请参阅[扩展安全性](../../../../docs/framework/wcf/extending/extending-security.md)。 如果要创建（或与）使用丰富声明的系统进行互操作，请参阅[授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)中的主题。  
  
## <a name="in-this-section"></a>섹션 내용  
 [WCF 보안 프로그래밍](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 메시지 보안을 설정하는 데 사용되는 프로그래밍 모델의 개요입니다.  
  
 [전송 보안 개요](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 전송 계층에서 메시지 보안을 설정하는 방법의 개요입니다.  
  
 [메시지 보안](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 汇总在 Windows Communication Foundation （WCF）中使用消息级安全的原因。  
  
 [보안 세션](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 讨论在保护 WCF 会话时需要注意的事项。  
  
 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 X.509 인증서를 사용할 때 필요한 일반 작업 중 일부에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>관련 섹션  
 [보안 개념](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [일반적인 보안 시나리오](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [바인딩 및 보안](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [사용자 지정 바인딩을 사용하는 보안 기능](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [보안 확장](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>另请参阅

- [기본 WCF 프로그래밍](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [Windows Server App Fabric 的安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
