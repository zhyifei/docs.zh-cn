---
title: "执行左外部联接"
description: "如何执行左外部联接。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 0c28c85bf933a411403aefcb91801d28fe1c268e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="fe9ad-104">执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="fe9ad-104">Perform left outer joins</span></span>
<span data-ttu-id="fe9ad-105">左外部联接是这样定义的：返回第一个集合的每个元素，无论该元素在第二个集合中是否有任何相关元素。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-105">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="fe9ad-106">可以使用 LINQ 通过对分组联接的结果调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 方法来执行左外部联接。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-106">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe9ad-107">示例</span><span class="sxs-lookup"><span data-stu-id="fe9ad-107">Example</span></span>  
 <span data-ttu-id="fe9ad-108">下面的示例演示如何对分组联接的结果调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 方法来执行左外部联接。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-108">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="fe9ad-109">若要生成两个集合的左外部联接，第一步是使用分组联接执行内联。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-109">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="fe9ad-110">（有关此过程的说明，请参阅[执行内联](perform-inner-joins.md)。）在此示例中，`Person` 对象列表基于与 `Pet.Owner` 匹配的 `Person` 对象内联到 `Pet` 对象列表。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-110">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="fe9ad-111">第二步是在结果集内包含第一个（左）集合的每个元素，即使该元素在右集合中没有匹配的元素也是如此。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-111">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="fe9ad-112">这是通过对分组联接中的每个匹配元素序列调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 来实现的。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-112">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="fe9ad-113">此示例中，对每个匹配 `Pet` 对象的序列调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-113">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="fe9ad-114">如果对于任何 `Person` 对象，匹配 `Pet` 对象序列均为空，则该方法返回一个包含单个默认值的集合，从而确保结果集合中显示每个 `Person` 对象。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-114">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe9ad-115">引用类型的默认值为 `null`；因此，该示例在访问每个 `Pet` 集合的每个元素之前会先检查是否存在空引用。</span><span class="sxs-lookup"><span data-stu-id="fe9ad-115">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="fe9ad-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe9ad-116">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="fe9ad-117">执行内部联接</span><span class="sxs-lookup"><span data-stu-id="fe9ad-117">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="fe9ad-118">执行分组联接</span><span class="sxs-lookup"><span data-stu-id="fe9ad-118">Perform grouped joins</span></span>](perform-grouped-joins.md)  
 [<span data-ttu-id="fe9ad-119">匿名类型</span><span class="sxs-lookup"><span data-stu-id="fe9ad-119">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
