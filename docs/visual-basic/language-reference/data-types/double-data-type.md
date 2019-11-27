---
title: Double 数据类型
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 347b5c7b7af4c4aafec0f91aca46a8cf640236b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344015"
---
# <a name="double-data-type-visual-basic"></a>Double 数据类型 (Visual Basic)

为负值以及从 4.94065645841246544 E-324 到 1.79769313486231570 E + 308 的值，保留已签名的 IEEE 64 位（8字节）双精度浮点数，其值范围为-1.79769313486231570 E + 308 到-4.94065645841246544 E-324正值。 双精度数字存储实数的近似值。

## <a name="remarks"></a>备注

`Double` 数据类型为数字提供最大和最小的度。

`Double` 的默认值为 0。

## <a name="programming-tips"></a>编程提示

- **Precision.** 使用浮点数时，请记住，它们在内存中不一定有精确的表示形式。 这可能会导致某些操作产生意外结果，如值比较和 `Mod` 运算符。 有关详细信息，请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。

- **尾随零。** 浮点数据类型不包含尾随零字符的任何内部表示形式。 例如，它们不区分4.2000 和4.2。 因此，在显示或打印浮点值时，不会出现尾随零字符。

- **键入字符。** 将文本类型字符 `R` 追加到文本会将其强制转换为 `Double` 数据类型。 例如，如果整数值后跟 `R`，则该值将更改为 `Double`。

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  将标识符类型字符 `#` 追加到任何标识符会将其强制转换为 `Double`。 在下面的示例中，变量 `num` 类型化为 `Double`：

  ```vb
  Dim num# = 3
  ```

- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Double?displayProperty=nameWithType> 结构。

## <a name="see-also"></a>另请参阅

- <xref:System.Double?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal 数据类型](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
