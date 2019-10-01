---
title: 无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: ba14c0cd8781b8771ac8b746e3efec29a457294a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701181"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>无法将匿名类型转换为表达式树，因为它包含用于初始化另一个字段的字段
当使用匿名类型的一个属性来初始化匿名类型的其他属性时，编译器不会接受从匿名转换为表达式树的情况。 例如，在下面的代码中，在初始化列表中声明 `Prop1`，然后将其用作 @no__t 的初始值。  
  
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
  
 **错误 ID：** BC36548  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 将 @no__t 值的初始值分配给本地变量。 将该变量分配给 @no__t 0 和 `Prop2`，如以下代码所示。  
  
    ```vb  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>请参阅

- [匿名类型（Visual Basic）](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [表达式树 (Visual Basic)](../../programming-guide/concepts/expression-trees/index.md)
- [如何：使用表达式树来生成动态查询（Visual Basic） ](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
