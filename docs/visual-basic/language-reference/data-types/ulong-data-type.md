---
title: ULong 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401315"
---
# <a name="ulong-data-type-visual-basic"></a>ULong 数据类型（可视基本）

持有未签名的 64 位（8 字节）整数，价值范围为 0 到 18，446，744，073，709，551，615（超过 1.84 倍 10 = 19）。

## <a name="remarks"></a>备注

使用`ULong`数据类型包含对于 的`UInteger`二进制数据太大或最大可能的无符号整数值。

`ULong` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配

您可以通过为其分配十进制文本、`ULong`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。 如果整数文本在 `ULong` 范围之外（即，如果它小于 <xref:System.UInt64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，表示为十进制、十六进制和二进制文本且等于 7,934,076,125 的整数被分配给 `ULong` 值。

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> `&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

数字文本还可以包括`UL`或`ul`[类型字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`ULong`数据类型，如下例所示。

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>编程提示

- **负数。** 因为它是`ULong`无符号类型，它不能表示负数。 如果在计算为键入`-``ULong`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Decimal`第一个表达式。

- **CLS 合规性。** 数据类型`ULong`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。

- **互操作注意事项。** 如果要与未为 .NET 框架编写的组件（例如自动化或 COM 对象）接口，请记住，例如在其他`ulong`环境中具有不同数据宽度（32 位）的类型。 如果要将 32 位参数传递给此类组件，请将其声明为`UInteger`托管 Visual `ULong` Basic 代码中而不是。

  此外，自动化不支持 Windows 95、Windows 98、Windows ME 或 Windows 2000 上的 64 位整数。 不能将 Visual Basic`ULong`参数传递给这些平台上的自动化组件。

- **扩大。** 数据类型`ULong`扩展到`Decimal`.`Single`和`Double`。 这意味着您可以转换为`ULong`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。

- **键入字符。** 将文本类型字符`UL`追加到文本强制它到`ULong`数据类型。 `ULong`没有标识符类型字符。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.UInt64?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.UInt64>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [如何：调用采用无符号类型的 Windows 函数](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
