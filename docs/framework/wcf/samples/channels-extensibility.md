---
title: "通道扩展性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 541770db6b9cc624fd08ab4db275bc63fa5deca9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="channels-extensibility"></a>通道扩展性
本节包含演示自定义通道的示例。  
  
## <a name="in-this-section"></a>本节内容  
 [本地通道](../../../../docs/framework/wcf/samples/local-channel.md)  
 演示本地通道，这是用于在相同应用程序域内进行通信的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 传输通道。  
  
 [可靠安全配置文件](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 演示如何编写 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和可靠安全配置文件 (RSP)。  
  
 [自定义通道调度程序](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 演示如何通过直接实现 <xref:System.ServiceModel.ServiceHostBase> 以自定义方式生成通道堆栈，以及如何在 Web 主机环境中创建自定义通道调度程序。  
  
 [区块通道](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 演示如何限制在使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发送大型消息时用于缓冲这些消息的内存占用量。  
  
 [HTTP 确认通道](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 演示更改单向消息传递模式的分层通道。  
  
 [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 演示如何生成自定义协议通道，以便使用 HTTP Cookie 进行会话管理。  
  
 [自定义消息拦截器](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 演示如何实现可创建通道工厂和通道侦听器的自定义绑定元素，以便在运行时堆栈的特定点截获所有传入和传出消息。
