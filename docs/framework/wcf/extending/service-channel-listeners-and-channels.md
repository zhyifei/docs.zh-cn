---
title: 服务： 通道侦听器和通道
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 88bfdc879e4f3c7df6b2c4035c7ed7fdc2b4c41d
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46516491"
---
# <a name="service-channel-listeners-and-channels"></a><span data-ttu-id="a7edc-102">服务： 通道侦听器和通道</span><span class="sxs-lookup"><span data-stu-id="a7edc-102">Service: Channel listeners and channels</span></span>

<span data-ttu-id="a7edc-103">有三个类别的通道对象： 通道、 通道侦听器和通道工厂。</span><span class="sxs-lookup"><span data-stu-id="a7edc-103">There are three categories of channel objects: channels, channel listeners, and channel factories.</span></span> <span data-ttu-id="a7edc-104">通道是应用程序和通道堆栈之间的接口。</span><span class="sxs-lookup"><span data-stu-id="a7edc-104">Channels are the interface between the application and the channel stack.</span></span> <span data-ttu-id="a7edc-105">通道侦听器负责在接收（即侦听）端创建通道，这通常是为了响应新传入的消息或连接。</span><span class="sxs-lookup"><span data-stu-id="a7edc-105">Channel listeners are responsible for creating channels on the receive (or listen) side, typically in response to a new incoming message or connection.</span></span> <span data-ttu-id="a7edc-106">通道工厂负责在发送端创建通道，以便启动与终结点的通信。</span><span class="sxs-lookup"><span data-stu-id="a7edc-106">Channel factories are responsible for creating channels on the send side to initiate communication with an endpoint.</span></span>

## <a name="channel-listeners-and-channels"></a><span data-ttu-id="a7edc-107">通道侦听器和通道</span><span class="sxs-lookup"><span data-stu-id="a7edc-107">Channel listeners and channels</span></span>

<span data-ttu-id="a7edc-108">通道侦听器负责创建通道并从下面的层或者从网络接收消息。</span><span class="sxs-lookup"><span data-stu-id="a7edc-108">Channel listeners are responsible for creating channels and receiving messages from the layer below or from the network.</span></span> <span data-ttu-id="a7edc-109">收到的消息将借助于通道侦听器所创建的通道传送到上面的层中。</span><span class="sxs-lookup"><span data-stu-id="a7edc-109">Received messages are delivered to the layer above using a channel that is created by the channel listener.</span></span>

<span data-ttu-id="a7edc-110">下面的关系图阐释了接收消息并将其传送到上面的层的过程。</span><span class="sxs-lookup"><span data-stu-id="a7edc-110">The following diagram illustrates the process of receiving messages and delivering them to the layer above.</span></span>

<span data-ttu-id="a7edc-111">![通道侦听器和通道](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")</span><span class="sxs-lookup"><span data-stu-id="a7edc-111">![Channel listeners and channels](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")</span></span>

<span data-ttu-id="a7edc-112">通道侦听器接收消息并借助于通道将收到的消息传送到上面的层。</span><span class="sxs-lookup"><span data-stu-id="a7edc-112">A channel listener receiving messages and delivering to the layer above through channels.</span></span>

<span data-ttu-id="a7edc-113">该过程在概念上可建模为每个通道中的一个队列，尽管在具体实现中可能并不实际使用队列。</span><span class="sxs-lookup"><span data-stu-id="a7edc-113">The process can be conceptually modeled as a queue inside each channel although the implementation may not actually use a queue.</span></span> <span data-ttu-id="a7edc-114">通道侦听器负责从下面的层或者从网络接收消息，并将收到的消息放入队列。</span><span class="sxs-lookup"><span data-stu-id="a7edc-114">The channel listener is responsible for receiving messages from the layer below or the network and putting them in the queue.</span></span> <span data-ttu-id="a7edc-115">通道负责从队列中获取消息，并在上面的层请求消息（例如通过对通道调用 `Receive`）时将收到的消息传送到该层。</span><span class="sxs-lookup"><span data-stu-id="a7edc-115">The channel is responsible for getting messages from the queue and handing them to the layer above when that layer asks for a message, for example by calling `Receive` on the channel.</span></span>

<span data-ttu-id="a7edc-116">WCF 为此过程提供基类帮助器。</span><span class="sxs-lookup"><span data-stu-id="a7edc-116">WCF provides base class helpers for this process.</span></span> <span data-ttu-id="a7edc-117">(在本文中讨论的通道帮助器类的一个关系图，请参阅[通道模型概述](channel-model-overview.md)。)</span><span class="sxs-lookup"><span data-stu-id="a7edc-117">(For a diagram of the channel helper classes discussed in this article, see [Channel Model Overview](channel-model-overview.md).)</span></span>

