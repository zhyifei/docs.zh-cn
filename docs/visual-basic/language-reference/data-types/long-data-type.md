---
title: Long 数据类型 (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b3970aad08f2be98d175b4175ef06711bcaf609
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731756"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="0f975-102">Long 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f975-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="0f975-103">保存有符号 64 位 （8 字节） 整数取值范围为-9223372036854775808 到 9,223,372,036,854,775,807 (9.2...E + 18)。</span><span class="sxs-lookup"><span data-stu-id="0f975-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f975-104">备注</span><span class="sxs-lookup"><span data-stu-id="0f975-104">Remarks</span></span>

 <span data-ttu-id="0f975-105">使用`Long`数据类型，以包含整数数字过大而无法放入`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="0f975-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>  
  
 <span data-ttu-id="0f975-106">`Long` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="0f975-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="0f975-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="0f975-107">Literal assignments</span></span> 

<span data-ttu-id="0f975-108">您可以声明并初始化`Long`变量由将其分配十进制文本、 十六进制文本八进制文本，或 （Visual Basic 从 2017年开始） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="0f975-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="0f975-109">如果整数文本在 `Long` 范围之外（即，如果它小于 <xref:System.Int64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int64.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="0f975-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="0f975-110">在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `Long` 值。</span><span class="sxs-lookup"><span data-stu-id="0f975-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> <span data-ttu-id="0f975-111">使用前缀`&h`或`&H`来表示十六进制文本前缀`&b`或`&B`来表示二进制文本和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="0f975-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="0f975-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="0f975-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="0f975-113">从 Visual Basic 2017 开始，你还可以使用下划线字符， `_`，作为数字分隔符，以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="0f975-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="0f975-114">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 作为前缀和十六进制、 二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="0f975-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="0f975-115">例如：</span><span class="sxs-lookup"><span data-stu-id="0f975-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="0f975-116">此外可以包含数值`L`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`Long`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="0f975-116">Numeric literals can also include the `L` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="0f975-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="0f975-117">Programming tips</span></span>

-   <span data-ttu-id="0f975-118">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="0f975-118">**Interop Considerations.**</span></span> <span data-ttu-id="0f975-119">如果你与不是为.NET Framework 中，如自动化或 COM 对象，编写组件交互记住`Long`在其他环境中具有不同的数据宽度 （32 位）。</span><span class="sxs-lookup"><span data-stu-id="0f975-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="0f975-120">如果您将 32 位自变量传递给此类组件，将其作为声明`Integer`而不是`Long`中新的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="0f975-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="0f975-121">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="0f975-121">**Widening.**</span></span> <span data-ttu-id="0f975-122">`Long`数据类型加宽到`Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="0f975-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="0f975-123">这意味着，你可以将 `Long` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="0f975-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="0f975-124">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="0f975-124">**Type Characters.**</span></span> <span data-ttu-id="0f975-125">将文本类型字符 `L` 追加到文本会将其强制转换为 `Long` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="0f975-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="0f975-126">将标识符类型字符 `&` 追加到任何标识符会将其强制转换为 `Long`。</span><span class="sxs-lookup"><span data-stu-id="0f975-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>  
  
-   <span data-ttu-id="0f975-127">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="0f975-127">**Framework Type.**</span></span> <span data-ttu-id="0f975-128">.NET Framework 中的对应类型是 <xref:System.Int64?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="0f975-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0f975-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f975-129">See also</span></span>

<span data-ttu-id="0f975-130"><xref:System.Int64>
[数据类型](../../../visual-basic/language-reference/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="0f975-130"><xref:System.Int64>
[Data Types](../../../visual-basic/language-reference/data-types/index.md) </span></span>  
<span data-ttu-id="0f975-131">[整数数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="0f975-131">[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="0f975-132">[Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="0f975-132">[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md) </span></span>  
<span data-ttu-id="0f975-133">[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="0f975-133">[Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="0f975-134">[转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="0f975-134">[Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
[<span data-ttu-id="0f975-135">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="0f975-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
