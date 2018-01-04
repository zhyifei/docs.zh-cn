---
title: "WCF 中的安全注意事项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f35bd56bdc69f8c57a7e46984778051b57b7a06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="security-considerations-in-wcf"></a>WCF 中的安全注意事项
本节中的主题列出在设计 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序时需要考虑的各种与安全相关的事项。  
  
## <a name="in-this-section"></a>本节内容  
 [信息泄漏](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 讨论信息可能泄露或受到攻击的各种方式，以及如何缓解这些问题。  
  
 [特权提升](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 讨论给予攻击者的权限超出最初授予的权限范围的后果，以及如何减轻这种后果。  
  
 [拒绝服务](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 讨论当系统无法正确处理消息时所发生的情况，以及如何缓解这一问题。  
  
 [篡改](../../../../docs/framework/wcf/feature-details/tampering.md)  
 讨论消息或消息传递的篡改以及如何缓解这种问题。  
  
 [重放攻击](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 讨论当攻击者复制通信双方之间的消息流并将该消息流向一方或多方重播时将发生的情况，以及如何缓解这一问题。  
  
 [安全会话的安全性注意事项](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 讨论在实现安全会话时影响安全的下列事项。  
  
 [不支持的方案](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 列出不支持某个特定安全方面的各种方案，应当避免或谨慎考虑这些方案。  
  
## <a name="reference"></a>参考  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>相关章节  
 [安全指导和最佳做法](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>请参阅  
 [安全性](../../../../docs/framework/wcf/feature-details/security.md)
