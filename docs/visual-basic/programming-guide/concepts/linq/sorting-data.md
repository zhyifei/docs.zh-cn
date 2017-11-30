---
title: "对数据进行排序 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8f17c6ecad721dd3a48a01c09693b0a1cf723a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="aa54c-102">对数据进行排序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa54c-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="aa54c-103">排序操作基于一个或多个属性对序列的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="aa54c-104">第一个排序条件对元素执行主要排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="aa54c-105">通过指定第二个排序条件，您可以对每个主要排序组内的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="aa54c-106">下图演示对一个字符序列执行按字母排序操作的结果。</span><span class="sxs-lookup"><span data-stu-id="aa54c-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="aa54c-107">![LINQ 排序操作](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="aa54c-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="aa54c-108">下节列出了对数据进行排序的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="aa54c-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa54c-109">方法</span><span class="sxs-lookup"><span data-stu-id="aa54c-109">Methods</span></span>  
  
|<span data-ttu-id="aa54c-110">方法名</span><span class="sxs-lookup"><span data-stu-id="aa54c-110">Method Name</span></span>|<span data-ttu-id="aa54c-111">描述</span><span class="sxs-lookup"><span data-stu-id="aa54c-111">Description</span></span>|<span data-ttu-id="aa54c-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="aa54c-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="aa54c-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="aa54c-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="aa54c-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="aa54c-114">OrderBy</span></span>|<span data-ttu-id="aa54c-115">按升序对值排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="aa54c-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="aa54c-116">OrderByDescending</span></span>|<span data-ttu-id="aa54c-117">按降序对值排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="aa54c-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="aa54c-118">ThenBy</span></span>|<span data-ttu-id="aa54c-119">按升序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="aa54c-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="aa54c-120">ThenByDescending</span></span>|<span data-ttu-id="aa54c-121">按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="aa54c-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="aa54c-122">Reverse</span></span>|<span data-ttu-id="aa54c-123">反转集合中元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="aa54c-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="aa54c-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="aa54c-125">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="aa54c-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="aa54c-126">主要排序示例</span><span class="sxs-lookup"><span data-stu-id="aa54c-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="aa54c-127">主要升序排序</span><span class="sxs-lookup"><span data-stu-id="aa54c-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="aa54c-128">下面的示例演示如何在 LINQ 查询中使用 `Order By` 子句按字符串长度对数组中的字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="aa54c-129">主要降序排序</span><span class="sxs-lookup"><span data-stu-id="aa54c-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="aa54c-130">下面的示例演示如何在 LINQ 查询中使用 `Order By Descending` 子句按字符串的第一个字母对字符串进行降序排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="aa54c-131">次要排序示例</span><span class="sxs-lookup"><span data-stu-id="aa54c-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="aa54c-132">次要升序排序</span><span class="sxs-lookup"><span data-stu-id="aa54c-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="aa54c-133">下面的示例演示如何在 LINQ 查询中使用 `Order By` 子句对数组中的字符串执行主要和次要排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="aa54c-134">首先按字符串长度，其次按字符串的第一个字母，对字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="aa54c-135">次要降序排序</span><span class="sxs-lookup"><span data-stu-id="aa54c-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="aa54c-136">下面的示例演示如何在 LINQ 查询中使用 `Order By Descending` 子句按升序执行主要排序，按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="aa54c-137">首先按字符串长度，其次按字符串的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="aa54c-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa54c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa54c-138">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="aa54c-139">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa54c-139">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="aa54c-140">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="aa54c-140">Order By Clause</span></span>](../../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="aa54c-141">如何：对查询结果进行排序</span><span class="sxs-lookup"><span data-stu-id="aa54c-141">How to: Sort Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)  
 [<span data-ttu-id="aa54c-142">如何： 排序或筛选器文本数据按任意词或字段 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa54c-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
