---
title: "扩展 ServiceHost 和服务模块层"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c73af3b9187fa5365d7ea99474ea182d5f5ae86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>扩展 ServiceHost 和服务模块层
服务模型层负责从基础通道拉取传入的消息，将它们翻译成应用程序代码形式的方法调用，并将结果发送回调用方。 服务模型扩展将修改或实现执行或通信行为与功能，包括客户端或调度程序功能、自定义行为、消息和参数截获以及其他扩展功能。  
  
## <a name="in-this-section"></a>本节内容  
 [扩展客户端](../../../../docs/framework/wcf/extending/extending-clients.md)  
 描述可以截获和修改客户端运行时的接口以及可以向其中插入客户端应用程序中的自定义扩展的类。 例如，您可以执行自定义客户端消息记录，执行自定义消息序列化，等等。  
  
 [扩展调度程序](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 描述可以截获和修改服务运行时的接口以及可以向其中插入服务应用程序中的自定义扩展的类。 例如，您可以执行自定义服务记录、服务侧消息验证、自定义调度，等等。  
  
 [可扩展对象](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 描述五个可扩展对象和 <xref:System.ServiceModel.IExtensibleObject%601> 模式。 可扩展对象模式用于使用新功能扩展现有运行时类，或者向对象中添加新状态。 附加到可扩展对象之一的扩展名，在访问附加到公共可扩展对象的共享状态和功能过程的各个不同阶段启用行为，各可扩展对象可以访问该公共扩展对象。  
  
 [使用行为配置和扩展运行时](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 若要更改 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 运行时中的设置或向其中插入扩展，请使用 Behaviors。 WCF 包括系统实现的用于控制遏制、实例化和大量服务及操作的其他方面的行为。 本节介绍如何通过编程方式和使用配置文件来创建您自己的自定义行为，以及如何使这些自定义行为变为可用。  
  
 [使用 ServiceHostFactory 扩展宿主](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 描述如何扩展 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 和 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 以及使用 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 类来自定义主机环境。  
  
## <a name="reference"></a>参考  
  
## <a name="related-sections"></a>相关章节
