---
title: "筛选数据 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fa2d3b6c5b81f137ab3a81f9b18707bb2da91f6e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="92313-102">筛选数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92313-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="92313-103">筛选是指将结果集包含满足指定的条件的这些元素限制的操作。</span><span class="sxs-lookup"><span data-stu-id="92313-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="92313-104">它也称为是所选内容。</span><span class="sxs-lookup"><span data-stu-id="92313-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="92313-105">下图显示的字符序列进行筛选的结果。</span><span class="sxs-lookup"><span data-stu-id="92313-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="92313-106">筛选操作谓词指定的字符必须是 A。</span><span class="sxs-lookup"><span data-stu-id="92313-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="92313-107">![LINQ 筛选操作](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="92313-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="92313-108">执行所选内容的标准查询运算符方法下一节中列出。</span><span class="sxs-lookup"><span data-stu-id="92313-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92313-109">方法</span><span class="sxs-lookup"><span data-stu-id="92313-109">Methods</span></span>  
  
|<span data-ttu-id="92313-110">方法名</span><span class="sxs-lookup"><span data-stu-id="92313-110">Method Name</span></span>|<span data-ttu-id="92313-111">描述</span><span class="sxs-lookup"><span data-stu-id="92313-111">Description</span></span>|<span data-ttu-id="92313-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="92313-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="92313-113">更多信息</span><span class="sxs-lookup"><span data-stu-id="92313-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="92313-114">OfType</span><span class="sxs-lookup"><span data-stu-id="92313-114">OfType</span></span>|<span data-ttu-id="92313-115">选择值，具体取决于他们可强制转换为指定类型的能力。</span><span class="sxs-lookup"><span data-stu-id="92313-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="92313-116">不适用。</span><span class="sxs-lookup"><span data-stu-id="92313-116">Not applicable.</span></span>|<span data-ttu-id="92313-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="92313-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="92313-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="92313-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="92313-119">Where</span><span class="sxs-lookup"><span data-stu-id="92313-119">Where</span></span>|<span data-ttu-id="92313-120">选择基于谓词的函数的值。</span><span class="sxs-lookup"><span data-stu-id="92313-120">Selects values that are based on a predicate function.</span></span>|`Where`|<span data-ttu-id="92313-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="92313-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="92313-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="92313-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="92313-123">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="92313-123">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="92313-124">下面的示例使用`Where`若要从数组中筛选这些具有特定长度的字符串。</span><span class="sxs-lookup"><span data-stu-id="92313-124">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a><span data-ttu-id="92313-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92313-125">See Also</span></span>  
 <span data-ttu-id="92313-126"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="92313-126"><xref:System.Linq></span></span>   
<span data-ttu-id="92313-127"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="92313-127"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="92313-128"> [其中子句](../../../../visual-basic/language-reference/queries/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="92313-128"> [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) </span></span>  
<span data-ttu-id="92313-129"> [如何︰ 筛选查询结果](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="92313-129"> [How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="92313-130"> [如何︰ 查询使用反射 (LINQ) (Visual Basic 中) 的程序集的元数据](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="92313-130"> [How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
<span data-ttu-id="92313-131"> [如何︰ 查询具有指定的特性或名称 (Visual Basic 中) 的文件](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="92313-131"> [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
<span data-ttu-id="92313-132"> [如何︰ 进行排序或筛选器按任意词或字段 (LINQ) (Visual Basic 中) 的文本数据](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="92313-132"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
