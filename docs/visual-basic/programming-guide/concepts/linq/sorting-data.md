---
title: 对数据进行排序 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: f52000d37df45c97754463de1e81cd523806e9c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646859"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="69698-102">对数据进行排序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69698-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="69698-103">排序操作基于一个或多个属性对序列的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="69698-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="69698-104">第一个排序条件对元素执行主要排序。</span><span class="sxs-lookup"><span data-stu-id="69698-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="69698-105">通过指定第二个排序条件，您可以对每个主要排序组内的元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="69698-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="69698-106">下图演示对一个字符序列执行按字母排序操作的结果。</span><span class="sxs-lookup"><span data-stu-id="69698-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="69698-107">![LINQ 排序操作](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="69698-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="69698-108">下节列出了对数据进行排序的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="69698-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69698-109">方法</span><span class="sxs-lookup"><span data-stu-id="69698-109">Methods</span></span>  
  
|<span data-ttu-id="69698-110">方法名</span><span class="sxs-lookup"><span data-stu-id="69698-110">Method Name</span></span>|<span data-ttu-id="69698-111">描述</span><span class="sxs-lookup"><span data-stu-id="69698-111">Description</span></span>|<span data-ttu-id="69698-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="69698-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="69698-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="69698-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="69698-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="69698-114">OrderBy</span></span>|<span data-ttu-id="69698-115">按升序对值排序。</span><span class="sxs-lookup"><span data-stu-id="69698-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="69698-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="69698-116">OrderByDescending</span></span>|<span data-ttu-id="69698-117">按降序对值排序。</span><span class="sxs-lookup"><span data-stu-id="69698-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="69698-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="69698-118">ThenBy</span></span>|<span data-ttu-id="69698-119">按升序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="69698-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="69698-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="69698-120">ThenByDescending</span></span>|<span data-ttu-id="69698-121">按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="69698-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="69698-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="69698-122">Reverse</span></span>|<span data-ttu-id="69698-123">反转集合中元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="69698-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="69698-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="69698-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="69698-125">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="69698-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="69698-126">主要排序示例</span><span class="sxs-lookup"><span data-stu-id="69698-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="69698-127">主要升序排序</span><span class="sxs-lookup"><span data-stu-id="69698-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="69698-128">下面的示例演示如何在 LINQ 查询中使用 `Order By` 子句按字符串长度对数组中的字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="69698-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="69698-129">主要降序排序</span><span class="sxs-lookup"><span data-stu-id="69698-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="69698-130">下面的示例演示如何在 LINQ 查询中使用 `Order By Descending` 子句按字符串的第一个字母对字符串进行降序排序。</span><span class="sxs-lookup"><span data-stu-id="69698-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="69698-131">次要排序示例</span><span class="sxs-lookup"><span data-stu-id="69698-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="69698-132">次要升序排序</span><span class="sxs-lookup"><span data-stu-id="69698-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="69698-133">下面的示例演示如何在 LINQ 查询中使用 `Order By` 子句对数组中的字符串执行主要和次要排序。</span><span class="sxs-lookup"><span data-stu-id="69698-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="69698-134">首先按字符串长度，其次按字符串的第一个字母，对字符串进行升序排序。</span><span class="sxs-lookup"><span data-stu-id="69698-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="69698-135">次要降序排序</span><span class="sxs-lookup"><span data-stu-id="69698-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="69698-136">下面的示例演示如何在 LINQ 查询中使用 `Order By Descending` 子句按升序执行主要排序，按降序执行次要排序。</span><span class="sxs-lookup"><span data-stu-id="69698-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="69698-137">首先按字符串长度，其次按字符串的第一个字母，对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="69698-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69698-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="69698-138">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="69698-139">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69698-139">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="69698-140">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="69698-140">Order By Clause</span></span>](../../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="69698-141">如何：对查询结果进行排序</span><span class="sxs-lookup"><span data-stu-id="69698-141">How to: Sort Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)  
 [<span data-ttu-id="69698-142">如何： 排序或筛选器文本数据按任意词或字段 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69698-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
