---
title: 如何：引用对象的当前实例 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: c1b79f1b6a9768941d6fe966c5b5886ea742f808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648354"
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
  
     尽管`Me`行为类似对象变量，你不能将其声明或向它分配任何内容。 `Me` 始终引用当前实例。  
  
## <a name="see-also"></a>请参阅  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
