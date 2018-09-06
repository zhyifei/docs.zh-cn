---
title: Null 值 (F#)
description: '了解如何在 F # 编程语言中使用 null 值。'
ms.date: 05/16/2016
ms.openlocfilehash: 8751ac402c43ddb07fb62e08b6c6d5403cbe9acc
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787891"
---
# <a name="null-values"></a><span data-ttu-id="46fc4-103">Null 值</span><span class="sxs-lookup"><span data-stu-id="46fc4-103">Null Values</span></span>

<span data-ttu-id="46fc4-104">本主题介绍如何在 F # 中使用 null 值。</span><span class="sxs-lookup"><span data-stu-id="46fc4-104">This topic describes how the null value is used in F#.</span></span>

## <a name="null-value"></a><span data-ttu-id="46fc4-105">Null 值</span><span class="sxs-lookup"><span data-stu-id="46fc4-105">Null Value</span></span>

<span data-ttu-id="46fc4-106">Null 值不正常情况下用于在 F # 中的值或变量。</span><span class="sxs-lookup"><span data-stu-id="46fc4-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="46fc4-107">但是，null 将显示异常值在某些情况下。</span><span class="sxs-lookup"><span data-stu-id="46fc4-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="46fc4-108">如果 F # 中定义了一个类型，null 不允许作为常规值除非[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)特性应用于类型。</span><span class="sxs-lookup"><span data-stu-id="46fc4-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="46fc4-109">如果某些其他.NET 语言中定义一个类型，则为 null，则是一个可能的值，并在 F # 代码进行互操作与此类类型时, 可能会遇到 null 值。</span><span class="sxs-lookup"><span data-stu-id="46fc4-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="46fc4-110">对于 F # 中定义的从 F # 使用严格的类型，创建一个 null 值，直接使用 F # 库的唯一方法是使用[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。</span><span class="sxs-lookup"><span data-stu-id="46fc4-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="46fc4-111">但是，对于 F # 类型的属性可以从使用其他.NET 语言，或如果未在 F # 中，如.NET Framework 编写的 API 与使用该类型可以出现 null 值。</span><span class="sxs-lookup"><span data-stu-id="46fc4-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="46fc4-112">可以使用`option`中 F # 时可能会与另一种.NET 语言中可能的 null 值使用引用变量的类型。</span><span class="sxs-lookup"><span data-stu-id="46fc4-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="46fc4-113">而不是 null，使用 F #`option`类型，使用选项值`None`如果没有对象。</span><span class="sxs-lookup"><span data-stu-id="46fc4-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="46fc4-114">使用选项值`Some(obj)`与对象`obj`对象时。</span><span class="sxs-lookup"><span data-stu-id="46fc4-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="46fc4-115">有关详细信息，请参阅[选项](../options.md)。</span><span class="sxs-lookup"><span data-stu-id="46fc4-115">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="46fc4-116">`null`关键字是在 F # 语言中，有效的关键字，您必须使用.NET Framework Api 或其他用其他.NET 语言编写的 Api 时使用它。</span><span class="sxs-lookup"><span data-stu-id="46fc4-116">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="46fc4-117">两种情况中，您可能需要一个 null 值是和解释的返回值或输出参数从.NET 方法调用时调用.NET API 和作为参数传递 null 值。</span><span class="sxs-lookup"><span data-stu-id="46fc4-117">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="46fc4-118">要将 null 值传递给.NET 方法，只需使用`null`调用代码中的关键字。</span><span class="sxs-lookup"><span data-stu-id="46fc4-118">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="46fc4-119">下面的代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="46fc4-119">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="46fc4-120">若要解释从.NET 方法获取一个 null 值，使用模式匹配，如果你知道如何操作。</span><span class="sxs-lookup"><span data-stu-id="46fc4-120">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="46fc4-121">下面的代码示例演示如何使用模式匹配来解释从返回的 null 值`ReadLine`当其尝试读取超出输入流的末尾。</span><span class="sxs-lookup"><span data-stu-id="46fc4-121">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="46fc4-122">此外可以在其他方面，例如在使用生成的 F # 类型的 null 值`Array.zeroCreate`，它调用`Unchecked.defaultof`。</span><span class="sxs-lookup"><span data-stu-id="46fc4-122">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="46fc4-123">您必须要注意此类的代码来跟封装的 null 值。</span><span class="sxs-lookup"><span data-stu-id="46fc4-123">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="46fc4-124">仅用于 F # 库，不需要检查每个函数中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="46fc4-124">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="46fc4-125">如果你正在编写用于与其他.NET 语言的互操作的库，您可能需要添加 null 检查输入参数，并引发`ArgumentNullException`，就像您在 C# 或 Visual Basic 代码中执行操作。</span><span class="sxs-lookup"><span data-stu-id="46fc4-125">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="46fc4-126">下面的代码可用于检查任意值是否为 null。</span><span class="sxs-lookup"><span data-stu-id="46fc4-126">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="46fc4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="46fc4-127">See also</span></span>

- [<span data-ttu-id="46fc4-128">值</span><span class="sxs-lookup"><span data-stu-id="46fc4-128">Values</span></span>](index.md)
- [<span data-ttu-id="46fc4-129">match 表达式</span><span class="sxs-lookup"><span data-stu-id="46fc4-129">Match Expressions</span></span>](../match-expressions.md)
