---
title: '&amp; 运算符'
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
ms.openlocfilehash: 4cae7e59083890e82d754bdaa58942c2224357b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336058"
---
# <a name="amp-operator-visual-basic"></a>&amp; 运算符（Visual Basic）
生成两个表达式的字符串串联。  
  
## <a name="syntax"></a>语法  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何 `String` 或 `Object` 变量。  
  
 `expression1`  
 必需。 数据类型扩大到 `String`的任何表达式。  
  
 `expression2`  
 必需。 数据类型扩大到 `String`的任何表达式。  
  
## <a name="remarks"></a>备注  
 如果 `expression1` 或 `expression2` 的数据类型未 `String` 但扩大到 `String`，则将其转换为 `String`。 如果数据类型中的任何一种不能扩大到 `String`，则编译器将生成错误。  
  
 `result` 的数据类型为 `String`。 如果一个或两个表达式的计算[结果都不为 <xref:System.DBNull.Value?displayProperty=nameWithType>](../../../visual-basic/language-reference/nothing.md) ，则将其视为值为 "" 的字符串。  
  
> [!NOTE]
> 可以*重载*`&` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
> [!NOTE]
> 与号（&）字符也可用于将变量标识为类型 `Long`。 有关详细信息，请参阅[类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)。  
  
## <a name="example"></a>示例  
 此示例使用 `&` 运算符强制字符串连接。 结果是一个表示两个字符串操作数串联的字符串值。  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- [&= 运算符](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的串联运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
