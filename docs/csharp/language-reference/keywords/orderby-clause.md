---
title: "orderby 子句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="ce22d-102">orderby 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ce22d-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="ce22d-103">在查询表达式中，`orderby` 子句可导致返回的序列或子序列（组）以升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="ce22d-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="ce22d-104">若要执行一个或多个次级排序操作，可以指定多个键。</span><span class="sxs-lookup"><span data-stu-id="ce22d-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="ce22d-105">元素类型的默认比较器执行排序。</span><span class="sxs-lookup"><span data-stu-id="ce22d-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="ce22d-106">默认排序顺序为升序。</span><span class="sxs-lookup"><span data-stu-id="ce22d-106">The default sort order is ascending.</span></span> <span data-ttu-id="ce22d-107">还可以指定自定义比较器。</span><span class="sxs-lookup"><span data-stu-id="ce22d-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="ce22d-108">但是，只适用于使用基于方法的语法。</span><span class="sxs-lookup"><span data-stu-id="ce22d-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="ce22d-109">有关详细信息，请参阅[对数据进行排序](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48)。</span><span class="sxs-lookup"><span data-stu-id="ce22d-109">For more information, see [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce22d-110">示例</span><span class="sxs-lookup"><span data-stu-id="ce22d-110">Example</span></span>  
 <span data-ttu-id="ce22d-111">在以下示例中，第一个查询按字母顺序从 A 开始对字词排序，而第二个查询则按降序对相同的字词排序。</span><span class="sxs-lookup"><span data-stu-id="ce22d-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="ce22d-112">（`ascending` 关键字是默认排序值，可省略。）</span><span class="sxs-lookup"><span data-stu-id="ce22d-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 <span data-ttu-id="ce22d-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ce22d-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce22d-114">示例</span><span class="sxs-lookup"><span data-stu-id="ce22d-114">Example</span></span>  
 <span data-ttu-id="ce22d-115">以下示例对学生的姓氏进行主要排序，然后对其名字进行次要排序。</span><span class="sxs-lookup"><span data-stu-id="ce22d-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 <span data-ttu-id="ce22d-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ce22d-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce22d-117">备注</span><span class="sxs-lookup"><span data-stu-id="ce22d-117">Remarks</span></span>  
 <span data-ttu-id="ce22d-118">编译时，`orderby` 子句将转换为对 <xref:System.Linq.Enumerable.OrderBy%2A> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="ce22d-118">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="ce22d-119">`orderby` 子句中的多个关键值将转换为 <xref:System.Linq.Enumerable.ThenBy%2A> 方法调用。</span><span class="sxs-lookup"><span data-stu-id="ce22d-119">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce22d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce22d-120">See Also</span></span>  
 <span data-ttu-id="ce22d-121">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce22d-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ce22d-122">[查询关键字 (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="ce22d-122">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="ce22d-123">[LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce22d-123">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="ce22d-124">[group 子句](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ce22d-124">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 [<span data-ttu-id="ce22d-125">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="ce22d-125">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

