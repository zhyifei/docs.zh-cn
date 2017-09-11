---
title: "泛型集合 (Visual Basic 中) 的接口中使用变体 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="f1c60-102">泛型集合 (Visual Basic 中) 的接口中使用变体</span><span class="sxs-lookup"><span data-stu-id="f1c60-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>
<span data-ttu-id="f1c60-103">协变接口允许其方法以返回更多比在接口中指定的派生的类型。</span><span class="sxs-lookup"><span data-stu-id="f1c60-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="f1c60-104">逆变接口允许其方法来接受较少比指定的那些接口中的派生类型的参数。</span><span class="sxs-lookup"><span data-stu-id="f1c60-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="f1c60-105">在.NET Framework 4 中，多个现有接口变得协变和逆变。</span><span class="sxs-lookup"><span data-stu-id="f1c60-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="f1c60-106">其中包括<xref:System.Collections.Generic.IEnumerable%601>和<xref:System.IComparable%601>。</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f1c60-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="f1c60-107">这样您就可以重用与基类型派生类型的集合的泛型集合进行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="f1c60-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="f1c60-108">.NET Framework 中的变体接口的列表，请参阅[泛型接口 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="f1c60-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="f1c60-109">转换泛型集合</span><span class="sxs-lookup"><span data-stu-id="f1c60-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="f1c60-110">下面的示例阐释了协变支持中的好处<xref:System.Collections.Generic.IEnumerable%601>接口。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f1c60-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f1c60-111">`PrintFullName`方法接受一套`IEnumerable(Of Person)`类型作为参数。</span><span class="sxs-lookup"><span data-stu-id="f1c60-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="f1c60-112">但是，您可以重复使用它的集合`IEnumerable(Of Person)`类型，因为`Employee`继承`Person`。</span><span class="sxs-lookup"><span data-stu-id="f1c60-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>  
  
<span data-ttu-id="f1c60-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f1c60-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="comparing-generic-collections"></a><span data-ttu-id="f1c60-114">比较泛型集合</span><span class="sxs-lookup"><span data-stu-id="f1c60-114">Comparing Generic Collections</span></span>  
 <span data-ttu-id="f1c60-115">下面的示例阐释了逆变中的支持权益<xref:System.Collections.Generic.IComparer%601>接口。</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="f1c60-115">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="f1c60-116">`PersonComparer` 类实现 `IComparer(Of Person)` 接口。</span><span class="sxs-lookup"><span data-stu-id="f1c60-116">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="f1c60-117">但是，您可以重复使用此类来比较的对象的序列`Employee`类型，因为`Employee`继承`Person`。</span><span class="sxs-lookup"><span data-stu-id="f1c60-117">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```vb  
' Simple hierarhcy of classes.  
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
  
## <a name="see-also"></a><span data-ttu-id="f1c60-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c60-118">See Also</span></span>  
 [<span data-ttu-id="f1c60-119">泛型接口 (Visual Basic 中) 中的变体</span><span class="sxs-lookup"><span data-stu-id="f1c60-119">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
