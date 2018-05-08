---
title: 如何：重载参数数量不确定的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 026dd59db135e8b195ae014aaff5e3a6a7846fc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>如何：重载参数数量不确定的过程 (Visual Basic)
如果过程有[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，不能定义采用一维数组的参数数组的重载的版本。 有关详细信息，请参阅"隐式重载为 ParamArray 参数"中[中重载过程注意事项](./considerations-in-overloading-procedures.md)。  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>若要重载采用数量可变的参数的过程  
  
1.  确定该过程，并调用代码逻辑受益于重载从多个版本`ParamArray`参数。 请参阅中的"重载和参数"[重载过程注意事项](./considerations-in-overloading-procedures.md)。  
  
2.  确定的第几个提供的值，则过程应接受在参数列表的变量部分。 这可能包括的任何值，这种情况，并且它可能包含一个单一的一维数组的大小写。  
  
3.  为每个可接受提供的值数，编写`Sub`或`Function`定义相应的参数列表的声明语句。 请勿使用`Optional`或`ParamArray`此重载版本中的关键字。  
  
4.  在每个声明，位于之前`Sub`或`Function`关键字后的跟[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。  
  
5.  以下每个声明，编写调用的代码提供对应于该声明的参数列表值时应执行该过程代码。  
  
6.  终止与每个过程`End Sub`或`End Function`作为适当的语句。  
  
## <a name="example"></a>示例  
 下面的示例演示用定义的过程[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，然后一组等效的重载过程。  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 无法重载采用一维数组的参数数组的参数列表的此类的过程。 但是，你可以使用其他隐式重载的签名。 以下声明说明这一点。  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 这些重载版本中的代码不需要测试是否调用的代码提供的一个或多个值`ParamArray`参数，或如果是这样，多少。 Visual Basic 将控制权传递给匹配调用实参列表的版本。  
  
## <a name="compiling-the-code"></a>编译代码  
 因为使用为过程`ParamArray`参数的值等效于一组重载版本，你无法使用与这些隐式重载任一对应的参数列表来重载这样的过程。 有关详细信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。 如果你接受一个参数数组，你应测试调用代码传递给它，该数组的长度，并采取适当的措施，如果你的应用程序太大。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [可选参数](./optional-parameters.md)  
 [参数数组](./parameter-arrays.md)  
 [过程重载](./procedure-overloading.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)  
 [如何：调用重载过程](./how-to-call-an-overloaded-procedure.md)  
 [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [重载决策](./overload-resolution.md)
