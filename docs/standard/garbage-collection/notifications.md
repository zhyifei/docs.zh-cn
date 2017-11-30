---
title: "垃圾回收通知"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a>垃圾回收通知
在有些情况下，公共语言运行时执行的完整垃圾回收（即第 2 代回收）可能会对性能产生负面影响。 这可以是一个问题尤其是对于处理大量请求; 的服务器在这种情况下，长垃圾回收可能会导致请求超时。若要防止中重要的时间段期间发生的完整集合，你可以通知完整的垃圾回收正在接近和则采取措施以将工作负荷重定向到另一个服务器实例。 你可以还自己引发回收，前提是当前的服务器实例不需要处理请求。  
  
 <xref:System.GC.RegisterForFullGCNotification%2A>方法注册的通知，以便在运行时检测该接近完整垃圾回收时引发。 有两个部分： 此通知： 当接近完整垃圾回收和完整的垃圾回收完成时。  
  
> [!WARNING]
>  只有阻止垃圾回收会引发通知。 当[ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)配置元素启用时，背景垃圾回收不会引发通知。  
  
 若要确定已时发出通知，请使用<xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法。 通常情况下，使用这些方法中的`while`循环来持续获取<xref:System.GCNotificationStatus>显示通知的状态的枚举。 如果此值为<xref:System.GCNotificationStatus.Succeeded>，你可以执行以下操作：  
  
-   响应使用获取通知<xref:System.GC.WaitForFullGCApproach%2A>方法，你可以重定向工作负荷并可能自己引发回收。  
  
-   响应使用获取通知<xref:System.GC.WaitForFullGCComplete%2A>方法，可使可用要再次处理请求的当前服务器实例。 你还可以收集信息。 例如，你可以使用<xref:System.GC.CollectionCount%2A>方法来记录的集合的数量。  
  
 <xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法设计为协同工作。 使用其中一种可能产生不确定结果。  
  
## <a name="full-garbage-collection"></a>完整的垃圾回收  
 在以下方案中的任何一种情况时，运行时将导致完整垃圾回收：  
  
-   足够的内存被提升到第 2 进行下一步的第 2 代回收代。  
  
-   足够的内存被提升到大型对象堆进行下一步的第 2 代回收。  
  
-   第 1 代集合升级到的其他因素由于第 2 代集合。  
  
 在指定的阈值<xref:System.GC.RegisterForFullGCNotification%2A>方法应用到的前两个方案。 但是，在第一个方案中你将不一定会收到通知在两个原因你指定的阈值值成正比的时间：  
  
-   运行时不会检查每个小型对象分配 （出于性能原因）。  
  
-   仅生成 1 的集合将内存提升到第 2 代。  
  
 第三个方案也增加了当你将收到通知的不确定性。 尽管这并不保证数据，但它未证实是有用的方法，以将请求重定向在此时间或集合自行引发时可以更好地容纳减轻不适当的完整垃圾回收的影响。  
  
## <a name="notification-threshold-parameters"></a>通知阈值参数  
 <xref:System.GC.RegisterForFullGCNotification%2A>方法具有两个参数指定的第 2 代对象和大型对象堆的阈值。 在满足这些值后，应引发垃圾回收通知。 下表介绍了这些参数。  
  
|参数|描述|  
|---------------|-----------------|  
|`maxGenerationThreshold`|一个介于 1 和 99 之间的数字，指定应何时引发通知根据在第 2 代提升的对象。|  
|`largeObjectHeapThreshold`|一个介于 1 和 99 之间的数字，指定应何时引发通知基于大型对象堆中分配的对象。|  
  
 如果指定一个值，太高，则很可能你将收到一个通知，但可能太长的运行时就会导致回收之前要等待的时间。 如果你自己引发回收，你可能回收更多的对象不是如果运行时就会导致回收将回收。  
  
 如果指定一个值，太低，可能会导致运行时集合之前你有足够的时间，若要得到通知。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 在下面的示例中，一组服务器传入 Web 请求提供服务。 若要模拟处理请求的工作负荷，字节数组添加到<xref:System.Collections.Generic.List%601>集合。 每个服务器垃圾回收通知的注册，然后启动上的线程`WaitForFullGCProc`用户方法来持续监视<xref:System.GCNotificationStatus>返回的枚举<xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法。  
  
 <xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法调用其各自的事件处理用户方法时引发通知：  
  
-   `OnFullGCApproachNotify`  
  
     此方法调用`RedirectRequests`用户方法，指示请求队列服务器挂起发送请求到的服务器。 这由设置类级变量模拟`bAllocate`到`false`以便分配更多的对象。  
  
     接下来，`FinishExistingRequests`用户方法调用以完成处理挂起的服务器请求。 这由清除模拟<xref:System.Collections.Generic.List%601>集合。  
  
     最后，因为工作负载较轻，被引发垃圾回收。  
  
-   `OnFullGCCompleteNotify`  
  
     此方法调用用户方法`AcceptRequests`继续接受请求，因为服务器无法再很容易受到完整垃圾回收。 此操作由设置模拟`bAllocate`变量`true`，使对象可以添加到恢复<xref:System.Collections.Generic.List%601>集合。  
  
 下面的代码包含`Main`方法的示例。  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 下面的代码包含`WaitForFullGCProc`包含连续的 while 循环，以检查垃圾回收通知的用户方法。  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 下面的代码包含`OnFullGCApproachNotify`方法，如从调用  
  
 `WaitForFullGCProc` 方法。  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 下面的代码包含`OnFullGCApproachComplete`方法，如从调用  
  
 `WaitForFullGCProc` 方法。  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 下面的代码包含从调用的用户方法`OnFullGCApproachNotify`和`OnFullGCCompleteNotify`方法。 用户方法将请求重定向、 完成现有请求，以及完整的垃圾回收发生后再继续请求。  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 整个代码示例是，如下所示：  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [垃圾回收](../../../docs/standard/garbage-collection/index.md)
