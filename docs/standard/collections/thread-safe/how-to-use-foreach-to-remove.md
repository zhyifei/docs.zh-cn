---
title: "如何：使用 ForEach 移除 BlockingCollection 中的项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b0f0ed30ae5192ed8a8f069d591855857bd2fa49
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="3bb85-102">如何：使用 ForEach 移除 BlockingCollection 中的项</span><span class="sxs-lookup"><span data-stu-id="3bb85-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>
<span data-ttu-id="3bb85-103">除了使用 <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 方法从 <xref:System.Collections.Concurrent.BlockingCollection%601> 中提取项之外，还可以使用 [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md)（在 Visual Basic 中为 [For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md)）删除项，直至添加完成并且集合为空。</span><span class="sxs-lookup"><span data-stu-id="3bb85-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="3bb85-104">由于与典型的 `foreach` (`For Each`) 循环不同，此枚举器通过删除项来修改源集合，因此将其称作*转变枚举*或*耗用枚举*。</span><span class="sxs-lookup"><span data-stu-id="3bb85-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bb85-105">示例</span><span class="sxs-lookup"><span data-stu-id="3bb85-105">Example</span></span>  
 <span data-ttu-id="3bb85-106">以下示例演示如何使用 `foreach` (`For Each`) 循环删除 <xref:System.Collections.Concurrent.BlockingCollection%601> 中的所有项。</span><span class="sxs-lookup"><span data-stu-id="3bb85-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>  
  
 <span data-ttu-id="3bb85-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span><span class="sxs-lookup"><span data-stu-id="3bb85-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span></span>  
  
 <span data-ttu-id="3bb85-108">此示例将 `foreach` 循环与耗用线程中的 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> 方法结合使用，这会导致在枚举每个项时将其从集合中删除。</span><span class="sxs-lookup"><span data-stu-id="3bb85-108">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="3bb85-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 随时限制集合中所包含的最大项数。</span><span class="sxs-lookup"><span data-stu-id="3bb85-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="3bb85-110">按照此方式枚举集合会在没有项可用或集合为空时阻止使用者线程。</span><span class="sxs-lookup"><span data-stu-id="3bb85-110">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="3bb85-111">在此示例中，由于制造者线程添加项的速度快于消耗项的速度，因此不需要考虑阻止问题。</span><span class="sxs-lookup"><span data-stu-id="3bb85-111">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>  
  
 <span data-ttu-id="3bb85-112">不能保证按照制造者线程添加项的同一顺序来枚举这些项。</span><span class="sxs-lookup"><span data-stu-id="3bb85-112">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>  
  
 <span data-ttu-id="3bb85-113">若要枚举集合而不对其进行修改，只需使用 `foreach` (`For Each`) 即可，无需使用 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3bb85-113">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="3bb85-114">但是，务必要了解此类枚举表示的是某个精确时间点的集合快照。</span><span class="sxs-lookup"><span data-stu-id="3bb85-114">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="3bb85-115">如果其他线程在你执行循环的同时添加或删除项，则循环可能不会表示集合的实际状态。</span><span class="sxs-lookup"><span data-stu-id="3bb85-115">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb85-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb85-116">See Also</span></span>  
 <span data-ttu-id="3bb85-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3bb85-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="3bb85-118">并行编程</span><span class="sxs-lookup"><span data-stu-id="3bb85-118">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)

