---
title: "枚举 (F#)"
description: "了解如何使用 F # 枚举代替文本以使代码更具可读性且更容易维护。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9272bf5a-9a9f-4314-9e34-a3248e5244f5
ms.openlocfilehash: de0273900b707c99e6fb1bcc84e5c2b9ef2bc725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="enumerations"></a><span data-ttu-id="3994b-104">枚举</span><span class="sxs-lookup"><span data-stu-id="3994b-104">Enumerations</span></span>

<span data-ttu-id="3994b-105">*枚举*，也称为*枚举*、 都是整型其中将标签分配给值的子集。</span><span class="sxs-lookup"><span data-stu-id="3994b-105">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="3994b-106">可以使用它们来代替文本，使代码更具可读性且更易维护。</span><span class="sxs-lookup"><span data-stu-id="3994b-106">You can use them in place of literals to make code more readable and maintainable.</span></span>


## <a name="syntax"></a><span data-ttu-id="3994b-107">语法</span><span class="sxs-lookup"><span data-stu-id="3994b-107">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="3994b-108">备注</span><span class="sxs-lookup"><span data-stu-id="3994b-108">Remarks</span></span>
<span data-ttu-id="3994b-109">枚举看起来非常类似于具有简单值的可区分联合只不过可以指定的值。</span><span class="sxs-lookup"><span data-stu-id="3994b-109">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="3994b-110">这些值通常是从 0 或 1，开始的整数或整数，用于表示位位置。</span><span class="sxs-lookup"><span data-stu-id="3994b-110">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="3994b-111">如果枚举用于表示位位置，你还应使用[标志](xref:System.FlagsAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="3994b-111">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="3994b-112">枚举的基础类型由使用时，该文本，以便，例如，你可以使用文本替换为后缀，例如`1u`， `2u`，依此类推，对于无符号整数 (`uint32`) 类型。</span><span class="sxs-lookup"><span data-stu-id="3994b-112">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="3994b-113">当引用已命名的值时，你必须使用枚举类型本身的名称用作限定符，即`enum-name.value1`，而不是`value1`。</span><span class="sxs-lookup"><span data-stu-id="3994b-113">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="3994b-114">此行为不同于可区分联合。</span><span class="sxs-lookup"><span data-stu-id="3994b-114">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="3994b-115">这是因为枚举始终具有[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性。</span><span class="sxs-lookup"><span data-stu-id="3994b-115">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="3994b-116">下面的代码演示的声明和用法的枚举。</span><span class="sxs-lookup"><span data-stu-id="3994b-116">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="3994b-117">你可以轻松地将转换枚举的基础类型通过使用适当的运算符，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="3994b-117">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="3994b-118">枚举的类型可以具有以下基础类型之一： `sbyte`， `byte`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint16`， `uint64`，和`char`。</span><span class="sxs-lookup"><span data-stu-id="3994b-118">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="3994b-119">枚举类型.NET Framework 中表示为从继承的类型`System.Enum`，其反过来继承自`System.ValueType`。</span><span class="sxs-lookup"><span data-stu-id="3994b-119">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="3994b-120">因此，它们就是位于堆栈或在包含的对象中，内联的值类型和基础类型的任何值是有效的值的枚举。</span><span class="sxs-lookup"><span data-stu-id="3994b-120">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="3994b-121">这很重要时模式匹配枚举值，因为你必须提供一种模式，捕获未命名的值。</span><span class="sxs-lookup"><span data-stu-id="3994b-121">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="3994b-122">`enum` F # 库中的函数可用来生成一个枚举值，即使其中一个的预定义以外的值命名值。</span><span class="sxs-lookup"><span data-stu-id="3994b-122">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="3994b-123">你使用`enum`函数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3994b-123">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="3994b-124">默认值`enum`函数配合类型`int32`。</span><span class="sxs-lookup"><span data-stu-id="3994b-124">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="3994b-125">因此，它不用于具有其他基础类型的枚举类型。</span><span class="sxs-lookup"><span data-stu-id="3994b-125">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="3994b-126">相反，使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="3994b-126">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a><span data-ttu-id="3994b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3994b-127">See Also</span></span>
[<span data-ttu-id="3994b-128">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="3994b-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="3994b-129">强制转换和转换</span><span class="sxs-lookup"><span data-stu-id="3994b-129">Casting and Conversions</span></span>](casting-and-conversions.md)
