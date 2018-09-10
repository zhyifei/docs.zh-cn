---
title: 执行左外部联接（C# 中的 LINQ）
description: 了解如何使用 C# 中的 LINQ 执行左外部联接。
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 329fe9e17640931c5eb39b33b791a7a77a6f7b89
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506591"
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="63a39-103">执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="63a39-103">Perform left outer joins</span></span>

<span data-ttu-id="63a39-104">左外部联接是这样定义的：返回第一个集合的每个元素，无论该元素在第二个集合中是否有任何相关元素。</span><span class="sxs-lookup"><span data-stu-id="63a39-104">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="63a39-105">可以使用 LINQ 通过对分组联接的结果调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 方法来执行左外部联接。</span><span class="sxs-lookup"><span data-stu-id="63a39-105">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>

## <a name="example"></a><span data-ttu-id="63a39-106">示例</span><span class="sxs-lookup"><span data-stu-id="63a39-106">Example</span></span>

<span data-ttu-id="63a39-107">下面的示例演示如何对分组联接的结果调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 方法来执行左外部联接。</span><span class="sxs-lookup"><span data-stu-id="63a39-107">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>

<span data-ttu-id="63a39-108">若要生成两个集合的左外部联接，第一步是使用分组联接执行内联。</span><span class="sxs-lookup"><span data-stu-id="63a39-108">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="63a39-109">（有关此过程的说明，请参阅[执行内联](perform-inner-joins.md)。）在此示例中，`Person` 对象列表基于与 `Pet.Owner` 匹配的 `Person` 对象内联到 `Pet` 对象列表。</span><span class="sxs-lookup"><span data-stu-id="63a39-109">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>

<span data-ttu-id="63a39-110">第二步是在结果集内包含第一个（左）集合的每个元素，即使该元素在右集合中没有匹配的元素也是如此。</span><span class="sxs-lookup"><span data-stu-id="63a39-110">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="63a39-111">这是通过对分组联接中的每个匹配元素序列调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 来实现的。</span><span class="sxs-lookup"><span data-stu-id="63a39-111">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="63a39-112">此示例中，对每个匹配 `Pet` 对象的序列调用 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>。</span><span class="sxs-lookup"><span data-stu-id="63a39-112">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="63a39-113">如果对于任何 `Person` 对象，匹配 `Pet` 对象序列均为空，则该方法返回一个包含单个默认值的集合，从而确保结果集合中显示每个 `Person` 对象。</span><span class="sxs-lookup"><span data-stu-id="63a39-113">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>

> [!NOTE]
> <span data-ttu-id="63a39-114">引用类型的默认值为 `null`；因此，该示例在访问每个 `Pet` 集合的每个元素之前会先检查是否存在空引用。</span><span class="sxs-lookup"><span data-stu-id="63a39-114">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a><span data-ttu-id="63a39-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="63a39-115">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>  
- <xref:System.Linq.Enumerable.GroupJoin%2A>  
- [<span data-ttu-id="63a39-116">执行内部联接</span><span class="sxs-lookup"><span data-stu-id="63a39-116">Perform inner joins</span></span>](perform-inner-joins.md)  
- [<span data-ttu-id="63a39-117">执行分组联接</span><span class="sxs-lookup"><span data-stu-id="63a39-117">Perform grouped joins</span></span>](perform-grouped-joins.md)  
- [<span data-ttu-id="63a39-118">匿名类型</span><span class="sxs-lookup"><span data-stu-id="63a39-118">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  