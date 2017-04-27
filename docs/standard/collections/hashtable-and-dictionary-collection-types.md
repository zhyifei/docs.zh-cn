---
title: "哈希表和字典集合类型 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 59aa4bd6160491ac6c6a4f45131531226ec7e58f
ms.lasthandoff: 04/18/2017

---
# <a name="hashtable-and-dictionary-collection-types"></a>哈希表和字典集合类型
<xref:System.Collections.Hashtable?displayProperty=fullName> 类、<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 和 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> 泛型类实现 <xref:System.Collections.IDictionary?displayProperty=fullName> 接口。 <xref:System.Collections.Generic.Dictionary%602> 泛型类还实现 <xref:System.Collections.Generic.IDictionary%602> 泛型接口。 因此，这些集合中的每个元素都是一个键值对。  
  
 <xref:System.Collections.Hashtable> 对象由包含集合元素的存储桶组成。 存储桶是 <xref:System.Collections.Hashtable> 中元素的虚拟子组，这样可以更快捷地执行搜索和检索（与大多数集合相比）。 每个存储桶都与一个哈希代码相关联，该哈希代码通过哈希函数生成并基于元素的键。  
  
 泛型 <xref:System.Collections.Generic.HashSet%601> 类是用于包含唯一元素的无序集合。  
  
 哈希函数是一种算法，返回基于键的数值哈希代码。 该键是所存储对象的某个属性的值。 哈希函数必须始终返回同一个键的同一哈希代码。 哈希函数有可能为两个不同的键生成相同的哈希代码，但从哈希表中检索元素时，为每个唯一的键生成唯一哈希代码的哈希函数具有更好的性能。  
  
 用作 <xref:System.Collections.Hashtable> 中元素的每个对象必须能够使用 <xref:System.Object.GetHashCode%2A> 方法的实现代码为自身生成哈希代码。 不过，还可以使用接受 <xref:System.Collections.IHashCodeProvider> 实现代码作为参数之一的 <xref:System.Collections.Hashtable> 构造函数，为 <xref:System.Collections.Hashtable> 中的所有元素指定哈希函数。  
  
 添加到 <xref:System.Collections.Hashtable> 中的对象存储在与哈希代码相关联的存储桶中，此哈希代码与对象哈希代码一致。 在 <xref:System.Collections.Hashtable> 中搜索值时，先生成此值的哈希代码，然后搜索与该哈希代码相关联的存储桶。  
  
 例如，用于字符串的哈希函数可能采用字符串中每个字符的 ASCII 代码，并将它们加总以生成哈希代码。 字符串“picnic”的哈希代码可能与字符串“basket”的哈希代码不同；因此，字符串“picnic”和“basket”可能在不同的存储桶中。 与此相反，“stressed”和“desserts”可能具有相同的哈希代码，并且位于同一个存储桶中。  
  
 <xref:System.Collections.Generic.Dictionary%602> 和 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 类具有与 <xref:System.Collections.Hashtable> 类相同的功能。 特定类型（而不是 <xref:System.Object>）的 <xref:System.Collections.Generic.Dictionary%602> 的性能优于值类型的 <xref:System.Collections.Hashtable>。 这是因为 <xref:System.Collections.Hashtable> 的元素属于 <xref:System.Object> 类型；因此，装箱和取消装箱通常发生在存储或检索值类型时。 应在多个线程可能同时访问集合时使用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 类。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.Hashtable>   
 <xref:System.Collections.IDictionary>   
 <xref:System.Collections.IHashCodeProvider>   
 <xref:System.Collections.Generic.Dictionary%602>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>   
 [常用的集合类型](../../../docs/standard/collections/commonly-used-collection-types.md)
