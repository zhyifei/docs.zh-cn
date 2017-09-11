---
title: "分组数据 (Visual Basic) |Microsoft 文档"
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
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
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
ms.openlocfilehash: ce4e8f924f91eed451d3b1a02cd0bcff75589537
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="00e6a-102">对数据进行分组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00e6a-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="00e6a-103">分组是指将数据放入组，以便每个组中的元素共享一个公共属性的操作。</span><span class="sxs-lookup"><span data-stu-id="00e6a-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="00e6a-104">下图显示的字符序列进行分组的结果。</span><span class="sxs-lookup"><span data-stu-id="00e6a-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="00e6a-105">每个组的密钥是字符。</span><span class="sxs-lookup"><span data-stu-id="00e6a-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="00e6a-106">![LINQ 分组操作](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="00e6a-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="00e6a-107">下一节中列出的数据元素进行分组的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="00e6a-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00e6a-108">方法</span><span class="sxs-lookup"><span data-stu-id="00e6a-108">Methods</span></span>  
  
|<span data-ttu-id="00e6a-109">方法名</span><span class="sxs-lookup"><span data-stu-id="00e6a-109">Method Name</span></span>|<span data-ttu-id="00e6a-110">说明</span><span class="sxs-lookup"><span data-stu-id="00e6a-110">Description</span></span>|<span data-ttu-id="00e6a-111">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="00e6a-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="00e6a-112">更多信息</span><span class="sxs-lookup"><span data-stu-id="00e6a-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="00e6a-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="00e6a-113">GroupBy</span></span>|<span data-ttu-id="00e6a-114">共享一个公共属性的元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="00e6a-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="00e6a-115">每个组都由<xref:System.Linq.IGrouping%602>对象。</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="00e6a-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<span data-ttu-id="00e6a-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="00e6a-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="00e6a-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="00e6a-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="00e6a-118">ToLookup</span><span class="sxs-lookup"><span data-stu-id="00e6a-118">ToLookup</span></span>|<span data-ttu-id="00e6a-119">将元素插入到<xref:System.Linq.Lookup%602>（一多字典） 根据键选择器函数。</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="00e6a-119">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="00e6a-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="00e6a-120">Not applicable.</span></span>|<span data-ttu-id="00e6a-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="00e6a-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="00e6a-122">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="00e6a-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="00e6a-123">下面的代码示例使用`Group By`整数根据它们是偶数还是奇数列表中进行分组的子句。</span><span class="sxs-lookup"><span data-stu-id="00e6a-123">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="00e6a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00e6a-124">See Also</span></span>  
 <span data-ttu-id="00e6a-125"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="00e6a-125"><xref:System.Linq></span></span>   
<span data-ttu-id="00e6a-126"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="00e6a-126"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="00e6a-127"> [Group By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="00e6a-127"> [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span></span>  
<span data-ttu-id="00e6a-128"> [如何︰ 通过扩展 (LINQ) (Visual Basic 中) 的文件进行分组](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="00e6a-128"> [How to: Group Files by Extension (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
<span data-ttu-id="00e6a-129"> [如何︰ 将一个文件拆分成多个文件，通过使用组 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="00e6a-129"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
