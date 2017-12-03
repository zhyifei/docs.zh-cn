---
title: "WCF 和 WebSocket"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 225bff20f514a653382f01becf133659dec4c5f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="8f193-102">WCF 和 WebSocket</span><span class="sxs-lookup"><span data-stu-id="8f193-102">WCF and WebSockets</span></span>
<span data-ttu-id="8f193-103">.NET Framework 4.5 引入了对 Windows Communication Foundation 中的 WebSocket 的支持。</span><span class="sxs-lookup"><span data-stu-id="8f193-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="8f193-104">WebSocket 是一种高效的、基于标准的技术，可通过标准 HTTP 端口 80 和 443 实现双向通信。</span><span class="sxs-lookup"><span data-stu-id="8f193-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="8f193-105">使用标准 HTTP 端口，WebSocket 可通过中介跨 Web 进行通信。</span><span class="sxs-lookup"><span data-stu-id="8f193-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="8f193-106">添加了两个新的标准绑定以支持通过 WebSocket 传输进行的通信。</span><span class="sxs-lookup"><span data-stu-id="8f193-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="8f193-107"><xref:System.ServiceModel.NetHttpBinding> 和 <xref:System.ServiceModel.NetHttpsBinding>。</span><span class="sxs-lookup"><span data-stu-id="8f193-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="8f193-108">可以在上配置 Websocket 特定设置<xref:System.ServiceModel.Channels.HttpTransportBindingElement>通过访问<xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8f193-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8f193-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f193-109">In This Section</span></span>  
 [<span data-ttu-id="8f193-110">使用 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8f193-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="8f193-111">讨论 <xref:System.ServiceModel.NetHttpBinding> 以及如何对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="8f193-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="8f193-112">如何： 创建通过 Websocket 进行通信的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="8f193-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="8f193-113">说明如何创建通过 Websocket 进行通信的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="8f193-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8f193-114">参考</span><span class="sxs-lookup"><span data-stu-id="8f193-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8f193-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="8f193-115">Related Sections</span></span>
