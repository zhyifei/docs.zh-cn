---
title: '* 运算符'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 4f6a8ea2c5f4e23791afdfe98d2a08bf67219048
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348368"
---
# <a name="-operator-visual-basic"></a>* 运算符 (Visual Basic)
将两个数字相乘。  
  
## <a name="syntax"></a>语法  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`number1`|必需。 任何数值表达式。|  
|`number2`|必需。 任何数值表达式。|  
  
## <a name="result"></a>结果  
 结果是 `number1` 和 `number2`的产品。  
  
## <a name="supported-types"></a>支持的类型  
 所有数值类型，包括无符号和浮点类型以及 `Decimal`。  
  
## <a name="remarks"></a>备注  
 结果的数据类型取决于操作数的类型。 下表显示了如何确定结果的数据类型。  
  
|操作数数据类型|Result 数据类型|  
|---|---|  
|这两个表达式均为整型数据类型（[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)、 [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)、 [Short](../../../visual-basic/language-reference/data-types/short-data-type.md)、 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)、 [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)、 [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)、 [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)、 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)）|适用于 `number1` 和 `number2`的数据类型的数值数据类型。 请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "整数算法" 表。|  
|两个表达式都是[小数](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|这两个表达式都是[单](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|这两个表达式都是浮点数据类型（`Single` 或[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)），但不是两者都 `Single` （注意 `Decimal` 不是浮点数据类型）|`Double`|  
  
 如果表达式的计算结果不为[空](../../../visual-basic/language-reference/nothing.md)，则将其视为零。  
  
## <a name="overloading"></a>重载  
 可以*重载*`*` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 此示例使用 `*` 运算符将两个数字相乘。 结果就是两个操作数的乘积。  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>另请参阅

- [*= 运算符](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
