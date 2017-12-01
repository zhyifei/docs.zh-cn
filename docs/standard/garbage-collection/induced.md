---
title: "被动回收"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: garbage collection, forced
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92918e347b10dfcf3a0d6e2c08cec8c7a6963f5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="induced-collections"></a>被动回收
在大多数情况下，垃圾回收器可以确定执行回收的最佳时间，应让其独立运行。 在某些不常见的情况下，强制回收可以提高应用程序的性能。 在这些情况下，你可以通过使用引发垃圾回收<xref:System.GC.Collect%2A?displayProperty=nameWithType>方法来强制进行垃圾回收。  
  
 使用<xref:System.GC.Collect%2A?displayProperty=nameWithType>方法是在应用程序代码中的特定点正在使用的内存量，大大减少时。 例如，如果你的应用程序使用具有几个控件的复杂对话框框，则调用<xref:System.GC.Collect%2A>关闭该对话框时可以通过立即回收对话框中使用的内存来提高性能。 请确保应用程序不会过于频繁地引发垃圾回收，否则当垃圾回收器无效率地尝试回收对象时，可能会使性能降低。 你可以提供<xref:System.GCCollectionMode.Optimized?displayProperty=nameWithType>枚举值到<xref:System.GC.Collect%2A>方法，以收集仅在下一节中所述，将工作效率，集合时。  
  
## <a name="gc-collection-mode"></a>GC 回收模式  
 你可以使用之一<xref:System.GC.Collect%2A?displayProperty=nameWithType>包括的方法重载<xref:System.GCCollectionMode>要指定强制回收的行为，如下所示的值。  
  
|`GCCollectionMode` 值|描述|  
|------------------------------|-----------------|  
|<xref:System.GCCollectionMode.Default>|正在运行版本的.NET 中使用默认垃圾集合设置。|  
|<xref:System.GCCollectionMode.Forced>|强制立即执行垃圾回收。 这是等效于调用<xref:System.GC.Collect?displayProperty=nameWithType>重载。 它会导致对所有分代进行完全阻塞回收。<br /><br /> 你还可以通过设置压缩大型对象堆<xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>属性<xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce?displayProperty=nameWithType>之前强制立即的完全阻止垃圾回收。|  
|<xref:System.GCCollectionMode.Optimized>|使垃圾回收器可以确定当前时间是否是回收对象的最佳时间。<br /><br /> 垃圾回收器可能判定回收效率不够高，因此回收不合理，在这种情况下将返回而不回收对象。|  
  
## <a name="background-or-blocking-collections"></a>后台回收或阻塞回收  
 你可以调用<xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=nameWithType>方法重载来指定或不是否阻止被动的集合。 执行回收的类型取决于的方法的组合`mode`和`blocking`参数。 `mode`为属于<xref:System.GCCollectionMode>枚举，和`blocking`是<xref:System.Boolean>值。 下表总结了`mode`和`blocking`自变量。  
  
|`mode`|`blocking` = `true`|`blocking` = `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode.Forced> 或 <xref:System.GCCollectionMode.Default>|尽快执行阻塞回收。 如果正在进行后台回收，生成是 0 或 1，<xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29>方法立即触发阻碍性回收，并在回收完成时返回。 如果后台回收正在进行和`generation`参数为 2，方法等待后台回收完成，触发阻止第 2 代回收，然后返回。|尽快执行回收。 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29>方法请求一个后台回收，但这不能保证; 取决于具体情况，可能仍执行阻碍性回收。 如果后台回收正在进行，该方法将立即返回。|  
|<xref:System.GCCollectionMode.Optimized>|可能执行阻碍性回收，具体取决于垃圾回收器的状态和`generation`参数。 垃圾回收器会尽量提供最佳性能。|根据垃圾回收器的状态，有时可执行回收。 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29>方法请求一个后台回收，但这不能保证; 取决于具体情况，可能仍执行阻碍性回收。 垃圾回收器会尽量提供最佳性能。 如果后台回收正在进行，该方法将立即返回。|  
  
## <a name="see-also"></a>另请参阅  
 [延迟模式](../../../docs/standard/garbage-collection/latency.md)  
 [垃圾回收](../../../docs/standard/garbage-collection/index.md)
