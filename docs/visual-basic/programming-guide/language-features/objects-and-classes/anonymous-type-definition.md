---
title: 匿名类型定义 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a>匿名类型定义 (Visual Basic)
在响应的匿名类型的实例声明时，编译器将创建包含类型的指定的属性的新类定义。  
  
## <a name="compiler-generated-code"></a>编译器生成的代码  
 以下定义`product`，编译器将创建一个包含属性的新类定义`Name`， `Price`，和`OnHand`。  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 类定义包含类似于下面的属性定义。 请注意，没有任何`Set`键属性的方法。 键属性的值是只读的。  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 此外，匿名类型定义包含一个默认构造函数。 不允许使用需要参数的构造函数。  
  
 类型定义匿名类型声明包含至少一个键属性，如果将继承自的三个成员重写<xref:System.Object>: <xref:System.Object.Equals%2A>， <xref:System.Object.GetHashCode%2A>，和<xref:System.Object.ToString%2A>。 如果不声明了任何键属性，仅<xref:System.Object.ToString%2A>被重写。 重写提供以下功能：  
  
-   `Equals`返回`True`如果两个匿名类型实例相同的实例，或者如果只要满足以下条件：  
  
    -   它们具有相同数量的属性。  
  
    -   属性声明中相同的顺序，具有相同名称和相同的推断类型。 名称比较不区分大小写。  
  
    -   至少一个属性是键属性，与`Key`关键字应用于相同的属性。  
  
    -   比较每个相对应的键属性对返回`True`。  
  
     例如，在以下示例中，`Equals`返回`True`仅为`employee01`和`employee08`。 前面每行指定为什么不匹配的新实例的原因的注释`employee01`。  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode`提供的适当唯一 GetHashCode 算法。 该算法使用仅键的属性来计算哈希代码。  
  
-   `ToString`返回连接的属性值的字符串，如下面的示例中所示。 将包含密钥和非键属性。  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 匿名类型的显式命名的属性不能与这些生成的方法冲突。 也就是说，不能使用`.Equals`， `.GetHashCode`，或`.ToString`以 name 属性。  
  
 包含至少一个匿名类型定义的键属性还实现<xref:System.IEquatable%601?displayProperty=nameWithType>接口，其中`T`是匿名类型的类型。  
  
> [!NOTE]
>  匿名类型声明中，它们出现在同一程序集中、 其属性具有相同名称和相同的推断类型、 属性的声明的相同顺序和相同的属性标记为键属性时，才会创建同一匿名类型。  
  
## <a name="see-also"></a>另请参阅  
 [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [如何：推断匿名类型声明中的属性名和类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
