---
title: "投影运算 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
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
ms.openlocfilehash: aac5cf69e6c3f4041a4302e8d606ca8dfddbc8a2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="projection-operations-visual-basic"></a><span data-ttu-id="f8b7b-102">投影运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8b7b-102">Projection Operations (Visual Basic)</span></span>
<span data-ttu-id="f8b7b-103">投影是指将对象转换通常只包含将在随后使用这些属性的新窗体的操作。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="f8b7b-104">通过使用投影，您可以构造从每个对象生成的新类型。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="f8b7b-105">可以投影一个属性，并对其执行数学函数。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="f8b7b-106">您也可以计划而不更改它的原始对象。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="f8b7b-107">下一节中列出执行投影的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8b7b-108">方法</span><span class="sxs-lookup"><span data-stu-id="f8b7b-108">Methods</span></span>  
  
|<span data-ttu-id="f8b7b-109">方法名</span><span class="sxs-lookup"><span data-stu-id="f8b7b-109">Method Name</span></span>|<span data-ttu-id="f8b7b-110">描述</span><span class="sxs-lookup"><span data-stu-id="f8b7b-110">Description</span></span>|<span data-ttu-id="f8b7b-111">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="f8b7b-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f8b7b-112">更多信息</span><span class="sxs-lookup"><span data-stu-id="f8b7b-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f8b7b-113">选择</span><span class="sxs-lookup"><span data-stu-id="f8b7b-113">Select</span></span>|<span data-ttu-id="f8b7b-114">根据转换函数的项目值。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-114">Projects values that are based on a transform function.</span></span>|`Select`|<span data-ttu-id="f8b7b-115"><xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8b7b-115"><xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8b7b-116"><xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8b7b-116"><xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f8b7b-117">SelectMany</span><span class="sxs-lookup"><span data-stu-id="f8b7b-117">SelectMany</span></span>|<span data-ttu-id="f8b7b-118">根据转换函数，然后将它们合并为一个序列的值的项目序列。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-118">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="f8b7b-119">使用多个`From`子句</span><span class="sxs-lookup"><span data-stu-id="f8b7b-119">Use multiple `From` clauses</span></span>|<span data-ttu-id="f8b7b-120"><xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8b7b-120"><xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f8b7b-121"><xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8b7b-121"><xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f8b7b-122">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="f8b7b-122">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="f8b7b-123">选择</span><span class="sxs-lookup"><span data-stu-id="f8b7b-123">Select</span></span>  
 <span data-ttu-id="f8b7b-124">下面的示例使用`Select`子句投影每个字符串的字符串的列表中的第一个字母。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-124">The following example uses the `Select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```vb  
Dim words = New List(Of String) From {"an", "apple", "a", "day"}  
  
Dim query = From word In words   
            Select word.Substring(0, 1)  
  
Dim sb As New System.Text.StringBuilder()  
For Each letter As String In query  
    sb.AppendLine(letter)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' a  
' a  
' a  
' d  
```  
  
### <a name="selectmany"></a><span data-ttu-id="f8b7b-125">SelectMany</span><span class="sxs-lookup"><span data-stu-id="f8b7b-125">SelectMany</span></span>  
 <span data-ttu-id="f8b7b-126">下面的示例使用多个`From`子句投影每个字符串的字符串的列表中的每个单词。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-126">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span></span>  
  
```vb  
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}  
  
Dim query = From phrase In phrases   
            From word In phrase.Split(" "c)   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' an  
