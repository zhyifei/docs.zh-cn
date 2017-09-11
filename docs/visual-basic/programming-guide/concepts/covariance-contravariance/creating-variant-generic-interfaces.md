---
title: "创建变体泛型接口 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2cbf0a204a5a3af45f55a14c011518c7021f5b4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="efc86-102">创建变体泛型接口 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efc86-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="efc86-103">您可以声明为协变的接口中的泛型类型参数或逆变。</span><span class="sxs-lookup"><span data-stu-id="efc86-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="efc86-104">*协变*允许接口方法更派生了比定义的泛型类型参数的返回类型。</span><span class="sxs-lookup"><span data-stu-id="efc86-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="efc86-105">*逆变*允许接口方法具有比指定的泛型参数的派生程度更小的参数类型。</span><span class="sxs-lookup"><span data-stu-id="efc86-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="efc86-106">泛型接口具有协变或逆变的泛型类型参数称为*变体*。</span><span class="sxs-lookup"><span data-stu-id="efc86-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc86-107">.NET framework 4 中引入了多个现有的泛型接口的变体支持。</span><span class="sxs-lookup"><span data-stu-id="efc86-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="efc86-108">.NET Framework 中的变体接口的列表，请参阅[泛型接口 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="efc86-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="efc86-109">声明的变体泛型接口</span><span class="sxs-lookup"><span data-stu-id="efc86-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="efc86-110">你可以使用声明变体泛型接口`in`和`out`对于泛型类型参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="efc86-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="efc86-111"> `ByRef`在 Visual Basic 中的参数不能为 variant 类型的值。</span><span class="sxs-lookup"><span data-stu-id="efc86-111"> `ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="efc86-112">值类型也不支持差异。</span><span class="sxs-lookup"><span data-stu-id="efc86-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="efc86-113">可以将泛型类型参数协变声明使用`out`关键字。</span><span class="sxs-lookup"><span data-stu-id="efc86-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="efc86-114">协变类型必须满足以下条件︰</span><span class="sxs-lookup"><span data-stu-id="efc86-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="efc86-115">类型是只用作接口方法的返回类型，不用作方法参数的类型。</span><span class="sxs-lookup"><span data-stu-id="efc86-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="efc86-116">在下面的示例中，在其中阐释了这类型`R`声明为协变。</span><span class="sxs-lookup"><span data-stu-id="efc86-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="efc86-117">此规则有一个例外。</span><span class="sxs-lookup"><span data-stu-id="efc86-117">There is one exception to this rule.</span></span> <span data-ttu-id="efc86-118">如果您具有作为方法参数的逆变泛型委托，可以为委托作为泛型类型参数使用类型。</span><span class="sxs-lookup"><span data-stu-id="efc86-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="efc86-119">阐释了这一点由类型`R`在下面的示例。</span><span class="sxs-lookup"><span data-stu-id="efc86-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="efc86-120">有关详细信息，请参阅[委托 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)和[对 Func 和 Action 泛型委托 (Visual Basic 中) 的使用方差](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)。</span><span class="sxs-lookup"><span data-stu-id="efc86-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="efc86-121">类型不用作接口方法的泛型约束。</span><span class="sxs-lookup"><span data-stu-id="efc86-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="efc86-122">下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="efc86-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="efc86-123">你可以使用声明为泛型类型参数逆变`in`关键字。</span><span class="sxs-lookup"><span data-stu-id="efc86-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="efc86-124">可以使用逆变类型，只能用作方法参数的类型，不能用作接口方法的返回类型。</span><span class="sxs-lookup"><span data-stu-id="efc86-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="efc86-125">逆变类型还可用于泛型约束。</span><span class="sxs-lookup"><span data-stu-id="efc86-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="efc86-126">下面的代码演示如何声明逆变接口和泛型约束用于其方法之一。</span><span class="sxs-lookup"><span data-stu-id="efc86-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="efc86-127">它还有可能以中相同的接口，但对于不同的类型参数支持协变和逆变，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="efc86-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="efc86-128">在 Visual Basic 中不能声明变体接口中的事件，而不指定委托类型。</span><span class="sxs-lookup"><span data-stu-id="efc86-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="efc86-129">此外，不能包含嵌套变体接口，类、 枚举或结构，但它可以有嵌套接口。</span><span class="sxs-lookup"><span data-stu-id="efc86-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="efc86-130">下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="efc86-130">This is illustrated in the following code.</span></span>  
  
```vb  
Interface ICovariant(Of Out R)  
    ' The following statement generates a compiler error.  
    ' Event SampleEvent()  
    ' The following statement specifies the delegate type and   
    ' does not generate an error.  
    Event AnotherEvent As EventHandler  
  
    ' The following statements generate compiler errors,  
    ' because a variant interface cannot have  
    ' nested enums, classes, or structures.  
  
    'Enum SampleEnum : test : End Enum  
    'Class SampleClass : End Class  
    'Structure SampleStructure : Dim value As Integer : End Structure  
  
    ' Variant interfaces can have nested interfaces.  
    Interface INested : End Interface  
End Interface  
```  
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="efc86-131">实现的变体泛型接口</span><span class="sxs-lookup"><span data-stu-id="efc86-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="efc86-132">通过使用相同的语法，用于固定接口，可以在类中实现变体泛型接口。</span><span class="sxs-lookup"><span data-stu-id="efc86-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="efc86-133">下面的代码示例演示如何实现泛型类中的协变的接口。</span><span class="sxs-lookup"><span data-stu-id="efc86-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
```vb  
Interface ICovariant(Of Out R)  
    Function GetSomething() As R  
