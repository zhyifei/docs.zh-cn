---
title: 类型推理 (F#)
description: '了解如何 F # 编译器推断出的值、 变量、 参数和返回值的类型。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b5f7861c0a638baebfe72c9b4cf7dca119339ae3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="type-inference"></a><span data-ttu-id="0d807-103">类型推断</span><span class="sxs-lookup"><span data-stu-id="0d807-103">Type Inference</span></span>

<span data-ttu-id="0d807-104">本主题介绍如何 F # 编译器推断出的值、 变量、 参数和返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="0d807-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="0d807-105">一般情况下类型推理</span><span class="sxs-lookup"><span data-stu-id="0d807-105">Type Inference in General</span></span>
<span data-ttu-id="0d807-106">类型推理思路是不需要指定除当编译器无法最终推断类型的 F # 构造的类型。</span><span class="sxs-lookup"><span data-stu-id="0d807-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="0d807-107">省略显式类型信息并不意味着 F # 是一种动态类型化的语言或 F # 中的值为弱类型化。</span><span class="sxs-lookup"><span data-stu-id="0d807-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="0d807-108">F # 是一种静态类型化的语言，这意味着编译器会在编译期间推导为每个构造的确切类型。</span><span class="sxs-lookup"><span data-stu-id="0d807-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="0d807-109">如果没有足够的信息供编译器推导出的每个构造类型，则必须在代码中某个位置添加显式类型批注通常提供附加类型信息。</span><span class="sxs-lookup"><span data-stu-id="0d807-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>


## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="0d807-110">参数和返回类型推理</span><span class="sxs-lookup"><span data-stu-id="0d807-110">Inference of Parameter and Return Types</span></span>
<span data-ttu-id="0d807-111">在参数列表中，无需指定每个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="0d807-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="0d807-112">和尚未，F # 是一种静态类型化的语言，并因此每个值和表达式具有明确的类型在编译时。</span><span class="sxs-lookup"><span data-stu-id="0d807-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="0d807-113">对于不显式指定这些类型，编译器推断出基于上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="0d807-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="0d807-114">如果类型不是否则指定，它将被推断为泛型。</span><span class="sxs-lookup"><span data-stu-id="0d807-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="0d807-115">如果代码不一致使用一个值，在这种方式中是否有没有一推断出的类型满足所有的用法的一个值，则编译器会报告错误。</span><span class="sxs-lookup"><span data-stu-id="0d807-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="0d807-116">函数返回类型由在函数中的最后一个表达式的类型确定。</span><span class="sxs-lookup"><span data-stu-id="0d807-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="0d807-117">例如，在下面的代码中，参数类型`a`和`b`和返回类型所有推断`int`因为文本`100`属于类型`int`。</span><span class="sxs-lookup"><span data-stu-id="0d807-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="0d807-118">你可以通过更改文本影响类型推理。</span><span class="sxs-lookup"><span data-stu-id="0d807-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="0d807-119">如果你进行`100``uint32`通过追加后缀`u`，类型的`a`， `b`，并返回的值会被推断为`uint32`。</span><span class="sxs-lookup"><span data-stu-id="0d807-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="0d807-120">也会影响使用的其他隐含限制的类型，例如函数和工作通过仅将特定类型的方法的构造类型推理。</span><span class="sxs-lookup"><span data-stu-id="0d807-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="0d807-121">此外，你可以将应用显式类型批注到函数或方法参数或变量在表达式中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0d807-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="0d807-122">如果在不同的约束之间发生冲突，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="0d807-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="0d807-123">你还可显式指定函数的返回值通过提供类型批注，别忘了参数。</span><span class="sxs-lookup"><span data-stu-id="0d807-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="0d807-124">参数的对象类型，并且你想要使用的成员时常见的情况，其中类型批注是有用的参数。</span><span class="sxs-lookup"><span data-stu-id="0d807-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a><span data-ttu-id="0d807-125">自动泛化</span><span class="sxs-lookup"><span data-stu-id="0d807-125">Automatic Generalization</span></span>
<span data-ttu-id="0d807-126">如果函数代码不依赖于参数的类型，编译器将认为是通用的参数。</span><span class="sxs-lookup"><span data-stu-id="0d807-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="0d807-127">这称为*自动泛化*，这可以在不增加复杂性的情况下编写泛型代码大有帮助。</span><span class="sxs-lookup"><span data-stu-id="0d807-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="0d807-128">例如，下面的函数将合并的元组的任何类型的两个参数。</span><span class="sxs-lookup"><span data-stu-id="0d807-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="0d807-129">类型推断为</span><span class="sxs-lookup"><span data-stu-id="0d807-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="0d807-130">其他信息</span><span class="sxs-lookup"><span data-stu-id="0d807-130">Additional Information</span></span>
<span data-ttu-id="0d807-131">F # 语言规范中的更详细地描述了类型推理。</span><span class="sxs-lookup"><span data-stu-id="0d807-131">Type inference is described in more detail in the F# Language Specification.</span></span>


## <a name="see-also"></a><span data-ttu-id="0d807-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d807-132">See Also</span></span>
[<span data-ttu-id="0d807-133">自动泛化</span><span class="sxs-lookup"><span data-stu-id="0d807-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
