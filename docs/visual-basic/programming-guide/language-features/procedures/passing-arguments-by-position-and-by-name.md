---
title: "按位置和名称传递自变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>按位置和名称传递自变量 (Visual Basic)
当调用`Sub`或`Function`过程中，你可以将参数传递*按位置*— 在过程定义中出现的顺序 — 或将它们传递*按名称*，而无需考虑位置。  
  
 当你按名称传递自变量时，你指定参数的声明名称后跟冒号和等号 (`:=`) 后, 跟自变量值。 你可以提供命名自变量的任何顺序。  
  
 例如，以下`Sub`过程使用三个参数：  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 在调用此过程时，你可以提供的自变量按位置、 按名称，或通过使用这两者的混合。  
  
## <a name="passing-arguments-by-position"></a>按位置传递自变量  
 您可以调用过程`studentInfo`参数传递的位置并且用逗号分隔，如下面的示例中所示：  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 如果省略可选的参数位置自变量列表中，你必须保留它用逗号分隔的位置。 下面的示例调用`studentInfo`而无需`age`自变量：  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a>按名称传递自变量  
 或者，可以调用`studentInfo`按名称传递自变量也用逗号分隔，如下面的示例中所示：  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>混合自变量按位置和名称  
 你可以提供自变量的位置和名称的单一过程调用中，如下面的示例中所示：  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 在前面的示例中，没有多余的逗号是保存的省略的位置所需`age`自变量，因为`birth`按名称传递了。  
  
 自变量提供的混合的位置和名称、 位置自变量时，都必须放在第一个。 一旦你按名称提供自变量，其余的自变量都必须是按名称。  
  
## <a name="supplying-optional-arguments-by-name"></a>提供按名称的可选自变量  
 在调用了具有多个可选参数的过程时，按名称传递自变量是特别有用。 如果按名称提供自变量，你不需要使用连续的逗号来表示缺少位置自变量。 按名称传递自变量还可以更轻松地跟踪的哪些参数将传递和你省略哪些功能。  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a>提供自变量按名称的限制  
 你不能按名称来避免输入所需的参数传递自变量。 可以省略仅的可选自变量。  
  
 你不能按名称传递参数数组。 这是因为在调用过程时，你提供的参数数组中，逗号分隔的参数数量不确定，并且编译器不能将多个自变量与单个名称关联。  
  
## <a name="see-also"></a>另请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [可选参数](./optional-parameters.md)  
 [参数数组](./parameter-arrays.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
