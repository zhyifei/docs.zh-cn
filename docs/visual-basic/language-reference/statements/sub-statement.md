---
title: Sub 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 7dc0ea1f1b30f5ffb0db8917538adf440c5ef891
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583189"
---
# <a name="sub-statement-visual-basic"></a>Sub 语句 (Visual Basic)

声明定义 `Sub` 过程的名称、参数和代码。

## <a name="syntax"></a>语法

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>部件

- `attributelist`

  可选。 请参阅[特性列表](attribute-list.md)。

- `Partial`

  可选。 指示分部方法的定义。 请参阅[分部方法](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)。

- `accessmodifier`

  可选。 可以是以下各项之一：

  - [COMClassAttribute](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。

- `proceduremodifiers`

  可选。 可以是以下各项之一：

  - [重载](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [New](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  可选。 请参阅[共享](../modifiers/shared.md)。

- `Shadows`

  可选。 请参阅[阴影](../modifiers/shadows.md)。

- `Async`

  可选。 请参阅[Async](../modifiers/async.md)。

- `name`

  必须的。 过程的名称。 请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。 若要为类创建构造函数过程，请将 `Sub` 过程的名称设置为 `New` 关键字。 有关详细信息，请参阅[对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。

- `typeparamlist`

  可选。 泛型过程的类型参数的列表。 请参阅[类型列表](type-list.md)。

- `parameterlist`

  可选。 表示此过程参数的本地变量名称列表。 请参阅[参数列表](parameter-list.md)。

- `Implements`

  可选。 指示此过程实现一个或多个 `Sub` 过程，每个过程都在此过程的包含类或结构实现的接口中定义。 请参阅[Implements 语句](implements-statement.md)。

- `implementslist`

  如果提供 `Implements`，则是必需的。 所实现的 `Sub` 过程的列表。

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

  可选。 要在此过程中运行的语句块。

- `End Sub`

  终止此过程的定义。

## <a name="remarks"></a>备注

所有可执行代码都必须在过程内。 如果不想将值返回到调用代码，请使用 `Sub` 过程。 如果要返回值，请使用 `Function` 过程。

## <a name="defining-a-sub-procedure"></a>定义 Sub 过程

只能在模块级别定义 `Sub` 过程。 因此，sub 过程的声明上下文必须是类、结构、模块或接口，不能是源文件、命名空间、过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。

`Sub` 过程默认为公共访问。 您可以使用访问修饰符调整其访问级别。

如果过程使用 `Implements` 关键字，则包含类或结构必须具有紧跟其 `Class` 或 `Structure` 语句的 `Implements` 语句。 @No__t_0 语句必须包括 `implementslist` 中指定的每个接口。 但是，接口定义 `Sub` （在 `definedname` 中）的名称不必与此过程的名称匹配（在 `name` 中）。

## <a name="returning-from-a-sub-procedure"></a>从 Sub 过程返回

当 `Sub` 过程返回到调用代码时，执行将继续执行调用它的语句之后的语句。

下面的示例演示如何从 `Sub` 过程返回。

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

@No__t_0 和 `Return` 语句导致立即退出 `Sub` 过程。 任意数量的 `Exit Sub` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Sub` 和 `Return` 语句。

## <a name="calling-a-sub-procedure"></a>调用 Sub 过程

通过在语句中使用过程名称，然后将该名称跟在括号中的参数列表后面来调用 `Sub` 过程。 仅当未提供任何参数时，才可以省略括号。 但是，如果你始终包含括号，你的代码将更具可读性。

@No__t_0 过程和 `Function` 过程可以具有参数并执行一系列语句。 但 `Function` 过程将返回一个值，而 `Sub` 过程不会。 因此，不能在表达式中使用 `Sub` 过程。

调用 `Sub` 过程时，可以使用 `Call` 关键字，但对于大多数用途，不建议使用该关键字。 有关详细信息，请参阅[Call 语句](call-statement.md)。

Visual Basic 有时会重新排列算术表达式以提高内部效率。 出于此原因，如果参数列表包含调用其他过程的表达式，则不应假定将按特定顺序调用这些表达式。

## <a name="async-sub-procedures"></a>Async Sub 过程

通过使用异步功能，你可以调用异步函数而无需使用显式回调或在多个函数或 lambda 表达式中手动拆分你的代码。

如果使用[Async](../modifiers/async.md)修饰符标记过程，则可以在过程中使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)运算符。 当控件在 `Async` 过程中到达 `Await` 表达式时，控件将返回到调用方，并且在等待的任务完成之前，将挂起过程中的进度。 任务完成后，可以在过程中继续执行。

> [!NOTE]
> 当遇到尚未完成的第一个等待对象或到达 `Async` 过程的结束时（以先发生者为准），`Async` 过程返回到调用方。

还可以使用 `Async` 修饰符标记[函数语句](function-statement.md)。 @No__t_0 函数的返回类型可以是 <xref:System.Threading.Tasks.Task%601> 或 <xref:System.Threading.Tasks.Task>。 本主题后面的示例演示了一个返回类型为 <xref:System.Threading.Tasks.Task%601> 的 `Async` 函数。

`Async` `Sub` 过程主要用于事件处理程序，其中不能返回值。 无法等待 `Async` 的 `Sub` 过程，并且 `Async` `Sub` 过程的调用方无法捕获 `Sub` 过程引发的异常。

@No__t_0 过程不能声明任何[ByRef](../modifiers/byref.md)参数。

有关 `Async` 过程的详细信息，请参阅[采用 async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)、[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)和[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。

## <a name="example"></a>示例

下面的示例使用 `Sub` 语句来定义构成 `Sub` 过程正文的名称、参数和代码。

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>示例

在下面的示例中，`DelayAsync` 是返回类型为 <xref:System.Threading.Tasks.Task%601> 的 `Async` `Function`。 `DelayAsync` 具有返回整数的 `Return` 语句。 因此，`DelayAsync` 的函数声明的返回类型必须为 `Task(Of Integer)`。 由于返回类型为 `Task(Of Integer)`，因此 `DoSomethingAsync` 中 `Await` 表达式的计算将生成一个整数，如以下语句所示： `Dim result As Integer = Await delayTask`。

@No__t_0 过程是 `Async Sub` 过程的示例。 由于 `DoSomethingAsync` 是 `Async` 函数，因此对 `DoSomethingAsync` 的调用的任务必须等待，如以下语句所示： `Await DoSomethingAsync()`。 必须使用 `Async` 修饰符定义 `startButton_Click` `Sub` 过程，因为它具有 `Await` 表达式。

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>请参阅

- [Implements 语句](implements-statement.md)
- [Function 语句](function-statement.md)
- [参数列表](parameter-list.md)
- [Dim 语句](dim-statement.md)
- [Call 语句](call-statement.md)
- [Of](of-clause.md)
- [参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [如何：使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [过程疑难解答](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [分部方法](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
