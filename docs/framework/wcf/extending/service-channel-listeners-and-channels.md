---
title: 服务：通道侦听器和通道
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 4367d844867db7fdad013e30d047f9385addbce5
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834803"
---
# <a name="service-channel-listeners-and-channels"></a><span data-ttu-id="ae24b-102">服务：通道侦听器和通道</span><span class="sxs-lookup"><span data-stu-id="ae24b-102">Service: Channel listeners and channels</span></span>

<span data-ttu-id="ae24b-103">有三种类别的通道对象：通道、通道侦听器和通道工厂。</span><span class="sxs-lookup"><span data-stu-id="ae24b-103">There are three categories of channel objects: channels, channel listeners, and channel factories.</span></span> <span data-ttu-id="ae24b-104">通道是应用程序和通道堆栈之间的接口。</span><span class="sxs-lookup"><span data-stu-id="ae24b-104">Channels are the interface between the application and the channel stack.</span></span> <span data-ttu-id="ae24b-105">通道侦听器负责在接收（即侦听）端创建通道，这通常是为了响应新传入的消息或连接。</span><span class="sxs-lookup"><span data-stu-id="ae24b-105">Channel listeners are responsible for creating channels on the receive (or listen) side, typically in response to a new incoming message or connection.</span></span> <span data-ttu-id="ae24b-106">通道工厂负责在发送端创建通道，以便启动与终结点的通信。</span><span class="sxs-lookup"><span data-stu-id="ae24b-106">Channel factories are responsible for creating channels on the send side to initiate communication with an endpoint.</span></span>

## <a name="channel-listeners-and-channels"></a><span data-ttu-id="ae24b-107">通道侦听器和通道</span><span class="sxs-lookup"><span data-stu-id="ae24b-107">Channel listeners and channels</span></span>

<span data-ttu-id="ae24b-108">通道侦听器负责创建通道并从下面的层或者从网络接收消息。</span><span class="sxs-lookup"><span data-stu-id="ae24b-108">Channel listeners are responsible for creating channels and receiving messages from the layer below or from the network.</span></span> <span data-ttu-id="ae24b-109">收到的消息将借助于通道侦听器所创建的通道传送到上面的层中。</span><span class="sxs-lookup"><span data-stu-id="ae24b-109">Received messages are delivered to the layer above using a channel that is created by the channel listener.</span></span>

<span data-ttu-id="ae24b-110">下面的关系图阐释了接收消息并将其传送到上面的层的过程。</span><span class="sxs-lookup"><span data-stu-id="ae24b-110">The following diagram illustrates the process of receiving messages and delivering them to the layer above.</span></span>

<span data-ttu-id="ae24b-111">![通道侦听器和通道](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")</span><span class="sxs-lookup"><span data-stu-id="ae24b-111">![Channel listeners and channels](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")</span></span>

<span data-ttu-id="ae24b-112">通道侦听器接收消息并借助于通道将收到的消息传送到上面的层。</span><span class="sxs-lookup"><span data-stu-id="ae24b-112">A channel listener receiving messages and delivering to the layer above through channels.</span></span>

<span data-ttu-id="ae24b-113">该过程在概念上可建模为每个通道中的一个队列，尽管在具体实现中可能并不实际使用队列。</span><span class="sxs-lookup"><span data-stu-id="ae24b-113">The process can be conceptually modeled as a queue inside each channel although the implementation may not actually use a queue.</span></span> <span data-ttu-id="ae24b-114">通道侦听器负责从下面的层或者从网络接收消息，并将收到的消息放入队列。</span><span class="sxs-lookup"><span data-stu-id="ae24b-114">The channel listener is responsible for receiving messages from the layer below or the network and putting them in the queue.</span></span> <span data-ttu-id="ae24b-115">通道负责从队列中获取消息，并在上面的层请求消息（例如通过对通道调用 `Receive`）时将收到的消息传送到该层。</span><span class="sxs-lookup"><span data-stu-id="ae24b-115">The channel is responsible for getting messages from the queue and handing them to the layer above when that layer asks for a message, for example by calling `Receive` on the channel.</span></span>

<span data-ttu-id="ae24b-116">WCF 为此过程提供基类帮助程序。</span><span class="sxs-lookup"><span data-stu-id="ae24b-116">WCF provides base class helpers for this process.</span></span> <span data-ttu-id="ae24b-117">有关本文中讨论的通道帮助器类的图示，请参阅[通道模型概述](channel-model-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ae24b-117">For a diagram of the channel helper classes discussed in this article, see [Channel Model Overview](channel-model-overview.md).</span></span>

- <span data-ttu-id="ae24b-118">@No__t 0 类实现 @no__t，并强制执行[开发通道](developing-channels.md)的步骤2中所述的状态机。</span><span class="sxs-lookup"><span data-stu-id="ae24b-118">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](developing-channels.md).</span></span>

