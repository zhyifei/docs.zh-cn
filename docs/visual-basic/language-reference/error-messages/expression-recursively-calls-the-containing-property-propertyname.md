---
title: 表达式递归调用包含属性&#39; &lt;propertyname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f14e2645772b22a8f6ff2385dcd316a42d1d5cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588838"
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>表达式递归调用包含属性&#39; &lt;propertyname&gt;&#39;
中的语句`Set`属性定义的过程将值存储到属性的名称。  
  
 保存属性的值的建议的方法是定义`Private`变量属性的容器中并使用它在这两`Get`和`Set`过程。 `Set`过程然后应将传入值存储在此`Private`变量。  
  
 `Get`过程的行为类似`Function`过程，以便它可以将值分配到属性名称，并将控件返回通过遇到`End Get`语句。 推荐的方法，但是，是包括`Private`变量中的值作为[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。  
  
 `Set`过程的行为类似`Sub`过程，不返回值。 因此，过程或属性名称已在没有特殊含义`Set`过程中，并且你无法将值存储到其中。  
  
 下面的示例演示可能导致此错误，跟建议的方法的方案。  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42026  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   重写要用建议的方法，如前面的示例中所示的属性定义。  
  
## <a name="see-also"></a>请参阅  
 [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)
