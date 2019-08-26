---
title: / 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: d30d871d48bc87e050a072cd01a38065be20616c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933257"
---
# <a name="-operator-visual-basic"></a>/ 运算符 (Visual Basic)
使两个数字相除, 返回浮点结果。  
  
## <a name="syntax"></a>语法  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>部件  
 `expression1`  
 必需。 任何数值表达式。  
  
 `expression2`  
 必需。 任何数值表达式。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型, 包括无符号和浮点类型和`Decimal`。  
  
## <a name="result"></a>结果  
 结果是`expression1` `expression2`除以的全部商, 包括余数。  
  
 [\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回整数商, 这会删除余数。  
  
## <a name="remarks"></a>备注  
 结果的数据类型取决于操作数的类型。 下表显示了如何确定结果的数据类型。  
  
|操作数数据类型|Result 数据类型|  
|------------------------|----------------------|  
|这两个表达式均为整型数据类型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)、 [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)、 [Short](../../../visual-basic/language-reference/data-types/short-data-type.md)、 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)、 [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)、 [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)、 [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)、 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|一个表达式是[单一](../../../visual-basic/language-reference/data-types/single-data-type.md)数据类型, 另一个表达式不是[双精度](../../../visual-basic/language-reference/data-types/double-data-type.md)型|`Single`|  
|一个表达式是[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型, 另一个表达式不是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)或[双精度](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|其中一个表达式为[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型|`Double`|  
  
 在执行除法运算之前, 所有整数数值表达式都将`Double`扩展到。 如果将结果赋给整数数据类型, Visual Basic 会尝试将结果从`Double`转换为该类型。 如果结果不适合该类型, 这可能会引发异常。 具体而言, 请参阅此帮助页上的 "尝试被零除"。  
  
 如果`expression1` 或`expression2`的计算结果不为[空](../../../visual-basic/language-reference/nothing.md), 则将其视为零。  
  
## <a name="attempted-division-by-zero"></a>尝试被零除  
 如果`expression2`计算结果为零, `/`则运算符的行为不同于不同的操作数数据类型。 下表显示了可能的行为。  
  
|操作数数据类型|为零`expression2`时的行为|  
|------------------------|---------------------------------------|  
|浮点 (`Single`或`Double`)|如果<xref:System.Double.PositiveInfinity> <xref:System.Double.NegativeInfinity> <xref:System.Double.NaN>也为零,则返回无穷(or),或(不是数字)`expression1`|  
|`Decimal`|却<xref:System.DivideByZeroException>|  
|整数 (有符号或无符号)|尝试转换回整型类型会引发<xref:System.OverflowException> , 因为整型类型不<xref:System.Double.PositiveInfinity>能<xref:System.Double.NegativeInfinity>接受、或<xref:System.Double.NaN>|  
  
> [!NOTE]
> 运算符可以重载, 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义其行为。 `/` 如果你的代码在该类或结构上使用此运算符, 请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 此示例使用`/`运算符来执行浮点除法。 结果是两个操作数的商。  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 前面的示例中的表达式返回值2.5 和3.333333。 请注意, 结果始终是浮点型 (`Double`), 即使两个操作数都是整数常量。  
  
## <a name="see-also"></a>请参阅

- [/= 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
