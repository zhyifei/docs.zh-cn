---
title: "对等名称发布和解析"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 581d06930240022ae8792c02674d26491f44fa06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="peer-name-publication-and-resolution"></a><span data-ttu-id="7ecd5-102">对等名称发布和解析</span><span class="sxs-lookup"><span data-stu-id="7ecd5-102">Peer Name Publication and Resolution</span></span>
## <a name="publishing-a-peer-name"></a><span data-ttu-id="7ecd5-103">发布对等名称</span><span class="sxs-lookup"><span data-stu-id="7ecd5-103">Publishing a Peer Name</span></span>  
 <span data-ttu-id="7ecd5-104">若要发布新 PNRP ID，对等机需执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ecd5-104">To publish a new PNRP ID, a peer performs the following:</span></span>  
  
-   <span data-ttu-id="7ecd5-105">将 PNRP 发布消息发送到缓存邻居（在缓存的最低级别中注册了 PNRP ID 的对等机）来播种缓存。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-105">Sends PNRP publication messages to its cache neighbors (the peers that have registered PNRP IDs in the lowest level of the cache) to seed their caches.</span></span>  
  
-   <span data-ttu-id="7ecd5-106">在云中选择不是其邻居的随机节点，并为其 P2P ID 发送 PNRP 名称解析请求。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-106">Chooses random nodes in the cloud that are not its neighbors and sends them PNRP name resolution requests for its own P2P ID.</span></span> <span data-ttu-id="7ecd5-107">生成的终结点确定进程使用发布对等机的 PNRP ID 对云中随机节点的缓存进行种子化。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-107">The resulting endpoint determination process seeds the caches of random nodes in the cloud with the PNRP ID of the publishing peer.</span></span>  
  
-  
  
 <span data-ttu-id="7ecd5-108">若 PNRP 版本 2 节点只解析其他 P2P ID，则不发布 PNRP ID。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-108">PNRP version 2 nodes do not publish PNRP IDs if they are only resolving other P2P IDs.</span></span> <span data-ttu-id="7ecd5-109">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1 注册表值 （REG_DWORD 类型）指定对等机仅使用 PNRP 进行名称解析，绝不进行名称发布。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-109">The HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1 registry value (REG_DWORD type) specifies that peers only use PNRP for name resolution, never for name publication.</span></span> <span data-ttu-id="7ecd5-110">也可通过组策略配置此注册表值。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-110">This registry value can also be configured through Group Policy.</span></span>  
  
## <a name="resolving-a-peer-name"></a><span data-ttu-id="7ecd5-111">解析对等名称</span><span class="sxs-lookup"><span data-stu-id="7ecd5-111">Resolving a Peer Name</span></span>  
 <span data-ttu-id="7ecd5-112">在 PNRP 网络或云中查找其他对等是一个包含两个阶段的过程：</span><span class="sxs-lookup"><span data-stu-id="7ecd5-112">Locating other peers in a PNRP network or cloud is a process comprised of two phases:</span></span>  
  
1.  <span data-ttu-id="7ecd5-113">终结点确定</span><span class="sxs-lookup"><span data-stu-id="7ecd5-113">Endpoint Determination</span></span>  
  
2.  <span data-ttu-id="7ecd5-114">PNRP ID 解析</span><span class="sxs-lookup"><span data-stu-id="7ecd5-114">PNRP ID Resolution</span></span>  
  
 <span data-ttu-id="7ecd5-115">在终结点确定阶段，尝试解析另一台计算机上的服务 PNRP ID 的对等机确定该远程对等机的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-115">In the endpoint determination phase, a peer that is attempting to resolve the PNRP ID of a service on another computer determines the IPv6 address of that remote peer.</span></span>  <span data-ttu-id="7ecd5-116">远程对等机是发布计算机或服务的 PNRP ID 或与之相关联的对等机。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-116">The remote peer is the one that published, or is associated with, the PNRP ID of the computer or service.</span></span>  
  
 <span data-ttu-id="7ecd5-117">确认远程终结点已注册到 PNRP 云中后，PNRP ID 解析阶段中的请求对等机向该对等机终结点发送请求以获取所需服务的 PNRP ID 。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-117">After confirming that the remote endpoint has been registered into the PNRP cloud, the requesting peer in the PNRP ID resolution phase sends a request to that peer endpoint for the PNRP ID of the desired service.</span></span> <span data-ttu-id="7ecd5-118">终结点发送确认该服务的 PNRP ID 回复、注释，以及最多 4 KB 的附加信息，请求对等机可将该信息用于将来的通信。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-118">The endpoint sends a reply confirming the PNRP ID of the service, a comment, and up to 4 kilobytes of additional information that the requesting peer can use for future communication.</span></span> <span data-ttu-id="7ecd5-119">例如，如果所需终结点是游戏服务器，附加对等名称记录数据可能包含有关游戏、游戏级别和当前玩家数量的信息。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-119">For example, if the desired endpoint is a gaming server, the additional peer name record data can contain information about the game, the level of play, and the current number of players.</span></span>  
  
 <span data-ttu-id="7ecd5-120">在终结点确定阶段中，PNRP 使用迭代过程来查找发布 PNRP ID 的节点，其中执行解析的节点负责联系更接近目标 PNRP ID 的节点。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-120">In the endpoint determination phase, PNRP uses an iterative process for locating the node that published the PNRP ID, in which the node performing the resolution is responsible for contacting nodes that are successively closer to the target PNRP ID.</span></span>  
  
 <span data-ttu-id="7ecd5-121">若要在 PNRP 中执行名称解析，对等机需检查其缓存中的条目，查找与目标 PNRP ID 匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-121">To perform name resolution in PNRP, the peer examines the entries in its own cache for an entry that matches the target PNRP ID.</span></span> <span data-ttu-id="7ecd5-122">找到后，对等机向对等机发送 PNRP 请求消息，并等待响应。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-122">If found, the peer sends a PNRP Request message to the peer and waits for a response.</span></span> <span data-ttu-id="7ecd5-123">如果未找到该 PNRP ID 的条目，对等机会向具有 PNRP ID（最接近目标 PNRP ID）的条目相对应的对等机发送 PNRP 请求消息。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-123">If an entry for the PNRP ID is not found, the peer sends a PNRP Request message to the peer that corresponds to the entry that has a PNRP ID that most closely matches the target PNRP ID.</span></span> <span data-ttu-id="7ecd5-124">接收 PNRP 请求消息的节点检查其缓存，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ecd5-124">The node that receives the PNRP Request message examines its own cache and does the following:</span></span>  
  
