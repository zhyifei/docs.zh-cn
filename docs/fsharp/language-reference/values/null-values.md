---
title: Null 值
description: 了解如何在F#编程语言中使用 null 值。
ms.date: 03/22/2019
ms.openlocfilehash: 2038c0a461fec9884c51edd50c3c9f336104e30e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630814"
---
# <a name="null-values"></a><span data-ttu-id="8986b-103">Null 值</span><span class="sxs-lookup"><span data-stu-id="8986b-103">Null Values</span></span>

<span data-ttu-id="8986b-104">本主题介绍如何在中F#使用 null 值。</span><span class="sxs-lookup"><span data-stu-id="8986b-104">This topic describes how the null value is used in F#.</span></span>

## <a name="null-value"></a><span data-ttu-id="8986b-105">Null 值</span><span class="sxs-lookup"><span data-stu-id="8986b-105">Null Value</span></span>

<span data-ttu-id="8986b-106">F#对于值或变量, 通常不使用 null 值。</span><span class="sxs-lookup"><span data-stu-id="8986b-106">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="8986b-107">但是, 在某些情况下, null 显示为异常值。</span><span class="sxs-lookup"><span data-stu-id="8986b-107">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="8986b-108">如果在中F#定义了类型, 则不允许将 null 作为常规值, 除非将[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)属性应用于该类型。</span><span class="sxs-lookup"><span data-stu-id="8986b-108">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="8986b-109">如果类型是使用其他某种 .NET 语言定义的, 则 null 是可能的值, 当您与此类类型进行互操作F#时, 您的代码可能会遇到 null 值。</span><span class="sxs-lookup"><span data-stu-id="8986b-109">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="8986b-110">对于在F#中定义并严格使用的类型F#, F#使用库直接创建 null 值的唯一方法是使用[unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[array.zerocreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。</span><span class="sxs-lookup"><span data-stu-id="8986b-110">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="8986b-111">但是, 对于从F#其他 .net 语言中使用的类型, 或者如果使用的是不是用编写F#的 API (如 .NET Framework), 则可能会出现 null 值。</span><span class="sxs-lookup"><span data-stu-id="8986b-111">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="8986b-112">当你可能在`option`其他 .net F#语言中使用具有可能为 null 值的引用变量时, 可以使用中的类型。</span><span class="sxs-lookup"><span data-stu-id="8986b-112">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="8986b-113">如果没有对象, 则可以F# `option`使用选项值`None` (而不是 null)。</span><span class="sxs-lookup"><span data-stu-id="8986b-113">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="8986b-114">当有对象时, `Some(obj)`可将选项`obj`值用于对象。</span><span class="sxs-lookup"><span data-stu-id="8986b-114">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="8986b-115">有关详细信息，请参阅[选项](../options.md)。</span><span class="sxs-lookup"><span data-stu-id="8986b-115">For more information, see [Options](../options.md).</span></span> <span data-ttu-id="8986b-116">`null`请注意, 如果`Some x` `x`的为`null`, 则仍可将值打包到选项中。</span><span class="sxs-lookup"><span data-stu-id="8986b-116">Note that you can still pack a `null` value into an Option if, for `Some x`, `x` happens to be `null`.</span></span> <span data-ttu-id="8986b-117">因此, 在值为`None` `null`时使用非常重要。</span><span class="sxs-lookup"><span data-stu-id="8986b-117">Because of this, it is important you use `None` when a value is `null`.</span></span>

<span data-ttu-id="8986b-118">关键字是F#语言中的有效关键字, 当你使用以其他 .net 语言编写的 .NET Framework api 或其他 api 时, 你必须使用它。 `null`</span><span class="sxs-lookup"><span data-stu-id="8986b-118">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="8986b-119">在以下两种情况下, 您可能需要 null 值: 调用 .NET API 并将 null 值作为参数传递, 以及从 .NET 方法调用解释返回值或输出参数。</span><span class="sxs-lookup"><span data-stu-id="8986b-119">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="8986b-120">若要将 null 值传递到 .net 方法, 只需在`null`调用代码中使用关键字。</span><span class="sxs-lookup"><span data-stu-id="8986b-120">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="8986b-121">下面的代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="8986b-121">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="8986b-122">若要解释从 .NET 方法获取的 null 值, 请在可以时使用模式匹配。</span><span class="sxs-lookup"><span data-stu-id="8986b-122">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="8986b-123">下面的代码示例演示如何使用模式匹配来解释在其尝试读取超出输入流末尾`ReadLine`时返回的 null 值。</span><span class="sxs-lookup"><span data-stu-id="8986b-123">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="8986b-124">还可以通过F#其他方式生成类型为 Null 的值, 例如在使用时, `Array.zeroCreate`将调用。 `Unchecked.defaultof`</span><span class="sxs-lookup"><span data-stu-id="8986b-124">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="8986b-125">必须谨慎处理此类代码, 使封装的值保持为空值。</span><span class="sxs-lookup"><span data-stu-id="8986b-125">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="8986b-126">在仅用于的F#库中, 无需在每个函数中检查 null 值。</span><span class="sxs-lookup"><span data-stu-id="8986b-126">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="8986b-127">如果要编写与其他 .net 语言的互操作性的库, 则可能必须添加对 null 输入参数的检查并引发`ArgumentNullException`, 就像在或 Visual Basic C#代码中一样。</span><span class="sxs-lookup"><span data-stu-id="8986b-127">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="8986b-128">可以使用以下代码检查任意值是否为 null。</span><span class="sxs-lookup"><span data-stu-id="8986b-128">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="8986b-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="8986b-129">See also</span></span>

- [<span data-ttu-id="8986b-130">值</span><span class="sxs-lookup"><span data-stu-id="8986b-130">Values</span></span>](index.md)
- [<span data-ttu-id="8986b-131">match 表达式</span><span class="sxs-lookup"><span data-stu-id="8986b-131">Match Expressions</span></span>](../match-expressions.md)
