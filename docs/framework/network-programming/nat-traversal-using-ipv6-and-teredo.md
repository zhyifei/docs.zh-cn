---
title: "使用 IPv6 和 Teredo 的 NAT 遍历 | Microsoft Docs"
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
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 使用 IPv6 和 Teredo 的 NAT 遍历
提供的网络地址转换\(NAT\)遍历支持的改进来。  这些更改旨在用于IPv6或teredo的使用，但是，同样适用于其他IP隧道技术的它们。  这些增强功能会影响 <xref:System.Net> 和相关命名空间的选件类。  
  
 这些更改会影响计划使用隧道技术的IP的客户端和服务器应用程序。  
  
 支持NAT遍历的更改仅可用于应用程序。使用.NET Framework版本4.版。  这些功能不可用在.NET Framework的早期版本。  
  
## 概述  
 internet协议版本4 \(IPv4\)长定义一个IPv4地址转换为32位。  因此， IPv4支持大约40亿个IP地址\(2^32\)。  为该计算机和网络计算机的数量在20\+世纪\+90\+年代扩展的Internet， IPv4地址空间的限制变得非常明显。  
  
 使用的几种方法之一来扩展生存期IPv4是部署NAT允许一个公共IP地址表示大量的私有IP地址\(专用Intranet\)。  在NAT计算机后的私有IP地址共享一个公共IPv4地址。  NAT计算机可以是私有的硬件设备\(如成本较低的无线访问点和路由器\)，或者运行服务的计算机提供NAT。  计算机或服务该公共IP地址的转换IP网络数据包在公共Internet和Intranet私有之间。  
  
 此模式用于将请求发送到其他IP地址运行在私有Intranet的客户端应用程序非常适合\(通常服务器\)在Internet。  ，当响应在何处返回它知道发送响应时， NAT计算机或服务器可能会保留映射客户端请求。  但是，此模式使若要提供服务，侦听数据包，并响应运行在私有Intranet中的应用程序的问题。NAT计算机之后。  这是对应用程序的特殊情况。  
  
 IPv6协议长定义一个IPv4地址转换为128位。  因此， IPv6支持非常大型IP地址空间3.2 x 10^38唯一地址\(2^128\)。  此范围地址空间，为每个设备可能会连接到将给定的Internet一个地址。  但是，有问题。  许多the world仍只使用IPv4。  具体而言，许多现有路由器和小公司、组织和家庭使用的无线访问点不支持IPv6。  对于这些客户服务的某些Internet服务提供商不支持还未配置为IPv6支持。  
  
 若干IPv6转换技术进行开发隧道IPv6在IPv4数据包的地址。  这些方法包括6to4， ISATAP，并且，对于unicast IPv6通信地址分配和宿主能够为宿主自动隧道路由凿船虫隧道，当IPv6宿主必须穿程IP4网络到达其他IPv6网络时。  IPv6发送数据包隧道作为IPv4数据包。  的若干隧道方法是一NAT设备允许 IPv6 地址的NAT遍历使用。  
  
 凿船虫是对IPv4网络组合IPv6连接的某IPv6转换技术。  凿船虫在internet工程特殊工作组4380文档发布的RFC \(IETF\)。  Windows XP SP2和更高版本提供可提供以大小为2001:0的公共 IPv6 地址:的虚拟凿船虫适配器支持: \/32.  此 IPv6 地址用于侦听来自Internet的传入连接，并且可以提供给IPv6希望连接到侦听的服务启用客户端。  使用其IPv6凿船虫地址，，，因为应用程序可以连接到它将从担心释放一应用程序如何解决在一NAT计算机后的计算机。  
  
## 支持NAT遍历或teredo的改进  
 使用IPv6或teredo，提高添加到 <xref:System.Net>、 <xref:System.Net.NetworkInformation>和 <xref:System.Net.Sockets> 命名空间支持的NAT遍历。  
  
 几个方法添加到 <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=fullName> 选件类获取unicast IP地址的主机上。  <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> 方法启动异步请求检索本地计算机的稳定unicast IP地址表。  <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> 方法结束挂起的异步请求检索本地计算机的稳定unicast IP地址表。  <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> 方法是一个同步请求检索本地计算机的稳定unicast IP地址表，等待，直到地址表如果需要，稳定。  
  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName> 属性可用于确定 <xref:System.Net.IPAddress> 是否IPv6凿船虫地址。  
  
 使用这些新 <xref:System.Net.NetworkInformation.IPGlobalProperties> 与 <xref:System.Net.IPAddress.IsIPv6Teredo%2A> 属性的组合选件类方法允许应用程序轻松查找凿船虫地址。  ，则将此信息到远程应用程序，应用程序通常只需要知道本地凿船虫地址。  例如，某位应用程序可能发送其所有 IPv6 地址到然后可以转发到其他对等类启用直接通信的做媒服务器。  
  
 应用程序在 <xref:System.Net.IPAddress.IPv6Any?displayProperty=fullName> 通常应将其侦听的服务侦听而不是在本地凿船虫地址。  因此，如果远程客户端或对等类有一个直接IPv6路由到侦听的服务主机，客户端或同级可以直接连接使用IPv6而不必使用凿船虫隧道数据包。  
  
 对于TCP应用程序， <xref:System.Net.Sockets.TcpListener?displayProperty=fullName> 选件类具有启用一个 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> 的方法NAT遍历。  对于UDP应用程序， <xref:System.Net.Sockets.UdpClient?displayProperty=fullName> 选件类具有启用一个 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> 的方法NAT遍历。  
  
 对于使用 <xref:System.Net.Sockets.Socket?displayProperty=fullName> ，并且相关选件类、 <xref:System.Net.Sockets.Socket.GetSocketOption%2A> 和 <xref:System.Net.Sockets.Socket.SetSocketOption%2A> 方法可用于以 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> 套接字选项查询的应用程序，启用或禁用NAT遍历。  
  
## 请参阅  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=fullName>