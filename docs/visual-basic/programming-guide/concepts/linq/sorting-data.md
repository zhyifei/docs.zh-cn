---
title: 对数据进行排序 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: ad39aca6a53221f077a6b8313262d508744ff5ea
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819081"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="8c615-102">对数据进行排序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c615-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="8c615-103">排序操作基于一个或多个属性对序列的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="8c615-104">第一个排序条件对元素执行主要排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="8c615-105">通过指定第二个排序条件，您可以对每个主要排序组内的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="8c615-106">下图演示对一个字符序列执行按字母排序操作的结果。</span><span class="sxs-lookup"><span data-stu-id="8c615-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 ![展示按字母顺序排序操作的图。](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="8c615-108">下节列出了对数据进行排序的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="8c615-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c615-109">方法</span><span class="sxs-lookup"><span data-stu-id="8c615-109">Methods</span></span>  
  
|<span data-ttu-id="8c615-110">方法名</span><span class="sxs-lookup"><span data-stu-id="8c615-110">Method Name</span></span>|<span data-ttu-id="8c615-111">描述</span><span class="sxs-lookup"><span data-stu-id="8c615-111">Description</span></span>|<span data-ttu-id="8c615-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="8c615-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="8c615-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="8c615-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="8c615-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="8c615-114">OrderBy</span></span>|<span data-ttu-id="8c615-115">按升序对值排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c615-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="8c615-116">OrderByDescending</span></span>|<span data-ttu-id="8c615-117">按降序对值排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c615-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="8c615-118">ThenBy</span></span>|<span data-ttu-id="8c615-119">按升序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c615-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="8c615-120">ThenByDescending</span></span>|<span data-ttu-id="8c615-121">按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c615-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="8c615-122">Reverse</span></span>|<span data-ttu-id="8c615-123">反转集合中元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="8c615-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="8c615-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="8c615-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="8c615-125">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="8c615-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="8c615-126">主要排序示例</span><span class="sxs-lookup"><span data-stu-id="8c615-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="8c615-127">主要升序排序</span><span class="sxs-lookup"><span data-stu-id="8c615-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="8c615-128">下面的示例演示如何在 LINQ 查询中使用 `Order By` 子句按字符串长度对数组中的字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="8c615-129">主要降序排序</span><span class="sxs-lookup"><span data-stu-id="8c615-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="8c615-130">下面的示例演示如何在 LINQ 查询中使用 `Order By Descending` 子句按字符串的第一个字母对字符串进行降序排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="8c615-131">次要排序示例</span><span class="sxs-lookup"><span data-stu-id="8c615-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="8c615-132">次要升序排序</span><span class="sxs-lookup"><span data-stu-id="8c615-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="8c615-133">下面的示例演示如何在 LINQ 查询中使用 `Order By` 子句对数组中的字符串执行主要和次要排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="8c615-134">首先按字符串长度，其次按字符串的第一个字母，对字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="8c615-135">次要降序排序</span><span class="sxs-lookup"><span data-stu-id="8c615-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="8c615-136">下面的示例演示如何在 LINQ 查询中使用 `Order By Descending` 子句按升序执行主要排序，按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="8c615-137">首先按字符串长度，其次按字符串的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="8c615-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c615-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c615-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="8c615-139">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c615-139">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="8c615-140">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="8c615-140">Order By Clause</span></span>](../../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="8c615-141">如何：对查询结果进行排序</span><span class="sxs-lookup"><span data-stu-id="8c615-141">How to: Sort Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="8c615-142">如何：排序或筛选器文本数据，按任意词或字段 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c615-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