End Interface  
  
Class SampleImplementation(Of R)  
    Implements ICovariant(Of R)  
    Public Function GetSomething() As R _  
    Implements ICovariant(Of R).GetSomething  
        ' Some code.  
    End Function  
End Class  
```  
  
 <span data-ttu-id="efc86-134">实现变体接口的类是不变。</span><span class="sxs-lookup"><span data-stu-id="efc86-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="efc86-135">例如，考虑下面的代码。</span><span class="sxs-lookup"><span data-stu-id="efc86-135">For example, consider the following code.</span></span>  
  
```vb  
 The interface is covariant.  
Dim ibutton As ICovariant(Of Button) =  
    New SampleImplementation(Of Button)  
Dim iobj As ICovariant(Of Object) = ibutton  
  
' The class is invariant.  
Dim button As SampleImplementation(Of Button) =  
    New SampleImplementation(Of Button)  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim obj As SampleImplementation(Of Object) = button  
```  
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="efc86-136">扩展的变体泛型接口</span><span class="sxs-lookup"><span data-stu-id="efc86-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="efc86-137">在扩展变体泛型接口时，您必须使用`in`和`out`关键字来显式指定派生的接口是否支持变体。</span><span class="sxs-lookup"><span data-stu-id="efc86-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="efc86-138">编译器无法推断从正在扩展的接口的方差。</span><span class="sxs-lookup"><span data-stu-id="efc86-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="efc86-139">例如，考虑下面的接口。</span><span class="sxs-lookup"><span data-stu-id="efc86-139">For example, consider the following interfaces.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T)  
End Interface  
  
Interface IExtCovariant(Of Out T)  
    Inherits ICovariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="efc86-140">在`Invariant(Of T)`接口的泛型类型参数`T`固定不变，而在`IExtCovariant (Of Out T)`该类型参数是协变的虽然这两个界面扩展相同的接口。</span><span class="sxs-lookup"><span data-stu-id="efc86-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="efc86-141">相同的规则应用于逆变泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="efc86-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="efc86-142">您可以创建可同时扩展接口的泛型类型参数的其中一个接口`T`是协变和其中如果处于扩展是逆变的接口的接口的泛型类型参数`T`是固定不变。</span><span class="sxs-lookup"><span data-stu-id="efc86-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="efc86-143">下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="efc86-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="efc86-144">但是，如果泛型类型参数`T`是声明为协变在一个界面，您不能将其声明逆变中扩展接口，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="efc86-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="efc86-145">下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="efc86-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="efc86-146">避免不明确性</span><span class="sxs-lookup"><span data-stu-id="efc86-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="efc86-147">当您实现变体泛型接口时，方差有时可能导致不明确。</span><span class="sxs-lookup"><span data-stu-id="efc86-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="efc86-148">应避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="efc86-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="efc86-149">例如，如果在一个类显式实现相同的变体泛型接口，使用不同的泛型类型参数，它可以创建二义性。</span><span class="sxs-lookup"><span data-stu-id="efc86-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="efc86-150">在这种情况下，编译器不会产生一个错误，但未指定将在运行时选择的接口的实现。</span><span class="sxs-lookup"><span data-stu-id="efc86-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="efc86-151">这可能导致您的代码中出现细微错误。</span><span class="sxs-lookup"><span data-stu-id="efc86-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="efc86-152">请考虑下面的代码示例。</span><span class="sxs-lookup"><span data-stu-id="efc86-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc86-153">与`Option Strict Off`，Visual Basic 会生成编译器警告，当不明确的接口的实现。</span><span class="sxs-lookup"><span data-stu-id="efc86-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="efc86-154">与`Option Strict On`，Visual Basic 生成一个编译器错误。</span><span class="sxs-lookup"><span data-stu-id="efc86-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
```vb  
' Simple class hierarchy.  
Class Animal  
End Class  
  
Class Cat  
    Inherits Animal  
End Class  
  
Class Dog  
    Inherits Animal  
End Class  
  
' This class introduces ambiguity  
' because IEnumerable(Of Out T) is covariant.  
Class Pets  
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)  
  
    Public Function GetEnumerator() As IEnumerator(Of Cat) _  
        Implements IEnumerable(Of Cat).GetEnumerator  
        Console.WriteLine("Cat")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator(Of Dog) _  
        Implements IEnumerable(Of Dog).GetEnumerator  
        Console.WriteLine("Dog")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator2() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
        ' Some code.  
    End Function  
End Class  
  
Sub Main()  
    Dim pets As IEnumerable(Of Animal) = New Pets()  
    pets.GetEnumerator()  
End Sub  
```  
  
 <span data-ttu-id="efc86-155">在此示例中，它是未指定如何`pets.GetEnumerator`方法选择之间`Cat`和`Dog`。</span><span class="sxs-lookup"><span data-stu-id="efc86-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="efc86-156">在代码中，这可能导致问题。</span><span class="sxs-lookup"><span data-stu-id="efc86-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc86-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efc86-157">See Also</span></span>  
 <span data-ttu-id="efc86-158">[泛型接口 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="efc86-158">[Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
<span data-ttu-id="efc86-159"> [对 Func 和 Action 泛型委托 (Visual Basic 中) 中使用变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="efc86-159"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
