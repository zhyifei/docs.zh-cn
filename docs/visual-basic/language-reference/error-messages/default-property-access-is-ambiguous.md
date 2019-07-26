---
title: 默认属性访问在接口“<defaultpropertyname>”的继承接口成员“<interfacename1>”和接口“<defaultpropertyname>”的“<interfacename2>”之间不明确
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: a36cfe8e5496bbfd1941afa8a46086491ae96a2a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512751"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>默认属性\<访问在接口 "\<1 >" 和 "\<defaultpropertyname >"\<的继承接口成员 "defaultpropertyname >" 之间不明确。i > "

接口继承自两个接口, 每个接口都声明一个具有相同名称的默认属性。 编译器无法解析对此默认属性的访问, 无需进行限定。 下面的示例阐释了这一点。

```vb
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

指定`testObj(1)`时, 编译器会尝试将其解析为默认属性。 不过, 由于继承了接口, 有两个可能的默认属性, 因此编译器会发出此错误信号。

**错误 ID:** BC30686

## <a name="to-correct-this-error"></a>更正此错误

- 避免继承任何具有相同名称的成员。 在前面的示例中, `testObj`如果不需要的任何成员 ( `Iface2`例如), 请按如下所示声明:

  ```vb
  Dim testObj As Iface1
  ```

  \- 或 -

- 在类中实现继承接口。 然后, 可以用不同的名称实现每个继承的属性。 但是, 其中只有一个可以是实现类的默认属性。 下面的示例阐释了这一点。

  ```vb
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
