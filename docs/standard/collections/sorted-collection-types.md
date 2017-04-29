---
title: "已排序的集合类型 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET Framework], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ac1552dba8756d033ee02651142476c4a15a485
ms.lasthandoff: 04/18/2017

---
# <a name="sorted-collection-types"></a>已排序的集合类型
<xref:System.Collections.SortedList?displayProperty=fullName> 类、<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> 泛型类和 <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> 泛型类与 <xref:System.Collections.Hashtable> 类和 <xref:System.Collections.Generic.Dictionary%602> 泛型类的类似之处在于均实现 <xref:System.Collections.IDictionary> 接口，不同之处在于这三个类的元素根据键保持排序顺序不变，并且没有哈希表的 O(1) 插入和检索特性。 这三个类具有若干共性：  
  
-   这三个类全都实现 <xref:System.Collections.IDictionary?displayProperty=fullName> 接口。 其中两个泛型类还实现 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName> 泛型接口。  
  
-   每个元素都是用于枚举的键/值对。  
  
    > [!NOTE]
    >  枚举时，非泛型 <xref:System.Collections.SortedList> 类返回的是 <xref:System.Collections.DictionaryEntry> 对象，尽管两个泛型类型返回的是 <xref:System.Collections.Generic.KeyValuePair%602> 对象。  
  
-   元素根据 <xref:System.Collections.IComparer?displayProperty=fullName> 实现代码（对于非泛型 <xref:System.Collections.SortedList>）或 <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> 实现代码（对于两个泛型类）进行排序。  
  
-   每个类提供了返回仅包含键或仅包含值的集合的属性。  
  
 下表列出了两个已排序的列表类与 <xref:System.Collections.Generic.SortedDictionary%602> 类的一些区别。  
  
|<xref:System.Collections.SortedList> 非泛型类和<xref:System.Collections.Generic.SortedList%602> 泛型类|<xref:System.Collections.Generic.SortedDictionary%602> 泛型类|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|返回键和值的属性是有索引的，从而允许高效的索引检索。|无索引的检索。|  
|检索属于 O(log `n`) 操作。|检索属于 O(log `n`) 操作。|  
|插入和删除一般属于 O(`n`) 操作；不过，对于已按排序顺序排序的数据，插入属于 O(1) 操作，这样每个元素都可以添加到列表的末尾。 （这假设不需要调整大小。）|插入和删除属于 O(log `n`) 操作。|  
|相比 <xref:System.Collections.Generic.SortedDictionary%602>，使用的内存更少。|相比 <xref:System.Collections.SortedList> 非泛型类和<xref:System.Collections.Generic.SortedList%602> 泛型类，使用的内存更多。|  
  
 对于必须能够通过多线程进行并发访问的已排序列表或字典，可以向派生自 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 的类添加排序逻辑。  
  
> [!NOTE]
>  对于包含自己的键的值（例如，包含员工 ID 号的员工记录），可以从 <xref:System.Collections.ObjectModel.KeyedCollection%602> 泛型类进行派生，创建具有部分列表特性和部分字典特性的键控集合。  
  
 自 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 起，<xref:System.Collections.Generic.SortedSet%601> 类提供自平衡树，用于在执行插入、删除和搜索操作之后保持数据的排序顺序不变。 此类和 <xref:System.Collections.Generic.HashSet%601> 类实现 <xref:System.Collections.Generic.ISet%601> 接口。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [常用的集合类型](../../../docs/standard/collections/commonly-used-collection-types.md)
