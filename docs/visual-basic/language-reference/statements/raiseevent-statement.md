---
title: "RaiseEvent 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6ba5ce4b009e0d8c675db07b56b9811c595ae2f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="raiseevent-statement"></a>RaiseEvent 语句
在类、 表单或文档中的模块级触发器事件的声明。  
  
## <a name="syntax"></a>语法  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>部件  
 `eventname`  
 必须的。 要触发的事件的名称。  
  
 `argumentlist`  
 可选。 变量、 数组或表达式的以逗号分隔列表。 `argumentlist`自变量必须括在圆括号。 如果不有任何自变量，必须省略括号。  
  
## <a name="remarks"></a>备注  
 所需`eventname`模块中声明事件的名称。 它遵循 Visual Basic 变量命名约定。  
  
 如果尚未引发该模块中声明事件，就会出错。 下面的代码段说明了事件声明和引发该事件的过程。  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 不能使用`RaiseEvent`来引发未在模块中显式声明的事件。 例如，所有窗体继承<xref:System.Windows.Forms.Control.Click>事件从<xref:System.Windows.Forms.Form?displayProperty=nameWithType>，不能提升使用`RaiseEvent`派生窗体中。 如果你声明`Click`事件在窗体模块中，它会隐藏窗体的自身<xref:System.Windows.Forms.Control.Click>事件。 你仍可以调用窗体的<xref:System.Windows.Forms.Control.Click>通过调用的事件<xref:System.Windows.Forms.Control.OnClick%2A>方法。  
  
 默认情况下，在 Visual Basic 中定义的事件引发顺序连接的建立其事件处理程序。 由于事件可以具有`ByRef`参数，后期连接的进程可能会收到已被更早版本的事件处理程序更改的参数。 事件处理程序执行后，控制权就会归还子例程中引发了事件。  
  
> [!NOTE]
>  不应在声明它们的类构造函数内引发非共享的事件。 尽管此类事件不会导致运行时错误，但它们可能无法由关联的事件处理程序捕获。 使用`Shared`修饰符来创建共享的事件，如果你需要从一个构造函数中引发事件。  
  
> [!NOTE]
>  可以通过定义自定义事件来更改事件的默认行为。 对于自定义事件，`RaiseEvent`语句调用事件的`RaiseEvent`访问器。 有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用事件从 10 秒到 0 秒进行倒计时。 代码演示了几个与事件相关的方法、 属性和语句，其中包括`RaiseEvent`语句。  
  
 引发事件的类是事件源，处理事件的方法是事件处理程序。 事件源对于它生成的事件可以具有多个处理程序。 类引发事件时，会在选择用于为对象的该实例处理事件的每个类上引发该事件。  
  
 该示例还使用一个窗体 (`Form1`)，其中包含一个按钮 (`Button1`) 和一个文本框 (`TextBox1`)。 单击该按钮时，第一个文本框显示从 10 秒到 0 秒的倒计时。 经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。  
  
 `Form1` 的代码指定窗体的初始和最终状态。 它还包含引发事件时执行的代码。  
  
 若要使用此示例中，打开一个新的 Windows 应用程序项目，添加名为的按钮`Button1`和一个名为文本框`TextBox1`到主窗体，名为`Form1`。 右键单击该表单，然后单击**查看代码**以打开代码编辑器。  
  
 添加`WithEvents`变量的声明部分`Form1`类。  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>示例  
 将下面的代码添加到 `Form1` 的代码： 替换可能存在，如任何重复过程`Form_Load`，或`Button_Click`。  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 按 f5 键以运行前面的示例中，并单击标记按钮**启动**。 第一个文本框中开始倒计时秒数。 经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。  
  
> [!NOTE]
>  `My.Application.DoEvents`窗体一样方法不完全相同的方式中处理事件。 若要使表单能够直接处理事件，可以使用多线程处理。 有关详细信息，请参阅[线程处理](../../programming-guide/concepts/threading/index.md)。  
  
## <a name="see-also"></a>请参阅  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
