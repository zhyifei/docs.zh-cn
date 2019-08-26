---
title: 通过实例访问共享成员；将不计算限定表达式
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947701"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>通过实例访问共享成员；将不计算限定表达式
类或结构的实例变量用于访问`Shared`在该类或结构中定义的变量、属性、过程或事件。 如果使用实例变量访问类或结构的隐式共享成员 (如常量或枚举) 或嵌套的类或结构, 也会出现此警告。  
  
 共享成员的目的是仅创建该成员的单个副本, 并使该单一副本可用于声明它的类或结构的每个实例。 它与此目的是为了通过其类`Shared`或结构的名称访问成员, 而不是通过包含该类或结构的单个实例的变量来访问成员。  
  
 通过实例变量访问`Shared`成员可以使代码更难理解,因为这样可以隐藏成员的事实。`Shared` 此外, 如果此类访问是执行其他操作 (例如`Function`返回共享成员实例的过程) 的表达式的一部分, Visual Basic 会绕过该表达式以及它将以其他方式执行的任何其他操作。  
  
 有关详细信息和示例, 请参阅[Shared](../../../visual-basic/language-reference/modifiers/shared.md)。  
  
 默认情况下，此消息是一个警告。 若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42025  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 使用定义`Shared`要访问的成员的类或结构的名称, 如下面的示例中所示。  
  
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
> 当两个编程元素具有相同的名称时, 请通知作用域的影响。 在上面的示例中, 如果使用`Dim testClass as testClass = Nothing`声明实例, 则编译器会将`testClass.sayHello()`调用视为通过类名称访问方法, 而不会出现警告。  
  
## <a name="see-also"></a>请参阅

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [范围 Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
