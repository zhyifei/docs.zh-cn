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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401381"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte 数据类型（可视基本）

保留在 -128 到 127 之间的值范围的已签名 8 位（1 字节）整数。

## <a name="remarks"></a>备注

使用`SByte`数据类型包含不需要 的完整数据宽度`Integer`甚至一半数据宽度的`Short`整数值。 在某些情况下，通用语言运行时可能能够将`SByte`变量紧密打包在一起并节省内存消耗。

`SByte` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配

您可以通过为其分配十进制文本、`SByte`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。

在下面的示例中，等于 -102 的整数，表示为十进制、十六进制和二进制文本`SByte`。 此示例要求您使用`/removeintchecks`编译器开关进行编译。

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> `&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

如果整数文本在 `SByte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.SByte.MaxValue?displayProperty=nameWithType>），会发生编译错误。 当整数文本没有后缀时，将推断出[整数](integer-data-type.md)。 如果整数文本超出`Integer`类型的范围，则推断为[Long。](long-data-type.md) 这意味着，在前面的示例中，数字文本`0x9A`和`0b10011010`转换为 32 位签名整数，值为 156，超过<xref:System.SByte.MaxValue?displayProperty=nameWithType>。 要成功编译像这样将非十进制整数分配给 的代码`SByte`，可以执行以下任一操作：

- 通过编译`/removeintchecks`编译器开关禁用整数边界检查。

- 使用[类型字符](../../programming-guide/language-features/data-types/type-characters.md)显式定义要分配给 的文本`SByte`值。 下面的示例将负文本`Short`值分配给 。 `SByte` 请注意，对于负数，必须设置数字文本的高阶字的高阶位。 在我们的示例中，这是文本`Short`值的第 15 位。

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>编程提示

- **CLS 合规性。** 数据类型`SByte`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。

- **扩大。** 数据类型`SByte`扩展到`Short`、、、、、、、`Integer``Long``Decimal``Single`和`Double`。 这意味着您可以转换为`SByte`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。

- **键入字符。** `SByte`没有文本类型字符或标识符类型字符。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.SByte?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.SByte?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [整数数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
