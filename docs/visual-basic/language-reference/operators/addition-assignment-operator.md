---
title: += 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 249a19abfb08677c01ac4cc484d049a7ed1a983c
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591649"
---
# <a name="-operator-visual-basic"></a>+= 运算符 (Visual Basic)
将数值表达式的值添加到数值变量或属性的值，并将结果赋给变量或属性。 还可用于将 @no__t 0 表达式连接到 @no__t 1 变量或属性，并将结果赋给变量或属性。  
  
## <a name="syntax"></a>语法  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>部件  
 `variableorproperty`  
 必需。 任何数值或 `String` 变量或属性。  
  
 `expression`  
 必需。 任何数值或 @no__t 0 表达式。  
  
## <a name="remarks"></a>备注  
 @No__t-0 运算符左侧的元素可以是简单的标量变量、属性或数组元素。 变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。  
  
 @No__t-0 运算符将其右侧的值添加到其左侧的变量或属性，并将结果赋给它左侧的变量或属性。 @No__t-0 运算符还可用于将其右侧的 @no__t 1 表达式连接到左侧的 `String` 变量或属性，并将结果分配给其左侧的变量或属性。  
  
> [!NOTE]
> 使用 @no__t 0 运算符时，可能无法确定是进行加法还是字符串串联。 将 `&=` 运算符用于串联以消除多义性，并提供自文档代码。  
  
 如果编译环境强制执行严格语义，则此赋值运算符隐式执行扩大但不进行收缩转换。 有关这些转换的详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。 有关严格语义和许可语义的详细信息，请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。  
  
 如果允许使用可许可语义，@no__t 0 运算符将隐式执行与 `+` 运算符执行的各种字符串和数值转换。 有关这些转换的详细信息，请参阅[+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)。  
  
## <a name="overloading"></a>重载  
 @No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 重载 `+` 运算符会影响 @no__t 1 运算符的行为。 如果你的代码在重载 @no__t 的类或结构上使用 `+=`，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `+=` 运算符将一个变量的值与另一个变量的值进行组合。 第一部分将 `+=` 与数值变量一起使用，以将一个值添加到另一个值。 第二部分将 `+=` 与 @no__t 变量一起使用，以将一个值与另一个值连接起来。 在这两种情况下，都会将结果赋给第一个变量。  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 @No__t 的值现在为13，`str1` 的值现在为 "103"。  
  
## <a name="see-also"></a>请参阅

- [+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)
- [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [串联运算符](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [语句](../../../visual-basic/programming-guide/language-features/statements.md)
