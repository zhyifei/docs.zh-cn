---
title: "集合和数据结构 | Microsoft Docs"
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
  - "将集合中的数据分组"
  - "对象 [.NET Framework], 在集合中分组"
  - "Array 类, 将集合中的数据分组"
  - "线程处理 [.NET Framework], 安全性"
  - "“集合”类"
  - "集合 [.NET Framework]"
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 35
---
# 集合和数据结构
类似的数据在作为集合而存储和操作时通常可以得到更高效地处理。 您可以使用<xref:System.Array?displayProperty=fullName>类或中的类<xref:System.Collections>， <xref:System.Collections.Generic>， <xref:System.Collections.Concurrent>，System.Collections.Immutable 命名空间，以添加、 删除和修改单个元素或某个范围的集合中的元素。  
  
 有两种主要的集合类型：泛型集合和非泛型集合。 泛型集合被添加在 .NET Framework 2.0 中，并提供编译时类型安全的集合。 因此，泛型集合通常能提供更好的性能。 构造泛型集合时，它们接受类型参数，并在向该集合添加项或从该集合删除项时无需在 <xref:System.Object> 类型间来回强制转换。  此外，[!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 应用程序支持大多数泛型集合。 非泛型集合将项存储为<xref:System.Object>，需要强制转换，并且大多数不支持[!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]应用程序开发。 但是，你可能会看到在较旧的代码中有非泛型集合。  
  
 从开始[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]中的集合<xref:System.Collections.Concurrent>命名空间提供高效的线程安全操作，以便从多个线程访问集合项。 System.Collections.Immutable 命名空间中的不可变集合类 ([NuGet 程序包](https://www.nuget.org/packages/System.Collections.Immutable)) 是本质上是线程安全，因为操作均在原始集合的副本上，不能修改原始集合。  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>常用集合功能  
 所有集合都提供用于在集合中添加、删除或查找项的方法。 此外，所有集合的直接或间接实现<xref:System.Collections.ICollection>接口或<xref:System.Collections.Generic.ICollection%601>接口共享这些功能︰  
  
-   **可枚举集合**  
  
     .NET framework 集合实现<xref:System.Collections.IEnumerable?displayProperty=fullName>或<xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>以启用要循环访问的集合。 可将枚举器看作集合中可指向任何元素的可移动指针。 [Foreach，请在](../Topic/foreach,%20in%20\(C%23%20Reference\).md)语句和[为每个...下一条语句](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md)使用枚举器公开的<xref:System.Collections.IEnumerable.GetEnumerator%2A>方法和隐藏操作枚举数的复杂性。 此外，用于实现的任何集合<xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>被视为*可查询类型*，并且可以使用 LINQ 查询。 LINQ 查询提供数据访问的一个通用模式。 它们通常比标准 `foreach` 循环更简洁、更具可读性，并提供筛选、排序和分组功能。 LINQ 查询还可提高性能。 有关详细信息，请参阅[LINQ to Objects](../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-objects.md)，[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)和[LINQ 查询 (C#) 简介](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)。  
  
-   **可将集合内容复制到数组**  
  
     可以将所有集合都复制到数组使用**CopyTo**方法; 但是，新数组中元素的顺序基于枚举器返回它们的顺序。 得到的数组始终是一维的，下限为零。  
  
 此外，许多集合类包含下列功能：  
  
-   **容量和计数属性**  
  
     集合的容量是它可包含的元素数。 集合的计数是它实际所含的元素数。 某些集合隐藏容量、计数或将这两者都隐藏。  
  
     达到当前容量时，大多数集合会自动扩展容量。 重新分配内存并将元素从旧集合复制到新集合。 这减少了要求使用集合的代码；但集合的性能可能会受到不利影响。 例如，对于<xref:System.Collections.Generic.List%601>，如果<xref:System.Collections.Generic.List%601.Count%2A>是小于<xref:System.Collections.Generic.List%601.Capacity%2A>，添加项就是 o （1） 操作。 如果需要增加以容纳新元素的容量，添加项成为 o （n） 操作，其中 n 是<xref:System.Collections.Generic.List%601.Count%2A>。 避免因多次重新分配而导致的性能较差的最佳方式是：将初始容量设置为集合的估计大小。  
  
     <xref:System.Collections.BitArray> 是一种特殊情况；其容量与长度相同，而长度与计数相同。  
  
-   **下限一致**  
  
     集合的下限是其第一个元素的索引。 <xref:System.Collections> 命名空间中所有索引集合的下限均为零，这表示它们从 0 开始建立索引。 <xref:System.Array>有下限为零，默认情况下，但创建的实例时，可以定义不同的下限**数组**类使用<xref:System.Array.CreateInstance%2A?displayProperty=fullName>。  
  
-   **用于从多个线程进行访问的同步**（仅 <xref:System.Collections> 类）。  
  
     中的非泛型集合类型<xref:System.Collections>命名空间通过同步提供一些线程安全性; 通常通过公开<xref:System.Collections.ICollection.SyncRoot%2A>和<xref:System.Collections.ICollection.IsSynchronized%2A>成员。 这些集合不是默认为线程安全的。 如需对集合进行可扩展、高效的多线程访问，请使用 <xref:System.Collections.Concurrent> 命名空间中的其中一个类或考虑使用不可变集合。 有关详细信息，请参阅[线程安全集合](../../../docs/standard/collections/thread-safe/index.md)。  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>选择集合  
 一般情况下，应使用泛型集合。 下表介绍了一些常用的集合方案和可用于这些方案的集合类。 如果你是使用泛型集合的新手，此表将帮助你选择最适合你的任务的泛型集合。  
  
|||||  
|-|-|-|-|  
|我要……|泛型集合选项|非泛型集合选项|线程安全或不可变集合选项|  
|将项存储为键/值对以通过键进行快速查找|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName></TKey, TValue>|<xref:System.Collections.Hashtable><br /><br /> （根据键的哈希代码组织的键/值对的集合。）|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> [ImmutableDictionary （TKey，TValue） 类](../Topic/ImmutableDictionary\(TKey,%20TValue\)%20Class.md)|  
|按索引访问项|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|[ImmutableList(T) 类](../Topic/ImmutableList\(T\)%20Class.md)<br /><br /> [ImmutableArray 类](../Topic/ImmutableArray%20Class.md)|  
|使用项先进先出 (FIFO)|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> [ImmutableQueue(T) 类](../Topic/ImmutableQueue\(T\)%20Class.md)|  
|使用数据后进先出 (LIFO)|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> [ImmutableStack(T) 类](../Topic/ImmutableStack\(T\)%20Class.md)|  
|按顺序访问项|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|无建议|无建议|  
|删除集合中的项或向集合添加项时接收通知。 (实现<xref:System.ComponentModel.INotifyPropertyChanged>和<xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>)|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|无建议|无建议|  
|已排序的集合|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>\</TKey, TValue>|<xref:System.Collections.SortedList?displayProperty=fullName>|[ImmutableSortedDictionary （TKey，TValue） 类](../Topic/ImmutableSortedDictionary\(TKey,%20TValue\)%20Class.md)<br /><br /> [ImmutableSortedSet(T) 类](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
|数学函数的一个集|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|无建议|[ImmutableHashSet(T) 类](../Topic/ImmutableHashSet\(T\)%20Class.md)<br /><br /> [ImmutableSortedSet(T) 类](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[选择集合类](../../../docs/standard/collections/selecting-a-collection-class.md)|描述不同的集合并帮助你为你的方案选择一个集合。|  
|[常用的集合类型](../../../docs/standard/collections/commonly-used-collection-types.md)|描述常用的泛型和非泛型集合类型，如<xref:System.Array?displayProperty=fullName>， <xref:System.Collections.Generic.List%601?displayProperty=fullName>，和<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>。\</TKey, TValue>|  
|[何时使用泛型集合](../../../docs/standard/collections/when-to-use-generic-collections.md)|讨论泛型集合类型的使用。|  
|[集合内的比较和排序](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|讨论在集合中使用等同性比较和排序比较。|  
|[已排序的集合类型](../../../docs/standard/collections/sorted-collection-types.md)|描述已排序集合的性能和特征|  
|[哈希表和字典集合类型](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|描述泛型和非泛型基于哈希的字典类型的功能。|  
|[线程安全集合](../../../docs/standard/collections/thread-safe/index.md)|描述集合类型，如<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>和<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>支持从多个线程的安全、 有效的并发访问。|  
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