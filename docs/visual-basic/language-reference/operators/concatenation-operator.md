---
title: '&amp; 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: eac99ba38841f6972b5bdc8a01f816519af06288
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684666"
---
# <a name="amp-operator-visual-basic"></a>&amp; 运算符 (Visual Basic)
生成两个表达式的字符串串联。  
  
## <a name="syntax"></a>语法  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何`String`或`Object`变量。  
  
 `expression1`  
 必需。 具有数据类型扩大到任何表达式`String`。  
  
 `expression2`  
 必需。 具有数据类型扩大到任何表达式`String`。  
  
## <a name="remarks"></a>备注  
 如果的数据类型`expression1`或`expression2`不是`String`加宽到但`String`，它将转换为`String`。 如果任一数据类型不会扩大到`String`，编译器将生成错误。  
  
 数据类型`result`是`String`。 如果一个或两个表达式的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md) ，或者包含的值<xref:System.DBNull.Value?displayProperty=nameWithType>，它们被视为值为字符串""。  
  
> [!NOTE]
>  `&`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
> [!NOTE]
>  And 符 (&) 字符还可用来标识作为类型的变量`Long`。 有关详细信息，请参阅[类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)。  
  
## <a name="example"></a>示例  
 此示例使用`&`要强制执行字符串串联运算符。 结果是表示的两个字符串操作数串联的字符串值。  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [&= 运算符](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [在 Visual Basic 中的串联运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
