---
title: NetworkInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3a72eb23c7ad053d6f0fe505668cd037e65d582b
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="networkinformation"></a><span data-ttu-id="88a4c-102">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="88a4c-102">NetworkInformation</span></span>
<span data-ttu-id="88a4c-103"><xref:System.Net.NetworkInformation> 命名空间使你能够收集有关网络事件、更改、统计信息和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="88a4c-103">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="88a4c-104">还可使用 <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> 类来确定是否可以访问远程主机。</span><span class="sxs-lookup"><span data-stu-id="88a4c-104">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="88a4c-105">网络可用性和事件</span><span class="sxs-lookup"><span data-stu-id="88a4c-105">Network Availability and Events</span></span>  
 <span data-ttu-id="88a4c-106"><xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName> 类使你能确定是否已更改网络地址或可用性。</span><span class="sxs-lookup"><span data-stu-id="88a4c-106">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="88a4c-107">若要使用此类，请创建事件处理程序来处理更改，并将其与 <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> 或 <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> 关联。</span><span class="sxs-lookup"><span data-stu-id="88a4c-107">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="88a4c-108">有关详细信息，请参阅[如何：检测网络可用性和地址更改](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="88a4c-108">For more information, see [How to: Detect Network Availability and Address Changes](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="88a4c-109">网络统计信息和属性</span><span class="sxs-lookup"><span data-stu-id="88a4c-109">Network Statistics and Properties</span></span>  
 <span data-ttu-id="88a4c-110">可在接口或协议基础上收集网络统计信息和属性。</span><span class="sxs-lookup"><span data-stu-id="88a4c-110">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="88a4c-111"><xref:System.Net.NetworkInformation.NetworkInterface>、<xref:System.Net.NetworkInformation.NetworkInterfaceType> 和 <xref:System.Net.NetworkInformation.PhysicalAddress> 类提供有关特定网络接口的信息，而 <xref:System.Net.NetworkInformation.IPInterfaceProperties>、<xref:System.Net.NetworkInformation.IPGlobalProperties>、<xref:System.Net.NetworkInformation.IPGlobalStatistics>、<xref:System.Net.NetworkInformation.TcpStatistics> 和 <xref:System.Net.NetworkInformation.UdpStatistics> 类提供有关第 3 层和第 4 层数据包的信息。</span><span class="sxs-lookup"><span data-stu-id="88a4c-111">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="88a4c-112">有关详细信息，请参阅[如何：获取接口和协议信息](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md)。</span><span class="sxs-lookup"><span data-stu-id="88a4c-112">For more information, see [How to: Get Interface and Protocol Information](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="88a4c-113">确定是否可访问远程主机</span><span class="sxs-lookup"><span data-stu-id="88a4c-113">Determine if a Remote Host is Reachable</span></span>  
 <span data-ttu-id="88a4c-114">可使用 <xref:System.Net.NetworkInformation.Ping> 类来确定远程主机是否运行、是否在线及是否可访问。</span><span class="sxs-lookup"><span data-stu-id="88a4c-114">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="88a4c-115">有关详细信息，请参阅[如何：Ping 主机](../../../docs/framework/network-programming/how-to-ping-a-host.md)。</span><span class="sxs-lookup"><span data-stu-id="88a4c-115">For more information, see [How to: Ping a Host](../../../docs/framework/network-programming/how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88a4c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88a4c-116">See Also</span></span>  
 <span data-ttu-id="88a4c-117">[网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md) </span><span class="sxs-lookup"><span data-stu-id="88a4c-117">[Network Programming Samples](../../../docs/framework/network-programming/network-programming-samples.md) </span></span>  
 <span data-ttu-id="88a4c-118">[网络信息技术示例](http://go.microsoft.com/fwlink/?LinkID=179564) </span><span class="sxs-lookup"><span data-stu-id="88a4c-118">[Network Information Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179564) </span></span>  
 <span data-ttu-id="88a4c-119">[NetStat 工具技术示例](http://go.microsoft.com/fwlink/?LinkID=179562) </span><span class="sxs-lookup"><span data-stu-id="88a4c-119">[NetStat Tool Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179562) </span></span>  
 [<span data-ttu-id="88a4c-120">Ping 客户端技术示例</span><span class="sxs-lookup"><span data-stu-id="88a4c-120">Ping Client Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179565)

