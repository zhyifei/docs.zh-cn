---
title: If 运算符
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
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249482"
---
# <a name="if-operator-visual-basic"></a>If 运算符 (Visual Basic)

使用短路评估有条件地返回两个值之一。 可以使用`If`三个参数或两个参数调用运算符。

## <a name="syntax"></a>语法

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>如果运算符使用三个参数调用

使用`If`三个参数调用时，第一个参数必须计算为可以转换为 的值`Boolean`。 该`Boolean`值将确定计算并返回其他两个参数中的哪一个。 仅当使用三个参数调用运算符`If`时，以下列表才适用。

### <a name="parts"></a>组成部分

|术语|定义|
|---|---|
|`argument1`|必需。 `Boolean`. 确定要计算和返回的其他参数。|
|`argument2`|必需。 `Object`. 如果`argument1`评估为`True`，则评估并返回。|
|`argument3`|必需。 `Object`. `argument1`如果计算为`False`或`argument1`如果为"[无"](../../../visual-basic/language-reference/nothing.md)[的可无变量](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean`，则计算并返回。|

使用`If`三个参数调用的运算符的工作方式类似于函数`IIf`，只不过它使用短路计算。 函数`IIf`始终计算其所有三个参数，而具有三个`If`参数的运算符只计算其中两个参数。 计算第`If`一个`Boolean`参数，并将结果强制转换为值或`True``False`。 如果值为`True`，`argument2`则计算其值，但不`argument3`计算该值。 如果`Boolean`表达式的值为`False`，`argument3`则计算其值并返回其值，但不`argument2`计算。 以下示例说明了使用三个参数`If`时的使用：

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

下面的示例说明了短路评估的价值。 该示例显示两次尝试将变量`number`除以变量`divisor`除以`divisor`变量，但为零时除外。 在这种情况下，应返回 0，并且不应尝试执行除法，因为将导致运行时错误。 由于`If`表达式使用短路计算，因此根据第一个参数的值计算第二个或第三个参数。 如果第一个参数为 true，则除法不是零，可以安全地计算第二个参数并执行除法。 如果第一个参数为 false，则仅计算第三个参数并返回 0。 因此，当除法器为 0 时，不会尝试执行除法，也没有错误结果。 但是，由于`IIf`不使用短路计算，因此即使第一个参数为 false，也会计算第二个参数。 这将导致运行时除以零错误。

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>如果运算符使用两个参数调用

`If`可以省略的第一个参数。 这样，只需使用两个参数就可以调用运算符。 仅当使用两个参数调用运算符`If`时，以下列表才适用。

### <a name="parts"></a>组成部分

|术语|定义|
|---|---|
|`argument2`|必需。 `Object`. 必须是引用值或空值类型。 当它评估到 以外的任何`Nothing`内容时，它进行评估并返回。|
|`argument3`|必需。 `Object`. 如果`argument2`评估为`Nothing`，则评估并返回。|

省略`Boolean`参数时，第一个参数必须是引用值类型或空值类型。 如果第一个参数计算到`Nothing`，则返回第二个参数的值。 在所有其他情况下，将返回第一个参数的值。 以下示例说明了此评估的工作原理：

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [可以为 null 的值类型](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
