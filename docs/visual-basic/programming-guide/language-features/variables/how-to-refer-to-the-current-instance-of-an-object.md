---
title: "如何：引用对象的当前实例 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>如何：引用对象的当前实例 (Visual Basic)
*当前实例*对象是当前在其中执行代码的实例。  
  
 你使用`Me`关键字来引用当前实例。  
  
### <a name="to-refer-to-the-current-instance"></a>若要引用的当前实例  
  
-   使用`Me`通常应使用对象变量的名称的关键字。  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     尽管`Me`行为类似对象变量，你不能将其声明或向它分配任何内容。 `Me`始终引用当前实例。  
  
## <a name="see-also"></a>另请参阅  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
