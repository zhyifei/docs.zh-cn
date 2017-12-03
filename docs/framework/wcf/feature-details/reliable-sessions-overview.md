---
title: "可靠会话概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6ca4b3e254055c7142259ea6022a53f003ea25f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions-overview"></a>可靠会话概述

[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] SOAP 可靠消息传递提供 SOAP 终结点之间的端对端消息传输可靠性。 此消息传递通过克服传输失败和 SOAP 消息级别失败，可在不可靠的网络上实现传输可靠性。 具体而言，它为跨 SOAP 或传输中介发送的消息提供了一种基于会话的、单一的和（可选）有序的传送。 基于会话的传递提供用于将消息分组具有顺序 （可选） 的消息的会话中。

本主题描述可靠会话、 如何和何时使用它们，以及如何保护它们。

## <a name="wcf-reliable-sessions"></a>WCF 可靠会话

[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠会话是一个如 WS-ReliableMessaging 协议所定义的 SOAP 可靠消息传递的实现。

[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SOAP 可靠消息传递提供两个终结点之间的端到端的可靠会话，而不管消息传递的终结点之间相隔的中介的数量或类型如何。 这包括不使用 SOAP （例如，HTTP 代理） 的任何传输中介或使用 SOAP 的中介 （例如，基于 SOAP 的路由器或网桥） 所需的消息的终结点之间流动。 可靠会话通道支持*交互式*通信，以便同时运行这类通道所连接的服务和交换和处理消息的低延迟、，即条件下在相对较短时间间隔。 这种耦合意味着这些组件将同时成功或同时失败，因此没有它们之间提供隔离。

可靠会话可以屏蔽两种失败情况：

- SOAP 消息级失败，其中包括消息丢失或重复的情况以及消息到达的顺序与消息发送的顺序不同的情况。

- 传输失败。

可靠会话实现 WS-ReliableMessaging 协议和内存中传输窗口以屏蔽 SOAP 消息级失败，并在传输失败的情况下重新建立连接。

可靠会话为 SOAP 消息提供 TCP 为 IP 数据包提供的内容。 TCP 套接字连接在节点之间提供单个的 IP 数据包有序传输。 可靠通道提供相同类型的可靠传输，但在以下方面与 TCP 套接字可靠性不同：

- 可靠性位于 SOAP 消息级别，而不是针对一个任意大小的字节数据包。

- 可靠性很非特定传输，而不仅仅用于通过 TCP 的传输。

- 可靠性不依赖于特定传输会话 （例如，TCP 连接提供会话），可以使用多个传输会话并发或顺序可靠会话的生存期内。

- 可靠会话是发送方和接收方的 SOAP 终结点之间的会话，与二者之间的连接所需的传输连接的数目无关。 简而言之，TCP 可靠性结束传输连接结束位置，而可靠会话提供端到端可靠性。

## <a name="reliable-sessions-and-bindings"></a>可靠会话和绑定

如前所述，可靠会话是非传输特定。 此外，你可以通过许多消息交换模式，例如请求-答复或双工建立可靠会话。 A[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]可靠会话作为一组绑定的属性进行公开。

使用终结点上使用可靠会话：

- 基于 HTTP 的传输协议标准绑定：

  - `WsHttpBinding` 并公开请求-答复或单向协定。

  - 当通过请求-答复或简单的单向服务协定使用可靠会话。

  - `WsDualHttpBinding` 并公开双工、请求-答复或单向协定。

  - `WsFederationHttpBinding` 并公开请求-答复或单向协定。

- 基于 TCP 的传输协议标准绑定：

  - `NetTcpBinding` 并公开双工、请求答复或单向协定。

通过创建自定义绑定，例如 HTTPS 在任何其他绑定上使用可靠会话 (有关问题的详细信息，请参阅<a href="#reliable-sessions-and-security">可靠会话和安全</a>) 或命名的管道绑定。

你可以堆栈可靠会话上不同的基础通道类型，并生成的可靠会话通道形状将会不同。 在客户端和服务器上，支持的可靠会话通道的类型取决于使用的基础通道的类型。 下表列出了在客户端上作为基础通道的一项功能支持的会话通道的类型。

| 支持可靠会话通道类型和 #8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | 是               | 是                      | 是              | 是                     |
| `IRequestSessionChannel`                        | 是               | 是                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | 是              | 是                     |

&#8224;支持的通道类型是可用于泛型值`TChannel`参数值传递到<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29>方法。

下表列出了在服务器上作为基础通道的一项功能支持的会话通道的类型。

| 支持可靠会话通道类型和 #8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | 是             | 是                    | 是              | 是                     |
| `IReplySessionChannel`                          | 是             | 是                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | 是              | 是                     |

&#8225;支持的通道类型是可用于泛型值`TChannel`参数值传递到<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29>方法。

## <a name="reliable-sessions-and-security"></a>可靠会话和安全

保护可靠会话务必确保通信方 （服务和客户端） 进行身份验证和会话中交换的消息未篡改。 此外，务必确保每个单独的可靠会话的完整性。 通过将其绑定到具有表示并由安全会话通道的安全上下文可以保护可靠会话。 安全通道提供安全会话。 然后，使用在会话建立的过程中交换的安全令牌保护可靠会话中的消息。

通过 TCP-S 进行可靠会话时，TCP 会话将关联到可靠会话。 因此，传输安全确保安全也取决于可靠会话。 在此情况下，将关闭重新建立连接的操作。

唯一的例外是在使用 HTTPS 时。 安全套接字层 (SSL) 会话未绑定到可靠会话。 因为共享安全上下文 （SSL 会话） 的会话未保护相互; 这会造成一个威胁这可能会也可能不是真正的威胁，具体取决于应用程序。

## <a name="using-reliable-sessions"></a>使用可靠会话

若要使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可靠会话，请使用支持可靠会话的绑定创建一个终结点。 使用系统提供的绑定之一，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]启用可靠会话提供或创建可完成此自己自定义绑定。

默认情况下支持并启用可靠会话的系统定义的绑定包括：

- <xref:System.ServiceModel.WSDualHttpBinding>

系统提供的绑定支持可靠会话作为一个选项，但默认情况下不启用包括：

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

有关如何创建自定义绑定的示例，请参阅[如何： 创建使用 HTTPS 的自定义的可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)。

有关的讨论[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]绑定支持可靠会话，请参阅[系统提供的绑定](../../../../docs/framework/wcf/system-provided-bindings.md)。

## <a name="when-to-use-reliable-sessions"></a>何时使用可靠会话

请务必了解何时在你的应用程序中使用可靠会话。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 支持同时处于活动状态并在生命期内的终结点之间的可靠会话。 如果你的应用程序要求的终结点之一将不可用的持续时间，然后使用队列来实现可靠性。

如果方案要求通过 TCP 连接的两个终结点，TCP 可能不足以提供可靠的消息交换。 尽管无需使用可靠会话，因为 TCP 可确保数据包到达顺序和唯一一次。

如果你的方案具有任何以下特征，然后您必须认真考虑使用可靠会话。

- SOAP 中介，例如 SOAP 路由器

- 代理中介或传输桥

- 间歇性连接

- 通过 HTTP 会话

## <a name="see-also"></a>请参阅

[使用绑定配置服务和客户端](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
[WS 可靠会话](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
