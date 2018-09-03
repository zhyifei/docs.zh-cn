---
title: orderby 子句（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: de649a7e1608e6a653f3280bfd5c4e52a3b661be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43391192"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="9b2a5-102">orderby 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9b2a5-102">orderby clause (C# Reference)</span></span>

<span data-ttu-id="9b2a5-103">在查询表达式中，`orderby` 子句可导致返回的序列或子序列（组）以升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="9b2a5-104">若要执行一个或多个次级排序操作，可以指定多个键。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="9b2a5-105">元素类型的默认比较器执行排序。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="9b2a5-106">默认排序顺序为升序。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-106">The default sort order is ascending.</span></span> <span data-ttu-id="9b2a5-107">还可以指定自定义比较器。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="9b2a5-108">但是，只适用于使用基于方法的语法。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="9b2a5-109">有关详细信息，请参阅[对数据进行排序](../../programming-guide/concepts/linq/sorting-data.md)。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="9b2a5-110">示例</span><span class="sxs-lookup"><span data-stu-id="9b2a5-110">Example</span></span>

<span data-ttu-id="9b2a5-111">在以下示例中，第一个查询按字母顺序从 A 开始对字词排序，而第二个查询则按降序对相同的字词排序。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="9b2a5-112">（`ascending` 关键字是默认排序值，可省略。）</span><span class="sxs-lookup"><span data-stu-id="9b2a5-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="9b2a5-113">示例</span><span class="sxs-lookup"><span data-stu-id="9b2a5-113">Example</span></span>

<span data-ttu-id="9b2a5-114">以下示例对学生的姓氏进行主要排序，然后对其名字进行次要排序。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="9b2a5-115">备注</span><span class="sxs-lookup"><span data-stu-id="9b2a5-115">Remarks</span></span>

<span data-ttu-id="9b2a5-116">编译时，`orderby` 子句将转换为对 <xref:System.Linq.Enumerable.OrderBy%2A> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="9b2a5-117">`orderby` 子句中的多个关键值将转换为 <xref:System.Linq.Enumerable.ThenBy%2A> 方法调用。</span><span class="sxs-lookup"><span data-stu-id="9b2a5-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b2a5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b2a5-118">See also</span></span>

- [<span data-ttu-id="9b2a5-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9b2a5-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9b2a5-120">查询关键字 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9b2a5-120">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="9b2a5-121">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9b2a5-121">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="9b2a5-122">group 子句</span><span class="sxs-lookup"><span data-stu-id="9b2a5-122">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="9b2a5-123">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="9b2a5-123">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)