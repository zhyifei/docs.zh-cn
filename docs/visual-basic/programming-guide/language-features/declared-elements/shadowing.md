---
title: "Visual Basic 中的隐藏 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- inheritance, shadowing
- overriding, and shadowing
- shadowing
- duplicate names
- shadowing, by inheritance
- declared elements, referencing
- shadowing, by scope
- declared elements, hiding
- naming conflicts, shadowing
- declared elements, shadowing
- shadowing, and overriding
- scope, shadowing
- Shadows keyword, about
- objects [Visual Basic], names
- names, shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6f6ef1512958b1ed67b27ea79492c85d94bd7cac
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="46c58-102">Visual Basic 中的隐藏</span><span class="sxs-lookup"><span data-stu-id="46c58-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="46c58-103">当两个编程元素共享相同的名称时，可以隐藏其中之一，或*阴影*，另一个。</span><span class="sxs-lookup"><span data-stu-id="46c58-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="46c58-104">在这种情况下，隐藏的元素不是供用户参考;相反，当您的代码使用元素名称、[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将其解析为隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="46c58-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="46c58-105">用途</span><span class="sxs-lookup"><span data-stu-id="46c58-105">Purpose</span></span>  
 <span data-ttu-id="46c58-106">隐藏的主要目的是保护类成员的定义。</span><span class="sxs-lookup"><span data-stu-id="46c58-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="46c58-107">基类可能会经历创建具有作为一个已定义的相同名称的元素的更改。</span><span class="sxs-lookup"><span data-stu-id="46c58-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="46c58-108">如果发生这种情况，`Shadows`通过您的类将解析为该成员的修饰符强制引用您定义，而不是到新的基类元素。</span><span class="sxs-lookup"><span data-stu-id="46c58-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="46c58-109">隐藏类型</span><span class="sxs-lookup"><span data-stu-id="46c58-109">Types of Shadowing</span></span>  
 <span data-ttu-id="46c58-110">元素可以在两种不同方式隐藏另一个元素。</span><span class="sxs-lookup"><span data-stu-id="46c58-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="46c58-111">隐藏的元素可以声明包含隐藏的元素中这, 种情况下隐藏来实现的区域的子区域内*通过范围*。</span><span class="sxs-lookup"><span data-stu-id="46c58-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="46c58-112">派生类可以定义一个基类，这种情况下隐藏来完成的成员或者*通过继承*。</span><span class="sxs-lookup"><span data-stu-id="46c58-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="46c58-113">通过范围进行隐藏</span><span class="sxs-lookup"><span data-stu-id="46c58-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="46c58-114">很可能相同的模块、 类或结构为具有相同名称但不同的作用域中的编程元素。</span><span class="sxs-lookup"><span data-stu-id="46c58-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="46c58-115">范围较窄的元素后，在这种方式中声明两个元素的代码引用它们共享的名称，隐藏的其他元素 （块范围是最小）。</span><span class="sxs-lookup"><span data-stu-id="46c58-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="46c58-116">例如，可以定义一个模块`Public`变量名为`temp`，而该模块内的一个过程可以声明也名为的本地变量`temp`。</span><span class="sxs-lookup"><span data-stu-id="46c58-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="46c58-117">对引用`temp`从过程来访问局部变量，而对引用`temp`从外部过程访问`Public`变量。</span><span class="sxs-lookup"><span data-stu-id="46c58-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="46c58-118">在此情况下，过程变量`temp`隐藏模块变量`temp`。</span><span class="sxs-lookup"><span data-stu-id="46c58-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="46c58-119">下图显示了两个变量，名为`temp`。</span><span class="sxs-lookup"><span data-stu-id="46c58-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="46c58-120">本地变量`temp`隐藏了成员变量`temp`时从其自己的程序内访问`p`。</span><span class="sxs-lookup"><span data-stu-id="46c58-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="46c58-121">但是，`MyClass`关键字绕开隐藏并访问的成员变量。</span><span class="sxs-lookup"><span data-stu-id="46c58-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 <span data-ttu-id="46c58-122">![通过范围进行隐藏示意图](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span><span class="sxs-lookup"><span data-stu-id="46c58-122">![Graphic diagram of shadowing through scope](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span></span>  
<span data-ttu-id="46c58-123">通过范围进行隐藏</span><span class="sxs-lookup"><span data-stu-id="46c58-123">Shadowing through scope</span></span>  
  
 <span data-ttu-id="46c58-124">通过范围进行隐藏的示例，请参阅[如何︰ 隐藏与您的变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="46c58-124">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="46c58-125">通过继承进行隐藏</span><span class="sxs-lookup"><span data-stu-id="46c58-125">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="46c58-126">如果派生的类重定义继承自基类的类的编程元素，重新定义的元素将隐藏原始元素。</span><span class="sxs-lookup"><span data-stu-id="46c58-126">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="46c58-127">与任何其他类型都可隐藏任何类型的已声明的元素或重载元素集。</span><span class="sxs-lookup"><span data-stu-id="46c58-127">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="46c58-128">例如，`Integer`变量可以隐藏`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="46c58-128">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="46c58-129">如果隐藏与另一个过程的过程，您可以使用不同的参数列表和不同的返回类型。</span><span class="sxs-lookup"><span data-stu-id="46c58-129">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="46c58-130">下图显示了一个基类`b`和派生的类`d`，该类继承自`b`。</span><span class="sxs-lookup"><span data-stu-id="46c58-130">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="46c58-131">该基类定义一个名为过程`proc`，然后用相同名称的另一个过程的派生的类隐藏它。</span><span class="sxs-lookup"><span data-stu-id="46c58-131">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="46c58-132">第一个`Call`语句访问该隐藏`proc`在派生类中。</span><span class="sxs-lookup"><span data-stu-id="46c58-132">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="46c58-133">但是，`MyBase`关键字绕开隐藏并访问基类中隐藏的过程。</span><span class="sxs-lookup"><span data-stu-id="46c58-133">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 <span data-ttu-id="46c58-134">![通过继承进行隐藏示意图](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span><span class="sxs-lookup"><span data-stu-id="46c58-134">![Graphic diagram of shadowing through inheritance](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span></span>  
<span data-ttu-id="46c58-135">通过继承进行隐藏</span><span class="sxs-lookup"><span data-stu-id="46c58-135">Shadowing through inheritance</span></span>  
  
 <span data-ttu-id="46c58-136">通过继承隐藏的示例，请参阅[如何︰ 隐藏与您的变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)和[如何︰ 隐藏继承变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="46c58-136">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="46c58-137">隐藏和访问级别</span><span class="sxs-lookup"><span data-stu-id="46c58-137">Shadowing and Access Level</span></span>  
 <span data-ttu-id="46c58-138">隐藏元素并不总是可以从使用派生的类的代码访问。</span><span class="sxs-lookup"><span data-stu-id="46c58-138">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="46c58-139">例如，可能会声明`Private`。</span><span class="sxs-lookup"><span data-stu-id="46c58-139">For example, it might be declared `Private`.</span></span> <span data-ttu-id="46c58-140">在这种情况下，隐藏的比较是失效，编译器将任何引用的同一个元素，它必须解析如果没有过没有隐藏。</span><span class="sxs-lookup"><span data-stu-id="46c58-140">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="46c58-141">此元素是可访问的元素最少派生自隐藏类向后步骤。</span><span class="sxs-lookup"><span data-stu-id="46c58-141">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="46c58-142">如果被隐藏的元素是一个过程，分辨率为最接近的可访问版本具有相同名称参数列表中，并返回类型。</span><span class="sxs-lookup"><span data-stu-id="46c58-142">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="46c58-143">下面的示例演示三个类的继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="46c58-143">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="46c58-144">每个类定义`Sub`过程`display`，并且每个派生类都隐藏`display`其基类中的过程。</span><span class="sxs-lookup"><span data-stu-id="46c58-144">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="46c58-145">在前面的示例中，派生类`secondClass`阴影`display`与`Private`过程。</span><span class="sxs-lookup"><span data-stu-id="46c58-145">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="46c58-146">当模块`callDisplay`调用`display`中`secondClass`，调用代码之外，则`secondClass`，因此不能访问私有`display`过程。</span><span class="sxs-lookup"><span data-stu-id="46c58-146">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="46c58-147">隐藏失败，并且编译器将对基类的引用解析`display`过程。</span><span class="sxs-lookup"><span data-stu-id="46c58-147">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="46c58-148">但是，进一步派生类`thirdClass`声明`display`作为`Public`，因此中的代码`callDisplay`可以访问它。</span><span class="sxs-lookup"><span data-stu-id="46c58-148">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="46c58-149">隐藏和重写</span><span class="sxs-lookup"><span data-stu-id="46c58-149">Shadowing and Overriding</span></span>  
 <span data-ttu-id="46c58-150">不要混淆隐藏和重写。</span><span class="sxs-lookup"><span data-stu-id="46c58-150">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="46c58-151">在派生的类继承自基类，并同时重新定义与另一个已声明的元素时，将使用它们。</span><span class="sxs-lookup"><span data-stu-id="46c58-151">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="46c58-152">但是，这两者之间的重大差异。</span><span class="sxs-lookup"><span data-stu-id="46c58-152">But there are significant differences between the two.</span></span> <span data-ttu-id="46c58-153">有关比较，请参阅[之间隐藏之间的差异和覆盖](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)。</span><span class="sxs-lookup"><span data-stu-id="46c58-153">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="46c58-154">隐藏和重载</span><span class="sxs-lookup"><span data-stu-id="46c58-154">Shadowing and Overloading</span></span>  
 <span data-ttu-id="46c58-155">如果在派生类中隐藏了多个元素具有的相同基类元素，隐藏的元素将变为该元素的重载的版本。</span><span class="sxs-lookup"><span data-stu-id="46c58-155">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="46c58-156">有关详细信息，请参阅[过程重载](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="46c58-156">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="46c58-157">访问隐藏的元素</span><span class="sxs-lookup"><span data-stu-id="46c58-157">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="46c58-158">当从派生类访问一个元素时，您通常要通过该派生类的当前实例的限定元素名与`Me`关键字。</span><span class="sxs-lookup"><span data-stu-id="46c58-158">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="46c58-159">如果在派生的类隐藏基类中的元素，则可以通过限定其与访问基类元素`MyBase`关键字。</span><span class="sxs-lookup"><span data-stu-id="46c58-159">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="46c58-160">访问隐藏的元素的示例，请参阅[如何︰ 访问被派生类变量隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。</span><span class="sxs-lookup"><span data-stu-id="46c58-160">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="46c58-161">对象变量的声明</span><span class="sxs-lookup"><span data-stu-id="46c58-161">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="46c58-162">如何创建对象变量也会影响是否派生的类是访问隐藏的元素还是被隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="46c58-162">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="46c58-163">下面的示例创建两个对象从派生类中，但一个对象声明为类的基类，另一个用作派生的类。</span><span class="sxs-lookup"><span data-stu-id="46c58-163">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="46c58-164">在前面的示例中，该变量`basObj`被声明为类的基类。</span><span class="sxs-lookup"><span data-stu-id="46c58-164">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="46c58-165">分配`dervCls`对象传递给它构成了扩大转换，因此有效。</span><span class="sxs-lookup"><span data-stu-id="46c58-165">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="46c58-166">但是，基类不能访问该变量的隐藏版本`z`在派生类中，因此编译器会将解析`basObj.z`为基类初始值。</span><span class="sxs-lookup"><span data-stu-id="46c58-166">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c58-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46c58-167">See Also</span></span>  
 <span data-ttu-id="46c58-168">[对已声明的元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="46c58-168">[References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="46c58-169"> [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="46c58-169"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="46c58-170"> [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="46c58-170"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="46c58-171"> [阴影](../../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="46c58-171"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="46c58-172"> [重写](../../../../visual-basic/language-reference/modifiers/overrides.md) </span><span class="sxs-lookup"><span data-stu-id="46c58-172"> [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md) </span></span>  
<span data-ttu-id="46c58-173"> [Me、 My、 MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md) </span><span class="sxs-lookup"><span data-stu-id="46c58-173"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md) </span></span>  
<span data-ttu-id="46c58-174"> [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)</span><span class="sxs-lookup"><span data-stu-id="46c58-174"> [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)</span></span>
