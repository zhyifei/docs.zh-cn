---
title: Sub 过程 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7258d57d2677042a2020097893a4f7a0adb35508
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="sub-procedures-visual-basic"></a>Sub 过程 (Visual Basic)
A`Sub`过程是一系列 Visual Basic 语句括在`Sub`和`End Sub`语句。 `Sub`过程执行任务，再将控制权返回给调用代码，但是它不会返回一个值调用的代码。  
  
 每次调用过程时，其执行语句，从第一个可执行之后的语句开始`Sub`语句和与第一个结束`End Sub`， `Exit Sub`，或`Return`遇到的语句。  
  
 你可以定义`Sub`模块、 类和结构中的过程。 默认情况下，它是`Public`，这意味着你可以调用它从任意位置有权访问模块、 类或结构定义它的应用程序中。 术语，*方法*，描述`Sub`或`Function`从其定义的外部访问的过程模块、 类或结构。 有关详细信息，请参阅[过程](./index.md)。  
  
 A`Sub`过程可以采用自变量，如常量、 变量或表达式，通过调用代码传递给它。  
  
## <a name="declaration-syntax"></a>声明语法  
 声明的语法`Sub`过程是，如下所示：  
  
 `[` *修饰符* `] Sub` *subname* `[(` *parameterlist*  `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 `modifiers`可以指定访问级别和有关重载、 重写、 共享和隐藏信息。 有关详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。  
  
## <a name="parameter-declaration"></a>参数声明  
 声明类似于如何声明变量时，指定的参数名称和数据类型的每个过程参数。 你还可以指定的传递机制，并指示参数是可选或参数数组。  
  
 在参数列表中每个参数的语法如下所示：  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*`As`*数据类型*   
  
 如果参数是可选的你还必须提供默认值作为其声明的一部分。 用于指定默认值的语法如下所示：  
  
 `Optional [ByVal | ByRef]`  *parametername*`As`*datatype*`=`*defaultvalue*   
  
### <a name="parameters-as-local-variables"></a>作为本地变量的参数  
 当控制权传递给该过程时，每个参数被视为本地变量。 这意味着它的生存期即相同的过程，并且其作用域是整个过程。  
  
## <a name="calling-syntax"></a>调用语法  
 调用`Sub`显式使用独立的调用语句的过程。 不能在表达式中使用其名称调用它。 你必须提供值的所有参数，不是可选的并且必须将自变量列表括在括号中。 如果未不提供任何参数，你可以选择省略括号。 使用`Call`关键字是可选的但不是建议这样做。  
  
 针对调用语法`Sub`过程是，如下所示：  
  
 `[Call]`  *subname* `[(` *argumentlist* `)]`  
  
 你可以调用`Sub`从定义它在类外部的方法。 首先，你必须使用`New`关键字来创建类的实例，或调用的方法返回类的实例。 有关详细信息，请参阅[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)。 然后，使用以下语法来调用`Sub`实例对象上的方法：  
  
 *对象*。*methodname*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>声明和调用图  
 以下`Sub`过程通知计算机运算符哪个任务应用程序即将执行，并且还显示时间戳。 而不是复制此代码开头的每个任务时，应用程序只调用`tellOperator`从不同位置。 每个调用将一个字符串中的传递`task`标识开始执行的任务的自变量。  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 下面的示例演示典型调用`tellOperator`。  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [如何：调用不返回值的过程](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [如何： 在 Visual Basic 中调用事件处理程序](./how-to-call-an-event-handler.md)