- <span data-ttu-id="ae24b-119"><xref:System.ServiceModel.Channels.ChannelManagerBase> 类实现 <xref:System.ServiceModel.Channels.CommunicationObject> 并为 <xref:System.ServiceModel.Channels.ChannelFactoryBase> 和 <xref:System.ServiceModel.Channels.ChannelListenerBase> 提供统一的基类。</span><span class="sxs-lookup"><span data-stu-id="ae24b-119">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="ae24b-120"><xref:System.ServiceModel.Channels.ChannelManagerBase> 类与 <xref:System.ServiceModel.Channels.ChannelBase>（用来实现 <xref:System.ServiceModel.Channels.IChannel> 的基类）结合使用。</span><span class="sxs-lookup"><span data-stu-id="ae24b-120">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>

- <span data-ttu-id="ae24b-121">@No__t 0 类实现 <xref:System.ServiceModel.Channels.ChannelManagerBase> 和 @no__t，并将 `CreateChannel` 重载合并为一个 @no__t 的抽象方法。</span><span class="sxs-lookup"><span data-stu-id="ae24b-121">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>

- <span data-ttu-id="ae24b-122"><xref:System.ServiceModel.Channels.ChannelListenerBase> 类实现 <xref:System.ServiceModel.Channels.IChannelListener>。</span><span class="sxs-lookup"><span data-stu-id="ae24b-122">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="ae24b-123">它负责执行基本状态管理。</span><span class="sxs-lookup"><span data-stu-id="ae24b-123">It takes care of basic state management.</span></span>

<span data-ttu-id="ae24b-124">以下讨论基于 @no__t 0Transport：UDP](../samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="ae24b-124">The following discussion is based upon the [Transport: UDP](../samples/transport-udp.md) sample.</span></span>

## <a name="creating-a-channel-listener"></a><span data-ttu-id="ae24b-125">创建通道侦听器</span><span class="sxs-lookup"><span data-stu-id="ae24b-125">Creating a channel listener</span></span>

<span data-ttu-id="ae24b-126">示例实现的 @no__t 0 从 @no__t 类派生。</span><span class="sxs-lookup"><span data-stu-id="ae24b-126">The `UdpChannelListener` that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="ae24b-127">它使用单个 UDP 套接字来接收数据报。</span><span class="sxs-lookup"><span data-stu-id="ae24b-127">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="ae24b-128">`OnOpen` 方法使用该 UDP 套接字以异步循环形式接收数据。</span><span class="sxs-lookup"><span data-stu-id="ae24b-128">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="ae24b-129">收到的数据随后将借助于消息编码系统转换为消息：</span><span class="sxs-lookup"><span data-stu-id="ae24b-129">The data are then converted into messages using the message encoding system:</span></span>

```csharp
message = UdpConstants.MessageEncoder.ReadMessage(
  new ArraySegment<byte>(buffer, 0, count),
  bufferManager
);
```

<span data-ttu-id="ae24b-130">由于可以用同一个数据报通道来表示来自多个源的消息，因此 `UdpChannelListener` 是一个单一实例侦听器。</span><span class="sxs-lookup"><span data-stu-id="ae24b-130">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="ae24b-131">一次最多可有一个活动 <xref:System.ServiceModel.Channels.IChannel> 与此侦听器关联。</span><span class="sxs-lookup"><span data-stu-id="ae24b-131">There is at most one active <xref:System.ServiceModel.Channels.IChannel> associated with this listener at a time.</span></span> <span data-ttu-id="ae24b-132">只有当随后释放了由 <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A> 方法返回的通道时，该示例才生成另一个通道。</span><span class="sxs-lookup"><span data-stu-id="ae24b-132">The sample generates another one only if a channel that is returned by the <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A> method is subsequently disposed.</span></span> <span data-ttu-id="ae24b-133">接收到消息时，它将排队传入此单独通道。</span><span class="sxs-lookup"><span data-stu-id="ae24b-133">When a message is received, it's enqueued into this singleton channel.</span></span>

### <a name="udpinputchannel"></a><span data-ttu-id="ae24b-134">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="ae24b-134">UdpInputChannel</span></span>

<span data-ttu-id="ae24b-135">`UdpInputChannel` 类实现 <xref:System.ServiceModel.Channels.IInputChannel>。</span><span class="sxs-lookup"><span data-stu-id="ae24b-135">The `UdpInputChannel` class implements <xref:System.ServiceModel.Channels.IInputChannel>.</span></span> <span data-ttu-id="ae24b-136">该类包括一个传入消息队列，该队列由 `UdpChannelListener` 的套接字来填充。</span><span class="sxs-lookup"><span data-stu-id="ae24b-136">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="ae24b-137">这些消息可以由 <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A> 方法取消排队。</span><span class="sxs-lookup"><span data-stu-id="ae24b-137">These messages are dequeued by the <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A> method.</span></span>
