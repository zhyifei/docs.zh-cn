---
title: OrElse 运算符
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 361de44711c3b41411f2fa1dd81a3dd8db6b01e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348231"
---
# <a name="orelse-operator-visual-basic"></a>OrElse 运算符 (Visual Basic)
对两个表达式执行短路包含逻辑析取。  
  
## <a name="syntax"></a>语法  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何 `Boolean` 表达式。  
  
 `expression1`  
 必需。 任何 `Boolean` 表达式。  
  
 `expression2`  
 必需。 任何 `Boolean` 表达式。  
  
## <a name="remarks"></a>备注  
 如果编译后的代码可以根据另一个表达式的结果跳过对一个表达式的计算，则将逻辑运算称为*短路*。 如果第一个表达式的计算结果确定了运算的最终结果，则不需要计算第二个表达式，因为它不能更改最终结果。 如果绕过的表达式较复杂，或者它涉及过程调用，则短路可以提高性能。  
  
 如果任意一个或两个表达式的计算结果为 `True`，`result` `True`。 下表说明了如何确定 `result`。  
  
|如果 `expression1` 为|并且 `expression2` 为|`result` 的值是|  
|-------------------------|--------------------------|------------------------------|  
|`True`|（未计算）|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>数据类型  
 仅为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)定义 `OrElse` 运算符。 Visual Basic 在计算表达式之前，根据需要将每个操作数转换为 `Boolean`。 如果将结果赋给数值类型，Visual Basic 会将其从 `Boolean` 转换为该类型，以便 `False` 成为 `0`，`True` 变为 `-1`。
有关详细信息，请参阅[布尔类型转换](../data-types/boolean-data-type.md#type-conversions)。
  
## <a name="overloading"></a>重载  
 可以*重载* [Or 运算符](../../../visual-basic/language-reference/operators/or-operator.md)和[IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 重载 `Or` 和 `IsTrue` 运算符会影响 `OrElse` 运算符的行为。 如果你的代码对 `Or` 和 `IsTrue`重载的类或结构使用 `OrElse`，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用 `OrElse` 运算符对两个表达式执行逻辑析取。 结果是一个 `Boolean` 值，该值表示两个表达式之一是否为 true。 如果 `True`第一个表达式，则不计算第二个表达式。  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 前面的示例分别产生 `True`、`True`和 `False` 的结果。 在 `firstCheck`的计算中，不计算第二个表达式，因为第一个表达式已 `True`。 但是，在 `secondCheck`的计算中计算第二个表达式。  
  
## <a name="example"></a>示例  
 下面的示例显示了包含两个过程调用的 `If`...`Then` 语句。 如果第一个调用返回 `True`，则不会调用第二个过程。 如果第二个过程执行的重要任务应始终在此部分代码运行时执行，这可能会产生意外的结果。  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>另请参阅

- [逻辑/按位运算符（Visual Basic）](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Or 运算符](../../../visual-basic/language-reference/operators/or-operator.md)
- [IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
