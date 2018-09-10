---
title: 如何：使用 ForEach 移除 BlockingCollection 中的项
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44b71ed726af585259b015c608e49d8c81e4e22a
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261572"
---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="918bf-102">如何：使用 ForEach 移除 BlockingCollection 中的项</span><span class="sxs-lookup"><span data-stu-id="918bf-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>
<span data-ttu-id="918bf-103">除了使用 <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 方法从 <xref:System.Collections.Concurrent.BlockingCollection%601> 中提取项之外，还可以使用 [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md)（在 Visual Basic 中为 [For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md)）删除项，直至添加完成并且集合为空。</span><span class="sxs-lookup"><span data-stu-id="918bf-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="918bf-104">由于与典型的 `foreach` (`For Each`) 循环不同，此枚举器通过删除项来修改源集合，因此将其称作*转变枚举*或*耗用枚举*。</span><span class="sxs-lookup"><span data-stu-id="918bf-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>  
  
## <a name="example"></a><span data-ttu-id="918bf-105">示例</span><span class="sxs-lookup"><span data-stu-id="918bf-105">Example</span></span>  
 <span data-ttu-id="918bf-106">以下示例演示如何使用 `foreach` (`For Each`) 循环删除 <xref:System.Collections.Concurrent.BlockingCollection%601> 中的所有项。</span><span class="sxs-lookup"><span data-stu-id="918bf-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 <span data-ttu-id="918bf-107">此示例将 `foreach` 循环与耗用线程中的 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> 方法结合使用，这会导致在枚举每个项时将其从集合中删除。</span><span class="sxs-lookup"><span data-stu-id="918bf-107">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="918bf-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> 随时限制集合中所包含的最大项数。</span><span class="sxs-lookup"><span data-stu-id="918bf-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="918bf-109">按照此方式枚举集合会在没有项可用或集合为空时阻止使用者线程。</span><span class="sxs-lookup"><span data-stu-id="918bf-109">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="918bf-110">在此示例中，由于制造者线程添加项的速度快于消耗项的速度，因此不需要考虑阻止问题。</span><span class="sxs-lookup"><span data-stu-id="918bf-110">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>  
  
 <span data-ttu-id="918bf-111">不能保证按照制造者线程添加项的同一顺序来枚举这些项。</span><span class="sxs-lookup"><span data-stu-id="918bf-111">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>  
  
 <span data-ttu-id="918bf-112">若要枚举集合而不对其进行修改，只需使用 `foreach` (`For Each`) 即可，无需使用 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="918bf-112">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="918bf-113">但是，务必要了解此类枚举表示的是某个精确时间点的集合快照。</span><span class="sxs-lookup"><span data-stu-id="918bf-113">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="918bf-114">如果其他线程在你执行循环的同时添加或删除项，则循环可能不会表示集合的实际状态。</span><span class="sxs-lookup"><span data-stu-id="918bf-114">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918bf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="918bf-115">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
- [<span data-ttu-id="918bf-116">并行编程</span><span class="sxs-lookup"><span data-stu-id="918bf-116">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)
