---
title: "套接字 | Microsoft Docs"
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
  - "数据请求，套接字"
  - "Windows 套接字"
  - "套接字，关于套接字"
  - "套接字类，关于套接字类"
  - "套接字"
  - "从 Internet 请求数据，套接字"
  - "网络，套接字"
  - "接收数据，套接字"
  - "协议，套接字"
  - "Internet，套接字"
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 套接字
<xref:System.Net.Sockets> 命名空间包含Windows套接字接口的托管实现。  在 <xref:System.Net> 命名空间的其他web Access选件类生成。套接字的此实现的顶部。  
  
 .NET Framework <xref:System.Net.Sockets.Socket> 选件类是Winsock32 API提供的套接字服务的托管代码版本。  在大多数情况下， **套接字** 选件类方法将数据添加到它们的本机Win32副本并处理所有命令性安全检查。  
  
 **套接字** 选件类支持两个基本模式，同步和异步。  在同步模式下，对执行网络操作的函数\(例如 <xref:System.Net.Sockets.Socket.Send%2A> 和 <xref:System.Net.Sockets.Socket.Receive%2A>\)等待，直到操作控件在返回之前完成调用程序。  在异步模式下，这些调用立即返回。  
  
## 请参阅  
 [如何：创建套接字](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)   
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)