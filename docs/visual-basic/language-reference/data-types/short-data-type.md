---
title: Short 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343939"
---
# <a name="short-data-type-visual-basic"></a>Short 数据类型（Visual Basic）

保存16位有符号整数，其值范围从-32768 到32767。  
  
## <a name="remarks"></a>备注  

 使用 `Short` 数据类型包含整数值，不需要 `Integer`的完整数据宽度。 在某些情况下，公共语言运行时可以将 `Short` 变量紧密地打包在一起，从而节省内存消耗。  
  
 `Short` 的默认值为 0。  
  
## <a name="literal-assignments"></a>文本赋值

可以通过为 `Short` 变量指定十进制文本、十六进制文本、八进制文本或（从 Visual Basic 2017）作为二进制文本来声明和初始化。 如果整数文本在 `Short` 范围之外（即，如果它小于 <xref:System.Int16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int16.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在下面的示例中，表示为十进制、十六进制和二进制文本的整数等于1034将从[整数](integer-data-type.md)隐式转换为 `Short` 值。

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> 使用前缀 `&h` 或 `&H` 来表示十六进制文本，使用前缀 `&b` 或 `&B` 来表示二进制文本，并使用前缀 `&o` 或 `&O` 来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，还可以使用下划线字符（`_`）作为数字分隔符，以增强可读性，如以下示例中所示。

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

从 Visual Basic 15.5 开始，还可以使用下划线字符（`_`）作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

数字文本还可以包括 `S`[类型字符](../../programming-guide/language-features/data-types/type-characters.md)来表示 `Short` 数据类型，如下面的示例所示。

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>编程提示

- **扩大.** `Short` 数据类型扩大到 `Integer`、`Long`、`Decimal`、`Single`或 `Double`。 这意味着，你可以将 `Short` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。  
  
- **键入字符。** 将文本类型字符 `S` 追加到文本会将其强制转换为 `Short` 数据类型。 `Short` 没有标识符类型字符。  
  
- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Int16?displayProperty=nameWithType> 结构。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Int16?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
