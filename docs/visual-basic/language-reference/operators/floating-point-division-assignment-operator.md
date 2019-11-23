---
title: /= 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592179"
---
# <a name="-operator-visual-basic"></a>/= 运算符 (Visual Basic)
将变量或属性的值除以表达式的值，并将浮点结果赋给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何数值变量或属性。  
  
 `expression`  
 必需。 任何数值表达式。  
  
## <a name="remarks"></a>备注  
 `/=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。 变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。  
  
 `/=` 运算符首先将变量或属性（位于运算符左侧）的值除以表达式的值（在运算符的右侧），而不是。 然后，运算符将该操作的浮点结果分配给变量或属性。  
  
 此语句将 `Double` 值分配给左侧的变量或属性。 如果 `On``Option Strict`，则 `variableorproperty` 必须是 `Double`。 如果 `Off``Option Strict`，Visual Basic 将执行隐式转换，并将生成的值分配给 `variableorproperty`，并在运行时使用可能的错误。 有关详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。  
  
## <a name="overloading"></a>重载  
 [/运算符（Visual Basic）](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)可以*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 重载 `/` 运算符会影响 `/=` 运算符的行为。 如果你的代码在重载 `/`的类或结构上使用 `/=`，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `/=` 运算符将一个 `Integer` 变量除以第二个变量，并将商分配给第一个变量。  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>另请参阅

- [/运算符（Visual Basic）](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [\\= 运算符](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
