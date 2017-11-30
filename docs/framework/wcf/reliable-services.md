---
title: "可靠服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4872afb097d01279b24697a7b385f336d34ea4f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="reliable-services"></a>可靠服务
队列和可靠会话是 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 用于实现可靠消息传递的功能。 本主题说明 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 的可靠消息传递功能。  
  
 *可靠消息传递*是指可靠消息源 (称为*源*) 将消息可靠地传送到可靠的消息目标 (称为*目标*)。  
  
 可靠消息传递执行以下功能：  
  
-   传送从源发送到目标的消息的保证，而不管消息传送或传输是否失败。  
  
-   使源和目标相互分离。 即使源或目标不可用，此功能也能为源和目标提供独立的故障与恢复，以及消息的可靠传送和传输。  
  
 可靠消息传递经常伴随高延迟成本。 *延迟*是到达从源目的地的消息所需要的时间。 因此，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 提供了以下类型的可靠消息传递：  
  
-   [可靠会话](../../../docs/framework/wcf/feature-details/reliable-sessions.md)，它提供可靠的传输，而无需的高延迟成本。  
  
-   [WCF 中的队列](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)，它提供了可靠传送和源和目标之间的分离。  
  
## <a name="reliable-sessions"></a>可靠会话  
 可靠会话使用 WS 可靠消息传递协议提供源和目标之间的端到端可靠消息传送，而不管分隔消息（源和目标）终结点的中介的数量和类型如何。 这包括不使用 SOAP 的任何传输中介（例如 HTTP 代理）或在终结点之间流动所必需的使用 SOAP 的中介（例如基于 SOAP 的路由器或网桥）。 可靠会话使用内存中的传送窗口屏蔽 SOAP 消息级别的失败并在传输失败时重新建立连接。  
  
 可靠会话提供低延迟可靠消息传送。 可靠会话通过任何代理或中介为 SOAP 消息提供的功能相当于 TCP 通过 IP 网桥为数据包提供的功能。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]可靠会话，请参阅[可靠会话](../../../docs/framework/wcf/feature-details/reliable-sessions.md)。  
  
### <a name="queues"></a>队列  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中的队列以高延迟为代价提供可靠的消息传送和源与目标之间的分离。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 排队的通信建立在消息队列 (MSMQ) 的基础之上。  
  
 MSMQ 作为可选组件随 Windows 提供。 MSMQ 服务作为 Windows 服务运行。 它捕获代表源的传输队列中要传输的消息，并将消息传递到目标队列。 目标队列代表目标接受消息，待以后目标请求消息时传递。 MSMQ 管理器实现可靠消息传递协议，使消息不会在传输中丢失。 此协议可以是本机的，也可以是基于 SOAP 的协议（称为 SOAP 可靠消息传递协议 (SRMP)）。  
  
 在队列之间与可靠消息传送相耦合的分离，使松耦合的应用程序能够可靠地通信。 与可靠会话不同，源和目标不必同时运行。 这暗示可以出现这种情况：当源产生消息的速率和目标使用消息的速率不匹配时，队列实际上用作一种负载平衡机制。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]队列，请参阅[WCF 中的队列](../../../docs/framework/wcf/feature-details/queues-in-wcf.md)。  
  
## <a name="see-also"></a>另请参阅  
 [可靠会话概述](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 [在 WCF 中排队](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
