---
title: CType 函数 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 4a0391b0a5d76f36803b433369d4832c02b05e09
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592100"
---
# <a name="ctype-function-visual-basic"></a>CType 函数 (Visual Basic)

返回将表达式显式转换为指定的数据类型、对象、结构、类或接口的结果。

## <a name="syntax"></a>语法

```vb
CType(expression, typename)
```

## <a name="parts"></a>部件

@no__t 任意有效的表达式。 如果 `expression` 的值超出 `typename` 允许的范围，Visual Basic 将引发异常。

`typename` 在 `Dim` 语句的 `As` 子句内合法的任何表达式，即任何数据类型、对象、结构、类或接口的名称。

## <a name="remarks"></a>备注

> [!TIP]
> 你还可以使用以下函数来执行类型转换：
>
> - 类型转换函数，例如 `CByte`、`CDbl` 和 `CInt` 执行到特定数据类型的转换。 有关详细信息，请参阅[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)。
> - [DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)或[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。 这些运算符要求一个类型继承自或实现另一个类型。 在转换为 @no__t 的数据类型时，它们可以提供比 @no__t 0 更好的性能。

@no__t 为内联编译，这意味着转换代码是计算表达式的代码的一部分。 在某些情况下，代码运行速度更快，因为没有调用任何过程来执行转换。

如果未定义从 `expression` 到 `typename` 的转换（例如从 `Integer` 到 `Date`），Visual Basic 将显示编译时错误消息。

如果转换在运行时失败，则会引发相应的异常。 如果收缩转换失败，最常见的结果是 @no__t 0。 如果未定义转换，则会引发 @no__t 0。 例如，如果 `expression` 的类型 @no__t 为-1，并且其运行时类型没有转换为 `typename`，则可能会发生这种情况。

如果 @no__t 的数据类型为-0 或 @no__t 为您定义的类或结构，则可以将该类或结构上的 @no__t 定义为转换运算符。 这使得 @no__t 为0作为*重载运算符*。 如果执行此操作，则可以控制与类或结构的转换的行为，包括可能引发的异常。

## <a name="overloading"></a>重载

也可以在代码外部定义的类或结构上重载 `CType` 运算符。 如果你的代码在此类或结构之间进行转换，请确保了解其 @no__t 运算符的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。

## <a name="converting-dynamic-objects"></a>转换动态对象

动态对象的类型转换由使用 @no__t 0 或 @no__t 方法的用户定义的动态转换执行。 如果使用的是动态对象，请使用 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 方法转换动态对象。

## <a name="example"></a>示例

下面的示例使用 `CType` 函数将表达式转换为 @no__t 的数据类型。

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

有关其他示例，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)。

## <a name="see-also"></a>请参阅

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换函数](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [如何：定义转换运算符 @ no__t-0
- [.NET Framework 中的类型转换](../../../standard/base-types/type-conversion.md)
