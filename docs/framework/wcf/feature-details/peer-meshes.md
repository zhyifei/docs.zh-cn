---
title: 对等网格
ms.date: 03/30/2017
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
ms.openlocfilehash: afd9eae36f28c28b33b74c4456feb4ba8c91314d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493332"
---
# <a name="peer-meshes"></a><span data-ttu-id="9a883-102">对等网格</span><span class="sxs-lookup"><span data-stu-id="9a883-102">Peer Meshes</span></span>
<span data-ttu-id="9a883-103">A*网格*是彼此之间可以相互通信并由唯一的网格 ID 标识的对等节点的命名的集合 （一个互连图）</span><span class="sxs-lookup"><span data-stu-id="9a883-103">A *mesh* is a named collection (an interconnected graph) of peer nodes that can communicate among themselves and that are identified by a unique mesh ID.</span></span> <span data-ttu-id="9a883-104">每个节点都与其他多个节点相连接。</span><span class="sxs-lookup"><span data-stu-id="9a883-104">Each node is connected to multiple other nodes.</span></span> <span data-ttu-id="9a883-105">在连接良好的网格中，任何两个节点之间都存在一条路径，网格最远端的节点之间的跃点也相对较少，并且即使失去某些节点或连接，网格也会保持连接。网格中的活动节点会发布自己的含有相应网格 ID 的终结点信息，以便其他对等节点可以找到它们。</span><span class="sxs-lookup"><span data-stu-id="9a883-105">In a well-connected mesh, there is a path between any two nodes, with relatively few hops between the nodes on the furthest edges of the mesh, and the mesh will remain connected even if some nodes or connections drop out. Active nodes in the mesh publish their endpoint information with a corresponding mesh ID so that other peers can find them.</span></span>  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a><span data-ttu-id="9a883-106">使用对等通道创建的网格的特征</span><span class="sxs-lookup"><span data-stu-id="9a883-106">Characteristics of a Mesh Created Using Peer Channel</span></span>  
  
#### <a name="uniquely-identified"></a><span data-ttu-id="9a883-107">标识唯一性</span><span class="sxs-lookup"><span data-stu-id="9a883-107">Uniquely Identified</span></span>  
  
-   <span data-ttu-id="9a883-108">每个网格由唯一的 ID 标识。</span><span class="sxs-lookup"><span data-stu-id="9a883-108">A unique ID identifies each mesh.</span></span> <span data-ttu-id="9a883-109">网格名称（或网格 ID）与域名系统 (DNS) 主机名的格式相同。</span><span class="sxs-lookup"><span data-stu-id="9a883-109">The name of the mesh (or mesh ID) is in the same format as a Domain Name System (DNS) host name.</span></span> <span data-ttu-id="9a883-110">因此，在所使用的解析程序的作用范围内，该网格 ID 对应用程序的目标客户端而言必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9a883-110">As such, this mesh ID must be unique for the intended client of the application within the scope of the resolver being used.</span></span> <span data-ttu-id="9a883-111">像“MyFamilysPeers”或“KevinsPokerTable”这样的常见名称很容易与其他用户名发生冲突，因此可能返回意外的对等终结点信息，从而导致发生隐私问题或增加连接延迟。</span><span class="sxs-lookup"><span data-stu-id="9a883-111">A common name such as "MyFamilysPeers" or "KevinsPokerTable," may easily collide with other user names and may return unintended peer endpoint information, which could result in privacy issues or increase connection latency.</span></span> <span data-ttu-id="9a883-112">避免这些问题的一种方法是给网格昵称添加一个唯一的 ID 作为后缀（例如“KevinsPokerTable90210”）。</span><span class="sxs-lookup"><span data-stu-id="9a883-112">One way to avoid these issues may be to add a unique ID as a postfix to the nickname for the mesh (for example, "KevinsPokerTable90210").</span></span>  
  
