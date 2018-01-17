---
title: "中间层客户端应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13399243994943ddf853447e2e29f3695702aa35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="middle-tier-client-applications"></a>中间层客户端应用程序
本主题讨论特定于使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的中间层客户端应用程序的各种问题。  
  
## <a name="increasing-middle-tier-client-performance"></a>提高中间层客户端应用程序的性能  
 与以前的通信技术（如使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 的 Web 服务）相比，由于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的功能集比较丰富，所以创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端实例会更复杂。 例如，打开 <xref:System.ServiceModel.ChannelFactory%601> 对象时，该对象会与服务建立一个安全会话，该过程将增加客户端实例的启动时间。 通常，这些附加功能不会对客户端应用程序造成很大影响，这是因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端执行几次调用后将关闭。  
  
 然而，中间层客户端应用程序可以快速地创建许多 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端对象，因此，可以体验到已提高的初始化要求。 调用服务时，有两种主要的方法可以提高中间层应用程序的性能：  
  
-   缓存 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端对象，并尽可能在后续调用中重用它。  
  
-   创建一个 <xref:System.ServiceModel.ChannelFactory%601> 对象，然后使用该对象为每次调用创建新的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端通道对象。  
  
 使用这些方法时要考虑的问题包括：  
  
-   如果服务正在使用会话维护特定于客户端的状态，则您就无法使用多客户层请求重用中间层 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端，因为服务的状态与中间层客户端的状态相关联。  
  
-   如果服务必须基于每个客户端执行身份验证，则必须在中间层为每个传入的请求创建新客户端，而不是重用中间层 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端（或 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端通道对象），原因是在创建了 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端（或 <xref:System.ServiceModel.ChannelFactory%601>）后将无法修改中间层的客户端凭据。  
  
-   由于通道及其创建的客户端是线程安全的，因此它们可能不支持同时向网络中写入多条消息。 如果要发送较大的消息，特别是消息流，则发送操作可能会阻塞，因为它要等待另一个发送操作完成。 这会导致两种问题：缺少并发性；当控制流返回到重用信道的服务（即，共享的客户端调用了一种服务，该服务的代码路径会导致对共享的客户端进行回调）时，存在死锁的可能性。 无论重用什么类型的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端，情况都是如此。  
  
-   无论您是否共享出错的通道，您都必须处理它。 然而，重用通道时，出错通道可以关闭多个挂起的请求或发送。  
  
 有关示例，演示重复使用多个请求的客户端的最佳做法，请参阅[ASP.NET 客户端中的数据绑定](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)。  
  
 此外，如果客户端使用可用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化的数据类型，则会在运行时生成并编译这些数据类型的序列化代码，从而导致启动性能降低；但您可以提高那些客户端的启动性能。 [ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)可以通过从应用程序的已编译程序集生成必要的序列化代码提高这些应用程序的启动性能。 有关详细信息，请参阅[How to： 改善启动时间的 WCF 客户端应用程序使用 XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 客户端访问服务](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
