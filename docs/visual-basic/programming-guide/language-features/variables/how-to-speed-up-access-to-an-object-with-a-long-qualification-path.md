---
title: 如何：加速访问具有长限定路径的对象 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650194"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>如何：加速访问具有长限定路径的对象 (Visual Basic)
如果你经常访问的对象需要多个方法和属性的限定路径，可以通过不重复限定路径来加快你的代码。  
  
 有两种方法可以避免重复限定路径。 你可以将对象分配给一个变量，或者可以使用它在`With`...`End With`块。  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>为了加快访问对很大程度限定对象为其分配给一个变量  
  
1.  声明要经常访问的对象类型的变量。 在声明的初始化部分中指定限定路径。  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  使用变量来访问该对象的成员。  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>为了加快访问对很大程度限定对象通过使用 With...End With 块  
  
1.  置于限定路径`With`语句。  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  访问内的对象的成员`With`阻止，之前`End With`语句。  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>请参阅  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [With...End With 语句](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
