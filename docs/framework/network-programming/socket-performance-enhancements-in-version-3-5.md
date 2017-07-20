---
title: "版本 3.5 中的套接字性能增强 | Microsoft Docs"
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
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 版本 3.5 中的套接字性能增强
<xref:System.Net.Sockets.Socket?displayProperty=fullName> 选件类在3.5版中引发了供使用异步网络I\/O完成高性能的应用程序。  一系列新选件类中添加为的一部分提供另一种异步模式可由专用的高性能套接字应用程序使用的设置的增强功能。 <xref:System.Net.Sockets.Socket> 选件类。  这些增强功能需要高性能的网络服务系统应用程序而设计。  应用程序在其应用程序针对的高放射性区域可以完全仅使用该增强的异步模式或\(例如在收到大量数据，时\)。  
  
## 选件类提高  
 这些增强功能的主要特点是可以避免在异步套接字 I\/O 量非常大时发生重复的对象分配和同步。  套接字异步I\/O的 <xref:System.Net.Sockets.Socket> 选件类当前实现的begin\/end设计模式要求一 <xref:System.IAsyncResult?displayProperty=fullName> 对象为每个异步套接字操作分配。  
  
 在新 <xref:System.Net.Sockets.Socket> 选件类的改进，套接字异步操作由应用程序分配和维护的可重用 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName> 选件类对象进行描述。  高性能套接字应用程序非常清楚地知道必须保持的重叠的套接字操作的量。  应用程序可以根据自身需要创建任意多的 <xref:System.Net.Sockets.SocketAsyncEventArgs> 对象。  例如，因此，如果服务器应用程序需要包含15套接字始终接受未处理的操作支持传入的客户端连接速度，它能提前分配15可重用 <xref:System.Net.Sockets.SocketAsyncEventArgs> 对象实现此目的。  
  
 使用此类执行异步套接字操作的模式包含以下步骤：  
  
1.  分配一个新的 <xref:System.Net.Sockets.SocketAsyncEventArgs> 上下文对象，或者从应用程序池中获取一个空闲的此类对象。  
  
2.  设置在上下文对象的属性设置为要执行的操作\(例如回调委托方法和数据缓冲区，\)。  
  
3.  调用适当的套接字方法 \(xxxAsync\) 以启动异步操作。  
  
4.  如果异步套接字方法\(xxxAsync\)返回true在回调，请查询完成状态的上下文属性。  
  
5.  如果异步套接字方法\(xxxAsync\)返回错误在回调，同步完成的操作。  可以查询上下文属性来获取操作结果。  
  
6.  将该上下文重用于另一个操作，将它放回到应用程序池中，或者将它丢弃。  
  
 在应用程序代码确定新异步套接字操作上下文对象的生存期引用，并且异步I\/O引用。  在对异步套接字操作上下文对象的引用作为一个参数提交给某个异步套接字操作方法之后，应用程序不必保留该引用。  在完成回调返回之前将一直引用该对象。  而是有利的以便应用程序可以保留对上下文对象，以便可以为将来的异步套接字操作中重用。  
  
## 请参阅  
 <xref:System.Net.Sockets.Socket?displayProperty=fullName>   
 <xref:System.Net.Sockets.SendPacketsElement?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=fullName>   
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)   
 [存储性能技术示例](http://go.microsoft.com/fwlink/?LinkID=179570)