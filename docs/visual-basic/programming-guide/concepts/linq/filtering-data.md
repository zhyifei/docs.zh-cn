---
title: "筛选数据 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 31e3a4729a98e1f4b588cd415a15fff270587234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="3a6fd-102">筛选数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a6fd-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="3a6fd-103">筛选是指将结果集限制为仅包含满足指定条件的元素的操作。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="3a6fd-104">它也称为选定内容。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="3a6fd-105">下图演示了对字符序列进行筛选的结果。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="3a6fd-106">筛选操作的谓词指定字符必须为“A”。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="3a6fd-107">![LINQ 筛选操作](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="3a6fd-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="3a6fd-108">下面一节列出了执行所选内容的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a6fd-109">方法</span><span class="sxs-lookup"><span data-stu-id="3a6fd-109">Methods</span></span>  
  
|<span data-ttu-id="3a6fd-110">方法名</span><span class="sxs-lookup"><span data-stu-id="3a6fd-110">Method Name</span></span>|<span data-ttu-id="3a6fd-111">描述</span><span class="sxs-lookup"><span data-stu-id="3a6fd-111">Description</span></span>|<span data-ttu-id="3a6fd-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="3a6fd-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3a6fd-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="3a6fd-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="3a6fd-114">OfType</span><span class="sxs-lookup"><span data-stu-id="3a6fd-114">OfType</span></span>|<span data-ttu-id="3a6fd-115">根据其转换为特定类型的能力选择值。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="3a6fd-116">不适用。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3a6fd-117">Where</span><span class="sxs-lookup"><span data-stu-id="3a6fd-117">Where</span></span>|<span data-ttu-id="3a6fd-118">选择基于谓词函数的值。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="3a6fd-119">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="3a6fd-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="3a6fd-120">下面的示例使用`Where`若要从数组中筛选这些具有特定长度的字符串。</span><span class="sxs-lookup"><span data-stu-id="3a6fd-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3a6fd-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a6fd-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="3a6fd-122">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a6fd-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="3a6fd-123">Where 子句</span><span class="sxs-lookup"><span data-stu-id="3a6fd-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="3a6fd-124">如何：筛选查询结果</span><span class="sxs-lookup"><span data-stu-id="3a6fd-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)  
 [<span data-ttu-id="3a6fd-125">如何： 查询使用反射 (LINQ) (Visual Basic) 的程序集的元数据</span><span class="sxs-lookup"><span data-stu-id="3a6fd-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="3a6fd-126">如何： 查询具有指定的特性或名称 (Visual Basic) 的文件</span><span class="sxs-lookup"><span data-stu-id="3a6fd-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="3a6fd-127">如何： 排序或筛选器文本数据按任意词或字段 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a6fd-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
