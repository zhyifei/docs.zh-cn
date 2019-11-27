---
title: << 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350984"
---
# <a name="-operator-visual-basic"></a>\<\< 运算符（Visual Basic）
对位模式执行算术左移位运算。  
  
## <a name="syntax"></a>语法  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 整数数值。 移位位模式的结果。 数据类型与 `pattern`的数据类型相同。  
  
 `pattern`  
 必需。 整数数值表达式。 要移动的位模式。 数据类型必须是整型（`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`或 `ULong`）。  
  
 `amount`  
 必需。 数值表达式。 要移位位模式的位数。 数据类型必须 `Integer` 或扩大到 `Integer`。  
  
## <a name="remarks"></a>备注  
 算术移位不是循环的，这意味着，不会在另一端重新引入结果的末尾以外的位。 在算术左移位中，将丢弃超出结果数据类型范围的位，并将在右侧空出的位位置设置为零。  
  
 若要防止移位比结果可以容纳的位数多，Visual Basic 用与 `pattern`的数据类型对应的大小掩码屏蔽 `amount` 的值。 这些值的二进制和均用于移位量。 大小掩码如下：  
  
|`pattern` 的数据类型|大小掩码（十进制）|大小掩码（十六进制）|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 如果 `amount` 为零，则 `result` 的值与 `pattern`的值相同。 如果 `amount` 为负数，则将它作为无符号值，并使用适当的大小掩码屏蔽。  
  
 算术移位从不产生溢出异常。  
  
> [!NOTE]
> 可以*重载*`<<` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果代码对这样的类或结构使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `<<` 运算符对整数值执行算术左移位。 结果始终与要移动的表达式的数据类型相同。  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 上述示例的结果如下所示：  
  
- `result1` 为192（0000 0000 1100 0000）。  
  
- `result2` 为3072（0000 1100 0000 0000）。  
  
- `result3` 为-32768 （1000 0000 0000 0000）。  
  
- `result4` 为384（0000 0001 1000 0000）。  
  
- `result5` 为0（向左移动15个位置）。  
  
 `result4` 的移位量计算为17和15，这等于1。  
  
## <a name="see-also"></a>另请参阅

- [移位运算符](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<<= 运算符](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
