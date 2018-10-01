---
title: IPv6 路由
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4ff5f131cfd9fac48e653b98e05d5e46dcfb0bec
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2018
ms.locfileid: "47399016"
---
# <a name="ipv6-routing"></a><span data-ttu-id="0a95f-102">IPv6 路由</span><span class="sxs-lookup"><span data-stu-id="0a95f-102">IPv6 Routing</span></span>
<span data-ttu-id="0a95f-103">灵活的路由机制是 IPv6 的优势之一。</span><span class="sxs-lookup"><span data-stu-id="0a95f-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="0a95f-104">由于 IPv4 网络 ID 以前和现在的分配方式，需要由 Internet 主干网上的路由器来维护大型路由表。</span><span class="sxs-lookup"><span data-stu-id="0a95f-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="0a95f-105">这些路由器必须了解所有路由，才能转发可能定向到 Internet 任何节点的数据包。</span><span class="sxs-lookup"><span data-stu-id="0a95f-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="0a95f-106">借助聚合地址的功能，IPv6 可以灵活寻址，并且大大减小路由表的大小。</span><span class="sxs-lookup"><span data-stu-id="0a95f-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="0a95f-107">在这种新型寻址体系结构中，中间路由器必须仅跟踪网络中的本地部分，才能恰当地转发消息。</span><span class="sxs-lookup"><span data-stu-id="0a95f-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="0a95f-108">邻居发现</span><span class="sxs-lookup"><span data-stu-id="0a95f-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="0a95f-109">邻居发现提供的一些功能是：</span><span class="sxs-lookup"><span data-stu-id="0a95f-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
-   <span data-ttu-id="0a95f-110">路由器发现。</span><span class="sxs-lookup"><span data-stu-id="0a95f-110">Router discovery.</span></span> <span data-ttu-id="0a95f-111">这允许主机识别本地路由器。</span><span class="sxs-lookup"><span data-stu-id="0a95f-111">This allows hosts to identify local routers.</span></span>  
  
-   <span data-ttu-id="0a95f-112">地址解析。</span><span class="sxs-lookup"><span data-stu-id="0a95f-112">Address resolution.</span></span> <span data-ttu-id="0a95f-113">这允许节点解析相应的下一跃点地址的链接层地址（地址解析协议 [ARP] 的替换）。</span><span class="sxs-lookup"><span data-stu-id="0a95f-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
-   <span data-ttu-id="0a95f-114">地址自动配置。</span><span class="sxs-lookup"><span data-stu-id="0a95f-114">Address auto-configuration.</span></span> <span data-ttu-id="0a95f-115">这允许主机自动配置站点本地和全局地址。</span><span class="sxs-lookup"><span data-stu-id="0a95f-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="0a95f-116">邻居发现使用 IPv6 的 Internet 控制消息协议 (ICMPv6) 消息，包括：</span><span class="sxs-lookup"><span data-stu-id="0a95f-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
-   <span data-ttu-id="0a95f-117">路由器播发。</span><span class="sxs-lookup"><span data-stu-id="0a95f-117">Router advertisement.</span></span> <span data-ttu-id="0a95f-118">由路由器在伪周期基础上发送或作为路由器招标的响应发送。</span><span class="sxs-lookup"><span data-stu-id="0a95f-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="0a95f-119">IPv6 路由器使用路由器播发来播发其可用性、地址前缀和其他参数。</span><span class="sxs-lookup"><span data-stu-id="0a95f-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
-   <span data-ttu-id="0a95f-120">路由器招标。</span><span class="sxs-lookup"><span data-stu-id="0a95f-120">Router solicitation.</span></span> <span data-ttu-id="0a95f-121">由主机发送以请求链接上的路由器立即发送路由器播发。</span><span class="sxs-lookup"><span data-stu-id="0a95f-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
-   <span data-ttu-id="0a95f-122">邻居招标。</span><span class="sxs-lookup"><span data-stu-id="0a95f-122">Neighbor solicitation.</span></span> <span data-ttu-id="0a95f-123">由节点发送，以进行地址解析、重复地址检测或验证邻居是否仍可以访问。</span><span class="sxs-lookup"><span data-stu-id="0a95f-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
-   <span data-ttu-id="0a95f-124">邻居播发。</span><span class="sxs-lookup"><span data-stu-id="0a95f-124">Neighbor advertisement.</span></span> <span data-ttu-id="0a95f-125">由节点发送，以响应邻居招标或通知邻居链接层地址的更改。</span><span class="sxs-lookup"><span data-stu-id="0a95f-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
-   <span data-ttu-id="0a95f-126">重定向。</span><span class="sxs-lookup"><span data-stu-id="0a95f-126">Redirect.</span></span> <span data-ttu-id="0a95f-127">由路由器发送，以指示特定目标的下一个更好的跃点地址，用于发送节点。</span><span class="sxs-lookup"><span data-stu-id="0a95f-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a95f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a95f-128">See Also</span></span>  
 [<span data-ttu-id="0a95f-129">Internet 协议版本 6</span><span class="sxs-lookup"><span data-stu-id="0a95f-129">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="0a95f-130">套接字</span><span class="sxs-lookup"><span data-stu-id="0a95f-130">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
