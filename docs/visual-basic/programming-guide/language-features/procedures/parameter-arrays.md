---
title: "参数数组 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ca2b5f02ac4fb3eb613488c8a9852eb2aa4ce5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-arrays-visual-basic"></a>参数数组 (Visual Basic)
通常情况下，不能调用带多个参数不是过程声明指定的过程。 当你需要自变量数量不确定时，可以声明*参数数组*，这样一个过程来接受参数的值的数组。 不需要知道的参数数组中的元素数，当你定义的过程。 数组大小由每个调用的过程单独确定。  
  
## <a name="declaring-a-paramarray"></a>声明一个参数数组  
 你使用[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)关键字来表示参数列表中的参数数组。 适用以下规则：  
  
-   一个过程只能定义只有一个参数数组，并且它必须在过程定义中的最后一个参数。  
  
-   必须通过值传递参数数组。 是一个很好的编程做法显式包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程定义中的关键字。  
  
-   参数数组是自动可选的。 其默认值为参数数组的元素类型的空一维数组。  
  
-   前面参数数组的所有参数都是必需的。 参数数组必须是唯一的可选参数。  
  
## <a name="calling-a-paramarray"></a>调用一个参数数组  
 时调用过程定义参数数组时，你可以用任何一种通过以下方式来提供自变量：  
  
-   执行任何操作-即，则可以省略[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)自变量。 在这种情况下，将为空数组传递给过程。 你还可以传递[执行任何操作](../../../../visual-basic/language-reference/nothing.md)关键字，使用相同的效果。  
  
-   任意数目的自变量，用逗号分隔列表。 每个自变量的数据类型必须是隐式转换为`ParamArray`元素类型。  
  
-   具有相同的元素类型为参数数组的元素类型数组。  
  
 在所有情况下，在过程中的代码将参数的数组包含与相同的数据类型的元素的一维数组视为`ParamArray`数据类型。  
  
> [!IMPORTANT]
>  每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。 如果你接受一个参数数组，你应进行测试以调用代码传递给它的数组的大小。 如果你的应用程序太大，请采取适当的措施。 有关详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
## <a name="example"></a>示例  
 下面的示例定义和调用函数`calcSum`。 `ParamArray`参数修饰符`args`启用接受数目可变的参数的函数。  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 下面的示例定义了一个带有参数数组，并将输出传递给参数数组的所有数组元素的值。  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)  
 [可选参数](./optional-parameters.md)  
 [过程重载](./procedure-overloading.md)  
 [阵列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
