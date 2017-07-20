---
title: ".NET Framework 应用程序中的缓存 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ASP.NET 缓存"
  - "缓存 [.NET Framework]"
  - "缓存 [ASP.NET]"
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
caps.latest.revision: 26
author: "tdykstra"
ms.author: "tdykstra"
manager: "wpickett"
caps.handback.revision: 26
---
# .NET Framework 应用程序中的缓存
缓存使您能够在内存中存储数据以实现快速访问。  当再次访问数据时，应用程序可以从缓存获取数据，而无需从原始源进行检索。  这可以改进性能和伸缩性。  此外，缓存还使数据在数据源临时不可用时可用。  
  
 .NET Framework 提供缓存功能，可以使用此功能改善 Windows 客户端和服务器应用程序（包括 ASP.NET.）的性能和可扩展性。  
  
> [!NOTE]
>  在 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 及早期版本中，ASP.NET 在 <xref:System.Web.Caching> 命名空间中提供内存中缓存实现。  在 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 的早期版本中，缓存仅可用于 <xref:System.Web> 命名空间，因此在 ASP.NET 类上需要有依赖项。  在 .NET Framework 4 中，<xref:System.Runtime.Caching> 命名空间包含针对 Web 和非 Web 应用程序设计的 API。  
  
## 缓存数据  
 您可以使用 <xref:System.Runtime.Caching> 命名空间中的类来缓存信息。  该命名空间中的缓存类提供以下功能：  
  
-   抽象类型，为创建自定义缓存实现提供基础。  
  
-   一个具体的内存中对象缓存实现。  
  
 抽象基本缓存类 \(<xref:System.Runtime.Caching.ObjectCache>\) 定义以下缓存任务：  
  
-   创建和管理缓存条目。  
  
-   指定过期和逐出信息。  
  
-   触发因响应缓存条目更改而引发的事件。  
  
 <xref:System.Runtime.Caching.MemoryCache> 类是 <xref:System.Runtime.Caching.ObjectCache> 类的内存中对象缓存实现。  您可以对多数缓存任务使用 <xref:System.Runtime.Caching.MemoryCache> 类。  
  
> [!NOTE]
>  <xref:System.Runtime.Caching.MemoryCache> 类在 <xref:System.Web.Caching> 命名空间中定义的 ASP.NET 缓存对象上进行建模。  因此，内部缓存逻辑与 ASP.NET 早期版本中提供的逻辑类似。  
  
 有关如何在 WPF 应用程序中使用缓存的示例，请参见[演练：在 WPF 应用程序中缓存应用程序数据](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)。  
  
## 在 ASP.NET 应用程序中缓存  
 <xref:System.Runtime.Caching> 命名空间中的缓存类提供在 ASP.NET 中缓存数据的功能。  
  
> [!NOTE]
>  如果您的应用程序以 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 或早期版本为目标，则必须使用 <xref:System.Web.Caching> 命名空间中定义的缓存类。  有关详细信息，请参阅[ASP.NET Caching Overview](../Topic/ASP.NET%20Caching%20Overview.md)。  
  
> [!NOTE]
>  当开发新应用程序时，建议您使用 <xref:System.Runtime.Caching.MemoryCache> 类。  <xref:System.Runtime.Caching> 命名空间中提供的 API 与 <xref:System.Web.Caching.Cache> 命名空间中提供的 API 类似。  因此，如果您使用过 ASP.NET 早期版本中的缓存，则会对 API 很熟悉。有关如何在 ASP.NET 应用程序中使用缓存的示例，请参见[Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md)。  
  
### 输出缓存  
 若要手动缓存应用程序数据，您可以使用 ASP.NET 中的 <xref:System.Runtime.Caching.MemoryCache> 类。ASP.NET 还支持输出缓存，以便将页面、控件和 HTTP 响应生成的输出存储到内存中。  您可以在 ASP.NET 网页中通过声明的方式，或者使用 Web.config 文件中的设置来配置输出缓存。  有关详细信息，请参阅[caching 的 outputCache 元素（ASP.NET 设置架构）](http://msdn.microsoft.com/zh-cn/47cd2b47-316f-4dfd-bbf8-539be3066fee)。  
  
 ASP.NET 允许您通过创建自定义输出缓存提供程序来扩展输出缓存。  通过使用自定义提供程序，可使用其他存储设备（如磁盘、云存储和分布式缓存引擎）来存储缓存内容。  若要创建自定义输出缓存提供程序，可创建从 <xref:System.Web.Caching.OutputCacheProvider> 类派生的类并将应用程序配置为使用自定义输出缓存提供程序。  
  
## 在 WCF REST 服务中缓存  
 对于 WCF REST 服务，.NET Framework 允许您利用 ASP.NET 中提供的声明式输出缓存。这样，您就可以缓存来自 WCF REST 服务操作的响应。  如果用户向配置为进行缓存的服务发送了 HTTP GET 请求，ASP.NET 将发送回已缓存的响应，且不会调用服务方法。  在缓存过期后，用户下次发送 HTTP GET 请求时，将会调用服务方法且再次缓存响应。  
  
 通过 .NET Framework，您还可以实现条件 HTTP GET 缓存。  在 REST 方案中，条件 HTTP GET 请求通常由服务用来实现[HTTP Specification](http://go.microsoft.com/fwlink/?LinkId=165800)所描述的智能 HTTP 缓存。  有关更多信息，请参见 [WCF Web HTTP 服务的缓存支持](http://go.microsoft.com/fwlink/?LinkId=184598)。  
  
## 在 .NET Framework 中扩展缓存  
 .NET Framework 中的缓存被设计为可进行扩展。  通过 <xref:System.Runtime.Caching.ObjectCache> 类，您可以创建自定义缓存实现。  该类提供可用于所有托管应用程序的成员，包括 Windows 窗体、Windows Presentation Foundation \(WPF\) 和 Windows Communications Foundation \(WCF\)。  若要创建使用不同存储机制的缓存类，或者要对缓存操作进行精细控制，则可以执行此操作。  
  
 若要扩展缓存，可执行以下操作：  
  
-   创建从 <xref:System.Runtime.Caching.ObjectCache> 类派生的自定义类，然后在派生类中提供自定义缓存实现。  
  
-   创建从 <xref:System.Runtime.Caching.MemoryCache> 类派生的类，并自定义或扩展派生类。  有关如何执行此操作的示例，请参见 [使用多个缓存对象缓存应用程序在 ASP.NET 应用程序的](http://blogs.msdn.com/aspnetue/archive/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application.aspx)。  
  
-   创建从 <xref:System.Web.Caching.OutputCacheProvider> 类派生的类，并将应用程序配置为使用自定义输出缓存提供程序。  
  
 有关更多信息，请参见 Scott Guthrie 博客上的[Extensible Output Caching with ASP.NET 4 \(VS 2010 and .NET 4.0 Series\)](http://go.microsoft.com/fwlink/?LinkId=185772)文章。  
  
## 请参阅  
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching.MemoryCache>   
 [演练：在 WPF 应用程序中缓存应用程序数据](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)   
 [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md)