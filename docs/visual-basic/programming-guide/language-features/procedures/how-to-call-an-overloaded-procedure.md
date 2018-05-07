---
title: 如何：调用重载过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 802a312d6ec6640594f3c6b662202d1ffcf2376d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>如何：调用重载过程 (Visual Basic)
重载过程的优点是在调用的灵活性。 调用代码可以获得它需要传递给过程，然后调用的单一过程名称，无论它传递的哪些自变量的信息。  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>若要调用具有多个定义版本的过程  
  
1.  在调用代码中，确定要传递给过程的数据。  
  
2.  以正常方式，参数列表中提供数据编写过程调用。 请确保参数与参数列表中为过程定义的版本之一相匹配。  
  
3.  无需确定哪个版本的过程调用。 Visual Basic 将控制权传递给匹配自变量列表的版本。  
  
     下面的示例调用`post`过程中，声明[How to： 过程的定义多个版本](./how-to-define-multiple-versions-of-a-procedure.md)。 它会获取的客户标识，确定它是否`String`或`Integer`，然后在任一情况下调用相同的过程。  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [过程重载](./procedure-overloading.md)  
 [过程疑难解答](./troubleshooting-procedures.md)  
 [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)  
 [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [如何：重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [重载过程注意事项](./considerations-in-overloading-procedures.md)  
 [重载决策](./overload-resolution.md)  
 [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)
