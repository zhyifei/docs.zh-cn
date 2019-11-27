---
title: ^= 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5e8fc2b64b9e7c33483612071d338a0ee22768
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331298"
---
# <a name="-operator-visual-basic"></a>^= 运算符 (Visual Basic)
将变量或属性的值提升为表达式的幂，并将结果赋回给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何数值变量或属性。  
  
 `expression`  
 必需。 任何数值表达式。  
  
## <a name="remarks"></a>备注  
 `^=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。 变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。  
  
 `^=` 运算符首先引发变量或属性（位于运算符左侧）的值，以使表达式的值（在运算符的右侧）的值的幂。 然后，运算符将该操作的结果赋给变量或属性。  
  
 Visual Basic 总是对[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)执行幂运算。 任何不同类型的操作数都转换为 `Double`，结果始终 `Double`。  
  
 `expression` 的值可以是小数、负数或同时为两者。  
  
## <a name="overloading"></a>重载  
 [^ 运算符](../../../visual-basic/language-reference/operators/exponentiation-operator.md)可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 重载 `^` 运算符会影响 `^=` 运算符的行为。 如果你的代码在重载 `^`的类或结构上使用 `^=`，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `^=` 运算符将一个 `Integer` 变量的值提升为第二个变量的幂，并将结果赋给第一个变量。  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>另请参阅

- [^ 运算符](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
