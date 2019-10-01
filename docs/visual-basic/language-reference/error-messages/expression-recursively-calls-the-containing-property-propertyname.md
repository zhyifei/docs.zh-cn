---
title: 表达式递归调用包含属性“<propertyname>”
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698569"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>表达式递归调用包含属性 "\<propertyname >"
属性定义的 @no__t 的语句中的语句将值存储到属性的名称中。  
  
 保存属性值的建议方法是在属性的容器中定义一个 @no__t 0 变量，并将其用于 @no__t 和 @no__t 2 过程。 然后 `Set` 过程应在此 `Private` 变量中存储传入值。  
  
 @No__t 的过程的行为类似于 @no__t 1 过程，因此它可以通过遇到 @no__t 2 语句，为属性名称赋值并返回控制权。 不过，建议的方法是在[返回语句](../../../visual-basic/language-reference/statements/return-statement.md)中包含 `Private` 变量作为值。  
  
 @No__t 的过程的行为类似于 @no__t 1 过程，该过程不返回值。 因此，该过程或属性名称在 @no__t 的过程中没有特殊含义，因此不能在其中存储值。  
  
 下面的示例说明了可能导致此错误的方法，并遵循建议的方法。  
  
```vb  
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
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID：** BC42026  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 如前面的示例所示，重写属性定义以使用建议的方法。  
  
## <a name="see-also"></a>请参阅

- [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)
