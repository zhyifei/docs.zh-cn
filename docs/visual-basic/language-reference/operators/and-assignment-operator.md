---
title: '&amp; = 运算符（Visual Basic）'
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
ms.openlocfilehash: 82d791e5d66c301442c99d2cc73e3172c3e30f17
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591627"
---
# <a name="amp-operator-visual-basic"></a>&amp; = 运算符（Visual Basic）
将 @no__t 0 表达式连接到 @no__t 变量或属性，并将结果赋给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何 @no__t 的变量或属性。  
  
 `expression`  
 必需。 任何 `String` 表达式。  
  
## <a name="remarks"></a>备注  
 @No__t-0 运算符左侧的元素可以是简单的标量变量、属性或数组元素。 变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。 @No__t-0 运算符将其右侧的 `String` 表达式连接到其左侧的 `String` 变量或属性，并将结果赋给它左侧的变量或属性。  
  
## <a name="overloading"></a>重载  
 可以*重载* [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 重载 `&` 运算符会影响 @no__t 1 运算符的行为。 如果你的代码在重载 @no__t 的类或结构上使用 `&=`，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `&=` 运算符来连接两个 @no__t 1 变量，并将结果赋给第一个变量。  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [+= 运算符](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
