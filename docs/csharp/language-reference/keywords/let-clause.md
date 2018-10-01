---
title: let 子句（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 62294df7f0f2ebb3249dffd72ba4910fbae984c8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47230705"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="0ec96-102">let 子句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0ec96-102">let clause (C# Reference)</span></span>

<span data-ttu-id="0ec96-103">在查询表达式中，存储子表达式的结果有时很有帮助，可在后续子句中使用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="0ec96-104">可以通过 `let` 关键字执行此操作，该关键字创建一个新的范围变量并通过提供的表达式结果初始化该变量。</span><span class="sxs-lookup"><span data-stu-id="0ec96-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="0ec96-105">使用值进行初始化后，范围变量不能用于存储另一个值。</span><span class="sxs-lookup"><span data-stu-id="0ec96-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="0ec96-106">但是，如果范围变量持有可查询类型，则可以查询该变量。</span><span class="sxs-lookup"><span data-stu-id="0ec96-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="0ec96-107">示例</span><span class="sxs-lookup"><span data-stu-id="0ec96-107">Example</span></span>

<span data-ttu-id="0ec96-108">以两种方式使用以下示例 `let`：</span><span class="sxs-lookup"><span data-stu-id="0ec96-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="0ec96-109">创建一个可以查询其自身的可枚举类型。</span><span class="sxs-lookup"><span data-stu-id="0ec96-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="0ec96-110">使查询仅调用一次范围变量 `word` 上的 `ToLower`。</span><span class="sxs-lookup"><span data-stu-id="0ec96-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="0ec96-111">如果不使用 `let`，则不得不调用 `where` 子句中的每个谓词的 `ToLower`。</span><span class="sxs-lookup"><span data-stu-id="0ec96-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="0ec96-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ec96-112">See also</span></span>

- [<span data-ttu-id="0ec96-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0ec96-113">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="0ec96-114">查询关键字 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="0ec96-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="0ec96-115">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="0ec96-115">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="0ec96-116">C# 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="0ec96-116">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="0ec96-117">在查询表达式中处理异常</span><span class="sxs-lookup"><span data-stu-id="0ec96-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)