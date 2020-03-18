---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: bc0604fd33d06521727c9aa0302ed313d8a2305f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "74428231"
---
# <a name="networkinformation"></a><span data-ttu-id="0eb78-102">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="0eb78-102">NetworkInformation</span></span>
<span data-ttu-id="0eb78-103"><xref:System.Net.NetworkInformation> 命名空间使你能够收集有关网络事件、更改、统计信息和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="0eb78-103">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="0eb78-104">还可使用 <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> 类来确定是否可以访问远程主机。</span><span class="sxs-lookup"><span data-stu-id="0eb78-104">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="0eb78-105">网络可用性和事件</span><span class="sxs-lookup"><span data-stu-id="0eb78-105">Network Availability and Events</span></span>  
 <span data-ttu-id="0eb78-106"><xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> 类使你能确定是否已更改网络地址或可用性。</span><span class="sxs-lookup"><span data-stu-id="0eb78-106">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="0eb78-107">若要使用此类，请创建事件处理程序来处理更改，并将其与 <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> 或 <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> 关联。</span><span class="sxs-lookup"><span data-stu-id="0eb78-107">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="0eb78-108">有关详细信息，请参阅[如何：检测网络可用性和地址更改](how-to-detect-network-availability-and-address-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb78-108">For more information, see [How to: Detect Network Availability and Address Changes](how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="0eb78-109">网络统计信息和属性</span><span class="sxs-lookup"><span data-stu-id="0eb78-109">Network Statistics and Properties</span></span>  
 <span data-ttu-id="0eb78-110">可在接口或协议基础上收集网络统计信息和属性。</span><span class="sxs-lookup"><span data-stu-id="0eb78-110">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="0eb78-111"><xref:System.Net.NetworkInformation.NetworkInterface>、<xref:System.Net.NetworkInformation.NetworkInterfaceType> 和 <xref:System.Net.NetworkInformation.PhysicalAddress> 类提供有关特定网络接口的信息，而 <xref:System.Net.NetworkInformation.IPInterfaceProperties>、<xref:System.Net.NetworkInformation.IPGlobalProperties>、<xref:System.Net.NetworkInformation.IPGlobalStatistics>、<xref:System.Net.NetworkInformation.TcpStatistics> 和 <xref:System.Net.NetworkInformation.UdpStatistics> 类提供有关第 3 层和第 4 层数据包的信息。</span><span class="sxs-lookup"><span data-stu-id="0eb78-111">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="0eb78-112">有关详细信息，请参阅[如何：获取接口和协议信息](how-to-get-interface-and-protocol-information.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb78-112">For more information, see [How to: Get Interface and Protocol Information](how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="0eb78-113">确定是否可访问远程主机</span><span class="sxs-lookup"><span data-stu-id="0eb78-113">Determine if a Remote Host is Reachable</span></span>  
 <span data-ttu-id="0eb78-114">可使用 <xref:System.Net.NetworkInformation.Ping> 类来确定远程主机是否运行、是否在线及是否可访问。</span><span class="sxs-lookup"><span data-stu-id="0eb78-114">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="0eb78-115">有关详细信息，请参阅[如何：Ping 主机](how-to-ping-a-host.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb78-115">For more information, see [How to: Ping a Host](how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb78-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eb78-116">See also</span></span>

- [<span data-ttu-id="0eb78-117">网络编程示例</span><span class="sxs-lookup"><span data-stu-id="0eb78-117">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
