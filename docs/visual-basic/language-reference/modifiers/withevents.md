---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68a58fd130c04f2ed0cb1f2e5b9250f6c85f120d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
指定一个或多个声明的成员变量引用可以引发事件的类的实例。  
  
## <a name="remarks"></a>备注  
 当使用定义变量`WithEvents`，你可以以声明方式指定一种方法处理使用的变量的事件`Handles`关键字。  
  
 你可以使用`WithEvents`只能在类或模块级别。 这意味着的声明上下文`WithEvents`变量必须是类或模块，而不能是源文件、 命名空间、 结构或过程。  
  
 不能使用`WithEvents`结构成员上。  
  
 可以通过声明仅单个变量-不数组-与`WithEvents`。  
  
## <a name="rules"></a>规则  
  
-   **元素类型。** 必须声明`WithEvents`变量是对象变量，以便它们可以接受类实例。 但是，您無法宣告它们作为`Object`。 你必须将它们声明为可引发事件的特定类。  
  
 `WithEvents`修饰符可用于在此上下文中： [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
