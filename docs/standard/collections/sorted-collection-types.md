---
title: "已排序的集合类型"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7efe53d472e1789d49acc3973acdf190c8ff6662
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="sorted-collection-types"></a><span data-ttu-id="f6df4-102">已排序的集合类型</span><span class="sxs-lookup"><span data-stu-id="f6df4-102">Sorted Collection Types</span></span>
<span data-ttu-id="f6df4-103"><xref:System.Collections.SortedList?displayProperty=nameWithType> 类、<xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> 泛型类和 <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> 泛型类与 <xref:System.Collections.Hashtable> 类和 <xref:System.Collections.Generic.Dictionary%602> 泛型类的相似之处在于均实现 <xref:System.Collections.IDictionary> 接口，不同之处在于它们让元素一直按键的排序顺序排列，并且不具备哈希表的 O(1) 插入和检索特性。</span><span class="sxs-lookup"><span data-stu-id="f6df4-103">The <xref:System.Collections.SortedList?displayProperty=nameWithType> class, the <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> generic class, and the <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> generic class are similar to the <xref:System.Collections.Hashtable> class and the <xref:System.Collections.Generic.Dictionary%602> generic class in that they implement the <xref:System.Collections.IDictionary> interface, but they maintain their elements in sort order by key, and they do not have the O(1) insertion and retrieval characteristic of hash tables.</span></span> <span data-ttu-id="f6df4-104">这三个类具有若干共性：</span><span class="sxs-lookup"><span data-stu-id="f6df4-104">The three classes have several features in common:</span></span>  
  
-   <span data-ttu-id="f6df4-105">这三个类全都实现 <xref:System.Collections.IDictionary?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="f6df4-105">All three classes implement the <xref:System.Collections.IDictionary?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="f6df4-106">两个泛型类还实现 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType> 泛型接口。</span><span class="sxs-lookup"><span data-stu-id="f6df4-106">The two generic classes also implement the <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType> generic interface.</span></span>  
  
-   <span data-ttu-id="f6df4-107">每个元素都是用于枚举的键/值对。</span><span class="sxs-lookup"><span data-stu-id="f6df4-107">Each element is a key/value pair for enumeration purposes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6df4-108">枚举时，非泛型 <xref:System.Collections.SortedList> 类返回 <xref:System.Collections.DictionaryEntry> 对象，尽管两个泛型类型返回 <xref:System.Collections.Generic.KeyValuePair%602> 对象。</span><span class="sxs-lookup"><span data-stu-id="f6df4-108">The nongeneric <xref:System.Collections.SortedList> class returns <xref:System.Collections.DictionaryEntry> objects when enumerated, although the two generic types return <xref:System.Collections.Generic.KeyValuePair%602> objects.</span></span>  
  
-   <span data-ttu-id="f6df4-109">元素按 <xref:System.Collections.IComparer?displayProperty=nameWithType> 实现代码（对于非泛型 <xref:System.Collections.SortedList>）或 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 实现代码（对于两个泛型类）进行排序。</span><span class="sxs-lookup"><span data-stu-id="f6df4-109">Elements are sorted according to a <xref:System.Collections.IComparer?displayProperty=nameWithType> implementation (for nongeneric <xref:System.Collections.SortedList>) or a <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation (for the two generic classes).</span></span>  
  
-   <span data-ttu-id="f6df4-110">每个类提供了返回仅包含键或仅包含值的集合的属性。</span><span class="sxs-lookup"><span data-stu-id="f6df4-110">Each class provides properties that return collections containing only the keys or only the values.</span></span>  
  
 <span data-ttu-id="f6df4-111">下表列出了两个已排序列表类与 <xref:System.Collections.Generic.SortedDictionary%602> 类之间的一些区别。</span><span class="sxs-lookup"><span data-stu-id="f6df4-111">The following table lists some of the differences between the two sorted list classes and the <xref:System.Collections.Generic.SortedDictionary%602> class.</span></span>  
  
