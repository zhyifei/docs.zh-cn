---
title: 如何：创建过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: da4cc299fbe35702990a62b5bf824e3ac71d5902
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649258"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>如何：创建过程 (Visual Basic)
你将包含起始的声明语句之间的过程 (`Sub`或`Function`) 和结束的声明语句 (`End Sub`或`End Function`)。 过程的所有代码均位于这些语句之间。  
  
 过程不能包含另一个过程，因此其起始和结束语句必须位于任何其他过程之外。  
  
 如果你有在不同的位置执行相同的任务的代码，你可以编写将任务作为过程一次，然后调用它从不同的位置在代码中。  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>若要创建过程，它不返回值  
  
1.  在任何其他过程之外使用`Sub`语句后, 跟`End Sub`语句。  
  
2.  在`Sub`语句，请按照`Sub`关键字的过程中，然后在括号中的参数列表的名称。  
  
3.  放置过程的代码语句之间`Sub`和`End Sub`语句。  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>创建过程中返回一个值  
  
1.  在任何其他过程之外使用`Function`语句后, 跟`End Function`语句。  
  
2.  在`Function`语句，请按照`Function`关键字的过程中，然后在括号中的参数列表的名称，然后`As`子句，用于指定返回值的数据类型。  
  
3.  放置过程的代码语句之间`Function`和`End Function`语句。  
  
4.  使用`Return`语句返回值返回到调用代码。  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>若要将新的过程与旧的重复代码块连接起来  
  
1.  请确保你在其中的旧代码有权访问它的位置来定义新的过程。  
  
2.  在旧的重复代码块，将执行该重复任务的调用的单个语句的语句`Sub`或`Function`过程。  
  
3.  如果过程是`Function`返回一个值，请确保调用语句中执行了操作与返回的值，如将其存储在变量中，否则将丢失的值。  
  
## <a name="example"></a>示例  
 以下`Function`过程计算的最长端或斜边直角三角形，其他两条边为给定的值。  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>请参阅

 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [递归过程](./recursive-procedures.md)  
 [过程重载](./procedure-overloading.md)  
 [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [面向对象的编程 (Visual Basic)](../../concepts/object-oriented-programming.md)  
