---
title: 可变类型
description: 了解如何使用F#可变类型批注，该批注指示参数、变量或值具有与指定类型兼容的类型。
ms.date: 05/16/2016
ms.openlocfilehash: bf05f78f163d1f9c73c667df60925b66a5315627
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083063"
---
# <a name="flexible-types"></a><span data-ttu-id="f109b-103">可变类型</span><span class="sxs-lookup"><span data-stu-id="f109b-103">Flexible Types</span></span>

<span data-ttu-id="f109b-104">*可变类型批注*指示参数、变量或值具有与指定类型兼容的类型，其中的兼容性由类或接口的面向对象的层次结构中的位置确定。</span><span class="sxs-lookup"><span data-stu-id="f109b-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="f109b-105">当不发生类型层次结构中较高的类型的自动转换但仍希望使你的功能可以与层次结构中的任何类型或实现接口的任何类型一起使用时，灵活类型特别有用。</span><span class="sxs-lookup"><span data-stu-id="f109b-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="f109b-106">语法</span><span class="sxs-lookup"><span data-stu-id="f109b-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="f109b-107">备注</span><span class="sxs-lookup"><span data-stu-id="f109b-107">Remarks</span></span>

<span data-ttu-id="f109b-108">在前面的语法中，*类型*表示基类型或接口。</span><span class="sxs-lookup"><span data-stu-id="f109b-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="f109b-109">灵活类型等效于具有约束的泛型类型，该约束将允许的类型限制为与基类型或接口类型兼容的类型。</span><span class="sxs-lookup"><span data-stu-id="f109b-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="f109b-110">也就是说，以下两行代码是等效的。</span><span class="sxs-lookup"><span data-stu-id="f109b-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="f109b-111">灵活类型在多种情况下都很有用。</span><span class="sxs-lookup"><span data-stu-id="f109b-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="f109b-112">例如，如果您具有高阶函数（采用函数作为参数的函数），则使函数返回灵活类型通常很有用。</span><span class="sxs-lookup"><span data-stu-id="f109b-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="f109b-113">在下面的示例中，在中`iterate2`使用带序列参数的灵活类型使高阶函数能够使用生成序列、数组、列表和任何其他可枚举类型的函数。</span><span class="sxs-lookup"><span data-stu-id="f109b-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="f109b-114">请考虑以下两个函数，其中一个函数返回一个序列，另一个返回一个可变类型。</span><span class="sxs-lookup"><span data-stu-id="f109b-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="f109b-115">作为另一个示例，请考虑[Seq](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library 函数：</span><span class="sxs-lookup"><span data-stu-id="f109b-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="f109b-116">可以将以下任一可枚举序列传递到此函数：</span><span class="sxs-lookup"><span data-stu-id="f109b-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="f109b-117">列表列表</span><span class="sxs-lookup"><span data-stu-id="f109b-117">A list of lists</span></span>
- <span data-ttu-id="f109b-118">数组的列表</span><span class="sxs-lookup"><span data-stu-id="f109b-118">A list of arrays</span></span>
- <span data-ttu-id="f109b-119">列表的数组</span><span class="sxs-lookup"><span data-stu-id="f109b-119">An array of lists</span></span>
- <span data-ttu-id="f109b-120">序列数组</span><span class="sxs-lookup"><span data-stu-id="f109b-120">An array of sequences</span></span>
- <span data-ttu-id="f109b-121">可枚举序列的任何其他组合</span><span class="sxs-lookup"><span data-stu-id="f109b-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="f109b-122">下面的代码使用`Seq.concat`灵活的类型来演示可支持的方案。</span><span class="sxs-lookup"><span data-stu-id="f109b-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="f109b-123">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="f109b-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="f109b-124">在F#中，与在其他面向对象的语言中一样，某些上下文中实现接口的派生类型或类型会自动转换为基类型或接口类型。</span><span class="sxs-lookup"><span data-stu-id="f109b-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="f109b-125">这些自动转换在直接参数中进行，但当类型位于从属位置时，不会发生在作为更复杂类型（如函数类型的返回类型）或类型参数的一部分的情况下。</span><span class="sxs-lookup"><span data-stu-id="f109b-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="f109b-126">因此，当您要将它应用到的类型是更复杂类型的一部分时，灵活的类型表示法主要非常有用。</span><span class="sxs-lookup"><span data-stu-id="f109b-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="f109b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="f109b-127">See also</span></span>

- [<span data-ttu-id="f109b-128">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f109b-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f109b-129">泛型</span><span class="sxs-lookup"><span data-stu-id="f109b-129">Generics</span></span>](./generics/index.md)
