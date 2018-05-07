---
title: 默认属性访问之间不明确继承的接口成员&#39; &lt;defaultpropertyname&gt; &#39;的接口&#39; &lt;interfacename1&gt; &#39;和&#39; &lt;defaultpropertyname&gt; &#39;的接口&#39; &lt;interfacename2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 65a10067284cad3bf56ecdc441ebefa0a740ef53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a>默认属性访问之间不明确继承的接口成员&#39; &lt;defaultpropertyname&gt; &#39;的接口&#39; &lt;interfacename1&gt; &#39;和&#39; &lt;defaultpropertyname&gt; &#39;的接口&#39; &lt;interfacename2&gt;&#39;
接口继承自两个接口，其中每个声明具有相同名称的默认属性。 编译器无法解析访问而无需限定此默认属性。 下面的示例阐释了这一点。  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 当指定`testObj(1)`，编译器会尝试将它解析为默认属性。 但是，有两个可能的默认属性由于继承的接口，因此，编译器将引发此错误。  
  
 **错误 ID:** BC30686  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   避免继承具有相同名称的任何成员。 在前面的示例中，如果`testObj`不需要的任何成员，即`Iface2`，然后将其声明，如下所示：  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     -或-  
  
-   在类中实现继承的接口。 然后你可以实现每个具有不同名称的继承属性。 但是，仅有一种可以实现的类的默认属性。 下面的示例阐释了这一点。  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a>请参阅  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
