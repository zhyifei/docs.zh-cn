---
title: 对象变量赋值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: f20a03c4d9a0e33203629ae066686f4c9f25c105
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656053"
---
# <a name="object-variable-assignment-visual-basic"></a>对象变量赋值 (Visual Basic)
你可以使用普通赋值语句将对象分配给对象变量。 你可以分配对象表达式或[执行任何操作](../../../../visual-basic/language-reference/nothing.md)关键字，如下面的示例演示。  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing` 意味着没有当前分配给变量对象。  
  
## <a name="initialization"></a>初始化  
 当你的代码开始运行，你的对象变量将初始化为`Nothing`。 这些声明中包含的初始化被重新初始化为指定的声明语句执行时的值。  
  
 您可以通过使用包括的声明初始化[新建](../../../../visual-basic/language-reference/operators/new-operator.md)关键字。 下面的声明语句声明对象变量`testUri`和`ver`并向它们分配特定的对象。 每个可以使用一种适当的类的重载构造函数来初始化对象。  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>解除关联  
 将对象变量设置为`Nothing`终止与任何特定的对象变量的关联。 这会防止意外更改通过更改变量的对象。 它还允许你可以测试是否对象变量指向有效的对象，如以下示例所示。  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 如果你变量引用的对象是在另一个应用程序中，无法确定此测试，该应用程序是否已终止或只需失效的对象。  
  
 对象变量值为`Nothing`也被称为*null 引用*。  
  
## <a name="current-instance"></a>当前实例  
 *当前实例*的对象是当前在其中执行代码。 由于所有代码的都执行过程内，当前实例是在其中调用此过程。  
  
 `Me`关键字作为引用的当前实例的对象变量。 如果不是一个过程[共享](../../../../visual-basic/language-reference/modifiers/shared.md)，它可以使用`Me`关键字用于获取指向当前实例。 共享的过程不能与类的特定实例关联。  
  
 使用`Me`很适合用于将当前实例传递给另一个模块中的过程。 例如，假设你有大量的 XML 文档，想要将一些标准的文本添加到所有这些。 下面的示例定义一个过程来执行此操作。  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 然后，每个 XML 文档对象无法调用的过程，并将它的当前实例作为参数传递。 下面的示例演示这一操作。  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>请参阅  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [如何： 声明对象变量并在 Visual Basic 中为其分配一个对象](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [如何：使对象变量不引用任何实例](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
