---
title: UInteger 数据类型 (Visual Basic)
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
ms.openlocfilehash: a79162c6171c764d4c4610fd10f14a5dac6ff1a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498994"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="8b695-102">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="8b695-102">UInteger data type</span></span>

<span data-ttu-id="8b695-103">包含无符号的 32 位 （4 字节） 整数取值范围为 0 到 4294967295。</span><span class="sxs-lookup"><span data-stu-id="8b695-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b695-104">备注</span><span class="sxs-lookup"><span data-stu-id="8b695-104">Remarks</span></span>

 <span data-ttu-id="8b695-105">`UInteger`数据类型提供了最有效的数据宽度的最大无符号的值。</span><span class="sxs-lookup"><span data-stu-id="8b695-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="8b695-106">`UInteger` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="8b695-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="8b695-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="8b695-107">Literal assignments</span></span>

<span data-ttu-id="8b695-108">您可以声明并初始化`UInteger`变量由将其分配十进制文本、 十六进制文本八进制文本，或 （Visual Basic 从 2017年开始） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="8b695-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="8b695-109">如果整数文本在 `UInteger` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="8b695-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="8b695-110">在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `UInteger` 值。</span><span class="sxs-lookup"><span data-stu-id="8b695-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="8b695-111">使用前缀`&h`或`&H`来表示十六进制文本前缀`&b`或`&B`来表示二进制文本和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="8b695-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8b695-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="8b695-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8b695-113">从 Visual Basic 2017 开始，你还可以使用下划线字符， `_`，作为数字分隔符，以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8b695-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="8b695-114">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 作为前缀和十六进制、 二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="8b695-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="8b695-115">例如：</span><span class="sxs-lookup"><span data-stu-id="8b695-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="8b695-116">此外可以包含数值`UI`或`ui`[键入字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`UInteger`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8b695-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="8b695-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="8b695-117">Programming tips</span></span>

 <span data-ttu-id="8b695-118">`UInteger`并`Integer`数据类型在 32 位处理器上，提供最佳性能，因为较小的整数类型 (`UShort`， `Short`， `Byte`，并`SByte`)，即使它们使用较少的位，需要更多的时间加载、 存储和提取。</span><span class="sxs-lookup"><span data-stu-id="8b695-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="8b695-119">**负号。**</span><span class="sxs-lookup"><span data-stu-id="8b695-119">**Negative Numbers.**</span></span> <span data-ttu-id="8b695-120">因为`UInteger`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="8b695-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="8b695-121">如果使用一元负 (`-`) 运算符的表达式的计算结果为类型`UInteger`，Visual Basic 将转换为表达式`Long`第一个。</span><span class="sxs-lookup"><span data-stu-id="8b695-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="8b695-122">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="8b695-122">**CLS Compliance.**</span></span> <span data-ttu-id="8b695-123">`UInteger`数据类型不属于[公共语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用使用它的组件。</span><span class="sxs-lookup"><span data-stu-id="8b695-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="8b695-124">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="8b695-124">**Interop Considerations.**</span></span> <span data-ttu-id="8b695-125">如果你与不是为.NET Framework 中，如自动化或 COM 对象，编写组件交互请记住，类型，如`uint`可以在其他环境中具有不同的数据宽度 （16 位）。</span><span class="sxs-lookup"><span data-stu-id="8b695-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="8b695-126">如果您将 16 位自变量传递给此类组件，将其作为声明`UShort`而不是`UInteger`中托管的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="8b695-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="8b695-127">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="8b695-127">**Widening.**</span></span> <span data-ttu-id="8b695-128">`UInteger`数据类型加宽到`Long`， `ULong`， `Decimal`， `Single`，并`Double`。</span><span class="sxs-lookup"><span data-stu-id="8b695-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="8b695-129">这意味着可以将转换`UInteger`而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="8b695-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="8b695-130">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="8b695-130">**Type Characters.**</span></span> <span data-ttu-id="8b695-131">追加文本类型字符`UI`为文本将其强制转换到`UInteger`数据类型。</span><span class="sxs-lookup"><span data-stu-id="8b695-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="8b695-132">`UInteger` 有没有标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="8b695-132">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="8b695-133">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="8b695-133">**Framework Type.**</span></span> <span data-ttu-id="8b695-134">.NET Framework 中的对应类型是 <xref:System.UInt32?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="8b695-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b695-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b695-135">See also</span></span>
- <xref:System.UInt32>
- [<span data-ttu-id="8b695-136">数据类型</span><span class="sxs-lookup"><span data-stu-id="8b695-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8b695-137">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="8b695-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8b695-138">转换摘要</span><span class="sxs-lookup"><span data-stu-id="8b695-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8b695-139">如何：调用需要使用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="8b695-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="8b695-140">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="8b695-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
