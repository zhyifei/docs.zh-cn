---
title: UInteger 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401375"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="2e560-102">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="2e560-102">UInteger data type</span></span>

<span data-ttu-id="2e560-103">保存未签名的 32 位（4 字节）整数，其值范围为 0 到 4，294，967，295。</span><span class="sxs-lookup"><span data-stu-id="2e560-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e560-104">备注</span><span class="sxs-lookup"><span data-stu-id="2e560-104">Remarks</span></span>

<span data-ttu-id="2e560-105">数据类型`UInteger`提供最有效的数据宽度中的最大未签名值。</span><span class="sxs-lookup"><span data-stu-id="2e560-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>

<span data-ttu-id="2e560-106">`UInteger` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="2e560-106">The default value of `UInteger` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2e560-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="2e560-107">Literal assignments</span></span>

<span data-ttu-id="2e560-108">您可以通过为其分配十进制文本、`UInteger`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。</span><span class="sxs-lookup"><span data-stu-id="2e560-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="2e560-109">如果整数文本在 `UInteger` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="2e560-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="2e560-110">在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `UInteger` 值。</span><span class="sxs-lookup"><span data-stu-id="2e560-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> <span data-ttu-id="2e560-111">`&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="2e560-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2e560-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="2e560-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2e560-113">从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="2e560-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

<span data-ttu-id="2e560-114">从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="2e560-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2e560-115">例如：</span><span class="sxs-lookup"><span data-stu-id="2e560-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2e560-116">数字文本还可以包括`UI`或`ui`[类型字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`UInteger`数据类型，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="2e560-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="2e560-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="2e560-117">Programming tips</span></span>

<span data-ttu-id="2e560-118">和`UInteger``Integer`数据类型在 32 位处理器上提供最佳性能，因为较小的整数类型 （、、`UShort``Short``Byte`和`SByte`）即使使用较少的位，也需要更多的时间来加载、存储和提取。</span><span class="sxs-lookup"><span data-stu-id="2e560-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>

- <span data-ttu-id="2e560-119">**负数。**</span><span class="sxs-lookup"><span data-stu-id="2e560-119">**Negative Numbers.**</span></span> <span data-ttu-id="2e560-120">因为它是`UInteger`无符号类型，它不能表示负数。</span><span class="sxs-lookup"><span data-stu-id="2e560-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="2e560-121">如果在计算为键入`-``UInteger`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Long`第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="2e560-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>

- <span data-ttu-id="2e560-122">**CLS 合规性。**</span><span class="sxs-lookup"><span data-stu-id="2e560-122">**CLS Compliance.**</span></span> <span data-ttu-id="2e560-123">数据类型`UInteger`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。</span><span class="sxs-lookup"><span data-stu-id="2e560-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="2e560-124">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="2e560-124">**Interop Considerations.**</span></span> <span data-ttu-id="2e560-125">如果要与未为 .NET 框架编写的组件（例如自动化或 COM 对象）接口，请记住，例如在其他`uint`环境中具有不同数据宽度（16 位）的类型。</span><span class="sxs-lookup"><span data-stu-id="2e560-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="2e560-126">如果要将 16 位参数传递给此类组件，请将其声明为`UShort`托管 Visual `UInteger` Basic 代码中而不是。</span><span class="sxs-lookup"><span data-stu-id="2e560-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

- <span data-ttu-id="2e560-127">**扩大。**</span><span class="sxs-lookup"><span data-stu-id="2e560-127">**Widening.**</span></span> <span data-ttu-id="2e560-128">数据类型`UInteger`扩展到`Long` `ULong`、、、`Decimal``Single`和`Double`。</span><span class="sxs-lookup"><span data-stu-id="2e560-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="2e560-129">这意味着您可以转换为`UInteger`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="2e560-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="2e560-130">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="2e560-130">**Type Characters.**</span></span> <span data-ttu-id="2e560-131">将文本类型字符`UI`追加到文本强制它到`UInteger`数据类型。</span><span class="sxs-lookup"><span data-stu-id="2e560-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="2e560-132">`UInteger`没有标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="2e560-132">`UInteger` has no identifier type character.</span></span>

- <span data-ttu-id="2e560-133">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="2e560-133">**Framework Type.**</span></span> <span data-ttu-id="2e560-134">.NET Framework 中的对应类型是 <xref:System.UInt32?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="2e560-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e560-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e560-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="2e560-136">数据类型</span><span class="sxs-lookup"><span data-stu-id="2e560-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2e560-137">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="2e560-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2e560-138">转换摘要</span><span class="sxs-lookup"><span data-stu-id="2e560-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2e560-139">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="2e560-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="2e560-140">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="2e560-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
