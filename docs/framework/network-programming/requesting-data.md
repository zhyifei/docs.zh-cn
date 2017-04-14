---
title: "正在请求数据... | Microsoft Docs"
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
  - "发送数据"
  - "WebRequest 类，发送和接收数据"
  - "从 Internet 请求数据，关于请求数据"
  - "WebClient 类，发送和接收数据"
  - "网络，请求数据"
  - "接收数据"
  - "发送数据，关于发送数据"
  - "响应 Internet 请求，关于响应 Internet 请求"
  - "数据请求"
  - "接收数据，关于接收数据"
  - "Internet，请求数据"
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 正在请求数据...
开发在今天Internet分配的运行环境中运行的应用程序提供用于检索数据需要一个高效，易于使用方法从任何类型资源。  可插入协议允许您开发使用单个接口从多个Internet协议检索数据的应用程序。  
  
## 上载和下载数据从Internet服务器  
 对于简单的请求和响应事务， <xref:System.Net.WebClient> 选件类用于上载到数据或下载数据提供最简单的方法从Internet服务器。  **WebClient** 用于上载和下载文件，发送和接收流和区域数据发送到服务器和接收响应的方法。  **WebClient** 使用 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 选件类生成与Internet资源的实际访问，因此，任何注册的可插入协议可供使用。  
  
 需要进行更复杂的事务使用 **WebRequest** 选件类及其子代，的客户端应用程序从服务器请求的数据。  **WebRequest** 封装连接到服务器，请求发送和接收响应详细信息。  **WebRequest** 是定义一组属性和方法对所有应用程序均可使用可插入协议的抽象类。  **WebRequest**子代，例如 <xref:System.Net.HttpWebRequest>，执行 **WebRequest** 定义的属性和方法用与基础协议一致的方法。  
  
 **WebRequest** 选件类创建 **WebRequest** 子代协议特殊化实例，使用URI的值传递给其 <xref:System.Net.WebRequest.Create%2A> 方法确定特定派生类的实例创建。  应用程序指示应使用哪一个 **WebRequest** 子代处理请求通过注册 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> 方法的派生类的构造函数。  
  
 发出请求Internet资源通过调用 <xref:System.Net.WebRequest.GetResponse%2A> 方法在 **WebRequest**。  **GetResponse** 方法使用从 **WebRequest**的属性的协议特殊化请求，生成或TCP、UDP套接字连接到服务器，并将该请求。  对数据发送到服务器，例如HTTP **Post** 或FTP **Put** 请求的请求， <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=fullName> 方法提供发送数据的网络流。  
  
 匹配 **WebRequest.**的 **GetResponse** 方法返回协议特殊化 **WebResponse**  
  
 **WebResponse** 选件类也是定义属性和方法对所有应用程序均可使用可插入协议的抽象类。  **WebResponse** 子代执行这些属性和方法基础协议的。  <xref:System.Net.HttpWebResponse> 选件类，例如，实现HTTP的 **WebResponse** 选件类。  
  
 服务器返回的数据提供给在 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName> 方法返回的流的应用程序。  如下面的示例所示，可以象使用任何其他的此流，。  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## 请参阅  
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)   
 [如何：请求 Web 页并以流的形式检索结果](../../../docs/framework/network-programming/how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)   
 [如何：检索与 WebRequest 匹配的特定于协议的 WebResponse](../../../docs/framework/network-programming/how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)