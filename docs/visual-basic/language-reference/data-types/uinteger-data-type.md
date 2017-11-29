---
title: "UInteger 数据类型"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
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
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a><span data-ttu-id="1a796-102">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="1a796-102">UInteger data type</span></span>

<span data-ttu-id="1a796-103">包含无符号的 32 位 （4 字节） 整数，范围为 0 到 4294967295。</span><span class="sxs-lookup"><span data-stu-id="1a796-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a796-104">备注</span><span class="sxs-lookup"><span data-stu-id="1a796-104">Remarks</span></span>

 <span data-ttu-id="1a796-105">`UInteger`数据类型提供了中的最有效的数据宽度的最大无符号的值。</span><span class="sxs-lookup"><span data-stu-id="1a796-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="1a796-106">`UInteger` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="1a796-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="1a796-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="1a796-107">Literal assignments</span></span>

<span data-ttu-id="1a796-108">你可以声明并初始化`UInteger`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="1a796-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1a796-109">如果整数文本在 `UInteger` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="1a796-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="1a796-110">在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `UInteger` 值。</span><span class="sxs-lookup"><span data-stu-id="1a796-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="1a796-111">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="1a796-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1a796-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="1a796-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1a796-113">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="1a796-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="1a796-114">此外可以包括数值`UI`或`ui`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`UInteger`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="1a796-114">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="1a796-115">编程提示</span><span class="sxs-lookup"><span data-stu-id="1a796-115">Programming tips</span></span>

 <span data-ttu-id="1a796-116">`UInteger`和`Integer`数据类型在 32 位处理器上，提供最佳性能，因为较小的整数类型 (`UShort`， `Short`， `Byte`，和`SByte`)，即使它们使用位数更少，需要更多的时间加载、 存储和提取。</span><span class="sxs-lookup"><span data-stu-id="1a796-116">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="1a796-117">**负数。**</span><span class="sxs-lookup"><span data-stu-id="1a796-117">**Negative Numbers.**</span></span> <span data-ttu-id="1a796-118">因为`UInteger`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="1a796-118">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="1a796-119">如果你使用一元负 (`-`) 运算符的表达式的计算结果为键入`UInteger`，Visual Basic 将转换为表达式`Long`第一个。</span><span class="sxs-lookup"><span data-stu-id="1a796-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="1a796-120">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="1a796-120">**CLS Compliance.**</span></span> <span data-ttu-id="1a796-121">`UInteger`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。</span><span class="sxs-lookup"><span data-stu-id="1a796-121">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="1a796-122">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="1a796-122">**Interop Considerations.**</span></span> <span data-ttu-id="1a796-123">如果你与不是为.NET Framework 中，如自动化或 COM 对象编写的组件交互请记住，类型，如`uint`可以在其他环境中具有不同的数据宽度 （16 位）。</span><span class="sxs-lookup"><span data-stu-id="1a796-123">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="1a796-124">如果你的 16 位自变量传递给此类组件，将其声明为`UShort`而不是`UInteger`托管 Visual Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="1a796-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="1a796-125">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="1a796-125">**Widening.**</span></span> <span data-ttu-id="1a796-126">`UInteger`数据类型加宽到`Long`， `ULong`， `Decimal`， `Single`，和`Double`。</span><span class="sxs-lookup"><span data-stu-id="1a796-126">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="1a796-127">这意味着你可以将转换`UInteger`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="1a796-127">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="1a796-128">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="1a796-128">**Type Characters.**</span></span> <span data-ttu-id="1a796-129">附加文本类型字符`UI`到文本将其强制转换到`UInteger`数据类型。</span><span class="sxs-lookup"><span data-stu-id="1a796-129">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="1a796-130">`UInteger`中有任何标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="1a796-130">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="1a796-131">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="1a796-131">**Framework Type.**</span></span> <span data-ttu-id="1a796-132">.NET Framework 中的对应类型是 <xref:System.UInt32?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="1a796-132">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a796-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a796-133">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="1a796-134">数据类型</span><span class="sxs-lookup"><span data-stu-id="1a796-134">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="1a796-135">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="1a796-135">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="1a796-136">转换摘要</span><span class="sxs-lookup"><span data-stu-id="1a796-136">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="1a796-137">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="1a796-137">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="1a796-138">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="1a796-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
