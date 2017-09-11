---
title: "查询关键字（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6dadce6d48e711032cca03a7f7c2ba02360e685f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="01159-102">查询关键字（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="01159-102">Query Keywords (C# Reference)</span></span>
<span data-ttu-id="01159-103">本部分包含在查询表达式中使用的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-103">This section contains the contextual keywords used in query expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01159-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="01159-104">In This Section</span></span>  
  
|<span data-ttu-id="01159-105">子句</span><span class="sxs-lookup"><span data-stu-id="01159-105">Clause</span></span>|<span data-ttu-id="01159-106">描述</span><span class="sxs-lookup"><span data-stu-id="01159-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01159-107">from</span><span class="sxs-lookup"><span data-stu-id="01159-107">from</span></span>](../../../csharp/language-reference/keywords/from-clause.md)|<span data-ttu-id="01159-108">指定数据源和范围变量（类似于迭代变量）。</span><span class="sxs-lookup"><span data-stu-id="01159-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|  
|[<span data-ttu-id="01159-109">where</span><span class="sxs-lookup"><span data-stu-id="01159-109">where</span></span>](../../../csharp/language-reference/keywords/where-clause.md)|<span data-ttu-id="01159-110">基于由逻辑 AND 和 OR 运算符（`&&` 或 <code>&#124;&#124;</code>）分隔的一个或多个布尔表达式筛选源元素。</span><span class="sxs-lookup"><span data-stu-id="01159-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|  
|[<span data-ttu-id="01159-111">select</span><span class="sxs-lookup"><span data-stu-id="01159-111">select</span></span>](../../../csharp/language-reference/keywords/select-clause.md)|<span data-ttu-id="01159-112">指定执行查询时，所返回序列中元素的类型和形状。</span><span class="sxs-lookup"><span data-stu-id="01159-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|  
|[<span data-ttu-id="01159-113">group</span><span class="sxs-lookup"><span data-stu-id="01159-113">group</span></span>](../../../csharp/language-reference/keywords/group-clause.md)|<span data-ttu-id="01159-114">根据指定的密钥值对查询结果分组。</span><span class="sxs-lookup"><span data-stu-id="01159-114">Groups query results according to a specified key value.</span></span>|  
|[<span data-ttu-id="01159-115">into</span><span class="sxs-lookup"><span data-stu-id="01159-115">into</span></span>](../../../csharp/language-reference/keywords/into.md)|<span data-ttu-id="01159-116">提供可作为对 join、group 或 select 子句结果引用的标识符。</span><span class="sxs-lookup"><span data-stu-id="01159-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|  
|[<span data-ttu-id="01159-117">orderby</span><span class="sxs-lookup"><span data-stu-id="01159-117">orderby</span></span>](../../../csharp/language-reference/keywords/orderby-clause.md)|<span data-ttu-id="01159-118">根据元素类型的默认比较器对查询结果进行升序或降序排序。</span><span class="sxs-lookup"><span data-stu-id="01159-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|  
|[<span data-ttu-id="01159-119">join</span><span class="sxs-lookup"><span data-stu-id="01159-119">join</span></span>](../../../csharp/language-reference/keywords/join-clause.md)|<span data-ttu-id="01159-120">基于两个指定匹配条件间的相等比较而联接两个数据源。</span><span class="sxs-lookup"><span data-stu-id="01159-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|  
|[<span data-ttu-id="01159-121">let</span><span class="sxs-lookup"><span data-stu-id="01159-121">let</span></span>](../../../csharp/language-reference/keywords/let-clause.md)|<span data-ttu-id="01159-122">引入范围变量，在查询表达式中存储子表达式结果。</span><span class="sxs-lookup"><span data-stu-id="01159-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|  
|[<span data-ttu-id="01159-123">in</span><span class="sxs-lookup"><span data-stu-id="01159-123">in</span></span>](../../../csharp/language-reference/keywords/in.md)|<span data-ttu-id="01159-124">[join](../../../csharp/language-reference/keywords/join-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-124">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="01159-125">on</span><span class="sxs-lookup"><span data-stu-id="01159-125">on</span></span>](../../../csharp/language-reference/keywords/on.md)|<span data-ttu-id="01159-126">[join](../../../csharp/language-reference/keywords/join-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-126">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="01159-127">equals</span><span class="sxs-lookup"><span data-stu-id="01159-127">equals</span></span>](../../../csharp/language-reference/keywords/equals.md)|<span data-ttu-id="01159-128">[join](../../../csharp/language-reference/keywords/join-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-128">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="01159-129">by</span><span class="sxs-lookup"><span data-stu-id="01159-129">by</span></span>](../../../csharp/language-reference/keywords/by.md)|<span data-ttu-id="01159-130">[group](../../../csharp/language-reference/keywords/group-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-130">Contextual keyword in a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>|  
|[<span data-ttu-id="01159-131">ascending</span><span class="sxs-lookup"><span data-stu-id="01159-131">ascending</span></span>](../../../csharp/language-reference/keywords/ascending.md)|<span data-ttu-id="01159-132">[orderby](../../../csharp/language-reference/keywords/orderby-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-132">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
|[<span data-ttu-id="01159-133">descending</span><span class="sxs-lookup"><span data-stu-id="01159-133">descending</span></span>](../../../csharp/language-reference/keywords/descending.md)|<span data-ttu-id="01159-134">[orderby](../../../csharp/language-reference/keywords/orderby-clause.md) 子句中的上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="01159-134">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01159-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01159-135">See Also</span></span>  
 <span data-ttu-id="01159-136">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="01159-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="01159-137">[LINQ（语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="01159-137">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="01159-138">[LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="01159-138">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="01159-139">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="01159-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

