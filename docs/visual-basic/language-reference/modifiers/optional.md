---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 3758f17634395236abf2cd7059418bf6f8b6c062
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630930"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

指定在调用过程时可以省略过程参数。

## <a name="remarks"></a>备注

对于每个可选参数, 必须将常数表达式指定为该参数的默认值。 如果表达式的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md), 则将值数据类型的默认值用作参数的默认值。

如果参数列表包含一个可选参数, 则其后的每个参数都必须是可选的。

          `Optional` 修饰符可用于下面的上下文中：

- [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)

- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)

> [!NOTE]
> 调用带有或不带可选参数的过程时, 可以按位置或按名称传递参数。 有关详细信息, 请参阅[按位置和按名称传递参数](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)。

> [!NOTE]
> 还可以通过使用重载来定义带有可选参数的过程。 如果有一个可选参数, 则可以定义过程的两个重载版本, 一个接受参数, 另一个不包含参数。 有关更多信息，请参见 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。

## <a name="example"></a>示例

下面的示例定义了一个具有可选参数的过程。

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a>示例

下面的示例演示如何调用带有按位置传递的参数和通过名称传递的参数的过程。 此过程具有两个可选参数。

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a>请参阅

- [参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)
- [可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
