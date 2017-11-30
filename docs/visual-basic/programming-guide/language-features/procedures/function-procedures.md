---
title: "Function 过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9520a6555e65fd801a5c40d40748028e04a10739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="function-procedures-visual-basic"></a>Function 过程 (Visual Basic)
A`Function`过程是一系列[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]语句括`Function`和`End Function`语句。 `Function`过程执行任务，再将控制权返回给调用代码。 当它返回控件时，它还到调用代码返回一个值。  
  
 每次调用过程时，运行，其语句开头的第一个可执行语句后`Function`语句和与第一个结束`End Function`， `Exit Function`，或`Return`遇到的语句。  
  
 你可以定义`Function`模块、 类或结构中的过程。 它是`Public`默认情况下，这意味着你可以从任何位置调用它有权访问模块、 类或结构定义它的应用程序中。  
  
 A`Function`过程可以采用自变量，如常量、 变量或表达式，通过调用代码传递给它。  
  
## <a name="declaration-syntax"></a>声明语法  
 声明的语法`Function`过程是，如下所示：  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *修饰符*可以指定访问级别和有关重载、 重写、 共享和隐藏信息。 有关详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。  
  
 声明每个参数使用的相同方式为[Sub 过程](./sub-procedures.md)。  
  
### <a name="data-type"></a>数据类型  
 每个`Function`过程具有数据类型，只需为每个变量一样。 此数据类型由指定`As`中的子句`Function`语句，并决定该函数返回到调用代码的值的数据类型。 下面的示例声明说明这一点。  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 有关详细信息，请参阅"部分" [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。  
  
## <a name="returning-values"></a>返回值  
 值`Function`过程将发送回调用代码调用它的返回值。 此过程返回此值在两种方式之一：  
  
-   它使用`Return`语句以指定返回值，并返回给调用程序立即控制。 下面的示例阐释了这一点。  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   它将值分配给它自己在过程的一个或多个语句中的函数名称。 控件不会返回之前调用程序`Exit Function`或`End Function`执行语句。 下面的示例阐释了这一点。  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 返回值分配到函数名称的优点是： 控件未返回从过程直到它遇到`Exit Function`或`End Function`语句。 这允许您指定一个初步的值，它更高版本在必要时调整。  
  
 有关返回值的详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。 有关返回数组的信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
## <a name="calling-syntax"></a>调用语法  
 调用`Function`通过包括其名称和参数放在右侧的赋值语句或表达式中的过程。 你必须提供值的所有参数，不是可选的并且必须将自变量列表括在括号中。 如果未不提供任何参数，你可以选择省略括号。  
  
 针对调用语法`Function`过程是，如下所示：  
  
 *左值*`=`*functionname* `[(` *argumentlist*    `)]`  
  
 `If ((`*functionname* `[(` *argumentlist* `)] / 3) <=`*表达式*  `) Then`  
  
 当调用`Function`过程中，则不需要使用其返回值。 如果不这样做，将执行的函数的所有操作，而将忽略返回值。 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>通常会调用这种方式。  
  
### <a name="illustration-of-declaration-and-call"></a>声明和调用图  
 以下`Function`过程计算的最长端或斜边直角三角形，其他两条边为给定的值。  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 下面的示例演示典型调用`hypotenuse`。  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [如何：创建返回值的过程](./how-to-create-a-procedure-that-returns-a-value.md)  
 [如何：从过程返回值](./how-to-return-a-value-from-a-procedure.md)  
 [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)
