---
title: UShort 数据类型 (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 520c21d4df5c340b41a8b1e9055b3fadddfdf6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ushort-data-type-visual-basic"></a>UShort 数据类型 (Visual Basic)

包含无符号的 16 位 （2 个字节） 整数，范围为 0 到 65,535。  
  
## <a name="remarks"></a>备注

 使用`UShort`数据类型包含二进制数据对于来说太大`Byte`。  
  
 `UShort` 的默认值为 0。  

# <a name="literal-assignments"></a>文本分配

你可以声明并初始化`UShort`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。 如果整数文本在 `UShort` 范围之外（即，如果它小于 <xref:System.UInt16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在下面的示例中，整数等于表示为十进制数字，十六进制，65,034 和二进制文本分配给`UShort`值。
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> 使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。 例如：

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

此外可以包括数值`US`或`us`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`UShort`数据类型，如以下示例所示。

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>编程提示
  
-   **负数。** 因为`UShort`是无符号的类型，它不能表示为负数。 如果你使用一元负 (`-`) 运算符的表达式的计算结果为键入`UShort`，Visual Basic 将转换为表达式`Integer`第一个。  
  
-   **CLS 遵从性。** `UShort`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。
  
-   **扩大转换。** `UShort`数据类型加宽到`Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，和`Double`。 这意味着你可以将转换`UShort`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。  
  
-   **类型字符。** 附加文本类型字符`US`到文本将其强制转换到`UShort`数据类型。 `UShort` 中有任何标识符类型字符。  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.UInt16?displayProperty=nameWithType> 结构。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.UInt16>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [如何：调用采用无符号类型的 Windows 函数](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
