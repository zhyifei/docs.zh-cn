---
title: 枚举 (F#)
description: '了解如何使用 F # 枚举来代替文本以使代码更具可读性且更易于维护。'
ms.date: 05/16/2016
ms.openlocfilehash: 47fb353c2698f8b1474834ebbd1b0eff2c7f76e7
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "44369061"
---
# <a name="enumerations"></a><span data-ttu-id="f3fc7-103">枚举</span><span class="sxs-lookup"><span data-stu-id="f3fc7-103">Enumerations</span></span>

<span data-ttu-id="f3fc7-104">*枚举*，也称为*枚举*、 是整型类型的标签分配到值的子集。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="f3fc7-105">可以使用它们来代替文本，使代码更具可读性且更易维护。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3fc7-106">语法</span><span class="sxs-lookup"><span data-stu-id="f3fc7-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="f3fc7-107">备注</span><span class="sxs-lookup"><span data-stu-id="f3fc7-107">Remarks</span></span>

<span data-ttu-id="f3fc7-108">一个枚举，看上去像可区分联合具有简单的值，只不过可以指定的值。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="f3fc7-109">这些值通常是从 0 或 1，开始的整数或整数，用于表示位位置。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="f3fc7-110">如果一个枚举，用于表示位位置，还应使用[标志](xref:System.FlagsAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="f3fc7-111">枚举的基础类型由文本使用，以便，例如，您可以使用文本带有后缀，如`1u`， `2u`，依此类推，对于无符号整数 (`uint32`) 类型。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="f3fc7-112">如果是指已命名值时，您必须使用枚举类型本身的名称用作限定符，，即`enum-name.value1`，而不是`value1`。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="f3fc7-113">此行为有何不同的可区分联合。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="f3fc7-114">这是因为枚举始终具有[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="f3fc7-115">下面的代码演示声明和使用的枚举。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="f3fc7-116">您可以轻松地转换为枚举的基础类型通过使用相应的运算符，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="f3fc7-117">枚举的类型可以具有以下基础类型之一： `sbyte`， `byte`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint16`， `uint64`，和`char`。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="f3fc7-118">枚举类型在.NET Framework 中表示为从继承的类型`System.Enum`，其又继承自`System.ValueType`。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="f3fc7-119">因此，它们是位于堆栈或内联的包含对象中的值类型，任何值的基础类型是枚举的有效值。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="f3fc7-120">这很重要时模式匹配枚举值，因为您必须提供一种模式可捕获未命名的值。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="f3fc7-121">`enum` F # 库中的函数可用于生成一个枚举值，甚至之外的预定义的值命名值。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="f3fc7-122">您使用`enum`函数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="f3fc7-123">默认值`enum`函数适用于类型`int32`。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="f3fc7-124">因此，它不能用于具有其他的基础类型的枚举类型。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="f3fc7-125">相反，使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="f3fc7-126">此外，情况下，对于枚举时，始终发出作为`public`。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="f3fc7-127">这是以使它们与 C# 和.NET 平台的其余部分保持一致。</span><span class="sxs-lookup"><span data-stu-id="f3fc7-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3fc7-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3fc7-128">See also</span></span>

- [<span data-ttu-id="f3fc7-129">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f3fc7-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f3fc7-130">强制转换和转换</span><span class="sxs-lookup"><span data-stu-id="f3fc7-130">Casting and Conversions</span></span>](casting-and-conversions.md)
