---
title: "UInteger 数据类型"
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea6d42a604e5a50fab62644034afc82e089792c7
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="uinteger-data-type"></a><span data-ttu-id="5080e-102">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="5080e-102">UInteger data type</span></span>

<span data-ttu-id="5080e-103">包含无符号的 32 位 （4 字节） 整数，范围为 0 到 4294967295。</span><span class="sxs-lookup"><span data-stu-id="5080e-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5080e-104">备注</span><span class="sxs-lookup"><span data-stu-id="5080e-104">Remarks</span></span>

 <span data-ttu-id="5080e-105">`UInteger`数据类型提供了中的最有效的数据宽度的最大无符号的值。</span><span class="sxs-lookup"><span data-stu-id="5080e-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="5080e-106">`UInteger` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="5080e-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="5080e-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="5080e-107">Literal assignments</span></span>

<span data-ttu-id="5080e-108">你可以声明并初始化`UInteger`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="5080e-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5080e-109">如果整数文本在 `UInteger` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="5080e-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5080e-110">在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `UInteger` 值。</span><span class="sxs-lookup"><span data-stu-id="5080e-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="5080e-111">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="5080e-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5080e-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="5080e-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5080e-113">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5080e-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="5080e-114">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="5080e-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="5080e-115">例如:</span><span class="sxs-lookup"><span data-stu-id="5080e-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="5080e-116">此外可以包括数值`UI`或`ui`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`UInteger`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5080e-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="5080e-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="5080e-117">Programming tips</span></span>

 <span data-ttu-id="5080e-118">`UInteger`和`Integer`数据类型在 32 位处理器上，提供最佳性能，因为较小的整数类型 (`UShort`， `Short`， `Byte`，和`SByte`)，即使它们使用位数更少，需要更多的时间加载、 存储和提取。</span><span class="sxs-lookup"><span data-stu-id="5080e-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="5080e-119">**负数。**</span><span class="sxs-lookup"><span data-stu-id="5080e-119">**Negative Numbers.**</span></span> <span data-ttu-id="5080e-120">因为`UInteger`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="5080e-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5080e-121">如果你使用一元负 (`-`) 运算符的表达式的计算结果为键入`UInteger`，Visual Basic 将转换为表达式`Long`第一个。</span><span class="sxs-lookup"><span data-stu-id="5080e-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="5080e-122">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="5080e-122">**CLS Compliance.**</span></span> <span data-ttu-id="5080e-123">`UInteger`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。</span><span class="sxs-lookup"><span data-stu-id="5080e-123">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="5080e-124">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="5080e-124">**Interop Considerations.**</span></span> <span data-ttu-id="5080e-125">如果你与不是为.NET Framework 中，如自动化或 COM 对象编写的组件交互请记住，类型，如`uint`可以在其他环境中具有不同的数据宽度 （16 位）。</span><span class="sxs-lookup"><span data-stu-id="5080e-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="5080e-126">如果你的 16 位自变量传递给此类组件，将其声明为`UShort`而不是`UInteger`托管 Visual Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="5080e-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="5080e-127">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="5080e-127">**Widening.**</span></span> <span data-ttu-id="5080e-128">`UInteger`数据类型加宽到`Long`， `ULong`， `Decimal`， `Single`，和`Double`。</span><span class="sxs-lookup"><span data-stu-id="5080e-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5080e-129">这意味着你可以将转换`UInteger`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="5080e-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="5080e-130">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="5080e-130">**Type Characters.**</span></span> <span data-ttu-id="5080e-131">附加文本类型字符`UI`到文本将其强制转换到`UInteger`数据类型。</span><span class="sxs-lookup"><span data-stu-id="5080e-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="5080e-132">`UInteger`中有任何标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="5080e-132">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="5080e-133">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="5080e-133">**Framework Type.**</span></span> <span data-ttu-id="5080e-134">.NET Framework 中的对应类型是 <xref:System.UInt32?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="5080e-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5080e-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5080e-135">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="5080e-136">数据类型</span><span class="sxs-lookup"><span data-stu-id="5080e-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="5080e-137">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="5080e-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5080e-138">转换摘要</span><span class="sxs-lookup"><span data-stu-id="5080e-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="5080e-139">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="5080e-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="5080e-140">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="5080e-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
