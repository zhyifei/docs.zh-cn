---
title: 在泛型集合 (Visual Basic 中) 的接口中使用变体
ms.date: 07/20/2015
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
ms.openlocfilehash: 3c7cde2baf6d8b163c6765b87d6bebef803eb6ee
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356697"
---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="4ceb6-102">在泛型集合 (Visual Basic 中) 的接口中使用变体</span><span class="sxs-lookup"><span data-stu-id="4ceb6-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>

<span data-ttu-id="4ceb6-103">协变接口允许其方法返回的派生类型多于接口中指定的派生类型。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="4ceb6-104">逆变接口允许其方法接受派生类型少于接口中指定的类型的参数。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>

<span data-ttu-id="4ceb6-105">在.NET Framework 4 中，多个现有接口已变为协变和逆变接口。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="4ceb6-106">包括 <xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.IComparable%601>。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="4ceb6-107">这使你可将对基类型的泛型集合进行操作的那些方法重用于派生类型的集合。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>

<span data-ttu-id="4ceb6-108">.NET Framework 中的变体接口的列表，请参阅[泛型接口 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>

## <a name="converting-generic-collections"></a><span data-ttu-id="4ceb6-109">转换泛型集合</span><span class="sxs-lookup"><span data-stu-id="4ceb6-109">Converting Generic Collections</span></span>

<span data-ttu-id="4ceb6-110">下例阐释了 <xref:System.Collections.Generic.IEnumerable%601> 接口中的协变支持的益处。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="4ceb6-111">`PrintFullName` 方法接受 `IEnumerable(Of Person)` 类型的集合作为参数。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="4ceb6-112">但可将该方法重用于 `IEnumerable(Of Person)` 类型的集合，因为 `Employee` 继承 `Person`。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class

' The method has a parameter of the IEnumerable(Of Person) type.
Public Sub PrintFullName(ByVal persons As IEnumerable(Of Person))
    For Each person As Person In persons
        Console.WriteLine(
            "Name: " & person.FirstName & " " & person.LastName)
    Next
End Sub

Sub Main()
    Dim employees As IEnumerable(Of Employee) = New List(Of Employee)

    ' You can pass IEnumerable(Of Employee),
    ' although the method expects IEnumerable(Of Person).

    PrintFullName(employees)

End Sub
```

## <a name="comparing-generic-collections"></a><span data-ttu-id="4ceb6-113">比较泛型集合</span><span class="sxs-lookup"><span data-stu-id="4ceb6-113">Comparing Generic Collections</span></span>

<span data-ttu-id="4ceb6-114">下例阐释了 <xref:System.Collections.Generic.IComparer%601> 接口中的逆变支持的益处。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="4ceb6-115">`PersonComparer` 类实现 `IComparer(Of Person)` 接口。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-115">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="4ceb6-116">但可以重用此类来比较 `Employee` 类型的对象序列，因为 `Employee` 继承 `Person`。</span><span class="sxs-lookup"><span data-stu-id="4ceb6-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>

```vb
' Simple hierarchy of classes.
Public Class Person
    Public Property FirstName As String
    Public Property LastName As String
End Class

Public Class Employee
    Inherits Person
End Class
' The custom comparer for the Person type
' with standard implementations of Equals()
' and GetHashCode() methods.
Class PersonComparer
    Implements IEqualityComparer(Of Person)

    Public Function Equals1(
        ByVal x As Person,
        ByVal y As Person) As Boolean _
        Implements IEqualityComparer(Of Person).Equals

        If x Is y Then Return True
        If x Is Nothing OrElse y Is Nothing Then Return False
        Return (x.FirstName = y.FirstName) AndAlso
            (x.LastName = y.LastName)
    End Function
    Public Function GetHashCode1(
        ByVal person As Person) As Integer _
        Implements IEqualityComparer(Of Person).GetHashCode

        If person Is Nothing Then Return 0
        Dim hashFirstName =
            If(person.FirstName Is Nothing,
            0, person.FirstName.GetHashCode())
        Dim hashLastName = person.LastName.GetHashCode()
        Return hashFirstName Xor hashLastName
    End Function
End Class

Sub Main()
    Dim employees = New List(Of Employee) From {
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}
    }

    ' You can pass PersonComparer,
    ' which implements IEqualityComparer(Of Person),
    ' although the method expects IEqualityComparer(Of Employee)

    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())

    For Each employee In noduplicates
        Console.WriteLine(employee.FirstName & " " & employee.LastName)
    Next
End Sub
```

## <a name="see-also"></a><span data-ttu-id="4ceb6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ceb6-117">See also</span></span>

- [<span data-ttu-id="4ceb6-118">泛型接口中的变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ceb6-118">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
