---
title: "如何：标记语句 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190ec9fc2392e6e4adae9b2b612edd69d73cedfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-label-statements-visual-basic"></a>如何：标记语句 (Visual Basic)
语句块组成的代码由冒号分隔的行。 标识字符串或整数的代码注释行可认为是*标记为*。 语句标签用于将标记的一行代码来确定它适用于使用与语句如`On Error Goto`。  
  
 标签可能任一有效的 Visual Basic 标识符，例如那些标识编程元素-或整数文本。 标签必须出现在代码的源代码行的开头，并必须跟一个冒号，无论是否其后的语句在同一行。  
  
 编译器通过检查行的开头是否与任何已定义的标识符匹配标识标签。 如果不存在，编译器将假定它是一个标签。  
  
 标签具有其自己声明空间，并不会干扰其他标识符。 标签的作用域是方法的正文。 标签声明在任何不明确的情况下将优先。  
  
> [!NOTE]
>  标签仅用于在方法内的可执行语句。  
  
### <a name="to-label-a-line-of-code"></a>若要标记的代码行  
  
-   将跟一个冒号，代码的源代码行开头的标识符。  
  
     例如，以下代码行标记为`Jump`和`120`分别：  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)  
 [已声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
