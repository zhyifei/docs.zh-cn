---
title: "System.Net 类的最佳实践 | Microsoft Docs"
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
  - "发送数据，最佳做法"
  - "从 Internet 请求数据，最佳做法"
  - "WebRequest 类，最佳做法"
  - "数据请求，最佳做法"
  - "WebResponse 类，最佳做法"
  - "最佳做法，数据请求"
  - "接收数据，最佳做法"
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# System.Net 类的最佳实践
下面的建议将帮助您在 <xref:System.Net> 包含的选件类对它们的最佳优点:  
  
-   使用 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 尽可能而不是转换为子代选件类的类型。  使用 **WebRequest** 和 **WebResponse** 的应用程序可以利用新的Internet协议，而无需大量代码更改。  
  
-   使用 **System.Net** 选件类时，编写在服务器上运行的ASP.NET应用程序，从性能视图通常比较好，，对于 <xref:System.Net.WebRequest.GetResponse%2A> 和 <xref:System.Net.WebResponse.GetResponseStream%2A>使用异步方法。  
  
-   中打开的连接数与Internet资源会对web性能和吞吐量的重大影响。  默认情况下**System.Net** 使用每个应用程序使用两个连接每台主机。  将 <xref:System.Net.ServicePoint> 的 <xref:System.Net.ServicePoint.ConnectionLimit%2A> 属性应用程序的可用于特定宿主增大此数字。  设置 <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> 属性可以为所有宿主增大此默认值。  
  
-   当编写存储级别协议，尝试使用 [TCPClient](frlrfsystemnetsocketstcpclientclasstopic) 或 [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) 尽可能而不是编写直接对 <xref:System.Net.Sockets.Socket>。  这两个客户端选件类封装TCP、UDP套接字的创建，而无需为处理连接的详细信息。  
  
-   在访问时需要凭据的网站，使用 <xref:System.Net.CredentialCache> 选件类创建一个缓存凭据而不是使用它们将每个请求。  **CredentialCache** 选件类搜索缓存查找相应的凭据存在于请求，释放您创建和提供基于URL的凭据的责任。  
  
## 请参阅  
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)