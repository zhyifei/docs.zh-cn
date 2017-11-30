---
title: "无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords: BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c2cf8a40060359393807cfb648c46fef9ed853af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段
当匿名类型的一个属性用于初始化匿名类型的另一个属性时，编译器不接受的匿名为表达式树的转换。 例如，在下面的代码中，`Prop1`是声明的初始化列表中，然后用作的初始值`Prop2`。  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **错误 ID:** BC36548  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   分配的初始值`Prop1`到本地变量。 将该变量分配到同时`Prop1`和`Prop2`，如下面的代码中所示。  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [表达式树](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [如何：使用表达式树来生成动态查询](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
