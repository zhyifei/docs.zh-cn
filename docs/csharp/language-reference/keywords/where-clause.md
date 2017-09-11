---
title: "where 子句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
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
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a><span data-ttu-id="a9706-102">where 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a9706-102">where clause (C# Reference)</span></span>
<span data-ttu-id="a9706-103">`where` 子句用在查询表达式中，用于指定将在查询表达式中返回数据源中的哪些元素。</span><span class="sxs-lookup"><span data-stu-id="a9706-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="a9706-104">它将一个布尔条件（谓词）应用于每个源元素（由范围变量引用），并返回满足指定条件的元素。</span><span class="sxs-lookup"><span data-stu-id="a9706-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="a9706-105">一个查询表达式可以包含多个 `where` 子句，一个子句可以包含多个谓词子表达式。</span><span class="sxs-lookup"><span data-stu-id="a9706-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9706-106">示例</span><span class="sxs-lookup"><span data-stu-id="a9706-106">Example</span></span>  
 <span data-ttu-id="a9706-107">在下面的示例中，`where` 子句筛选出除小于五的数字外的所有数字。</span><span class="sxs-lookup"><span data-stu-id="a9706-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="a9706-108">如果删除 `where` 子句，则会返回数据源中的所有数字。</span><span class="sxs-lookup"><span data-stu-id="a9706-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="a9706-109">表达式 `num < 5` 是应用于每个元素的谓词。</span><span class="sxs-lookup"><span data-stu-id="a9706-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 <span data-ttu-id="a9706-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9706-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9706-111">示例</span><span class="sxs-lookup"><span data-stu-id="a9706-111">Example</span></span>  
 <span data-ttu-id="a9706-112">在单个 `where` 子句中，可以使用 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 和 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) 运算符根据需要指定任意多个谓词。</span><span class="sxs-lookup"><span data-stu-id="a9706-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="a9706-113">在下面的示例中，查询将指定两个谓词，以便只选择小于五的偶数。</span><span class="sxs-lookup"><span data-stu-id="a9706-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 <span data-ttu-id="a9706-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9706-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9706-115">示例</span><span class="sxs-lookup"><span data-stu-id="a9706-115">Example</span></span>  
 <span data-ttu-id="a9706-116">一个 `where` 子句可以包含一个或多个返回布尔值的方法。</span><span class="sxs-lookup"><span data-stu-id="a9706-116">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="a9706-117">在下面的示例中，`where` 子句使用一种方法来确定范围变量的当前值是偶数还是奇数。</span><span class="sxs-lookup"><span data-stu-id="a9706-117">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 <span data-ttu-id="a9706-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9706-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9706-119">备注</span><span class="sxs-lookup"><span data-stu-id="a9706-119">Remarks</span></span>  
 <span data-ttu-id="a9706-120">`where` 子句是一种筛选机制。</span><span class="sxs-lookup"><span data-stu-id="a9706-120">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="a9706-121">除了不能是第一个或最后一个子句外，它几乎可以放在查询表达式中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="a9706-121">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="a9706-122">`where` 子句可以出现在 [group](../../../csharp/language-reference/keywords/group-clause.md) 子句的前面或后面，具体取决于时必须在对源元素进行分组之前还是之后来筛选源元素。</span><span class="sxs-lookup"><span data-stu-id="a9706-122">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="a9706-123">如果指定的谓词对于数据源中的元素无效，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="a9706-123">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="a9706-124">这是 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 提供的强类型检查的一个优点。</span><span class="sxs-lookup"><span data-stu-id="a9706-124">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="a9706-125">在编译时，`where` 关键字将转换为对 <xref:System.Linq.Enumerable.Where%2A> 标准查询运算符方法的调用。</span><span class="sxs-lookup"><span data-stu-id="a9706-125">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9706-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9706-126">See Also</span></span>  
 <span data-ttu-id="a9706-127">[查询关键字 (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="a9706-127">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="a9706-128">[from 子句](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a9706-128">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="a9706-129">[select 子句](../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a9706-129">[select clause](../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="a9706-130">[筛选数据](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span><span class="sxs-lookup"><span data-stu-id="a9706-130">[Filtering Data](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span></span>  
 <span data-ttu-id="a9706-131">[LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9706-131">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="a9706-132">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="a9706-132">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

