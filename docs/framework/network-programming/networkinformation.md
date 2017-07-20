---
title: "NetworkInformation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "网络"
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# NetworkInformation
<xref:System.Net.NetworkInformation> 命名空间可以收集有关web事件、更改、统计信息和属性的信息。  还可以确定远程主机是否是可访问的使用 <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> 选件类。  
  
## 网络可用性和事件  
 <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName> 选件类使您能够确定网络地址或可用性是否已更改。  若要使用此选件类，请创建一个事件处理程序的更改，并将其与 <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> 或 <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>。  有关更多信息，请参见[如何：检测网络可用性和地址更改](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md)。  
  
## 网络统计信息和属性  
 您可以收集网络统计信息和属性在接口或协议基类型。  ，而 <xref:System.Net.NetworkInformation.IPInterfaceProperties>、 <xref:System.Net.NetworkInformation.IPGlobalProperties>、 <xref:System.Net.NetworkInformation.IPGlobalStatistics>、 <xref:System.Net.NetworkInformation.TcpStatistics>和 <xref:System.Net.NetworkInformation.UdpStatistics> 选件类提供有关层3和4层数据包，的信息 <xref:System.Net.NetworkInformation.NetworkInterface>、 <xref:System.Net.NetworkInformation.NetworkInterfaceType>和 <xref:System.Net.NetworkInformation.PhysicalAddress> 选件类提供有关特定网络接口的信息。  有关更多信息，请参见[如何：获取接口和协议信息](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md)。  
  
## 确定远程主机是否是可访问的。  
 可以使用 <xref:System.Net.NetworkInformation.Ping> 选件类确定远程主机是否启用，在网络，并且可访问。  有关更多信息，请参见[如何：Ping 主机](../../../docs/framework/network-programming/how-to-ping-a-host.md)。  
  
## 请参阅  
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)   
 [网络信息技术示例](http://go.microsoft.com/fwlink/?LinkID=179564)   
 [NetStat工具技术示例](http://go.microsoft.com/fwlink/?LinkID=179562)   
 [Ping客户端技术示例](http://go.microsoft.com/fwlink/?LinkID=179565)