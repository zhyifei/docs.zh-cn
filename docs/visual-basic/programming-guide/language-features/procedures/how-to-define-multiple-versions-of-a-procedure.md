---
title: 如何：定义一个过程的多个版本 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6db075e9b31355d4a0a593040b1fe7c96a0c730
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>如何：定义一个过程的多个版本 (Visual Basic)
你可以通过多个版本中定义的过程*重载*它在每个版本中使用的相同名称但不同的参数列表。 重载的目的是定义过程的几个密切相关的版本，而无需将它们按名称区分开来。  
  
 有关详细信息，请参阅[过程重载](./procedure-overloading.md)。  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>若要定义过程的多个版本  
  
1.  编写`Sub`或`Function`你想要定义的过程的每个版本的声明语句。 在每个声明中使用相同的过程名称。  
  
2.  位于之前`Sub`或`Function`具有每个声明中的关键字[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。 你可以选择性地省略`Overloads`在声明中，但如果你将其包含在任何声明，您必须将其包含在每个声明。  
  
3.  以下每个声明语句中，编写过程代码以处理其中调用代码提供了该版本的参数列表匹配的自变量的特定情况。 无需测试调用的代码已提供的参数。 Visual Basic 将控制权传递给你的过程中匹配的版本。  
  
4.  终止与过程的每个版本`End Sub`或`End Function`作为适当的语句。  
  
## <a name="example"></a>示例  
 下面的示例定义`Sub`过程针对客户的帐户余额发送一个事务。 它使用`Overloads`关键字来定义两个版本的过程中，一个接受通过帐号按名称和其他客户。  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 调用代码可以获取的客户标识为`String`或`Integer`，然后在任一情况下使用相同的调用语句。  
  
 有关如何调用的这些版本的信息`post`过程，请参阅[如何： 调用重载过程](./how-to-call-an-overloaded-procedure.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
 请确保每个重载版本具有相同的过程名称，但不同的参数列表。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [重载过程注意事项](./considerations-in-overloading-procedures.md)  
 [重载决策](./overload-resolution.md)
