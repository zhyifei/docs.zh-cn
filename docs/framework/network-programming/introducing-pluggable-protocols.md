---
title: "可插入协议简介 | Microsoft Docs"
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
  - "数据请求，可插入协议"
  - "WebRequest 类，可插入协议"
  - "响应 Internet 请求，可插入协议"
  - "URI"
  - "Windows 套接字"
  - "请求/响应模型"
  - "发送数据，可插入协议"
  - "可插入协议"
  - "WebClient 类，关于 WebClient 类"
  - "可插入协议，关于可插入协议"
  - "Internet，可插入协议"
  - "路径标识符"
  - "统一资源标识符"
  - "应用程序开发 [.NET Framework]，可插入协议"
  - "从 Internet 请求数据，可插入协议"
  - "接收数据，可插入协议"
  - "协议，可插入"
  - "服务器标识符"
  - "方案标识符"
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 可插入协议简介
Microsoft .NET Framework提供的Internet服务一个分层，可扩展的和托管的实现可以集成快速轻松地应用程序。  在 <xref:System.Net> 和 <xref:System.Net.Sockets> 命名空间的Internet访问选件类可用于实现基于web和基于Internet的应用程序。  
  
## Internet应用程序  
 Internet应用程序中通常被分为两种:请求的客户端应用程序信息和响应信息的服务器应用程序从客户端请求。  经典Internet客户端\/服务器应用程序是万维网，方访问的使用浏览器文档在Web服务器上存储的其他数据翻番。  
  
 应用程序不限于单一这些角色;例如，熟悉中间层应用程序服务器响应来自客户端的请求通过请求从其他服务器上的数据，，在为服务器和客户端情况下。  
  
 客户端应用程序传递标识请求的Internet资源和通信协议。请求和响应使用发出请求。  如果需要，客户端还提供所需的任何其他的信息完成请求，如代理位置或身份验证信息\(用户名，密码，等等\)。  一次请求形成，请求可以发送到服务器。  
  
## 标识资源  
 .NET Framework使用统一资源标识符\(uri\) \(URI\)标识请求的Internet资源和通信协议。  URI包括至少也可能是四，片断:模式标识符，标识请求和响应的通信协议;服务器标识符，包括域名系统\(DNS\)主机名或TCP地址唯一标识在Internet上服务器上;路径标识符，独立请求的信息服务器上;和可选查询字符串，到服务器传递来自客户端的信息。  例如， URI “http:\/\/www.contoso.com\/whatsnew.aspx?date\=today”包括模式标识符“http”，服务器标识符“www.contoso.com”，路径“\/whatsnew.aspx”和查询字符串“? date\=today”。  
  
 在服务器收到请求并处理响应后，它将返回到客户端应用程序的响应。  响应包括补充信息，如将内容的类型\(如基元的文本或XML数据，\)。  
  
## 请求和响应在.NET Framework  
 .NET Framework使用特定选件类通过请求\/响应模型所需的访问Internet资源三条信息: <xref:System.Uri> 选件类，包含Internet资源的URI您查找; <xref:System.Net.WebRequest> 选件类，包含一个对资源;并 <xref:System.Net.WebResponse> 选件类，来为传入响应提供容器。  
  
 客户端应用程序通过网络资源的URI创建 `WebRequest` 实例。 <xref:System.Net.WebRequest.Create%2A> 方法。  此静态方法创建特定协议的 `WebRequest` ，例如HTTP。  返回的 `WebRequest` 提供对控件对数据流的服务器请求和访问发送的属性，则该请求时。  在 `WebRequest` 的 <xref:System.Net.WebRequest.GetResponse%2A> 方法从客户端应用程序请求发送到URI标识的服务器。  在响应可能延迟种情况下，请求来异步使用 <xref:System.Net.WebRequest.BeginGetResponse%2A> 方法在 **WebRequest**，使用 <xref:System.Net.WebRequest.EndGetResponse%2A> 方案，并且，如果响应可在以后返回。  
  
 **GetResponse** 和 **EndGetResponse** 方法返回提供对服务器返回的数据 **WebResponse** 。  由于此数据提供给请求的应用程序以流使用 <xref:System.Net.WebResponse.GetResponseStream%2A> 方法，可用于任何位置应用程序数据流使用。  
  
 **WebRequest** 和 **WebResponse** 选件类是可插入协议的基类型—使开发应用程序使用Internet资源，不允许协议特定详细信息每个资源使用担心web服务的实现。  **WebRequest** 子代选件类向 **WebRequest** 选件类中管理生成与Internet资源的实际连接详细信息。  
  
 例如，使用HTTP， <xref:System.Net.HttpWebRequest> 选件类管理连接到Internet资源详细信息。  默认情况下，那么，当从“HTTP开始的 **WebRequest.Create** 方法遇到URI: ”或“https: ” \(HTTP和安全HTTP的草案标识符\)，返回的 **WebRequest** 可以使用与也可以是转换为 **HttpWebRequest** 访问协议特殊化属性。  在大多数情况下， **WebRequest** 为请求提供所有必需的信息。  
  
 可以表示为请求\/响应事务的所有协议可用于 **WebRequest**。  可以从 **WebRequest** 和 **WebResponse** 派生协议特殊化选件类随后注册它们旨在用于静态 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> 方法的应用程序。  
  
 当需要时Internet请求的客户端权限， **WebRequest** 的 <xref:System.Net.WebRequest.Credentials%2A> 属性提供必需的凭据。  这些凭据是一个简单名\/密码对于基本的HTTP或摘要式身份验证对或者为NTLM或Kerberos身份验证设置的名称\/密码\/字段。  一组凭据。 [NetworkCredentials](frlrfsystemnetnetworkcredentialclasstopic) 实例可以存储，或多个在 <xref:System.Net.CredentialCache> 实例设置可同时存储。  **CredentialCache** 使用服务器支持确定该请求和身份验证方案的URI发送的哪凭据到服务器。  
  
## 与网络客户端的简单请求  
 对于需要进行简单的需要Internet资源的应用程序， <xref:System.Net.WebClient> 选件类用于上载到数据或下载数据的常用方法从Internet服务器。  **WebClient** 依赖 **WebRequest** 选件类提供对Internet资源;因此， **WebClient** 选件类可以使用任何注册的可插入协议。  
  
 用于不能使用请求\/响应模型的应用程序，或已在网络需要侦听以及发送请求的应用程序， **System.Net.Sockets** 命名空间提供 [TCPClient](frlrfsystemnetsocketstcpclientclasstopic)、 [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic)和 [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) 选件类。  这些类处理使用不同的传输协议建立连接的详细信息，并且作为流向应用程序公开网络连接。  
  
 需要编程提供的控件在套接字级别的开发人员熟悉Windows套接字接口或那些用户会发现 **System.Net.Sockets** 选件类满足其需求的。  **System.Net.Sockets** 选件类是从托管转折点到 **System.Net** 选件类中的本机代码。  在大多数情况下， **System.Net.Sockets** 类别送数据按它们的Windows 32位副本，以及处理所有命令性安全检查。  
  
## 请参阅  
 [对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)   
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)   
 [.NET的网络连接的示例MSDN代码库](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)