---
title: 未设置对象变量或 With 块变量
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040559"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>未设置对象变量或 With 块变量
正在引用无效的对象变量。   出现此错误的原因可能有多种：

- 声明了变量, 但未指定类型。 如果在未指定类型的情况下声明了变量, 则默认`Object`为类型。

    例如, 使用`Dim x`声明的变量的`Dim x As String`类型`Object;` `String`将为类型。

    > [!TIP]
    > 语句不允许使用`Object`导致类型的隐式类型。 `Option Strict` 如果省略该类型, 则会发生编译时错误。 请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。

- 你正在尝试引用已设置为`Nothing`的对象。

- 您正在尝试访问未正确声明的数组变量的元素。

    例如, 如果您尝试引用数组`products() As String` `products(3) = "Widget"`的元素, 则声明为的数组将触发错误。 数组没有元素, 被视为对象。

- 在初始化块之前, 您正尝试`With...End With`访问代码块中的代码。   必须通过`With`执行语句入口点初始化`With...End With`块。

> [!NOTE]
> 在 Visual Basic 或 VBA 的早期版本中, 还会通过在`Set`不使用关键字的情况下为变量赋值 (`x = "name"`而不是`Set x = "name"`) 来触发此错误。 `Set`关键字在 Visual Basic .net 中不再有效。

## <a name="to-correct-this-error"></a>更正此错误

1. 通过`Option Strict`将`On`以下代码添加到文件的开头, 将设置为:

    ```vb
    Option Strict On
    ```

    运行该项目时, 将在**错误列表**中为没有类型指定的任何变量显示编译器错误。

2. 如果不想启用`Option Strict`, 请在代码中搜索未指定类型 (`Dim x`而不`Dim x As String`是) 的任何变量, 并将目标类型添加到声明。

3. 请确保未引用已设置为`Nothing`的对象变量。  在代码中搜索关键字`Nothing`, 然后修改代码, 使对象在引用之前不会设置为。 `Nothing`

4. 在访问数组变量之前, 请确保对其进行标注。 您可以在首次创建数组 (`Dim x(5) As String` `Dim x() As String`而不是`ReDim` ) 时分配维度, 或者使用关键字在第一次访问数组之前设置其维度。

5. 请确保`With`通过`With`执行语句入口点初始化块。

## <a name="see-also"></a>请参阅

- [对象变量声明](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
- [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
