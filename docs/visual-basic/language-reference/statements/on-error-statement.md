---
title: "On Error 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96baa5d91d0a600b84ed832fb1e3b1ed71a9d89d
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="on-error-statement-visual-basic"></a>On Error 语句 (Visual Basic)
启用错误处理例程，并指定过程; 中的例程的位置此外可以用于禁用错误处理例程。  
  
 如果错误处理，不会发生任何运行时错误是致命： 显示错误消息，并且停止执行。  
  
 只要有可能，我们建议你使用结构化的异常处理在代码中，而不是使用非结构化的异常处理和`On Error`语句。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
> [!NOTE]
>  `Error`关键字还用于[Error 语句](../../../visual-basic/language-reference/statements/error-statement.md)，这为了向后兼容受支持。  
  
## <a name="syntax"></a>语法  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`GoTo` `line`|启用开始指定所需的代码行的错误处理例程`line`自变量。 `line`自变量可以是任何行标签或行号。 如果发生运行时错误，则控制分支到指定的行，以激活错误处理程序。 指定的行必须是相同的过程中`On Error`语句或编译时错误会发生。|  
|`GoTo` 0|禁用当前的过程中启用的错误处理和重置为`Nothing`。|  
|`GoTo` -1|禁用当前的过程中已启用的异常和重置为`Nothing`。|  
|`Resume Next`|指定的运行时错误时，控件跳转到紧跟其中发生错误，并从该点继续执行该语句的语句。 使用此窗体而非`On Error GoTo`时访问的对象。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  我们建议你使用结构化的异常处理，只要有可能，在代码中，而不是无需使用非结构化的异常处理和`On Error`语句。 有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
 "Enabled"错误处理程序是指通过开启`On Error`语句。 "活动"的错误处理程序是已启用的处理程序正在处理错误。  
  
 错误处理程序处于活动状态时如果发生错误 (之间发生错误的和`Resume`， `Exit Sub`， `Exit Function`，或`Exit Property`语句)，则当前过程的错误处理程序无法处理该错误。 控制权返回给调用的过程。  
  
 如果调用过程有一个已启用的错误处理程序，它将激活地处理错误。 如果调用过程的错误处理程序还处于活动状态的控制权将传递回通过前一个调用过程中，直到找到已启用，但非活动状态、 错误处理程序。 如果不找到任何此类错误处理程序，这个错误是致命它实际发生的时候。  
  
 错误处理程序将控制权返回给调用过程时，每次该过程将成为当前过程。 在当前过程中由指定的位置后通过错误处理程序的任何程序中处理错误，继续执行`Resume`语句。  
  
> [!NOTE]
>  错误处理例程不`Sub`过程或`Function`过程。 它是一段代码标记的行标签或行号。  
  
## <a name="number-property"></a>Number 属性  
 错误处理例程依赖于中的值`Number`属性`Err`对象以确定错误的原因。 例程应测试或保存中相关的属性值`Err`对象之前可能出现其他错误或错误调用之前可能会导致的过程。 属性值将在`Err`对象只反映最新的错误。 与关联的错误消息`Err.Number`中包含`Err.Description`。  
  
## <a name="throw-statement"></a>Throw 语句  
 引发错误`Err.Raise`方法设置`Exception`属性的新创建的实例<xref:System.Exception>类。 为了支持派生的异常类型的异常引发`Throw`语句支持的语言。 这将是要引发的异常实例的单个参数。 下面的示例演示如何与现有异常处理支持使用这些功能：  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 请注意，`On Error GoTo`语句捕获所有错误，而不考虑异常类。  
  
## <a name="on-error-resume-next"></a>On Error Resume Next  
 `On Error Resume Next`会导致执行继续紧跟导致运行时错误的语句的语句或使用紧随最新的语句调用外过程包含`On Error Resume Next`语句。 此语句允许执行运行时错误时仍继续。 你可以将会出现错误的错误处理例程，而不是将控制转移到过程内的另一个位置。 `On Error Resume Next`语句变为非活动状态时调用另一个过程，因此应执行`On Error Resume Next`中每个语句调用例程，如果你想内联错误处理中该例程。  
  
> [!NOTE]
>  `On Error Resume Next`构造可能优于`On Error GoTo`时处理期间对其他对象的访问生成的错误。 检查`Err`与对象的每个交互清楚地了解对象所访问的代码后。 你可以将确定哪些对象放置中的错误代码`Err.Number`，以及哪些对象最初生成错误 (中指定的对象`Err.Source`)。  
  
## <a name="on-error-goto-0"></a>On Error GoTo 0  
 `On Error GoTo 0`禁用当前的过程中的错误处理。 它不会作为错误处理代码中，开始指定 0 行，即使过程包含编号为 0 的行。 而无需`On Error GoTo 0`过程退出时，会自动禁用语句，错误处理程序。  
  
## <a name="on-error-goto--1"></a>On Error GoTo-1  
 `On Error GoTo -1`禁用当前的过程中的异常。 即使过程包含编号为-1 的行，它不作为错误处理代码中，开始指定行-1。 而无需`On Error GoTo -1`过程退出时，会自动禁用语句，异常。  
  
 若要防止错误处理代码运行时未发生错误，将放置`Exit Sub`， `Exit Function`，或`Exit Property`语句之前的错误处理例程，如以下片段中所示：  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 在这里，错误处理代码遵循`Exit Sub`语句位于`End Sub`语句以将其与过程流。 可以将错误处理代码放置在过程中的任意位置。  
  
## <a name="untrapped-errors"></a>无法捕获的错误  
 当对象的可执行文件以运行时无法捕获的错误，在对象中返回给控制应用程序。 在开发环境中，无法捕获的错误返回到控制应用程序仅当设置了正确的选项。 请参阅有关种选项应为在调试过程中的集、 如何进行设置，和主机是否可以创建类的说明的主机应用程序的文档。  
  
 如果创建了访问其他对象的对象，你应尝试处理它们可能传回任何未处理的错误。 如果你不能映射中的错误代码`Err.Number`到其中一个你自己的错误，然后将传递它们重新添加到你的对象的调用方。 你应通过添加你的错误代码来指定错误`VbObjectError`常量。 例如，如果你的错误代码是 1052年，将其分配，如下所示：  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  对 Windows 动态链接库 (Dll) 的调用期间的系统错误不会引发异常和无法困在 Visual Basic 错误捕获。 当调用 DLL 函数，应检查成功或失败 （根据 API 规范），每个返回值和出现故障，请检查此值`Err`对象的`LastDLLError`属性。  
  
## <a name="example"></a>示例  
 此示例首先使用`On Error GoTo`语句指定的过程中的错误处理例程的位置。 在示例中，尝试除以零会生成错误编号为 6。 错误处理中的错误处理例程，并且控件然后返回到导致错误的语句。 `On Error GoTo 0`语句关闭错误捕获。 则`On Error Resume Next`语句用于推迟错误捕获，以便可以为某些已知所生成错误的下一个语句的上下文。 请注意，`Err.Clear`用于清除`Err`处理该错误后的对象的属性。  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## <a name="requirements"></a>惠?  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Resume 语句](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [错误消息](../../../visual-basic/language-reference/error-messages/index.md)  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
