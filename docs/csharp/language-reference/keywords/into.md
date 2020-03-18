---
title: into - C# 参考
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: f0f5ff1e56a65e83385f814df2fadd957f53561e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713629"
---
# <a name="into-c-reference"></a><span data-ttu-id="476aa-102">into（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="476aa-102">into (C# Reference)</span></span>

<span data-ttu-id="476aa-103">可使用 `into` 上下文关键字创建临时标识符，将 [group](group-clause.md)、[join](join-clause.md) 或 [select](select-clause.md) 子句的结果存储至新标识符。</span><span class="sxs-lookup"><span data-stu-id="476aa-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="476aa-104">此标识符本身可以是附加查询命令的生成器。</span><span class="sxs-lookup"><span data-stu-id="476aa-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="476aa-105">有时称在 `group` 或 `select` 子句中使用新标识符为“延续”  。</span><span class="sxs-lookup"><span data-stu-id="476aa-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="476aa-106">示例</span><span class="sxs-lookup"><span data-stu-id="476aa-106">Example</span></span>

<span data-ttu-id="476aa-107">下面的示例演示使用 `into` 关键字来启用具有推断类型 `fruitGroup` 的临时标识符 `IGrouping`。</span><span class="sxs-lookup"><span data-stu-id="476aa-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="476aa-108">通过使用该标识符，可对每个组调用 <xref:System.Linq.Enumerable.Count%2A> 方法，并且仅选择那些包含两个或更多个单词的组。</span><span class="sxs-lookup"><span data-stu-id="476aa-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="476aa-109">仅当希望对每个组执行附加查询操作时，才需在 `into` 子句中使用 `group`。</span><span class="sxs-lookup"><span data-stu-id="476aa-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="476aa-110">有关详细信息，请参阅 [group 子句](group-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="476aa-110">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="476aa-111">有关在 `into` 子句中使用 `join` 的示例，请参见 [join 子句](join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="476aa-111">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="476aa-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="476aa-112">See also</span></span>

- [<span data-ttu-id="476aa-113">查询关键字 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="476aa-113">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="476aa-114">C# 中的 LINQ</span><span class="sxs-lookup"><span data-stu-id="476aa-114">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="476aa-115">group 子句</span><span class="sxs-lookup"><span data-stu-id="476aa-115">group clause</span></span>](group-clause.md)
