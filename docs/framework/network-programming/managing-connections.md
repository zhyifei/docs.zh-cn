---
title: "管理连接 | Microsoft Docs"
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
  - "Internet，连接"
  - "HTTP，用于连接的类"
  - "从 Internet 请求数据，连接"
  - "发送数据，连接"
  - "接收数据，连接"
  - "ServicePoint 类，关于 ServicePoint 类"
  - "响应 Internet 请求，连接"
  - "连接 [.NET Framework]，类"
  - "网络资源，连接"
  - "下载 Internet 资源，连接"
  - "ServicePointManager 类，关于 ServicePointManager 类"
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 管理连接
使用HTTP连接到数据资源的应用程序可以使用.NET framework的 <xref:System.Net.ServicePoint> 和 <xref:System.Net.ServicePointManager> 选件类管理与Internet的连接和帮助他们实现最佳缩放和性能。  
  
 **ServicePoint** 选件类提供了应用程序的应用程序可以连接到访问Internet资源的终点。  每 **ServicePoint** 包含可通过共享在连接之间的优化信息改进性能优化与Internet服务器的连接的信息。  
  
 每 **ServicePoint** 由统一资源标识符\(uri\) \(URI\)定位和基于URI的模式标识符和宿主片段类别。  例如，同一 **ServicePoint** 实例将提供请求的URI http:\/\/www.contoso.com\/index.htm和http:\/\/www.contoso.com\/news.htm?date\=today，因为它们具有相同架构标识符\(HTTP\)和宿主片段\(www.contoso.com\)。  如果应用程序已具有服务器www.contoso.com的持久连接，它使用该连接检索两个请求，以避免创建两个连接。  
  
 **ServicePointManager** 是管理 **ServicePoint** 实例的创建和析构的静态选件类。  **ServicePointManager** 创建 **ServicePoint** ，如果应用程序请求不在现有 **ServicePoint** 实例的集合的Internet资源。  销毁**ServicePoint** 实例，则会超出了最大空闲时间时，或者当现有 **ServicePoint** 实例的数目超过 **ServicePoint** 实例的最大数量应用程序时。  可通过将 **ServicePointManager**的 <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> 和 <xref:System.Net.ServicePointManager.MaxServicePoints%2A> 属性控制默认的最大空闲时间和 **ServicePoint** 实例的最大数目。  
  
 连接数客户端和服务器间可能对应用程序吞吐量的重大影响。  默认情况下，使用 <xref:System.Net.HttpWebRequest> 选件类的应用程序最多使用与特定服务器上的两个持久连接，但是，您可以设置最大连接数。基于每个应用程序基类型的。  
  
> [!NOTE]
>  HTTP\/1.1规范范围连接数从应用程序中的每个服务器最多使用两个连接。  
  
 连接的最佳的数目取决于运行应用程序的现实情况。  增加可用的连接数与应用程序不能影响应用程序性能。  若要确定更多连接的影响，请运行性能测试时，更改连接时的数目。  如下面的代码示例所示，可以更改应用程序通过将 **ServicePointManager** 选件类的静态 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 属性使用应用程序初始化连接数，。  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 更改 **ServicePointManager.DefaultConnectionLimit** 属性不影响之前初始化的 **ServicePoint** 实例。  下面的代码演示将现有 **ServicePoint** 的连接限制服务器的http:\/\/www.contoso.com到 `newLimit`存储的值。  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## 请参阅  
 [连接分组](../../../docs/framework/network-programming/connection-grouping.md)   
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)