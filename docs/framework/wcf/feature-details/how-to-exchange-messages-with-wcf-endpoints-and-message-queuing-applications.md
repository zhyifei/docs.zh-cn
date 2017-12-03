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
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="fb4e2-102">如何：与 WCF 终结点和消息队列应用程序交换消息</span><span class="sxs-lookup"><span data-stu-id="fb4e2-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="fb4e2-103">通过使用 MSMQ 集成绑定，可以将现有消息队列 (MSMQ) 应用程序与 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序进行集成，从而在 MSMQ 消息与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 消息之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-103">You can integrate existing Message Queuing (MSMQ) applications with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications by using the MSMQ integration binding to convert MSMQ messages to and from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] messages.</span></span> <span data-ttu-id="fb4e2-104">利用这一功能，可以在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端调用 MSMQ 接收方应用程序，也可以在 MSMQ 发送方应用程序中调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-104">This allows you to call into MSMQ receiver applications from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients as well as call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="fb4e2-105">本节中，将说明如何将 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 用于 (1) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端和使用 System.Messaging 编写的 MSMQ 应用程序服务之间的排队通信，以及 (2) MSMQ 应用程序客户端和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务之间的排队通信。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="fb4e2-106">有关完整示例，演示如何调用 MSMQ 接收方应用程序从[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端，请参阅[Windows Communication Foundation 到消息队列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)示例。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="fb4e2-107">有关完整示例，演示如何调用[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务从 MSMQ 客户端，请参阅[消息队列 Windows Communication foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)示例。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-107">For a complete sample that demonstrates how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="fb4e2-108">创建从 MSMQ 客户端接收消息的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="fb4e2-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="fb4e2-109">定义一个接口，该接口为从 MSMQ 发送方应用程序接收排队消息的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务定义服务协定，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-109">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="fb4e2-110">实现该接口，将 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性应用于该类，如下面示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="fb4e2-111">创建一个配置文件，在该配置文件中指定 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="fb4e2-112">实例化一个 <xref:System.ServiceModel.ServiceHost> 对象，该对象使用所配置的绑定。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="fb4e2-113">创建向 MSMQ 接收方应用程序发送消息的 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="fb4e2-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="fb4e2-114">定义一个接口，该接口为向 MSMQ 接收方发送排队消息的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端定义服务协定，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-114">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="fb4e2-115">定义一个客户端类，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端使用该类来调用 MSMQ 接收方。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-115">Define a client class that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="fb4e2-116">创建一个配置文件，在该配置文件中指定 MsmqIntegrationBinding 绑定的用法。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="fb4e2-117">创建该客户端类的一个实例，并调用消息接收服务所定义的方法。</span><span class="sxs-lookup"><span data-stu-id="fb4e2-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fb4e2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb4e2-118">See Also</span></span>  
 [<span data-ttu-id="fb4e2-119">队列概述</span><span class="sxs-lookup"><span data-stu-id="fb4e2-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="fb4e2-120">如何： 交换排队消息的 WCF 终结点</span><span class="sxs-lookup"><span data-stu-id="fb4e2-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="fb4e2-121">Windows Communication Foundation 到消息队列</span><span class="sxs-lookup"><span data-stu-id="fb4e2-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="fb4e2-122">安装消息队列 (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="fb4e2-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="fb4e2-123">消息队列到 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fb4e2-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="fb4e2-124">通过消息队列的消息安全</span><span class="sxs-lookup"><span data-stu-id="fb4e2-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
