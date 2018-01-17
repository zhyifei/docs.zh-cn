---
title: "可靠会话的最佳做法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c022db62103826aa89e9035fd36c050d1f7c0f84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-reliable-sessions"></a>可靠会话的最佳做法

本主题讨论为可靠会话的最佳实践。

## <a name="setting-maxtransferwindowsize"></a>设置 MaxTransferWindowSize

[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的可靠会话使用传输窗口保存客户端和服务上的消息。 可配置属性 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 指示传输窗口可以保存多少条消息。

对于发件人，这表示传输窗口可以保存在等待确认; 时的消息数在接收方，它指示要为服务缓冲的消息数。

选择合适的大小会影响网络的效率和服务的最佳容量。 下列各节将详细介绍选择此属性和值的影响的值时要考虑。

默认传输窗口大小为八个消息。

### <a name="efficient-use-of-the-network"></a>有效地利用网络

在此上下文中，术语*网络*对应于用作客户端 （发送方） 和服务 （接收方） 之间的通信的基础的所有内容。 这包括传输连接和任何中间站点或在之间的桥梁包括 SOAP 路由器或 HTTP 代理/防火墙。

有效使用网络可确保充分利用网络容量。 可以每秒通过网络传输的数据量 (*数据速率*) 和从发送方到接收方传输数据的时间 (*延迟*) 如何有效地影响网络利用。

在发送方，属性 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 指示在等待确认消息时，其传输窗口可以保存多少条消息。 如果网络延迟较高，并且为了确保及时响应发送者和网络有效利用，应增加传输窗口大小。

例如即使发送方满足数据速率，延迟可能是高如果发送者和接收者之间存在多个中介或者数据必须穿过有损中介或网络。 因此，发送方必须接受新消息在网络上发送之前，等待其传输窗口中的消息的确认。 具有高延迟、 更少的有效越小的缓冲区的网络使用率。 另一方面，传输窗口大小过高可能会影响服务，因为该服务可能需要满足客户端发送的数据的速率很高。

### <a name="running-the-service-to-capacity"></a>容量运行服务

尽可能高效地使用该网络，理想情况下你还想要在最佳容量运行的服务。 接收方上的传输窗口大小属性指示接收方可以缓冲多少条消息。 此消息缓冲不仅帮助网络流控制，而且还可让服务满负荷运行。 例如，如果缓冲区是一条消息，而且消息到达的速度超过了服务可以处理它们，然后网络可能会丢弃一些消息，并可能浪费或闲置容量。

使用缓冲区可提高服务的可用性，如并发接收和处理以前接收的消息时缓冲消息。

我们建议你使用相同`MaxTransferWindowSize`发送方和接收方。

### <a name="enabling-flow-control"></a>启用流控制

*流控制*是一种机制，以确保在发送者和接收者步伐相互、 使用和处理消息，即快速它们正在生成。 客户端和服务上的传输窗口大小可确保发送方和接收方在一个合理的同步窗口中。

我们强烈建议你设置属性<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A>到`true`当使用可靠会话之间[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端和[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务。

## <a name="setting-maxpendingchannels"></a>设置 MaxPendingChannels

编写一服务，使来自不同客户端的可靠会话通信，时，可能有许多客户端，建立与该服务在同一时间的可靠会话。 在这些情况下，服务的响应取决于 `MaxPendingChannels` 属性。

当发送方创建到接收方的可靠会话通道时，发送方和接收方之间的握手将建立可靠会话。 建立可靠会话之后，该通道会放入到挂起的通道队列中以供服务接受。 此 `MaxPendingChannels` 属性指示有多少个通道可以处于此状态。

它有可能要在其中它无法接受更多通道的状态进行的服务。 如果队列已满，则拒绝尝试建立可靠会话，并且客户端必须重试。

还有可能更长的时间在队列中挂起的通道保留在队列中。 在此期间，可能出现可靠会话的非活动超时，从而导致通道转换到出错状态。

在编写同时服务多个客户端服务时，应设置一个值，适用于你的需求。 设置过高的值`MaxPendingChannels`属性会影响您的工作集。

默认值为<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A>是四个通道。

## <a name="reliable-sessions-and-hosting"></a>可靠会话和宿主

Web 承载的服务时使用可靠会话时，你应该记住下面的重要注意事项：

- 可靠会话是有状态的，而状态在 AppDomain 中进行维护。 这意味着，属于可靠会话的一部分的所有消息必须在同一个 AppDomain 中进行处理。 场或园的大小大于一个节点的 web 场和网络园无法保证此约束。

- 可靠会话使用双工 HTTP 通道 (例如，使用`WsDualHttpBinding`) 会要求多于默认的两个 HTTP 连接每个客户端。 这意味着双工可靠会话，因为并发应用程序和协议消息可能会将传输每种方法在任何给定时间，也可能需要最多两个连接这两种方法。 某些情况下根据消息交换模式的服务，这意味着它是可能出现死锁使用双工 HTTP 和可靠会话的 web 承载服务。 若要增加的每个客户端允许的 HTTP 连接数，将以下代码添加到相关的配置文件 (例如， *web.config*问题的服务):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  值`maxconnection`属性为所需的连接数。 在这种情况下，最小值应为四个连接。
