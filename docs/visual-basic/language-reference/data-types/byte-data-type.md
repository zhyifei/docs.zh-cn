---
title: "Byte 数据类型 (Visual Basic)"
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02234afc0dc51a2c1338cdd16d1f97765f64b45e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="byte-data-type-visual-basic"></a>Byte 数据类型 (Visual Basic)
包含无符号的 8 位 （1 个字节） 整数，值的范围从 0 到 255 之间。

## <a name="remarks"></a>备注

使用`Byte`要包含二进制数据的数据类型。  
  
`Byte` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配

你可以声明并初始化`Byte`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。 如果整型文本之外的范围，则`Byte`(即，如果它是小于<xref:System.Byte.MinValue?displayProperty=nameWithType>或大于<xref:System.Byte.MaxValue?displayProperty=nameWithType>)，会发生编译错误。

在下面的示例中，整数等于 201，表示为十进制数字，十六进制，和从隐式转换二进制文本[整数](integer-data-type.md)到`byte`值。

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> 使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。 例如:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>编程提示

-   **负数。** 因为`Byte`是无符号的类型，它不能表示为负数。 如果你使用一元负 (`-`) 运算符的表达式的计算结果为键入`Byte`，Visual Basic 将转换为表达式`Short`第一个。
  
-   **格式转换。** 当 Visual Basic 中读取或写入文件，或者它将调用 Dll、 方法和属性，它可以自动将数据格式之间转换。 二进制数据存储在`Byte`这种格式转换过程中会保留变量和数组。 不应使用`String`变量对二进制数据，因为其内容可能损坏 ANSI 和 Unicode 格式之间转换的过程。

-   **扩大转换。** `Byte`数据类型加宽到`Short`， `UShort`， `Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，或`Double`。 这意味着你可以将转换`Byte`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。
  
-   **类型字符。** `Byte`不包含文本类型字符或标识符类型字符。

-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Byte?displayProperty=nameWithType> 结构。

## <a name="example"></a>示例

 在下面的示例中，`b`是`Byte`变量。 语句演示了变量范围和移位运算符应用于它。

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>请参阅

 <xref:System.Byte?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
