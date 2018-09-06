---
title: 自动泛化 (F#)
description: '了解如何 F # 自动泛化的参数和类型的函数，以便它们适用于多个类型在可能的情况。'
ms.date: 05/16/2016
ms.openlocfilehash: 84de9cbb2b9fcf2488393f7dbdfc3b610cdcffb0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855772"
---
# <a name="automatic-generalization"></a><span data-ttu-id="ef854-103">自动泛化</span><span class="sxs-lookup"><span data-stu-id="ef854-103">Automatic Generalization</span></span>

<span data-ttu-id="ef854-104">F # 使用类型推理来评估函数和表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="ef854-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="ef854-105">本主题介绍如何 F # 自动泛化的参数和类型的函数，使它们工作的多个类型时做到这一点。</span><span class="sxs-lookup"><span data-stu-id="ef854-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="ef854-106">自动泛化</span><span class="sxs-lookup"><span data-stu-id="ef854-106">Automatic Generalization</span></span>

<span data-ttu-id="ef854-107">F # 编译器，它执行上一个函数，类型推理时确定是否为给定的参数可以为泛型。</span><span class="sxs-lookup"><span data-stu-id="ef854-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="ef854-108">编译器检查每个参数，并确定该函数是否具有该参数的特定类型的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="ef854-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="ef854-109">如果未显示，类型推断为泛型。</span><span class="sxs-lookup"><span data-stu-id="ef854-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="ef854-110">下面的代码示例演示编译器将推断是通用的函数。</span><span class="sxs-lookup"><span data-stu-id="ef854-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="ef854-111">类型被推断为`'a -> 'a -> 'a`。</span><span class="sxs-lookup"><span data-stu-id="ef854-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="ef854-112">该类型指示这是采用相同的未知类型的两个参数并返回相同类型的值的函数。</span><span class="sxs-lookup"><span data-stu-id="ef854-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="ef854-113">可以是上一个函数的原因之一泛型是： 大于-运算符 (`>`) 本身是泛型。</span><span class="sxs-lookup"><span data-stu-id="ef854-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="ef854-114">更高版本-不是运算符具有签名`'a -> 'a -> bool`。</span><span class="sxs-lookup"><span data-stu-id="ef854-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="ef854-115">并非所有运算符都是泛型，并在函数中的代码使用与非泛型函数或运算符的参数类型，如果该参数类型不能使用通用。</span><span class="sxs-lookup"><span data-stu-id="ef854-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="ef854-116">因为`max`是泛型类型，它可用于类型如`int`， `float`，依此类推，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ef854-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="ef854-117">但是，两个参数必须属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="ef854-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="ef854-118">该签名是`'a -> 'a -> 'a`，而不`'a -> 'b -> 'a`。</span><span class="sxs-lookup"><span data-stu-id="ef854-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="ef854-119">因此，下面的代码生成错误，因为类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="ef854-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="ef854-120">`max`函数也可用于支持较大的任何类型的运算符。</span><span class="sxs-lookup"><span data-stu-id="ef854-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="ef854-121">因此，你无法使用它在一个字符串，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="ef854-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="ef854-122">值限制</span><span class="sxs-lookup"><span data-stu-id="ef854-122">Value Restriction</span></span>

<span data-ttu-id="ef854-123">编译器会执行自动泛化仅在具有显式参数的完整函数定义和简单的不可变值。</span><span class="sxs-lookup"><span data-stu-id="ef854-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="ef854-124">这意味着编译器发出错误，如果您尝试编译代码未充分约束为特定的类型，但也不是可归纳。</span><span class="sxs-lookup"><span data-stu-id="ef854-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="ef854-125">此问题的错误消息是指此限制的值作为自动泛化*值限制*。</span><span class="sxs-lookup"><span data-stu-id="ef854-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="ef854-126">通常情况下，值限制错误发生时所需的构造是通用，但编译器没有足够的信息进行通用化处理，或在无意中省略足够在非泛型构造函数中的类型信息时。</span><span class="sxs-lookup"><span data-stu-id="ef854-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="ef854-127">值限制错误的解决方案是提供更明确的信息，以更全面地约束类型推理问题，通过以下方式之一：</span><span class="sxs-lookup"><span data-stu-id="ef854-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="ef854-128">将通过将显式类型批注添加到值或参数为非泛型类型约束。</span><span class="sxs-lookup"><span data-stu-id="ef854-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="ef854-129">如果使用问题不可泛化构造来定义如函数组合或不完整的泛型函数应用的扩充的函数自变量，请尝试重写为普通函数定义的函数。</span><span class="sxs-lookup"><span data-stu-id="ef854-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="ef854-130">如果问题是太复杂，无法进行一般化，通过添加额外的未使用参数来使到函数的表达式。</span><span class="sxs-lookup"><span data-stu-id="ef854-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="ef854-131">添加显式泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="ef854-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="ef854-132">很少使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ef854-132">This option is rarely used.</span></span>

- <span data-ttu-id="ef854-133">下面的代码示例说明了每种方案。</span><span class="sxs-lookup"><span data-stu-id="ef854-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="ef854-134">案例 1： 太复杂的表达式。</span><span class="sxs-lookup"><span data-stu-id="ef854-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="ef854-135">在此示例中，列表`counter`用于`int option ref`，但它不定义为一个简单的不可变值。</span><span class="sxs-lookup"><span data-stu-id="ef854-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="ef854-136">案例 2： 使用不可泛化构造定义的泛型函数。</span><span class="sxs-lookup"><span data-stu-id="ef854-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="ef854-137">在此示例中，构造是不可泛化，因为它涉及到部分应用函数自变量。</span><span class="sxs-lookup"><span data-stu-id="ef854-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="ef854-138">案例 3： 添加一个额外的、 未使用的参数。</span><span class="sxs-lookup"><span data-stu-id="ef854-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="ef854-139">此表达式不是简单的泛化，因为编译器会发出值限制错误。</span><span class="sxs-lookup"><span data-stu-id="ef854-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="ef854-140">情形 4： 添加的类型参数。</span><span class="sxs-lookup"><span data-stu-id="ef854-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="ef854-141">在最后一种情况下，值将成为类型函数，可用于创建许多不同类型的值为例，如下：</span><span class="sxs-lookup"><span data-stu-id="ef854-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="ef854-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef854-142">See also</span></span>

- [<span data-ttu-id="ef854-143">类型推断</span><span class="sxs-lookup"><span data-stu-id="ef854-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="ef854-144">泛型</span><span class="sxs-lookup"><span data-stu-id="ef854-144">Generics</span></span>](index.md)
- [<span data-ttu-id="ef854-145">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="ef854-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="ef854-146">约束</span><span class="sxs-lookup"><span data-stu-id="ef854-146">Constraints</span></span>](constraints.md)
