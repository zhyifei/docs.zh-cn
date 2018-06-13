---
title: 方法的&#39;System.Nullable (Of T)&#39;不能用作的操作数&#39;AddressOf&#39;运算符
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 3a3e4fc033f47fb6a72076dff79f1eece8d01a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594115"
---
# <a name="methods-of-39systemnullableof-t39-cannot-be-used-as-operands-of-the-39addressof39-operator"></a>方法的&#39;System.Nullable (Of T)&#39;不能用作的操作数&#39;AddressOf&#39;运算符
语句使用`AddressOf`运算符的操作数，表示的过程与<xref:System.Nullable%601>结构。  
  
 **错误 ID:** BC32126  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   中的过程名称替换`AddressOf`子句的操作数不是的成员， <xref:System.Nullable%601>。  
  
-   编写包装的方法的类<xref:System.Nullable%601>你想要使用。 在下面的示例中，`NullableWrapper`类定义一个名为的新方法`GetValueOrDefault`。 因为此新方法不是成员的<xref:System.Nullable%601>，它可以应用于`nullInstance`，可以为 null 的类型，以形成的自变量的实例`AddressOf`。  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Nullable%601>  
 [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
