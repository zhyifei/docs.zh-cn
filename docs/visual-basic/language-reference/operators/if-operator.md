---
title: If 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 244c0598c65ba691decc09c36293799571211a40
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701156"
---
# <a name="if-operator-visual-basic"></a>If 运算符 (Visual Basic)
使用短路计算有条件地返回两个值中的一个值。 可以用三个参数或两个参数调用 `If` 运算符。  
  
## <a name="syntax"></a>语法  
  
```vb  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>如果调用运算符时有三个参数  
 使用三个参数调用 `If` 时，第一个参数的计算结果必须为可强制转换为 `Boolean` 的值。 该 @no__t 值将确定计算并返回其他两个参数中的哪一个。 以下列表仅适用于使用三个参数调用 @no__t 0 运算符的情况。  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`argument1`|必需。 `Boolean`。 确定要计算和返回的其他参数的值。|  
|`argument2`|必需。 `Object`。 如果 `argument1` 的计算结果为 `True`，则计算并返回。|  
|`argument3`|必需。 `Object`。 如果 `argument1` 的计算结果为 `False`，则计算并返回; 如果 @no__t 为[可以 @no__t 为 null 的可为 null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)的值[，则为](../../../visual-basic/language-reference/nothing.md)null。|  
  
 使用三个参数调用的 @no__t 0 运算符的工作方式类似于 `IIf` 函数，只不过它使用短路计算。 @No__t-0 函数始终计算其所有三个参数，而具有三个参数的 @no__t 1 运算符只计算两个参数中的两个。 计算第一个 @no__t 0 参数，并将结果强制转换为 `Boolean` 值，@no__t 为-2 或 @no__t 为3。 如果值为 `True`，则计算 @no__t 并返回其值，但不会计算 `argument3`。 如果 @no__t @no__t 表达式的值为-1，则计算 `argument3` 并且返回其值，但不计算 `argument2`。 以下示例说明了使用三个参数时 `If`：  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 下面的示例说明了短路计算的值。 该示例显示两次尝试将变量 `number` 除以变量 `divisor` （`divisor` 为零时除外）。 在这种情况下，应返回0，并且不会尝试执行除法，因为将导致运行时错误。 由于 @no__t 0 表达式使用短路计算，因此它将计算第二个或第三个参数，具体取决于第一个参数的值。 如果第一个参数为 true，则除数不为零，并且可以安全地计算第二个参数并执行除法运算。 如果第一个参数为 false，则只计算第三个参数，并返回0。 因此，当除数为0时，将不会尝试执行除法，也不会产生错误结果。 但是，因为 `IIf` 不使用短路计算，所以即使第一个参数为 false，也会计算第二个参数。 这将导致运行时被零除错误。  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a>如果运算符调用了两个自变量  
 可以省略 `If` 的第一个参数。 这使得仅使用两个参数即可调用运算符。 以下列表仅适用于调用带有两个参数的 `If` 运算符时。  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`argument2`|必需。 `Object`。 必须是一个引用或可以为 null 的类型。 当计算结果为除 @no__t 0 以外的任何值时，计算并返回该值。|  
|`argument3`|必需。 `Object`。 如果 `argument2` 的计算结果为 `Nothing`，则计算并返回。|  
  
 当省略 @no__t 0 参数时，第一个参数必须是引用或可以为 null 的类型。 如果第一个参数的计算结果为 `Nothing`，则返回第二个参数的值。 在所有其他情况下，返回第一个参数的值。 下面的示例说明了此计算的工作原理。  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
