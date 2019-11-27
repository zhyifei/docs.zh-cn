---
title: 阴影操作
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 034b5c0ecf3be6e77048fb7318e931801575f07a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345331"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="59fba-102">Visual Basic 中的隐藏</span><span class="sxs-lookup"><span data-stu-id="59fba-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="59fba-103">当两个编程元素共享同一名称时，其中一个元素可以*隐藏或隐藏*另一个。</span><span class="sxs-lookup"><span data-stu-id="59fba-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="59fba-104">在这种情况下，隐藏的元素不可用于引用;相反，当你的代码使用元素名称时，Visual Basic 编译器会将其解析为隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="59fba-105">目的</span><span class="sxs-lookup"><span data-stu-id="59fba-105">Purpose</span></span>  
 <span data-ttu-id="59fba-106">隐藏的主要目的是保护类成员的定义。</span><span class="sxs-lookup"><span data-stu-id="59fba-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="59fba-107">基类可能会发生更改，该更改将创建一个与已定义的元素同名的元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="59fba-108">如果发生这种情况，则 `Shadows` 修饰符强制将通过类的引用解析为你定义的成员，而不是新的基类元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="59fba-109">隐藏类型</span><span class="sxs-lookup"><span data-stu-id="59fba-109">Types of Shadowing</span></span>  
 <span data-ttu-id="59fba-110">元素可通过两种不同的方式隐藏其他元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="59fba-111">可以在包含隐藏元素的区域的子区域内声明隐藏元素，在这种情况下，隐藏是*通过范围*实现的。</span><span class="sxs-lookup"><span data-stu-id="59fba-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="59fba-112">或派生类可以重新定义基类的成员，在这种情况下，将*通过继承*来完成隐藏。</span><span class="sxs-lookup"><span data-stu-id="59fba-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="59fba-113">通过范围隐藏</span><span class="sxs-lookup"><span data-stu-id="59fba-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="59fba-114">同一模块、类或结构中的编程元素可以具有相同的名称，但范围不同。</span><span class="sxs-lookup"><span data-stu-id="59fba-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="59fba-115">如果以这种方式声明了两个元素，而代码引用了它们共享的名称，则范围较窄的元素将隐藏另一个元素（块范围是最窄的）。</span><span class="sxs-lookup"><span data-stu-id="59fba-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="59fba-116">例如，模块可以定义一个名为 `temp`的 `Public` 变量，并且该模块中的一个过程可以声明同样名为 `temp`的局部变量。</span><span class="sxs-lookup"><span data-stu-id="59fba-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="59fba-117">在过程中对 `temp` 的引用将访问本地变量，而从外部对 `temp` 的引用将访问 `Public` 变量。</span><span class="sxs-lookup"><span data-stu-id="59fba-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="59fba-118">在这种情况下，过程变量 `temp` 隐藏模块变量 `temp`。</span><span class="sxs-lookup"><span data-stu-id="59fba-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="59fba-119">下图显示了两个变量，两者都命名 `temp`。</span><span class="sxs-lookup"><span data-stu-id="59fba-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="59fba-120">本地变量 `temp` 在从其自己的过程 `p`内访问成员变量 `temp`。</span><span class="sxs-lookup"><span data-stu-id="59fba-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="59fba-121">但 `MyClass` 关键字会绕过隐藏并访问成员变量。</span><span class="sxs-lookup"><span data-stu-id="59fba-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![显示通过范围隐藏的图形。](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="59fba-123">有关通过范围进行隐藏的示例，请参阅[如何：隐藏与您的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)同名的变量。</span><span class="sxs-lookup"><span data-stu-id="59fba-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="59fba-124">通过继承隐藏</span><span class="sxs-lookup"><span data-stu-id="59fba-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="59fba-125">如果派生类重定义了从基类继承的编程元素，则重定义元素将隐藏原始元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="59fba-126">可以用任何其他类型隐藏任何类型的已声明元素或重载元素集。</span><span class="sxs-lookup"><span data-stu-id="59fba-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="59fba-127">例如，`Integer` 变量可以隐藏 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="59fba-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="59fba-128">如果使用另一个过程来隐藏过程，则可以使用不同的参数列表和不同的返回类型。</span><span class="sxs-lookup"><span data-stu-id="59fba-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="59fba-129">下图显示了一个基类 `b` 和从 `b`继承的派生类 `d`。</span><span class="sxs-lookup"><span data-stu-id="59fba-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="59fba-130">基类定义了一个名为 `proc`的过程，派生类将使用另一个同名的过程来隐藏该过程。</span><span class="sxs-lookup"><span data-stu-id="59fba-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="59fba-131">第一个 `Call` 语句访问派生类中的隐藏 `proc`。</span><span class="sxs-lookup"><span data-stu-id="59fba-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="59fba-132">但 `MyBase` 关键字会绕过隐藏并访问基类中的隐藏过程。</span><span class="sxs-lookup"><span data-stu-id="59fba-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![通过继承进行隐藏示意图](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="59fba-134">有关通过继承进行隐藏的示例，请参阅[如何：隐藏与您的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)同名的变量和[如何：隐藏继承的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="59fba-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="59fba-135">隐藏和访问级别</span><span class="sxs-lookup"><span data-stu-id="59fba-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="59fba-136">不能始终使用派生类从代码访问隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="59fba-137">例如，它可能已 `Private`声明。</span><span class="sxs-lookup"><span data-stu-id="59fba-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="59fba-138">在这种情况下，隐藏会失效，如果没有隐藏，编译器将解析对同一元素的任何引用。</span><span class="sxs-lookup"><span data-stu-id="59fba-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="59fba-139">此元素是可访问的元素，它是从隐藏类向后 derivational 的最少步骤。</span><span class="sxs-lookup"><span data-stu-id="59fba-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="59fba-140">如果隐藏的元素是一个过程，则将其解析为具有相同名称、参数列表和返回类型的最接近的可访问版本。</span><span class="sxs-lookup"><span data-stu-id="59fba-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="59fba-141">下面的示例显示了三个类的继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="59fba-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="59fba-142">每个类都定义一个 `Sub` 过程 `display`，每个派生类都会在其基类中隐藏 `display` 过程。</span><span class="sxs-lookup"><span data-stu-id="59fba-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="59fba-143">在前面的示例中，派生类 `secondClass` 与 `Private` 过程 `display` 阴影。</span><span class="sxs-lookup"><span data-stu-id="59fba-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="59fba-144">当模块 `callDisplay` 在 `secondClass`调用 `display` 时，调用代码在 `secondClass` 外部，因此无法访问私有 `display` 过程。</span><span class="sxs-lookup"><span data-stu-id="59fba-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="59fba-145">隐藏会失效，编译器会将对基类的引用解析 `display` 过程中。</span><span class="sxs-lookup"><span data-stu-id="59fba-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="59fba-146">但是，更进一步的派生类 `thirdClass` 将 `display` 声明为 `Public`，因此 `callDisplay` 中的代码可以访问它。</span><span class="sxs-lookup"><span data-stu-id="59fba-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="59fba-147">隐藏和重写</span><span class="sxs-lookup"><span data-stu-id="59fba-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="59fba-148">不要将隐藏与重写混淆。</span><span class="sxs-lookup"><span data-stu-id="59fba-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="59fba-149">当派生类从基类继承时，同时使用这两种方法，并将一个声明的元素重定义为另一个。</span><span class="sxs-lookup"><span data-stu-id="59fba-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="59fba-150">但两者之间存在重大差异。</span><span class="sxs-lookup"><span data-stu-id="59fba-150">But there are significant differences between the two.</span></span> <span data-ttu-id="59fba-151">有关比较，请参阅[隐藏和重写之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)。</span><span class="sxs-lookup"><span data-stu-id="59fba-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="59fba-152">隐藏和重载</span><span class="sxs-lookup"><span data-stu-id="59fba-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="59fba-153">如果在派生类中隐藏具有多个元素的同一个基类元素，则隐藏元素将成为该元素的重载版本。</span><span class="sxs-lookup"><span data-stu-id="59fba-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="59fba-154">有关更多信息，请参见 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="59fba-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="59fba-155">访问隐藏的元素</span><span class="sxs-lookup"><span data-stu-id="59fba-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="59fba-156">从派生类访问某个元素时，通常通过该派生类的当前实例执行此操作，方法是使用 `Me` 关键字限定元素名称。</span><span class="sxs-lookup"><span data-stu-id="59fba-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="59fba-157">如果派生类隐藏了基类中的元素，则可以通过使用 `MyBase` 关键字来限定它来访问基类元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="59fba-158">有关访问隐藏的元素的示例，请参阅[如何：访问由派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。</span><span class="sxs-lookup"><span data-stu-id="59fba-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="59fba-159">对象变量的声明</span><span class="sxs-lookup"><span data-stu-id="59fba-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="59fba-160">创建对象变量的方式还会影响派生类是访问隐藏元素还是访问隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="59fba-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="59fba-161">下面的示例从派生类创建两个对象，但一个对象声明为基类，另一个对象作为派生类。</span><span class="sxs-lookup"><span data-stu-id="59fba-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="59fba-162">在前面的示例中，变量 `basObj` 声明为基类。</span><span class="sxs-lookup"><span data-stu-id="59fba-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="59fba-163">将 `dervCls` 对象分配给它构成了扩大转换，因此是有效的。</span><span class="sxs-lookup"><span data-stu-id="59fba-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="59fba-164">但是，基类无法访问派生类中的变量 `z` 的隐藏版本，因此编译器会将 `basObj.z` 解析为原始基类值。</span><span class="sxs-lookup"><span data-stu-id="59fba-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fba-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59fba-165">See also</span></span>

- [<span data-ttu-id="59fba-166">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="59fba-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="59fba-167">范围 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59fba-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="59fba-168">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="59fba-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="59fba-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="59fba-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="59fba-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="59fba-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="59fba-171">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="59fba-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="59fba-172">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="59fba-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
