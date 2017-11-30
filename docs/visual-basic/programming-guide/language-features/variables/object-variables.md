---
title: "Visual Basic 中的对象变量"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a>Visual Basic 中的对象变量
除了直接存储值，变量还可以引用的对象。 出于相同原因向变量分配任何值，可以向变量分配一个对象：  
  
-   变量名称通常是更短且易于记住比的方法和属性访问的对象本身所需的完整路径。  
  
-   使用引用的对象的变量是比重复通过所需的方法或属性访问的对象本身更高效。  
  
-   你可以更改一个变量来运行你的代码时引用其他对象。  
  
## <a name="making-code-shorter"></a>使代码更短  
 可以使用对象变量来缩短的代码，你已为类型。 下面的示例使用方法和属性的完整路径访问<xref:System.Windows.Forms.Control>对象。  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 你可以缩短此代码中，并加快执行，如果你使用的对象变量进行控制。 你应声明对象变量与你想要向其分配特定类 (`Control`在这种情况下)。 一旦你将对象分配给该变量时，你可以它完全相同的方式来处理将它所引用的对象。 你可以设置或检索该对象的属性或使用任何其方法。 下面的示例使用对象变量来简化在前面的示例代码。  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>另请参阅  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [如何：加速访问具有长限定路径的对象](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
