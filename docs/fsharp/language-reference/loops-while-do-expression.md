---
title: "循环：while...do 表达式 (F#)"
description: "请参阅如何 while...是否会使用表达式来指定的测试条件为 true 时执行迭代执行 （循环）。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 6a186d75dcda383764949c2cd3b09bc9e3d1080a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="1a98b-104">循环：while...do 表达式</span><span class="sxs-lookup"><span data-stu-id="1a98b-104">Loops: while...do Expression</span></span>

<span data-ttu-id="1a98b-105">`while...do`会使用表达式来指定的测试条件为 true 时执行迭代执行 （循环）。</span><span class="sxs-lookup"><span data-stu-id="1a98b-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="1a98b-106">语法</span><span class="sxs-lookup"><span data-stu-id="1a98b-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="1a98b-107">备注</span><span class="sxs-lookup"><span data-stu-id="1a98b-107">Remarks</span></span>
<span data-ttu-id="1a98b-108">*测试表达式*计算; 如果它是`true`、*主体表达式*执行和重新计算的测试表达式。</span><span class="sxs-lookup"><span data-stu-id="1a98b-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="1a98b-109">*主体表达式*必须具有类型`unit`。</span><span class="sxs-lookup"><span data-stu-id="1a98b-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="1a98b-110">如果测试表达式为`false`，在迭代结束。</span><span class="sxs-lookup"><span data-stu-id="1a98b-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="1a98b-111">下面的示例演示如何使用`while...do`表达式。</span><span class="sxs-lookup"><span data-stu-id="1a98b-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="1a98b-112">上述代码的输出是其中的最后一个为 10 个介于 1 和 20 之间的随机数的流。</span><span class="sxs-lookup"><span data-stu-id="1a98b-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="1a98b-113">你可以使用`while...do`序列表达式和其他计算表达式，在这种情况下的自定义的版本`while...do`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="1a98b-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="1a98b-114">有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[计算表达式](computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="1a98b-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="1a98b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a98b-115">See Also</span></span>
[<span data-ttu-id="1a98b-116">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="1a98b-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="1a98b-117">循环：`for...in` 表达式</span><span class="sxs-lookup"><span data-stu-id="1a98b-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="1a98b-118">循环：`for...to` 表达式</span><span class="sxs-lookup"><span data-stu-id="1a98b-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
