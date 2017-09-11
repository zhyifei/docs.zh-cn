---
title: "转换数据类型 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
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
ms.openlocfilehash: 948779e1648291b00a68bfd83d57750d48a9a6d8
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="d7926-102">转换数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7926-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="d7926-103">转换方法更改输入对象的类型。</span><span class="sxs-lookup"><span data-stu-id="d7926-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="d7926-104">LINQ 查询中的转换运算可在各种应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d7926-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="d7926-105">以下是一些示例︰</span><span class="sxs-lookup"><span data-stu-id="d7926-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="d7926-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>方法可用来隐藏控件的标准查询运算符的类型的自定义实现。</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="d7926-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>方法可以用于启用非参数化以进行 LINQ 查询的集合。</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="d7926-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>， <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>， <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>，和<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>方法可用于强制立即执行查询而不是推迟到枚举该查询。</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7926-109">方法</span><span class="sxs-lookup"><span data-stu-id="d7926-109">Methods</span></span>  
 <span data-ttu-id="d7926-110">下表列出了执行数据类型转换的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="d7926-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="d7926-111">此名称以"As"开头的表中的转换方法更改源集合的静态类型，但不是枚举。</span><span class="sxs-lookup"><span data-stu-id="d7926-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="d7926-112">键入名称以开头"来枚举源集合，以及将项目放入相应的集合"的方法。</span><span class="sxs-lookup"><span data-stu-id="d7926-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="d7926-113">方法名</span><span class="sxs-lookup"><span data-stu-id="d7926-113">Method Name</span></span>|<span data-ttu-id="d7926-114">说明</span><span class="sxs-lookup"><span data-stu-id="d7926-114">Description</span></span>|<span data-ttu-id="d7926-115">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="d7926-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="d7926-116">更多信息</span><span class="sxs-lookup"><span data-stu-id="d7926-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="d7926-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="d7926-117">AsEnumerable</span></span>|<span data-ttu-id="d7926-118">返回类型化为<xref:System.Collections.Generic.IEnumerable%601>。</xref:System.Collections.Generic.IEnumerable%601>输入</span><span class="sxs-lookup"><span data-stu-id="d7926-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="d7926-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-119">Not applicable.</span></span>|<span data-ttu-id="d7926-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="d7926-121">AsQueryable</span></span>|<span data-ttu-id="d7926-122">将转换 （泛型）<xref:System.Collections.IEnumerable>到 （泛型） <xref:System.Linq.IQueryable>。</xref:System.Linq.IQueryable> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="d7926-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="d7926-123">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-123">Not applicable.</span></span>|<span data-ttu-id="d7926-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-125">Cast</span><span class="sxs-lookup"><span data-stu-id="d7926-125">Cast</span></span>|<span data-ttu-id="d7926-126">将强制转换为指定的类型集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="d7926-126">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<span data-ttu-id="d7926-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="d7926-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-129">OfType</span><span class="sxs-lookup"><span data-stu-id="d7926-129">OfType</span></span>|<span data-ttu-id="d7926-130">筛选值，具体取决于他们可强制转换为指定类型的能力。</span><span class="sxs-lookup"><span data-stu-id="d7926-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="d7926-131">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-131">Not applicable.</span></span>|<span data-ttu-id="d7926-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="d7926-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-134">ToArray</span><span class="sxs-lookup"><span data-stu-id="d7926-134">ToArray</span></span>|<span data-ttu-id="d7926-135">将集合转换为数组。</span><span class="sxs-lookup"><span data-stu-id="d7926-135">Converts a collection to an array.</span></span> <span data-ttu-id="d7926-136">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="d7926-136">This method forces query execution.</span></span>|<span data-ttu-id="d7926-137">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-137">Not applicable.</span></span>|<span data-ttu-id="d7926-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-139">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="d7926-139">ToDictionary</span></span>|<span data-ttu-id="d7926-140">将元素放入<xref:System.Collections.Generic.Dictionary%602>根据键选择器函数。</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="d7926-140">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="d7926-141">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="d7926-141">This method forces query execution.</span></span>|<span data-ttu-id="d7926-142">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-142">Not applicable.</span></span>|<span data-ttu-id="d7926-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-144">ToList</span><span class="sxs-lookup"><span data-stu-id="d7926-144">ToList</span></span>|<span data-ttu-id="d7926-145">将集合转换为一种<xref:System.Collections.Generic.List%601>。</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="d7926-145">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="d7926-146">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="d7926-146">This method forces query execution.</span></span>|<span data-ttu-id="d7926-147">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-147">Not applicable.</span></span>|<span data-ttu-id="d7926-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="d7926-149">ToLookup</span><span class="sxs-lookup"><span data-stu-id="d7926-149">ToLookup</span></span>|<span data-ttu-id="d7926-150">将元素放入<xref:System.Linq.Lookup%602>（一多字典） 根据键选择器函数。</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="d7926-150">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="d7926-151">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="d7926-151">This method forces query execution.</span></span>|<span data-ttu-id="d7926-152">不适用。</span><span class="sxs-lookup"><span data-stu-id="d7926-152">Not applicable.</span></span>|<span data-ttu-id="d7926-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7926-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="d7926-154">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="d7926-154">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="d7926-155">下面的代码示例使用`From As`子句，以访问仅适用于子类型的成员之前转换为子类型。</span><span class="sxs-lookup"><span data-stu-id="d7926-155">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7926-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7926-156">See Also</span></span>  
 <span data-ttu-id="d7926-157"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="d7926-157"><xref:System.Linq></span></span>   
<span data-ttu-id="d7926-158"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="d7926-158"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="d7926-159"> [From 子句](../../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="d7926-159"> [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="d7926-160"> [如何︰ 使用 (Visual Basic 中) 的 LINQ 查询 ArrayList](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="d7926-160"> [How to: Query an ArrayList with LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span></span>
