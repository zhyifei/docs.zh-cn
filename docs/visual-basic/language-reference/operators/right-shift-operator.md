---
title: '&gt;&gt; 运算符 (Visual Basic)'
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
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt; 运算符 (Visual Basic)
对位模式执行算术右移位运算。  
  
## <a name="syntax"></a>语法  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必须的。 整型数值。 移位位模式的结果。 数据类型是相同的`pattern`。  
  
 `pattern`  
 必须的。 整型数值表达式。 要移动的位模式。 数据类型必须为整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。  
  
 `amount`  
 必须的。 数值表达式。 要位移位模式的位数数。 数据类型必须为`Integer`或扩大到`Integer`。  
  
## <a name="remarks"></a>备注  
 算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。 在算术右移位运算移出最右边的位位置的位将被丢弃，并最左侧 （符号） 位传播到左侧空出的位位置。 这意味着，如果`pattern`具有负值，空出的位置将设置为一个; 否则设置为零。  
  
 请注意，数据类型`Byte`， `UShort`， `UInteger`，和`ULong`是无符号整数，因此没有任何符号位传播。 如果`pattern`的任何无符号类型，空出的位置将始终设置为零。  
  
 若要防止移位的更多位数超过结果所能容纳，Visual Basic 使用的值`amount`使用对应的数据类型的大小掩码`pattern`。 这些值的二进制 AND 用于位移量。 大小掩码如下所示：  
  
|数据类型 `pattern`|大小掩码 （十进制）|大小掩码 （十六进制）|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 如果`amount`为零的值`result`的值是否相同`pattern`。 如果`amount`是负数，它采用无符号值并使用适当的大小掩码进行屏蔽。  
  
 算术移位永远不会生成溢出异常。  
  
## <a name="overloading"></a>重载  
 `>>`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`>>`运算符对整型值执行算术右移位。 结果始终具有相同的数据被移位的表达式的类型。  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 上述示例的结果如下所示：  
  
-   `result1` 为 2560 (0000 1010年 0000 0000)。  
  
-   `result2` 为 160 (0000 0000 1010年 0000)。  
  
-   `result3` 为 2 (0000 0000 0000 0010)。  
  
-   `result4` 为 640 (0000 0010 1000年 0000)。  
  
-   `result5` 为 0 （向右移位 15 位数）。  
  
 移位量`result4`的计算方法为 18 和 15，等于 2。  
  
 下面的示例演示上一个负数值的算术移位。  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 上述示例的结果如下所示：  
  
-   `negresult1` 是-512 (1111年 1110年 0000 0000)。  
  
-   `negresult2` 为-1 （传播符号位）。  
  
## <a name="see-also"></a>请参阅  
 [移位运算符](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [>>= 运算符](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
