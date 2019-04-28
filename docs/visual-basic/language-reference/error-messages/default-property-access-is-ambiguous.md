---
title: 默认属性访问在接口“<defaultpropertyname>”的继承接口成员“<interfacename1>”和接口“<defaultpropertyname>”的“<interfacename2>”之间不明确
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5f058c8e7d480b9145452ae85f186a6ac2ed0d56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803725"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>默认属性访问之间不明确继承的接口成员的\<defaultpropertyname > 的接口\<interfacename1 >' 和 '\<defaultpropertyname > 的接口\<interfacename2 >
接口继承自两个接口，其中每个声明具有相同名称的默认属性。 编译器无法解析所需的访问而无需限定此默认属性。 下面的示例阐释了这一点。  
  
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
  
- 避免继承具有相同名称的任何成员。 在前面的示例中，如果`testObj`不需要任何的成员，例如， `Iface2`，然后将其声明，如下所示：  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     或  
  
- 在类中实现继承的接口。 然后您可以实现每个具有不同名称的继承属性。 但是，仅有一种可以实现类的默认属性。 下面的示例阐释了这一点。  
  
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

- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
