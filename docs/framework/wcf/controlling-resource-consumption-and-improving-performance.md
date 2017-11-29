---
title: "控制资源使用并提高性能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a829669-5f76-4c88-80ec-92d0c62c0660
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d11cc876ba6fc9dcd94a88ebcde18b4bd13797de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="controlling-resource-consumption-and-improving-performance"></a>控制资源使用并提高性能
本主题介绍 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 体系结构的不同方面的不同属性，这些属性可控制资源使用并影响性能指标。  
  
## <a name="properties-that-constrain-resource-consumption-in-wcf"></a>WCF 中约束资源使用的属性  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 对某些类型的进程应用约束，以实现安全或性能方面的目的。 这些约束有两种主要形式，即：配额和控制器。 *配额*时达到或超过系统中触发立即异常在某个时间点的限制。 *限制*不立即会导致引发异常的限制。 达到控制器限制时，处理仍将继续进行，但不会超过该控制器值所设置的限制。 这一受限处理可能会在另外某处引发异常，但这取决于具体的应用程序。  
  
 除了配额与控制器之间存在区别之外，序列化级别、传输级别以及应用程序级别中也分别存在一些约束属性。 例如，配额 <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>（由所有系统提供的传输绑定元素实现）默认情况下设置为 65,536 字节，以阻止恶意客户端通过导致过度的内存使用来对服务发起拒绝服务攻击。 （通常，您可以通过降低这一值来提高性能）。  
  
 序列化配额的一个示例是 <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> 属性，该属性指定序列化程序在一次 <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> 方法调用中序列化或反序列化的对象的最大数目。 应用程序级控制器的一个示例是 <xref:System.ServiceModel.Dispatcher.ServiceThrottle.MaxConcurrentSessions%2A?displayProperty=nameWithType> 属性，该属性默认情况下将并发会话通道连接的数目限定为不超过 10 个。 （与配额不同，如果达到此控制器值，应用程序会继续处理，但不接受新的会话通道，也就是说，在其中某个会话通道终止之前，新客户端将无法连接。）  
  
 这些控制机制旨在针对某些类型的攻击提供现成的缓解措施，或者改善内存需求量、启动时间等性能指标。 但是，根据不同的应用程序，这些控制机制可能会妨碍服务应用程序性能或者使应用程序根本无法工作。 例如，旨在传送视频的应用程序可能很容易超过默认的 <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType> 属性值。 本主题概述适用于 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 各级别的应用程序的各种控制机制，介绍不同的方法来让您详细了解某个设置是否会妨碍应用程序，并介绍纠正各种问题的方法。 大多数控制器以及某些配额都是在应用程序级别提供的，即使基属性是序列化约束或传输约束，也是如此。 例如，可使用 Service 类的 <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> 属性来设置 <xref:System.ServiceModel.ServiceBehaviorAttribute.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> 属性。  
  
> [!NOTE]
>  如果你有特定的问题，则应该先阅读[WCF 疑难解答快速入门](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)以查看你的问题 （和解决方案） 是否存在列出。  
  
 禁止序列化进程的属性列在[数据的安全注意事项](../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)。 限制与传输相关的资源消耗的属性列在[传输配额](../../../docs/framework/wcf/feature-details/transport-quotas.md)。 限制应用程序层的资源使用的属性是 <xref:System.ServiceModel.Dispatcher.ServiceThrottle> 类的成员。  
  
## <a name="detecting-application-and-performance-issues-related-to-quota-settings"></a>检测与配额设置有关的应用程序和性能问题  
 为了在各种应用程序类型中启用基本的应用程序功能，同时针对常见安全问题提供基本保护，系统选择了上述值的默认值。 但是，不同的应用程序设计可能会超出一个或多个控制器设置，不过可以通过其他手段保护应用程序的安全，并使应用程序按照设计的方式工作。 在这些情况下，必须识别出超过的是哪些控制器值，是在哪一级别超过的，并确定适当的操作过程来提高应用程序的吞吐量。  
  
 通常，当编写并调试应用程序时，应当在配置文件中或者以编程方式将 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> 属性设置为 `true`。 这指示 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 将服务异常堆栈跟踪返回给客户端应用程序以供查看。 此功能可报告大多数的应用程序级异常，旨在显示导致出现问题的相关配额设置。  
  
 一些异常是在运行时发生的，在应用程序层不可见。它们不是使用此机制返回的，并且不能由自定义 <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType> 实现来处理。 如果您使用的是像 Microsoft Visual Studio 这样的开发环境，则这些异常中的大多数都将自动显示。 但是，可以通过开发环境设置，例如屏蔽一些例外情况[仅我的代码](http://go.microsoft.com/fwlink/?LinkId=82174)Visual Studio 2005 中的设置。  
  
 无论开发环境的功能如何，您都可以使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 跟踪和消息日志记录的功能来对所有异常进行调试并优化应用程序的性能。 有关详细信息，请参阅[解决应用程序使用跟踪](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)。  
  
## <a name="performance-issues-and-xmlserializer"></a>性能问题和 XmlSerializer  
 如果服务和客户端应用程序使用可用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化的数据类型，则会在运行时生成并编译这些数据类型的序列化代码，从而导致启动性能降低。  
  
> [!NOTE]
>  预生成的序列化代码只能在客户端应用程序中使用，不能在服务中使用。  
  
 [ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)可以通过从应用程序的已编译程序集生成必要的序列化代码提高这些应用程序的启动性能。 有关详细信息，请参阅[How to： 改善启动时间的 WCF 客户端应用程序使用 XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)。  
  
## <a name="performance-issues-when-hosting-wcf-services-under-aspnet"></a>在 ASP.NET 下承载 WCF 服务时的性能问题  
 当在 IIS 和 ASP.NET 下承载 WCF 服务时，IIS 和 ASP.NET 的配置设置可能会影响 WCF 服务的吞吐量和内存需求量。  [!INCLUDE[crabout](../../../includes/crabout-md.md)]ASP.NET 性能，请参阅[因而提高了 ASP.NET 性能](http://go.microsoft.com/fwlink/?LinkId=186462)。  可能具有意外结果的一种设置为 <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>，该设置为 <xref:System.Web.Configuration.ProcessModelSection> 的属性。 如果应用程序具有固定量或少量的客户端，则将 <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A> 设置为 2 可能会显著提高 CPU 利用率接近 100% 的多处理器计算机上的吞吐量。 这种性能上的提高是以增加内存使用为代价的，这可能会降低可伸缩性。  
  
## <a name="see-also"></a>另请参阅  
 [管理和诊断](../../../docs/framework/wcf/diagnostics/index.md)  
 [大型数据和流式处理](../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)
