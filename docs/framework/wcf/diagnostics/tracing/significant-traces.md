---
title: "重要跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95b4794848927b9319ddb07d75461f5d5e71e1f5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="significant-traces"></a><span data-ttu-id="7af69-102">重要跟踪</span><span class="sxs-lookup"><span data-stu-id="7af69-102">Significant Traces</span></span>
<span data-ttu-id="7af69-103">本主题列出 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 发出的一些主要跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-103">This topic lists some of the major traces emitted by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="significant-traces"></a><span data-ttu-id="7af69-104">重要跟踪</span><span class="sxs-lookup"><span data-stu-id="7af69-104">Significant Traces</span></span>  
  
|<span data-ttu-id="7af69-105">跟踪</span><span class="sxs-lookup"><span data-stu-id="7af69-105">Trace</span></span>|<span data-ttu-id="7af69-106">描述</span><span class="sxs-lookup"><span data-stu-id="7af69-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7af69-107">消息日志跟踪</span><span class="sxs-lookup"><span data-stu-id="7af69-107">Message log trace</span></span>|<span data-ttu-id="7af69-108">如果启用了 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪源，则当消息日志记录功能记录下 `System.ServiceModel.MessageLogging` 消息时发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-108">The trace is emitted when a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message is logged by the message logging feature when the `System.ServiceModel.MessageLogging` trace source is enabled.</span></span> <span data-ttu-id="7af69-109">单击此跟踪可以显示消息。</span><span class="sxs-lookup"><span data-stu-id="7af69-109">Clicking this trace displays the message.</span></span> <span data-ttu-id="7af69-110">一条消息有四个可配置的记录点：`ServiceLevelSendRequest`、`TransportSend`、`TransportReceive`、`ServiceLevelReceiveRequest`，消息日志跟踪的“消息源”属性中也指明了它们。</span><span class="sxs-lookup"><span data-stu-id="7af69-110">There are four configurable logging points for a message: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, also indicated by the Message Source attribute in the message log trace.</span></span>|  
|<span data-ttu-id="7af69-111">已接收消息的跟踪</span><span class="sxs-lookup"><span data-stu-id="7af69-111">Message received trace</span></span>|<span data-ttu-id="7af69-112">如果在信息级别或详细级别启用了 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪源，则将在接收到 `System.ServiceModel` 消息时发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-112">This trace is emitted when a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message is received if the `System.ServiceModel` trace source is enabled at information or verbose level.</span></span> <span data-ttu-id="7af69-113">此跟踪对于在活动图形视图中查看消息相关箭头而言是必需的。</span><span class="sxs-lookup"><span data-stu-id="7af69-113">This trace is necessary to see the message correlation arrow in the activity graph view.</span></span>|  
|<span data-ttu-id="7af69-114">已发送消息的跟踪</span><span class="sxs-lookup"><span data-stu-id="7af69-114">Message sent trace</span></span>|<span data-ttu-id="7af69-115">如果在信息级别或详细级别启用了 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪源，则当发送 `System.ServiceModel` 消息时发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-115">This trace is emitted when a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message is sent if the `System.ServiceModel` trace source is enabled at information or verbose level.</span></span> <span data-ttu-id="7af69-116">此跟踪对于在活动图形视图中查看消息相关箭头而言是必需的。</span><span class="sxs-lookup"><span data-stu-id="7af69-116">This trace is necessary to see the message correlation arrow in the activity graph view.</span></span>|  
|<span data-ttu-id="7af69-117">获取 ChannelEndpointElement</span><span class="sxs-lookup"><span data-stu-id="7af69-117">Get ChannelEndpointElement</span></span>|<span data-ttu-id="7af69-118">在构建通道工厂时以信息级别发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-118">This trace is emitted in Construct channel factory, at information level.</span></span> <span data-ttu-id="7af69-119">此跟踪提供对与客户端通信的终结点的说明（远程地址、绑定、协定名称）。</span><span class="sxs-lookup"><span data-stu-id="7af69-119">It provides a description of the endpoint the client is talking to (remote address, binding, contract name).</span></span>|  
|<span data-ttu-id="7af69-120">获取 ServiceElement</span><span class="sxs-lookup"><span data-stu-id="7af69-120">Get ServiceElement</span></span>|<span data-ttu-id="7af69-121">在构建服务主机时以信息级别发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-121">This trace is emitted in Construct service host, at Information level.</span></span> <span data-ttu-id="7af69-122">此跟踪提供对服务协定和绑定的说明。</span><span class="sxs-lookup"><span data-stu-id="7af69-122">It provides a description of the service contract and binding.</span></span>|  
|<span data-ttu-id="7af69-123">SocketConnection 创建</span><span class="sxs-lookup"><span data-stu-id="7af69-123">SocketConnection create</span></span>|<span data-ttu-id="7af69-124">在客户端执行的第一个处理操作中，以及在服务上的接收字节活动中发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="7af69-124">This trace is emitted in the first Process action performed by the client and in the Receive bytes activity on the service.</span></span> <span data-ttu-id="7af69-125">此跟踪提供本地和远程 IP 地址，</span><span class="sxs-lookup"><span data-stu-id="7af69-125">It provides the local and remote IP addresses.</span></span> <span data-ttu-id="7af69-126">以信息级别发出。</span><span class="sxs-lookup"><span data-stu-id="7af69-126">It is emitted at Information level.</span></span>|
