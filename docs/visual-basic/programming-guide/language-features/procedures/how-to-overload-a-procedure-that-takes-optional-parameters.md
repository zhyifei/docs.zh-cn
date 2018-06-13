---
title: 如何：重载带有可选参数的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 1da1d67726a9669477721aabc0aace0119aa7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652891"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>如何：重载带有可选参数的过程 (Visual Basic)
如果过程有一个或多个[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数，不能定义匹配任何其隐式重载的重载的版本。 有关详细信息，请参见"隐式重载为可选参数"[中重载过程注意事项](./considerations-in-overloading-procedures.md)。  
  
## <a name="one-optional-parameter"></a>一个可选参数  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>若要重载采用一个可选参数的过程  
  
1.  编写`Sub`或`Function`参数列表中包含的可选参数的声明语句。 不要使用`Optional`此重载版本中的关键字。  
  
2.  位于之前`Sub`或`Function`关键字后的跟[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。  
  
3.  编写调用的代码提供的可选参数时应执行的过程代码。  
  
4.  终止与过程`End Sub`或`End Function`作为适当的语句。  
  
5.  编写等同于第一个声明，只不过它不包括可选的参数在参数列表中的第二个声明语句。  
  
6.  写入时调用的代码不会提供可选自变量应执行该过程代码。 终止与过程`End Sub`或`End Function`作为适当的语句。  
  
     下面的示例演示一个定义带可选参数，一组等效的两个重载的过程，最后的和示例无效且有效的重载版本的过程。  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a>多个可选参数  
 对于带多个可选参数的过程，你通常需要两个以上的重载的版本。 例如，如果有两个可选参数，并且调用代码可以提供或省略相互独立的每一个，则需要四个重载的版本，分别针对每个可能提供的自变量的组合。  
  
 当可选参数的数目增加时，会增加重载的复杂性。 除非不接受提供的自变量的某些组合，为 N 可选参数中需要 2 ^ N 重载版本。 根据过程的性质，你可能会发现的逻辑清晰度对齐定义所有重载的版本的额外工作。  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>若要重载采用多个可选参数的过程  
  
1.  确定提供的可选自变量的组合可接受的过程的逻辑。 如果依赖于另一个可选参数，则可能会出现不可接受的组合。 例如，如果一个参数接受一个配偶的姓名，另一个接受配偶的年龄是不可接受的自变量提供年龄但省略名称组合。  
  
2.  对于提供的可选自变量的每个可接受组合，编写`Sub`或`Function`定义相应的参数列表的声明语句。 不要使用`Optional`关键字。  
  
3.  在每个声明，位于之前`Sub`或`Function`关键字后的跟[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。  
  
4.  以下每个声明，编写调用的代码提供对应于该声明的参数列表的自变量列表时应执行该过程代码。  
  
5.  终止与每个过程`End Sub`或`End Function`作为适当的语句。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [可选参数](./optional-parameters.md)  
 [参数数组](./parameter-arrays.md)  
 [过程重载](./procedure-overloading.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)  
 [如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)  
 [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [重载决策](./overload-resolution.md)
