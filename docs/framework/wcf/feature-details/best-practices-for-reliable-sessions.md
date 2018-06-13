---
title: 可靠会话的最佳做法
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 1d9671e7e3124d535b66de8cd8468f76dcb32b10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491620"
---
# <a name="best-practices-for-reliable-sessions"></a><span data-ttu-id="c0ad9-102">可靠会话的最佳做法</span><span class="sxs-lookup"><span data-stu-id="c0ad9-102">Best Practices for Reliable Sessions</span></span>

<span data-ttu-id="c0ad9-103">本主题讨论为可靠会话的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-103">This topic discusses best practices for reliable sessions.</span></span>

## <a name="setting-maxtransferwindowsize"></a><span data-ttu-id="c0ad9-104">设置 MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="c0ad9-104">Setting MaxTransferWindowSize</span></span>

<span data-ttu-id="c0ad9-105">可靠会话中 Windows Communication Foundation (WCF) 使用传输窗口保存客户端和服务上的消息。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-105">Reliable sessions in Windows Communication Foundation (WCF) use a transfer window to hold messages on the client and service.</span></span> <span data-ttu-id="c0ad9-106">可配置属性 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 指示传输窗口可以保存多少条消息。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-106">The configurable property <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indicates how many messages the transfer window can hold.</span></span>

<span data-ttu-id="c0ad9-107">对于发件人，这表示传输窗口可以保存在等待确认; 时的消息数在接收方，它指示要为服务缓冲的消息数。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-107">On the sender, this indicates how many messages the transfer window can hold while waiting for acknowledgements; on the receiver, it indicates how many messages to buffer for the service.</span></span>

<span data-ttu-id="c0ad9-108">选择合适的大小会影响网络的效率和服务的最佳容量。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-108">Choosing the right size impacts the efficiency of the network and the optimal capacity of the service.</span></span> <span data-ttu-id="c0ad9-109">下列各节将详细介绍选择此属性和值的影响的值时要考虑。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-109">The following sections detail what to consider when choosing a value for this property and the impact of the value.</span></span>

<span data-ttu-id="c0ad9-110">默认传输窗口大小为八个消息。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-110">The default transfer window size is eight messages.</span></span>

### <a name="efficient-use-of-the-network"></a><span data-ttu-id="c0ad9-111">有效地利用网络</span><span class="sxs-lookup"><span data-stu-id="c0ad9-111">Efficient use of the network</span></span>

<span data-ttu-id="c0ad9-112">在此上下文中，术语*网络*对应于用作客户端 （发送方） 和服务 （接收方） 之间的通信的基础的所有内容。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-112">In this context, the term *network* corresponds to everything used as the basis of communication between a client (sender) and a service (receiver).</span></span> <span data-ttu-id="c0ad9-113">这包括传输连接和任何中间站点或在之间的桥梁包括 SOAP 路由器或 HTTP 代理/防火墙。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-113">This includes the transport connections and any intermediary or bridges in between, including SOAP routers or HTTP proxies/firewalls.</span></span>

<span data-ttu-id="c0ad9-114">有效使用网络可确保充分利用网络容量。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-114">Efficient use of the network ensures that network capacity is fully used.</span></span> <span data-ttu-id="c0ad9-115">可以每秒通过网络传输的数据量 (*数据速率*) 和从发送方到接收方传输数据的时间 (*延迟*) 如何有效地影响网络利用。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-115">Both the amount of data that can be transferred per second over the network (*data rate*) and the time it takes to transfer data from the sender to the receiver (*latency*) impact how effectively the network is utilized.</span></span>

<span data-ttu-id="c0ad9-116">在发送方，属性 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 指示在等待确认消息时，其传输窗口可以保存多少条消息。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-116">On the sender, the property <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indicates how many messages its transfer window can hold while waiting for acknowledgements.</span></span> <span data-ttu-id="c0ad9-117">如果网络延迟较高，并且为了确保及时响应发送者和网络有效利用，应增加传输窗口大小。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-117">If the network latency is high and in order to ensure a responsive sender and effective network utilization, you should increase the transfer window size.</span></span>

