---
title: "如何：执行对象的延迟初始化 | Microsoft Docs"
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
  - ".NET 中的延迟初始化, 如何执行"
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 如何：执行对象的延迟初始化
<xref:System.Lazy%601?displayProperty=fullName> 类简化了执行对象的延迟初始化和实例化的工作。  通过以延迟方式实例化对象，可避免在根本不需要的情况下必须创建所有的对象，或者可以将对象的初始化延迟到第一次访问它们的时候。  有关更多信息，请参见[延迟初始化](../../../docs/framework/performance/lazy-initialization.md)。  
  
## 示例  
 下面的示例演示如何使用 <xref:System.Lazy%601> 初始化值。  假定延迟变量可能不是必需的，具体取决于将 `someCondition` 变量设置为 true 或 false 的一些其他代码。  
  
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
  
## 示例  
 下面的示例演示如何使用 <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> 类来初始化仅对当前线程上的当前对象实例可见的类型。  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## 请参阅  
 <xref:System.Threading.LazyInitializer?displayProperty=fullName>   
 [延迟初始化](../../../docs/framework/performance/lazy-initialization.md)