---
title: 查询关键字（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 9ec163e1de018bd87348a5b39a1f34654d7d6d84
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45624757"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="3c2b0-102">查询关键字（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3c2b0-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="3c2b0-103">本部分包含在查询表达式中使用的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3c2b0-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="3c2b0-104">In this section</span></span>

|<span data-ttu-id="3c2b0-105">子句</span><span class="sxs-lookup"><span data-stu-id="3c2b0-105">Clause</span></span>|<span data-ttu-id="3c2b0-106">描述</span><span class="sxs-lookup"><span data-stu-id="3c2b0-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="3c2b0-107">from</span><span class="sxs-lookup"><span data-stu-id="3c2b0-107">from</span></span>](from-clause.md)|<span data-ttu-id="3c2b0-108">指定数据源和范围变量（类似于迭代变量）。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="3c2b0-109">where</span><span class="sxs-lookup"><span data-stu-id="3c2b0-109">where</span></span>](where-clause.md)|<span data-ttu-id="3c2b0-110">基于由逻辑 AND 和 OR 运算符（`&&` 或 <code>&#124;&#124;</code>）分隔的一个或多个布尔表达式筛选源元素。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="3c2b0-111">select</span><span class="sxs-lookup"><span data-stu-id="3c2b0-111">select</span></span>](select-clause.md)|<span data-ttu-id="3c2b0-112">指定执行查询时，所返回序列中元素的类型和形状。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="3c2b0-113">group</span><span class="sxs-lookup"><span data-stu-id="3c2b0-113">group</span></span>](group-clause.md)|<span data-ttu-id="3c2b0-114">根据指定的密钥值对查询结果分组。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="3c2b0-115">into</span><span class="sxs-lookup"><span data-stu-id="3c2b0-115">into</span></span>](into.md)|<span data-ttu-id="3c2b0-116">提供可作为对 join、group 或 select 子句结果引用的标识符。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="3c2b0-117">orderby</span><span class="sxs-lookup"><span data-stu-id="3c2b0-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="3c2b0-118">根据元素类型的默认比较器对查询结果进行升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="3c2b0-119">join</span><span class="sxs-lookup"><span data-stu-id="3c2b0-119">join</span></span>](join-clause.md)|<span data-ttu-id="3c2b0-120">基于两个指定匹配条件间的相等比较而联接两个数据源。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="3c2b0-121">let</span><span class="sxs-lookup"><span data-stu-id="3c2b0-121">let</span></span>](let-clause.md)|<span data-ttu-id="3c2b0-122">引入范围变量，在查询表达式中存储子表达式结果。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="3c2b0-123">in</span><span class="sxs-lookup"><span data-stu-id="3c2b0-123">in</span></span>](in.md)|<span data-ttu-id="3c2b0-124">[join](join-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="3c2b0-125">on</span><span class="sxs-lookup"><span data-stu-id="3c2b0-125">on</span></span>](on.md)|<span data-ttu-id="3c2b0-126">[join](join-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="3c2b0-127">equals</span><span class="sxs-lookup"><span data-stu-id="3c2b0-127">equals</span></span>](equals.md)|<span data-ttu-id="3c2b0-128">[join](join-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="3c2b0-129">by</span><span class="sxs-lookup"><span data-stu-id="3c2b0-129">by</span></span>](by.md)|<span data-ttu-id="3c2b0-130">[group](group-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="3c2b0-131">ascending</span><span class="sxs-lookup"><span data-stu-id="3c2b0-131">ascending</span></span>](ascending.md)|<span data-ttu-id="3c2b0-132">[orderby](orderby-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="3c2b0-133">descending</span><span class="sxs-lookup"><span data-stu-id="3c2b0-133">descending</span></span>](descending.md)|<span data-ttu-id="3c2b0-134">[orderby](orderby-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="3c2b0-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3c2b0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c2b0-135">See also</span></span>

- [<span data-ttu-id="3c2b0-136">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3c2b0-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3c2b0-137">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="3c2b0-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="3c2b0-138">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="3c2b0-138">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="3c2b0-139">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="3c2b0-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)