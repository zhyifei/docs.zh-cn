---
title: Byte 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401351"
---
# <a name="byte-data-type-visual-basic"></a>字节数据类型（可视基本）

保存未签名的 8 位（1 字节）整数，其值范围为 0 到 255。

## <a name="remarks"></a>备注

使用`Byte`数据类型包含二进制数据。  
  
`Byte` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配

您可以通过为其分配十进制文本、`Byte`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。 如果积分文本超出 的范围`Byte`（即，如果它小于<xref:System.Byte.MinValue?displayProperty=nameWithType>或大于<xref:System.Byte.MaxValue?displayProperty=nameWithType>），则会发生编译错误。

在下面的示例中，等于 201 的整数表示为十进制、十六进制和二进制文本，从[整数](integer-data-type.md)隐式转换为`byte`值。

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> `&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>编程提示

- **负数。** 因为它是`Byte`无符号类型，它不能表示负数。 如果在计算为键入`-``Byte`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Short`第一个表达式。
  
- **格式转换。** 当 Visual Basic 读取或写入文件时，或者当它调用 DLL、方法和属性时，它可以在数据格式之间自动转换。 存储在变量和数组`Byte`中的二进制数据在此类格式转换期间保留。 不应将`String`变量用于二进制数据，因为其内容在 ANSI 和 Unicode 格式之间的转换过程中可能会损坏。

- **扩大。** 数据类型`Byte``Short`扩展到 、 `UShort` `Integer`、 、 `UInteger`、 `Long` `ULong`、 `Decimal` `Single`、 `Double`、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 这意味着您可以转换为`Byte`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。
  
- **键入字符。** `Byte`没有文本类型字符或标识符类型字符。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Byte?displayProperty=nameWithType> 结构。

## <a name="example"></a>示例

 在下面的示例中，`b`是一个`Byte`变量。 这些语句演示了变量的范围以及位移位运算符对变量的应用。

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>另请参阅

- <xref:System.Byte?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
