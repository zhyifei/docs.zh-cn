---
title: 递归过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 8ea7741c943ea563fbd0c7649ac0ff85b2f9ebba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="recursive-procedures-visual-basic"></a>递归过程 (Visual Basic)
A*递归*过程是指调用自身。 一般情况下，这不是编写 Visual Basic 代码的最有效方法。  
  
 以下过程使用递归将计算其原始的自变量的阶乘。  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>递归过程注意事项  
 **限制条件**。 必须设计一个用于测试可以终止递归的至少一个条件的递归过程和你还必须处理其中任何此类条件满足中合理数目的递归调用这种情况。 没有可以满足而不会出现的至少一个条件，您的过程运行在无限循环中执行的高风险。  
  
 **内存使用率**。 将应用程序将有限的本地变量的空间量。 过程调用其自身，每次它使用多个该空间的其本地变量的其他副本。 如果此过程将无限期地继续，则最终会导致<xref:System.StackOverflowException>错误。  
  
 **效率**。 您几乎总是可以替换递归循环。 循环没有初始化其他存储和返回值传递自变量的开销。 你的性能可以大幅提高递归调用。  
  
 **相互递归**。 如果两个过程调用相互，可能会发现很差的性能或甚至产生无限循环。 此类设计展示在单个递归过程中，相同的问题，但很难检测和调试。  
  
 **调用时使用括号**。 当`Function`过程调用其自身以递归方式，你必须在过程名后面加括号，即使没有自变量列表。 否则，执行的函数名称作为表示函数的返回值。  
  
 **测试**。 如果您编写一个递归的过程，你应测试它应非常仔细地以确保始终满足某些限制条件。 你还应该确保你不能运行由于递归调用过多的内存不足。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.StackOverflowException>  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [过程重载](./procedure-overloading.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [异常疑难解答：System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
