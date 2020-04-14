---
title: Decimal 数据类型
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243318"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal 数据类型 (Visual Basic)

保存由表示 96 位（12 字节）整数按 10 的可变次幂缩放所得的 128 位（16 字节）值。 缩放因子指定小数点右侧的数字数;范围从 0 到 28。 其刻度为 0（无小数位数），最大可能值为 +/-79，228，162，514，264，337，593，543，950，335 （+/-7.922816251423355353535535553355+28）。 对于 28 位小数，最大值为 +//922816251426433759355439555555555555303335，最小非零值为 +//00000000000000000000000001（+//-1E-28）。

## <a name="remarks"></a>备注

数据类型`Decimal`为数字提供最多数量的重要数字。 它最多支持 29 位有效数字，可以表示大于 7.9228 x 10^28 的值。 它特别适用于需要大量数字但不能容忍舍入错误的计算（如财务）。

`Decimal` 的默认值为 0。

## <a name="programming-tips"></a>编程提示

- **精度。** `Decimal`不是浮点数据类型。 结构`Decimal`包含二进制整数值，以及符号位和整数缩放因子，指定值的哪一部分是十进制分数。 因此，与浮`Decimal`点类型 （和`Single``Double`） 相比，数字在内存中的表示法更精确。

- **性能。** 数据类型`Decimal`是所有数值类型中最慢的。 在选择数据类型之前，应权衡精度与性能的重要性。

- **扩大。** 数据类型`Decimal`扩展到`Single`或`Double`。 这意味着您可以转换为`Decimal`其中任一<xref:System.OverflowException?displayProperty=nameWithType>类型，而不会遇到错误。

- **尾随零。** 视觉基础不会在`Decimal`文本中存储尾随零。 但是，`Decimal`变量保留在计算中获取的任何尾随零。 下面的示例对此进行了演示。

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  上`MsgBox`例中的输出如下：

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **键入字符。** 将文本类型字符 `D` 追加到文本会将其强制转换为 `Decimal` 数据类型。 将标识符类型字符 `@` 追加到任何标识符会将其强制转换为 `Decimal`。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Decimal?displayProperty=nameWithType> 结构。

## <a name="range"></a>范围

 您可能需要使用`D`类型字符将大值分配给`Decimal`变量或常量。 此要求是因为编译器将文本解释为`Long`除非文本类型字符遵循文本，如下例所示。

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

的声明`bigDec1`不会生成溢出，因为分配给它的值在`Long` 可以将`Long`该值分配给`Decimal`变量。

的声明`bigDec2`生成溢出错误，因为分配给它的值对于`Long`来说太大。 由于数字文本不能首先解释为 ，`Long`无法将其分配给`Decimal`变量。

对于`bigDec3`，文本类型字符`D`通过强制编译器将文本解释为`Decimal`而不是 解说，从而解决了问题。 `Long`

## <a name="see-also"></a>另请参阅

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
