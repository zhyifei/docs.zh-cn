---
title: "已排序的集合类型 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "集合 [.NET Framework], SortedList 集合类型"
  - "将集合中的数据分组, SortedList 集合类型"
  - "SortedDictionary 集合类型"
  - "SortedList 类, 将集合中的数据分组"
  - "SortedList 集合类型"
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# 已排序的集合类型
<xref:System.Collections.SortedList?displayProperty=fullName> 类、<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> 泛型类和 <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> 泛型类类似于 <xref:System.Collections.Hashtable> 类和 <xref:System.Collections.Generic.Dictionary%602> 泛型类，因为它们也实现 <xref:System.Collections.IDictionary> 接口，但是它们以基于键的排序顺序维护元素，没有哈希表的 O\(1\) 插入和检索特性。  这三个类具有若干共性：  
  
-   三个类都实现 <xref:System.Collections.IDictionary?displayProperty=fullName> 接口。  两个泛型类还实现 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName> 泛型接口。  
  
-   每个元素是一个键\/值对，以进行枚举。  
  
    > [!NOTE]
    >  非泛型 <xref:System.Collections.SortedList> 类在被枚举时返回 <xref:System.Collections.DictionaryEntry> 对象，而两个泛型类型返回 <xref:System.Collections.Generic.KeyValuePair%602> 对象。  
  
-   元素按照 <xref:System.Collections.IComparer?displayProperty=fullName> 实现（对于非泛型 <xref:System.Collections.SortedList>）或 <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> 实现（对于两个泛型类）排序。  
  
-   每个类提供了返回仅包含键或仅包含值的集合的属性。  
  
 下表列举两个排序的列表类与 <xref:System.Collections.Generic.SortedDictionary%602> 类之间的一些区别。  
  
|<xref:System.Collections.SortedList> 非泛型类和 <xref:System.Collections.Generic.SortedList%602> 泛型类|<xref:System.Collections.Generic.SortedDictionary%602> 泛型类|  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|返回键和值的属性是有索引的，从而允许高效的索引检索。|无索引的检索。|  
|检索的运算复杂度为 O\(log `n`\)。|检索的运算复杂度为 O\(log `n`\)。|  
|插入和移除的运算复杂度一般为 O\(`n`\)；但是，对于已经处于排序顺序的数据，插入操作的运算复杂度为 O\(1\)，因此每个元素都被添加到列表的末尾。（这假设不需要调整大小。）|插入和移除的运算复杂度为 O\(log `n`\)。|  
|比 <xref:System.Collections.Generic.SortedDictionary%602> 使用更少的内存。|比 <xref:System.Collections.SortedList> 非泛型类和 <xref:System.Collections.Generic.SortedList%602> 泛型类使用更多内存。|  
  
 对于必须可从多个线程并发访问的已排序列表或字典，可以向从 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 派生的类添加排序逻辑。  
  
> [!NOTE]
>  对于包含自己的键的值（例如，包含雇员 ID 编号的雇员记录），可以通过从 <xref:System.Collections.ObjectModel.KeyedCollection%602> 泛型类派生创建带键的集合，该集合具有列表的一些特征和字典的一些特征。  
  
 从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，<xref:System.Collections.Generic.SortedSet%601> 类提供了一个在执行插入、删除和搜索操作之后维护对数据的排序的自平衡树。  此类和 <xref:System.Collections.Generic.HashSet%601> 类实现 <xref:System.Collections.Generic.ISet%601> 接口。  
  
## 请参阅  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [常用的集合类型](../../../docs/standard/collections/commonly-used-collection-types.md)