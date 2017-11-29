---
title: "客户端通道级编程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a6ffe482c8d04314b79ee5bb7029d2583c56c363
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="client-channel-level-programming"></a><span data-ttu-id="42dd5-102">客户端通道级编程</span><span class="sxs-lookup"><span data-stu-id="42dd5-102">Client Channel-Level Programming</span></span>
<span data-ttu-id="42dd5-103">本主题介绍如何在不使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 类及其关联的对象模型的情况下编写 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="42dd5-103">This topic describes how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application without using the <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> class and its associated object model.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="42dd5-104">发送消息</span><span class="sxs-lookup"><span data-stu-id="42dd5-104">Sending Messages</span></span>  
 <span data-ttu-id="42dd5-105">若要准备发送消息并接收和处理回复，需要执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="42dd5-105">To be ready to send messages and receive and process replies, the following steps are required:</span></span>  
  
1.  <span data-ttu-id="42dd5-106">创建绑定。</span><span class="sxs-lookup"><span data-stu-id="42dd5-106">Create a binding.</span></span>  
  
2.  <span data-ttu-id="42dd5-107">生成通道工厂。</span><span class="sxs-lookup"><span data-stu-id="42dd5-107">Build a channel factory.</span></span>  
  
3.  <span data-ttu-id="42dd5-108">创建通道。</span><span class="sxs-lookup"><span data-stu-id="42dd5-108">Create a channel.</span></span>  
  
4.  <span data-ttu-id="42dd5-109">发送请求并读取回复。</span><span class="sxs-lookup"><span data-stu-id="42dd5-109">Send a request and read the reply.</span></span>  
  
5.  <span data-ttu-id="42dd5-110">关闭所有通道对象。</span><span class="sxs-lookup"><span data-stu-id="42dd5-110">Close all channel objects.</span></span>  
  
#### <a name="creating-a-binding"></a><span data-ttu-id="42dd5-111">创建绑定</span><span class="sxs-lookup"><span data-stu-id="42dd5-111">Creating a Binding</span></span>  
 <span data-ttu-id="42dd5-112">与接收情况类似 (请参阅[服务通道级编程](../../../../docs/framework/wcf/extending/service-channel-level-programming.md))，通过创建绑定发送消息开始。</span><span class="sxs-lookup"><span data-stu-id="42dd5-112">Similar to the receiving case (see [Service Channel-Level Programming](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), sending messages starts by creating a binding.</span></span> <span data-ttu-id="42dd5-113">本示例创建一个新的 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> 并将一个 <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> 添加到其 Elements 集合中。</span><span class="sxs-lookup"><span data-stu-id="42dd5-113">This example creates a new <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> and adds an <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> to its Elements collection.</span></span>  
  
#### <a name="building-a-channelfactory"></a><span data-ttu-id="42dd5-114">生成 ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="42dd5-114">Building a ChannelFactory</span></span>  
 <span data-ttu-id="42dd5-115">这次我们不创建 <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>，而是通过调用类型参数为 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 的绑定上的 <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> 来创建一个 <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="42dd5-115">Instead of creating a <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, this time we create a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> by calling <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> on the binding where the type parameter is <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span></span> <span data-ttu-id="42dd5-116">当等待传入消息的一方使用通道侦听器时，发起通信以创建通道的一方将使用通道工厂。</span><span class="sxs-lookup"><span data-stu-id="42dd5-116">While channel listeners are used by the side that waits for incoming messages, channel factories are used by the side that initiates the communication to create a channel.</span></span> <span data-ttu-id="42dd5-117">和通道侦听器相似，必须先打开通道工厂之后才能使用通道工厂。</span><span class="sxs-lookup"><span data-stu-id="42dd5-117">Just like channel listeners, channel factories must be opened first before they can be used.</span></span>  
  
#### <a name="creating-a-channel"></a><span data-ttu-id="42dd5-118">创建通道</span><span class="sxs-lookup"><span data-stu-id="42dd5-118">Creating a Channel</span></span>  
 <span data-ttu-id="42dd5-119">然后我们调用 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> 来创建一个 <xref:System.ServiceModel.Channels.IRequestChannel>。</span><span class="sxs-lookup"><span data-stu-id="42dd5-119">We then call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> to create an <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span> <span data-ttu-id="42dd5-120">此调用接受我们要使用创建的新通道与之通信的终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="42dd5-120">This call takes the address of the endpoint with which we want to communicate using the new channel being created.</span></span> <span data-ttu-id="42dd5-121">得到通道后，我们调用它的 Open 以使其处于通信就绪状态。</span><span class="sxs-lookup"><span data-stu-id="42dd5-121">Once we have a channel, we call Open on it to put it in a state ready for communication.</span></span> <span data-ttu-id="42dd5-122">根据传输的性质，这次对 Open 的调用可能发起与目标终结点的连接，或者在网络上根本不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="42dd5-122">Depending on the nature of the transport, this call to Open may initiate a connection with the target endpoint or may do nothing at all on the network.</span></span>  
  
#### <a name="sending-a-request-and-reading-the-reply"></a><span data-ttu-id="42dd5-123">发送请求并读取回复</span><span class="sxs-lookup"><span data-stu-id="42dd5-123">Sending a Request and Reading the Reply</span></span>  
 <span data-ttu-id="42dd5-124">打开通道之后，可以创建消息并使用通道的 Request 方法发送请求并等待回复返回。</span><span class="sxs-lookup"><span data-stu-id="42dd5-124">Once we have an opened channel, we can create a message and use the channel’s Request method to send the request and wait for the reply to come back.</span></span> <span data-ttu-id="42dd5-125">当此方法返回时，我们将得到回复消息，可以读取该消息以发现终结点回复的内容。</span><span class="sxs-lookup"><span data-stu-id="42dd5-125">When this method returns, we have a reply message that we can read to find out what the endpoint’s reply was.</span></span>  
  
#### <a name="closing-objects"></a><span data-ttu-id="42dd5-126">关闭对象</span><span class="sxs-lookup"><span data-stu-id="42dd5-126">Closing Objects</span></span>  
 <span data-ttu-id="42dd5-127">为避免泄漏资源，我们将关闭通信中不再需要使用的对象。</span><span class="sxs-lookup"><span data-stu-id="42dd5-127">To avoid leaking resources, we close objects used in communications when they are no longer required.</span></span>  
  
 <span data-ttu-id="42dd5-128">下面的代码示例演示了一个基本客户端使用通道工厂发送消息并读取回复。</span><span class="sxs-lookup"><span data-stu-id="42dd5-128">The following code example shows a basic client using the channel factory to send a message and read the reply.</span></span>  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
