---
title: RaiseEvent 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: ee52b4adf893ea0926c4016fcb6a89d0010ee6ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957770"
---
# <a name="raiseevent-statement"></a>RaiseEvent 语句
触发在类、窗体或文档中的模块级别声明的事件。  
  
## <a name="syntax"></a>语法  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>部件  
 `eventname`  
 必需。 要触发的事件的名称。  
  
 `argumentlist`  
 可选。 以逗号分隔的变量、数组或表达式的列表。 参数`argumentlist`必须括在括号中。 如果没有参数, 则必须省略括号。  
  
## <a name="remarks"></a>备注  
 所需`eventname`的是在模块中声明的事件的名称。 它遵循 Visual Basic 变量命名约定。  
  
 如果未在引发事件的模块内声明事件, 则会发生错误。 下面的代码段演示了事件声明和引发事件的过程。  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 不能使用`RaiseEvent`来引发未在模块中显式声明的事件。 例如, 所有窗体都从<xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Form?displayProperty=nameWithType>继承事件, 无法在派生窗体`RaiseEvent`中使用来引发该事件。 如果在窗体`Click`模块中声明事件, 它将隐藏窗体<xref:System.Windows.Forms.Control.Click>的事件。 你仍可以通过<xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Control.OnClick%2A>调用方法来调用窗体的事件。  
  
 默认情况下, 在 Visual Basic 中定义的事件将按照建立连接的顺序引发其事件处理程序。 由于事件可以有`ByRef`参数, 因此, 延迟连接的进程可能会收到先前的事件处理程序已更改的参数。 在事件处理程序执行后, 控制将返回到引发事件的子例程。  
  
> [!NOTE]
> 非共享事件不应在声明它们的类的构造函数中引发。 尽管此类事件不会导致运行时错误, 但是它们可能无法被关联的事件处理程序捕获。 如果需要从构造函数引发事件, 请使用修饰符创建共享事件。`Shared`  
  
> [!NOTE]
> 可以通过定义自定义事件来更改事件的默认行为。 对于自定义事件, `RaiseEvent`该语句将调用事件`RaiseEvent`的访问器。 有关自定义事件的详细信息, 请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用事件从 10 秒到 0 秒进行倒计时。 此代码演示了一些与事件相关的方法、属性和语句, 包括`RaiseEvent`语句。  
  
 引发事件的类是事件源，处理事件的方法是事件处理程序。 事件源对于它生成的事件可以具有多个处理程序。 类引发事件时，会在选择用于为对象的该实例处理事件的每个类上引发该事件。  
  
 该示例还使用一个窗体 (`Form1`)，其中包含一个按钮 (`Button1`) 和一个文本框 (`TextBox1`)。 单击该按钮时，第一个文本框显示从 10 秒到 0 秒的倒计时。 经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。  
  
 `Form1` 的代码指定窗体的初始和最终状态。 它还包含引发事件时执行的代码。  
  
 若要使用此示例, 请打开一个新的 Windows 应用程序项目, `Button1`添加一个名为的`TextBox1`按钮, 并将一个名`Form1`为的文本框添加到名为的主窗体。 然后, 右键单击该窗体, 然后单击 "**查看代码**" 以打开代码编辑器。  
  
 将变量添加到`Form1`类的声明部分。 `WithEvents`  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>示例  
 将下面的代码添加到 `Form1` 的代码： 替换任何可能存在的重复过程, 如`Form_Load`或。 `Button_Click`  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 按 F5 运行前面的示例, 并单击标签为 "**启动**" 的按钮。 第一个文本框中开始倒计时秒数。 经过了全部时间（10 秒）之后，第一个文本框会显示“Done”。  
  
> [!NOTE]
> `My.Application.DoEvents`方法不以与窗体相同的方式处理事件。 若要允许窗体直接处理事件, 可以使用多线程处理。 有关详细信息, 请参阅[托管线程处理](../../../standard/threading/index.md)。  
  
## <a name="see-also"></a>请参阅

- [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
