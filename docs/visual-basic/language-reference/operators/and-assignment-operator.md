---
title: '&amp;= 运算符'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350268"
---
# <a name="amp-operator-visual-basic"></a>&amp;= 运算符（Visual Basic）
将 `String` 表达式连接到 `String` 变量或属性，并将结果赋给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何 `String` 变量或属性。  
  
 `expression`  
 必需。 任何 `String` 表达式。  
  
## <a name="remarks"></a>备注  
 `&=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。 变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。 `&=` 运算符将其右侧的 `String` 表达式连接到其左边的 `String` 变量或属性，并将结果赋给它左侧的变量或属性。  
  
## <a name="overloading"></a>重载  
 可以*重载* [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 重载 `&` 运算符会影响 `&=` 运算符的行为。 如果你的代码在重载 `&`的类或结构上使用 `&=`，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `&=` 运算符将两个 `String` 变量连接起来，并将结果赋给第一个变量。  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>另请参阅

- [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [+= 运算符](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
