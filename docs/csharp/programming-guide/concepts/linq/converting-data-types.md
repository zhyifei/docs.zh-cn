---
title: 转换数据类型 (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 54ef612ad4e92058d9af4d96b7b3cde9732b2f9c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271070"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="b7030-102">转换数据类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="b7030-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="b7030-103">转换方法可更改输入对象的类型。</span><span class="sxs-lookup"><span data-stu-id="b7030-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="b7030-104">LINQ 查询中的转换运算可用于各种应用程序。</span><span class="sxs-lookup"><span data-stu-id="b7030-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="b7030-105">以下是一些示例：</span><span class="sxs-lookup"><span data-stu-id="b7030-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="b7030-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> 方法可用于隐藏类型的标准查询运算符自定义实现。</span><span class="sxs-lookup"><span data-stu-id="b7030-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="b7030-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> 方法可用于为 LINQ 查询启用非参数化集合。</span><span class="sxs-lookup"><span data-stu-id="b7030-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="b7030-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> 和 <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> 方法可用于强制执行即时的查询，而不是将其推迟到枚举该查询时。</span><span class="sxs-lookup"><span data-stu-id="b7030-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7030-109">方法</span><span class="sxs-lookup"><span data-stu-id="b7030-109">Methods</span></span>  
 <span data-ttu-id="b7030-110">下表列出了执行数据类型转换的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="b7030-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="b7030-111">本表中名称以“As”开头的转换方法可更改源集合的静态类型，但不对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="b7030-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="b7030-112">名称以“To”开头的方法可枚举源集合，并将项放入相应的集合类型。</span><span class="sxs-lookup"><span data-stu-id="b7030-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="b7030-113">方法名</span><span class="sxs-lookup"><span data-stu-id="b7030-113">Method Name</span></span>|<span data-ttu-id="b7030-114">描述</span><span class="sxs-lookup"><span data-stu-id="b7030-114">Description</span></span>|<span data-ttu-id="b7030-115">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="b7030-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="b7030-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b7030-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b7030-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="b7030-117">AsEnumerable</span></span>|<span data-ttu-id="b7030-118">返回类型化为 <xref:System.Collections.Generic.IEnumerable%601> 的输入。</span><span class="sxs-lookup"><span data-stu-id="b7030-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="b7030-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="b7030-120">AsQueryable</span></span>|<span data-ttu-id="b7030-121">将（泛型）<xref:System.Collections.IEnumerable> 转换为（泛型）<xref:System.Linq.IQueryable>。</span><span class="sxs-lookup"><span data-stu-id="b7030-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="b7030-122">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-123">Cast</span><span class="sxs-lookup"><span data-stu-id="b7030-123">Cast</span></span>|<span data-ttu-id="b7030-124">将集合中的元素转换为指定类型。</span><span class="sxs-lookup"><span data-stu-id="b7030-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="b7030-125">使用显式类型化的范围变量。</span><span class="sxs-lookup"><span data-stu-id="b7030-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="b7030-126">例如:</span><span class="sxs-lookup"><span data-stu-id="b7030-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-127">OfType</span><span class="sxs-lookup"><span data-stu-id="b7030-127">OfType</span></span>|<span data-ttu-id="b7030-128">根据其转换为指定类型的能力筛选值。</span><span class="sxs-lookup"><span data-stu-id="b7030-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="b7030-129">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="b7030-130">ToArray</span></span>|<span data-ttu-id="b7030-131">将集合转换为数组。</span><span class="sxs-lookup"><span data-stu-id="b7030-131">Converts a collection to an array.</span></span> <span data-ttu-id="b7030-132">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="b7030-132">This method forces query execution.</span></span>|<span data-ttu-id="b7030-133">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="b7030-134">ToDictionary</span></span>|<span data-ttu-id="b7030-135">根据键选择器函数将元素放入 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="b7030-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="b7030-136">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="b7030-136">This method forces query execution.</span></span>|<span data-ttu-id="b7030-137">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-138">ToList</span><span class="sxs-lookup"><span data-stu-id="b7030-138">ToList</span></span>|<span data-ttu-id="b7030-139">将集合转换为 <xref:System.Collections.Generic.List%601>。</span><span class="sxs-lookup"><span data-stu-id="b7030-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="b7030-140">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="b7030-140">This method forces query execution.</span></span>|<span data-ttu-id="b7030-141">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b7030-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="b7030-142">ToLookup</span></span>|<span data-ttu-id="b7030-143">根据键选择器函数将元素放入 <xref:System.Linq.Lookup%602>（一对多字典）。</span><span class="sxs-lookup"><span data-stu-id="b7030-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="b7030-144">此方法强制执行查询。</span><span class="sxs-lookup"><span data-stu-id="b7030-144">This method forces query execution.</span></span>|<span data-ttu-id="b7030-145">不适用。</span><span class="sxs-lookup"><span data-stu-id="b7030-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="b7030-146">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="b7030-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="b7030-147">下面的代码示例使用显式类型化的范围变量将类型转换为子类型，然后才访问仅在此子类型上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="b7030-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7030-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7030-148">See Also</span></span>

- <xref:System.Linq>  
- [<span data-ttu-id="b7030-149">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="b7030-149">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="b7030-150">from 子句</span><span class="sxs-lookup"><span data-stu-id="b7030-150">from clause</span></span>](../../../../csharp/language-reference/keywords/from-clause.md)  
- [<span data-ttu-id="b7030-151">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="b7030-151">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [<span data-ttu-id="b7030-152">如何：使用 LINQ 查询 ArrayList (C#)</span><span class="sxs-lookup"><span data-stu-id="b7030-152">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
