---
title: 类型推断
description: 了解如何F#编译器推断类型的值、 变量、 参数和返回值。
ms.date: 05/16/2016
ms.openlocfilehash: 3e61d5c81fde0a48af66a47745123a842dc04cb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666230"
---
# <a name="type-inference"></a><span data-ttu-id="2cfa2-103">类型推断</span><span class="sxs-lookup"><span data-stu-id="2cfa2-103">Type Inference</span></span>

<span data-ttu-id="2cfa2-104">本主题介绍如何将F#编译器推断类型的值、 变量、 参数和返回值。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="2cfa2-105">一般情况下，类型推理</span><span class="sxs-lookup"><span data-stu-id="2cfa2-105">Type Inference in General</span></span>

<span data-ttu-id="2cfa2-106">类型推理的理念是，不需要指定类型的F#除时，编译器无法最终推断类型的构造。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="2cfa2-107">省略显式类型信息并不意味着F#是动态类型化的语言或中的值F#是弱类型化。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="2cfa2-108">F#是静态类型化的语言，这意味着编译器将在编译期间推导为每个构造的确切类型。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="2cfa2-109">如果没有足够的信息供编译器推导出的每个构造的类型，则必须在代码中某个位置添加明确的类型注释通常提供附加类型信息。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="2cfa2-110">参数和返回类型推理</span><span class="sxs-lookup"><span data-stu-id="2cfa2-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="2cfa2-111">在参数列表中，无需指定每个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="2cfa2-112">并且，F#是一种静态类型化的语言，并因此的每个值和表达式具有明确的类型在编译时。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="2cfa2-113">对于不显式指定这些类型，编译器将推断基于上下文的类型。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="2cfa2-114">如果类型不是以其他方式指定，它被推断为泛型。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="2cfa2-115">如果代码使用一个值不一致，这样一种方式中是否有没有一推断满足的一个值，所有使用编译器会报告错误的类型。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="2cfa2-116">一个函数的返回类型取决于在函数中的最后一个表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="2cfa2-117">例如，在下面的代码中，参数类型`a`并`b`以及所有推断为返回类型`int`因为文本`100`属于类型`int`。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="2cfa2-118">您可以通过更改文本影响类型推理。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="2cfa2-119">如果进行`100``uint32`通过追加后缀`u`，类型的`a`， `b`，并返回值会被推断为`uint32`。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="2cfa2-120">也可以影响使用隐含的类型，如函数和方法适用于特定类型的限制的其他构造类型推理。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="2cfa2-121">此外，您可以应用显式类型批注函数或方法参数或变量在表达式中，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="2cfa2-122">不同的约束之间发生冲突时，将导致错误。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="2cfa2-123">通过提供类型批注所有参数，可以显式指定函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="2cfa2-124">类型批注的参数非常有用的常见情况是当该参数是一个对象类型，你想要使用成员。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="2cfa2-125">自动泛化</span><span class="sxs-lookup"><span data-stu-id="2cfa2-125">Automatic Generalization</span></span>

<span data-ttu-id="2cfa2-126">如果函数代码并不依赖参数的类型，编译器会考虑要为泛型的参数。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="2cfa2-127">这称为*自动泛化*，它可以是编写泛型代码，且不会增加复杂性大有帮助。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="2cfa2-128">例如，以下函数将任何类型的元组的两个参数组合。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="2cfa2-129">推断的类型为</span><span class="sxs-lookup"><span data-stu-id="2cfa2-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="2cfa2-130">其他信息</span><span class="sxs-lookup"><span data-stu-id="2cfa2-130">Additional Information</span></span>

<span data-ttu-id="2cfa2-131">中更详细地介绍了类型推断F#语言规范。</span><span class="sxs-lookup"><span data-stu-id="2cfa2-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cfa2-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cfa2-132">See also</span></span>

- [<span data-ttu-id="2cfa2-133">自动泛化</span><span class="sxs-lookup"><span data-stu-id="2cfa2-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)