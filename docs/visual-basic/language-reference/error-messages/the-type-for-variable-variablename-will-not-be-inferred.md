---
title: 变量的类型&#39; &lt;variablename&gt; &#39;将不无法推断，因为它绑定到封闭范围中的字段
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: cb423e8dcced6956eb86d484607915030c91412b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594278"
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>变量的类型&#39; &lt;variablename&gt; &#39;将不无法推断，因为它绑定到封闭范围中的字段
变量的类型\<variablename > 绑定到封闭范围中的字段，因此将不会推断。 可更改的名称\<variablename >，或使用完全限定的名称 （例如，Me.variablename 或 MyBase.variablename）。  
  
 在代码中的循环控制变量的类或其他封闭作用域的字段具有相同的名称。 因为控制变量用而无需`As`子句，将其绑定到封闭范围中中的字段和编译器不会为它创建一个新的变量或推断出类型。  
  
 在下面的示例中，`Index`中的控制变量`For`语句中，绑定到`Index`字段`Customer`类。 编译器不会创建一个新的变量为控制变量`Index`或推断出类型。  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 默认情况下，此消息是一个警告。 有关如何隐藏警告或如何将警告视为错误的信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42110  
  
### <a name="to-address-this-warning"></a>解决此警告  
  
-   通过将其名称更改为标识符，也不是类的字段的名称使本地循环控制变量。  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   阐明循环控制变量绑定到类字段，前缀`Me.`向变量名称。  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   而不是依靠局部类型推理，使用`As`子句来指定 for 循环控制变量的类型。  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>示例  
 下面的代码演示在位置中的第一个更正与前面的示例。  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>请参阅  
 [Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [如何：引用对象的当前实例](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Me、My、MyBase 和 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
