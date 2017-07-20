---
title: "使用套接字侦听 | Microsoft Docs"
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
  - "应用程序协议，套接字"
  - "发送数据，套接字"
  - "套接字，使用套接字侦听"
  - "数据请求，套接字"
  - "从 Internet 请求数据，套接字"
  - "接收数据，套接字"
  - "协议，套接字"
  - "使用套接字侦听"
  - "Internet，套接字"
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 使用套接字侦听
侦听器或服务器套接字打开网络的端口然后等待客户端连接到该端口。  尽管其他网络地址族和协议存在，本示例演示如何创建TCP\/IP网络的远程服务。  
  
 TCP\/IP服务的唯一地址通过将宿主端适配器的IP地址定义与服务的端口号创建服务的终结点。  <xref:System.Net.Dns> 选件类提供了返回有关本地网络设备支持的网络地址信息的方法。  当本地网络设备具有多个网络地址时，或者，如果本地系统支持多个网络设备， **Dns** 选件类返回有关所有网络地址的信息，因此，应用程序必须选择适当的服务地址。  internet指定号码适当\(Iana\)定义常用的服务的端口号\(有关更多信息，请参见www.iana.org\/assignments\/port\-numbers\)。  其他服务可以注册了在1,024到65,535范围内的端口号。  
  
 下面的示例通过合并主机的 **Dns** 返回的第一个IP地址服务器上创建 <xref:System.Net.IPEndPoint> 与注册的端口号范围选择的端口号。  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 在本地终结点确定后，该终结点必须与使用 <xref:System.Net.Sockets.Socket.Listen%2A> 方法， <xref:System.Net.Sockets.Socket> 与该终结点使用 <xref:System.Net.Sockets.Socket.Bind%2A> 方法和设置侦听。  ，如果具体地址和端口组合已被使用，**绑定** 引发异常。  下面的示例演示关联 **套接字** 与 **IPEndPoint**。  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 **Listen** 方法采用指定的单个参数与 **套接字** 的多少挂起的连接，允许在服务器忙错误返回到连接的客户端之前。  在这种情况下，，在一个服务器忙响应返回给客户号101之前， 100 client在连接队列中放置。  
  
## 请参阅  
 [使用同步服务器套接字](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [使用异步服务器套接字](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [使用客户端套接字](../../../docs/framework/network-programming/using-client-sockets.md)   
 [如何：创建套接字](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)