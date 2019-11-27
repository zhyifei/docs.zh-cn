---
title: 布尔数据类型
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
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347845"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean 数据类型 (Visual Basic)

保存的值只能是 `True` 或 `False`。 关键字 `True` 和 `False` 对应于 `Boolean` 变量的两个状态。  
  
## <a name="remarks"></a>备注  

 使用[布尔数据类型（Visual Basic）](../../../visual-basic/language-reference/data-types/boolean-data-type.md)来包含双状态值，如 true/false、yes/no 或 on/off。  
  
 `Boolean` 的默认值为 `False`。  
  
 `Boolean` 值不会存储为数字，并且存储的值不应与数字等效。 永远不应编写依赖于 `True` 和 `False`等效数值的代码。 应尽可能将 `Boolean` 变量的使用限制为它们的设计逻辑值。  
  
## <a name="type-conversions"></a>类型转换  

 当 Visual Basic 将数值数据类型值转换为 `Boolean`时，0将变为 `False`，其他所有值将变为 `True`。 当 Visual Basic 将 `Boolean` 值转换为数值类型时，`False` 将变为0，`True` 将为-1。  
  
 在 `Boolean` 值和数值数据类型之间进行转换时，请记住，.NET Framework 转换方法并不总是产生与 Visual Basic 转换关键字相同的结果。 这是因为 Visual Basic 转换会保持与以前版本兼容的行为。 有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)中的 "布尔类型不会精确转换为数值类型"。  
  
## <a name="programming-tips"></a>编程提示  
  
- **负数。** `Boolean` 不是数值类型，且不能表示负值。 在任何情况下，不应使用 `Boolean` 来保存数值。  
  
- **键入字符。** `Boolean` 没有文本类型字符或标识符类型字符。  
  
- **Framework 类型。** .NET Framework 中的对应类型是 <xref:System.Boolean?displayProperty=nameWithType> 结构。  
  
## <a name="example"></a>示例  

 在下面的示例中，`runningVB` 是一个 `Boolean` 变量，它存储了一个简单的 "是/否" 设置。  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Boolean?displayProperty=nameWithType>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)
