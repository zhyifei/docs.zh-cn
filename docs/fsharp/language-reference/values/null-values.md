---
title: Null 值 (F#)
description: '了解如何在 F # 编程语言中使用 null 值。'
ms.date: 05/16/2016
ms.openlocfilehash: 7367b35cb6e910f926179e52992d5533e5cdda0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563904"
---
# <a name="null-values"></a><span data-ttu-id="83b85-103">Null 值</span><span class="sxs-lookup"><span data-stu-id="83b85-103">Null Values</span></span>

<span data-ttu-id="83b85-104">本主题介绍如何在 F # 中使用 null 值。</span><span class="sxs-lookup"><span data-stu-id="83b85-104">This topic describes how the null value is used in F#.</span></span>


## <a name="null-value"></a><span data-ttu-id="83b85-105">Null 值</span><span class="sxs-lookup"><span data-stu-id="83b85-105">Null Value</span></span>
<span data-ttu-id="83b85-106">Null 值不通常用于在 F # 中的值或变量。</span><span class="sxs-lookup"><span data-stu-id="83b85-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="83b85-107">但是，在某些情况下异常值都会显示 null。</span><span class="sxs-lookup"><span data-stu-id="83b85-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="83b85-108">如果在 F # 中定义了类型，null 不允许作为正则值除非[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)属性应用于该类型。</span><span class="sxs-lookup"><span data-stu-id="83b85-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="83b85-109">如果类型在定义某些其他.NET 语言中，null，则是一个可能的值，并且时进行互操作与此类类型，F # 代码可能会遇到 null 值。</span><span class="sxs-lookup"><span data-stu-id="83b85-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="83b85-110">对于在 F # 中定义的从 F # 使用严格的类型，创建 null 值直接使用 F # 库的唯一方法是使用[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。</span><span class="sxs-lookup"><span data-stu-id="83b85-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="83b85-111">但是，F # 类型，用于从其他.NET 语言，或如果你正在使用一个 API，则不会写在 F # 中，如.NET Framework 中，该类型可以出现 null 值。</span><span class="sxs-lookup"><span data-stu-id="83b85-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="83b85-112">你可以使用`option`F # 时可能会与其他.NET 语言中的可能的 null 值使用引用变量中的类型。</span><span class="sxs-lookup"><span data-stu-id="83b85-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="83b85-113">而不是 null，F #`option`类型，使用选项值`None`如果没有对象。</span><span class="sxs-lookup"><span data-stu-id="83b85-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="83b85-114">使用选项值`Some(obj)`的对象`obj`对象时。</span><span class="sxs-lookup"><span data-stu-id="83b85-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="83b85-115">有关详细信息，请参阅[选项](../options.md)。</span><span class="sxs-lookup"><span data-stu-id="83b85-115">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="83b85-116">`null`关键字是有效的关键字在 F # 语言中，并且你必须在使用.NET Framework Api 或其他.NET 语言编写的其他 Api 时使用它。</span><span class="sxs-lookup"><span data-stu-id="83b85-116">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="83b85-117">中，您可能需要一个 null 值的两种情况是当您调用.NET API 和传递 null 值作为参数，并且在解释返回值或从.NET 方法调用输出参数。</span><span class="sxs-lookup"><span data-stu-id="83b85-117">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="83b85-118">若要将 null 值传递给.NET 方法，只需使用`null`调用代码中的关键字。</span><span class="sxs-lookup"><span data-stu-id="83b85-118">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="83b85-119">下面的代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="83b85-119">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="83b85-120">若要解释从.NET 方法获得一个 null 值，使用模式匹配，如果你知道如何操作。</span><span class="sxs-lookup"><span data-stu-id="83b85-120">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="83b85-121">下面的代码示例演示如何使用模式匹配来解释从返回的 null 值`ReadLine`时试图读取输入流的末尾。</span><span class="sxs-lookup"><span data-stu-id="83b85-121">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="83b85-122">也可以在其他方面，例如，当你使用生成的 F # 类型的 null 值`Array.zeroCreate`，哪些调用`Unchecked.defaultof`。</span><span class="sxs-lookup"><span data-stu-id="83b85-122">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="83b85-123">必须小心使用此类代码保留封装空值。</span><span class="sxs-lookup"><span data-stu-id="83b85-123">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="83b85-124">在库仅用于 F # 中，无需检查每个函数中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="83b85-124">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="83b85-125">如果你正在编写用于与其他.NET 语言间的互操作的库，你可能需要添加针对 null 检查输入参数和引发`ArgumentNullException`，就像在 C# 或 Visual Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="83b85-125">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="83b85-126">下面的代码可用于检查任意值是否为 null。</span><span class="sxs-lookup"><span data-stu-id="83b85-126">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="83b85-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="83b85-127">See Also</span></span>
[<span data-ttu-id="83b85-128">值</span><span class="sxs-lookup"><span data-stu-id="83b85-128">Values</span></span>](index.md)

[<span data-ttu-id="83b85-129">match 表达式</span><span class="sxs-lookup"><span data-stu-id="83b85-129">Match Expressions</span></span>](../match-expressions.md)
