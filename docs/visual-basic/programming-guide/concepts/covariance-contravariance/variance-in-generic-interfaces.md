---
title: "泛型接口 (Visual Basic 中) 中的变体 |Microsoft 文档"
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
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
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
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="38d7c-102">泛型接口 (Visual Basic 中) 中的变体</span><span class="sxs-lookup"><span data-stu-id="38d7c-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="38d7c-103">.NET framework 4 中引入了多个现有的泛型接口的变体支持。</span><span class="sxs-lookup"><span data-stu-id="38d7c-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="38d7c-104">变体支持允许实现这些接口的类的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="38d7c-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="38d7c-105">下面的接口是现在为变体︰</span><span class="sxs-lookup"><span data-stu-id="38d7c-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="38d7c-106"><xref:System.Collections.Generic.IEnumerable%601>（T 是协变）</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="38d7c-107"><xref:System.Collections.Generic.IEnumerator%601>（T 是协变）</xref:System.Collections.Generic.IEnumerator%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="38d7c-108"><xref:System.Linq.IQueryable%601>（T 是协变）</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="38d7c-109"><xref:System.Linq.IGrouping%602>(`TKey`和`TElement`都是协变)</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="38d7c-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="38d7c-110"><xref:System.Collections.Generic.IComparer%601>（T 是逆变）</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="38d7c-111"><xref:System.Collections.Generic.IEqualityComparer%601>（T 是逆变）</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="38d7c-112"><xref:System.IComparable%601>（T 是逆变）</xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="38d7c-113">协变允许具有派生程度更大的返回类型相比，通过该接口的泛型类型参数定义的方法。</span><span class="sxs-lookup"><span data-stu-id="38d7c-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="38d7c-114">若要阐释了协变功能，请考虑以下泛型接口︰`IEnumerable(Of Object)`和`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="38d7c-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="38d7c-115">`IEnumerable(Of String)`接口不会继承`IEnumerable(Of Object)`接口。</span><span class="sxs-lookup"><span data-stu-id="38d7c-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="38d7c-116">但是，`String`类型会继承`Object`类型，在某些情况下，可能想要将这些接口的对象分配给彼此。</span><span class="sxs-lookup"><span data-stu-id="38d7c-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="38d7c-117">下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="38d7c-117">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="38d7c-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="38d7c-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="38d7c-119">在.NET framework 的早期版本，此代码会导致编译错误，在 Visual Basic 中的`Option Strict On`。</span><span class="sxs-lookup"><span data-stu-id="38d7c-119">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="38d7c-120">但现在，您可以使用`strings`而不是`objects`，前面的示例中所示，因为<xref:System.Collections.Generic.IEnumerable%601>接口是协变。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-120">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="38d7c-121">逆变允许方法具有比指定的接口的泛型参数的派生程度更小的参数类型。</span><span class="sxs-lookup"><span data-stu-id="38d7c-121">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="38d7c-122">为了说明逆变，假设您已创建`BaseComparer`类来比较的实例`BaseClass`类。</span><span class="sxs-lookup"><span data-stu-id="38d7c-122">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="38d7c-123">`BaseComparer` 类实现 `IEqualityComparer(Of BaseClass)` 接口。</span><span class="sxs-lookup"><span data-stu-id="38d7c-123">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="38d7c-124">因为<xref:System.Collections.Generic.IEqualityComparer%601>接口现在为逆变接口，则可以使用`BaseComparer`比较继承的类的实例`BaseClass`类</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-124">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="38d7c-125">下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="38d7c-125">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="38d7c-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="38d7c-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="38d7c-127">有关更多示例，请参阅[使用泛型集合 (Visual Basic 中) 的接口中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)。</span><span class="sxs-lookup"><span data-stu-id="38d7c-127">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="38d7c-128">仅适用于引用类型才支持变体泛型接口中。</span><span class="sxs-lookup"><span data-stu-id="38d7c-128">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="38d7c-129">值类型不支持差异。</span><span class="sxs-lookup"><span data-stu-id="38d7c-129">Value types do not support variance.</span></span> <span data-ttu-id="38d7c-130">例如，`IEnumerable(Of Integer)`不能隐式转换为`IEnumerable(Of Object)`，这是因为整数表示由值类型。</span><span class="sxs-lookup"><span data-stu-id="38d7c-130">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
<span data-ttu-id="38d7c-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="38d7c-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="38d7c-132">它还是一定要记住，实现变体接口的类仍然是固定的。</span><span class="sxs-lookup"><span data-stu-id="38d7c-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="38d7c-133">例如，尽管<xref:System.Collections.Generic.List%601>实现协变接口<xref:System.Collections.Generic.IEnumerable%601>，你不能隐式转换`List(Of Object)`到`List(Of String)`。</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="38d7c-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="38d7c-134">下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="38d7c-134">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="38d7c-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38d7c-135">See Also</span></span>  
 <span data-ttu-id="38d7c-136">[泛型集合 (Visual Basic 中) 的接口中使用变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="38d7c-136">[Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span></span>  
<span data-ttu-id="38d7c-137"> [创建变体泛型接口 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="38d7c-137"> [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span></span>  
<span data-ttu-id="38d7c-138"> [泛型接口](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span><span class="sxs-lookup"><span data-stu-id="38d7c-138"> [Generic Interfaces](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span></span>  
<span data-ttu-id="38d7c-139"> [委托 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="38d7c-139"> [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span></span>
