---
title: 参数和自变量之间的差异 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a5075c218371b754ac883b97475ab941811966b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>参数和自变量之间的差异 (Visual Basic)
在大多数情况下中的过程必须具有已在其中调用它的情况有关的一些信息。 执行重复或共享任务过程每个调用使用不同的信息。 此信息包含变量、 常量和调用它时传递给过程的表达式。  
  
 此将信息传递给该过程，为过程所定义*参数*，然后调用代码将传递*参数*给该参数。 你可以将参数作为一个停车和当作一辆汽车的自变量。 就像不同的汽车可以在不同时间停放停车空间，调用代码可以传递不同的自变量相同的参数到每次调用过程时。  
  
## <a name="parameters"></a>参数  
 A*参数*表示过程希望在调用它时传递的值。 过程声明定义其参数。  
  
 在定义`Function`或`Sub`过程，你指定*参数列表*直接在过程名称后面的括号中。 对于每个参数，您可以指定名称、 数据类型和传递机制 ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md))。 您还可以指示参数是可选。 这意味着调用的代码不需要传递的值。  
  
 每个参数的名称用作*局部变量*过程中。 你使用的参数名称相同的方式使用任何其他变量。  
  
## <a name="arguments"></a>自变量  
 *参数*表示在调用过程时传递给过程参数的值。 在调用该过程时，调用代码将提供自变量。  
  
 当调用`Function`或`Sub`过程，包括*自变量列表*直接在过程名称后面的括号中。 每个自变量对应于列表中的相同位置中的参数。  
  
 与参数定义自变量没有名称。 每个自变量是一个表达式，它可以包含零个或多个变量、 常量和文本。 计算的表达式的数据类型通常应匹配定义的相应参数的数据类型，并在任何情况下必须能够转换为参数类型。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [Function 过程](./function-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [如何：为过程定义参数](./how-to-define-a-parameter-for-a-procedure.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [递归过程](./recursive-procedures.md)  
 [过程重载](./procedure-overloading.md)