<span data-ttu-id="c0ad9-118">例如即使发送方满足数据速率，延迟可能是高如果发送者和接收者之间存在多个中介或者数据必须穿过有损中介或网络。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-118">For example even if the sender keeps up with data rate, latency could be high if several intermediaries exist between the sender and receiver or the data must pass through a lossy intermediary or network.</span></span> <span data-ttu-id="c0ad9-119">因此，发送方必须接受新消息在网络上发送之前，等待其传输窗口中的消息的确认。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-119">Thus, the sender has to wait for acknowledgements for the messages in its transfer window before accepting new messages to send on the wire.</span></span> <span data-ttu-id="c0ad9-120">具有高延迟、 更少的有效越小的缓冲区的网络使用率。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-120">The smaller the buffer with high latency, the less effective the network utilization.</span></span> <span data-ttu-id="c0ad9-121">另一方面，传输窗口大小过高可能会影响服务，因为该服务可能需要满足客户端发送的数据的速率很高。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-121">On the other hand, too high a transfer window size may impact the service because the service may need to catch up to the high rate of data sent by the client.</span></span>

### <a name="running-the-service-to-capacity"></a><span data-ttu-id="c0ad9-122">容量运行服务</span><span class="sxs-lookup"><span data-stu-id="c0ad9-122">Running the service to capacity</span></span>

<span data-ttu-id="c0ad9-123">尽可能高效地使用该网络，理想情况下你还想要在最佳容量运行的服务。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-123">As much as the network is used efficiently, ideally you also want the service to run at optimal capacity.</span></span> <span data-ttu-id="c0ad9-124">接收方上的传输窗口大小属性指示接收方可以缓冲多少条消息。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-124">The transfer window size property on the receiver indicates how many messages the receiver can buffer.</span></span> <span data-ttu-id="c0ad9-125">此消息缓冲不仅帮助网络流控制，而且还可让服务满负荷运行。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-125">This message buffering helps not only the network flow control but also enables the service to run to full capacity.</span></span> <span data-ttu-id="c0ad9-126">例如，如果缓冲区是一条消息，而且消息到达的速度超过了服务可以处理它们，然后网络可能会丢弃一些消息，并可能浪费或闲置容量。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-126">For example if the buffer is one message and messages arrive faster than the service can process them, then the network might drop messages and capacity might be wasted or underutilized.</span></span>

<span data-ttu-id="c0ad9-127">使用缓冲区可提高服务的可用性，如并发接收和处理以前接收的消息时缓冲消息。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-127">Using a buffer increases the availability of the service as it concurrently receives and buffers a message while processing the previously received messages.</span></span>

<span data-ttu-id="c0ad9-128">我们建议你使用相同`MaxTransferWindowSize`发送方和接收方。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-128">We recommended that you use the same `MaxTransferWindowSize` on both the sender and receiver.</span></span>

### <a name="enabling-flow-control"></a><span data-ttu-id="c0ad9-129">启用流控制</span><span class="sxs-lookup"><span data-stu-id="c0ad9-129">Enabling flow control</span></span>

<span data-ttu-id="c0ad9-130">*流控制*是一种机制，以确保在发送者和接收者步伐相互、 使用和处理消息，即快速它们正在生成。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-130">*Flow control* is a mechanism that ensures that the sender and receiver keep pace with each other, that is, the messages are consumed and acted upon as fast as they're produced.</span></span> <span data-ttu-id="c0ad9-131">客户端和服务上的传输窗口大小可确保发送方和接收方在一个合理的同步窗口中。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-131">The transfer window size on the client and service ensures that the sender and receiver are within a reasonable window of synchronization.</span></span>

<span data-ttu-id="c0ad9-132">我们强烈建议你设置属性<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A>到`true`当使用 WCF 客户端和 WCF 服务之间的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-132">We highly recommended that you set the property <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> to `true` when you're using a reliable session between a WCF client and a WCF service.</span></span>

## <a name="setting-maxpendingchannels"></a><span data-ttu-id="c0ad9-133">设置 MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="c0ad9-133">Setting MaxPendingChannels</span></span>

<span data-ttu-id="c0ad9-134">编写一服务，使来自不同客户端的可靠会话通信，时，可能有许多客户端，建立与该服务在同一时间的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-134">When writing a service that enables reliable session communication from different clients, it's possible to have many clients establish a reliable session to the service at the same time.</span></span> <span data-ttu-id="c0ad9-135">在这些情况下，服务的响应取决于 `MaxPendingChannels` 属性。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-135">The response of the service in these situations depends on the `MaxPendingChannels` property.</span></span>

<span data-ttu-id="c0ad9-136">当发送方创建到接收方的可靠会话通道时，发送方和接收方之间的握手将建立可靠会话。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-136">When the sender creates a reliable session channel to a receiver, a handshake between them establishes a reliable session.</span></span> <span data-ttu-id="c0ad9-137">建立可靠会话之后，该通道会放入到挂起的通道队列中以供服务接受。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-137">After the reliable session is established, the channel is put in a pending channel queue for acceptance by the service.</span></span> <span data-ttu-id="c0ad9-138">此 `MaxPendingChannels` 属性指示有多少个通道可以处于此状态。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-138">The `MaxPendingChannels` property indicates how many channels can be in this state.</span></span>

