---
title: 循环：while...do 表达式 (F#)
description: 请参阅如何时...是否会使用表达式来指定的测试条件为 true 时执行迭代执行 （循环）。
ms.date: 05/16/2016
ms.openlocfilehash: e3198246e44bbb11b226f04da6795f3da22626e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562227"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="b1d38-103">循环：while...do 表达式</span><span class="sxs-lookup"><span data-stu-id="b1d38-103">Loops: while...do Expression</span></span>

<span data-ttu-id="b1d38-104">`while...do`会使用表达式来指定的测试条件为 true 时执行迭代执行 （循环）。</span><span class="sxs-lookup"><span data-stu-id="b1d38-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="b1d38-105">语法</span><span class="sxs-lookup"><span data-stu-id="b1d38-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="b1d38-106">备注</span><span class="sxs-lookup"><span data-stu-id="b1d38-106">Remarks</span></span>
<span data-ttu-id="b1d38-107">*测试表达式*计算; 如果它是`true`、*主体表达式*执行和重新计算的测试表达式。</span><span class="sxs-lookup"><span data-stu-id="b1d38-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="b1d38-108">*主体表达式*必须具有类型`unit`。</span><span class="sxs-lookup"><span data-stu-id="b1d38-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="b1d38-109">如果测试表达式为`false`，在迭代结束。</span><span class="sxs-lookup"><span data-stu-id="b1d38-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="b1d38-110">下面的示例演示如何使用`while...do`表达式。</span><span class="sxs-lookup"><span data-stu-id="b1d38-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="b1d38-111">上述代码的输出是其中的最后一个为 10 个介于 1 和 20 之间的随机数的流。</span><span class="sxs-lookup"><span data-stu-id="b1d38-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="b1d38-112">你可以使用`while...do`序列表达式和其他计算表达式，在这种情况下的自定义的版本`while...do`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="b1d38-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="b1d38-113">有关详细信息，请参阅[序列](sequences.md)，[异步工作流](asynchronous-workflows.md)，和[计算表达式](computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="b1d38-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="b1d38-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1d38-114">See Also</span></span>
[<span data-ttu-id="b1d38-115">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b1d38-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b1d38-116">循环：`for...in` 表达式</span><span class="sxs-lookup"><span data-stu-id="b1d38-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="b1d38-117">循环：`for...to` 表达式</span><span class="sxs-lookup"><span data-stu-id="b1d38-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
