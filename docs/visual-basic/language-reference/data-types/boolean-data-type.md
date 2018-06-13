---
title: Boolean 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 00f77fe5e98099868e02d74fe1adc7690cb95cca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590272"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean 数据类型 (Visual Basic)
只能是保留值`True`或`False`。 关键字`True`和`False`对应的两个状态`Boolean`变量。  
  
## <a name="remarks"></a>备注  
 使用[布尔数据类型 (Visual Basic 中)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)以包含两个状态如 true/false 的值是/否或开/关。  
  
 `Boolean` 的默认值为 `False`。  
  
 `Boolean` 值不会存储为数字，并且存储的值不应为等效于数字。 绝不应编写依赖于等效数字值的代码`True`和`False`。 只要有可能，应限制使用`Boolean`到为其设计的逻辑值的变量。  
  
## <a name="type-conversions"></a>类型转换  
 当 Visual Basic 数值数据类型将值转换为`Boolean`，0 会变为`False`和所有其他值将成为`True`。 当 Visual Basic 将转换`Boolean`为数字类型的值`False`变为 0 和`True`会变为-1。  
  
 你之间进行转换时`Boolean`值和数值数据类型，请记住情况下，.NET Framework 的转换方法不始终生成 Visual Basic 转换关键字与相同的结果。 这是因为 Visual Basic 转换可以保留与以前的版本兼容的行为。 有关详细信息，请参阅"布尔类型不会不转换为数值类型准确地"中[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。  
  
## <a name="programming-tips"></a>编程提示  
  
-   **负数。** `Boolean` 不是数值类型，不能表示为负值。 在任何情况下，不应使用`Boolean`来保存数值。  
  
-   **类型字符。** `Boolean` 不包含文本类型字符或标识符类型字符。  
  
-   **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Boolean?displayProperty=nameWithType> 结构。  
  
## <a name="example"></a>示例  
 在下面的示例中，`runningVB`是`Boolean`变量不同，后者将存储是/否设置一个简单。  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)