<span data-ttu-id="c0ad9-139">它有可能要在其中它无法接受更多通道的状态进行的服务。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-139">It's possible for the service to be in a state where it can't accept more channels.</span></span> <span data-ttu-id="c0ad9-140">如果队列已满，则拒绝尝试建立可靠会话，并且客户端必须重试。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-140">If the queue is full, an attempt to establish a reliable session is rejected, and the client must retry.</span></span>

<span data-ttu-id="c0ad9-141">还有可能更长的时间在队列中挂起的通道保留在队列中。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-141">It's also possible that the pending channels in the queue remain in the queue for a longer duration.</span></span> <span data-ttu-id="c0ad9-142">在此期间，可能出现可靠会话的非活动超时，从而导致通道转换到出错状态。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-142">In the meantime, an inactivity timeout on the reliable session may occur, causing the channel to transition to a faulted state.</span></span>

<span data-ttu-id="c0ad9-143">在编写同时服务多个客户端服务时，应设置一个值，适用于你的需求。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-143">When writing a service that services multiple clients simultaneously, you should set a value that's suitable for your needs.</span></span> <span data-ttu-id="c0ad9-144">设置过高的值`MaxPendingChannels`属性会影响您的工作集。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-144">Setting too high a value for the `MaxPendingChannels` property impacts your working set.</span></span>

<span data-ttu-id="c0ad9-145">默认值为<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A>是四个通道。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-145">The default value for <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> is four channels.</span></span>

## <a name="reliable-sessions-and-hosting"></a><span data-ttu-id="c0ad9-146">可靠会话和宿主</span><span class="sxs-lookup"><span data-stu-id="c0ad9-146">Reliable sessions and hosting</span></span>

<span data-ttu-id="c0ad9-147">Web 承载的服务时使用可靠会话时，你应该记住下面的重要注意事项：</span><span class="sxs-lookup"><span data-stu-id="c0ad9-147">When web hosting a service that uses reliable sessions, you should keep the following important considerations in mind:</span></span>

- <span data-ttu-id="c0ad9-148">可靠会话是有状态的，而状态在 AppDomain 中进行维护。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-148">Reliable sessions are stateful, and state is maintained in the AppDomain.</span></span> <span data-ttu-id="c0ad9-149">这意味着，属于可靠会话的一部分的所有消息必须在同一个 AppDomain 中进行处理。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-149">This means that all messages that are part of a reliable session must be processed in the same AppDomain.</span></span> <span data-ttu-id="c0ad9-150">场或园的大小大于一个节点的 web 场和网络园无法保证此约束。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-150">Web farms and web gardens where the size of the farm or garden is greater than one node can't guarantee this constraint.</span></span>

- <span data-ttu-id="c0ad9-151">可靠会话使用双工 HTTP 通道 (例如，使用`WsDualHttpBinding`) 会要求多于默认的两个 HTTP 连接每个客户端。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-151">Reliable sessions using dual HTTP channels (for example, using `WsDualHttpBinding`) can require more than the default of two HTTP connections per-client.</span></span> <span data-ttu-id="c0ad9-152">这意味着双工可靠会话，因为并发应用程序和协议消息可能会将传输每种方法在任何给定时间，也可能需要最多两个连接这两种方法。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-152">This means a duplex reliable session can require up to two connections each way because concurrent application and protocol messages may be transferring each way at any given time.</span></span> <span data-ttu-id="c0ad9-153">某些情况下根据消息交换模式的服务，这意味着它是可能出现死锁使用双工 HTTP 和可靠会话的 web 承载服务。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-153">Under certain conditions depending on the message exchange pattern of the service, this means that it's possible to deadlock a web-hosted service using dual HTTP and reliable sessions.</span></span> <span data-ttu-id="c0ad9-154">若要增加的每个客户端允许的 HTTP 连接数，将以下代码添加到相关的配置文件 (例如， *web.config*问题的服务):</span><span class="sxs-lookup"><span data-stu-id="c0ad9-154">To increase the number of allowable HTTP connections per client, add the following to the relevant configuration file (for example, *web.config* of the service in question):</span></span>

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  <span data-ttu-id="c0ad9-155">值`maxconnection`属性为所需的连接数。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-155">The value of the `maxconnection` attribute is the number of connections needed.</span></span> <span data-ttu-id="c0ad9-156">在这种情况下，最小值应为四个连接。</span><span class="sxs-lookup"><span data-stu-id="c0ad9-156">The minimum in this case should be four connections.</span></span>
