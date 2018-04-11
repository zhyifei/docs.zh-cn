---
title: 通过实例访问共享成员；将不计算限定表达式
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bcf3c37852e73464eec612e9e1d458ca707342e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>通过实例访问共享成员；将不计算限定表达式
使用类或结构的一个实例变量访问`Shared`变量、 属性、 过程或在该类或结构中定义的事件。 如果使用实例变量访问的类或结构，例如常量或枚举，或一个嵌套的类或结构的隐式共享的成员，也会发生此警告。  
  
 共享成员的目的是创建仅该成员的单个副本并将该单个副本提供的类或结构声明它的每个实例。 它是与此目的访问一致`Shared`成员通过其类或结构的名称而不是包含的单独实例，该类或结构的变量。  
  
 访问`Shared`成员通过实例变量会导致代码更难理解通过隐藏该成员是事实`Shared`。 此外，如果表达式的一部分进行访问时，将执行其他操作，如`Function`返回的共享成员，实例的过程[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将忽略表达式以及它将执行的任何其他操作。  
  
 有关详细信息及示例，请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42025  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用的类或结构，它定义名称`Shared`成员来访问它，如下面的示例中所示。  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  当两个编程元素具有相同名称时，则发出警报的作用域的效果。 在上一示例中，如果你使用声明实例`Dim testClass as testClass = Nothing`，编译器将调用`testClass.sayHello()`通过类名称和任何警告的方法的访问权限发生时。  
  
## <a name="see-also"></a>另请参阅  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [在 Visual Basic 中的作用域](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
