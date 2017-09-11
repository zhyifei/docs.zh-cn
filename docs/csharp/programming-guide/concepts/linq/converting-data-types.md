---
title: "转换数据类型 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 454fb0ce937d7d20dfce26d92dbf49de24f062f0
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="converting-data-types-c"></a><span data-ttu-id="374a5-102">转换数据类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="374a5-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="374a5-103">转换方法可更改输入对象的类型。</span><span class="sxs-lookup"><span data-stu-id="374a5-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="374a5-104">LINQ 查询中的转换运算可用于各种应用程序。</span><span class="sxs-lookup"><span data-stu-id="374a5-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="374a5-105">以下是一些示例：</span><span class="sxs-lookup"><span data-stu-id="374a5-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="374a5-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> 方法可用于隐藏类型的标准查询运算符自定义实现。</span><span class="sxs-lookup"><span data-stu-id="374a5-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="374a5-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> 方法可用于为 LINQ 查询启用非参数化集合。</span><span class="sxs-lookup"><span data-stu-id="374a5-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="374a5-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>、<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>、<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> 和 <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> 方法可用于强制执行即时的查询，而不是将其推迟到枚举该查询时。</span><span class="sxs-lookup"><span data-stu-id="374a5-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="374a5-109">方法</span><span class="sxs-lookup"><span data-stu-id="374a5-109">Methods</span></span>  
 <span data-ttu-id="374a5-110">下表列出了执行数据类型转换的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="374a5-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="374a5-111">本表中名称以“As”开头的转换方法可更改源集合的静态类型，但不对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="374a5-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="374a5-112">名称以“To”开头的方法可枚举源集合，并将项放入相应的集合类型。</span><span class="sxs-lookup"><span data-stu-id="374a5-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="374a5-113">方法名</span><span class="sxs-lookup"><span data-stu-id="374a5-113">Method Name</span></span>|<span data-ttu-id="374a5-114">描述</span><span class="sxs-lookup"><span data-stu-id="374a5-114">Description</span></span>|<span data-ttu-id="374a5-115">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="374a5-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="374a5-116">更多信息</span><span class="sxs-lookup"><span data-stu-id="374a5-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="374a5-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="374a5-117">AsEnumerable</span></span>|<span data-ttu-id="374a5-118">返回类型化为 <xref:System.Collections.Generic.IEnumerable%601> 的输入。</span><span class="sxs-lookup"><span data-stu-id="374a5-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="374a5-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="374a5-120">AsQueryable</span></span>|<span data-ttu-id="374a5-121">将（泛型）<xref:System.Collections.IEnumerable> 转换为（泛型）<xref:System.Linq.IQueryable>。</span><span class="sxs-lookup"><span data-stu-id="374a5-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="374a5-122">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-123">Cast</span><span class="sxs-lookup"><span data-stu-id="374a5-123">Cast</span></span>|<span data-ttu-id="374a5-124">将集合中的元素转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="374a5-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="374a5-125">使用显式类型化的范围变量。</span><span class="sxs-lookup"><span data-stu-id="374a5-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="374a5-126">例如: </span><span class="sxs-lookup"><span data-stu-id="374a5-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-127">OfType</span><span class="sxs-lookup"><span data-stu-id="374a5-127">OfType</span></span>|<span data-ttu-id="374a5-128">根据其转换为指定类型的能力筛选值。</span><span class="sxs-lookup"><span data-stu-id="374a5-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="374a5-129">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="374a5-130">ToArray</span></span>|<span data-ttu-id="374a5-131">将集合转换为数组。</span><span class="sxs-lookup"><span data-stu-id="374a5-131">Converts a collection to an array.</span></span> <span data-ttu-id="374a5-132">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="374a5-132">This method forces query execution.</span></span>|<span data-ttu-id="374a5-133">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="374a5-134">ToDictionary</span></span>|<span data-ttu-id="374a5-135">根据键选择器函数将元素放入 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="374a5-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="374a5-136">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="374a5-136">This method forces query execution.</span></span>|<span data-ttu-id="374a5-137">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-138">ToList</span><span class="sxs-lookup"><span data-stu-id="374a5-138">ToList</span></span>|<span data-ttu-id="374a5-139">将集合转换为 <xref:System.Collections.Generic.List%601>。</span><span class="sxs-lookup"><span data-stu-id="374a5-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="374a5-140">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="374a5-140">This method forces query execution.</span></span>|<span data-ttu-id="374a5-141">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|<span data-ttu-id="374a5-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="374a5-142">ToLookup</span></span>|<span data-ttu-id="374a5-143">根据键选择器函数将元素放入 <xref:System.Linq.Lookup%602>（一对多字典）。</span><span class="sxs-lookup"><span data-stu-id="374a5-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="374a5-144">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="374a5-144">This method forces query execution.</span></span>|<span data-ttu-id="374a5-145">不适用。</span><span class="sxs-lookup"><span data-stu-id="374a5-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="374a5-146">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="374a5-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="374a5-147">下面的代码示例使用显式类型化的范围变量将类型转换为子类型，然后才访问仅在此子类型上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="374a5-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="374a5-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="374a5-148">See Also</span></span>  
 <span data-ttu-id="374a5-149"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="374a5-149"><xref:System.Linq></span></span>   
 <span data-ttu-id="374a5-150">[标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="374a5-150">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="374a5-151">[from 子句](../../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="374a5-151">[from clause](../../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="374a5-152">[LINQ 查询表达式](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="374a5-152">[LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="374a5-153">如何：使用 LINQ 查询 ArrayList (C#)</span><span class="sxs-lookup"><span data-stu-id="374a5-153">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)

