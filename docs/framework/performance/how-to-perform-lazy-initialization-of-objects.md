---
title: "如何：执行对象的延迟初始化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1728165dbed9a011afe6e621df86be7b372a684f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a><span data-ttu-id="d680f-102">如何：执行对象的延迟初始化</span><span class="sxs-lookup"><span data-stu-id="d680f-102">How to: Perform Lazy Initialization of Objects</span></span>
<span data-ttu-id="d680f-103"><xref:System.Lazy%601?displayProperty=nameWithType> 类可简化执行迟缓初始化和对象实例化的工作。</span><span class="sxs-lookup"><span data-stu-id="d680f-103">The <xref:System.Lazy%601?displayProperty=nameWithType> class simplifies the work of performing lazy initialization and instantiation of objects.</span></span> <span data-ttu-id="d680f-104">通过以迟缓方式初始化对象，可在不需要对象的情况下避免创建所有对象，或可在首次访问对象之后再进行迟缓初始化。</span><span class="sxs-lookup"><span data-stu-id="d680f-104">By initializing objects in a lazy manner, you can avoid having to create them at all if they are never needed, or you can postpone their initialization until they are first accessed.</span></span> <span data-ttu-id="d680f-105">若要了解详细信息，请参阅[迟缓初始化](../../../docs/framework/performance/lazy-initialization.md)</span><span class="sxs-lookup"><span data-stu-id="d680f-105">For more information, see [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d680f-106">示例</span><span class="sxs-lookup"><span data-stu-id="d680f-106">Example</span></span>  
 <span data-ttu-id="d680f-107">以下示例演示如何使用 <xref:System.Lazy%601> 初始化值。</span><span class="sxs-lookup"><span data-stu-id="d680f-107">The following example shows how to initialize a value with <xref:System.Lazy%601>.</span></span> <span data-ttu-id="d680f-108">假定可能不需要迟缓变量，这取决于将 `someCondition` 变量设置为 true 或 false 的一些其他代码。</span><span class="sxs-lookup"><span data-stu-id="d680f-108">Assume that the lazy variable might not be needed, depending on some other code that sets the `someCondition` variable to true or false.</span></span>  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
{  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="d680f-109">示例</span><span class="sxs-lookup"><span data-stu-id="d680f-109">Example</span></span>  
 <span data-ttu-id="d680f-110">以下示例演示如何使用 <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> 类初始化仅对当前线程上的当前对象实例可见的类型。</span><span class="sxs-lookup"><span data-stu-id="d680f-110">The following example shows how to use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to initialize a type that is visible only to the current object instance on the current thread.</span></span>  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="d680f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d680f-111">See Also</span></span>  
 <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>  
 [<span data-ttu-id="d680f-112">迟缓初始化</span><span class="sxs-lookup"><span data-stu-id="d680f-112">Lazy Initialization</span></span>](../../../docs/framework/performance/lazy-initialization.md)
