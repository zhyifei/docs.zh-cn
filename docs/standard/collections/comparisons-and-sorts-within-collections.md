---
title: "集合内的比较和排序 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0da0bed43cb7871f522b94b134afb164d8ee3ab5
ms.lasthandoff: 04/18/2017

---
# <a name="comparisons-and-sorts-within-collections"></a>集合内的比较和排序
<xref:System.Collections> 类在集合管理涉及的几乎所有进程中都会执行比较操作，无论是搜索要删除的元素，还是返回键值对的值。  
  
 集合通常使用相等比较器和/或排序比较器。 有两个构造用于比较。  
  
<a name="BKMK_Checkingforequality"></a>   
## <a name="checking-for-equality"></a>检查等同性  
 `Contains`、<xref:System.Collections.IList.IndexOf%2A>、<xref:System.Collections.Generic.List%601.LastIndexOf%2A> 和 `Remove` 等方法对集合元素使用相等比较器。 如果集合是泛型的，则按照以下原则比较项是否相等：  
  
-   如果类型 T 实现 <xref:System.IEquatable%601> 泛型接口，那么相等比较器就是此接口的 <xref:System.IEquatable%601.Equals%2A> 方法。  
  
-   如果类型 T 未实现 <xref:System.IEquatable%601>，那么使用的就是 <xref:System.Object.Equals%2A?displayProperty=fullName>。  
  
 此外，字典集合的一些构造函数重载接受 <xref:System.Collections.Generic.IEqualityComparer%601> 实现代码，用于比较键是否相等。 有关示例，请参阅 <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A?displayProperty=fullName> 构造函数。  
  
<a name="BKMK_Determiningsortorder"></a>   
## <a name="determining-sort-order"></a>确定排序顺序  
 `BinarySearch` 和 `Sort` 等方法将排序比较器用于集合元素。 可在集合的元素间进行比较，或在元素或指定值之间进行比较。 对于比较对象，有`default comparer`和`explicit comparer`的概念。  
  
 为了实现 **IComparable** 接口，默认比较器依赖至少一个比较对象。 最好对用作列表集合的值或字典集合的键的所有类实现 **IComparable**。 对泛型集合而言，等同性比较是根据以下内容确定的：  
  
-   如果类型 T 实现 <xref:System.IComparable%601?displayProperty=fullName> 泛型接口，那么默认比较器就是此接口的 <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=fullName> 方法  
  
-   如果类型 T 实现非泛型 <xref:System.IComparable?displayProperty=fullName> 接口，那么默认比较器就是此接口的 <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=fullName> 方法。  
  
-   如果类型 T 未实现任何接口，则没有默认比较器，必须显式提供一个比较器或比较委托。  
  
 为了提供显式比较，一些方法接受将 **IComparer** 实现代码用作参数。 例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> 方法接受 <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> 实现代码。  
  
 系统当前的区域性设置可影响集合中的比较和排序。 默认情况下，**Collections** 类中的比较和排序区分区域性。 若要忽略区域性设置，从而生成一致的比较和排序结果，请使用成员重载接受 <xref:System.Globalization.CultureInfo> 的 <xref:System.Globalization.CultureInfo.InvariantCulture%2A>。 有关详细信息，请参阅[在集合中执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)和[在数组中执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)。  
  
<a name="BKMK_Equalityandsortexample"></a>   
## <a name="equality-and-sort-example"></a>等同性和排序示例  
 下面的代码展示了如何对简单业务对象实现 <xref:System.IEquatable%601> 和 <xref:System.IComparable%601>。 此外，如果对象存储在列表中并已排序，则会发现调用 <xref:System.Collections.Generic.List%601.Sort> 方法会导致对 `Part` 类型使用默认比较器，并使用通过匿名方法实现的 <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> 方法。  
  
 [!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
 [!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.IComparer>   
 <xref:System.IEquatable%601>   
 <xref:System.Collections.Generic.IComparer%601>   
 <xref:System.IComparable>   
 <xref:System.IComparable%601>
