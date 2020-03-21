---
title: Long 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401399"
---
# <a name="long-data-type-visual-basic"></a>长数据类型（可视基本）

持有已签名的 64 位（8 字节）整数，价值范围为 -9，223，372，036，854，775，808 到 9，223，372，036，854，775，807 （9.2...E=18）。

## <a name="remarks"></a>备注

使用`Long`数据类型包含太大而不适合数据类型的`Integer`整数。

`Long` 的默认值为 0。

## <a name="literal-assignments"></a>文本分配

您可以通过为其分配十进制文本、`Long`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。 如果整数文本在 `Long` 范围之外（即，如果它小于 <xref:System.Int64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int64.MaxValue?displayProperty=nameWithType>），会发生编译错误。

在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `Long` 值。

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> `&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。 十进制文本没有前缀。

从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。 例如：

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

数字文本还可以包括`L`表示`Long`数据类型[的类型字符](../../programming-guide/language-features/data-types/type-characters.md)，如下例所示。

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>编程提示

- **互操作注意事项。** 如果要与未为 .NET 框架编写的组件（例如自动化或 COM 对象）接口，请记住，`Long`在其他环境中具有不同的数据宽度（32 位）。 如果要将 32 位参数传递给此类组件，请将其声明为`Integer`而不是在新的 Visual `Long` Basic 代码中。

- **扩大。** 数据类型`Long`扩展到`Decimal`或`Single`。 `Double` 这意味着，你可以将 `Long` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。

- **键入字符。** 将文本类型字符 `L` 追加到文本会将其强制转换为 `Long` 数据类型。 将标识符类型字符 `&` 追加到任何标识符会将其强制转换为 `Long`。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Int64?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.Int64>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [整数数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
