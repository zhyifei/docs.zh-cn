---
title: SByte 数据类型
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343947"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte 数据类型（Visual Basic）

保存8位有符号整数，其值范围从-128 到127。

## <a name="remarks"></a>备注

使用 `SByte` 数据类型包含整数值，不需要 `Integer` 的完整数据宽度，甚至 `Short`的半数据宽度。 在某些情况下，公共语言运行时可以将 `SByte` 变量紧密地打包在一起，从而节省内存消耗。

`SByte` 的默认值为 0。

## <a name="literal-assignments"></a>文本赋值

可以通过为 `SByte` 变量指定十进制文本、十六进制文本、八进制文本或（从 Visual Basic 2017）作为二进制文本来声明和初始化。

在下面的示例中，表示为十进制、十六进制和二进制文本的整数等于-102，分配给 `SByte` 值。 此示例要求你编译 `/removeintchecks` 编译器开关。

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> 使用前缀 `&h` 或 `&H` 来表示十六进制文本，使用前缀 `&b` 或 `&B` 来表示二进制文本，并使用前缀 `&o` 或 `&O` 来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，还可以使用下划线字符（`_`）作为数字分隔符，以增强可读性，如以下示例中所示。

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

从 Visual Basic 15.5 开始，还可以使用下划线字符（`_`）作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

如果整数文本在 `SByte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.SByte.MaxValue?displayProperty=nameWithType>），会发生编译错误。 如果整数文本没有后缀，则会推理[整数](integer-data-type.md)。 如果整数文本超出 `Integer` 类型的范围，则将推断一个[长](long-data-type.md)整型值。 这意味着，在前面的示例中，数值 `0x9A` 和 `0b10011010` 被解释为32位有符号整数，其156值超过了 <xref:System.SByte.MaxValue?displayProperty=nameWithType>。 若要成功编译此类代码，以便将非十进制整数分配到 `SByte`，你可以执行以下任一操作：

- 通过使用 `/removeintchecks` 编译器开关进行编译来禁用整数边界检查。

- 使用[类型字符](../../programming-guide/language-features/data-types/type-characters.md)显式定义要分配给 `SByte`的文本值。 下面的示例将 `Short` 值分配给 `SByte`。 请注意，对于负数，必须设置数值文本的高序位字的高阶位。 对于我们的示例，这是文本 `Short` 值的位15。

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>编程提示

- **CLS 遵从性。** `SByte` 的数据类型不是[公共语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（cls）的一部分，因此符合 CLS 的代码无法使用使用它的组件。

- **扩大.** `SByte` 数据类型扩大到 `Short`、`Integer`、`Long`、`Decimal`、`Single`和 `Double`。 这意味着，可以将 `SByte` 转换为这些类型中的任何一种，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。

- **键入字符。** `SByte` 没有文本类型字符或标识符类型字符。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.SByte?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.SByte?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
