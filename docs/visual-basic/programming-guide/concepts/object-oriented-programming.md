---
title: 面向对象的编程 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 058d8b932e50f784d4a5cefa9fadfb31953687f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153914"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="44a9f-102">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44a9f-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="44a9f-103">Visual Basic 为面向对象的编程，包括封装、 继承和多态性提供完整支持。</span><span class="sxs-lookup"><span data-stu-id="44a9f-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="44a9f-104">“封装”意味着将一组相关属性、方法和其他成员视为一个单元或对象。</span><span class="sxs-lookup"><span data-stu-id="44a9f-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="44a9f-105">“继承”描述基于现有类创建新类的能力。</span><span class="sxs-lookup"><span data-stu-id="44a9f-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="44a9f-106">多态性意味着可以有多个可互换使用的类，即使每个类以不同方式实现相同属性或方法。</span><span class="sxs-lookup"><span data-stu-id="44a9f-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="44a9f-107">本节介绍下列概念：</span><span class="sxs-lookup"><span data-stu-id="44a9f-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="44a9f-108">类和对象</span><span class="sxs-lookup"><span data-stu-id="44a9f-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="44a9f-109">类成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="44a9f-110">属性和字段</span><span class="sxs-lookup"><span data-stu-id="44a9f-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="44a9f-111">方法</span><span class="sxs-lookup"><span data-stu-id="44a9f-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="44a9f-112">构造函数</span><span class="sxs-lookup"><span data-stu-id="44a9f-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="44a9f-113">析构函数</span><span class="sxs-lookup"><span data-stu-id="44a9f-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="44a9f-114">事件</span><span class="sxs-lookup"><span data-stu-id="44a9f-114">Events</span></span>](#events)
    - [<span data-ttu-id="44a9f-115">嵌套的类</span><span class="sxs-lookup"><span data-stu-id="44a9f-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="44a9f-116">访问修饰符和访问级别</span><span class="sxs-lookup"><span data-stu-id="44a9f-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="44a9f-117">实例化类</span><span class="sxs-lookup"><span data-stu-id="44a9f-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="44a9f-118">共享的类和成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="44a9f-119">匿名类型</span><span class="sxs-lookup"><span data-stu-id="44a9f-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="44a9f-120">继承</span><span class="sxs-lookup"><span data-stu-id="44a9f-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="44a9f-121">重写成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="44a9f-122">接口</span><span class="sxs-lookup"><span data-stu-id="44a9f-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="44a9f-123">泛型</span><span class="sxs-lookup"><span data-stu-id="44a9f-123">Generics</span></span>](#generics)
- [<span data-ttu-id="44a9f-124">委托</span><span class="sxs-lookup"><span data-stu-id="44a9f-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="44a9f-125">类和对象</span><span class="sxs-lookup"><span data-stu-id="44a9f-125">Classes and objects</span></span>

<span data-ttu-id="44a9f-126">“类”和“对象”这两个术语有时互换使用，但实际上，类描述对象的“类型”，而对象是类的可用“实例”。</span><span class="sxs-lookup"><span data-stu-id="44a9f-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="44a9f-127">因此，创建对象的操作称为“实例化”。</span><span class="sxs-lookup"><span data-stu-id="44a9f-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="44a9f-128">如果使用蓝图类比，类是蓝图，对象就是基于该蓝图的建筑。</span><span class="sxs-lookup"><span data-stu-id="44a9f-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="44a9f-129">定义类：</span><span class="sxs-lookup"><span data-stu-id="44a9f-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="44a9f-130">Visual Basic 还提供了名为的类的轻量版本*结构*时您需要创建大量对象并执行一些有用不想要为此，占用过多内存。</span><span class="sxs-lookup"><span data-stu-id="44a9f-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="44a9f-131">定义结构：</span><span class="sxs-lookup"><span data-stu-id="44a9f-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="44a9f-132">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-132">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-133">Class 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="44a9f-134">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="44a9f-135">类成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-135">Class members</span></span>

<span data-ttu-id="44a9f-136">每个类都可以具有不同的“类成员”。类成员包括属性（用于描述类数据）、方法（用于定义类行为）和事件（用于在不同的类和对象之间提供通信）。</span><span class="sxs-lookup"><span data-stu-id="44a9f-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="44a9f-137">属性和字段</span><span class="sxs-lookup"><span data-stu-id="44a9f-137">Properties and fields</span></span>

<span data-ttu-id="44a9f-138">字段和属性表示对象包含的信息。</span><span class="sxs-lookup"><span data-stu-id="44a9f-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="44a9f-139">字段类似于变量，因为可以直接读取或设置它们。</span><span class="sxs-lookup"><span data-stu-id="44a9f-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="44a9f-140">定义字段：</span><span class="sxs-lookup"><span data-stu-id="44a9f-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="44a9f-141">属性具有 get 和 set 过程，它们对如何设置或返回值提供更多的控制。</span><span class="sxs-lookup"><span data-stu-id="44a9f-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="44a9f-142">Visual Basic 允许你创建私有字段来存储属性值，或者使用所谓的自动实现属性，创建此字段自动在后台，并为属性过程提供基本逻辑。</span><span class="sxs-lookup"><span data-stu-id="44a9f-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="44a9f-143">定义自动实现的属性：</span><span class="sxs-lookup"><span data-stu-id="44a9f-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="44a9f-144">如果你需要执行一些其他操作来读取和写入属性值，请定义一个用于存储属性值的字段，并提供用于存储和检索该字段的基本逻辑：</span><span class="sxs-lookup"><span data-stu-id="44a9f-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="44a9f-145">大多数属性的方法或过程都是既可以设置也可以获取属性值。</span><span class="sxs-lookup"><span data-stu-id="44a9f-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="44a9f-146">但你可以创建只读或只写属性来限制对它们的修改或读取。</span><span class="sxs-lookup"><span data-stu-id="44a9f-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="44a9f-147">在 Visual Basic 中，可以使用 `ReadOnly` 和 `WriteOnly` 关键字。</span><span class="sxs-lookup"><span data-stu-id="44a9f-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="44a9f-148">但是，自动实现的属性不能为只读或只写。</span><span class="sxs-lookup"><span data-stu-id="44a9f-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="44a9f-149">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-149">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-150">Property 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="44a9f-151">Get 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="44a9f-152">Set 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="44a9f-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="44a9f-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="44a9f-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="44a9f-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="44a9f-155">方法</span><span class="sxs-lookup"><span data-stu-id="44a9f-155">Methods</span></span>

 <span data-ttu-id="44a9f-156">“方法”是对象可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="44a9f-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="44a9f-157">在 Visual Basic 中，方法的创建途径有两种：如果方法不返回值，可使用 `Sub` 语句；如果方法返回值，可使用 `Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="44a9f-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="44a9f-158">定义类的方法：</span><span class="sxs-lookup"><span data-stu-id="44a9f-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="44a9f-159">对于同一方法，一个类可以有多个实现，也叫“重载”，这些实现的区别在于参数个数或参数类型的不同。</span><span class="sxs-lookup"><span data-stu-id="44a9f-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="44a9f-160">重载方法：</span><span class="sxs-lookup"><span data-stu-id="44a9f-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="44a9f-161">大多数情况下，方法是在类定义中声明的。</span><span class="sxs-lookup"><span data-stu-id="44a9f-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="44a9f-162">但是，Visual Basic 还支持*扩展方法*，可以将方法添加到现有类之外的类的实际定义。</span><span class="sxs-lookup"><span data-stu-id="44a9f-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="44a9f-163">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-163">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-164">Function 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="44a9f-165">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="44a9f-166">重载</span><span class="sxs-lookup"><span data-stu-id="44a9f-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="44a9f-167">扩展方法</span><span class="sxs-lookup"><span data-stu-id="44a9f-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="44a9f-168">构造函数</span><span class="sxs-lookup"><span data-stu-id="44a9f-168">Constructors</span></span>

<span data-ttu-id="44a9f-169">构造函数一种类方法，它们在创建给定类型的对象时自动执行。</span><span class="sxs-lookup"><span data-stu-id="44a9f-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="44a9f-170">构造函数通常用于初始化新对象的数据成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="44a9f-171">构造函数只能在创建类时运行一次。</span><span class="sxs-lookup"><span data-stu-id="44a9f-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="44a9f-172">此外，构造函数中的代码始终在类中所有其他代码之前运行。</span><span class="sxs-lookup"><span data-stu-id="44a9f-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="44a9f-173">但是，你可以按照为任何其他方法创建重载的方式，创建多个构造函数重载。</span><span class="sxs-lookup"><span data-stu-id="44a9f-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="44a9f-174">定义类的构造函数：</span><span class="sxs-lookup"><span data-stu-id="44a9f-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="44a9f-175">有关详细信息，请参见:[对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="44a9f-176">析构函数</span><span class="sxs-lookup"><span data-stu-id="44a9f-176">Destructors</span></span>

<span data-ttu-id="44a9f-177">析构函数用于析构类的实例。</span><span class="sxs-lookup"><span data-stu-id="44a9f-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="44a9f-178">在 .NET Framework 中，垃圾回收器自动管理应用程序中托管对象的内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="44a9f-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="44a9f-179">但是，你可能仍会需要析构函数来清理应用程序创建的所有非托管资源。</span><span class="sxs-lookup"><span data-stu-id="44a9f-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="44a9f-180">一个类只能有一个析构函数。</span><span class="sxs-lookup"><span data-stu-id="44a9f-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="44a9f-181">有关析构函数和 .NET Framework 垃圾回收的详细信息，请参阅[垃圾回收](../../../standard/garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="44a9f-182">事件</span><span class="sxs-lookup"><span data-stu-id="44a9f-182">Events</span></span>

<span data-ttu-id="44a9f-183">类或对象可以通过事件向其他类或对象通知发生的相关事情。</span><span class="sxs-lookup"><span data-stu-id="44a9f-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="44a9f-184">发送（或引发）事件的类称为“发行者”，接收（或处理）事件的类称为“订户”。</span><span class="sxs-lookup"><span data-stu-id="44a9f-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="44a9f-185">有关事件以及如何引发和处理事件的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="44a9f-186">若要声明事件，请使用[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="44a9f-187">若要引发事件，请使用[RaiseEvent 语句](../../../visual-basic/language-reference/statements/raiseevent-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="44a9f-188">若要指定事件处理程序声明的方式，请使用[WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)语句和[处理](../../../visual-basic/language-reference/statements/handles-clause.md)子句。</span><span class="sxs-lookup"><span data-stu-id="44a9f-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="44a9f-189">若要能够动态地添加、 删除和更改与事件关联的事件处理程序，请使用[AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)并[RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md)一起使用[AddressOf运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="44a9f-190">嵌套的类</span><span class="sxs-lookup"><span data-stu-id="44a9f-190">Nested classes</span></span>

<span data-ttu-id="44a9f-191">在另一个类中定义的类称为“嵌套”。</span><span class="sxs-lookup"><span data-stu-id="44a9f-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="44a9f-192">默认情况下，嵌套类是私有类。</span><span class="sxs-lookup"><span data-stu-id="44a9f-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="44a9f-193">若要创建嵌套类的实例，请使用容器类的名称，后接一个点，再接嵌套类的名称：</span><span class="sxs-lookup"><span data-stu-id="44a9f-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="44a9f-194">访问修饰符和访问级别</span><span class="sxs-lookup"><span data-stu-id="44a9f-194">Access modifiers and access levels</span></span>

<span data-ttu-id="44a9f-195">所有类和类方法都可以使用“访问修饰符”指定自己为其他类提供的访问级别。</span><span class="sxs-lookup"><span data-stu-id="44a9f-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="44a9f-196">可用的访问修饰符有以下这些：</span><span class="sxs-lookup"><span data-stu-id="44a9f-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="44a9f-197">Visual Basic 修饰符</span><span class="sxs-lookup"><span data-stu-id="44a9f-197">Visual Basic Modifier</span></span>|<span data-ttu-id="44a9f-198">定义</span><span class="sxs-lookup"><span data-stu-id="44a9f-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="44a9f-199">Public</span><span class="sxs-lookup"><span data-stu-id="44a9f-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="44a9f-200">同一程序集中的任何其他代码或引用该程序集的其他程序集都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="44a9f-201">Private</span><span class="sxs-lookup"><span data-stu-id="44a9f-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="44a9f-202">只有同一类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="44a9f-203">Protected</span><span class="sxs-lookup"><span data-stu-id="44a9f-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="44a9f-204">只有同一类或派生类中的代码可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="44a9f-205">Friend</span><span class="sxs-lookup"><span data-stu-id="44a9f-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="44a9f-206">同一程序集中的任何代码都可以访问该类型或成员，但其他程序集中的代码不可以。</span><span class="sxs-lookup"><span data-stu-id="44a9f-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="44a9f-207">同一程序集中的任何代码或其他程序集中的任何派生类都可以访问该类型或成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="44a9f-208">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="44a9f-209">实例化类</span><span class="sxs-lookup"><span data-stu-id="44a9f-209">Instantiating classes</span></span>

<span data-ttu-id="44a9f-210">若要创建对象，你需要实例化类，即创建类实例。</span><span class="sxs-lookup"><span data-stu-id="44a9f-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="44a9f-211">实例化类之后，可以为该实例的属性和字段赋值，还可以调用类方法。</span><span class="sxs-lookup"><span data-stu-id="44a9f-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="44a9f-212">若要在类的实例化过程中为属性赋值，请使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="44a9f-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="44a9f-213">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-213">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-214">New 运算符</span><span class="sxs-lookup"><span data-stu-id="44a9f-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="44a9f-215">对象初始值设定项：命名和匿名类型</span><span class="sxs-lookup"><span data-stu-id="44a9f-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="44a9f-216">共享的类和成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-216">Shared classes and members</span></span>

 <span data-ttu-id="44a9f-217">类的共享的成员是类的属性、 过程或字段的所有实例共享。</span><span class="sxs-lookup"><span data-stu-id="44a9f-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="44a9f-218">若要定义的共享的成员：</span><span class="sxs-lookup"><span data-stu-id="44a9f-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="44a9f-219">若要访问共享的成员，而无需创建此类的对象使用的类的名称：</span><span class="sxs-lookup"><span data-stu-id="44a9f-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="44a9f-220">在 Visual Basic 中的共享的模块共享了仅限成员并不能实例化。</span><span class="sxs-lookup"><span data-stu-id="44a9f-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="44a9f-221">共享的成员也不能访问非共享的属性、 字段或方法</span><span class="sxs-lookup"><span data-stu-id="44a9f-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="44a9f-222">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-222">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-223">Shared</span><span class="sxs-lookup"><span data-stu-id="44a9f-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="44a9f-224">Module 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="44a9f-225">匿名类型</span><span class="sxs-lookup"><span data-stu-id="44a9f-225">Anonymous types</span></span>

<span data-ttu-id="44a9f-226">匿名类型使你无需为数据类型编写类定义即可创建对象。</span><span class="sxs-lookup"><span data-stu-id="44a9f-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="44a9f-227">此时，编译器将为你生成类。</span><span class="sxs-lookup"><span data-stu-id="44a9f-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="44a9f-228">该类没有可使用的名称，且包含在声明对象时指定的属性。</span><span class="sxs-lookup"><span data-stu-id="44a9f-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="44a9f-229">创建匿名类型的实例：</span><span class="sxs-lookup"><span data-stu-id="44a9f-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="44a9f-230">有关详细信息，请参见:[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="44a9f-231">继承</span><span class="sxs-lookup"><span data-stu-id="44a9f-231">Inheritance</span></span>

<span data-ttu-id="44a9f-232">通过继承，可以创建一个新类，它重用、扩展和修改另一个类中定义的行为。</span><span class="sxs-lookup"><span data-stu-id="44a9f-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="44a9f-233">其成员被继承的类称为“基类”，继承这些成员的类称为“派生类”。</span><span class="sxs-lookup"><span data-stu-id="44a9f-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="44a9f-234">但是，在 Visual Basic 中的所有类隐式都继承自<xref:System.Object>类，该类支持.NET 类层次结构，并向所有类提供低级服务。</span><span class="sxs-lookup"><span data-stu-id="44a9f-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="44a9f-235">Visual Basic 不支持多重继承。</span><span class="sxs-lookup"><span data-stu-id="44a9f-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="44a9f-236">即，只能为一个派生类指定一个基类。</span><span class="sxs-lookup"><span data-stu-id="44a9f-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="44a9f-237">从基类继承：</span><span class="sxs-lookup"><span data-stu-id="44a9f-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="44a9f-238">默认情况下，可以继承所有类。</span><span class="sxs-lookup"><span data-stu-id="44a9f-238">By default all classes can be inherited.</span></span> <span data-ttu-id="44a9f-239">但你可以指定不得将某个类用作基类，也可以创建只能用作基类的类。</span><span class="sxs-lookup"><span data-stu-id="44a9f-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="44a9f-240">指定不得将某个类用作基类：</span><span class="sxs-lookup"><span data-stu-id="44a9f-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="44a9f-241">指定只能用作基类且无法实例化的类：</span><span class="sxs-lookup"><span data-stu-id="44a9f-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="44a9f-242">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-242">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-243">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="44a9f-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="44a9f-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="44a9f-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="44a9f-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="44a9f-246">重写成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-246">Overriding members</span></span>

<span data-ttu-id="44a9f-247">默认情况下，派生类继承其基类的所有成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="44a9f-248">若希望更改继承成员的行为，则需要重写该成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="44a9f-249">即，可以在派生类中定义方法、属性或事件的新实现。</span><span class="sxs-lookup"><span data-stu-id="44a9f-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="44a9f-250">下列修饰符用于控制如何重写属性和方法：</span><span class="sxs-lookup"><span data-stu-id="44a9f-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="44a9f-251">Visual Basic 修饰符</span><span class="sxs-lookup"><span data-stu-id="44a9f-251">Visual Basic Modifier</span></span>|<span data-ttu-id="44a9f-252">定义</span><span class="sxs-lookup"><span data-stu-id="44a9f-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="44a9f-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="44a9f-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="44a9f-254">允许在派生类中重写类成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="44a9f-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="44a9f-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="44a9f-256">重写基类中定义的虚拟（可重写）成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="44a9f-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="44a9f-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="44a9f-258">禁止在继承类中重写成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="44a9f-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="44a9f-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="44a9f-260">要求在派生类中重写类成员。</span><span class="sxs-lookup"><span data-stu-id="44a9f-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="44a9f-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="44a9f-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="44a9f-262">隐藏继承自基类的成员</span><span class="sxs-lookup"><span data-stu-id="44a9f-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="44a9f-263">接口</span><span class="sxs-lookup"><span data-stu-id="44a9f-263">Interfaces</span></span>

<span data-ttu-id="44a9f-264">和类一样，接口也定义了一系列属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="44a9f-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="44a9f-265">但与类不同的是，接口并不提供实现。</span><span class="sxs-lookup"><span data-stu-id="44a9f-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="44a9f-266">它们由类来实现，并从类中被定义为单独的实体。</span><span class="sxs-lookup"><span data-stu-id="44a9f-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="44a9f-267">接口表示一种约定，实现接口的类必须严格按其定义来实现接口的每个方面。</span><span class="sxs-lookup"><span data-stu-id="44a9f-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="44a9f-268">定义接口：</span><span class="sxs-lookup"><span data-stu-id="44a9f-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="44a9f-269">在类中实现接口：</span><span class="sxs-lookup"><span data-stu-id="44a9f-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="44a9f-270">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-270">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-271">接口</span><span class="sxs-lookup"><span data-stu-id="44a9f-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="44a9f-272">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="44a9f-273">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="44a9f-274">泛型</span><span class="sxs-lookup"><span data-stu-id="44a9f-274">Generics</span></span>

<span data-ttu-id="44a9f-275">类、 结构、 接口和.NET 中的方法可以包括*类型参数*定义类型的对象，它们可以存储或使用。</span><span class="sxs-lookup"><span data-stu-id="44a9f-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="44a9f-276">最常见的泛型示例是集合，从中可以指定要存储在集合中的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="44a9f-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="44a9f-277">定义泛型类：</span><span class="sxs-lookup"><span data-stu-id="44a9f-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="44a9f-278">创建泛型类的实例：</span><span class="sxs-lookup"><span data-stu-id="44a9f-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="44a9f-279">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-279">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-280">泛型</span><span class="sxs-lookup"><span data-stu-id="44a9f-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="44a9f-281">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="44a9f-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="44a9f-282">委托</span><span class="sxs-lookup"><span data-stu-id="44a9f-282">Delegates</span></span>

 <span data-ttu-id="44a9f-283">“委托”是一种类型，它定义方法签名，可以提供对具有兼容签名的任何方法的引用。</span><span class="sxs-lookup"><span data-stu-id="44a9f-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="44a9f-284">你可以通过委托调用方法。</span><span class="sxs-lookup"><span data-stu-id="44a9f-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="44a9f-285">委托用于将方法作为参数传递给其他方法。</span><span class="sxs-lookup"><span data-stu-id="44a9f-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="44a9f-286">事件处理程序就是通过委托调用的方法。</span><span class="sxs-lookup"><span data-stu-id="44a9f-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="44a9f-287">有关在事件处理中使用委托的详细信息，请参阅[事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="44a9f-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="44a9f-288">创建委托：</span><span class="sxs-lookup"><span data-stu-id="44a9f-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="44a9f-289">创建对与委托指定的签名相匹配的方法的引用：</span><span class="sxs-lookup"><span data-stu-id="44a9f-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="44a9f-290">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="44a9f-290">For more information, see:</span></span>

- [<span data-ttu-id="44a9f-291">委托</span><span class="sxs-lookup"><span data-stu-id="44a9f-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="44a9f-292">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="44a9f-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="44a9f-293">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="44a9f-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="44a9f-294">请参阅</span><span class="sxs-lookup"><span data-stu-id="44a9f-294">See also</span></span>

- [<span data-ttu-id="44a9f-295">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="44a9f-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
