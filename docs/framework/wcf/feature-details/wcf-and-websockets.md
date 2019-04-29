---
title: WCF 和 WebSocket
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768727"
---
# <a name="wcf-and-websockets"></a>WCF 和 WebSocket
.NET Framework 4.5 引入了对 Windows Communication Foundation 中的 WebSocket 的支持。  WebSocket 是一种高效的、基于标准的技术，可通过标准 HTTP 端口 80 和 443 实现双向通信。 使用标准 HTTP 端口，WebSocket 可通过中介跨 Web 进行通信。  添加了两个新的标准绑定以支持通过 WebSocket 传输进行的通信。 <xref:System.ServiceModel.NetHttpBinding> 和 <xref:System.ServiceModel.NetHttpsBinding>。 可以根据特定于 Websocket 的设置<xref:System.ServiceModel.Channels.HttpTransportBindingElement>通过访问<xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A>属性。
  
## <a name="in-this-section"></a>本节内容  
 [使用 NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 讨论 <xref:System.ServiceModel.NetHttpBinding> 以及如何对其进行配置。  
  
 [如何：创建通过 Websocket 进行通信的 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 说明如何创建通过 Websocket 进行通信的 WCF 服务。  
  
## <a name="reference"></a>参考  
  
## <a name="related-sections"></a>相关章节
