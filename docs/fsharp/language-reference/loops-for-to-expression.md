---
title: "循环：for...to 表达式 (F#)"
description: "请参阅如何 F # 为..表达式用于在循环中循环访问一系列的循环变量的值。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forto-expression"></a><span data-ttu-id="8e49a-104">循环：for...to 表达式</span><span class="sxs-lookup"><span data-stu-id="8e49a-104">Loops: for...to Expression</span></span>

<span data-ttu-id="8e49a-105">`for...to`表达式用于在循环中循环访问一系列的循环变量的值。</span><span class="sxs-lookup"><span data-stu-id="8e49a-105">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="8e49a-106">语法</span><span class="sxs-lookup"><span data-stu-id="8e49a-106">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="8e49a-107">备注</span><span class="sxs-lookup"><span data-stu-id="8e49a-107">Remarks</span></span>
<span data-ttu-id="8e49a-108">标识符的类型推断的一种从*启动*和*完成*表达式。</span><span class="sxs-lookup"><span data-stu-id="8e49a-108">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="8e49a-109">这些表达式的类型必须是 32 位整数。</span><span class="sxs-lookup"><span data-stu-id="8e49a-109">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="8e49a-110">尽管从技术上讲的表达式，`for...to`是更像在命令性编程语言中的传统语句。</span><span class="sxs-lookup"><span data-stu-id="8e49a-110">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="8e49a-111">返回类型*主体表达式*必须`unit`。</span><span class="sxs-lookup"><span data-stu-id="8e49a-111">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="8e49a-112">下面的示例演示的各种用法`for...to`表达式。</span><span class="sxs-lookup"><span data-stu-id="8e49a-112">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="8e49a-113">上述代码的输出结果如下。</span><span class="sxs-lookup"><span data-stu-id="8e49a-113">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="8e49a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e49a-114">See Also</span></span>
[<span data-ttu-id="8e49a-115">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="8e49a-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8e49a-116">循环：`for...in` 表达式</span><span class="sxs-lookup"><span data-stu-id="8e49a-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="8e49a-117">循环：`while...do` 表达式</span><span class="sxs-lookup"><span data-stu-id="8e49a-117">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
