---
title: unit 类型
description: 了解F# "unit" 类型如何经常用于在无需任何值或需要任何值时保存语言语法需要值的位置。
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424030"
---
# <a name="unit-type"></a><span data-ttu-id="8a226-103">unit 类型</span><span class="sxs-lookup"><span data-stu-id="8a226-103">Unit Type</span></span>

<span data-ttu-id="8a226-104">`unit` 类型是指示缺少特定值的类型;`unit` 类型仅包含一个值，该值在不存在任何其他值或需要时充当占位符。</span><span class="sxs-lookup"><span data-stu-id="8a226-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a226-105">语法</span><span class="sxs-lookup"><span data-stu-id="8a226-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="8a226-106">备注</span><span class="sxs-lookup"><span data-stu-id="8a226-106">Remarks</span></span>

<span data-ttu-id="8a226-107">每F#个表达式的计算结果都必须为值。</span><span class="sxs-lookup"><span data-stu-id="8a226-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="8a226-108">对于不生成相关值的表达式，将使用 `unit` 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8a226-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="8a226-109">`unit` 类型类似于C#和C++之类的语言 `void` 类型。</span><span class="sxs-lookup"><span data-stu-id="8a226-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="8a226-110">`unit` 类型具有单个值，并且该值由标记 `()`指示。</span><span class="sxs-lookup"><span data-stu-id="8a226-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="8a226-111">`unit` 类型的值通常用在编程中F# ，用于保存语言语法需要值的位置，但不需要或不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="8a226-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="8a226-112">一个示例可能是 `printf` 函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="8a226-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="8a226-113">由于函数中发生了 `printf` 操作的重要操作，因此该函数不必返回实际值。</span><span class="sxs-lookup"><span data-stu-id="8a226-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="8a226-114">因此，返回值的类型为 `unit`。</span><span class="sxs-lookup"><span data-stu-id="8a226-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="8a226-115">某些构造需要 `unit` 值。</span><span class="sxs-lookup"><span data-stu-id="8a226-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="8a226-116">例如，在模块的顶级 `do` 绑定或任何代码的计算结果应为 `unit` 值。</span><span class="sxs-lookup"><span data-stu-id="8a226-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="8a226-117">当某个模块的顶级 `do` 绑定或代码产生的结果不是未使用的 `unit` 值时，编译器将报告警告，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="8a226-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="8a226-118">此警告是函数编程的一个特性;它不会显示在其他 .NET 编程语言中。</span><span class="sxs-lookup"><span data-stu-id="8a226-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="8a226-119">在纯粹的函数中，函数没有任何副作用，最终返回值是函数调用的唯一结果。</span><span class="sxs-lookup"><span data-stu-id="8a226-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="8a226-120">因此，如果忽略结果，则可能是编程错误。</span><span class="sxs-lookup"><span data-stu-id="8a226-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="8a226-121">尽管F#不是纯粹的函数编程语言，但最好尽可能遵循函数编程样式。</span><span class="sxs-lookup"><span data-stu-id="8a226-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a226-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a226-122">See also</span></span>

- [<span data-ttu-id="8a226-123">基本</span><span class="sxs-lookup"><span data-stu-id="8a226-123">Primitive</span></span>](basic-types.md)
- [<span data-ttu-id="8a226-124">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="8a226-124">F# Language Reference</span></span>](index.md)
