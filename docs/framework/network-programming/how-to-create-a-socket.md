---
title: "如何：创建套接字 | Microsoft Docs"
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
  - "网络"
  - "发送数据，套接字"
  - "数据请求，套接字"
  - "从 Internet 请求数据，套接字"
  - "套接字类，创建套接字"
  - "网络资源"
  - "接收数据，套接字"
  - "协议，套接字"
  - "Internet，套接字"
  - "套接字，创建"
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 如何：创建套接字
在使用套接字与远程计算机通信之前，必须先初始化套接字与协议和网络地址信息。  <xref:System.Net.Sockets.Socket> 选件类的构造函数具有指定地址族、套接字类型和协议类型套接字使用的连接的参数。  
  
## 示例  
 下面的示例创建在基于TCP\/IP的网络可用于通信的一个存储，例如Internet。  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
  
```  
  
 若要使用UDP而不是TCP，请更改协议类型，如下面的示例所示:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
  
```  
  
 <xref:System.Net.Sockets.AddressFamily> 枚举指定 **套接字** 选件类用于的标准地址族解决网络地址\(例如， **AddressFamily.InterNetwork** 成员指定IP地址版本4系列\)。  
  
 <xref:System.Net.Sockets.SocketType> 枚举指定套接字的类型\(例如， **SocketType.Stream** 成员指示发送和接收数据的标准套接字与流控件\)。  
  
 <xref:System.Net.Sockets.ProtocolType> 枚举时指定网络协议使用进行通信。 **套接字** \(例如， **ProtocolType.Tcp** 指示套接字使用TCP; **ProtocolType.Udp** 指示套接字使用UDP\)。  
  
 在 **套接字** 创建后，它可能首次与远程终结点的连接或接收从远程计算机的连接。  
  
## 请参阅  
 [使用客户端套接字](../../../docs/framework/network-programming/using-client-sockets.md)   
 [使用套接字侦听](../../../docs/framework/network-programming/listening-with-sockets.md)