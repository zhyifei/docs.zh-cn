---
title: "如何：在 ConcurrentDictionary 中添加和删除项 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9d20d75b2492c214305c07a5e19941cd91b66f67
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>如何：在 ConcurrentDictionary 中添加和移除项
本示例展示了如何在 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> 中添加、检索、更新和删除项。 此集合类是一个线程安全实现。 建议在多个线程可能同时尝试访问元素时使用此集合类。  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 提供了多种便捷方法，这样代码就无需在尝试添加或删除数据之前先检查键是否存在。 下表列出了这些便捷的方法，并说明在何种情况下这些方法。  
  
|方法|何时使用…|  
|------------|---------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|需要为指定键添加新值，如果此键已存在，则需要替换其值。|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|需要检索指定键的现有值，如果此键不存在，则需要指定一个键/值对。|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>、<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A>、<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A>、<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|需要添加、获取、更新或移除键/值对，如果此键已存在或因任何其他原因导致尝试失败，则需执行某种备选操作。|  
  
## <a name="example"></a>示例  
 下面的示例使用两个 <xref:System.Threading.Tasks.Task> 实例将一些元素同时添加到 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 中，然后输出所有内容，以指明元素已成功添加。 此示例还展示了如何使用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>、<xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> 和 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 方法在集合中添加、更新和检索项。  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 专为多线程方案而设计。 无需在代码中使用锁定即可在集合中添加或移除项。 但始终可能出现以下情况：一个线程检索一个值，而另一线程通过为同一键赋予新值来立即更新集合。  
  
 此外，尽管所有 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 方法都是线程安全方法，但并不是所有都是原子方法，尤其是 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 和 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>。 传递给这些方法的用户委托将在词典的内部锁之外调用。 （这样做是为了防止未知代码阻塞所有线程。）因此，可能发生以下事件序列：  
  
 1\) threadA 调用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>，但找不到任何项，然后通过调用 valueFactory 委托新建要添加的项。  
  
 2\) threadB 同时调用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>，它的 valueFactory 委托受到调用，并先于 threadA 到达内部锁位置，所以它的新键值对被添加到字典中。  
  
 3\) threadA 的用户委托完成，此线程到达锁位置，但现在发现已有项存在  
  
 4\) threadA 执行“Get”，返回之前由 threadB 添加的数据。  
  
 因此，无法保证 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 返回的数据就是线程的 valueFactory 创建的数据。 调用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> 时，也可能会发生类似的一系列事件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)
