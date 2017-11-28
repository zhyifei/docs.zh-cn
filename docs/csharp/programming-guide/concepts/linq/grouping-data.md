---
title: "对数据分组 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4aef8d10eaffb384fe919ffa6a1e742cb837f540
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="grouping-data-c"></a><span data-ttu-id="cb70d-102">对数据分组 (C#)</span><span class="sxs-lookup"><span data-stu-id="cb70d-102">Grouping Data (C#)</span></span>
<span data-ttu-id="cb70d-103">分组是指将数据分到不同的组，使每组中的元素拥有公共的属性。</span><span class="sxs-lookup"><span data-stu-id="cb70d-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="cb70d-104">下图演示了对字符序列进行分组的结果。</span><span class="sxs-lookup"><span data-stu-id="cb70d-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="cb70d-105">每个组的键是字符。</span><span class="sxs-lookup"><span data-stu-id="cb70d-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="cb70d-106">![LINQ 分组操作](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="cb70d-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="cb70d-107">下一节列出了对数据元素进行分组的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="cb70d-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb70d-108">方法</span><span class="sxs-lookup"><span data-stu-id="cb70d-108">Methods</span></span>  
  
|<span data-ttu-id="cb70d-109">方法名</span><span class="sxs-lookup"><span data-stu-id="cb70d-109">Method Name</span></span>|<span data-ttu-id="cb70d-110">描述</span><span class="sxs-lookup"><span data-stu-id="cb70d-110">Description</span></span>|<span data-ttu-id="cb70d-111">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="cb70d-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="cb70d-112">更多信息</span><span class="sxs-lookup"><span data-stu-id="cb70d-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="cb70d-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="cb70d-113">GroupBy</span></span>|<span data-ttu-id="cb70d-114">对共享通用属性的元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="cb70d-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="cb70d-115">每组由一个 <xref:System.Linq.IGrouping%602> 对象表示。</span><span class="sxs-lookup"><span data-stu-id="cb70d-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="cb70d-116">- 或 -</span><span class="sxs-lookup"><span data-stu-id="cb70d-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cb70d-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="cb70d-117">ToLookup</span></span>|<span data-ttu-id="cb70d-118">将元素插入基于键选择器函数的 <xref:System.Linq.Lookup%602>（一种一对多字典）。</span><span class="sxs-lookup"><span data-stu-id="cb70d-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="cb70d-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="cb70d-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="cb70d-120">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="cb70d-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="cb70d-121">下列代码示例根据奇偶性，使用 `group by` 子句对列表中的整数进行分组。</span><span class="sxs-lookup"><span data-stu-id="cb70d-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb70d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb70d-122">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="cb70d-123">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="cb70d-123">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="cb70d-124">group 子句</span><span class="sxs-lookup"><span data-stu-id="cb70d-124">group clause</span></span>](../../../../csharp/language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="cb70d-125">如何：创建嵌套组</span><span class="sxs-lookup"><span data-stu-id="cb70d-125">How to: Create a Nested Group</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
 [<span data-ttu-id="cb70d-126">如何：按扩展名对文件分组 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cb70d-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 [<span data-ttu-id="cb70d-127">如何：对查询结果进行分组</span><span class="sxs-lookup"><span data-stu-id="cb70d-127">How to: Group Query Results</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
 [<span data-ttu-id="cb70d-128">如何：对分组操作执行子查询</span><span class="sxs-lookup"><span data-stu-id="cb70d-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="cb70d-129">如何：使用组将一个文件拆分成多个文件 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cb70d-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
