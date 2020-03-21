---
title: Long 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401399"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="f3597-102">长数据类型（可视基本）</span><span class="sxs-lookup"><span data-stu-id="f3597-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="f3597-103">持有已签名的 64 位（8 字节）整数，价值范围为 -9，223，372，036，854，775，808 到 9，223，372，036，854，775，807 （9.2...E=18）。</span><span class="sxs-lookup"><span data-stu-id="f3597-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="f3597-104">备注</span><span class="sxs-lookup"><span data-stu-id="f3597-104">Remarks</span></span>

<span data-ttu-id="f3597-105">使用`Long`数据类型包含太大而不适合数据类型的`Integer`整数。</span><span class="sxs-lookup"><span data-stu-id="f3597-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="f3597-106">`Long` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="f3597-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="f3597-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="f3597-107">Literal assignments</span></span>

<span data-ttu-id="f3597-108">您可以通过为其分配十进制文本、`Long`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。</span><span class="sxs-lookup"><span data-stu-id="f3597-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="f3597-109">如果整数文本在 `Long` 范围之外（即，如果它小于 <xref:System.Int64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int64.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="f3597-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="f3597-110">在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `Long` 值。</span><span class="sxs-lookup"><span data-stu-id="f3597-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="f3597-111">`&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="f3597-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="f3597-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="f3597-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f3597-113">从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="f3597-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="f3597-114">从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="f3597-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="f3597-115">例如：</span><span class="sxs-lookup"><span data-stu-id="f3597-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="f3597-116">数字文本还可以包括`L`表示`Long`数据类型[的类型字符](../../programming-guide/language-features/data-types/type-characters.md)，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="f3597-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="f3597-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="f3597-117">Programming tips</span></span>

- <span data-ttu-id="f3597-118">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="f3597-118">**Interop Considerations.**</span></span> <span data-ttu-id="f3597-119">如果要与未为 .NET 框架编写的组件（例如自动化或 COM 对象）接口，请记住，`Long`在其他环境中具有不同的数据宽度（32 位）。</span><span class="sxs-lookup"><span data-stu-id="f3597-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="f3597-120">如果要将 32 位参数传递给此类组件，请将其声明为`Integer`而不是在新的 Visual `Long` Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="f3597-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="f3597-121">**扩大。**</span><span class="sxs-lookup"><span data-stu-id="f3597-121">**Widening.**</span></span> <span data-ttu-id="f3597-122">数据类型`Long`扩展到`Decimal`或`Single`。 `Double`</span><span class="sxs-lookup"><span data-stu-id="f3597-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="f3597-123">这意味着，你可以将 `Long` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="f3597-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="f3597-124">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="f3597-124">**Type Characters.**</span></span> <span data-ttu-id="f3597-125">将文本类型字符 `L` 追加到文本会将其强制转换为 `Long` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3597-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="f3597-126">将标识符类型字符 `&` 追加到任何标识符会将其强制转换为 `Long`。</span><span class="sxs-lookup"><span data-stu-id="f3597-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="f3597-127">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="f3597-127">**Framework Type.**</span></span> <span data-ttu-id="f3597-128">.NET Framework 中的对应类型是 <xref:System.Int64?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="f3597-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3597-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3597-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="f3597-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="f3597-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f3597-131">整数数据类型</span><span class="sxs-lookup"><span data-stu-id="f3597-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="f3597-132">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="f3597-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="f3597-133">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="f3597-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f3597-134">转换摘要</span><span class="sxs-lookup"><span data-stu-id="f3597-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="f3597-135">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="f3597-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
