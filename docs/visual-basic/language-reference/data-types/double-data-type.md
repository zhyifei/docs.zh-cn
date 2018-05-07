---
title: Double 数据类型 (Visual Basic)
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
ms.openlocfilehash: c2d3d7d360ccb240bafbe0e19e9f396adfba7f7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="double-data-type-visual-basic"></a>Double 数据类型 (Visual Basic)
保留带符号的 IEEE 64 位 （8 字节） 双精度浮点数，从-1.79769313486231570 e + 308 到-的值的范围 4.94065645841246544 e-324 负值和 4.94065645841246544 e-324 1.79769313486231570 e + 308 到正值。 双精度数字存储实际数目的近似值。  
  
## <a name="remarks"></a>备注  
 `Double`数据类型提供了大量的最大和最小可能大量度。  
  
 `Double` 的默认值为 0。  
  
## <a name="programming-tips"></a>编程提示  
  
-   **精度。** 在使用浮点数，请记得在内存中不始终具有精确的表示形式。 这可能导致意外的结果从某些操作，如值比较和`Mod`运算符。 有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。  
  
-   **尾随零。** 浮点数据类型不具有任何内部表示形式尾随零字符。 例如，它们不区分 4.2000 和 4.2。 因此，尾随零字符不显示时显示或打印的浮点值。  
  
-   **类型字符。** 将文本类型字符 `R` 追加到文本会将其强制转换为 `Double` 数据类型。 例如，如果一个整数值后, 跟`R`的值更改为`Double`。  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     将标识符类型字符 `#` 追加到任何标识符会将其强制转换为 `Double`。 在下面的示例中，变量`num`被类型化为`Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Double?displayProperty=nameWithType> 结构。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Double?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Decimal 数据类型](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Single 数据类型](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
