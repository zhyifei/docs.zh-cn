---
title: 客户端：通道工厂和通道
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: 3f045f56f7b73c5416e7a21a3afde29d22212d68
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182432"
---
# <a name="client-channel-factories-and-channels"></a><span data-ttu-id="23c0a-102">客户端：通道工厂和通道</span><span class="sxs-lookup"><span data-stu-id="23c0a-102">Client: Channel Factories and Channels</span></span>
<span data-ttu-id="23c0a-103">本主题介绍通道工厂和通道的创建。</span><span class="sxs-lookup"><span data-stu-id="23c0a-103">This topic discusses the creation of channel factories and channels.</span></span>  
  
## <a name="channel-factories-and-channels"></a><span data-ttu-id="23c0a-104">通道工厂和通道</span><span class="sxs-lookup"><span data-stu-id="23c0a-104">Channel Factories and Channels</span></span>  
 <span data-ttu-id="23c0a-105">通道工厂负责创建通道。</span><span class="sxs-lookup"><span data-stu-id="23c0a-105">Channel factories are responsible for creating channels.</span></span> <span data-ttu-id="23c0a-106">由通道工厂创建的通道用于发送消息。</span><span class="sxs-lookup"><span data-stu-id="23c0a-106">Channels created by channel factories are used for sending messages.</span></span> <span data-ttu-id="23c0a-107">这些通道负责获取来自上一层的消息，对消息进行必要的处理，然后将消息发送到下一层。</span><span class="sxs-lookup"><span data-stu-id="23c0a-107">These channels are responsible for getting the message from the layer above, performing whatever processing is necessary, then sending the message to the layer below.</span></span> <span data-ttu-id="23c0a-108">下图演示此过程。</span><span class="sxs-lookup"><span data-stu-id="23c0a-108">The following graphic illustrates this process.</span></span>  
  
 <span data-ttu-id="23c0a-109">![客户端工厂和通道](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span><span class="sxs-lookup"><span data-stu-id="23c0a-109">![Client Factories and Channels](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")</span></span>  
<span data-ttu-id="23c0a-110">通道工厂创建通道。</span><span class="sxs-lookup"><span data-stu-id="23c0a-110">A channel factory creates channels.</span></span>  
  
 <span data-ttu-id="23c0a-111">通道工厂在关闭时负责关闭其创建的但尚未关闭的所有通道。</span><span class="sxs-lookup"><span data-stu-id="23c0a-111">When closed, channel factories are responsible for closing any channels they created that are not yet closed.</span></span> <span data-ttu-id="23c0a-112">请注意，此处的模型是非对称的，原因是当通道侦听器关闭时，它仅停止接受新通道，而使现有通道保持打开状态以便继续接收消息。</span><span class="sxs-lookup"><span data-stu-id="23c0a-112">Note that the model is asymmetric here because when a channel listener is closed, it only stops accepting new channels but leaves existing channels open so that they can continue receiving messages.</span></span>  
  
 <span data-ttu-id="23c0a-113">WCF 为此过程提供基类帮助器。</span><span class="sxs-lookup"><span data-stu-id="23c0a-113">WCF provides base class helpers for this process.</span></span> <span data-ttu-id="23c0a-114">(有关本主题中讨论的通道帮助器类的图，请参阅[通道模型概述](../../../../docs/framework/wcf/extending/channel-model-overview.md)。)</span><span class="sxs-lookup"><span data-stu-id="23c0a-114">(For a diagram of the channel helper classes discussed in this topic, see [Channel Model Overview](../../../../docs/framework/wcf/extending/channel-model-overview.md).)</span></span>  
  
-   <span data-ttu-id="23c0a-115"><xref:System.ServiceModel.Channels.CommunicationObject>类实现<xref:System.ServiceModel.ICommunicationObject>并强制执行的步骤 2 中所述的状态机[开发通道](../../../../docs/framework/wcf/extending/developing-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="23c0a-115">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md).</span></span>  
  
-   <span data-ttu-id="23c0a-116"><xref:System.ServiceModel.Channels.ChannelManagerBase> 类实现 <xref:System.ServiceModel.Channels.CommunicationObject> 并为 <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> 和 <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType> 提供统一的基类。</span><span class="sxs-lookup"><span data-stu-id="23c0a-116">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> and <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="23c0a-117"><xref:System.ServiceModel.Channels.ChannelManagerBase> 类与 <xref:System.ServiceModel.Channels.ChannelBase>（用来实现 <xref:System.ServiceModel.Channels.IChannel> 的基类）结合使用。</span><span class="sxs-lookup"><span data-stu-id="23c0a-117">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>
  
-   <span data-ttu-id="23c0a-118"><xref:System.ServiceModel.Channels.ChannelFactoryBase>类实现<xref:System.ServiceModel.Channels.ChannelManagerBase>并<xref:System.ServiceModel.Channels.IChannelFactory>并将合并`CreateChannel`成一个重载`OnCreateChannel`抽象方法。</span><span class="sxs-lookup"><span data-stu-id="23c0a-118">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>
  
-   <span data-ttu-id="23c0a-119"><xref:System.ServiceModel.Channels.ChannelListenerBase> 类实现 <xref:System.ServiceModel.Channels.IChannelListener>。</span><span class="sxs-lookup"><span data-stu-id="23c0a-119">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="23c0a-120">它负责执行基本状态管理。</span><span class="sxs-lookup"><span data-stu-id="23c0a-120">It takes care of basic state management.</span></span> 
  
 <span data-ttu-id="23c0a-121">下面的讨论基于[传输： UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="23c0a-121">The following discussion is based upon the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="creating-a-channel-factory"></a><span data-ttu-id="23c0a-122">创建通道工厂</span><span class="sxs-lookup"><span data-stu-id="23c0a-122">Creating a Channel Factory</span></span>  
 <span data-ttu-id="23c0a-123">`UdpChannelFactory` 派生自 <xref:System.ServiceModel.Channels.ChannelFactoryBase>。</span><span class="sxs-lookup"><span data-stu-id="23c0a-123">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="23c0a-124">该示例重写 <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> 以提供对消息编码器的消息版本的访问。</span><span class="sxs-lookup"><span data-stu-id="23c0a-124">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="23c0a-125">该示例还重写 <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> 以在状态机转变时拆开 <xref:System.ServiceModel.Channels.BufferManager> 的实例。</span><span class="sxs-lookup"><span data-stu-id="23c0a-125">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> to tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="23c0a-126">UDP 输出通道</span><span class="sxs-lookup"><span data-stu-id="23c0a-126">The UDP Output Channel</span></span>  
 <span data-ttu-id="23c0a-127">`UdpOutputChannel` 实现 <xref:System.ServiceModel.Channels.IOutputChannel>。</span><span class="sxs-lookup"><span data-stu-id="23c0a-127">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="23c0a-128">构造函数对参数进行验证，并基于传入的 <xref:System.Net.EndPoint> 来构造目标 <xref:System.ServiceModel.EndpointAddress> 对象。</span><span class="sxs-lookup"><span data-stu-id="23c0a-128">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
 <span data-ttu-id="23c0a-129">重写 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> 将创建用于向此 <xref:System.Net.EndPoint> 发送消息的套接字。</span><span class="sxs-lookup"><span data-stu-id="23c0a-129">The override of <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> creates a socket that is used to send messages to this <xref:System.Net.EndPoint>.</span></span>  
  
 ```csharp 
this.socket = new Socket(  
this.remoteEndPoint.AddressFamily,
   SocketType.Dgram,
   ProtocolType.Udp
);  
```  

 <span data-ttu-id="23c0a-130">通道可以正常关闭或非正常关闭。</span><span class="sxs-lookup"><span data-stu-id="23c0a-130">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="23c0a-131">如果通道正常关闭，则套接字也将关闭，并调用基类 `OnClose` 方法。</span><span class="sxs-lookup"><span data-stu-id="23c0a-131">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="23c0a-132">如果引发异常，则基础结构将调用 `Abort` 以确保清理该通道。</span><span class="sxs-lookup"><span data-stu-id="23c0a-132">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 <span data-ttu-id="23c0a-133">实现`Send()`并`BeginSend()` / `EndSend()`。</span><span class="sxs-lookup"><span data-stu-id="23c0a-133">Implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="23c0a-134">这将分解为两个主要部分。</span><span class="sxs-lookup"><span data-stu-id="23c0a-134">This breaks down into two main sections.</span></span> <span data-ttu-id="23c0a-135">首先，将消息序列化为字节数组：</span><span class="sxs-lookup"><span data-stu-id="23c0a-135">First serialize the message into a byte array:</span></span>  
  
```csharp  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="23c0a-136">然后，在网络上发送生成的数据：</span><span class="sxs-lookup"><span data-stu-id="23c0a-136">Then send the resulting data on the wire:</span></span>  
  
```csharp  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="23c0a-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="23c0a-137">See Also</span></span>  
 [<span data-ttu-id="23c0a-138">开发通道</span><span class="sxs-lookup"><span data-stu-id="23c0a-138">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)
