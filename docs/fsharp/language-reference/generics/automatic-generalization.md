---
title: 自动泛化
description: 了解如何F#自动通用化函数的自变量和类型, 以便它们可以使用多个类型。
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630623"
---
# <a name="automatic-generalization"></a><span data-ttu-id="1f9e5-103">自动泛化</span><span class="sxs-lookup"><span data-stu-id="1f9e5-103">Automatic Generalization</span></span>

<span data-ttu-id="1f9e5-104">F#使用类型推理来计算函数和表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-104">F# uses type inference to evaluate the types of functions and expressions.</span></span> <span data-ttu-id="1f9e5-105">本主题介绍如何F#自动通用化函数的自变量和类型, 以便在可能的情况下使用多个类型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-105">This topic describes how F# automatically generalizes the arguments and types of functions so that they work with multiple types when this is possible.</span></span>

## <a name="automatic-generalization"></a><span data-ttu-id="1f9e5-106">自动泛化</span><span class="sxs-lookup"><span data-stu-id="1f9e5-106">Automatic Generalization</span></span>

<span data-ttu-id="1f9e5-107">F#编译器在对函数执行类型推理时, 确定给定的参数是否可以为泛型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-107">The F# compiler, when it performs type inference on a function, determines whether a given parameter can be generic.</span></span> <span data-ttu-id="1f9e5-108">编译器检查每个参数, 并确定该函数是否依赖于该参数的特定类型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-108">The compiler examines each parameter and determines whether the function has a dependency on the specific type of that parameter.</span></span> <span data-ttu-id="1f9e5-109">如果不是, 则将类型推断为泛型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-109">If it does not, the type is inferred to be generic.</span></span>

<span data-ttu-id="1f9e5-110">下面的代码示例阐释了编译器推断为泛型的函数。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-110">The following code example illustrates a function that the compiler infers to be generic.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

<span data-ttu-id="1f9e5-111">将类型推断`'a -> 'a -> 'a`为。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-111">The type is inferred to be `'a -> 'a -> 'a`.</span></span>

<span data-ttu-id="1f9e5-112">类型指示这是一个函数, 该函数采用同一未知类型的两个参数, 并返回该类型的值。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-112">The type indicates that this is a function that takes two arguments of the same unknown type and returns a value of that same type.</span></span> <span data-ttu-id="1f9e5-113">上一个函数可以是泛型的原因之一是, 大于运算符 (`>`) 本身是泛型的。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-113">One of the reasons that the previous function can be generic is that the greater-than operator (`>`) is itself generic.</span></span> <span data-ttu-id="1f9e5-114">大于运算符具有签名`'a -> 'a -> bool`。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-114">The greater-than operator has the signature `'a -> 'a -> bool`.</span></span> <span data-ttu-id="1f9e5-115">并非所有运算符都是泛型运算符, 并且如果函数中的代码将参数类型与非泛型函数或运算符一起使用, 则不能通用化该参数类型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-115">Not all operators are generic, and if the code in a function uses a parameter type together with a non-generic function or operator, that parameter type cannot be generalized.</span></span>

<span data-ttu-id="1f9e5-116">由于`max`是泛型的, 因此它可用于类型`int`(如、 `float`等), 如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-116">Because `max` is generic, it can be used with types such as `int`, `float`, and so on, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

<span data-ttu-id="1f9e5-117">但是, 这两个参数必须属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-117">However, the two arguments must be of the same type.</span></span> <span data-ttu-id="1f9e5-118">签名为, `'a -> 'a -> 'a`而不`'a -> 'b -> 'a`是。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-118">The signature is `'a -> 'a -> 'a`, not `'a -> 'b -> 'a`.</span></span> <span data-ttu-id="1f9e5-119">因此, 以下代码将生成错误, 因为类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-119">Therefore, the following code produces an error because the types do not match.</span></span>

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

<span data-ttu-id="1f9e5-120">`max`函数还适用于支持大于运算符的任何类型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-120">The `max` function also works with any type that supports the greater-than operator.</span></span> <span data-ttu-id="1f9e5-121">因此, 您还可以对字符串使用它, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-121">Therefore, you could also use it on a string, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a><span data-ttu-id="1f9e5-122">值限制</span><span class="sxs-lookup"><span data-stu-id="1f9e5-122">Value Restriction</span></span>

<span data-ttu-id="1f9e5-123">编译器仅对具有显式自变量的完整函数定义和简单的不可变值执行自动泛化。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-123">The compiler performs automatic generalization only on complete function definitions that have explicit arguments, and on simple immutable values.</span></span>