-   <span data-ttu-id="7ecd5-125">找到该 PNRP ID 后，所请求的终结点对等机直接回复请求对等机。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-125">If the PNRP ID is found, the requested endpoint peer replies directly to the requesting peer.</span></span>  
  
-   <span data-ttu-id="7ecd5-126">如果未找到该 PNRP ID 且缓存中的 PNRP ID 更接近目标 PNRP ID，则所请求的对等机向请求对等机发送响应，其中包含表示具有更接近目标 PNRP ID 的 PNRP ID 条目的对等机的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-126">If the PNRP ID is not found and a PNRP ID in the cache is closer to the target PNRP ID, the requested peer sends a response to the requesting peer containing the IPv6 address of the peer that represents the entry with a PNRP ID that more closely matches the target PNRP ID.</span></span> <span data-ttu-id="7ecd5-127">在响应中使用 IP 地址，请求节点向 IPv6 地址发送另一个 PNRP 请求消息，以响应或检查其缓存。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-127">Using the IP address in the response, the requesting node sends another PNRP Request message to the IPv6 address to respond or examine its cache.</span></span>  
  
-   <span data-ttu-id="7ecd5-128">如果未找到该 PNRP ID 且缓存中没有更接近目标 PNRP ID 的 PNRP ID，则所请求的对等机向请求对等机发送表明此情况的响应。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-128">If the PNRP ID is not found and there is no PNRP ID in its cache that is closer to the target PNRP ID, the requested peer sends the requesting peer a response that indicates this condition.</span></span> <span data-ttu-id="7ecd5-129">然后请求对等机选择下一个最接近的 PNRP ID。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-129">The requesting peer then chooses the next-closest PNRP ID.</span></span>  
  
-  
  
 <span data-ttu-id="7ecd5-130">请求对等机通过连续迭代继续此过程，最终查找已注册该 PNRP ID 的节点。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-130">The requesting peer continues this process with successive iterations, eventually locating the node that registered the PNRP ID.</span></span>  
  
 <span data-ttu-id="7ecd5-131">在 <xref:System.Net.PeerToPeer> 命名空间中，<xref:System.Net.PeerToPeer.PeerName> 记录之间存在多对多的关系，这些关系包含终结点和 PNRP 云或用于通信的对等网格。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-131">Within the <xref:System.Net.PeerToPeer> namespace, there is a many-to-many relationship between the <xref:System.Net.PeerToPeer.PeerName> records that contain endpoints and PNRP clouds or meshes in which they communicate.</span></span> <span data-ttu-id="7ecd5-132">有重复或过时条目，或具有相同对等名称的多个节点时，PNRP 节点可以使用 <xref:System.Net.PeerToPeer.PeerNameResolver> 类获取当前信息。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-132">When there are duplicate or stale entries, or multiple nodes with the same peer name, PNRP nodes can obtain current information using the <xref:System.Net.PeerToPeer.PeerNameResolver> class.</span></span> <span data-ttu-id="7ecd5-133"><xref:System.Net.PeerToPeer.PeerNameResolver> 方法使用单一对等名称，将透视简化为一对多对等名称记录和相同的一对多对等机和云的名称记录。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-133">The <xref:System.Net.PeerToPeer.PeerNameResolver> methods use a single peer name to simplify the perspective to one peer-to-many peer name records and the same one peer to many clouds.</span></span> <span data-ttu-id="7ecd5-134">这类似于使用关系表联接执行的查询。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-134">This is similar to a query performed using a relational-table join.</span></span> <span data-ttu-id="7ecd5-135">成功完成后，解析程序对象返回指定对等名称的 <xref:System.Net.PeerToPeer.PeerNameRecordCollection>。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-135">Upon successful completion, the Resolver object returns a <xref:System.Net.PeerToPeer.PeerNameRecordCollection> for the specified peer name.</span></span>  <span data-ttu-id="7ecd5-136">例如，集合中所有对等名称记录中将会出现由云排序的对等名称。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-136">For example, a peer name would occur in all the peer name records in the collection, ordered by cloud.</span></span> <span data-ttu-id="7ecd5-137">这些是对等名称实例，基于 PNRP 的应用程序可能请求这些支持数据。</span><span class="sxs-lookup"><span data-stu-id="7ecd5-137">These are the instances of the peer name whose supporting data may be requested by a PNRP-based application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ecd5-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ecd5-138">See Also</span></span>  
 <xref:System.Net.PeerToPeer>