- <span data-ttu-id="a7edc-118"><xref:System.ServiceModel.Channels.CommunicationObject>类实现<xref:System.ServiceModel.ICommunicationObject>并强制执行的步骤 2 中所述的状态机[开发通道](developing-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="a7edc-118">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine described in step 2 of [Developing Channels](developing-channels.md).</span></span>

- <span data-ttu-id="a7edc-119"><xref:System.ServiceModel.Channels.ChannelManagerBase> 类实现 <xref:System.ServiceModel.Channels.CommunicationObject> 并为 <xref:System.ServiceModel.Channels.ChannelFactoryBase> 和 <xref:System.ServiceModel.Channels.ChannelListenerBase> 提供统一的基类。</span><span class="sxs-lookup"><span data-stu-id="a7edc-119">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="a7edc-120"><xref:System.ServiceModel.Channels.ChannelManagerBase> 类与 <xref:System.ServiceModel.Channels.ChannelBase>（用来实现 <xref:System.ServiceModel.Channels.IChannel> 的基类）结合使用。</span><span class="sxs-lookup"><span data-stu-id="a7edc-120">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>

- <span data-ttu-id="a7edc-121"><xref:System.ServiceModel.Channels.ChannelFactoryBase>类实现<xref:System.ServiceModel.Channels.ChannelManagerBase>并<xref:System.ServiceModel.Channels.IChannelFactory>并将合并`CreateChannel`成一个重载`OnCreateChannel`抽象方法。</span><span class="sxs-lookup"><span data-stu-id="a7edc-121">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>

- <span data-ttu-id="a7edc-122"><xref:System.ServiceModel.Channels.ChannelListenerBase> 类实现 <xref:System.ServiceModel.Channels.IChannelListener>。</span><span class="sxs-lookup"><span data-stu-id="a7edc-122">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="a7edc-123">它负责执行基本状态管理。</span><span class="sxs-lookup"><span data-stu-id="a7edc-123">It takes care of basic state management.</span></span>

<span data-ttu-id="a7edc-124">下面的讨论基于[传输： UDP](../../../../docs/framework/wcf/samples/transport-udp.md)示例。</span><span class="sxs-lookup"><span data-stu-id="a7edc-124">The following discussion is based upon the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>

## <a name="creating-a-channel-listener"></a><span data-ttu-id="a7edc-125">创建通道侦听器</span><span class="sxs-lookup"><span data-stu-id="a7edc-125">Creating a channel listener</span></span>

<span data-ttu-id="a7edc-126">`UdpChannelListener`该示例实现派生自<xref:System.ServiceModel.Channels.ChannelListenerBase>类。</span><span class="sxs-lookup"><span data-stu-id="a7edc-126">The `UdpChannelListener` that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="a7edc-127">它使用单个 UDP 套接字来接收数据报。</span><span class="sxs-lookup"><span data-stu-id="a7edc-127">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="a7edc-128">`OnOpen` 方法使用该 UDP 套接字以异步循环形式接收数据。</span><span class="sxs-lookup"><span data-stu-id="a7edc-128">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="a7edc-129">收到的数据随后将借助于消息编码系统转换为消息：</span><span class="sxs-lookup"><span data-stu-id="a7edc-129">The data are then converted into messages using the message encoding system:</span></span>

```csharp
message = UdpConstants.MessageEncoder.ReadMessage(
  new ArraySegment<byte>(buffer, 0, count),
  bufferManager
);
```

<span data-ttu-id="a7edc-130">由于可以用同一个数据报通道来表示来自多个源的消息，因此 `UdpChannelListener` 是一个单一实例侦听器。</span><span class="sxs-lookup"><span data-stu-id="a7edc-130">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="a7edc-131">最多一个活动没有<xref:System.ServiceModel.Channels.IChannel>一次与此侦听器相关联。</span><span class="sxs-lookup"><span data-stu-id="a7edc-131">There is at most one active <xref:System.ServiceModel.Channels.IChannel> associated with this listener at a time.</span></span> <span data-ttu-id="a7edc-132">只有当随后释放了由 <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A> 方法返回的通道时，该示例才生成另一个通道。</span><span class="sxs-lookup"><span data-stu-id="a7edc-132">The sample generates another one only if a channel that is returned by the <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A> method is subsequently disposed.</span></span> <span data-ttu-id="a7edc-133">收到一条消息后，它是此单一实例通道中的排队。</span><span class="sxs-lookup"><span data-stu-id="a7edc-133">When a message is received, it's enqueued into this singleton channel.</span></span>

### <a name="udpinputchannel"></a><span data-ttu-id="a7edc-134">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="a7edc-134">UdpInputChannel</span></span>

<span data-ttu-id="a7edc-135">`UdpInputChannel` 类实现 <xref:System.ServiceModel.Channels.IInputChannel>。</span><span class="sxs-lookup"><span data-stu-id="a7edc-135">The `UdpInputChannel` class implements <xref:System.ServiceModel.Channels.IInputChannel>.</span></span> <span data-ttu-id="a7edc-136">该类包括一个传入消息队列，该队列由 `UdpChannelListener` 的套接字来填充。</span><span class="sxs-lookup"><span data-stu-id="a7edc-136">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="a7edc-137">这些消息可以由 <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A> 方法取消排队。</span><span class="sxs-lookup"><span data-stu-id="a7edc-137">These messages are dequeued by the <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A> method.</span></span>
