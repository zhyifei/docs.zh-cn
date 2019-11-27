---
title: 循环：for...to 表达式
description: F#请参阅to expression 用于在循环变量的一系列值中循环访问循环。
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283907"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="cf748-103">循环：for...to 表达式</span><span class="sxs-lookup"><span data-stu-id="cf748-103">Loops: for...to Expression</span></span>

<span data-ttu-id="cf748-104">`for...to` 表达式用于在循环变量的一系列值上循环访问循环。</span><span class="sxs-lookup"><span data-stu-id="cf748-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf748-105">语法</span><span class="sxs-lookup"><span data-stu-id="cf748-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="cf748-106">备注</span><span class="sxs-lookup"><span data-stu-id="cf748-106">Remarks</span></span>

<span data-ttu-id="cf748-107">标识符的类型从*开始*和*结束*表达式的类型推断而来。</span><span class="sxs-lookup"><span data-stu-id="cf748-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="cf748-108">这些表达式的类型必须是32位整数。</span><span class="sxs-lookup"><span data-stu-id="cf748-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="cf748-109">尽管从技术上讲，`for...to` 更像是命令式编程语言中的传统语句。</span><span class="sxs-lookup"><span data-stu-id="cf748-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="cf748-110">*主体表达式*的返回类型必须是 `unit`。</span><span class="sxs-lookup"><span data-stu-id="cf748-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="cf748-111">下面的示例演示 `for...to` 表达式的各种用法。</span><span class="sxs-lookup"><span data-stu-id="cf748-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="cf748-112">上述代码的输出结果如下。</span><span class="sxs-lookup"><span data-stu-id="cf748-112">The output of the previous code is as follows.</span></span>

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="cf748-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf748-113">See also</span></span>

- [<span data-ttu-id="cf748-114">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="cf748-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="cf748-115">循环：`for...in` 表达式</span><span class="sxs-lookup"><span data-stu-id="cf748-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="cf748-116">循环：`while...do` 表达式</span><span class="sxs-lookup"><span data-stu-id="cf748-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
