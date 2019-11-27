---
title: 如何：调用事件处理程序
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 0c626a9ad92fe2cd0ea117a9abdd2965a09df2ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340425"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>如何：在 Visual Basic 中调用事件处理程序

事件是指由某些程序组件识别的操作或*事件*（例如鼠标单击或信用限制），可以为其编写代码来做出响应。 *事件处理程序*是为响应事件而编写的代码。

 Visual Basic 中的事件处理程序是一个 `Sub` 过程。 不过，通常不会像其他 `Sub` 过程那样调用它。 而是将该过程标识为事件的处理程序。 您可以使用[Handles](../../../language-reference/statements/handles-clause.md)子句和[WithEvents](../../../language-reference/modifiers/withevents.md)变量或使用[AddHandler 语句](../../../language-reference/statements/addhandler-statement.md)来执行此操作。 使用 `Handles` 子句是在 Visual Basic 中声明事件处理程序的默认方式。 当你在集成开发环境（IDE）中编程时，这就是设计器编写事件处理程序的方式。 `AddHandler` 语句适用于在运行时动态引发事件。

 事件发生时，Visual Basic 会自动调用事件处理程序过程。 有权访问事件的任何代码都可以通过执行[RaiseEvent 语句](../../../language-reference/statements/raiseevent-statement.md)来导致事件发生。

 可以将多个事件处理程序与同一事件关联。 在某些情况下，您可以取消关联事件的处理程序。 有关更多信息，请参见 [事件](../events/index.md)中定义的接口的私有 C++ 特定实现。

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>使用 Handles 和 WithEvents 调用事件处理程序

1. 请确保事件是用[事件语句](../../../language-reference/statements/event-statement.md)声明的。

2. 使用[WithEvents](../../../language-reference/modifiers/withevents.md)关键字在模块或类级别声明对象变量。 此变量的 `As` 子句必须指定引发事件的类。

3. 在事件处理 `Sub` 过程的声明中，添加一个指定 `WithEvents` 变量和事件名称的[Handles](../../../language-reference/statements/handles-clause.md)子句。

4. 事件发生时，Visual Basic 会自动调用 `Sub` 过程。 你的代码可以使用 `RaiseEvent` 语句来使事件发生。

     下面的示例定义了一个事件和一个 `WithEvents` 变量，该变量引用引发事件的类。 事件处理 `Sub` 过程使用 `Handles` 子句来指定它处理的类和事件。

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>使用 AddHandler 调用事件处理程序

1. 请确保使用 `Event` 语句声明事件。

2. 执行[AddHandler 语句](../../../language-reference/statements/addhandler-statement.md)，以将事件处理 `Sub` 过程与事件动态连接。

3. 事件发生时，Visual Basic 会自动调用 `Sub` 过程。 你的代码可以使用 `RaiseEvent` 语句来使事件发生。

     下面的示例定义了一个用于处理窗体的 <xref:System.Windows.Forms.Form.Closing> 事件的 `Sub` 过程。 然后，它使用[AddHandler 语句](../../../language-reference/statements/addhandler-statement.md)将 `catchClose` 过程关联为 <xref:System.Windows.Forms.Form.Closing>的事件处理程序。

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     可以通过执行[RemoveHandler 语句](../../../language-reference/statements/removehandler-statement.md)，将事件处理程序与事件取消关联。

## <a name="see-also"></a>另请参阅

- [过程](index.md)
- [Sub 过程](sub-procedures.md)
- [Sub 语句](../../../language-reference/statements/sub-statement.md)
- [AddressOf 运算符](../../../language-reference/operators/addressof-operator.md)
- [如何：创建过程](how-to-create-a-procedure.md)
- [如何：调用不返回值的过程](how-to-call-a-procedure-that-does-not-return-a-value.md)
