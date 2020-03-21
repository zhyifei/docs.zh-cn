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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266880"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="50610-102">Visual Basic 中的隐藏</span><span class="sxs-lookup"><span data-stu-id="50610-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="50610-103">当两个编程元素共享相同的名称时，其中一个元素可以隐藏或*隐藏*另一个。</span><span class="sxs-lookup"><span data-stu-id="50610-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="50610-104">在这种情况下，阴影元素不能供参考;相反，当代码使用元素名称时，Visual Basic 编译器会将其解析为隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="50610-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="50610-105">目的</span><span class="sxs-lookup"><span data-stu-id="50610-105">Purpose</span></span>  
 <span data-ttu-id="50610-106">阴影的主要目的是保护类成员的定义。</span><span class="sxs-lookup"><span data-stu-id="50610-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="50610-107">基类可能会经历一个更改，该更改创建与已定义的元素同名的元素。</span><span class="sxs-lookup"><span data-stu-id="50610-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="50610-108">如果发生这种情况，`Shadows`修改器将强制通过类的引用解析为您定义的成员，而不是新的基类元素。</span><span class="sxs-lookup"><span data-stu-id="50610-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="50610-109">阴影类型</span><span class="sxs-lookup"><span data-stu-id="50610-109">Types of Shadowing</span></span>  
 <span data-ttu-id="50610-110">元素可以通过两种不同的方式隐藏另一个元素。</span><span class="sxs-lookup"><span data-stu-id="50610-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="50610-111">阴影元素可以在包含阴影元素的区域的次区域内声明，在这种情况下，阴影*是通过作用域*完成的。</span><span class="sxs-lookup"><span data-stu-id="50610-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="50610-112">或者派生类可以重新定义基类的成员，在这种情况下，阴影*是通过继承*来完成的。</span><span class="sxs-lookup"><span data-stu-id="50610-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="50610-113">阴影范围</span><span class="sxs-lookup"><span data-stu-id="50610-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="50610-114">同一模块、类或结构中的编程元素可以具有相同的名称但范围不同。</span><span class="sxs-lookup"><span data-stu-id="50610-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="50610-115">以这种方式声明两个元素并且代码引用它们共享的名称时，具有较窄范围的元素会阴影另一个元素（块作用域是最窄的）。</span><span class="sxs-lookup"><span data-stu-id="50610-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="50610-116">例如，模块可以定义名为 的`Public``temp`变量，模块中的过程可以声明也命名为 的`temp`局部变量。</span><span class="sxs-lookup"><span data-stu-id="50610-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="50610-117">从过程`temp`内部对的引用访问局部变量，而从过程外部`temp`的引用访问`Public`该变量。</span><span class="sxs-lookup"><span data-stu-id="50610-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="50610-118">在这种情况下，过程变量`temp`对模块变量`temp`进行阴影。</span><span class="sxs-lookup"><span data-stu-id="50610-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="50610-119">下图显示了两个变量，这两个变量`temp`都命名为 。</span><span class="sxs-lookup"><span data-stu-id="50610-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="50610-120">当从其`temp`自己的过程中`p`访问成员`temp`变量时，局部变量将隐藏成员变量。</span><span class="sxs-lookup"><span data-stu-id="50610-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="50610-121">但是，`MyClass`关键字绕过阴影并访问成员变量。</span><span class="sxs-lookup"><span data-stu-id="50610-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![显示阴影范围的图形。](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="50610-123">有关在作用域中隐藏的示例，请参阅[如何：隐藏与变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="50610-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="50610-124">通过继承进行阴影</span><span class="sxs-lookup"><span data-stu-id="50610-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="50610-125">如果派生类重新定义从基类继承的编程元素，则重新定义元素将隐藏原始元素。</span><span class="sxs-lookup"><span data-stu-id="50610-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="50610-126">可以使用任何其他类型隐藏任何类型的声明元素或一组重载元素。</span><span class="sxs-lookup"><span data-stu-id="50610-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="50610-127">例如，`Integer`变量可以隐藏`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="50610-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="50610-128">如果使用另一个过程对过程进行阴影，则可以使用不同的参数列表和不同的返回类型。</span><span class="sxs-lookup"><span data-stu-id="50610-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="50610-129">下图显示了从`b``b`继承的基类和派生类`d`。</span><span class="sxs-lookup"><span data-stu-id="50610-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="50610-130">基类定义名为 的过程`proc`，派生类使用另一个同名过程来隐藏它。</span><span class="sxs-lookup"><span data-stu-id="50610-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="50610-131">第一`Call`个语句访问派生类中的`proc`阴影。</span><span class="sxs-lookup"><span data-stu-id="50610-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="50610-132">但是，`MyBase`关键字绕过阴影并访问基类中的隐藏过程。</span><span class="sxs-lookup"><span data-stu-id="50610-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![通过继承进行隐藏示意图](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="50610-134">有关通过继承进行阴影的示例，请参阅[如何：隐藏与变量同名的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)以及如何[：隐藏继承变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="50610-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="50610-135">阴影和访问级别</span><span class="sxs-lookup"><span data-stu-id="50610-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="50610-136">使用派生类的代码并不总是可以访问阴影元素。</span><span class="sxs-lookup"><span data-stu-id="50610-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="50610-137">例如，它可能声明`Private`。</span><span class="sxs-lookup"><span data-stu-id="50610-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="50610-138">在这种情况下，阴影将失败，编译器解析对如果没有阴影时的相同元素的任何引用。</span><span class="sxs-lookup"><span data-stu-id="50610-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="50610-139">此元素是从阴影类向后派生最少的可访问元素。</span><span class="sxs-lookup"><span data-stu-id="50610-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="50610-140">如果隐藏元素是过程，则分辨率是最接近的可访问版本，具有相同的名称、参数列表和返回类型。</span><span class="sxs-lookup"><span data-stu-id="50610-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="50610-141">下面的示例显示了三个类的继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="50610-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="50610-142">每个类定义一个`Sub`过程`display`，每个派生类在其基类`display`中隐藏该过程。</span><span class="sxs-lookup"><span data-stu-id="50610-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="50610-143">在前面的示例中，派生类`secondClass`阴影`display`带有一个`Private`过程。</span><span class="sxs-lookup"><span data-stu-id="50610-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="50610-144">当模块`callDisplay`调用`display``secondClass`时，调用代码位于外部`secondClass`，因此无法访问私有`display`过程。</span><span class="sxs-lookup"><span data-stu-id="50610-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="50610-145">隐藏将失败，编译器解析对基类`display`过程的引用。</span><span class="sxs-lookup"><span data-stu-id="50610-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="50610-146">但是，进一步的派生`thirdClass`类声明`display`为`Public`，因此 中`callDisplay`的代码可以访问它。</span><span class="sxs-lookup"><span data-stu-id="50610-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="50610-147">阴影和覆盖</span><span class="sxs-lookup"><span data-stu-id="50610-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="50610-148">不要混淆阴影和重写。</span><span class="sxs-lookup"><span data-stu-id="50610-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="50610-149">当派生类从基类继承时，两者都使用，并且都与另一个类重新定义一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="50610-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="50610-150">但两者之间存在显著差异。</span><span class="sxs-lookup"><span data-stu-id="50610-150">But there are significant differences between the two.</span></span> <span data-ttu-id="50610-151">有关比较，请参阅[阴影和覆盖之间的差异](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)。</span><span class="sxs-lookup"><span data-stu-id="50610-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="50610-152">阴影和重载</span><span class="sxs-lookup"><span data-stu-id="50610-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="50610-153">如果对派生类中具有多个元素的同一基类元素进行阴影，则阴影元素将成为该元素的重载版本。</span><span class="sxs-lookup"><span data-stu-id="50610-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="50610-154">有关更多信息，请参见 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="50610-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="50610-155">访问隐藏元素</span><span class="sxs-lookup"><span data-stu-id="50610-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="50610-156">当您从派生类访问元素时，通常通过派生类的当前实例，通过`Me`用 关键字限定元素名称来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="50610-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="50610-157">如果派生类对基类中的元素造成阴影，则可以通过使用`MyBase`关键字限定基类元素来访问该元素元素。</span><span class="sxs-lookup"><span data-stu-id="50610-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="50610-158">有关访问隐藏元素的示例，请参阅[如何：访问派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。</span><span class="sxs-lookup"><span data-stu-id="50610-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="50610-159">对象变量的声明</span><span class="sxs-lookup"><span data-stu-id="50610-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="50610-160">创建对象变量的方式还可以影响派生类是访问阴影元素还是隐影元素。</span><span class="sxs-lookup"><span data-stu-id="50610-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="50610-161">下面的示例从派生类创建两个对象，但一个对象声明为基类，另一个对象声明为派生类。</span><span class="sxs-lookup"><span data-stu-id="50610-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="50610-162">在前面的示例中，变量`basObj`声明为基类。</span><span class="sxs-lookup"><span data-stu-id="50610-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="50610-163">向其分配`dervCls`对象构成扩大转换，因此有效。</span><span class="sxs-lookup"><span data-stu-id="50610-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="50610-164">但是，基类无法访问派生类中变量`z`的隐藏版本，因此编译器解析`basObj.z`为原始基类值。</span><span class="sxs-lookup"><span data-stu-id="50610-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50610-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50610-165">See also</span></span>

- [<span data-ttu-id="50610-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="50610-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="50610-167">Visual Basic 中的范围</span><span class="sxs-lookup"><span data-stu-id="50610-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="50610-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="50610-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="50610-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="50610-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="50610-170">重写</span><span class="sxs-lookup"><span data-stu-id="50610-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="50610-171">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="50610-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="50610-172">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="50610-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
