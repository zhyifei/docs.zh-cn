---
title: 可变类型 (F#)
description: '了解如何使用 F # 可变类型批注，这表示参数、 变量或值具有与指定的类型兼容的类型。'
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615555"
---
# <a name="flexible-types"></a><span data-ttu-id="274ea-103">可变类型</span><span class="sxs-lookup"><span data-stu-id="274ea-103">Flexible Types</span></span>

<span data-ttu-id="274ea-104">一个*可变类型批注*指示参数、 变量或值具有兼容类型的具有指定类型，其兼容性由面向对象的层次结构中的类或接口的位置。</span><span class="sxs-lookup"><span data-stu-id="274ea-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="274ea-105">可变类型非常有用，特别是，当自动转换为类型层次结构中级别更高的类型不会发生，但你仍想要启用您要使用在层次结构中的任何类型或实现接口的任何类型的功能。</span><span class="sxs-lookup"><span data-stu-id="274ea-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="274ea-106">语法</span><span class="sxs-lookup"><span data-stu-id="274ea-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="274ea-107">备注</span><span class="sxs-lookup"><span data-stu-id="274ea-107">Remarks</span></span>

<span data-ttu-id="274ea-108">在上述语法中，*类型*表示基类型或接口。</span><span class="sxs-lookup"><span data-stu-id="274ea-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="274ea-109">灵活的类型是等效的泛型类型，有一个约束，限制为与 base 或接口类型相兼容的类型允许的类型。</span><span class="sxs-lookup"><span data-stu-id="274ea-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="274ea-110">也就是说，以下两行代码是等效的。</span><span class="sxs-lookup"><span data-stu-id="274ea-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="274ea-111">可变类型是在多种类型的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="274ea-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="274ea-112">例如，如果具有更高版本的 order 函数 （采用函数作为参数的函数），通常很函数返回灵活类型很有用。</span><span class="sxs-lookup"><span data-stu-id="274ea-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="274ea-113">在下面的示例中，包含序列参数中的灵活类型使用`iterate2`使高阶函数用于生成序列、 数组、 列表和其他任何可枚举类型的函数。</span><span class="sxs-lookup"><span data-stu-id="274ea-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="274ea-114">请考虑以下两个函数，其中一个的哪些返回一个序列，这些其他返回可变类型。</span><span class="sxs-lookup"><span data-stu-id="274ea-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="274ea-115">作为另一个示例，请考虑[Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712)库函数：</span><span class="sxs-lookup"><span data-stu-id="274ea-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="274ea-116">可以将任何以下的可枚举序列传递给此函数：</span><span class="sxs-lookup"><span data-stu-id="274ea-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="274ea-117">列表的列表</span><span class="sxs-lookup"><span data-stu-id="274ea-117">A list of lists</span></span>
- <span data-ttu-id="274ea-118">数组列表</span><span class="sxs-lookup"><span data-stu-id="274ea-118">A list of arrays</span></span>
- <span data-ttu-id="274ea-119">列表的数组</span><span class="sxs-lookup"><span data-stu-id="274ea-119">An array of lists</span></span>
- <span data-ttu-id="274ea-120">序列的数组</span><span class="sxs-lookup"><span data-stu-id="274ea-120">An array of sequences</span></span>
- <span data-ttu-id="274ea-121">可枚举序列的任何其他组合</span><span class="sxs-lookup"><span data-stu-id="274ea-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="274ea-122">下面的代码使用`Seq.concat`来演示您可以通过使用可变类型支持的方案。</span><span class="sxs-lookup"><span data-stu-id="274ea-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="274ea-123">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="274ea-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="274ea-124">在 F # 中，如下所示的面向对象的其他语言中，有一些的上下文中的派生的类型或实现接口的类型自动转换为基类型或接口类型。</span><span class="sxs-lookup"><span data-stu-id="274ea-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="274ea-125">在直接自变量，但不是在该类型位于从属的位置，例如函数类型的返回类型的更复杂类型的一部分或作为类型参数时，会发生这些自动转换。</span><span class="sxs-lookup"><span data-stu-id="274ea-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="274ea-126">因此，灵活类型表示法时，主要是要将应用到的类型是更复杂类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="274ea-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="274ea-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="274ea-127">See also</span></span>

- [<span data-ttu-id="274ea-128">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="274ea-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="274ea-129">泛型</span><span class="sxs-lookup"><span data-stu-id="274ea-129">Generics</span></span>](generics/index.md)
