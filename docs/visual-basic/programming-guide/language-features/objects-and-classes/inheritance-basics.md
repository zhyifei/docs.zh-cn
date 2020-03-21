---
title: 继承的基础知识
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
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401459"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="81bbd-102">继承的基础知识 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81bbd-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="81bbd-103">该`Inherits`语句用于根据称为*基类*的新类（称为*派生类*）声明新类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="81bbd-104">派生类继承并可以扩展基类中定义的属性、方法、事件、字段和常量。</span><span class="sxs-lookup"><span data-stu-id="81bbd-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="81bbd-105">以下部分介绍继承的一些规则，以及可用于更改类继承或继承方式的修改器：</span><span class="sxs-lookup"><span data-stu-id="81bbd-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="81bbd-106">默认情况下，除非用 关键字标记，否则所有类都是`NotInheritable`可继承的。</span><span class="sxs-lookup"><span data-stu-id="81bbd-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="81bbd-107">类可以从项目中的其他类或项目引用的其他程序集中的类继承。</span><span class="sxs-lookup"><span data-stu-id="81bbd-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="81bbd-108">与允许多重继承的语言不同，Visual Basic 只允许在类中进行单个继承;也就是说，派生类只能有一个基类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="81bbd-109">尽管类中不允许多次继承，但类可以实现多个接口，从而有效地实现相同的目的。</span><span class="sxs-lookup"><span data-stu-id="81bbd-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="81bbd-110">为了防止在基类中公开受限制项，派生类的访问类型必须等于或比其基类更具限制性。</span><span class="sxs-lookup"><span data-stu-id="81bbd-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="81bbd-111">`Public`例如，类不能继承 或`Friend``Private`类，并且`Friend`类不能继承类。 `Private`</span><span class="sxs-lookup"><span data-stu-id="81bbd-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="81bbd-112">继承修改器</span><span class="sxs-lookup"><span data-stu-id="81bbd-112">Inheritance Modifiers</span></span>

<span data-ttu-id="81bbd-113">Visual Basic 引入了以下类级语句和修改器来支持继承：</span><span class="sxs-lookup"><span data-stu-id="81bbd-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="81bbd-114">`Inherits`语句 = 指定基类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="81bbd-115">`NotInheritable`修改器 = 防止程序员将类用作基类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="81bbd-116">`MustInherit`修改器 = 指定类仅用于基类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="81bbd-117">不能直接创建`MustInherit`类的实例;因此，无法直接创建类的实例。它们只能创建为派生类的基类实例。</span><span class="sxs-lookup"><span data-stu-id="81bbd-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="81bbd-118">（其他编程语言（如C++和 C#）使用术语*抽象类*来描述此类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="81bbd-119">派生类中的重写属性和方法</span><span class="sxs-lookup"><span data-stu-id="81bbd-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="81bbd-120">默认情况下，派生类继承其基类的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="81bbd-121">如果继承的属性或方法在派生类中的行为不同，则可以*重写*它。</span><span class="sxs-lookup"><span data-stu-id="81bbd-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="81bbd-122">也就是说，您可以在派生类中定义方法的新实现。</span><span class="sxs-lookup"><span data-stu-id="81bbd-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="81bbd-123">下列修饰符用于控制如何重写属性和方法：</span><span class="sxs-lookup"><span data-stu-id="81bbd-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="81bbd-124">`Overridable`• 允许在派生类中重写类中的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="81bbd-125">`Overrides`• 重写基`Overridable`类中定义的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="81bbd-126">`NotOverridable`• 防止在继承类中重写属性或方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="81bbd-127">默认情况下，`Public`方法为`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="81bbd-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="81bbd-128">`MustOverride`• 要求派生类重写属性或方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="81bbd-129">使用`MustOverride`关键字时，方法定义仅包含`Sub`。 `Function`。 `Property`</span><span class="sxs-lookup"><span data-stu-id="81bbd-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="81bbd-130">不允许任何其他语句，特别是没有`End Sub`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="81bbd-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="81bbd-131">`MustOverride`方法必须在类中`MustInherit`声明。</span><span class="sxs-lookup"><span data-stu-id="81bbd-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="81bbd-132">假设您要定义要处理工资单的类。</span><span class="sxs-lookup"><span data-stu-id="81bbd-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="81bbd-133">您可以定义一个泛`Payroll`型类，其中包含计算`RunPayroll`典型星期的工资单的方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="81bbd-134">然后，您可以将用作`Payroll`更专业`BonusPayroll`类的基类，该类可用于分发员工奖金。</span><span class="sxs-lookup"><span data-stu-id="81bbd-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="81bbd-135">类`BonusPayroll`可以继承和重写基`PayEmployee``Payroll`类中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="81bbd-136">下面的示例定义基类`Payroll,`和派生类 ，`BonusPayroll`它重写继承的方法 。 `PayEmployee`</span><span class="sxs-lookup"><span data-stu-id="81bbd-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="81bbd-137">过程 ，`RunPayroll``Payroll`创建，然后将对象和`BonusPayroll`对象传递给一个函数 ，`Pay`执行两个对象`PayEmployee`的方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="81bbd-138">MyBase 关键字</span><span class="sxs-lookup"><span data-stu-id="81bbd-138">The MyBase Keyword</span></span>

