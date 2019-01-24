---
title: 如何：调用重载的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 8320bc550c818fd2bea53f75107709eab8456096
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706412"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>如何：调用重载的过程 (Visual Basic)
重载过程的优点是在调用的灵活性。 调用代码可以获取要传递给该过程，然后调用单个过程名称，无论它传递哪些参数所需的信息。  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>调用已定义的多个版本的过程  
  
1.  在调用代码中，确定要传递给过程的数据。  
  
2.  以正常方式表示的参数列表中的数据写入过程调用。 请确保参数匹配的参数列表中为过程定义的版本之一。  
  
3.  无需确定要调用的过程的哪个版本。 Visual Basic 将控制传递给参数列表匹配的版本。  
  
     下面的示例调用`post`过程中声明[如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)。 它获取的客户标识，确定它是否`String`或`Integer`，然后在任一情况下调用相同的过程。  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>请参阅
- [过程](./index.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [过程重载](./procedure-overloading.md)
- [过程疑难解答](./troubleshooting-procedures.md)
- [如何：定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md)
- [如何：重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [如何：重载的参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [重载过程注意事项](./considerations-in-overloading-procedures.md)
- [重载决策](./overload-resolution.md)
- [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)
