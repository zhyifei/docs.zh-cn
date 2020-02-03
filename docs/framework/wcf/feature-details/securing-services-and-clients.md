---
title: 保护服务和客户端的安全
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
# <a name="securing-services-and-clients"></a>保护服务和客户端的安全
本部分中的信息重点介绍 Windows Communication Foundation （WCF）中的编程安全性。 通常，这包括选择系统提供的相应绑定、设置安全元素的属性，然后设置服务行为的属性（控制检索凭据以供服务或客户端使用的方式）。 这些技术涵盖大多数用户在大多数情况下的安全要求，如[常见安全方案](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)中所示。 如果你的方案需要更多功能，请首先查看[具有自定义绑定的安全功能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md);如果解决方案不明显，请参阅[扩展安全性](../../../../docs/framework/wcf/extending/extending-security.md)。 如果要创建（或与）使用丰富声明的系统进行互操作，请参阅[授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)中的主题。  
  
## <a name="in-this-section"></a>本节内容  
 [WCF 安全编程](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 用于保护消息安全的编程模型概述。  
  
 [传输安全性概述](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 如何通过传输层保护消息安全概述。  
  
 [消息安全性](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 汇总在 Windows Communication Foundation （WCF）中使用消息级安全的原因。  
  
 [安全会话](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 讨论在保护 WCF 会话时需要注意的事项。  
  
 [使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 说明使用 X.509 证书时必须完成的一些常见任务。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>相关章节  
 [安全性概念](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [扩展安全性](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [常用安全方案](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [绑定与安全](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [使用自定义绑定的安全功能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [扩展安全性](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [授权](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>另请参阅

- [基本 WCF 编程](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [Windows Server App Fabric 的安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
