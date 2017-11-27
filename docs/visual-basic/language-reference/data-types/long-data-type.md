---
title: "Long 数据类型 (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Long
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e21ed43ddc6efb018df0581faed1ebf270ab3ca
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="e4a35-102">Long 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4a35-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="e4a35-103">保存有符号数值范围从-9223372036854775808 到 9223372036854775807 之间的 64 位 （8 字节） 整数 (9.2 … E + 18)。</span><span class="sxs-lookup"><span data-stu-id="e4a35-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4a35-104">备注</span><span class="sxs-lookup"><span data-stu-id="e4a35-104">Remarks</span></span>

 <span data-ttu-id="e4a35-105">使用`Long`数据类型包含整数的数字，则太大，无法容纳`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4a35-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="e4a35-106">`Long` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="e4a35-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="e4a35-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="e4a35-107">Literal assignments</span></span> 

<span data-ttu-id="e4a35-108">你可以声明并初始化`Long`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="e4a35-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="e4a35-109">如果整数文本在 `Long` 范围之外（即，如果它小于 <xref:System.Int64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int64.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="e4a35-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="e4a35-110">在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `Long` 值。</span><span class="sxs-lookup"><span data-stu-id="e4a35-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="e4a35-111">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="e4a35-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="e4a35-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="e4a35-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="e4a35-113">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="e4a35-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="e4a35-114">此外可以包括数值`L`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`Long`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="e4a35-114">Numeric literals can also include the `L` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC0326L
```

## <a name="programming-tips"></a><span data-ttu-id="e4a35-115">编程提示</span><span class="sxs-lookup"><span data-stu-id="e4a35-115">Programming tips</span></span>

-   <span data-ttu-id="e4a35-116">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="e4a35-116">**Interop Considerations.**</span></span> <span data-ttu-id="e4a35-117">如果你与不是为.NET Framework 中，如自动化或 COM 对象编写的组件交互请记住，`Long`在其他环境中具有不同的数据宽度 （32 位）。</span><span class="sxs-lookup"><span data-stu-id="e4a35-117">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="e4a35-118">如果你的 32 位自变量传递给此类组件，将其声明为`Integer`而不是`Long`在新的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="e4a35-118">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="e4a35-119">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="e4a35-119">**Widening.**</span></span> <span data-ttu-id="e4a35-120">`Long`数据类型加宽到`Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="e4a35-120">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="e4a35-121">这意味着，你可以将 `Long` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="e4a35-121">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="e4a35-122">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="e4a35-122">**Type Characters.**</span></span> <span data-ttu-id="e4a35-123">将文本类型字符 `L` 追加到文本会将其强制转换为 `Long` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4a35-123">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="e4a35-124">将标识符类型字符 `&` 追加到任何标识符会将其强制转换为 `Long`。</span><span class="sxs-lookup"><span data-stu-id="e4a35-124">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
-   <span data-ttu-id="e4a35-125">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="e4a35-125">**Framework Type.**</span></span> <span data-ttu-id="e4a35-126">.NET Framework 中的对应类型是 <xref:System.Int64?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="e4a35-126">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4a35-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4a35-127">See also</span></span>

<span data-ttu-id="e4a35-128"><xref:System.Int64>[数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="e4a35-128"><xref:System.Int64> [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="e4a35-129">[整数数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="e4a35-129">[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="e4a35-130">[Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="e4a35-130">[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md) </span></span>  
<span data-ttu-id="e4a35-131">[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="e4a35-131">[Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="e4a35-132">[转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="e4a35-132">[Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
[<span data-ttu-id="e4a35-133">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="e4a35-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