<span data-ttu-id="81bbd-139">关键字`MyBase`的作用类似于引用类当前实例的基类的对象变量。</span><span class="sxs-lookup"><span data-stu-id="81bbd-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="81bbd-140">`MyBase`通常用于访问派生类中重写或隐藏基类成员。</span><span class="sxs-lookup"><span data-stu-id="81bbd-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="81bbd-141">特别是，`MyBase.New`用于从派生类构造函数显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="81bbd-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="81bbd-142">例如，假设您正在设计一个派生类，该类重写从基类继承的方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="81bbd-143">重写方法可以在基类中调用 方法并修改返回值，如以下代码片段所示：</span><span class="sxs-lookup"><span data-stu-id="81bbd-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="81bbd-144">下面的列表描述了对 使用`MyBase`的限制：</span><span class="sxs-lookup"><span data-stu-id="81bbd-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="81bbd-145">`MyBase`指直接基类及其继承成员。</span><span class="sxs-lookup"><span data-stu-id="81bbd-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="81bbd-146">它不能用于访问`Private`类中的成员。</span><span class="sxs-lookup"><span data-stu-id="81bbd-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="81bbd-147">`MyBase`是关键字，而不是真实对象。</span><span class="sxs-lookup"><span data-stu-id="81bbd-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="81bbd-148">`MyBase`不能分配给变量、传递给过程或用于`Is`比较。</span><span class="sxs-lookup"><span data-stu-id="81bbd-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="81bbd-149">`MyBase`限定的方法不必在直接基类中定义;它可以在间接继承的基类中定义。</span><span class="sxs-lookup"><span data-stu-id="81bbd-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="81bbd-150">为了使 引用`MyBase`具有正确的编译，某些基类必须包含一个方法，匹配调用中显示的参数的名称和类型。</span><span class="sxs-lookup"><span data-stu-id="81bbd-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="81bbd-151">不能使用`MyBase`调用`MustOverride`基类方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="81bbd-152">`MyBase`不能用来限定自己。</span><span class="sxs-lookup"><span data-stu-id="81bbd-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="81bbd-153">因此，以下代码无效：</span><span class="sxs-lookup"><span data-stu-id="81bbd-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="81bbd-154">`MyBase`不能在模块中使用。</span><span class="sxs-lookup"><span data-stu-id="81bbd-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="81bbd-155">`MyBase`不能用于访问标记为`Friend`基类的基类成员，因为基类位于其他程序集中。</span><span class="sxs-lookup"><span data-stu-id="81bbd-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="81bbd-156">有关详细信息和另一个示例，请参阅[如何：访问派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。</span><span class="sxs-lookup"><span data-stu-id="81bbd-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="81bbd-157">MyClass 关键字</span><span class="sxs-lookup"><span data-stu-id="81bbd-157">The MyClass Keyword</span></span>

<span data-ttu-id="81bbd-158">关键字`MyClass`的作用类似于对象变量，该变量引用最初实现的类的当前实例。</span><span class="sxs-lookup"><span data-stu-id="81bbd-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="81bbd-159">`MyClass`类似于`Me`，但每个方法和属性调用`MyClass`都被视为方法或属性[不是可重写的](../../../../visual-basic/language-reference/modifiers/notoverridable.md)。</span><span class="sxs-lookup"><span data-stu-id="81bbd-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="81bbd-160">因此，方法或属性不受派生类中重写的影响。</span><span class="sxs-lookup"><span data-stu-id="81bbd-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="81bbd-161">`MyClass`是关键字，而不是真实对象。</span><span class="sxs-lookup"><span data-stu-id="81bbd-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="81bbd-162">`MyClass`不能分配给变量、传递给过程或用于`Is`比较。</span><span class="sxs-lookup"><span data-stu-id="81bbd-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="81bbd-163">`MyClass`引用包含类及其继承成员。</span><span class="sxs-lookup"><span data-stu-id="81bbd-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="81bbd-164">`MyClass`可用作成员的`Shared`限定符。</span><span class="sxs-lookup"><span data-stu-id="81bbd-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="81bbd-165">`MyClass`不能在`Shared`方法内使用，但可以在实例方法内访问类的共享成员。</span><span class="sxs-lookup"><span data-stu-id="81bbd-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="81bbd-166">`MyClass`不能在标准模块中使用。</span><span class="sxs-lookup"><span data-stu-id="81bbd-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="81bbd-167">`MyClass`可用于限定在基类中定义且没有该类中提供的方法的实现的方法。</span><span class="sxs-lookup"><span data-stu-id="81bbd-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="81bbd-168">这种引用与`MyBase.`*方法*的含义相同。</span><span class="sxs-lookup"><span data-stu-id="81bbd-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="81bbd-169">下面的示例比较`Me`和`MyClass`。</span><span class="sxs-lookup"><span data-stu-id="81bbd-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="81bbd-170">`derivedClass`即使重写`testMethod`，`MyClass`中的`useMyClass`关键字将取消重写的效果，编译器解析对 基类版本的`testMethod`调用。</span><span class="sxs-lookup"><span data-stu-id="81bbd-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="81bbd-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81bbd-171">See also</span></span>

- [<span data-ttu-id="81bbd-172">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="81bbd-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="81bbd-173">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="81bbd-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
