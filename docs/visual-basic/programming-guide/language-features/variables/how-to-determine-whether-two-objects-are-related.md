---
title: 如何：确定两个对象是否相关 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2041f89ffd954e479046eb85c6dd82de1f8793ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>如何：确定两个对象是否相关 (Visual Basic)
你可以比较两个对象以确定关系，如果有，从中创建的类之间。 <xref:System.Type.IsInstanceOfType%2A>方法<xref:System.Type?displayProperty=nameWithType>类返回`True`如果指定的类继承自当前类中，或如果当前类型是接口，支持由指定的类。  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>若要确定是否一个对象继承自另一个对象的类或接口  
  
1.  在你认为的对象可能是基类型，则调用<xref:System.Object.GetType%2A>方法。  
  
2.  上<xref:System.Type?displayProperty=nameWithType>返回对象<xref:System.Object.GetType%2A>，调用<xref:System.Type.IsInstanceOfType%2A>方法。  
  
3.  中的自变量列表<xref:System.Type.IsInstanceOfType%2A>，指定的派生类型可能是你认为的对象。  
  
     <xref:System.Type.IsInstanceOfType%2A> 返回`True`如果其自变量类型都继承自<xref:System.Type?displayProperty=nameWithType>对象类型。  
  
## <a name="example"></a>示例  
 下面的示例确定一个对象是否表示从另一个对象的类派生的类。  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 请注意对的调用中的两个对象变量的意外的位置<xref:System.Type.IsInstanceOfType%2A>。 假定的基类型用于生成<xref:System.Type?displayProperty=nameWithType>类，并且假定的派生的类型的自变量作为传递<xref:System.Type.IsInstanceOfType%2A>方法。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [如何：确定两个对象是否相同](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
