---
title: Mod 运算符
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: b7552550d4b0496d6ad7ee76a7327054d544b874
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350918"
---
# <a name="mod-operator-visual-basic"></a>Mod 运算符（Visual Basic）

将两个数字相除，仅返回余数。

## <a name="syntax"></a>语法

```vb
result = number1 Mod number2
```

## <a name="parts"></a>部件

`result` \
必需。 任何数值变量或属性。

`number1` \
必需。 任何数值表达式。

`number2` \
必需。 任何数值表达式。

## <a name="supported-types"></a>支持的类型

所有数值类型。 这包括无符号和浮点类型以及 `Decimal`。

## <a name="result"></a>结果

结果是 `number1` 除以 `number2`后所得的余数。 例如，表达式 `14 Mod 4` 的计算结果为2。

> [!NOTE]
> 在数学中，*余数*和*模数*之间存在差异，但负数的结果不同。 Visual Basic 中的 `Mod` 运算符、.NET Framework `op_Modulus` 运算符和基础[rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 指令都执行余数运算。

`Mod` 操作的结果保留被除数的符号，`number1`，因此它可以是正数也可以是负数。 结果始终处于范围内（-`number2`、`number2`）。 例如：

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>备注

如果 `number1` 或 `number2` 为浮点值，则返回相除的浮点余数。 结果的数据类型是最小的数据类型，该数据类型可保存由 `number1` 和 `number2`的数据类型分割导致的所有可能值。

如果 `number1` 或 `number2` 的计算结果不为[空，则](../../../visual-basic/language-reference/nothing.md)将其视为零。

相关运算符包括：

- [\ 运算符（Visual Basic）](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回相除的整数商。 例如，表达式 `14 \ 4` 的计算结果为3。

- [/运算符（Visual Basic）](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)以浮点数的形式返回所有商，包括余数。 例如，表达式 `14 / 4` 的计算结果为3.5。

## <a name="attempted-division-by-zero"></a>尝试被零除

如果 `number2` 的计算结果为零，则 `Mod` 运算符的行为取决于操作数的数据类型：

- 如果在编译时无法确定 `number2`，则整数除法会引发 <xref:System.DivideByZeroException> 异常并生成编译时错误 `BC30542 Division by zero occurred while evaluating this expression` 如果在编译时将 `number2` 计算为零。
- 浮点除法返回 <xref:System.Double.NaN?displayProperty=nameWithType>。

## <a name="equivalent-formula"></a>等效公式

表达式 `a Mod b` 等效于以下公式之一：

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>浮点不精确性

使用浮点数时，请记住，内存中不一定有精确的十进制表示形式。 这可能会导致某些操作产生意外结果，如值比较和 `Mod` 运算符。 有关详细信息，请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。

## <a name="overloading"></a>重载

`Mod` 运算符可以进行*重载*，这意味着类或结构可以重新定义它的行为。 如果你的代码将 `Mod` 应用到包含此类重载的类或结构的实例，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。

## <a name="example"></a>示例

下面的示例使用 `Mod` 运算符将两个数字相除，仅返回余数。 如果其中一个数字为浮点数，则结果为一个表示余数的浮点数。

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>示例

下面的示例演示了浮点操作数的潜在不精确性。 在第一个语句中，操作数是 `Double`的，0.2 是一个无限重复的二进制小数，其存储值为0.20000000000000001。 在第二个语句中，文本类型字符 `D` 强制两个操作数都 `Decimal`，0.2 具有精确的表示形式。

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [\ 运算符（Visual Basic）](../../../visual-basic/language-reference/operators/integer-division-operator.md)
