---
title: UInteger 数据类型
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
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401375"
---
# <a name="uinteger-data-type"></a>UInteger 数据类型

保存未签名的 32 位（4 字节）整数，其值范围为 0 到 4，294，967，295。

## <a name="remarks"></a>备注

数据类型`UInteger`提供最有效的数据宽度中的最大未签名值。

`UInteger` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配

您可以通过为其分配十进制文本、`UInteger`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。 如果整数文本在 `UInteger` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `UInteger` 值。

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> `&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

数字文本还可以包括`UI`或`ui`[类型字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`UInteger`数据类型，如下例所示。

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>编程提示

和`UInteger``Integer`数据类型在 32 位处理器上提供最佳性能，因为较小的整数类型 （、、`UShort``Short``Byte`和`SByte`）即使使用较少的位，也需要更多的时间来加载、存储和提取。

- **负数。** 因为它是`UInteger`无符号类型，它不能表示负数。 如果在计算为键入`-``UInteger`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Long`第一个表达式。

- **CLS 合规性。** 数据类型`UInteger`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。

- **互操作注意事项。** 如果要与未为 .NET 框架编写的组件（例如自动化或 COM 对象）接口，请记住，例如在其他`uint`环境中具有不同数据宽度（16 位）的类型。 如果要将 16 位参数传递给此类组件，请将其声明为`UShort`托管 Visual `UInteger` Basic 代码中而不是。

- **扩大。** 数据类型`UInteger`扩展到`Long` `ULong`、、、`Decimal``Single`和`Double`。 这意味着您可以转换为`UInteger`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。

- **键入字符。** 将文本类型字符`UI`追加到文本强制它到`UInteger`数据类型。 `UInteger`没有标识符类型字符。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.UInt32?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.UInt32>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [如何：调用采用无符号类型的 Windows 函数](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
