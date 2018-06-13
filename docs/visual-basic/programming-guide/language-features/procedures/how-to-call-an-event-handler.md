---
title: 如何：在 Visual Basic 中调用事件处理程序
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 4e6aeaee8027e462dcdf80cae34b4b246fd58cf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652677"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>如何：在 Visual Basic 中调用事件处理程序
*事件*是匹配项或操作-例如鼠标单击或信用额度超出-，识别被某程序组件，并为其编写代码以响应。 *事件处理程序*是为响应事件而编写的代码。  
  
 在 Visual Basic 中的一个事件处理程序`Sub`过程。 但是，你不能正常情况下调用此相同方式其他`Sub`过程。 相反，为事件处理程序标识过程。 你可以使用执行此操作[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句和[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)变量，或与[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)。 使用`Handles`子句是声明一个事件处理程序在 Visual Basic 中的默认方法。 这是事件处理程序编写的设计器时在集成的开发环境 (IDE) 中编程的方式。 `AddHandler`语句是适用于在运行时动态引发事件。  
  
 发生事件时，Visual Basic 会自动调用事件处理程序过程中。 有权访问该事件的任何代码可能会导致它通过执行发生[RaiseEvent 语句](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)。  
  
 你可以与同一事件关联多个事件处理程序。 在某些情况下可以取消关联从事件处理程序。 有关详细信息，请参阅[事件](../../../../visual-basic/programming-guide/language-features/events/index.md)。  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>若要调用事件处理程序使用句柄和 WithEvents  
  
1.  请确保该事件声明与[Event 语句](../../../../visual-basic/language-reference/statements/event-statement.md)。  
  
2.  声明对象变量在模块或类级别，请使用[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)关键字。 `As`此变量的子句必须指定引发事件的类。  
  
3.  事件处理的声明中`Sub`过程中，添加[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句，以指定`WithEvents`变量和事件名称。  
  
4.  发生事件时，Visual Basic 将自动调用`Sub`过程。 你的代码可以使用`RaiseEvent`语句使发生的事件。  
  
     下面的示例定义一个事件和一个`WithEvents`引用引发事件的类中的变量。 事件处理`Sub`过程使用`Handles`子句指定的类和它所处理的事件。  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>若要调用事件处理程序使用 AddHandler  
  
1.  请确保该事件声明与`Event`语句。  
  
2.  执行[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)动态连接事件处理`Sub`与事件的过程。  
  
3.  发生事件时，Visual Basic 将自动调用`Sub`过程。 你的代码可以使用`RaiseEvent`语句使发生的事件。  
  
     下面的示例定义`Sub`过程来处理<xref:System.Windows.Forms.Form.Closing>窗体的事件。 然后，它使用[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)关联`catchClose`的事件处理程序的过程<xref:System.Windows.Forms.Form.Closing>。  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     你可以通过执行取消事件处理程序从事件[RemoveHandler 语句](../../../../visual-basic/language-reference/statements/removehandler-statement.md)。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [AddressOf 运算符](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [如何：创建过程](./how-to-create-a-procedure.md)  
 [如何：调用不返回值的过程](./how-to-call-a-procedure-that-does-not-return-a-value.md)
