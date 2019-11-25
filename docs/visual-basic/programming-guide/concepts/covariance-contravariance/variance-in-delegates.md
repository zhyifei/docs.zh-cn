---
title: 委托中的变体
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 11146bc4a60f55fc0373f0b5dfa5d44dcf748a5b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349005"
---
# <a name="variance-in-delegates-visual-basic"></a>Variance in Delegates (Visual Basic)

.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic. 这表明不仅可以将具有匹配签名的方法分配给委托，还可以将返回派生程度较大的派生类型的方法分配给委托（协变），或者如果方法所接受参数的派生类型所具有的派生程度小于委托类型指定的程度（逆变），也可将其分配给委托。 这包括泛型委托和非泛型委托。

例如，思考以下代码，该代码具有两个类和两个委托：泛型和非泛型。

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

创建 `SampleDelegate` 或 `SampleDelegate(Of A, R)` 类型的委托时，可以将以下任一方法分配给这些委托。

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

以下代码示例说明了方法签名与委托类型之间的隐式转换。

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

## <a name="variance-in-generic-type-parameters"></a>泛型类型参数中的变体

In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.

若要启用隐式转换，必须使用 `in` 或 `out` 关键字将委托中的泛型参数显式声明为协变或逆变。

以下代码示例演示了如何创建一个具有协变泛型类型参数的委托。

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

如果仅使用变体支持来匹配方法签名和委托类型，且不使用 `in` 和 `out` 关键字，则可能会发现有时可以使用相同的 lambda 表达式或方法实例化委托，但不能将一个委托分配给另一个委托。

In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`. 可以使用 `out` 关键字标记 泛型参数 `T` 解决此问题。

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>.NET Framework 中具有变体类型参数的泛型委托

.NET Framework 4 在几个现有泛型委托中引入了泛型类型参数的变体支持：

- <xref:System> 命名空间的 `Action` 委托，例如 <xref:System.Action%601> 和 <xref:System.Action%602>

- <xref:System> 命名空间的 `Func` 委托，例如 <xref:System.Func%601> 和 <xref:System.Func%602>

- <xref:System.Predicate%601> 委托

- <xref:System.Comparison%601> 委托

- <xref:System.Converter%602> 委托

For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>声明泛型委托中的变体类型参数

如果泛型委托具有协变或逆变泛型类型参数，则该委托可被称为“变体泛型委托”。

可以使用 `out` 关键字声明泛型委托中的泛型类型参数协变。 协变类型只能用作方法返回类型，而不能用作方法参数的类型。 以下代码示例演示了如何声明协变泛型委托。

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

可以使用 `in` 关键字声明泛型委托中的泛型类型参数逆变。 逆变类型只能用作方法参数的类型，而不能用作方法返回类型。 以下代码示例演示了如何声明逆变泛型委托。

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> `ByRef` parameters in Visual Basic can't be marked as variant.

可以在同一个委托中支持变体和协变，但这只适用于不同类型的参数。 这在下面的示例中显示。

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a>实例化和调用变体泛型委托

可以像实例化和调用固定委托一样，实例化和调用变体委托。 在以下示例中，该委托通过 lambda 表达式进行实例化。

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a>合并变体泛型委托

不应合并变体委托。 <xref:System.Delegate.Combine%2A> 方法不支持变体委托转换，并且要求委托的类型完全相同。 This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>泛型类型参数中用于值和引用类型的变体

泛型类型参数的变体仅支持引用类型。 For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.

以下示例演示了泛型类型参数中的变体不支持值类型。

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Relaxed Delegate Conversion in Visual Basic

Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types. For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate. For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).

## <a name="see-also"></a>请参阅

- [泛型](../../../../standard/generics/index.md)
- [对 Func 和 Action 泛型委托使用变体 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
