---
title: "自动泛化 (F#)"
description: "了解如何 F # 自动泛化的自变量和类型的函数，使它们工作的多个类型在可能的情况。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 14a3554c-3fad-4eba-a93d-8ba07d1245b4
ms.openlocfilehash: d60831084cef76ce29f64322362b4920520f71d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-generalization"></a><span data-ttu-id="62294-104">自动泛化</span><span class="sxs-lookup"><span data-stu-id="62294-104">Automatic Generalization</span></span>

<span data-ttu-id="62294-105">F # 使用类型推理来评估现有的函数和表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="62294-105">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="62294-106">本主题介绍如何 F # 自动泛化的自变量和类型的函数，使它们可以将其工作的多个类型时这是可行的。</span><span class="sxs-lookup"><span data-stu-id="62294-106">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>


## <a name="automatic-generalization"></a><span data-ttu-id="62294-107">自动泛化</span><span class="sxs-lookup"><span data-stu-id="62294-107">Automatic Generalization</span></span>
<span data-ttu-id="62294-108">F # 编译器上一个函数，, 执行类型推理时确定的给定的参数是否可以为泛型。</span><span class="sxs-lookup"><span data-stu-id="62294-108">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="62294-109">编译器将检查每个参数，并确定该函数是否具有该参数的特定类型的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="62294-109">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="62294-110">如果不存在，推断的类型为泛型。</span><span class="sxs-lookup"><span data-stu-id="62294-110">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="62294-111">下面的代码示例阐释了编译器推断出是通用的函数。</span><span class="sxs-lookup"><span data-stu-id="62294-111">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="62294-112">类型将被推断`'a -> 'a -> 'a`。</span><span class="sxs-lookup"><span data-stu-id="62294-112">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="62294-113">该类型指示这是一个函数，它采用相同的未知类型的两个参数并返回该同一类型的值。</span><span class="sxs-lookup"><span data-stu-id="62294-113">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="62294-114">以前的函数可以是原因之一而泛型是： 大于-运算符 (`>`) 本身是泛型。</span><span class="sxs-lookup"><span data-stu-id="62294-114">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="62294-115">较大的-不是运算符具有签名`'a -> 'a -> bool`。</span><span class="sxs-lookup"><span data-stu-id="62294-115">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="62294-116">并非所有运算符都是泛型，并且如果在函数中的代码使用与非泛型函数或运算符的参数类型，该参数类型不能通用。</span><span class="sxs-lookup"><span data-stu-id="62294-116">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="62294-117">因为`max`是泛型，它可与类型如`int`， `float`，依此类推，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="62294-117">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="62294-118">但是，两个自变量必须是类型的相同。</span><span class="sxs-lookup"><span data-stu-id="62294-118">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="62294-119">该签名是`'a -> 'a -> 'a`，而不`'a -> 'b -> 'a`。</span><span class="sxs-lookup"><span data-stu-id="62294-119">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="62294-120">因此，下面的代码产生一个错误，因为类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="62294-120">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="62294-121">`max`函数也适用于支持大于任何类型的运算符。</span><span class="sxs-lookup"><span data-stu-id="62294-121">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="62294-122">因此，你可能还上使用它一个字符串，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="62294-122">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a><span data-ttu-id="62294-123">值限制</span><span class="sxs-lookup"><span data-stu-id="62294-123">Value Restriction</span></span>
<span data-ttu-id="62294-124">编译器执行自动泛化，只能在具有显式参数的完整函数定义上和简单不可变的值。</span><span class="sxs-lookup"><span data-stu-id="62294-124">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="62294-125">这意味着，编译器将发出错误，如果您尝试编译未充分约束为特定类型，但也不可泛化的代码。</span><span class="sxs-lookup"><span data-stu-id="62294-125">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="62294-126">此问题的错误消息是指此限制的值作为自动泛化*值限制*。</span><span class="sxs-lookup"><span data-stu-id="62294-126">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="62294-127">通常，当你想构造来为泛型，但编译器没有足够的信息来通用化，或者当你无意中忽略足够非泛型构造中的类型信息时，会发生值限制错误。</span><span class="sxs-lookup"><span data-stu-id="62294-127">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="62294-128">值限制错误的解决方案是提供更明确的信息，以便更全面地约束类型推理问题，通过以下方式之一：</span><span class="sxs-lookup"><span data-stu-id="62294-128">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>


- <span data-ttu-id="62294-129">限制要通过将显式类型批注添加到的值或参数非泛型的类型。</span><span class="sxs-lookup"><span data-stu-id="62294-129">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="62294-130">如果问题使用不可泛化构造来定义泛型功能，例如函数组合或未完整应用的扩充的函数自变量，请尝试重写为普通函数定义的函数。</span><span class="sxs-lookup"><span data-stu-id="62294-130">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="62294-131">如果问题是太复杂，无法泛化，使它成为函数通过添加额外的未使用参数的表达式。</span><span class="sxs-lookup"><span data-stu-id="62294-131">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="62294-132">添加显式的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="62294-132">Add explicit generic type parameters.</span></span> <span data-ttu-id="62294-133">很少使用此选项。</span><span class="sxs-lookup"><span data-stu-id="62294-133">This option is rarely used.</span></span>

- <span data-ttu-id="62294-134">下面的代码示例说明了每种方案。</span><span class="sxs-lookup"><span data-stu-id="62294-134">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="62294-135">案例 1： 太复杂的表达式。</span><span class="sxs-lookup"><span data-stu-id="62294-135">Case 1: Too complex an expression.</span></span> <span data-ttu-id="62294-136">在此示例中，列表`counter`旨在`int option ref`，但它未定义为一个简单的不可变值。</span><span class="sxs-lookup"><span data-stu-id="62294-136">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="62294-137">案例 2： 使用不可泛化构造来定义的泛型函数。</span><span class="sxs-lookup"><span data-stu-id="62294-137">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="62294-138">在此示例中，则构造是不可泛化，因为它涉及部分应用函数自变量。</span><span class="sxs-lookup"><span data-stu-id="62294-138">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="62294-139">情况 3： 添加额外的未使用参数。</span><span class="sxs-lookup"><span data-stu-id="62294-139">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="62294-140">此表达式不是简单的泛化，因为编译器会发出值限制错误。</span><span class="sxs-lookup"><span data-stu-id="62294-140">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="62294-141">案例 4： 添加的类型参数。</span><span class="sxs-lookup"><span data-stu-id="62294-141">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="62294-142">在最后一种情况中的值将成为类型函数，可用于创建例如在如下所示的许多不同类型，值：</span><span class="sxs-lookup"><span data-stu-id="62294-142">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="62294-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62294-143">See Also</span></span>
[<span data-ttu-id="62294-144">类型推断</span><span class="sxs-lookup"><span data-stu-id="62294-144">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="62294-145">泛型</span><span class="sxs-lookup"><span data-stu-id="62294-145">Generics</span></span>](index.md)

[<span data-ttu-id="62294-146">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="62294-146">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)

[<span data-ttu-id="62294-147">约束</span><span class="sxs-lookup"><span data-stu-id="62294-147">Constraints</span></span>](constraints.md)