|<span data-ttu-id="f6df4-112"><xref:System.Collections.SortedList> 非泛型类和 <xref:System.Collections.Generic.SortedList%602> 泛型类</span><span class="sxs-lookup"><span data-stu-id="f6df4-112"><xref:System.Collections.SortedList> nongeneric class and <xref:System.Collections.Generic.SortedList%602> generic class</span></span>|<span data-ttu-id="f6df4-113"><xref:System.Collections.Generic.SortedDictionary%602> 泛型类</span><span class="sxs-lookup"><span data-stu-id="f6df4-113"><xref:System.Collections.Generic.SortedDictionary%602> generic class</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="f6df4-114">返回键和值的属性是有索引的，从而允许高效的索引检索。</span><span class="sxs-lookup"><span data-stu-id="f6df4-114">The properties that return keys and values are indexed, allowing efficient indexed retrieval.</span></span>|<span data-ttu-id="f6df4-115">无索引的检索。</span><span class="sxs-lookup"><span data-stu-id="f6df4-115">No indexed retrieval.</span></span>|  
|<span data-ttu-id="f6df4-116">检索属于 O(log `n`) 操作。</span><span class="sxs-lookup"><span data-stu-id="f6df4-116">Retrieval is O(log `n`).</span></span>|<span data-ttu-id="f6df4-117">检索属于 O(log `n`) 操作。</span><span class="sxs-lookup"><span data-stu-id="f6df4-117">Retrieval is O(log `n`).</span></span>|  
|<span data-ttu-id="f6df4-118">插入和删除通常属于 O(`n`) 操作；不过，对于已按排序顺序排列的数据，插入属于 O(log `n`) 操作，这样每个元素都可以添加到列表的末尾。</span><span class="sxs-lookup"><span data-stu-id="f6df4-118">Insertion and removal are generally O(`n`); however, insertion is O(log `n`) for data that are already in sort order, so that each element is added to the end of the list.</span></span> <span data-ttu-id="f6df4-119">（这假设不需要调整大小。）</span><span class="sxs-lookup"><span data-stu-id="f6df4-119">(This assumes that a resize is not required.)</span></span>|<span data-ttu-id="f6df4-120">插入和删除属于 O(log `n`) 操作。</span><span class="sxs-lookup"><span data-stu-id="f6df4-120">Insertion and removal are O(log `n`).</span></span>|  
|<span data-ttu-id="f6df4-121">比 <xref:System.Collections.Generic.SortedDictionary%602> 使用更少的内存。</span><span class="sxs-lookup"><span data-stu-id="f6df4-121">Uses less memory than a <xref:System.Collections.Generic.SortedDictionary%602>.</span></span>|<span data-ttu-id="f6df4-122">比 <xref:System.Collections.SortedList> 非泛型类和 <xref:System.Collections.Generic.SortedList%602> 泛型类使用更多内存。</span><span class="sxs-lookup"><span data-stu-id="f6df4-122">Uses more memory than the <xref:System.Collections.SortedList> nongeneric class and the <xref:System.Collections.Generic.SortedList%602> generic class.</span></span>|  
  
 <span data-ttu-id="f6df4-123">对于必须可通过多个线程并发访问的已排序列表或字典，可以向派生自 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 的类添加排序逻辑。</span><span class="sxs-lookup"><span data-stu-id="f6df4-123">For sorted lists or dictionaries that must be accessible concurrently from multiple threads, you can add sorting logic to a class that derives from <xref:System.Collections.Concurrent.ConcurrentDictionary%602>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6df4-124">对于包含自己的键的值（例如，包含雇员 ID 编号的雇员记录），可以通过派生自 <xref:System.Collections.ObjectModel.KeyedCollection%602> 泛型类，创建具有列表和字典的某些特性的键控集合。</span><span class="sxs-lookup"><span data-stu-id="f6df4-124">For values that contain their own keys (for example, employee records that contain an employee ID number), you can create a keyed collection that has some characteristics of a list and some characteristics of a dictionary by deriving from the <xref:System.Collections.ObjectModel.KeyedCollection%602> generic class.</span></span>  
  
 <span data-ttu-id="f6df4-125">自 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 起，<xref:System.Collections.Generic.SortedSet%601> 类提供在执行插入、删除和搜索操作之后让数据一直按排序顺序排列的自平衡树。</span><span class="sxs-lookup"><span data-stu-id="f6df4-125">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the <xref:System.Collections.Generic.SortedSet%601> class provides a self-balancing tree that maintains data in sorted order after insertions, deletions, and searches.</span></span> <span data-ttu-id="f6df4-126">此类和 <xref:System.Collections.Generic.HashSet%601> 类实现 <xref:System.Collections.Generic.ISet%601> 接口。</span><span class="sxs-lookup"><span data-stu-id="f6df4-126">This class and the <xref:System.Collections.Generic.HashSet%601> class implement the <xref:System.Collections.Generic.ISet%601> interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6df4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6df4-127">See Also</span></span>  
 <xref:System.Collections.IDictionary?displayProperty=nameWithType>  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>  
 [<span data-ttu-id="f6df4-128">常用的集合类型</span><span class="sxs-lookup"><span data-stu-id="f6df4-128">Commonly Used Collection Types</span></span>](../../../docs/standard/collections/commonly-used-collection-types.md)
