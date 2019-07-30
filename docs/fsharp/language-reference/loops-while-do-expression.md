---
title: 循环：while...do 表达式
description: 了解如何操作 .。。当指定的测试条件为 true 时, do expression 用于执行迭代执行 (循环)。
ms.date: 05/16/2016
ms.openlocfilehash: f05bdd9f8f4b9446d59f68e1231fb75e18e9b526
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630756"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="a5c93-103">循环：while...do 表达式</span><span class="sxs-lookup"><span data-stu-id="a5c93-103">Loops: while...do Expression</span></span>

<span data-ttu-id="a5c93-104">`while...do`表达式用于在指定的测试条件为 true 时执行迭代执行 (循环)。</span><span class="sxs-lookup"><span data-stu-id="a5c93-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5c93-105">语法</span><span class="sxs-lookup"><span data-stu-id="a5c93-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="a5c93-106">备注</span><span class="sxs-lookup"><span data-stu-id="a5c93-106">Remarks</span></span>

<span data-ttu-id="a5c93-107">计算*测试表达式*;如果为`true`, 则执行*主体表达式*, 并再次计算测试表达式。</span><span class="sxs-lookup"><span data-stu-id="a5c93-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="a5c93-108">*主体表达式*的类型`unit`必须为。</span><span class="sxs-lookup"><span data-stu-id="a5c93-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="a5c93-109">如果测试表达式为`false`, 则迭代结束。</span><span class="sxs-lookup"><span data-stu-id="a5c93-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="a5c93-110">下面的示例阐释了`while...do`表达式的用法。</span><span class="sxs-lookup"><span data-stu-id="a5c93-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="a5c93-111">上述代码的输出是介于1和20之间的随机数的流, 其中最后一个值为10。</span><span class="sxs-lookup"><span data-stu-id="a5c93-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="a5c93-112">可以在序列`while...do`表达式和其他计算表达式中使用, 在这种情况下, 将使用`while...do`自定义版本的表达式。</span><span class="sxs-lookup"><span data-stu-id="a5c93-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="a5c93-113">有关详细信息, 请参阅[序列](sequences.md)、[异步工作流](asynchronous-workflows.md)和[计算表达式](computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="a5c93-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5c93-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5c93-114">See also</span></span>

- [<span data-ttu-id="a5c93-115">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a5c93-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a5c93-116">循环`for...in`表达式</span><span class="sxs-lookup"><span data-stu-id="a5c93-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="a5c93-117">循环`for...to`表达式</span><span class="sxs-lookup"><span data-stu-id="a5c93-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
