---
title: "如何：与 WCF 终结点和消息队列应用程序交换消息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75b18dab37a18723671cebf51c3cc943b907b38a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>如何：与 WCF 终结点和消息队列应用程序交换消息
通过使用 MSMQ 集成绑定，可以将现有消息队列 (MSMQ) 应用程序与 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序进行集成，从而在 MSMQ 消息与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 消息之间进行转换。 利用这一功能，可以在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端调用 MSMQ 接收方应用程序，也可以在 MSMQ 发送方应用程序中调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。  
  
 本节中，将说明如何将 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 用于 (1) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端和使用 System.Messaging 编写的 MSMQ 应用程序服务之间的排队通信，以及 (2) MSMQ 应用程序客户端和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务之间的排队通信。  
  
 有关完整示例，演示如何调用 MSMQ 接收方应用程序从[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端，请参阅[Windows Communication Foundation 到消息队列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)示例。  
  
 有关完整示例，演示如何调用[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务从 MSMQ 客户端，请参阅[消息队列 Windows Communication foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)示例。  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>创建从 MSMQ 客户端接收消息的 WCF 服务  
  
1.  定义一个接口，该接口为从 MSMQ 发送方应用程序接收排队消息的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务定义服务协定，如下面的示例代码所示。  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  实现该接口，将 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性应用于该类，如下面示例代码所示。  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  创建一个配置文件，在该配置文件中指定 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>。  
  
  
  
4.  实例化一个 <xref:System.ServiceModel.ServiceHost> 对象，该对象使用所配置的绑定。  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>创建向 MSMQ 接收方应用程序发送消息的 WCF 客户端  
  
1.  定义一个接口，该接口为向 MSMQ 接收方发送排队消息的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端定义服务协定，如下面的示例代码所示。  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  定义一个客户端类，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端使用该类来调用 MSMQ 接收方。  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  创建一个配置文件，在该配置文件中指定 MsmqIntegrationBinding 绑定的用法。  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  创建该客户端类的一个实例，并调用消息接收服务所定义的方法。  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>另请参阅  
 [队列概述](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [如何： 交换排队消息的 WCF 终结点](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [Windows Communication Foundation 到消息队列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [安装消息队列 (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [消息队列到 Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [通过消息队列的消息安全](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
