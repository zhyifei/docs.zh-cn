---
title: ".NET Framework 4.5.1 中的运行时更改 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- runtime changes
- .NET Framework 4.5.1
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e4903c2f25354005f95b3ed8f9728cfe8a0a92e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-451"></a>.NET Framework 4.5.1 中的运行时更改
在极少数情况下，运行时更改可能影响面向 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 或 4.5 但在 4.51 运行时上运行的现有应用。 它们包括以下区域中的更改：  
  
-   [核心](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
 下表中的“范围”列指定每个更改的基数：  
  
-   主要。 显著的更改，可影响大量应用或需要修改大量代码。 请注意，没有运行时更改归入此类别。  
  
-   次要。 影响少量应用或需要修改少量代码的更改。  
  
-   边缘。 仅在少数非常特定的情况下影响应用的更改。  
  
-   透明。 对应用的开发人员或用户没有明显影响的更改。 不需要由于此更改而修改应用。  
  
<a name="Core"></a>   
## <a name="core-runtime-changes"></a>核心运行时更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> 序列化|在 .NET Framework 4.5 中使用 <xref:System.Runtime.Serialization.NetDataContractSerializer> 序列化的 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象，仅仅因为类型的内部更改而无法在 .NET Framework 4.5.1 和 4.5.2 中进行反序列化。<br /><br /> 此更改*不*适用于以下场景：<br /><br /> 一个 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象在 .NET Framework 4.5 中进行序列化，在 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中进行反序列化。 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中的 <xref:System.Runtime.Serialization.NetDataContractSerializer> 可以对该对象进行反序列化。<br /><br /> 一个 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象在 .NET Framework 的较高版本中进行序列化，在 .NET Framework 4.5 中进行反序列化。 .NET Framework 4.5 中的 <xref:System.Runtime.Serialization.NetDataContractSerializer> 可以对该对象进行反序列化。<br /><br /> 一个 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象在高于 .NET Framework 4.5 的任何 .NET Framework 版本之间进行版本间序列化和反序列化。 此更改*仅*适用于使用 .NET Framework 4.5 序列化的对象。|如果有必要在 .NET Framework 4.5 中对 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象进行序列化，在更高版本的 .NET Framework 中对该对象进行反序列化，可以使用以下两种解决办法：<br /><br /> 使用备用序列化程序，如 <xref:System.Runtime.Serialization.DataContractSerializer> 或 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>。<br /><br /> 升级到 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]，它支持对使用 .NET Framework 4.5 序列化的 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象进行反序列化。|次要|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> 类|<xref:System.Diagnostics.Tracing.EventListener> 会截断带有内嵌空字符的字符串。 空字符不受 <xref:System.Diagnostics.Tracing.EventSource> 类支持。|此更改仅影响使用 <xref:System.Diagnostics.Tracing.EventListener> 读取进程中 <xref:System.Diagnostics.Tracing.EventSource> 数据的应用以及使用空字符作为分隔符的应用。|边缘|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 类|运行时现在强制执行用于指定以下内容的协定：从 <xref:System.Diagnostics.Tracing.EventSource> 派生、定义 ETW 事件方法的类必须使用事件 ID（后跟 ETW 事件方法已传递的相同自变量）调用基类 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> 方法。|如果 <xref:System.Diagnostics.Tracing.EventListener> 读取违反此协定的事件源进程中的 <xref:System.Diagnostics.Tracing.EventSource> 数据，则将引发 <xref:System.IndexOutOfRangeException> 异常。<br /><br /> 请参阅[缓解：EventSource.WriteEvent 方法调用](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)|次要|  
|跨应用程序域的对象的反序列化|在某些情况下，当应用使用两个或更多带有不同应用程序基的应用域时，尝试跨应用域在逻辑调用上下文中为对象反序列化将引发异常。|此问题在十分特定的方案中出现。 有关详细信息和缓解措施，请参阅[缓解：跨应用域的对象的反序列化](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)。|边缘|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName> 方法|在 [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 应用中，[!INCLUDE[wrt](../../../includes/wrt-md.md)] 流适配器不再从 <xref:System.IO.Stream.Dispose%2A> 方法调用 <xref:System.IO.Stream.FlushAsync%2A> 方法。|此更改应该为透明。 开发人员可以通过编写如下代码还原之前的行为：<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|透明|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>Windows Communication Foundation (WCF) 运行时更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|[minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx) 配置设置|此设置可确立激活 WCF 服务之前必须在服务器上可用的最小内存。 它旨在阻止 <xref:System.OutOfMemoryException> 异常。 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，此设置没有效果。 在 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 中，观察到此设置。|如果 Web 服务器上的可用内存少于由配置设置定义的百分比，将引发异常。 某些成功启动并且在受约束的内存环境中运行的 WCF 服务现在可能失败。<br /><br /> 请参阅[缓解：minFreeMemoryPercentageToActiveService 配置设置](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md)。|次要|  
  
## <a name="see-also"></a>另请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.2 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
