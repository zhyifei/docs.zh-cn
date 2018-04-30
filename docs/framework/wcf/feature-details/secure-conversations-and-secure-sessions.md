---
title: 安全对话和安全会话
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 502064ce30f6e117168834643a116d3983811fb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="secure-conversations-and-secure-sessions"></a>安全对话和安全会话
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的一项功能是能够在如下两个终结点之间建立安全会话：这两个终结点互相进行身份验证，并就加密和数字签名过程达成一致。 例如，服务终结点可能要求客户端终结点发送一个基于 X.509 证书的安全令牌，以便进行身份验证。 在对客户端进行身份验证之后，服务终结点将向客户端返回一个安全上下文令牌 (SCT)，该令牌随后将用于保护该会话中的所有后续消息。 通过建立这一安全会话，可使两个终结点之间交换的一组消息更有效率，因为 SCT 具有对称密钥。 在生成数字签名或加密一组数据时，与对称密钥相比，作为 X.509 证书基础的非对称密钥明显需要更多的计算能力。  
  
 启动策略 (6.2.7 节中定义[Ws-securitypolicy](http://go.microsoft.com/fwlink/?LinkId=99817)标准) 包含用于通道的安全和身份验证之前 RST/SCT 和 RSTR/SCT exchange 客户端的消息安全断言。 某些 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标准绑定具有一个 `Security.Message.EstablishSecurityContext` 属性，该属性用于控制是否使用安全对话。 当使用自定义绑定时由嵌套的安全绑定元素，不论是通过指示 bootstrap [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)在配置文件中，或通过调用<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>在代码中。  
  
 有关会话的详细信息，请参阅[使用会话](../../../../docs/framework/wcf/using-sessions.md)。  
  
## <a name="see-also"></a>请参阅  
 [会话、实例化和并发](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [如何：创建要求会话的服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
