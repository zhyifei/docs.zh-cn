---
title: "扩展性介绍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3f045fd35ef57be51c10d7948275899c1ae4f01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-extensibility"></a>扩展性介绍
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 应用程序模型设计用于解决任何分布式应用程序的大部分通信要求。 但是，总是会存在一些默认应用程序模型和系统提供的实现不支持的情况。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 扩展性模型旨在支持自定义方案，方法是通过修改各个级别的系统行为，甚至替换整个应用程序模型。 本主题概述各个扩展范围并指出关于每个范围的更多信息。  
  
## <a name="areas-to-extend"></a>要扩展的范围  
 可以扩展：  
  
-   应用程序运行库。 这将扩展应用程序消息的调度和处理。 此范围还包括扩展安全系统、元数据系统、序列化系统以及将应用程序与基础通道系统相连的绑定和绑定元素。  
  
-   通道和通道运行库。 这将扩展在消息级别运行的系统，用于提供协议、传输和编码支持。  
  
-   主机运行库。 此范围将主机应用程序域的关系扩展到通道和应用程序运行库。  
  
### <a name="extending-the-application-runtime"></a>扩展应用程序运行库  
 在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序中，发往相应通道的消息与发往应用程序本身的消息之间存在差别。 通道消息支持某些与通道相关的功能，如建立安全对话或可靠会话。 这些消息对于应用程序运行库不可用；涉及应用程序层之前，将处理这些消息。  
  
 应用程序消息中包含发往客户端或发往您或您的客户创建的服务操作的数据。 这些消息可用于采用消息或对象形式的应用程序级扩展系统，具体取决于您的需要。  
  
 所有消息都通过通道系统传递；只有应用程序消息是从通道系统传入应用程序的。 若要创建新的通道级功能，必须扩展通道系统。 若要创建新的应用程序级功能，必须扩展服务或客户端运行库（分别为调度程序和通道工厂）。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]扩展应用程序运行时，请参阅[扩展 ServiceHost 和服务模型层](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)。  
  
#### <a name="extending-security"></a>扩展安全性  
 若要生成自定义安全机制（如令牌和凭据），必须扩展安全系统。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][扩展安全性](../../../docs/framework/wcf/extending/extending-security.md)。  
  
#### <a name="extending-metadata"></a>扩展元数据  
 若要以非默认方式公开元数据，必须扩展元数据系统。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][扩展元数据系统](../../../docs/framework/wcf/extending/extending-the-metadata-system.md)。  
  
#### <a name="extending-serialization"></a>扩展序列化  
 若要生成自定义编码器、提供数据代理项或涉及自定义传输数据的其他工作，必须扩展序列化系统。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][扩展编码器和序列化程序](../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)。  
  
#### <a name="extending-bindings"></a>扩展绑定  
 若要将传输通道或协议通道与应用程序层关联，必须扩展绑定系统。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][扩展绑定](../../../docs/framework/wcf/extending/extending-bindings.md)。  
  
### <a name="extending-the-channel-system"></a>扩展通道系统  
 若要创建频道，以支持自定义传输或协议功能，请参阅[扩展通道层](../../../docs/framework/wcf/extending/extending-the-channel-layer.md)。  
  
### <a name="extending-the-service-hosting-system"></a>扩展服务主机系统  
 若要修改服务范围的应用程序模型，必须扩展 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 类。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][扩展 ServiceHost 和服务模型层](../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)。  
  
 若要修改主机应用程序域和服务主机之间的关系，必须扩展 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 类。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][使用 ServiceHostFactory 扩展宿主](../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)。  
  
## <a name="see-also"></a>请参阅  
 [扩展 WCF](../../../docs/framework/wcf/extending/extending-wcf.md)
