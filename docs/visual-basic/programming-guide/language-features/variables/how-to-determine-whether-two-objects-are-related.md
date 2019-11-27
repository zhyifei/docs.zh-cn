---
title: 如何：确定两个对象是否相关
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348632"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>如何：确定两个对象是否相关 (Visual Basic)

您可以比较两个对象，以确定从中创建它们的类之间的关系（如果有）。 如果指定的类从当前类继承，或者当前类型是指定类支持的接口，则 <xref:System.Type?displayProperty=nameWithType> 类的 <xref:System.Type.IsInstanceOfType%2A> 方法返回 `True`。

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>确定一个对象是否继承自另一个对象的类或接口

1. 在您认为可能是基类型的对象上，调用 <xref:System.Object.GetType%2A> 方法。

2. 在 <xref:System.Object.GetType%2A>返回的 <xref:System.Type?displayProperty=nameWithType> 对象上，调用 <xref:System.Type.IsInstanceOfType%2A> 方法。

3. 在 <xref:System.Type.IsInstanceOfType%2A>的参数列表中，指定你认为可能是派生类型的对象。

    如果 `True` 参数类型从 <xref:System.Type?displayProperty=nameWithType> 对象类型继承，则 <xref:System.Type.IsInstanceOfType%2A> 返回。

## <a name="example"></a>示例
 下面的示例确定一个对象是否表示一个派生自另一个对象的类的类。

```vb
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

请注意，在调用 <xref:System.Type.IsInstanceOfType%2A>时，两个对象变量的意外位置。 假定的基类型用于生成 <xref:System.Type?displayProperty=nameWithType> 类，假设的派生类型作为参数传递给 <xref:System.Type.IsInstanceOfType%2A> 方法。

## <a name="see-also"></a>另请参阅

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [如何：确定两个对象是否相同](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
