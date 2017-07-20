---
title: "TCP/UDP | Microsoft Docs"
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
  - "协议，TCP/UDP"
  - "网络资源，TCP/UDP"
  - "发送数据，TCP/UDP"
  - "TCP/UDP"
  - "TcpClient 类，关于 TcpClient 类"
  - "应用程序协议，TCP/UDP"
  - "接收数据，TCP/UDP"
  - "TcpListener 类，关于 TcpListener 类"
  - "套接字类，关于套接字类"
  - "UDP"
  - "数据请求，TCP/UDP"
  - "从 Internet 请求数据，TCP/UDP"
  - "Internet，TCP/UDP"
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# TCP/UDP
应用程序可以使用控件传输协议\(TCP\)和用户数据协议和 <xref:System.Net.Sockets.TcpClient>、 <xref:System.Net.Sockets.TcpListener>和 <xref:System.Net.Sockets.UdpClient> 选件类的\(UDP\)服务。  这些协议选件类生成。 <xref:System.Net.Sockets.Socket?displayProperty=fullName> 选件类的顶部并保管传输数据的详细信息。  
  
 协议选件类使用 **套接字** 选件类的同步方法提供对web服务的简单又访问，而无需开销保留状态信息或已知设置协议特殊化套接字详细信息。  若要使用异步 **套接字** 方法，可以使用 <xref:System.Net.Sockets.NetworkStream> 选件类提供的异步方法。  对协议选件类未显示的 **套接字** 选件类的访问功能，则必须使用 **套接字** 选件类。  
  
 使用 **NetworkStream** 选件类，**TcpClient** 和 **TcpListener** 表示网络。  使用 <xref:System.Net.Sockets.TcpClient.GetStream%2A> 方法返回网络流，然后调用流的 <xref:System.Net.Sockets.NetworkStream.Read%2A> 和 <xref:System.Net.Sockets.NetworkStream.Write%2A> 方法。  **NetworkStream** 不属于协议选件类中的基础套接字，因此关闭它不会影响套接字。  
  
 **UdpClient** 选件类使用字节保存UDP数据进行。  使用 <xref:System.Net.Sockets.UdpClient.Send%2A> 方法将数据发送到网络和 <xref:System.Net.Sockets.UdpClient.Receive%2A> 方法接收一个传入的数据进行。  
  
## 请参阅  
 [使用 TCP 服务](../../../docs/framework/network-programming/using-tcp-services.md)   
 [使用 UDP 服务](../../../docs/framework/network-programming/using-udp-services.md)   
 [在网络上使用流](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [使用异步服务器套接字](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [使用异步客户端套接字](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)