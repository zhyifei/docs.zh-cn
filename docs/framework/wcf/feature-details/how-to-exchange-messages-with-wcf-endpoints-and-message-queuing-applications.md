---
title: 如何：与 WCF 终结点和消息队列应用程序交换消息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 807a34ac50ea317ace42ec12eddcd9ec7cf3736b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491074"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="b8535-102">如何：与 WCF 终结点和消息队列应用程序交换消息</span><span class="sxs-lookup"><span data-stu-id="b8535-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="b8535-103">通过使用 MSMQ 集成绑定来与其他 WCF 消息转换 MSMQ 消息，可以将现有消息队列 (MSMQ) 应用程序集成与 Windows Communication Foundation (WCF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8535-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="b8535-104">这样，你可以调入 WCF 客户端从 MSMQ 接收方应用程序，以及从 MSMQ 发送方应用程序调入 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b8535-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="b8535-105">在本部分中，我们将介绍如何使用<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>（1） WCF 客户端和使用 System.Messaging 和 （2） MSMQ 应用程序客户端和 WCF 服务编写的 MSMQ 应用程序服务之间的排队通信。</span><span class="sxs-lookup"><span data-stu-id="b8535-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="b8535-106">有关完整示例，演示如何从 WCF 客户端调用 MSMQ 接收方应用程序的说明，请参阅[Windows Communication Foundation 到消息队列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)示例。</span><span class="sxs-lookup"><span data-stu-id="b8535-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="b8535-107">有关完整示例，演示如何从 MSMQ 客户端调用 WCF 服务的说明，请参阅[消息队列 Windows Communication foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)示例。</span><span class="sxs-lookup"><span data-stu-id="b8535-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="b8535-108">创建从 MSMQ 客户端接收消息的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="b8535-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="b8535-109">定义用于定义从 MSMQ 发送方应用程序，接收排队的消息的 WCF 服务的服务协定，如下面的代码示例中所示的接口。</span><span class="sxs-lookup"><span data-stu-id="b8535-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="b8535-110">实现该接口，将 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性应用于该类，如下面示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="b8535-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="b8535-111">创建一个配置文件，在该配置文件中指定 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>。</span><span class="sxs-lookup"><span data-stu-id="b8535-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="b8535-112">实例化一个 <xref:System.ServiceModel.ServiceHost> 对象，该对象使用所配置的绑定。</span><span class="sxs-lookup"><span data-stu-id="b8535-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="b8535-113">创建向 MSMQ 接收方应用程序发送消息的 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="b8535-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="b8535-114">定义用于定义发送排队消息到 MSMQ 接收方，WCF 客户端的服务协定，如下面的代码示例中所示的接口。</span><span class="sxs-lookup"><span data-stu-id="b8535-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="b8535-115">定义 WCF 客户端调用 MSMQ 接收方使用的客户端类。</span><span class="sxs-lookup"><span data-stu-id="b8535-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="b8535-116">创建一个配置文件，在该配置文件中指定 MsmqIntegrationBinding 绑定的用法。</span><span class="sxs-lookup"><span data-stu-id="b8535-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="b8535-117">创建该客户端类的一个实例，并调用消息接收服务所定义的方法。</span><span class="sxs-lookup"><span data-stu-id="b8535-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b8535-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8535-118">See Also</span></span>  
 [<span data-ttu-id="b8535-119">队列概述</span><span class="sxs-lookup"><span data-stu-id="b8535-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="b8535-120">如何：使用 WCF 终结点交换排队消息</span><span class="sxs-lookup"><span data-stu-id="b8535-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="b8535-121">Windows Communication Foundation 到消息队列</span><span class="sxs-lookup"><span data-stu-id="b8535-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="b8535-122">安装消息队列 (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="b8535-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="b8535-123">到 Windows Communication Foundation 的消息队列</span><span class="sxs-lookup"><span data-stu-id="b8535-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="b8535-124">基于消息队列的消息安全性</span><span class="sxs-lookup"><span data-stu-id="b8535-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
