---
title: 对等网格
ms.date: 03/30/2017
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
ms.openlocfilehash: afd9eae36f28c28b33b74c4456feb4ba8c91314d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766787"
---
# <a name="peer-meshes"></a>对等网格
一个*mesh*是它可以在彼此之间进行通信和唯一的网格 id 标识的对等节点的命名的集合 （一个互连图） 每个节点都与其他多个节点相连接。 在连接良好的网格中，任何两个节点之间都存在一条路径，网格最远端的节点之间的跃点也相对较少，并且即使失去某些节点或连接，网格也会保持连接。网格中的活动节点会发布自己的含有相应网格 ID 的终结点信息，以便其他对等节点可以找到它们。  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a>使用对等通道创建的网格的特征  
  
#### <a name="uniquely-identified"></a>标识唯一性  
  
- 每个网格由唯一的 ID 标识。 网格名称（或网格 ID）与域名系统 (DNS) 主机名的格式相同。 因此，在所使用的解析程序的作用范围内，该网格 ID 对应用程序的目标客户端而言必须是唯一的。 像“MyFamilysPeers”或“KevinsPokerTable”这样的常见名称很容易与其他用户名发生冲突，因此可能返回意外的对等终结点信息，从而导致发生隐私问题或增加连接延迟。 避免这些问题的一种方法是给网格昵称添加一个唯一的 ID 作为后缀（例如“KevinsPokerTable90210”）。  
  
#### <a name="message-flooding"></a>消息洪泛  
  
- 网格允许消息从一个或多个发送方传播到同一网格中的其他所有对等节点。 由对等节点发送的消息洪流使用 `http://schemas.microsoft.com/net/2006/05/peer` 上的命名空间中指定的标头。  
  
#### <a name="optimized-connections"></a>优化的连接  
  
- 当节点加入和离开网格时，对等通道网格会自动进行调整，以确保所有节点都具有良好的连接性，并尽可能降低产生分区（相互隔离的节点组）的可能性。 网格中的连接还根据当前流量模式进行动态优化，以便尽量减小从发送方到接收方的消息延迟。  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a>对等通道不提供的常用网络功能  
 了解对等通道没有提供的一些常用网络功能非常重要。 这些功能可能全部构建在对等通道之上，其中包括：  
  
- **消息排序：** 从单个源发出的消息不会到达的相同顺序或源发送的顺序在所有其他参与方。 要求按一定顺序传递消息的应用程序必须将此功能内置到应用程序中（例如，通过在所有消息中包含一个单调递增的 ID）。  
  
- **可靠消息传送：** 对等通道不包括一种机制来确保所有对等节点都接收到消息。 若要保证消息得到传递，必须在对等通道之上编写一个可靠层。
