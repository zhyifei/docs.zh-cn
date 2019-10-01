---
title: '>> 运算符（Visual Basic）'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 337d651e831dc2ab132056f6e9a1f2b5300bf7f8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701332"
---
# <a name="-operator-visual-basic"></a>> > 运算符（Visual Basic）
对位模式执行算术右移位运算。  
  
## <a name="syntax"></a>语法  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 整数数值。 移位位模式的结果。 数据类型与的数据类型相同`pattern`。  
  
 `pattern`  
 必需。 整数数值表达式。 要移动的位模式。 数据类型`SByte`必须为整型类型（、 `UShort` `Integer` `Short` 、、`ULong`、、 `UInteger` 、或）。`Long` `Byte`  
  
 `amount`  
 必需。 数值表达式。 要移位位模式的位数。 数据类型必须`Integer`为或扩大到`Integer`。  
  
## <a name="remarks"></a>备注  
 算术移位不是循环的，这意味着，不会在另一端重新引入结果的末尾以外的位。 在算术右移位中，将丢弃超出最右位位置的位，并将最左侧的（符号）位传播到左端空出的位位置。 这意味着，如果 `pattern` 的值为负值，则空出的位置设置为 1;否则，它们会被设置为零。  
  
 请注意，数据类型 `Byte`、`UShort`、`UInteger` 和 `ULong` 是无符号的，因此没有要传播的符号位。 如果 @no__t 为任何无符号类型，则空出的位置始终设置为零。  
  
 若要防止超过结果的移位量，请 Visual Basic 使用与 @no__t 的数据类型相对应的大小掩码来屏蔽 @no__t 的值。 这些值的二进制和均用于移位量。 大小掩码如下：  
  
|@No__t 的数据类型-0|大小掩码（十进制）|大小掩码（十六进制）|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`， `Byte`|7|& H00000007|  
|`Short`， `UShort`|15|& H0000000F|  
|`Integer`， `UInteger`|31|& H0000001F|  
|`Long`， `ULong`|63|& H0000003F|  
  
 如果 @no__t 为零，`result` 的值与 @no__t 的值相同。 如果 `amount` 为负数，则将其视为无符号值，并使用适当的大小掩码掩码。  
  
 算术移位从不产生溢出异常。  
  
## <a name="overloading"></a>重载  
 @No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `>>` 运算符对整数值执行算术右移位运算。 结果始终与要移动的表达式的数据类型相同。  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 上述示例的结果如下所示：  
  
- @no__t 为2560（0000 1010 0000 0000）。  
  
- @no__t 为160（0000 0000 1010 0000）。  
  
- @no__t 为2（0000 0000 0000 0010）。  
  
- @no__t 为640（0000 0010 1000 0000）。  
  
- @no__t 为0（向右移动15个位置）。  
  
 @No__t 的移位量计算为18和15，这等于2。  
  
 下面的示例演示如何对负值进行算术移位运算。  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 上述示例的结果如下所示：  
  
- `negresult1` 为-512 （1111 1110 0000 0000）。  
  
- `negresult2` 为-1 （传播符号位）。  
  
## <a name="see-also"></a>请参阅

- [移位运算符](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [>>= 运算符](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
