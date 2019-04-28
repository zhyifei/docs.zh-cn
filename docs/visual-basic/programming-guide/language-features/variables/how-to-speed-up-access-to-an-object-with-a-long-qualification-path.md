---
title: 如何：加速访问具有长限定路径 (Visual Basic 中) 的对象
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 94c838a69aab9fcae9dc0c79b6038ee90e2369e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769039"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>如何：加速访问具有长限定路径 (Visual Basic 中) 的对象
如果经常访问的对象需要多个方法和属性的限定路径，可以通过不重复限定路径来加快你的代码。  
  
 有两种方法可以避免重复限定路径。 可以将对象分配给一个变量，也可以使用它在`With`...`End With`块。  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>若要加速访问很大程度限定对象将其分配给一个变量  
  
1. 声明要经常访问的对象类型的变量。 在声明的初始化部分中指定的限定路径。  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2. 使用变量来访问该对象的成员。  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>若要加速访问很大程度限定对象通过使用 With...End With 块  
  
1. 将限定路径放在`With`语句。  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2. 访问内部对象的成员`With`阻止，之前`End With`语句。  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>请参阅

- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [With...End With 语句](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
