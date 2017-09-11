---
title: "如何︰ 为 LINQ 查询 (Visual Basic 中) 添加自定义方法 |Microsoft 文档"
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
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
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
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="a5952-102">如何︰ 为 LINQ 查询 (Visual Basic 中) 添加自定义方法</span><span class="sxs-lookup"><span data-stu-id="a5952-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>
<span data-ttu-id="a5952-103">您可以扩展，可以通过添加的扩展方法使用 LINQ 查询方法的一套<xref:System.Collections.Generic.IEnumerable%601>接口。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="a5952-104">例如，除了标准平均值或最大操作数中，可以创建自定义的聚合方法来计算单个值序列中的值。</span><span class="sxs-lookup"><span data-stu-id="a5952-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="a5952-105">此外可以创建一个方法，用作自定义筛选器或特定数据转换为一系列的值并返回新的序列。</span><span class="sxs-lookup"><span data-stu-id="a5952-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="a5952-106">此类方法的示例包括<xref:System.Linq.Enumerable.Distinct%2A>， <xref:System.Linq.Enumerable.Skip%2A>，和<xref:System.Linq.Enumerable.Reverse%2A>。</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="a5952-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>  
  
 <span data-ttu-id="a5952-107">在扩展<xref:System.Collections.Generic.IEnumerable%601>接口，可以将自定义方法应用于任何可枚举集合。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="a5952-108">有关详细信息，请参阅[扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="a5952-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="adding-an-aggregate-method"></a><span data-ttu-id="a5952-109">添加聚合方法</span><span class="sxs-lookup"><span data-stu-id="a5952-109">Adding an Aggregate Method</span></span>  
 <span data-ttu-id="a5952-110">聚合方法计算出单个值从一组值。</span><span class="sxs-lookup"><span data-stu-id="a5952-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="a5952-111">LINQ 提供了几种聚合方法，包括<xref:System.Linq.Enumerable.Average%2A>， <xref:System.Linq.Enumerable.Min%2A>，和<xref:System.Linq.Enumerable.Max%2A>。</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="a5952-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="a5952-112">可以通过添加到扩展方法来创建您自己的聚合方法<xref:System.Collections.Generic.IEnumerable%601>接口。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="a5952-113">下面的代码示例演示如何创建扩展方法调用`Median`来计算的类型的数字序列中的中间值`double`。</span><span class="sxs-lookup"><span data-stu-id="a5952-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 <span data-ttu-id="a5952-114">与调用从其他聚合方法相同的方式，为任何可枚举集合调用此扩展方法<xref:System.Collections.Generic.IEnumerable%601>接口。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5952-115">在 Visual Basic 中，您可以使用方法调用或标准的查询语法`Aggregate`或`Group By`子句。</span><span class="sxs-lookup"><span data-stu-id="a5952-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="a5952-116">有关详细信息，请参阅[Aggregate 子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)和[组 By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a5952-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="a5952-117">下面的代码示例演示如何使用`Median`类型的数组的方法`double`。</span><span class="sxs-lookup"><span data-stu-id="a5952-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>  
  
<span data-ttu-id="a5952-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="a5952-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="a5952-120">重载以接受各种类型的聚合方法</span><span class="sxs-lookup"><span data-stu-id="a5952-120">Overloading an Aggregate Method to Accept Various Types</span></span>  
 <span data-ttu-id="a5952-121">您可以重载聚合方法，以便它接受各种类型的序列。</span><span class="sxs-lookup"><span data-stu-id="a5952-121">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="a5952-122">标准的方法是创建每种类型的重载。</span><span class="sxs-lookup"><span data-stu-id="a5952-122">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="a5952-123">另一种方法是创建一个重载，它将采用泛型类型，并将其转换为特定类型使用委托。</span><span class="sxs-lookup"><span data-stu-id="a5952-123">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="a5952-124">此外可以结合这两种方法。</span><span class="sxs-lookup"><span data-stu-id="a5952-124">You can also combine both approaches.</span></span>  
  
#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="a5952-125">若要创建每种类型的重载</span><span class="sxs-lookup"><span data-stu-id="a5952-125">To create an overload for each type</span></span>  
 <span data-ttu-id="a5952-126">您可以创建您想要支持每种类型的特定重载。</span><span class="sxs-lookup"><span data-stu-id="a5952-126">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="a5952-127">下面的代码示例演示的重载`Median`方法`integer`类型。</span><span class="sxs-lookup"><span data-stu-id="a5952-127">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>  
  
<span data-ttu-id="a5952-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="a5952-129">现在，您可以调用`Median`两个重载`integer`和`double`类型，如下面的代码中所示︰</span><span class="sxs-lookup"><span data-stu-id="a5952-129">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>  
  
<span data-ttu-id="a5952-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="a5952-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="a5952-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="a5952-133">若要创建的泛型重载</span><span class="sxs-lookup"><span data-stu-id="a5952-133">To create a generic overload</span></span>  
 <span data-ttu-id="a5952-134">此外可以创建一个重载，它接受泛型对象的序列。</span><span class="sxs-lookup"><span data-stu-id="a5952-134">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="a5952-135">此重载采用委托作为参数，并使用它来将泛型类型的对象的序列转换为特定类型。</span><span class="sxs-lookup"><span data-stu-id="a5952-135">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>  
  
 <span data-ttu-id="a5952-136">下面的代码演示的重载`Median`采用的方法<xref:System.Func%602>委托作为参数。</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="a5952-136">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="a5952-137">此委托采用泛型类型 T 的对象，并返回类型的对象`double`。</span><span class="sxs-lookup"><span data-stu-id="a5952-137">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 <span data-ttu-id="a5952-138">现在，您可以调用`Median`为一系列的任何类型的对象的方法。</span><span class="sxs-lookup"><span data-stu-id="a5952-138">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="a5952-139">如果类型不具有其自己的方法重载，您必须将传递委托参数。</span><span class="sxs-lookup"><span data-stu-id="a5952-139">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="a5952-140">在 Visual Basic 中，您可以实现此目的使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a5952-140">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="a5952-141">此外，如果您使用`Aggregate`或`Group By`子句而不是方法调用中的，您可以传递任何值或处于范围内，此子句的表达式。</span><span class="sxs-lookup"><span data-stu-id="a5952-141">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>  
  
 <span data-ttu-id="a5952-142">下面的代码示例演示如何调用`Median`为整数的数组和一个字符串数组的方法。</span><span class="sxs-lookup"><span data-stu-id="a5952-142">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="a5952-143">对于字符串，字符串长度的数组中的中值被计算。</span><span class="sxs-lookup"><span data-stu-id="a5952-143">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="a5952-144">该示例演示如何将传递<xref:System.Func%602>委托到的参数`Median`每个用例的方法。</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="a5952-144">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>  
  
<span data-ttu-id="a5952-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="a5952-146">添加返回的集合的方法</span><span class="sxs-lookup"><span data-stu-id="a5952-146">Adding a Method That Returns a Collection</span></span>  
 <span data-ttu-id="a5952-147">您可以扩展<xref:System.Collections.Generic.IEnumerable%601>与返回一系列值的自定义查询方法的接口。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-147">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="a5952-148">在这种情况下，该方法必须返回类型<xref:System.Collections.Generic.IEnumerable%601>。</xref:System.Collections.Generic.IEnumerable%601>的集合</span><span class="sxs-lookup"><span data-stu-id="a5952-148">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="a5952-149">这种方法可以用于将筛选器或数据转换应用于一系列值。</span><span class="sxs-lookup"><span data-stu-id="a5952-149">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>  
  
 <span data-ttu-id="a5952-150">下面的示例演示如何创建名为的扩展方法`AlternateElements`返回每个其他元素在集合中，从第一个元素开始。</span><span class="sxs-lookup"><span data-stu-id="a5952-150">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>  
  
<span data-ttu-id="a5952-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a5952-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="a5952-152">可以为任何可枚举集合调用此扩展方法，就像将调用其他方法从<xref:System.Collections.Generic.IEnumerable%601>接口，如下面的代码中所示︰</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-152">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5952-153">请参见</span><span class="sxs-lookup"><span data-stu-id="a5952-153">See Also</span></span>  
 <span data-ttu-id="a5952-154"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a5952-154"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="a5952-155"> [扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="a5952-155"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
