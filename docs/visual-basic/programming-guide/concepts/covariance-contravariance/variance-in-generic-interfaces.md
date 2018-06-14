---
title: 泛型接口 (Visual Basic 中) 中的变体
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: c18f014897ace71e437bd733ff6fcd1d4d8810dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643453"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a>泛型接口 (Visual Basic 中) 中的变体
.NET Framework 4 引入了对多个现有泛型接口的变体支持。 变体支持允许实现这些接口的类进行隐式转换。 下面的接口现在是变体：  
  
-   <xref:System.Collections.Generic.IEnumerable%601>（T 是协变）  
  
-   <xref:System.Collections.Generic.IEnumerator%601>（T 是协变）  
  
-   <xref:System.Linq.IQueryable%601>（T 是协变）  
  
-   <xref:System.Linq.IGrouping%602>（`TKey` 和 `TElement` 都是协变）  
  
-   <xref:System.Collections.Generic.IComparer%601>（T 是逆变）  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601>（T 是逆变）  
  
-   <xref:System.IComparable%601>（T 是逆变）  
  
 协变允许方法具有的返回类型比接口的泛型类型参数定义的返回类型的派生程度更大。 若要演示协变功能，请考虑以下泛型接口：`IEnumerable(Of Object)` 和 `IEnumerable(Of String)`。 `IEnumerable(Of String)` 接口不继承 `IEnumerable(Of Object)` 接口。 但是，`String` 类型会继承 `Object` 类型，在某些情况下，建议为这些接口互相指派彼此的对象。 下面的代码示例对此进行了演示。  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 在.NET framework 的早期版本，此代码会导致编译错误在与 Visual Basic 中的`Option Strict On`。 但现在可使用 `strings` 代替 `objects`，如上例所示，因为 <xref:System.Collections.Generic.IEnumerable%601> 接口是协变接口。  
  
 逆变允许方法具有的实参类型比接口的泛型形参定义的类型的派生程度更小。 若要演示逆变，假设已创建了 `BaseComparer` 类来比较 `BaseClass` 类的实例。 `BaseComparer` 类实现 `IEqualityComparer(Of BaseClass)` 接口。 因为 <xref:System.Collections.Generic.IEqualityComparer%601> 接口现在是逆变接口，因此可使用 `BaseComparer` 比较继承 `BaseClass` 类的类的实例。 下面的代码示例对此进行了演示。  
  
```vb  
' Simple hierarchy of classes.  
Class BaseClass  
End Class  
  
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
' Comparer class.  
Class BaseComparer  
    Implements IEqualityComparer(Of BaseClass)  
  
    Public Function Equals1(ByVal x As BaseClass,  
                            ByVal y As BaseClass) As Boolean _  
                            Implements IEqualityComparer(Of BaseClass).Equals  
        Return (x.Equals(y))  
    End Function  
  
    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _  
        Implements IEqualityComparer(Of BaseClass).GetHashCode  
        Return obj.GetHashCode  
    End Function  
End Class  
Sub Test()  
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer  
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to   
    ' IEqualityComparer(Of DerivedClass).  
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer  
End Sub  
```  
  
 有关更多示例，请参阅[使用泛型集合 (Visual Basic 中) 的接口中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)。  
  
 只有引用类型才支持使用泛型接口中的变体。 值类型不支持变体。 例如，无法将 `IEnumerable(Of Integer)` 隐式转换为 `IEnumerable(Of Object)`，因为整数由值类型表示。  
  
```vb  
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)  
' The following statement generates a compiler error  
' with Option Strict On, because Integer is a value type.  
' Dim objects As IEnumerable(Of Object) = integers  
```  
  
 还需记住，实现变体接口的类仍是固定类。 例如，虽然 <xref:System.Collections.Generic.List%601> 实现协变接口 <xref:System.Collections.Generic.IEnumerable%601>，但不能将 `List(Of Object)` 隐式转换为 `List(Of String)`。 以下代码示例阐释了这一点。  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a>请参阅  
 [在泛型集合的接口中使用变体 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)  
 [创建变体泛型接口 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)  
 [泛型接口](../../../../standard/generics/interfaces.md)  
 [委托中的变体 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
