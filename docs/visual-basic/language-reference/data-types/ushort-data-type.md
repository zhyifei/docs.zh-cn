---
title: UShort 数据类型
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
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401309"
---
# <a name="ushort-data-type-visual-basic"></a>UShort 数据类型（可视基本）

保存未签名的 16 位（2 字节）整数，其值范围为 0 到 65，535。  
  
## <a name="remarks"></a>备注

 使用`UShort`数据类型包含的二进制数据太大。 `Byte`  
  
 `UShort` 的默认值为 0。  

## <a name="literal-assignments"></a>文本分配

您可以通过为其分配十进制文本、`UShort`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。 如果整数文本在 `UShort` 范围之外（即，如果它小于 <xref:System.UInt16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在下面的示例中，等于 65，034 的整数，表示为十进制、十六进制和二进制文本`UShort`。
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> `&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

数字文本还可以包括`US`或`us`[类型字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`UShort`数据类型，如下例所示。

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>编程提示
  
- **负数。** 因为它是`UShort`无符号类型，它不能表示负数。 如果在计算为键入`-``UShort`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Integer`第一个表达式。  
  
- **CLS 合规性。** 数据类型`UShort`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。
  
- **扩大。** 数据类型`UShort`扩展到`Integer`、、、、、、、、`Single``Double``UInteger``Long``ULong``Decimal`和 。 这意味着您可以转换为`UShort`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。  
  
- **键入字符。** 将文本类型字符`US`追加到文本强制它到`UShort`数据类型。 `UShort`没有标识符类型字符。  
  
- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.UInt16?displayProperty=nameWithType> 结构。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.UInt16>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [如何：调用采用无符号类型的 Windows 函数](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
