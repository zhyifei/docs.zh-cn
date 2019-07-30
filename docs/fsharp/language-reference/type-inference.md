---
title: 类型推断
description: 了解F#编译器如何推断值、变量、参数和返回值的类型。
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630183"
---
# <a name="type-inference"></a><span data-ttu-id="e4fd7-103">类型推断</span><span class="sxs-lookup"><span data-stu-id="e4fd7-103">Type Inference</span></span>

<span data-ttu-id="e4fd7-104">本主题介绍F#编译器如何推断值、变量、参数和返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="e4fd7-105">类型推理概述</span><span class="sxs-lookup"><span data-stu-id="e4fd7-105">Type Inference in General</span></span>

<span data-ttu-id="e4fd7-106">类型推理的理念是, 无需指定F#构造类型, 除非编译器无法最终推断类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="e4fd7-107">省略显式类型信息并不意味着这F#是动态类型化语言, 或者中F#的值是弱类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="e4fd7-108">F#是一种静态类型化语言, 这意味着编译器将在编译过程中为每个构造推导一个确切的类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="e4fd7-109">如果编译器没有足够的信息来推导每个构造的类型, 则必须提供附加类型信息, 通常是在代码中的某个位置添加显式类型批注。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="e4fd7-110">参数和返回类型的推理</span><span class="sxs-lookup"><span data-stu-id="e4fd7-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="e4fd7-111">在参数列表中, 无需指定每个参数的类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="e4fd7-112">而且, F#是一种静态类型的语言, 因此每个值和表达式在编译时都有一个明确的类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="e4fd7-113">对于未显式指定的类型, 编译器将根据上下文推断类型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="e4fd7-114">如果未指定该类型, 则将其推断为泛型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="e4fd7-115">如果代码使用值的方式不一致, 这样一来, 就不存在满足所有值使用的单推断类型, 编译器将报告错误。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="e4fd7-116">函数的返回类型由函数中最后一个表达式的类型确定。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="e4fd7-117">例如, 在下面的代码中, 参数类型`a`和`b`和返回类型全都推断为`int` , 因为文字`100`的类型`int`为。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="e4fd7-118">您可以通过更改文本来影响类型推理。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="e4fd7-119">`100`如果`uint32`通过追加`b`后缀来`u`创建,则会将、和返回值的类型推断为。`a` `uint32`</span><span class="sxs-lookup"><span data-stu-id="e4fd7-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="e4fd7-120">您还可以通过使用隐含对类型的限制的其他构造 (如仅适用于特定类型的函数和方法) 来影响类型推理。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="e4fd7-121">此外, 还可以将显式类型批注应用于函数或方法参数或表达式中的变量, 如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="e4fd7-122">如果不同的约束之间发生冲突, 将导致错误。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="e4fd7-123">还可以通过在所有参数后面提供类型注释来显式指定函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="e4fd7-124">类型批注对参数有用的常见情况是: 参数为对象类型, 并且你想要使用成员。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="e4fd7-125">自动泛化</span><span class="sxs-lookup"><span data-stu-id="e4fd7-125">Automatic Generalization</span></span>

<span data-ttu-id="e4fd7-126">如果函数代码不依赖于参数的类型, 则编译器会将参数视为泛型。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="e4fd7-127">这称为*自动泛化*, 它是一种功能强大的工具, 可在不增加复杂性的情况下编写泛型代码。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="e4fd7-128">例如, 下面的函数将任意类型的两个参数合并为一个元组。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="e4fd7-129">将类型推断为</span><span class="sxs-lookup"><span data-stu-id="e4fd7-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="e4fd7-130">其他信息</span><span class="sxs-lookup"><span data-stu-id="e4fd7-130">Additional Information</span></span>

<span data-ttu-id="e4fd7-131">F#语言规范中更详细地介绍了类型推理。</span><span class="sxs-lookup"><span data-stu-id="e4fd7-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4fd7-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4fd7-132">See also</span></span>

- [<span data-ttu-id="e4fd7-133">自动泛化</span><span class="sxs-lookup"><span data-stu-id="e4fd7-133">Automatic Generalization</span></span>](./generics/automatic-generalization.md)
