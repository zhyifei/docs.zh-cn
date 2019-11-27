---
title: Of 子句
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353845"
---
# <a name="of-clause-visual-basic"></a>Of 子句 (Visual Basic)
引入 `Of` 子句，该子句标识*泛型*类、结构、接口、委托或过程中的*类型参数*。 有关泛型类型的信息，请参阅[Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。  
  
## <a name="using-the-of-keyword"></a>使用关键字 of  
 下面的代码示例使用 `Of` 关键字定义带有两个类型参数的类的轮廓。 它通过 <xref:System.IComparable> 接口*限制*`keyType` 参数，这意味着使用的代码必须提供实现 <xref:System.IComparable>的类型参数。 这是必需的，以便 `add` 过程可以调用 <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> 方法。 有关约束的详细信息，请参阅 [Type List](../../../visual-basic/language-reference/statements/type-list.md)。  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 如果你完成了前面的类定义，则可以从它构造各种 `dictionary` 类。 您提供的用于 `entryType` 和 `keyType` 确定类的项类型以及它与每个项关联的键的类型。 由于约束，你必须提供以 `keyType` 实现 <xref:System.IComparable>的类型。  
  
 下面的代码示例创建一个对象，该对象保存 `String` 项，并将 `Integer` 键与每个项关联。 `Integer` 实现 <xref:System.IComparable>，因此满足 `keyType`的约束。  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 `Of` 关键字可用于以下上下文中：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.IComparable>
- [类型列表](../../../visual-basic/language-reference/statements/type-list.md)
- [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
