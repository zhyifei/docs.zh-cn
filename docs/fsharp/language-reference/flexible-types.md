---
title: 可变类型 (F#)
description: '了解如何使用 F # 灵活类型批注，这表示参数、 变量或值具有与指定的类型兼容的类型。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bee2364a6c30b1fbdc09aa0aac2249e3f0c295e8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="flexible-types"></a><span data-ttu-id="bf04b-103">可变类型</span><span class="sxs-lookup"><span data-stu-id="bf04b-103">Flexible Types</span></span>

<span data-ttu-id="bf04b-104">A*灵活类型批注*指示参数、 变量或值具有兼容类型使用指定的类型，兼容性由面向对象的层次结构中的类或接口的位置。</span><span class="sxs-lookup"><span data-stu-id="bf04b-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="bf04b-105">灵活的类型很有用，特别是，当自动转换为的类型层次结构中较高的类型不会发生，但你仍想要启用你要使用层次结构中的任何类型或实现接口的任何类型的功能。</span><span class="sxs-lookup"><span data-stu-id="bf04b-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf04b-106">语法</span><span class="sxs-lookup"><span data-stu-id="bf04b-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="bf04b-107">备注</span><span class="sxs-lookup"><span data-stu-id="bf04b-107">Remarks</span></span>

<span data-ttu-id="bf04b-108">在上述语法中，*类型*表示基类型或接口。</span><span class="sxs-lookup"><span data-stu-id="bf04b-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="bf04b-109">可变类型等效于具有限制到与基或接口类型相兼容的类型允许的类型的约束的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="bf04b-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="bf04b-110">也就是说，以下两行代码是等效的。</span><span class="sxs-lookup"><span data-stu-id="bf04b-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="bf04b-111">可变类型是几种类型的情况下有用。</span><span class="sxs-lookup"><span data-stu-id="bf04b-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="bf04b-112">例如，如果必须高阶函数 （采用一个函数作为自变量的函数），很有用具有函数返回可变类型。</span><span class="sxs-lookup"><span data-stu-id="bf04b-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="bf04b-113">在下面的示例中，带中的序列参数的灵活类型使用`iterate2`使更高版本的高阶函数，若要使用生成序列、 数组、 列表和任何其他可枚举类型的函数。</span><span class="sxs-lookup"><span data-stu-id="bf04b-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="bf04b-114">请考虑以下两项功能，其中一个的它将返回一个序列，其中其他返回可变类型。</span><span class="sxs-lookup"><span data-stu-id="bf04b-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="bf04b-115">作为另一个示例，请考虑[Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712)库函数：</span><span class="sxs-lookup"><span data-stu-id="bf04b-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="bf04b-116">可以将任何以下的可枚举序列传递给此函数：</span><span class="sxs-lookup"><span data-stu-id="bf04b-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="bf04b-117">列表的列表</span><span class="sxs-lookup"><span data-stu-id="bf04b-117">A list of lists</span></span>
- <span data-ttu-id="bf04b-118">阵列的列表</span><span class="sxs-lookup"><span data-stu-id="bf04b-118">A list of arrays</span></span>
- <span data-ttu-id="bf04b-119">列表的数组</span><span class="sxs-lookup"><span data-stu-id="bf04b-119">An array of lists</span></span>
- <span data-ttu-id="bf04b-120">序列的数组</span><span class="sxs-lookup"><span data-stu-id="bf04b-120">An array of sequences</span></span>
- <span data-ttu-id="bf04b-121">可枚举的序列的任何其他组合</span><span class="sxs-lookup"><span data-stu-id="bf04b-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="bf04b-122">下面的代码使用`Seq.concat`演示您可以通过使用可变类型支持的方案。</span><span class="sxs-lookup"><span data-stu-id="bf04b-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="bf04b-123">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="bf04b-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="bf04b-124">在 F # 中，如下所示其他面向对象的语言，有在其中派生的类型或实现接口的类型自动转换为基类型或接口类型的上下文。</span><span class="sxs-lookup"><span data-stu-id="bf04b-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="bf04b-125">在直接自变量，但不是在该类型位于作为一个更复杂的类型，例如函数类型，返回类型的一部分或作为类型参数的从属位置时，会发生这些自动转换。</span><span class="sxs-lookup"><span data-stu-id="bf04b-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="bf04b-126">因此，灵活类型表示法是主要适用，当你要将应用到的类型是更复杂类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf04b-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf04b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf04b-127">See Also</span></span>

[<span data-ttu-id="bf04b-128">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="bf04b-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="bf04b-129">泛型</span><span class="sxs-lookup"><span data-stu-id="bf04b-129">Generics</span></span>](generics/index.md)
