---
title: Null 值
description: 了解如何在中使用 null 值F#编程语言。
ms.date: 03/22/2019
ms.openlocfilehash: 93ac48eddf36981b9df550e76405c3175ae92e0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902273"
---
# <a name="null-values"></a><span data-ttu-id="8b3ac-103">Null 值</span><span class="sxs-lookup"><span data-stu-id="8b3ac-103">Null Values</span></span>

<span data-ttu-id="8b3ac-104">本主题介绍如何在中使用 null 值F#。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-104">This topic describes how the null value is used in F#.</span></span>

## <a name="null-value"></a><span data-ttu-id="8b3ac-105">Null 值</span><span class="sxs-lookup"><span data-stu-id="8b3ac-105">Null Value</span></span>

<span data-ttu-id="8b3ac-106">Null 值通常不使用在F#的值或变量。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="8b3ac-107">但是，null 将显示异常值在某些情况下。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="8b3ac-108">如果类型在定义F#，null 不允许作为常规的值，除非[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)特性应用于类型。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="8b3ac-109">如果某些其他.NET 语言中定义了一个类型，null 是一个可能的值，并进行互操作与此类类型时在F#代码可能会遇到 null 值。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="8b3ac-110">中定义的类型为F#和使用严格地根据F#，只能创建一个 null 值使用F#库直接将使用[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="8b3ac-111">但是，对于F#类型用于从其他.NET 语言，或者如果正在使用一个 API，编写时未使用该类型F#，如.NET Framework 中，可以出现 null 值。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="8b3ac-112">可以使用`option`中键入F#时可能会使用引用变量与另一种.NET 语言中可能的 null 值。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="8b3ac-113">而不是 null，与F#`option`类型，使用该选项的值`None`如果没有对象。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="8b3ac-114">使用选项值`Some(obj)`与对象`obj`对象时。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="8b3ac-115">有关详细信息，请参阅[选项](../options.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-115">For more information, see [Options](../options.md).</span></span> <span data-ttu-id="8b3ac-116">请注意，仍能够打包`null`成选项值如果为`Some x`，`x`恰好是`null`。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-116">Note that you can still pack a `null` value into an Option if, for `Some x`, `x` happens to be `null`.</span></span> <span data-ttu-id="8b3ac-117">因此，务必使用`None`值时`null`。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-117">Because of this, it is important you use `None` when a value is `null`.</span></span>

<span data-ttu-id="8b3ac-118">`null`关键字是中的有效关键字F#语言中，并且你必须使用.NET Framework Api 或其他用其他.NET 语言编写的 Api 时使用它。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-118">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="8b3ac-119">两种情况中，您可能需要一个 null 值是和解释的返回值或输出参数从.NET 方法调用时调用.NET API 和作为参数传递 null 值。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-119">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="8b3ac-120">要将 null 值传递给.NET 方法，只需使用`null`调用代码中的关键字。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-120">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="8b3ac-121">下面的代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-121">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="8b3ac-122">若要解释从.NET 方法获取一个 null 值，使用模式匹配，如果你知道如何操作。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-122">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="8b3ac-123">下面的代码示例演示如何使用模式匹配来解释从返回的 null 值`ReadLine`当其尝试读取超出输入流的末尾。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-123">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="8b3ac-124">为空值F#还可以在其他方面，例如在使用生成类型`Array.zeroCreate`，它调用`Unchecked.defaultof`。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-124">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="8b3ac-125">您必须要注意此类的代码来跟封装的 null 值。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-125">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="8b3ac-126">仅适用于库中F#，不需要检查每个函数中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-126">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="8b3ac-127">如果你正在编写用于与其他.NET 语言的互操作的库，您可能需要添加 null 检查输入参数，并引发`ArgumentNullException`，就像您在 C# 或 Visual Basic 代码中执行操作。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-127">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="8b3ac-128">下面的代码可用于检查任意值是否为 null。</span><span class="sxs-lookup"><span data-stu-id="8b3ac-128">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="8b3ac-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b3ac-129">See also</span></span>

- [<span data-ttu-id="8b3ac-130">值</span><span class="sxs-lookup"><span data-stu-id="8b3ac-130">Values</span></span>](index.md)
- [<span data-ttu-id="8b3ac-131">match 表达式</span><span class="sxs-lookup"><span data-stu-id="8b3ac-131">Match Expressions</span></span>](../match-expressions.md)
