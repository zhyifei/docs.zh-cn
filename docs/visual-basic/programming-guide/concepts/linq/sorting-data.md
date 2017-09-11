---
title: "对数据 (Visual Basic 中) 进行排序 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1870d401ffdeeb2452ace1b74a8fb70e19c9b9ed
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="8ab6c-102">对数据进行排序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ab6c-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="8ab6c-103">排序操作基于一个或多个属性对序列的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="8ab6c-104">第一个排序条件对元素执行主要排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="8ab6c-105">通过指定第二个排序条件，您可以对每个主要排序组内的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="8ab6c-106">下图显示对一个序列的字符的字母顺序排序操作的结果。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="8ab6c-107">![LINQ 排序操作](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="8ab6c-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="8ab6c-108">对数据进行排序的标准查询运算符方法下一节中列出。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ab6c-109">方法</span><span class="sxs-lookup"><span data-stu-id="8ab6c-109">Methods</span></span>  
  
|<span data-ttu-id="8ab6c-110">方法名</span><span class="sxs-lookup"><span data-stu-id="8ab6c-110">Method Name</span></span>|<span data-ttu-id="8ab6c-111">描述</span><span class="sxs-lookup"><span data-stu-id="8ab6c-111">Description</span></span>|<span data-ttu-id="8ab6c-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="8ab6c-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="8ab6c-113">更多信息</span><span class="sxs-lookup"><span data-stu-id="8ab6c-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="8ab6c-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="8ab6c-114">OrderBy</span></span>|<span data-ttu-id="8ab6c-115">按升序排序的值进行排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-115">Sorts values in ascending order.</span></span>|`Order By`|<span data-ttu-id="8ab6c-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8ab6c-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8ab6c-118">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="8ab6c-118">OrderByDescending</span></span>|<span data-ttu-id="8ab6c-119">按降序顺序的值进行排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-119">Sorts values in descending order.</span></span>|`Order By … Descending`|<span data-ttu-id="8ab6c-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8ab6c-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8ab6c-122">ThenBy</span><span class="sxs-lookup"><span data-stu-id="8ab6c-122">ThenBy</span></span>|<span data-ttu-id="8ab6c-123">按升序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-123">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<span data-ttu-id="8ab6c-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8ab6c-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8ab6c-126">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="8ab6c-126">ThenByDescending</span></span>|<span data-ttu-id="8ab6c-127">按降序顺序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-127">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<span data-ttu-id="8ab6c-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8ab6c-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="8ab6c-130">Reverse</span><span class="sxs-lookup"><span data-stu-id="8ab6c-130">Reverse</span></span>|<span data-ttu-id="8ab6c-131">集合中的元素的顺序反转。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-131">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="8ab6c-132">不适用。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-132">Not applicable.</span></span>|<span data-ttu-id="8ab6c-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="8ab6c-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8ab6c-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="8ab6c-135">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="8ab6c-135">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="8ab6c-136">主要排序示例</span><span class="sxs-lookup"><span data-stu-id="8ab6c-136">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="8ab6c-137">主要的升序排序</span><span class="sxs-lookup"><span data-stu-id="8ab6c-137">Primary Ascending Sort</span></span>  
 <span data-ttu-id="8ab6c-138">下面的示例演示如何使用`Order By`按字符串长度，以升序排序字符串数组中的 LINQ 查询中的子句。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-138">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="8ab6c-139">主要降序排序</span><span class="sxs-lookup"><span data-stu-id="8ab6c-139">Primary Descending Sort</span></span>  
 <span data-ttu-id="8ab6c-140">下一个示例演示如何使用`Order By Descending`LINQ 查询以按其第一个字母，按降序排序字符串中的子句。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-140">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="8ab6c-141">次要排序示例</span><span class="sxs-lookup"><span data-stu-id="8ab6c-141">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="8ab6c-142">辅助按升序排序</span><span class="sxs-lookup"><span data-stu-id="8ab6c-142">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="8ab6c-143">下面的示例演示如何使用`Order By`在 LINQ 查询来执行数组中的字符串中的主要和次要的排序子句。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-143">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="8ab6c-144">主要由长度，其次对字符串进行升序排序的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-144">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="8ab6c-145">次要降序排序</span><span class="sxs-lookup"><span data-stu-id="8ab6c-145">Secondary Descending Sort</span></span>  
 <span data-ttu-id="8ab6c-146">下一个示例演示如何使用`Order By Descending`中 LINQ 查询以升序排序，，次要排序，按降序顺序执行主要排序子句。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-146">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="8ab6c-147">主要由长度，其次字符串的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="8ab6c-147">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ab6c-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab6c-148">See Also</span></span>  
 <span data-ttu-id="8ab6c-149"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8ab6c-149"><xref:System.Linq></span></span>   
<span data-ttu-id="8ab6c-150"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6c-150"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="8ab6c-151"> [Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6c-151"> [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="8ab6c-152"> [如何︰ 对查询结果进行排序](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6c-152"> [How to: Sort Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="8ab6c-153"> [如何︰ 进行排序或筛选器按任意词或字段 (LINQ) (Visual Basic 中) 的文本数据](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="8ab6c-153"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