<span data-ttu-id="1f9e5-124">这意味着, 如果您尝试编译的代码未充分约束为特定类型, 但也不能归纳, 则编译器会发出错误。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-124">This means that the compiler issues an error if you try to compile code that is not sufficiently constrained to be a specific type, but is also not generalizable.</span></span> <span data-ttu-id="1f9e5-125">此问题的错误消息将对值的自动泛化进行此限制, 以作为*值限制*。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-125">The error message for this problem refers to this restriction on automatic generalization for values as the *value restriction*.</span></span>

<span data-ttu-id="1f9e5-126">通常情况下, 如果您希望构造是泛型的, 但编译器没有足够的信息来通用化它, 或在非泛型构造中无意中省略了足够的类型信息, 则会发生值限制错误。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-126">Typically, the value restriction error occurs either when you want a construct to be generic but the compiler has insufficient information to generalize it, or when you unintentionally omit sufficient type information in a nongeneric construct.</span></span> <span data-ttu-id="1f9e5-127">值限制错误的解决方案是提供更多显式信息以通过以下方式之一来更好地约束类型推理问题:</span><span class="sxs-lookup"><span data-stu-id="1f9e5-127">The solution to the value restriction error is to provide more explicit information to more fully constrain the type inference problem, in one of the following ways:</span></span>

- <span data-ttu-id="1f9e5-128">通过将显式类型批注添加到值或参数, 将类型限制为非泛型。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-128">Constrain a type to be nongeneric by adding an explicit type annotation to a value or parameter.</span></span>

- <span data-ttu-id="1f9e5-129">如果问题是使用 nongeneralizable 构造来定义泛型函数, 例如函数组合或未完全应用的扩充函数参数, 请尝试将函数重写为普通函数定义。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-129">If the problem is using a nongeneralizable construct to define a generic function, such as a function composition or incompletely applied curried function arguments, try to rewrite the function as an ordinary function definition.</span></span>

- <span data-ttu-id="1f9e5-130">如果问题是过于复杂而无法通用化的表达式, 则通过添加额外的未使用的参数将其置于函数中。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-130">If the problem is an expression that is too complex to be generalized, make it into a function by adding an extra, unused parameter.</span></span>

- <span data-ttu-id="1f9e5-131">添加显式泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-131">Add explicit generic type parameters.</span></span> <span data-ttu-id="1f9e5-132">此选项很少使用。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-132">This option is rarely used.</span></span>

- <span data-ttu-id="1f9e5-133">下面的代码示例演示了每种情况。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-133">The following code examples illustrate each of these scenarios.</span></span>

<span data-ttu-id="1f9e5-134">案例 1:表达式太复杂。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-134">Case 1: Too complex an expression.</span></span> <span data-ttu-id="1f9e5-135">在此示例中, 此`counter`列表应`int option ref`为, 但不会将其定义为简单的不可变值。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-135">In this example, the list `counter` is intended to be `int option ref`, but it is not defined as a simple immutable value.</span></span>

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

<span data-ttu-id="1f9e5-136">案例 2:使用 nongeneralizable 构造定义泛型函数。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-136">Case 2: Using a nongeneralizable construct to define a generic function.</span></span> <span data-ttu-id="1f9e5-137">在此示例中, 构造是 nongeneralizable 的, 因为它涉及函数参数的部分应用。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-137">In this example, the construct is nongeneralizable because it involves partial application of function arguments.</span></span>

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

<span data-ttu-id="1f9e5-138">案例 3:添加多余的未使用参数。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-138">Case 3: Adding an extra, unused parameter.</span></span> <span data-ttu-id="1f9e5-139">由于此表达式对于通用化而言不够简单, 因此编译器会发出值限制错误。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-139">Because this expression is not simple enough for generalization, the compiler issues the value restriction error.</span></span>

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

<span data-ttu-id="1f9e5-140">情况 4:添加类型参数。</span><span class="sxs-lookup"><span data-stu-id="1f9e5-140">Case 4: Adding type parameters.</span></span>

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

<span data-ttu-id="1f9e5-141">在最后一种情况下, 值变成类型函数, 可用于创建许多不同类型的值, 例如:</span><span class="sxs-lookup"><span data-stu-id="1f9e5-141">In the last case, the value becomes a type function, which may be used to create values of many different types, for example as follows:</span></span>

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a><span data-ttu-id="1f9e5-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f9e5-142">See also</span></span>

- [<span data-ttu-id="1f9e5-143">类型推断</span><span class="sxs-lookup"><span data-stu-id="1f9e5-143">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="1f9e5-144">泛型</span><span class="sxs-lookup"><span data-stu-id="1f9e5-144">Generics</span></span>](index.md)
- [<span data-ttu-id="1f9e5-145">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="1f9e5-145">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)
- [<span data-ttu-id="1f9e5-146">约束</span><span class="sxs-lookup"><span data-stu-id="1f9e5-146">Constraints</span></span>](constraints.md)
