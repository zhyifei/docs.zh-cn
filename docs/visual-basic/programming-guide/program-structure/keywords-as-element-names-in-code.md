---
title: "代码中用作元素名称的关键字 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f410a0eaac0dcc034d406a89ed1d01a8f228a583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>代码中用作元素名称的关键字 (Visual Basic)
任何程序元素-例如变量、 类或成员-可以具有相同的名称与受限制的关键字。 例如，可以创建一个名为变量`Loop`。 但是，来指代你版-它具有与同名的受限`Loop`关键字-必须在它前面加上一个完全限定字符串，或将它括在方括号 (`[ ]`)，如下面的示例所示。  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 如果你不执行其中一种，则 Visual Basic 假设的内部函数的使用`Loop`关键字，并生成错误，如以下示例所示：  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 在引用窗体和控件，以及时，可以使用方括号声明一个变量或与受限制的关键字定义具有相同名称的过程。 将很容易忘记限定名称或包含方括号，因此将错误引入到你的代码并导致更难以读取。 为此，我们建议你不要将受限制的关键字用作的程序元素的名称。 但是，如果将来版本的 Visual Basic 定义了一个新的关键字冲突，与现有窗体或控件名称，然后你可以使用此方法更新你的代码时要使用新版本。  
  
> [!NOTE]
>  程序还可能包括由其他引用的程序集的元素名称。 如果这些名称与受限制的关键字冲突，然后加上方括号围绕它们会导致 Visual Basic 将解释为您定义的元素。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)