' apple  
' a  
' day  
' the  
' quick  
' brown  
' fox  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="f8b7b-127">选择与 SelectMany</span><span class="sxs-lookup"><span data-stu-id="f8b7b-127">Select versus SelectMany</span></span>  
 <span data-ttu-id="f8b7b-128">这两者的工作`Select()`和`SelectMany()`旨在源值从生成结果值 （或值）。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-128">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="f8b7b-129">`Select()`生成的每个源值的一个结果值。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-129">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="f8b7b-130">总结果因此是具有与源集合相同数量的元素的集合。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-130">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="f8b7b-131">与此相反，`SelectMany()`生成包含从每个源值的串联子集合的单个整体结果。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-131">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="f8b7b-132">转换函数作为参数传递`SelectMany()`必须返回可枚举序列的每个源值的值。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-132">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="f8b7b-133">这些可枚举序列然后将其串联通过`SelectMany()`来创建一个大的序列。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-133">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="f8b7b-134">下面的两个图例显示了这两种方法的操作的概念区别。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-134">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="f8b7b-135">每种情况下，假定选择器 （转换） 函数从每个源值中选择的鲜花的数组。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-135">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="f8b7b-136">此图描绘了如何`Select()`返回具有与源集合相同数量的元素的集合。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-136">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 <span data-ttu-id="f8b7b-137">![Select （） 的操作的概念图示](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span><span class="sxs-lookup"><span data-stu-id="f8b7b-137">![Conceptual illustration of the action of Select&#40;&#41;](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span></span>  
  
 <span data-ttu-id="f8b7b-138">此图描绘了如何`SelectMany()`串联为一个最终结果值，其中包含每个中间数组中的每个值的数组中间序列。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-138">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 <span data-ttu-id="f8b7b-139">![显示 Selectmany 操作的图。] (../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span><span class="sxs-lookup"><span data-stu-id="f8b7b-139">![Graphic showing the action of SelectMany&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span></span>  
  
### <a name="code-example"></a><span data-ttu-id="f8b7b-140">代码示例</span><span class="sxs-lookup"><span data-stu-id="f8b7b-140">Code Example</span></span>  
 <span data-ttu-id="f8b7b-141">下面的示例比较的行为`Select()`和`SelectMany()`。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-141">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="f8b7b-142">该代码通过对源集合中执行的鲜花名称的每个列表中的前两个项目创建""美丽的鲜花鲜花。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-142">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="f8b7b-143">在此示例中，"单个值"的转换函数<xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>使用本身是值的集合。</xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29></span><span class="sxs-lookup"><span data-stu-id="f8b7b-143">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="f8b7b-144">这需要额外`For Each`循环，以枚举每个子序列中的每个字符串。</span><span class="sxs-lookup"><span data-stu-id="f8b7b-144">This requires the extra `For Each` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```vb  
Class Bouquet  
    Public Flowers As List(Of String)  
End Class  
  
Sub SelectVsSelectMany()  
    Dim bouquets = New List(Of Bouquet) From {   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}  
  
    Dim output As New System.Text.StringBuilder  
  
    ' Select()  
    Dim query1 = bouquets.Select(Function(b) b.Flowers)  
  
    output.AppendLine("Using Select():")  
    For Each flowerList In query1  
        For Each str As String In flowerList  
            output.AppendLine(str)  
        Next  
    Next  
  
    ' SelectMany()  
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)  
  
    output.AppendLine(vbCrLf & "Using SelectMany():")  
    For Each str As String In query2  
        output.AppendLine(str)  
    Next  
  
    ' Display the output  
    MsgBox(output.ToString())  
  
    ' This code produces the following output:  
    '  
    ' Using Select():  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
    ' Using SelectMany()  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8b7b-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8b7b-145">See Also</span></span>  
 <span data-ttu-id="f8b7b-146"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f8b7b-146"><xref:System.Linq></span></span>   
<span data-ttu-id="f8b7b-147"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f8b7b-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="f8b7b-148"> [Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f8b7b-148"> [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) </span></span>  
<span data-ttu-id="f8b7b-149"> [如何︰ 使用联接合并数据](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md) </span><span class="sxs-lookup"><span data-stu-id="f8b7b-149"> [How to: Combine Data with Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md) </span></span>  
<span data-ttu-id="f8b7b-150"> [如何︰ 从多个源 (LINQ) (Visual Basic 中) 填充对象集合](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f8b7b-150"> [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md) </span></span>  
<span data-ttu-id="f8b7b-151"> [如何︰ 返回 LINQ 查询结果为特定的类型](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md) </span><span class="sxs-lookup"><span data-stu-id="f8b7b-151"> [How to: Return a LINQ Query Result as a Specific Type](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md) </span></span>  
<span data-ttu-id="f8b7b-152"> [如何︰ 将一个文件拆分成多个文件，通过使用组 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f8b7b-152"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