#### <a name="message-flooding"></a><span data-ttu-id="9a883-113">消息洪泛</span><span class="sxs-lookup"><span data-stu-id="9a883-113">Message Flooding</span></span>  
  
-   <span data-ttu-id="9a883-114">网格允许消息从一个或多个发送方传播到同一网格中的其他所有对等节点。</span><span class="sxs-lookup"><span data-stu-id="9a883-114">The mesh allows messages to be propagated from one or more senders to all other peer nodes in the same mesh.</span></span> <span data-ttu-id="9a883-115">由对等节点发送的消息洪流使用 `http://schemas.microsoft.com/net/2006/05/peer` 上的命名空间中指定的标头。</span><span class="sxs-lookup"><span data-stu-id="9a883-115">Messages flooded by peer nodes use headers specified in the namespace at `http://schemas.microsoft.com/net/2006/05/peer`.</span></span>  
  
#### <a name="optimized-connections"></a><span data-ttu-id="9a883-116">优化的连接</span><span class="sxs-lookup"><span data-stu-id="9a883-116">Optimized Connections</span></span>  
  
-   <span data-ttu-id="9a883-117">当节点加入和离开网格时，对等通道网格会自动进行调整，以确保所有节点都具有良好的连接性，并尽可能降低产生分区（相互隔离的节点组）的可能性。</span><span class="sxs-lookup"><span data-stu-id="9a883-117">A Peer Channel mesh automatically adjusts when nodes join and leave, ensuring that all nodes have good connectivity with little chance of creating partitions (groups of nodes isolated from each other).</span></span> <span data-ttu-id="9a883-118">网格中的连接还根据当前流量模式进行动态优化，以便尽量减小从发送方到接收方的消息延迟。</span><span class="sxs-lookup"><span data-stu-id="9a883-118">Connections in the mesh are also dynamically optimized based on current traffic patterns so that message latency from sender to receiver is as small as possible.</span></span>  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a><span data-ttu-id="9a883-119">对等通道不提供的常用网络功能</span><span class="sxs-lookup"><span data-stu-id="9a883-119">Popular Network Features That Peer Channel Does Not Provide</span></span>  
 <span data-ttu-id="9a883-120">了解对等通道没有提供的一些常用网络功能非常重要。</span><span class="sxs-lookup"><span data-stu-id="9a883-120">It is important to be aware of popular network features that Peer Channel does not provide.</span></span> <span data-ttu-id="9a883-121">这些功能可能全部构建在对等通道之上，其中包括：</span><span class="sxs-lookup"><span data-stu-id="9a883-121">These features, which may all be built on top of Peer Channel, include the following:</span></span>  
  
-   <span data-ttu-id="9a883-122">**消息排序：** 来自单个源的消息可能不会到达其他所有方相同顺序或源的发送的顺序。</span><span class="sxs-lookup"><span data-stu-id="9a883-122">**Message ordering:** Messages originating from a single source may not arrive at all other parties in the same order or in the order that the source sent.</span></span> <span data-ttu-id="9a883-123">要求按一定顺序传递消息的应用程序必须将此功能内置到应用程序中（例如，通过在所有消息中包含一个单调递增的 ID）。</span><span class="sxs-lookup"><span data-stu-id="9a883-123">Applications that require messages be delivered in a certain order must build it into their applications (for example, by including a monotonically increasing ID with all messages).</span></span>  
  
-   <span data-ttu-id="9a883-124">**可靠的消息传送：** 对等通道不包括确保所有对等节点接收到消息的机制。</span><span class="sxs-lookup"><span data-stu-id="9a883-124">**Reliable messaging:** Peer Channel does not include a mechanism to ensure message reception by all peers.</span></span> <span data-ttu-id="9a883-125">若要保证消息得到传递，必须在对等通道之上编写一个可靠层。</span><span class="sxs-lookup"><span data-stu-id="9a883-125">To guarantee message delivery, you must write a reliability layer on top of Peer Channel.</span></span>
