---
title: "路由协定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: daebd84c9cef5e64ea7ed55c27b671ba01d14df0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="routing-contracts"></a>路由协定
路由协定定义路由服务可处理的消息模式。  每个协定都是无类型协定，允许服务在不了解消息架构或操作的情况下接收消息。 这样，路由服务就可以按照通常方式来路由消息，而不必对路由的基础消息的细节进行额外配置。  
  
## <a name="routing-contracts"></a>路由协定  
 由于路由服务接受泛型 WCF 消息对象，因此，在选择协定时，首先需要考虑与客户端和服务通信时将采用的通道的形状。 路由服务在处理消息时使用对称消息泵，因此，入站协定的形状通常必须与出站协定的形状匹配。 但是，有服务模型的调度程序可以在其中修改形状，如当调度程序将双工通道转换到请求-答复通道，或从通道中删除会话支持，它不是必需的并且不 （即正在使用时的情况下当**SessionMode.Allowed**、 转换**IInputSessionChannel**到**IInputChannel**)。  
  
 为了支持这些消息泵，路由服务在 <xref:System.ServiceModel.Routing> 命名空间中提供了一些协定，当定义路由服务使用的服务终结点时，必须使用这些协定。 这些协定都是无类型协定，允许接收任何消息类型或操作，并允许路由服务在不了解特定消息架构的情况下处理消息。 有关使用路由服务协定的详细信息，请参阅[路由协定](../../../../docs/framework/wcf/feature-details/routing-contracts.md)。  
  
 路由服务提供的协定位于 <xref:System.ServiceModel.Routing> 命名空间中，下表对这些协定进行了说明。  
  
|协定|形状|通道形状|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel -> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel -> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel -> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel -> IDuplexSessionChannel|  
  
## <a name="see-also"></a>另请参阅  
 [路由服务](http://msdn.microsoft.com/en-us/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)  
 [路由简介](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
