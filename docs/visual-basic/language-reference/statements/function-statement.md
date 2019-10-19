---
title: Function 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 046a3a7d50d15cd3e59205998554a4c330d4552c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581837"
---
# <a name="function-statement-visual-basic"></a>Function 语句 (Visual Basic)

声明定义 `Function` 过程的名称、参数和代码。

## <a name="syntax"></a>语法

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>部件

- `attributelist`

  可选。 请参阅[特性列表](attribute-list.md)。

- `accessmodifier`

  可选。 可以是以下各项之一：

  - [COMClassAttribute](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。

- `proceduremodifiers`

  可选。 可以是以下各项之一：

  - [重载](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [New](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  可选。 请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。

- `Shadows`

  可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。

- `Async`

  可选。 请参阅[Async](../../../visual-basic/language-reference/modifiers/async.md)。

- `Iterator`

  可选。 请参阅[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。

- `name`

  必须的。 过程的名称。 请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。

- `typeparamlist`

  可选。 泛型过程的类型参数的列表。 请参阅[类型列表](type-list.md)。

- `parameterlist`

  可选。 表示此过程参数的本地变量名称列表。 请参阅[参数列表](parameter-list.md)。

- `returntype`

  如果 `Option Strict` `On`，则为必需。 此过程返回的值的数据类型。

- `Implements`

  可选。 指示此过程实现一个或多个 `Function` 过程，每个过程都在此过程的包含类或结构实现的接口中定义。 请参阅[Implements 语句](implements-statement.md)。

- `implementslist`

  如果提供 `Implements`，则是必需的。 所实现的 `Function` 过程的列表。

  `implementedprocedure [ , implementedprocedure ... ]`

  每个 `implementedprocedure` 都具有以下语法和部件：

  `interface.definedname`

  |部件|描述|
  |---|---|
  |`interface`|必须的。 此过程的包含类或结构实现的接口的名称。|
  |`definedname`|必须的。 在 `interface` 中用于定义过程的名称。|

- `Handles`

  可选。 指示此过程可以处理一个或多个特定事件。 请参阅[句柄](handles-clause.md)。

- `eventlist`

  如果提供 `Handles`，则是必需的。 此过程处理的事件列表。

  `eventspecifier [ , eventspecifier ... ]`

  每个 `eventspecifier` 都具有以下语法和部件：

  `eventvariable.event`

  |部件|描述|
  |---|---|
  |`eventvariable`|必须的。 用引发事件的类或结构的数据类型声明的对象变量。|
  |`event`|必须的。 此过程处理的事件的名称。|

- `statements`

  可选。 要在此过程中执行的语句块。

- `End Function`

  终止此过程的定义。

## <a name="remarks"></a>备注

所有可执行代码都必须在过程内。 反过来，每个过程都在类、结构或模块（称为包含类、结构或模块）中声明。

若要将值返回到调用代码，请使用 `Function` 过程;否则，请使用 `Sub` 过程。

## <a name="defining-a-function"></a>定义函数

只能在模块级别定义 `Function` 过程。 因此，函数的声明上下文必须是类、结构、模块或接口，不能是源文件、命名空间、过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。

`Function` 过程默认为公共访问。 您可以使用访问修饰符调整其访问级别。

@No__t_0 过程可以声明过程返回的值的数据类型。 您可以指定任何数据类型或枚举、结构、类或接口的名称。 如果未指定 `returntype` 参数，则该过程将返回 `Object`。

如果此过程使用 `Implements` 关键字，则包含类或结构还必须具有紧跟其 `Class` 或 `Structure` 语句的 `Implements` 语句。 @No__t_0 语句必须包括 `implementslist` 中指定的每个接口。 但是，接口用于定义 `Function` 的名称（在 `definedname` 中）无需与此过程的名称匹配（在 `name` 中）。

> [!NOTE]
> 您可以使用 lambda 表达式来定义内联函数表达式。 有关详细信息，请参阅[函数表达式](../../../visual-basic/language-reference/operators/function-expression.md)和[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。

## <a name="returning-from-a-function"></a>从函数返回

当 `Function` 过程返回到调用代码时，执行将继续执行调用该过程的语句后面的语句。

若要从函数返回值，可以将值分配给函数名称，或者将其包含在 `Return` 语句中。

@No__t_0 语句同时分配返回值并退出函数，如下面的示例所示。

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

下面的示例将返回值分配给函数名称 `myFunction`，然后使用 `Exit Function` 语句返回。

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

@No__t_0 和 `Return` 语句导致立即退出 `Function` 过程。 任意数量的 `Exit Function` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Function` 和 `Return` 语句。

如果在不指定 `name` 值的情况下使用 `Exit Function`，则该过程将返回 `returntype` 中指定的数据类型的默认值。 如果未指定 `returntype`，则该过程将返回 `Nothing`，这是 `Object` 的默认值。

## <a name="calling-a-function"></a>调用函数

通过在表达式中使用过程名称后跟括号中的参数列表，可以调用 `Function` 过程。 仅当未提供任何参数时，才可以省略括号。 但是，如果你始终包含括号，你的代码将更具可读性。

调用 `Function` 过程的方式与调用任何库函数（如 `Sqrt`、`Cos` 或 `ChrW`）的方式相同。

还可以通过使用 `Call` 关键字调用函数。 在这种情况下，将忽略返回值。 在大多数情况下不建议使用 `Call` 关键字。 有关详细信息，请参阅[Call 语句](call-statement.md)。

Visual Basic 有时会重新排列算术表达式以提高内部效率。 出于此原因，当函数更改同一表达式中变量的值时，不应使用算术表达式中的 `Function` 过程。

## <a name="async-functions"></a>异步函数

使用*异步*功能可以调用异步函数，而无需使用显式回调或在多个函数或 lambda 表达式中手动拆分代码。

如果使用[Async](../../../visual-basic/language-reference/modifiers/async.md)修饰符标记函数，则可以在函数中使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)运算符。 当控件在 `Async` 函数中到达 `Await` 表达式时，控件将返回到调用方，并且在等待的任务完成之前，将挂起该函数中的进度。 任务完成后，可以在函数中继续执行。

> [!NOTE]
> 当某个 `Async` 过程遇到尚未完成的第一个等待对象时，它将返回到调用方，或者到达 `Async` 过程的末尾，以先发生者为准。

@No__t_0 函数的返回类型可以是 <xref:System.Threading.Tasks.Task%601> 或 <xref:System.Threading.Tasks.Task>。 下面提供了返回类型为 <xref:System.Threading.Tasks.Task%601> 的 `Async` 函数的示例。

@No__t_0 函数不能声明任何[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)参数。

还可以使用 `Async` 修饰符来标记[Sub 语句](sub-statement.md)。 这主要用于事件处理程序，其中不能返回值。 无法等待 `Async` 的 `Sub` 过程，并且 `Async` `Sub` 过程的调用方无法捕获由 `Sub` 过程引发的异常。

有关 `Async` 函数的详细信息，请参阅[采用 async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)、[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)和[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。

## <a name="iterator-functions"></a>迭代器函数

*迭代器*函数在集合上执行自定义迭代，如列表或数组。 Iterator 函数使用[Yield](yield-statement.md)语句每次返回一个元素。 当到达[Yield](yield-statement.md)语句时，将记住代码中的当前位置。 下次调用迭代器函数时，将从该位置重新开始执行。

使用 For Each ... 将从客户端代码调用迭代器[下一](for-each-next-statement.md)语句。

迭代器函数的返回类型可以是 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator> 或 <xref:System.Collections.Generic.IEnumerator%601>。

有关详细信息，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。

## <a name="example"></a>示例

下面的示例使用 `Function` 语句来声明构成 `Function` 过程正文的名称、参数和代码。 @No__t_0 修饰符使函数可以接受数量可变的参数。

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>示例

下面的示例调用在前面的示例中声明的函数。

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>示例

在下面的示例中，`DelayAsync` 是返回类型为 <xref:System.Threading.Tasks.Task%601> 的 `Async` `Function`。 `DelayAsync` 具有返回整数的 `Return` 语句。 因此，`DelayAsync` 的函数声明需要具有 `Task(Of Integer)` 的返回类型。 由于返回类型为 `Task(Of Integer)`，因此 `DoSomethingAsync` 中 `Await` 表达式的计算将产生整数。 此语句演示了这一点： `Dim result As Integer = Await delayTask`。

@No__t_0 过程是 `Async Sub` 过程的示例。 由于 `DoSomethingAsync` 是 `Async` 函数，因此对 `DoSomethingAsync` 的调用的任务必须等待，如以下语句所示： `Await DoSomethingAsync()`。 必须使用 `Async` 修饰符定义 `startButton_Click` `Sub` 过程，因为它具有 `Await` 表达式。

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>请参阅

- [Sub 语句](sub-statement.md)
- [Function 过程](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [参数列表](parameter-list.md)
- [Dim 语句](dim-statement.md)
- [Call 语句](call-statement.md)
- [Of](of-clause.md)
- [参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [如何：使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [过程疑难解答](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [函数表达式](../../../visual-basic/language-reference/operators/function-expression.md)
