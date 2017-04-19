---
title: "何时使用泛型集合 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
caps.latest.revision: 17
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9dcf0802b1d9a1d6b63d108289cbc814b73e8c48
ms.lasthandoff: 04/18/2017

---
# <a name="when-to-use-generic-collections"></a>何时使用泛型集合
通常建议使用泛型集合，因为这样你可以获得类型安全的直接优点而无需从基集合类型派生和实现特定类型的成员。 当集合元素为值类型时，泛型集合类型也通常优于对应的非泛型集合类型（比从非泛型基集合类型派生的类型好），因为使用泛型时不必对元素进行装箱。  
  
 对于面向 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 或更高版本的程序，你应在多个线程可能会同时向集合添加项或从集合中删除项时使用 <xref:System.Collections.Concurrent> 命名空间中的泛型集合。  
  
 以下泛型类型对应于现有集合类型：  
  
-   <xref:System.Collections.Generic.List%601> 是对应于 <xref:System.Collections.ArrayList> 的泛型类型。  
  
-   <xref:System.Collections.Generic.Dictionary%602> 和 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 是对应于 <xref:System.Collections.Hashtable> 的泛型类型。  
  
-   <xref:System.Collections.ObjectModel.Collection%601> 是对应于 <xref:System.Collections.CollectionBase> 的泛型类型。 <xref:System.Collections.ObjectModel.Collection%601> 可用作基类，但与 <xref:System.Collections.CollectionBase> 不同，它不是抽象类。 这使得它更易于使用。  
  
-   <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 是对应于 <xref:System.Collections.ReadOnlyCollectionBase> 的泛型类型。 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 不是抽象类，且具有一个构造函数，可轻松将现有 <xref:System.Collections.Generic.List%601> 作为只读集合进行公开。  
  
-   <xref:System.Collections.Generic.Queue%601>、<xref:System.Collections.Concurrent.ConcurrentQueue%601>、<xref:System.Collections.Generic.Stack%601>、<xref:System.Collections.Concurrent.ConcurrentStack%601> 和 <xref:System.Collections.Generic.SortedList%602> 泛型类分别对应于相同名称的非泛型类。  
  
## <a name="additional-types"></a>其他类型  
 几种泛型集合类型没有对应的非泛型集合类型。 它们包括以下类型：  
  
-   <xref:System.Collections.Generic.LinkedList%601> 是一个通用的链接列表，该列表提供 O(1) 插入和删除操作。  
  
-   <xref:System.Collections.Generic.SortedDictionary%602> 是具有 O（日志 `n`）插入和检索操作的排序字典，这些特征使其成为 <xref:System.Collections.Generic.SortedList%602> 的有效替换项。  
  
-   <xref:System.Collections.ObjectModel.KeyedCollection%602> 是列表和字典的结合，它提供一种方法来存储包含自己的键的对象。  
  
-   <xref:System.Collections.Concurrent.BlockingCollection%601> 通过限制和阻塞功能实现集合类。  
  
-   <xref:System.Collections.Concurrent.ConcurrentBag%601> 可实现无序元素的快速插入和删除。  
  
## <a name="linq-to-objects"></a>LINQ to Objects  
 LINQ to Objects 功能允许使用 LINQ 查询来访问内存中的对象，但条件是该对象类型要实现 <xref:System.Collections.IEnumerable?displayProperty=fullName> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 接口。 LINQ 查询提供了一种通用的数据访问模式；与标准 `foreach` 循环相比，它通常更加简洁，可读性更高；这种查询可提供筛选、排序和分组功能。 LINQ 查询还可提高性能。 有关详细信息，请参阅 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) 和[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)。  
  
## <a name="additional-functionality"></a>其他功能  
 一些泛型类型具有非泛型集合类型中找不到的功能。 比如与非泛型 <xref:System.Collections.ArrayList> 类相对的 <xref:System.Collections.Generic.List%601> 类有大量接受泛型委托的方法，例如允许你指定搜索列表的方法的 <xref:System.Predicate%601> 委托、代表对列表中每个元素发挥作用的 <xref:System.Action%601> 委托和在类型间定义对话的 <xref:System.Converter%602> 委托。  
  
 <xref:System.Collections.Generic.List%601> 类允许用户指定自己的 <xref:System.Collections.Generic.IComparer%601> 泛型接口实现，用于对列表进行排序和搜索。 <xref:System.Collections.Generic.SortedDictionary%602> 和 <xref:System.Collections.Generic.SortedList%602> 类也具有此功能。 另外，这些类使你可以在创建集合时指定比较器。 同样地，使用 <xref:System.Collections.Generic.Dictionary%602> 和 <xref:System.Collections.ObjectModel.KeyedCollection%602> 类可以指定自己的相等性比较器。  
  
## <a name="see-also"></a>另请参阅  
 [集合和数据结构](../../../docs/standard/collections/index.md)   
 [常用的集合类型](../../../docs/standard/collections/commonly-used-collection-types.md)   
 [泛型](../../../docs/standard/generics/index.md)
