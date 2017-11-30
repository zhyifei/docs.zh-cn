---
title: "如何：为过程定义参数 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c909cfe1b45a42aae91948917f310474575f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>如何：为过程定义参数 (Visual Basic)
A*参数*允许调用代码将值传递给过程时它将调用它。 声明一个过程的每个参数相同的方式声明变量，指定其名称和数据类型。 你还指定的传递机制，以及是否是可选参数。  
  
 有关详细信息，请参阅[过程参数和自变量](./procedure-parameters-and-arguments.md)。  
  
### <a name="to-define-a-procedure-parameter"></a>若要定义过程参数  
  
1.  在过程声明中，将添加到过程的参数列表中，用逗号将其与其他参数的参数名称。  
  
2.  确定参数的数据类型。  
  
3.  参数名后面加上`As`子句以指定数据类型。  
  
4.  确定所需的参数的传递机制。 通常情况下参数按值传递，除非你想要能够更改其值调用的代码中的过程。  
  
5.  参数名前面放置[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)指定的传递机制。 有关详细信息，请参阅[差异之间传递自变量传递的值和按引用](./differences-between-passing-an-argument-by-value-and-by-reference.md)。  
  
6.  如果参数是可选的位于之前使用的传递机制[可选](../../../../visual-basic/language-reference/modifiers/optional.md)并按照以等号的参数数据类型 (`=`) 和默认值。  
  
     下面的示例定义的大纲`Sub`带有三个参数的过程。 前两个是必需而且是可选的第三个。 参数声明用逗号分隔的参数列表中。  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     第一个参数接受`customer`对象，和`updateCustomer`可以直接更新传递给该变量`c`因为自变量传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。 过程不能更改的最后两个自变量的值，因为它们的传递[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。  
  
     如果调用的代码不会提供的值`level`参数，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将其设置为默认值为 0。  
  
     如果类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`Off`、`As`子句是可选的当定义参数。 但是，如果任何一个参数使用`As`子句，所有这些必须使用它。 如果类型检查开关`On`、`As`子句是必需的每个参数定义。  
  
     指定所有编程元素的数据类型被称为*强类型化*。 当你将设置`Option Strict On`，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]强制实施强类型化。 这是强烈建议，原因如下：  
  
    -   它使对变量和参数的 IntelliSense 支持。 这样，你可以查看其属性和其他成员，在你的代码中键入。  
  
    -   它允许编译器执行类型检查。 这将有助于捕捉可能会在运行时由于如溢出错误而导致失败的语句。 它还不支持这些选项的对象上捕获对方法的调用。  
  
    -   这会导致你的代码的执行速度更快。 一个原因是，如果你不指定一个编程元素，数据类型[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器会将其分配`Object`类型。 已编译的代码可能需要将之间来回转换`Object`和其他数据类型，这会降低性能。  
  
## <a name="see-also"></a>另请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [递归过程](./recursive-procedures.md)  
 [过程重载](./procedure-overloading.md)  
 [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [面向对象的编程](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
