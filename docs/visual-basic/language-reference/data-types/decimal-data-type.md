---
title: Decimal 数据类型 (Visual Basic)
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
ms.openlocfilehash: 892824b61cfb6a0172361d220c638cab0a78565d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700865"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal 数据类型 (Visual Basic)

保存有符号128位（16字节）的值，这些值表示按10的可变幂进行缩放的96位（12字节）整数。 缩放系数指定小数点右侧的数字位数;范围为0到28。 当小数位数为0（没有小数位数）时，可能的最大值为 +/-79228162514264337593543950335 （+/-7.9228162514264337593543950335E + 28）。 如果有28个小数位数，则最大值为 +/-7.9228162514264337593543950335，最小非零值为 +/-0.0000000000000000000000000001 （+/-1E-28）。

## <a name="remarks"></a>备注

@No__t 的数据类型为数字提供了最大的有效位数。 它最多支持29个有效位数，并可表示超过 7.9228 x 10 ^ 28 的值。 它特别适用于需要大量数字但不允许舍入误差的计算（例如财务）。

`Decimal` 的默认值为 0。

## <a name="programming-tips"></a>编程提示

- **Precision.** `Decimal` 不是浮点数据类型。 @No__t-0 结构保存二进制整数值，同时包含一个符号位和一个整数比例因子，用于指定值的哪一部分是小数部分。 因此，@no__t 0 数字在内存中的表示形式比浮点类型（`Single` 和 `Double`）更精确。

- **性能。** @No__t 的数据类型是所有数值类型最慢的一个。 在选择数据类型之前，应权衡精度与性能的重要性。

- **扩大.** @No__t 的数据类型扩大到 @no__t 或 @no__t。 这意味着可以将 `Decimal` 转换为这些类型中的任何一种，而不会遇到 @no__t 错误。

- **尾随零。** Visual Basic 不会在 @no__t 0 文本中存储尾随零。 但是，@no__t 0 变量保留了任何尾随零获取计算。 下面的示例阐释了这一点。

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  上述示例中 `MsgBox` 的输出如下所示：

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **键入字符。** 将文本类型字符 `D` 追加到文本会将其强制转换为 `Decimal` 数据类型。 将标识符类型字符 `@` 追加到任何标识符会将其强制转换为 `Decimal`。

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Decimal?displayProperty=nameWithType> 结构。

## <a name="range"></a>范围
 你可能需要使用 @no__t 类型的字符将较大的值分配给 @no__t 1 变量或常量。 此要求的原因是编译器将文本解释为 `Long`，除非文本类型字符跟随文本，如下面的示例所示。

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

@No__t 的声明不会产生溢出，因为赋给它的值落在 @no__t 的范围内。 可以将 `Long` 值分配给 @no__t 变量。

@No__t 的声明生成溢出错误，因为赋给它的值太大，无法用于 `Long`。 因为数值不能首先被解释为 `Long`，所以不能将其分配给 @no__t 变量。

对于 `bigDec3`，通过强制编译器将文本解释为 `Decimal` 而不是 @no__t 3 @no__t，可以解决此问题。

## <a name="see-also"></a>请参阅

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
