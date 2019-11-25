---
title: Integer 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: c5b1041b8ef0ca9898a846fea03888537bb4abbf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343984"
---
# <a name="integer-data-type-visual-basic"></a>Integer data type (Visual Basic)

保存 32 位（4 字节）带符号整数，值的范围为 -2,147,483,648 到 2,147,483,647。  
  
## <a name="remarks"></a>备注

 `Integer` 数据类型为 32 位处理器提供了优化性能。 其他整数类型在内存中的加载和存储的速度都要稍慢一些。  
  
 `Integer` 的默认值为 0。  

## <a name="literal-assignments"></a>Literal assignments

You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal. 如果整数文本在 `Integer` 范围之外（即，如果它小于 <xref:System.Int32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int32.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，表示为十进制、十六进制和二进制文本且等于 90,946 的整数被分配给 `Integer` 值。

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal. 十进制文本没有前缀。

Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits. 例如:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>编程提示

- **Interop Considerations.** If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments. 如果将一个 16 位自变量传递给此类组件，请在新的 Visual Basic 代码中将其声明为 `Short` 而不是 `Integer`。  
  
- **Widening.** `Integer` 数据类型加宽到 `Long`、`Decimal`、`Single` 或 `Double`。 这意味着，你可以将 `Integer` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。  
  
- **Type Characters.** 将文本类型字符 `I` 追加到文本会将其强制转换为 `Integer` 数据类型。 将标识符类型字符 `%` 追加到任何标识符会将其强制转换为 `Integer`。  
  
- **Framework Type.** .NET Framework 中的对应类型是 <xref:System.Int32?displayProperty=nameWithType> 结构。  
  
## <a name="range"></a>范围

如果尝试将整型变量设置为其类型范围以外的数字，则将出错。 如果尝试将其设置为小数，则数字将向上或向下舍入为最接近的整数值。 如果数字同样接近两个整数值，则值将舍入为最接近的偶数整数。 这种做法可将因单方向持续舍入中点值而导致的舍入误差降到最低。 下面的代码演示了舍入的示例。  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a>请参阅

- <xref:System.Int32?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
