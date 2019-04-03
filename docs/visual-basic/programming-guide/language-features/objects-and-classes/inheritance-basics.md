---
title: 继承的基础知识 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 5e4b8511145e758bf3d6328141be0e526965dccf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826569"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="acf0a-102">继承的基础知识 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acf0a-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="acf0a-103">`Inherits`语句用于声明一个名为的新类*派生类*基于现有类，称为*基类*。</span><span class="sxs-lookup"><span data-stu-id="acf0a-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="acf0a-104">派生的类继承，并可以扩展属性、 方法、 事件、 字段和基类中定义的常量。</span><span class="sxs-lookup"><span data-stu-id="acf0a-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="acf0a-105">以下部分介绍了一些有关继承的规则和修饰符可用于更改方式类继承，或将继承：</span><span class="sxs-lookup"><span data-stu-id="acf0a-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="acf0a-106">默认情况下，所有类都是可继承的除非标记为`NotInheritable`关键字。</span><span class="sxs-lookup"><span data-stu-id="acf0a-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="acf0a-107">从你的项目中的其他类或在你的项目引用其他程序集中的类，类可以继承。</span><span class="sxs-lookup"><span data-stu-id="acf0a-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="acf0a-108">与允许多个继承的语言，Visual Basic 只允许单个继承类; 中也就是说，派生的类可以有一个基类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="acf0a-109">虽然类中不允许多个继承，类可以实现多个接口，这样可以有效地实现相同目的。</span><span class="sxs-lookup"><span data-stu-id="acf0a-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="acf0a-110">若要防止公开限制在基类中的项，必须等于或高于其基本类派生的类的访问类型。</span><span class="sxs-lookup"><span data-stu-id="acf0a-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="acf0a-111">例如，`Public`类不能继承`Friend`或`Private`类，和一个`Friend`类不能继承`Private`类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="acf0a-112">继承修饰符</span><span class="sxs-lookup"><span data-stu-id="acf0a-112">Inheritance Modifiers</span></span>  
 <span data-ttu-id="acf0a-113">以下类级语句和修饰符以支持继承，引入了 Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="acf0a-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="acf0a-114">`Inherits` 语句-指定的基类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="acf0a-115">`NotInheritable` 修饰符，使程序员使用类作为基类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="acf0a-116">`MustInherit` 修饰符-指定类旨在用作仅基类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="acf0a-117">实例`MustInherit`类不能直接创建; 他们只能在创建的派生类作为基类的类实例。</span><span class="sxs-lookup"><span data-stu-id="acf0a-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="acf0a-118">(其他编程语言，如 c + + 和C#，使用术语*抽象类*来描述此类的类。)</span><span class="sxs-lookup"><span data-stu-id="acf0a-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="acf0a-119">属性和方法在派生类中的重写</span><span class="sxs-lookup"><span data-stu-id="acf0a-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="acf0a-120">默认情况下，派生的类从其基类中继承属性和方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="acf0a-121">如果继承的属性或方法的行为必须以不同的方式在派生类中它可以是*重写*。</span><span class="sxs-lookup"><span data-stu-id="acf0a-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="acf0a-122">也就是说，您可以在派生类中定义方法的新实现。</span><span class="sxs-lookup"><span data-stu-id="acf0a-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="acf0a-123">下列修饰符用于控制如何重写属性和方法：</span><span class="sxs-lookup"><span data-stu-id="acf0a-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="acf0a-124">`Overridable` -允许的属性或方法中的类在派生类中重写。</span><span class="sxs-lookup"><span data-stu-id="acf0a-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="acf0a-125">`Overrides` -重写`Overridable`属性或方法的基类中定义。</span><span class="sxs-lookup"><span data-stu-id="acf0a-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="acf0a-126">`NotOverridable` -防止属性或方法被重写继承的类中。</span><span class="sxs-lookup"><span data-stu-id="acf0a-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="acf0a-127">默认情况下`Public`方法都是`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="acf0a-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="acf0a-128">`MustOverride` -需要在派生的类重写属性或方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="acf0a-129">当`MustOverride`使用关键字、 方法定义组成只`Sub`， `Function`，或`Property`语句。</span><span class="sxs-lookup"><span data-stu-id="acf0a-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="acf0a-130">不允许任何其他语句，以及具体而言是没有`End Sub`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="acf0a-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="acf0a-131">`MustOverride` 方法必须声明为中`MustInherit`类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="acf0a-132">假设你想要定义要处理工资单类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="acf0a-133">可以定义一个泛型`Payroll`类，该类包含`RunPayroll`典型周计算工资单的方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="acf0a-134">然后，可以使用`Payroll`用作基类的更专业`BonusPayroll`类，该类可以分发雇员奖金时使用。</span><span class="sxs-lookup"><span data-stu-id="acf0a-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="acf0a-135">`BonusPayroll`类可以继承，并且重写，请`PayEmployee`基类中定义的方法`Payroll`类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="acf0a-136">下面的示例定义一个基类，`Payroll,`和派生的类`BonusPayroll`，这会重写继承的方法， `PayEmployee`。</span><span class="sxs-lookup"><span data-stu-id="acf0a-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="acf0a-137">一个过程中， `RunPayroll`，创建并随后将传递`Payroll`对象和一个`BonusPayroll`的函数对象`Pay`，用于执行`PayEmployee`这两个对象的方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="acf0a-138">MyBase 关键字</span><span class="sxs-lookup"><span data-stu-id="acf0a-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="acf0a-139">`MyBase`关键字的行为类似于一个类的当前实例的基类是指的对象变量。</span><span class="sxs-lookup"><span data-stu-id="acf0a-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="acf0a-140">`MyBase` 通常用于访问基类成员被重写或派生类中被隐藏。</span><span class="sxs-lookup"><span data-stu-id="acf0a-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="acf0a-141">具体而言，`MyBase.New`用于从派生的类构造函数中显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="acf0a-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="acf0a-142">例如，假设您要设计一个重写从基类继承的方法的派生的类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="acf0a-143">重写的方法可以调用基类中的方法，并修改返回的值，如下面的代码段中所示：</span><span class="sxs-lookup"><span data-stu-id="acf0a-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 <span data-ttu-id="acf0a-144">以下列表描述对使用的限制`MyBase`:</span><span class="sxs-lookup"><span data-stu-id="acf0a-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="acf0a-145">`MyBase` 是指直接基类和继承的成员。</span><span class="sxs-lookup"><span data-stu-id="acf0a-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="acf0a-146">不能用于访问`Private`类中的成员。</span><span class="sxs-lookup"><span data-stu-id="acf0a-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="acf0a-147">`MyBase` 是关键字，而不是真实对象。</span><span class="sxs-lookup"><span data-stu-id="acf0a-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="acf0a-148">`MyBase` 不能分配给一个变量，传递给过程，或者使用在`Is`比较。</span><span class="sxs-lookup"><span data-stu-id="acf0a-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="acf0a-149">该方法的`MyBase`限定无需在直接基类; 中定义而可能间接继承的基类中定义。</span><span class="sxs-lookup"><span data-stu-id="acf0a-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="acf0a-150">为了使由限定的引用`MyBase`正确编译，一些基类必须包含匹配的名称和类型的调用中出现的参数的方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="acf0a-151">不能使用`MyBase`调用`MustOverride`基类方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="acf0a-152">`MyBase` 不能用于限定本身。</span><span class="sxs-lookup"><span data-stu-id="acf0a-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="acf0a-153">因此，下面的代码不是有效的：</span><span class="sxs-lookup"><span data-stu-id="acf0a-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="acf0a-154">`MyBase` 不能在模块中使用。</span><span class="sxs-lookup"><span data-stu-id="acf0a-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="acf0a-155">`MyBase` 不能用于访问基类成员标记为`Friend`基类是否在不同的程序集。</span><span class="sxs-lookup"><span data-stu-id="acf0a-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="acf0a-156">有关详细信息和另一个示例，请参阅[如何：访问被派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。</span><span class="sxs-lookup"><span data-stu-id="acf0a-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="acf0a-157">MyClass 关键字</span><span class="sxs-lookup"><span data-stu-id="acf0a-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="acf0a-158">`MyClass`关键字的行为方式类似于最初实现的类的当前实例是指的对象变量。</span><span class="sxs-lookup"><span data-stu-id="acf0a-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="acf0a-159">`MyClass` 类似于`Me`，但对每个方法和属性调用`MyClass`被看作方法或属性是[NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)。</span><span class="sxs-lookup"><span data-stu-id="acf0a-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="acf0a-160">因此，该方法或属性是不受影响通过派生类中重写。</span><span class="sxs-lookup"><span data-stu-id="acf0a-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="acf0a-161">`MyClass` 是关键字，而不是真实对象。</span><span class="sxs-lookup"><span data-stu-id="acf0a-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="acf0a-162">`MyClass` 不能分配给一个变量，传递给过程，或者使用在`Is`比较。</span><span class="sxs-lookup"><span data-stu-id="acf0a-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="acf0a-163">`MyClass` 指包含类和其继承的成员。</span><span class="sxs-lookup"><span data-stu-id="acf0a-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="acf0a-164">`MyClass` 可以使用与为限定符`Shared`成员。</span><span class="sxs-lookup"><span data-stu-id="acf0a-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="acf0a-165">`MyClass` 无法在内部使用`Shared`方法，但可以使用实例方法内部来访问共享的成员的类。</span><span class="sxs-lookup"><span data-stu-id="acf0a-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="acf0a-166">`MyClass` 不能在标准模块中使用。</span><span class="sxs-lookup"><span data-stu-id="acf0a-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="acf0a-167">`MyClass` 可以用于限定基类中定义并具有在该类中提供的方法没有实现的方法。</span><span class="sxs-lookup"><span data-stu-id="acf0a-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="acf0a-168">此类引用与具有相同含义`MyBase.`*方法*。</span><span class="sxs-lookup"><span data-stu-id="acf0a-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="acf0a-169">下面的示例比较`Me`和`MyClass`。</span><span class="sxs-lookup"><span data-stu-id="acf0a-169">The following example compares `Me` and `MyClass`.</span></span>  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="acf0a-170">即使`derivedClass`重写`testMethod`，则`MyClass`中的关键字`useMyClass`使基类版本的调用无效的重写，而编译器解析效果`testMethod`。</span><span class="sxs-lookup"><span data-stu-id="acf0a-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf0a-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="acf0a-171">See also</span></span>

- [<span data-ttu-id="acf0a-172">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="acf0a-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="acf0a-173">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="acf0a-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
