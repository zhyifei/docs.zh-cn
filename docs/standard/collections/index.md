---
title: "集合和数据结构 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grouping data in collections
- objects [.NET Framework], grouping in collections
- Array class, grouping data in collections
- threading [.NET Framework], safety
- Collections classes
- collections [.NET Framework]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 27c475b8d29eb295bb3d6be24aa9ee9188f5c114
ms.lasthandoff: 04/08/2017

---
# <a name="collections-and-data-structures"></a>集合和数据结构
类似的数据在作为集合而存储和操作时通常可以得到更高效地处理。 可以使用 <xref:System.Array?displayProperty=fullName> 类或 <xref:System.Collections>、<xref:System.Collections.Generic>、<xref:System.Collections.Concurrent> 或 System.Collections.Immutable 命名空间中的类来添加、删除和修改集合中的单个元素或一系列元素。  
  
 有两种主要的集合类型：泛型集合和非泛型集合。 泛型集合被添加在 .NET Framework 2.0 中，并提供编译时类型安全的集合。 因此，泛型集合通常能提供更好的性能。 构造的泛型集合接受类型参数，在集合中添加或删除项时无需转换成 <xref:System.Object> 类型，也无需从此类型进行转换。  此外，[!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 应用程序支持大多数泛型集合。 非泛型集合将项存储为 <xref:System.Object>，需要进行转换，并且大多数不为 [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 应用程序开发所支持。 但是，你可能会看到在较旧的代码中有非泛型集合。  
  
 自 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 起，<xref:System.Collections.Concurrent> 命名空间中的集合可提供高效的线程安全操作，以便通过多线程访问集合项。 System.Collections.Immutable 命名空间（[NuGet 包](https://www.nuget.org/packages/System.Collections.Immutable)）中的不可变集合类本质上就是线程安全的，因为是在原始集合的副本上执行操作，且不能修改原始集合。  
  
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>常用集合功能  
 所有集合都提供用于在集合中添加、删除或查找项的方法。 此外，所有直接或间接实现 <xref:System.Collections.ICollection> 或 <xref:System.Collections.Generic.ICollection%601> 接口的集合共用这些功能：  
  
-   **可枚举集合**  
  
     .NET Framework 集合实现 <xref:System.Collections.IEnumerable?displayProperty=fullName> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>，以启用要循环访问的集合。 可将枚举器看作集合中可指向任何元素的可移动指针。 [foreach, in](~/docs/csharp/language-reference/keywords/foreach-in.md) 语句和 [For Each...Next 语句](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md)使用 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 方法公开的枚举器，隐藏了控制枚举器的复杂性。 此外，任何实现 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 的集合均被视作*可查询类型*，可使用 LINQ 进行查询。 LINQ 查询提供数据访问的一个通用模式。 它们通常比标准 `foreach` 循环更简洁、更具可读性，并提供筛选、排序和分组功能。 LINQ 查询还可提高性能。 有关详细信息，请参阅 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)、[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) 和 [LINQ 查询简介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。  
  
-   **可将集合内容复制到数组**  
  
     可使用 **CopyTo** 方法将所有集合复制到数组中；但新数组中的元素顺序是以枚举器返回元素的顺序为依据。 得到的数组始终是一维的，下限为零。  
  
 此外，许多集合类包含下列功能：  
  
-   **容量和计数属性**  
  
     集合的容量是它可包含的元素数。 集合的计数是它实际所含的元素数。 某些集合隐藏容量、计数或将这两者都隐藏。  
  
     达到当前容量时，大多数集合会自动扩展容量。 重新分配内存并将元素从旧集合复制到新集合。 这减少了要求使用集合的代码；但集合的性能可能会受到不利影响。 例如，对于 <xref:System.Collections.Generic.List%601>，如果 <xref:System.Collections.Generic.List%601.Count%2A> 小于 <xref:System.Collections.Generic.List%601.Capacity%2A>，那么添加项就属于 O(1) 操作。 如需增加容量来容纳新元素，添加项就属于 O(n) 操作，其中 n 是 <xref:System.Collections.Generic.List%601.Count%2A>。 避免因多次重新分配而导致的性能较差的最佳方式是：将初始容量设置为集合的估计大小。  
  
     <xref:System.Collections.BitArray> 是一种特殊情况；其容量与长度相同，而长度又与计数相同。  
  
-   **下限一致**  
  
     集合的下限是其第一个元素的索引。 <xref:System.Collections> 命名空间中所有已编入索引的集合的下限均为零。也就是说，这些集合是从 0 开始编制索引。 虽然 <xref:System.Array> 的默认下限为零，但在使用 <xref:System.Array.CreateInstance%2A?displayProperty=fullName> 创建 **Array** 类实例时可定义其他下限。  
  
-   **同步以便能够通过多线程进行访问**（仅限 <xref:System.Collections> 类）。  
  
     <xref:System.Collections> 命名空间中的非泛型集合类型通过同步提供线程安全性；通常通过 <xref:System.Collections.ICollection.SyncRoot%2A> 和 <xref:System.Collections.ICollection.IsSynchronized%2A> 成员进行公开。 这些集合不是默认为线程安全的。 如需对集合进行可扩展的高效多线程访问，请使用 <xref:System.Collections.Concurrent> 命名空间中的一个类或考虑使用不可变集合。 有关详细信息，请参阅[线程安全集合](../../../docs/standard/collections/thread-safe/index.md)。  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>选择集合  
 一般情况下，应使用泛型集合。 下表介绍了一些常用的集合方案和可用于这些方案的集合类。 如果你是使用泛型集合的新手，此表将帮助你选择最适合你的任务的泛型集合。  
<!-- todo: All code-formatted API refs in the table need to be changed into links -->  
|我要……|泛型集合选项|非泛型集合选项|线程安全或不可变集合选项|  
|-|-|-|-|  
|将项存储为键/值对以通过键进行快速查找|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>|<xref:System.Collections.Hashtable><br /><br /> （根据键的哈希代码组织的键/值对的集合。）|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName><br /><br /> `ImmutableDictionary(TKey, TValue) Class`|  
|按索引访问项|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|`ImmutableList(T) Class`<br /><br /> `ImmutableArray Class`|  
|使用项先进先出 (FIFO)|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> `ImmutableQueue(T) Class`|  
|使用数据后进先出 (LIFO)|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> `ImmutableStack(T) Class`|  
|按顺序访问项|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|无建议|无建议|  
|删除集合中的项或向集合添加项时接收通知。 （实现 <xref:System.ComponentModel.INotifyPropertyChanged> 和 <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>）|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|无建议|无建议|  
|已排序的集合|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>|<xref:System.Collections.SortedList?displayProperty=fullName>|`ImmutableSortedDictionary(TKey, TValue) Class`<br /><br /> `ImmutableSortedSet(T) Class`|  
|数学函数的一个集|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|无建议|`ImmutableHashSet(T) Class`<br /><br /> `ImmutableSortedSet(T) Class`|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[选择集合类](../../../docs/standard/collections/selecting-a-collection-class.md)|描述不同的集合并帮助你为你的方案选择一个集合。|  
|[常用的集合类型](../../../docs/standard/collections/commonly-used-collection-types.md)|介绍了常用的泛型和非泛型集合类型，如 <xref:System.Array?displayProperty=fullName>、<xref:System.Collections.Generic.List%601?displayProperty=fullName> 和 <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>。|  
|[何时使用泛型集合](../../../docs/standard/collections/when-to-use-generic-collections.md)|讨论泛型集合类型的使用。|  
|[集合内的比较和排序](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|讨论在集合中使用等同性比较和排序比较。|  
|[已排序的集合类型](../../../docs/standard/collections/sorted-collection-types.md)|描述已排序集合的性能和特征|  
|[哈希表和字典集合类型](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|描述泛型和非泛型基于哈希的字典类型的功能。|  
|[线程安全集合](../../../docs/standard/collections/thread-safe/index.md)|介绍了支持通过多线程进行安全高效的并发访问的集合类型，如 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 和 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>。|  
|System.Collections.Immutable|介绍不可变集合并提供各集合类型的链接。|  
  
<a name="BKMK_Reference"></a>   
## <a name="reference"></a>参考  
 <xref:System.Array?displayProperty=fullName>  
  
 <xref:System.Collections?displayProperty=fullName>  
  
 <xref:System.Collections.Concurrent?displayProperty=fullName>  
  
 <xref:System.Collections.Generic?displayProperty=fullName>  
  
 <xref:System.Collections.Specialized?displayProperty=fullName>  
  
 <xref:System.Linq?displayProperty=fullName>  
  
 System.Collections.Immutable
