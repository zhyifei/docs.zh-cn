---
title: 枚举
description: 了解如何使用F#枚举替代文本, 使代码更具可读性和更易维护性。
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630339"
---
# <a name="enumerations"></a><span data-ttu-id="46357-103">枚举</span><span class="sxs-lookup"><span data-stu-id="46357-103">Enumerations</span></span>

<span data-ttu-id="46357-104">*枚举*(也称为*枚举*) 是整型类型, 其中标签分配给值的子集。</span><span class="sxs-lookup"><span data-stu-id="46357-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="46357-105">可以使用它们来代替文本，使代码更具可读性且更易维护。</span><span class="sxs-lookup"><span data-stu-id="46357-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="46357-106">语法</span><span class="sxs-lookup"><span data-stu-id="46357-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="46357-107">备注</span><span class="sxs-lookup"><span data-stu-id="46357-107">Remarks</span></span>

<span data-ttu-id="46357-108">枚举非常类似于具有简单值的可区分联合, 只不过可以指定这些值。</span><span class="sxs-lookup"><span data-stu-id="46357-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="46357-109">值通常是从0或1开始的整数, 或者是表示位位置的整数。</span><span class="sxs-lookup"><span data-stu-id="46357-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="46357-110">如果枚举旨在表示位位置, 还应使用[Flags](xref:System.FlagsAttribute)特性。</span><span class="sxs-lookup"><span data-stu-id="46357-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="46357-111">枚举的基础类型是根据使用的文本确定的, 因此, 例如, 可以对无符号整数 ( `1u``uint32`) 类型使用带有后缀的文本 (例如、 `2u`等)。</span><span class="sxs-lookup"><span data-stu-id="46357-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="46357-112">引用命名值时, 必须使用枚举类型本身的名称作为限定符, `enum-name.value1`即, 而不只`value1`是。</span><span class="sxs-lookup"><span data-stu-id="46357-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="46357-113">此行为不同于可区分联合的行为。</span><span class="sxs-lookup"><span data-stu-id="46357-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="46357-114">这是因为枚举始终具有[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性。</span><span class="sxs-lookup"><span data-stu-id="46357-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="46357-115">下面的代码演示了枚举的声明和使用。</span><span class="sxs-lookup"><span data-stu-id="46357-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="46357-116">使用适当的运算符可以轻松地将枚举转换为基础类型, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="46357-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="46357-117">枚举类型可以`sbyte`具有以下基础类型之一:、 `int32` `uint16` `uint32` `int16` `byte` 、、`uint64`、、 `uint16`、、、和`char`。 `int64`</span><span class="sxs-lookup"><span data-stu-id="46357-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="46357-118">枚举类型在 .NET Framework 中表示为从`System.Enum`继承的类型, 而后者又继承自。 `System.ValueType`</span><span class="sxs-lookup"><span data-stu-id="46357-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="46357-119">因此, 它们是位于堆栈上或内联在包含对象中的值类型, 并且基础类型的任何值都是枚举的有效值。</span><span class="sxs-lookup"><span data-stu-id="46357-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="46357-120">这在对枚举值进行模式匹配时很重要, 因为您必须提供一个模式来捕获未命名的值。</span><span class="sxs-lookup"><span data-stu-id="46357-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="46357-121">库中的`enum`函数可用于生成枚举值, 甚至是预定义的命名值之一之外的值。 F#</span><span class="sxs-lookup"><span data-stu-id="46357-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="46357-122">`enum`函数如下所示。</span><span class="sxs-lookup"><span data-stu-id="46357-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="46357-123">默认`enum`函数适用于类型`int32`。</span><span class="sxs-lookup"><span data-stu-id="46357-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="46357-124">因此, 它不能与具有其他基础类型的枚举类型一起使用。</span><span class="sxs-lookup"><span data-stu-id="46357-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="46357-125">请改用以下各项。</span><span class="sxs-lookup"><span data-stu-id="46357-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="46357-126">此外, 枚举事例始终作为`public`发出。</span><span class="sxs-lookup"><span data-stu-id="46357-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="46357-127">这是为了使它们与C# .net 平台的其余部分保持一致。</span><span class="sxs-lookup"><span data-stu-id="46357-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="46357-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="46357-128">See also</span></span>

- [<span data-ttu-id="46357-129">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="46357-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="46357-130">强制转换和转换</span><span class="sxs-lookup"><span data-stu-id="46357-130">Casting and Conversions</span></span>](casting-and-conversions.md)
