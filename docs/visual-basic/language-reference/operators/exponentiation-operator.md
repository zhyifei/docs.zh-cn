---
title: ^ 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 8cdfbec917608211e19c39eb37bd12dbc7c4d33f
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592211"
---
# <a name="-operator-visual-basic"></a>^ 运算符 (Visual Basic)

计算一个数字的另一个数字的幂。

## <a name="syntax"></a>语法

```vb
number ^ exponent
```

## <a name="parts"></a>部件

`number`\
必需。 任何数值表达式。

`exponent`\
必需。 任何数值表达式。

## <a name="result"></a>结果

结果为 `number` 的幂 `exponent`，始终以 `Double` 值的形式出现。

## <a name="supported-types"></a>支持的类型

`Double`。 任何不同类型的操作数将转换为 `Double`。

## <a name="remarks"></a>备注

Visual Basic 总是对[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)执行幂运算。

@No__t-0 的值可以是小数、负数或同时为两者。

如果在单个表达式中执行了多个幂运算，则会计算 @no__t 0 运算符，因为它是从左到右发生的。

> [!NOTE]
> @No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。

## <a name="example"></a>示例

下面的示例使用 `^` 运算符对某个数字进行幂运算。 结果是第一个操作数的次幂。

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

前面的示例生成了以下结果：

@no__t 设置为4（2 squared）。

@no__t 设置为19683（3），然后设置为 ""。

`exp3` 设置为-125 （-5 立方）。

@no__t 设置为625（-5 到第四次幂）。

@no__t 设置为2（共8个多维数据集的根）。

@no__t 设置为0.5 （1.0 除以8的 cube 根）。

请注意前面示例的表达式中的括号的重要性。 由于*运算符优先级*，Visual Basic 通常在任何其他运算符（甚至一元 `–` 运算符）之前执行 @no__t 1 运算符。 如果未使用括号计算 @no__t 0 和 `exp6`，则会生成以下结果：

`exp4 = -5 ^ 4` 将计算为–（5到第四次幂），这会导致-625。

`exp6 = 8 ^ -1.0 / 3.0` 将计算为（8到1个幂，即0.125）除以3.0，这将导致0.041666666666666666666666666666667。

## <a name="see-also"></a>请参阅

- [^= 运算符](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
